# S3t: shortify npm commands and run them quickly

S3t is a small tool (no dependencies, 50 lines of code) to run npm commands faster.

Suppose you often type a command like the following one:

```
ng generate component src/module/components my-component
```

What if you can achieve the same result with:

```
npm run new:c my-component  
```

You can then _shortify_ and make it a template like below:

```
npx s3t \"ng generate component src/module/components $component\" -- 
```

Now you can put it in your `package.json` like in the example below:

```json

"new:c": "npx s3t \"ng generate component src/module/components $component\" --"

```

When you run it, it will ask for the component name and then launch your original command.

```
npm run new:c
```

Note that you can specify the component name inline:

```
npm run new:c my-component
```
