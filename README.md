# S3t: shortify npm commands and run them quickly

S3t is a small tool (no dependencies, 50 lines of code) to run npm commands faster.

## The problem

We developers have a very short memory.

If autocomplete is not available, then we can memorize at most few characters.

S3t helps you transform long npm commands in shorter ones, transforming parameters into template parts.

## How does it work?

Suppose you often type a command like the following one:

```
ng generate component src/module/components my-component
```

What if you can achieve the same result with:

```
npm run new:c  
```

You can _shortify_ the command above in your `package.json` like in the example below:

```json
"new:c": "npx s3t \"ng generate component src/module/components $component\" --"
```

Note that the parameter `my-component` is now a parameter of the _template_.

When you run it, it will ask for the component name and then launch your original command.

```
npm run new:c
```

Anyway, you can specify the component name inline too:

```
npm run new:c my-component
```
