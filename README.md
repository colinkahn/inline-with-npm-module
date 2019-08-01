# Inline Resource with `:npm-module` Target

## Issue

Using `shadow.resource/inline` with the `:browser` target correctly recompiles
the file it's used in when the resource is changed. This doesn't happen when
using the `:npm-module` target.

## To reproduce

```
npx shadow-cljs watch :project
```

Once compiled run:

```
node ./out/project.core.js
```

This logs the contents of `src/project/test.json`:

```
{message: "Hello World!"}
```

Edit and save `src/project/test.json`. You'll see the watch trigger and compile.

Run this again:

```
node ./out/project.core.js
```

You'll see the same output as before.
