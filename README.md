# notes-careertrack-26.m
## Webpacks
* Webpacks started because web pages became more advanced than just the JS, HTML, and CSS. The files were getting too big and complex.
* Webpacks were made to help create an easier development experience for getting libraries and frameworks. 
* Browsers were also having issues with large JS so developers had to create polyfills to make sure the code could be read properly. 
* Webpacks is static module bundler.
* Webpacks create dependency graph and modules for apps that require it to work...then the package creates all needed files in a small bundle. 
## Breakdown
* Entry-by default is index.js, but can be modified 
```
module.exports = {
    entry: 'newpathhere.what.ever.js'
}
```

* Output-by default ./dist/main.js but can be modified
```
const path = require('path');

module.exports = {
  entry: './path/newpathhere.what.ever.js',
  output: {
    path: path.resolve(__dirname, 'dist'),
    filename: 'the-best-webpack.bundle.js'
  }
};
```
* Loaders- allow webpack to process other types of files (besides JavaScript and JSON)
test property and use property are it's main things. 
```
const path = require('path');

module.exports = {
  output: {
    filename: 'my-first-webpack.bundle.js'
  },
  module: {
    rules: [
      { test: /\.txt$/, use: 'raw-loader' }
    ]
  }
};
```
* Plugins-perform a few things but examples are optimization, management and injection of variables. 
```
module.exports = {
  module: {
    rules: [
      { test: /\.txt$/, use: 'raw-loader' }
    ]
  },
  plugins: [
    new HtmlWebpackPlugin({template: './src/index.html'})
  ]
};
```
* Mode-3 settings: develpment, production, or none. 
* Browser compatibility -Needs ES5 or newer...(EI8 not supported...because of course it's not) if you wanted those dinosaur browsers to be compatible you'll need a Promise to make them work. You will also need to load a  polyfill as well. 

I bookmarked the other webpages because I'm guessing we're diving into those in case. 

