# The JavaScript Ecosystem, from the Ground Up

March 8th, 2026

One of the most frightening things about learning JavaScript is the massive scope of the ecosystem that surrounds it. There is so much going on compared to many other languages, which can make it really difficult to feel confident as a developer who is new to JS. In this blog post, we'll look at the JS ecosystem, starting from the lowest-level and working our way up.

## Who is this for?

I am writing this post for people who have a basic understanding of JavaScript, but who want to understand their work in the context of the systems that surround it. While I don't go into immense detail on any particular topic, I have tried to provide helpful links for you to learn more about anything that catches your eye.

## JavaScript engines

JavaScript is an interpreted language. Sort of... In reality, modern web apps demand so much performance that JS interpreters will often run [just-in-time (JIT) compilation](https://en.wikipedia.org/wiki/Just-in-time_compilation) of performance-intensive code-paths in JS code. While this will never perform as well as fully-compiled languages such as C and Rust, it is still a huge step up from interpreting intermediary bytecode, or (worse) running the code line-by-line. Because modern software that executes JavaScript isn't purely an interpreter, we call it an "engine" instead.

One such engine is [V8](https://v8.dev/), which is the interpreter used by many projects. In particular, it is used by Chromium-based browsers, as well as many other environments such as NodeJS. There are many other JS engines as well. [JavaScriptCore](https://docs.webkit.org/Deep%20Dive/JSC/JavaScriptCore.html) is the engine used by Safari, and [SpiderMonkey](https://spidermonkey.dev/) is the engine used by Firefox.

While all of these engines can run the same JavaScript, their internal designs and implementations are all different, so how can we be confident that they all behave the same?

## ECMAScript

[ECMAScript](https://en.wikipedia.org/wiki/ECMAScript) is the standard that dictates how JavaScript code should behave when run. It seems a little strange that they wouldn't just call it the "JavaScript standard", but due to historical reasons, "JavaScript" is [trademarked by Oracle](https://javascript.tm/), meaning even the official standard specification for JavaScript can't call itself the JavaScript standard.

As such, when you see people talk about ECMAScript or "ES", they are usually referring to the standard for JavaScript, including its syntax and base data types such as arrays and objects. However, beyond those basics, the higher-level language features tend to depend on where JavaScript is being used. In a web browser, JS code has functions to let programmers access and modify the state of a web page; whereas in a server-side application, there are functions for tasks like accessing the filesystem and spawning subprocesses. So what is it that allows JavaScript to have different features in different environments?

## Runtimes

The answer is JavaScript runtimes. These are a collection of features bundled with an engine to allow your JS code to interact with the world.

For the JavaScript run in web browsers, all runtimes implement features from the same set of [Web APIs](https://developer.mozilla.org/en-US/docs/Web/API). The most notable of these is the [DOM (Document Object Model)](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model), which allows JS to access and change the state of a web page, as well as listen for and respond to events such as users clicking on buttons. Due to the standardisation of these web APIs, things are pretty consistent in modern web browsers, but in the past, [nonstandard features](https://en.wikipedia.org/wiki/Internet_Explorer#Non-standard_extensions) in web browsers and JS web APIs caused [significant browser fragmentation and monopolisation](https://en.wikipedia.org/wiki/United_States_v._Microsoft_Corp.), making for an awful developer experience.

Outside of web browsers, things are a lot less consistent. The most-popular runtime for servers is [NodeJS](https://nodejs.org/en). It uses the V8 engine and surrounds it with APIs to allow JS programs to run web servers, access file systems, and perform other actions required in server and CLI applications.

There are also other runtimes for JS, which make changes to underlying features or APIs in order to improve the developer experience, boost performance for certain workloads, or run in specialised environments. For example, [Bun](https://bun.sh/) is a server-side runtime which opts to use JavaScriptCore instead of V8. This often gives better performance because although V8 has a better-optimised interpreter, JavaScriptCore starts up faster, which is very helpful for server-side and command-line applications. Bun also has machine-code [reimplementations of Node's APIs](https://bun.com/docs/runtime/nodejs-compat) which are often many times faster than the originals.

As another example, Cloudflare has a specialised runtime called [workerd](https://github.com/cloudflare/workerd) (pronounced "worker d") for their cloud computing platform. They made their own runtime to improve isolation of different users' code, so that they can securely run thousands of JS apps on the same server without needing to use [virtualisation](https://en.wikipedia.org/wiki/Virtual_machine) or [containerisation](https://en.wikipedia.org/wiki/Containerization_(computing)) systems which would slow down performance.

This demonstrates the immense power of the JS ecosystem, as many different systems exist to optimise code to work incredibly well in many different environments. Just by changing the set of APIs available to programs, you can give a script full control over your system to implement powerful server features, or block access to everything it doesn't need so that it can be safely run in isolation from other sensitive data.

But even with these APIs to help us, writing large-scale applications can be immensely tedious. Fortunately, in the JS ecosystem, we stand upon the shoulders of giants.
## Package management

[NPM](https://docs.npmjs.com/about-npm) is the Node Package Manager (tool that downloads and installs dependencies), as well as a package registry (place where those packages are hosted on the internet for people to download). The package manager CLI is often criticised for its poor performance, and so many NPM-compatible-ish package managers have been created as replacements, such as [pnpm](https://pnpm.io/), [yarn](https://yarnpkg.com/) and [bun](https://bun.sh/). All of these still use the same NPM package registry, they just manage installed packages differently.

As for the NPM registry, it has much less competition, since it is generally quite solid, aside from the frequently-discovered [malware packages](https://www.reversinglabs.com/blog/shai-hulud-worm-npm); a difficult problem to resolve. However, [JSR](https://jsr.io/) does look interesting, and has better native support for TypeScript.

## Code transpilation

A lot of the time, we want to use the latest JS features in older runtime environments. Transpilation is the process of automatically converting from one programming language to another, or from one version of a language to an older version. For example, the popular test runner Jest doesn't support some modern JS features, and so is often used alongside additional tools such as [Babel](https://babeljs.io/) to compile new JavaScript into old JavaScript code that Jest can execute.

TypeScript is also a common target for transpilation: since some runtimes can't execute it directly, it often needs to be converted into JS before it can be run. While runtimes such as Bun (and [sort-of Node](https://nodejs.org/en/learn/typescript/run-natively)) support executing TypeScript directly, the support is often partial, and doesn't actually perform the type-checking that TypeScript's compiler offers.

When writing JavaScript for the web, things become a lot more complicated. Many users, and many servers have limited bandwidth, and so developers often want to reduce the file size of any JS that they send to their website visitors. To do this, we use a "bundler", which is a specialised type of transpiler specifically designed to reduce file sizes and group lots of files into one. Common bundlers are [Rolldown](https://rolldown.rs/) and [WebPack](https://webpack.js.org/). Often bundlers will also perform actions such as image compression and other optimisation. These days, it's a lot rarer to use a bundler directly. Instead, developers prefer to use build tools such as [Vite](https://vite.dev/), which make the process of configuring bundlers and other tools a lot simpler, as well as giving excellent development features such as hot reloading.

## Web frameworks

When building website front-ends, using plain JS is pretty tedious, since it is a very imperative language. Imperative means that you list instructions step by step, whereas declarative means you specify and end result, and the program finds a way to get there. For websites, people often prefer to use libraries and frameworks such as [React](https://react.dev/) or [Svelte](https://svelte.dev/) to write the code for their websites in a more-declarative way. That code is then transpiled into plain JS so that it can be executed within a web browser. On top of that, you can find meta-frameworks such as [NextJS](https://nextjs.org/) and [TanStack](https://tanstack.com/) (for React) and [SvelteKit](https://svelte.dev/docs/kit/introduction) (for Svelte) which provide a highly-opinionated way to use those libraries in order to create large-scale web apps.

## In summary

Wow! That's a lot to wrap your head around. From engines to meta-frameworks, JavaScript has by far one of the largest and most-complex ecosystems of any programming language. This offers incredible power, allowing for the specialisation of underlying tools whilst permitting developers to use the same powerful high-level language for their work, but means that understanding JavaScript as a whole can be a very difficult task. Hopefully this blog post has brought you some clarity!

See you next time!
Maddy