# ng-inline-styles-loader
A simple webpack loader for inlined stylesheets of angular components (designed for people who like small components with inlined styles).

Currently this loader supports minification by using [clean-css](https://github.com/jakubpawlowicz/clean-css) and adds vendor prefixes with [autoprefixer](https://github.com/postcss/autoprefixer).

## install
`npm install ng-inline-styles-loader --save-dev`

## example usage
chain the `ng-inline-styles-loader` to your currently used typescript loader:

```js
loaders: ['awesome-typescript-loader', 'ng-inline-styles-loader'],
```

with options (disables minfication and prefixing ... very senseless example IMHO):

```js
loaders: ['awesome-typescript-loader', 'ng-inline-styles-loader?minify=false&prefix=false'],
```

with autoprefixer options (no prefixes for flexbox properties):

```js
loaders: ['awesome-typescript-loader', 'ng-inline-styles-loader?flexbox=false'],
```

You can see all available options for autoprefixer [here](https://github.com/postcss/autoprefixer#options) (but of course I have not tested all of them).

## bugs
I've already added some unit tests that worked for my current angular projects (very large non-optimized non-aot-compiled bundles with a f**ton of components) but I'm really sure that my regular expressions do suck.
So feel free to add bug reports with your actual angular component and the expected result.
Pull requests are also accepted if I like your avatar.