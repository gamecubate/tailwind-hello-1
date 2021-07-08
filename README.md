1. Create tailwind.config.js: `npx -i tailwindcss`

2. Configure tailwind.config.js:
```
module.exports = {
  purge: [
    './**/*.html'
  ],
  theme: {},
  variants: {},
  plugins: [],
}
```

3. Create infile.css:
```
@tailwind base;
@tailwind components;
@tailwind utilities;
```

4. Watch for changes: `$ npx tailwindcss -i infile.css -o outfile.css --watch`

5. index.html:
```
<!doctype html>
<html>
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <link href="./outfile.css" rel="stylesheet">
</head>
<body>
  <h1 class="font-bold text-5xl text-red-500">TAILWIND-CSS</h1>
</body>
</html>
```

6. Refactor classes as components:
```
// infile.css
@tailwind base;
@tailwind components;
@tailwind utilities;
@layer components {
  .my-title {
    @apply font-bold text-5xl text-red-500;
  }
}
```

7. Update index.html:
```
<h1 class="my-title"> TAILWIND-CSS</h1>
```

7. When ready to deploy hence optimize: `NODE_ENV=production npx tailwindcss  -i infile.css -o outfile.css`
