# Learn Javascript

Steve Purves

Javascript (JS) gets a hard time, yet it is the glue that holds the internet together. JS + HTML5 + CSS is the route to highly usable, custom UIs with rich interactivity, that are intuitive and a pleasure to use. JS opens a door to an incredibly fast moving ecosystem of libraries built for front end wizardry as well as fast, lightweight servers. Of course there are other approaches to awesome interactive visualisation in python; like bokeh or holoviews but working in JS allows freedom.

If your starting point is geocomputing in python, why would you want or need to use javascript? Maybe:

 1. Creating a custom component for a framework like Bokeh
 1. Adding interacrivity to a server-side rendered app
 1. Building a custom single page application

These 3 points represent 3 different levels of engaging with JS development as well as increasing amounts of freedom when you do so.

Here are 5 reasons why you should [re]consider learning Javascript.

## Code into the future
JS is evolving quickly, far faster than browsers can respond with support for new language features. Browser' support for the latest language features will always be incomplete, they are both playing catch up and are independent implementations which will always have some differences.

If you are [re]learning JS, start with a [good primer](https://developer.mozilla.org/en-US/docs/Web/JavaScript) then learn about [the latest language features](https://www.greycampus.com/blog/programming/java-script-versions). A good place to play is in the [babel online repl](https://babeljs.io/repl).

[When starting out] Decide where you are going to compromise between browser support and langauge features ([caniuse](http://www.caniuse.com)) and use the most modern featureset that you can.

Establish a build environment for your project using a transpiler like [babel](https://en.wikipedia.org/wiki/Babel_(transcompiler)) and a packager like [parcel.js](https://parceljs.org/) or [webpack](https://webpack.js.org/). This allows you to work in modern javascript with clean code base, watch your files for changes and automatically build compact .js files to include in your app. This is not necessarily a luxury, as these systems also enable various polyfills and patches needed to make your code work cross-browser once out in the wild.

Modern JS is functional, powerful and beautiful. If you have not seen JS recently, do you even recognise this?

```
// faux api call to our seismic trace server
// remove an offset from our samples and plot them
http.get('/trace/1110/2128/samples',
	({data, offset}) => data.map(sample => sample - offset))
	.then(trace => plot(trace))
```

Here's another comparative example; [old JS](https://jsbin.com/dadena/edit?js,console) and [modern JS](https://jsbin.com/misobet/47/edit?js,console)

## Packages at your fingertips
JS has a massive and growing ecosystem of libaries. In June 2019, the number of packages on [npm](https://www.npmjs.com/), the de-facto standard package manager for JS, surpassed `1e6`. If there is one JS library to include any project it is [lodash](https://lodash.com/) which takes JS's functional and collection based programming capalities to the next level.

## Think asynchronous
JS excels in aysnychonous tasks as its engine is non-blocking, if you are familar with python's deferred object or futures, then JS's Promises will be a small step. Promises are poweful but leave us with additional code to write. Modern JS goes a step further by introducing async/await keywords that allow asynchronous code to be written synchronously, making for less code and better readaility. Which one of these is easier to read?

```
// A - LHS - async code with promises
myFunctionReturningAPromise()
	.then(function(data) {
		// do something
		return data.something;
	}, function(err) {
		console.error('Oops!', err)
	})
	.then(funtion(something) {
		console.log("Received Something", something)
	})
```

```
// B - RHS - async code with async/await
let something;
try {
	something = await myAsyncFunction();
	console.log("Received Something", something)
}
catch (err) {
	console.error('Oops!', err);
}
```

## Frameworks - never start from scratch
JS has many frameworks and you can always find something to fit your needs, no matter how [small](https://github.com/alpinejs/alpine). Opinions and debates on frameworks run wild.

In my opinion, start out with either [React](https://reactjs.org/) or [Vue](https://vuejs.org/), both are easy to get started and do wonderful [reactive](https://en.wikipedia.org/wiki/Reactive_programming) things with, embrace good practices like [immutable state](https://en.wikipedia.org/wiki/Immutable_object) and provide solid start app generators ([create-react-app](https://github.com/facebook/create-react-app), [vue-cli](https://cli.vuejs.org/)) which will give you a build system and skeleton to build from.

## Rethinking the server
Javascript is not just for the browser. [node.js](//www.modejs.com/) is a fast, efficient JS runtime that you can use for practically anything from scripting, AWS lambdas, to web scale application servers.

The next time you reach for python's Flask, ask yourself do you *need* to run in-process python? The answer for anything computational, is likely no. Instead reach for node.js plus a lightweight server library like [express.js](https://expressjs.com/) and call your python in a separate process. Likely you'll get a more readily deployable backend with better tooling for build, test and interfacing with other APIs, up faster than with flask+python. (search terms: node, expressjs, rest, starter, generator)

## Rethinking the desktop
Finally, JS is powering a new wave of desktop applications via [Electron](//electron.atom.io). Pioneered by github as a base for the atom editor, this node.js based application framework is a cross platform paradise for desktop apps it allows us to mash together the cloud with local data and present HMTL5 UI's and visualisations that we expect to see in web apps. Indeed we can develop our webapp and load it in Electron to give it desktop superpowers! What's more, node.js has a solid C/C++ based add on API, allowing you to interface with any code or hardware in any language! Build modular, componentised applications and that use the best language and toolchain for each part of the app.
