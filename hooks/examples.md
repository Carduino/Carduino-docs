# Hook examples

There are many ways in which hooks can be used. Below are some short examples how that show how to quickly add useful functionality to a service. The [authentication chapter](../authentication/readme.md) has more examples on how to use hooks for user authorization.

## Created/Updated at

If the [database adapter](../databases/readme.md) does not support it already, timestamps can be easily added as a *before* hook like this:

```js
app.service('todos').before({
  create(hook) {
    hook.data.created_at = new Date();
  },
  
  update(hook) {
    hook.data.updated_at = new Date();
  },
  
  patch(hook) {
    hook.data.updated_at = new Date();
  }
})
```

## Fetching related items

Hooks can also be used to fetch related items from other services. The following hook checks for a `related` query parameter in `get` and if it exists, includes all todos for the user in the response:

```js
app.service('users').after({
  get(hook) {
    // The user id
    const id = hook.result.id;
    
    if(hook.params.query.related) {
      return hook.app.service('todos').find({
        query: { user_id: id }
      }).then(todos => {
        // Set the todos on the user property
        hook.result.todos = todos;
        // Always return the hook object or `undefined`
        return hook;
      });
    }
  }
});
```

## Soft delete

Sometimes you might not want to actually delete items in the database but just mark them as deleted. We can do this by adding a `remove` *before* hook, marking the todo as deleted and then setting `hook.result`. That way we can completely skip the original service method.

```js
app.service('todos').before({
  remove(hook) {
    // Instead of calling the service remote, call `patch` and set deleted to `true`
    return this.patch(hook.id, { deleted: true }, hook.params).then(data => {
      // Set the result from `patch` as the method call result
      hook.result = data;
      // Always return the hook or `undefined`
      return hook;
    });
  },
  
  find(hook) {
    // Only query items that have not been marked as deleted
    hook.params.query.deleted = { $ne: true };
  }
});
```

> __Note:__ Setting `hook.result` will only skip the actual method. *after* hooks will still run in the order they have been registered.
