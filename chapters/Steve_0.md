# Learn Javascript

Steve Purves

Javascript (JS) gets a hard time yet it is the glue that makes the holds the frontend of internet together. JS + HTML5 + CSS is the route to flexible, usable and visualisation rich UIs that are intuitive and a pleasure to use. JS opens a door to an incredibly fast moving ecosystem of libraries built for front end wizardry as well as fast, lightweight servers. Of course thre are other awesome visualisation soloutions, just take Python's Bokeh but JS is the only thing that runs natively in any browser.

Here are 5 reasons why you should [re]consider learning Javascript.

## Code in the future - Javascipt's new clothes
JS is evolving quickly, far faster than browsers can respond with support for new language features. Waiting for consistent support is impractical and painful. Address by using a transpiler, essentially a compiler that allows us to code the latest javascript while conpiling back to a baseline that will work across the browsers that we want to target. Don't learn y'olde JS, use [Babel](//babeljs.io/) one such transpiler, and jump start your learning with a good [starter kit](https://github.com/kriasoft/babel-starter-kit). (search terms: babel, es6, es2015+)

Modern JS is functional, powerful and beautiful.

(example)
calbackHell(){ { { {} } } }

Lovely ES6 example

## Rethinking the server
Javascript is not just for the browser. [node.js](//www.modejs.com/) is a fast, efficient JS runtime that you can use for practically anything from scription to web scale application servers. Node comes with (at the time of writing) the largest collection of packages in the world accessible through the [npm](//www.npmjs.com) package manager. 

Python's package ecosystem will beat npm hands down on computational packages but for practically everything else there is npm.

The next time you reach for python's Flask, ask yourself do you need ot run in-process python? and indeed should you be anyways! The answer is likely no. Instead reach for node.js plus a lightweight server library like express.js and call your python in a separate process. Likely you'll get to a more readily deployable backend with better tooling for build, test and interfacing with other APIs, faster than with flask+python. (search terms: node, expressjs, rest, es6, starter, generator)

## Packages at your fingertips
We've already mentioned npm but there are many evolutions of package management for javascript, easily pull in and manage front end dependencies [bower](//www.bower.com/).

## Browser Issues aren't nearly as bad as you think
Whilst it's true that browser implementations are still patchy and unreliable (when in doubt check [www.caniuse.com](//www.caniuse.com/) ) the build system that a transpiler gives us goes a long way to cope with the worst. When configuring babel we can incude shims and polyfills that patch gaps in compiler support. In practice this brings compatibility issues down to specific APIs and styling issues, reducing the compatibility burden. A good sarter kit will have this done for us, find one when starting.

## Think asynchronous
JS excels in aysnychonous tasks as it's engine is non-blocking, if you are familar with python's deferred object then JS's Promises will be a small step. Promises and deferreds are poweful but leave us with additional code to write. Modern JS goes a step further by introducing async/await keywords that allow asynchronous code to be written as synchronous, making for less code and . 

(see example)
 + promise chaining {}{}

 + await and async

## Rethinking the desktop
Finally, JS is powering a new wave of desktop applications via [Electron](//electron.atom.io). Pioneered by github as a base for the atom editor, this node.js based application framework is a cross platform paradise for desktop apps it allows us to mash together the cloud with local data and present HMTL5 UI's and visualisations that we expect to see in web apps.