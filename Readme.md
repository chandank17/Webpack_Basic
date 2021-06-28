# Web Pack

**Web Pack** is module bundler which takes all js/css/images etc and converts it into one single file called bundle. This we can include in our application.


**Web Pack** uses webpack.config.js file to configure our webpack rules. By default webpack uses default config to generate bundle file.

Let's get started.

First let's create a directory, initialize npm, install webpack locally, and install the webpack-cli (the tool used to run webpack on the command line):

# mkdir webpack-demo
# cd webpack-demo
# npm init -y
# npm install webpack webpack-cli --save-dev

Out of the box, webpack won't require you to use a configuration file. However, it will assume the entry point of your project is src/index.js and will output the result in dist/main.js minified and optimized for production.

Usually your projects will need to extend this functionality, for this you can create a webpack.config.js file in the root folder and webpack will automatically use it.

If for some reason you want to use different configuration file depending on certain situations you can change this via command line by using the --config flag.


```js
    const path = require('path');
    const HtmlWebpackPlugin = require('html-webpack-plugin');

    module.exports = {
        mode: 'production',
        // production - enable many optimizations for production builds
        // development - enables usefull dev tools for development
        // none - no defaults, uses production
    
        entry: './src/app.js',
        // defaults to ./src
        // Here the application starts executing
        // and webpack starts bundling

        output: {
            path: path.resolve(__dirname, 'dist'),
            filename: 'bundle.js',
        },
        // options related to how webpack emits results 
        // must be an absolute path (use the Node.js path module)
       
       plugins: [
            new HtmlWebpackPlugin({ template: 'index.html' })
       ]

    //    The plugin will generate an HTML5 file for you that includes all your webpack bundles in the body using script tags.
    }
```










