## SASS

[Home](../README.md) 

[Reference](https://sass-lang.com/guide)  

[Installation](https://sass-lang.com/install)  

[CheatSheet](https://devhints.io/sass)

[Sass in Django](https://github.com/jrief/django-sass-processor#introduction)  
[Nextjs component and globas css](https://nextjs.org/blog/next-9-3#built-in-sass-css-module-support-for-component-level-styles)  

 - npm install sass
 - create pages/_app.js
 - copy and paste the contents from the blog
 - apply it globally (for this you will have to build again)
 - after that your modularization works well as well

You can also use - bootstrap, bulma, tailwindcss, skeleton, material ui.

In terminal:
-npx create-next-app my_app-tailwind
- choose with-tailwindcss
- this will add postcss.config.js  and tailwind.config.js

copy from the config files and the dev dependencies
```
CREATE /tailwind.config.js

module.exports = {
  purge: ['./components/**/*.{js,ts,jsx,tsx}', './pages/**/*.{js,ts,jsx,tsx}'],
  theme: {
    extend: {},
  },
  variants: {},
  plugins: [],
}
```

```
ADD this to /package.json

  "devDependencies": {
    "postcss-preset-env": "^6.7.0",
    "tailwindcss": "^1.4.0"
  }
```

```
CREATE /postcss.config.js

module.exports = {
  plugins: ['tailwindcss', 'postcss-preset-env'],
}
```

grab everything from index.css related to the tailwind
```
IN TERMINAL
npm i
npm run dev
```
```
ADD to the styles.scss

at the bottom of the page:
@tailwind utilities;
```
```
at the top of the page
@tailwind base;
@tailwind components;
```