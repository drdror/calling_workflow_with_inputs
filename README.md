# Pass between Workflow and Action

Here you can find a minimal example how to define an action that's being used in the same repo.
Furthermore, the calling workflow passes information to the action which in turn returns a processed answer to the caller.
Lastly, be careful, in this example the action unmasks the secret passed from the caller!
In general you probably do not want to do it.

## Bonus

When polishing this example, I used [`act`](https://nektosact.com/usage/index.html) which is very helpful.
Basically, assuming you have `docker` installed, you can simply run something like:

```bash
act -p -r --var SOME_VAR="and here is a variable" -s SOME_SECRET="this_is_my_secret"
```

and the workflow(s) can be executed locally.
Note that in [`.actrc`](./.actrc) I included the following:

```
--container-architecture=linux/amd64
```

Which can also be passed directly to the call to `act`.
