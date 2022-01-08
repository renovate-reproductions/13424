# 13424

Minimal reproduction for [issue 13424 on main Renovate repository](https://github.com/renovatebot/renovate/issues/13424).

## Current behavior

If there is a comment behind the version number, it will get clobbered in the Renovate PR that updates the version number:

```yaml
    steps:
      - name: Checkout repository
        uses: actions/checkout@v2 # if (isNotFork) <--- This comment will get clobbered
```

## Expected behavior

Renovate should probably only update the version number of the linked action, and keep the comment as-is:

```yaml
    steps:
      - name: Checkout repository
        uses: actions/checkout@v2 # if (isNotFork) <--- Keep comment as-is
```
