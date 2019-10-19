# Learn Javascript

Steve Purves

Javascript (JS) gets a hard time yet it is the glue that holds the internet together, the front end at least. JS + HTML5 + CSS is the route to flexible, usable and visualisation rich UIs that are intuitive and a pleasure to use. JS opens a door to an incredibly fast moving ecosystem of libraries built for front end wizardry as well as fast, lightweight servers. Of course there are other awesome visualisation soloutions, just take Python's Bokeh but JS is the only thing that runs natively in any browser.

Here are 5 reasons why you should [re]consider learning Javascript.

## Code in the future - Javascipt's new clothes
JS is evolving quickly, far faster than browsers can respond with support for new language features. Waiting for consistent support is impractical and painful. Address this by using a transpiler, a tool that allows us to code in the latest javascript while compiling back to a baseline that will work across different browsers. Don't just learn y'olde JS, start with a [good primer](https://developer.mozilla.org/en-US/docs/Web/JavaScript) then learn about [ES6/ES2015+ features](https://babeljs.io/learn-es2015/) and use [Babel](//babeljs.io/) to tranpile, and jump start your projects with a good [starter kit](https://github.com/kriasoft/babel-starter-kit). (search terms: babel, es6, es2015+)

Modern JS is functional, powerful and beautiful.
If you have not seen JS recently, do you even recognise this?

// faux api call to our seismic trace server
// remove an offset from our samples and plot them
http.get('/trace/1110/2128/samples',
	({data, offset}) => data.map(sample => sample - offset))
	.then(trace => plot(trace))

Here's a comparitive example; [ES5](https://jsbin.com/dadena/edit?js,console) and [ES2015+](https://jsbin.com/misobet/47/edit?js,console)

## Rethinking the server
Javascript is not just for the browser. [node.js](//www.modejs.com/) is a fast, efficient JS runtime that you can use for practically anything from scription to web scale application servers. Node comes with (at the time of writing) the largest collection of packages in the world accessible through the [npm](//www.npmjs.com) package manager. 

Python's package ecosystem will beat npm hands down on computational packages but for practically everything else there is npm.

The next time you reach for python's Flask, ask yourself do you need ot run in-process python? and indeed should you be anyways! The answer is likely no. Instead reach for node.js plus a lightweight server library like express.js and call your python in a separate process. Likely you'll get to a more readily deployable backend with better tooling for build, test and interfacing with other APIs, faster than with flask+python. (search terms: node, expressjs, rest, es6, starter, generator)

## Packages at your fingertips
We've already mentioned npm but there are many evolutions of package management for javascript, easily pull in and manage front end dependencies [bower](//www.bower.com/).

## Browser Issues aren't nearly as bad as you think
Whilst it's true that browser implementations are still patchy and unreliable (when in doubt check [www.caniuse.com](//www.caniuse.com/) ) the build system that a transpiler gives us goes a long way to cope with the worst. When configuring babel we can incude shims and polyfills that patch gaps in compiler support. In practice this brings compatibility issues down to specific APIs and styling issues, reducing the compatibility burden. A good sarter kit will have this done for us, find one when starting.

## Think asynchronous
JS excels in aysnychonous tasks as it's engine is non-blocking, if you are familar with python's deferred object then JS's Promises will be a small step. Promises and deferreds are poweful but leave us with additional code to write. Modern JS (ES2017+) goes a step further by introducing async/await keywords that allow asynchronous code to be written as synchronous, making for less code and better reasoning, even though everything is still executed asynchronously. Which one of these is easier to read?

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

	// B - RHS - async code with async/await
	let something;
	try {
		something = await myAsyncFunction();
		console.log("Received Something", something)
	}
	catch (err) {
		console.error('Oops!', err);
	}


## Rethinking the desktop
Finally, JS is powering a new wave of desktop applications via [Electron](//electron.atom.io). Pioneered by github as a base for the atom editor, this node.js based application framework is a cross platform paradise for desktop apps it allows us to mash together the cloud with local data and present HMTL5 UI's and visualisations that we expect to see in web apps. What's more, node.js has a solid C/C++ based add on API, allowing you to interface with any code, in any language! Build modular, componentised applications and that use the best language and toolchain for each part of the app.