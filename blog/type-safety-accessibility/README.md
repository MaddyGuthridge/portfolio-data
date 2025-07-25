# Type safety is an accessibility feature

<small>Maddy Guthridge --- March 16th 2025</small>

I consider myself to be a pretty skilled software engineer. I have built many advanced projects, and am confident in my understanding of many languages, all the way from Python to MIPS Assembly. But one thing that stops me in my tracks and slows my work to crawl when developing is a lack of type safety.

## The traditional arguments for static typing

The main selling point of statically-typed programming languages is compile-time (or CI-time) warnings when code is incorrect. Essentially, your compiler (and editor) can warn you when you've messed something up, and sometimes even suggest fixes, all without ever running the code, allowing you to build and refactor your code with the confidence that "if it compiles, it works".

Additionally, type safety often allows for powerful editor integrations, where your editor can suggest relevant completions, and even show you inline documentation for functions, classes and variables that you access. It's like having an AI assistant reading your code, offering smart suggestions and pointing out mistakes, but without the electricity waste and ethical concerns.

This is great and all -- many people recognise the benefits that type safety brings for code correctness and engineering efficiently. However, I have seen very little discussion on the impact of type safety when it comes to making software development accessible for disabled developers.

## My argument for static typing

I have severe ADHD, which significantly impacts my ability to keep multiple pieces of information in my head simultaneously, and to context-switch between different tasks. Essentially, I have a very limited working memory. As projects grow, I can find it quite difficult to keep track of an entire code-base. Of course, this affects all people to a certain extent, but without accessibility accommodations, even relatively simple programs can become a challenge for me to develop. This means that learning to navigate an unfamiliar project can be a daunting and tedious task. Without accommodations, I often struggle to make simple changes efficiently, even after I have developed a strong mental model of the design.

As an example of this, a few years ago, I was working on a symbolic maths interpreter [Equator](https://maddyguthridge.com/portfolio/projects/equator) which made use of the un-typed library [`sympy`](https://sympy.org/). During this process, I found a [confusing bug](https://github.com/sympy/sympy/issues/22142) which I wished to resolve. However, due to the lack of static types, navigating the code and seeing how parts related to each other was nearly impossible for me. Even now, with 4 years' more experience, I don't feel confident I could resolve the bug in an un-typed codebase (although the fact that the issue is still open at the time of writing indicates that it may be a little more complex than I anticipated).

Last year, I completed most of Advent of Code by using [a different programming language each day](https://github.com/MaddyGuthridge/aoc-2024). Overall, I found that I struggled far more when it came to learning dynamic languages such as Julia, where the lack of clear namespaces and strong type-checking by-default made it very challenging to write my solution. Even when I used Julia's static typing features, my experience was still sub-par compared to other languages. Even for languages that used unfamiliar paradigms, such as Haskell and its purely-functional nature, strong type checking made the process of learning the language far easier.

In fact, when I develop software using familiar languages like Python and JavaScript, I intentionally only choose libraries and tools that offer static type definitions as a feature, or which are covered by libraries such as [DefinitelyTyped](https://definitelytyped.org/) and [typeshed](https://github.com/python/typeshed). When I do use un-typed libraries, I almost always need to write my own set of type definitions before I can use them confidently. Without these definitions, I'll be hopelessly lost. While many libraries have excellent online documentation, hunting through it requires constant context-switching (for both my brain and my laptop) as I hop between my editor and my web browser. This is a simple task for most people (and for the Linux kernel), but can be an overwhelming nightmare for me due to my limited working memory -- the act of switching to my browser makes me forget the context of the code I am working on, meaning I need to re-orient myself as soon as I return to my editor.

## Arguments against static typing

One of the things I find most frustrating in discussions about this is how people argue against type safety for popular projects. I advocate that people should write code in whatever way suits them best for their own projects, but if a project is depended upon by many people, a lack of static typing will make the project far more difficult for people with similar disabilities to me. If a project wishes to be inclusive towards its users and contributors, I believe that static typing is a must-have feature.

As such, it can be a little infuriating when a discussion of this devolves into a [4-year-long GitHub Issues debate](https://github.com/sympy/sympy/issues/17945), where people argue that adding type annotations to a popular library is "too invasive". Arguments such as this invalidate working memory-related disabilities, by suggesting that people with these disabilities are somehow less-deserving of accommodations than those with other forms of disability. Given the level of effort invested into other accessibility features such as supporting alt-text on images, and using [`aria-*` attributes](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA) in HTML to accommodate blind people and people with limited motor abilities, arguments like this against accommodations for people with a limited working memory feel extremely dismissive of the accessibility needs of people such as myself. I believe that accommodations for both physical and mental disabilities are equally important, and should not be viewed as more or less justified based on their nature.

Of course, that isn't an issue unique to software engineering -- I have reported countless issues at my workplace that uniquely impact people with similar disabilities to me, with almost all of them being resolved unsatisfactorily. Of course, failure to accommodate disabled people in the workplace is often illegal, but unfortunately, mental disabilities like ADHD and autism are often not as easily visible to abled people, which can lead to them being prioritised less in discussions of accessibility, despite the significant impact that these disabilities have.

<small>(It goes without saying that this doesn't negate the massive importance of accommodating physically-disabled people).</small>

Another argument against making projects type-safe is the confusion that complex type information can cause. This is particularly try for people unfamiliar with statically-typed code, especially for features like generics. Complex code can sometimes lead to "type gymnastics", which can make development and maintenance of code challenging. While this is a valid concern, and projects should absolutely consider the simplicity of their code when making design decisions, I do not think that this concern holds up to scrutiny in most cases.

* Complex types definitions, such as generic classes are relatively rare in most code-bases, usually being reserved for libraries used by other applications in highly-varied ways.

* Type gymnastics can be frustrating, but most interpreted languages offer an escape hatch in the form of an `any` type. While this is frowned-upon by some, features like this allow for incremental and partial adoption of static types, which can allow for a balance between accessibility and simplicity.

* In my experience, many cases of type gymnastics are an indication of a poor design. Types are a reflection of the code they describe, and so senselessly-complex types mean senselessly-complex code, or the lack of an important typing feature such as [tagged unions](https://en.wikipedia.org/wiki/Tagged_union). When I reflect on some of the worst type gymnastics I have written, it often stems from a poor system design (such as [this example](https://github.com/MaddyGuthridge/Universal-Controller-Script/blob/96e1c802305b0878d6e54fe186d379c0d96511d3/src/devices/device_shadow.py#L35), where I *really* shouldn't have allowed custom parameters for callback functions). Of course, this isn't always true, but as a general rule, code that is difficult to describe to a type-checker is also difficult to understand as a human.

* In order to write correct code, a developer needs to understand the types of all data used by the application. As such, documenting these types is a sensible strategy to help ensure you can keep your code correct in the long-term, as well as contributing towards the dream of making your code self-documenting (an unattainable goal, but a noble one nonetheless).

* Working with statically-typed code does require some additional learning, but the code is often very simple to understand once this learning is complete. Contrastingly, I can't simply learn to work with un-typed code -- disabilities don't have an "off switch". Perhaps people who struggle with type gymnastics should spend some more time in the "type gym".

Of course, while I may disagree with the perspectives I discussed above, it is important to remember that those arguments do have merit, and should be considered when deciding whether static typing is right for a project.

## Less-sensible arguments against static typing

Of course, alongside the mostly-rational debate, there is always ideological us-vs-them nonsense, which can be found in blog posts such as [*"The Inevitable Decline of TypeScript has Begun"*](https://levelup.gitconnected.com/the-inevitable-decline-of-typescript-has-begun-22e4899d0ae1), in which author Attila Vágó claims that TypeScript originated from "Microsoft engineers [who] were too stuck in their ways", needed to "go to therapy", to address the fact that they "couldn't (or wouldn't) appreciate the beautiful permissiveness of JavaScript". I'm far from a Microsoft fan, but the unashamed insults and ad-hominem attacks in this paragraph (and throughout the rest of the post) are far from justified, demonstrating how Vágó can't (or won't) appreciate differences when it comes to opinions on programming language design.

Vágó describes the use of static typing as anti-pragmatic, stating that users of TypeScript do so "for the sake of tech and tech alone". Given my discussion of the importance of static typing for accessibility above, I find this opinion insulting. I can confidently say that without tools such as TypeScript, I would be unable to write code in large projects effectively. This is not because I am unskilled, or an "elitist" who wants to say "no more pizza and free beer" to JS users. It is because I am disabled. I am sure that Attila is a lovely person, but his opinion on TypeScript leaves a bad taste in my mouth.

I don't wish to spend any more time discussing perspectives like those of Vágó. In my opinion, those sorts of arguments are purely ideological, with little meaningful discussion to support them. ***Like all inflammatory posts, content like this should be debunked then ignored*** if we intend to have productive discussions about software engineering and the tools we use to do our jobs.

## To conclude

The more I learn about software engineering, the more I grow to appreciate static typing, not just for the benefits it brings to software that uses it, but also for the way it makes computer programming accessible to me despite my disability. I truly consider type-safe code to be an accessibility feature, which is a necessity for me to work productively. However, as with most accommodations, static typing benefits everyone, much like how audio subtitles are useful when you forgot to bring earbuds, or how elevators are great when you really don't feel like walking up 5 flights of stairs. Software that uses static typing benefits from far better editor support, and more-efficient error detection: offerings that almost all developers love. Sure, it may not be right for every project, but I believe that projects which adopt it are easier to use, and easier to contribute to. Accessibility is always a positive, and in my opinion, type-safe software is no different.

See you next time!
<br>
Maddy

