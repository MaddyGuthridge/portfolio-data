# Scatterbrained curiosity killed the RCE

July 6th, 2026

Just over a week ago, I stumbled across a remote code execution vulnerability that had somehow survived 9 years without being patched. This happened because I got sidetracked, and then sidetracked again. I've often considered my frequent side-questing and distractability to be my biggest flaw when it comes to being a productive member of society, but with this discovery, my perception of this aspect of myself has changed dramatically.

Note: this blog post doesn't focus on the technical details of the vulnerability. For that, you can check out my [proof-of-concept repository](https://github.com/MaddyGuthridge/sync-rce), which has a full breakdown.

## Security research wasn't what I set out to do

It was a Friday afternoon, and I was boredly working though the issue tracker for my personal website. One of my to-do list tasks was to try out [e18e](https://e18e.dev/docs/cli/), a performance and dependency analysis tool I had recently come across. I gave it a go, and found myself impressed by its suggestions for dependency replacements, and so looked into how they managed to track those dependencies.

It turned out they had [a repository](https://github.com/e18e/module-replacements) to define these replacements, and a [dedicated website](https://replacements.fyi/) to explore them. It was very interesting to scroll through their suggested replacements, understanding the rationales and learning about the history of why JavaScript is *Like This*. Noticing a few spots where I knew of libraries with better alternatives, I opened up some issues to share my knowledge with others: [one serious](https://github.com/e18e/module-replacements/issues/757), [one for comic relief](https://github.com/e18e/module-replacements/issues/756), and [another with a suggestion for usability improvements](https://github.com/e18e/replacements.fyi/issues/76).

That serious replacement suggestion, swapping [`sync-request`](https://github.com/ForbesLindesay/sync-request) for the 20x-more-performant [`sync-request-curl`](https://github.com/nktnet1/sync-request-curl), piqued my curiosity further. What was it about `sync-request` that made it so slow? This led me to `sync-rpc`, a library for executing asynchronous code synchronously by offloading it to a worker process. While reading its code to understand its performance, [I found something horrific](https://github.com/ForbesLindesay/sync-rpc/blob/f500876453721b37376419ad855388aae0579ccf/lib/worker.js#L52): a `require` on an arbitrary file requested over an unauthenticated TCP connection.

And so began a long night of creating [a write-up and proof-of-concept](https://github.com/MaddyGuthridge/sync-rce), rather than improving my personal website. This wasn't what I had meant to do with my Friday, but there I was, with a full-on critical-severity RCE on my hands. One responsible disclose later, the bug was fixed, and that library's 800000 weekly downloaders are hopefully breathing sighs of relief, now that the dependency is secured.

## This vulnerability wasn't special

I'm not some mega-genius here. While I studied the [introductory security course](https://handbook.unsw.edu.au/undergraduate/courses/2023/comp6841?year=2023) at my university, and consider myself to be a capable software engineer, this vulnerability only required a basic understanding of remote process communication and the behaviour of Node's `require` function: hardly specialised knowledge. So then how did this vulnerability sit unnoticed in a library with 800000 downloads per week for 9 years?

It's not like there were no eyes on this library. A course I teach, [COMP1531](https://cgi.cse.unsw.edu.au/~cs1531/), invested much time and effort into understanding and diagnosing its poor performance, ultimately deciding to rewrite it entirely. It is a little surprising to me that nobody noticed this security issue during this process. What did I do differently?

## *Be curious on your journey*

I think that the answer is that I was curious to a fault. I didn't doggedly stick to the one goal at the exclusion of the context around me, I followed where my brain wanted to take me. I may not have closed as many issues on my personal website as I wanted, but I did share ideas and knowledge with the open-source community, and discovered a security issue affecting hundreds of thousands of users.

In fact, one of the most-prolific security discoveries in recent memory, the [xz-utils backdoor](https://en.wikipedia.org/wiki/XZ_Utils_backdoor) was only discovered because developer Andres Freund [decided to investigate high CPU usage from `sshd`](https://x.com/AndresFreundTec/status/1774190743776866374?s=20). That wasn't his job, and he could have easily moved on with his life, but he didn't. He took the time to dig deeper, and follow his curiosity about the issue.

So where does this curiosity and the drive to follow it come from? I can't speak for Andres, but for me, it stems from my enthusiasm for learning, and passion for software engineering; and I believe that I am driven to learn and explore these because I am ADHD.

## Working with ADHD

In my previous blog post *[Type safety is an accessibility feature](https://maddyguthridge.com/blog/type-safety-accessibility)*, I have discussed my experience as an ADHD person, especially the impact on my working memory, and the corresponding accessibility challenges that I frequently face as someone with this disability. However, occasionally, it actually can be sunshine and rainbows. This seems to be what happened here. I was sidetracked, then got sidetracked even further. I was following my curiosity, and ended up in a place that nobody had ever arrived at.

ADHD folks such as myself tend to be "human gas molecules": we work best when we can bounce around and do lots of little things. It is very rare for me to focus on one project for more than a few hours at a time. This is a trait that I worry about a lot. It is very hard for me to grind out tedious tasks like assignment marking, which can lead to long periods of poor productivity. This is something I have often tried hard to fight against, often with significant impacts to my mental and physical health, from overindulgence in snacks as bribery to get work done to full-on burnout. My experience following my curiosity has inspired me to make a change to this. My brain likes to wander, so perhaps it's ok to let it do so. Even though I wasn't productive on the "right things", I still got a lot of work done, and made a significant positive contribution to the world. That should be celebrated.

## How can I accommodate this?

Of course, letting my brain run wild after any topic that catches its interest isn't ideal. I still need to get things done and meet deadlines. However, that doesn't mean things need to remain the same. Here are the things I plan to do to accommodate my brain and benefit from its scatterbrained curiosity while minimising the negative side effects.

- Ensure my employers understand how my brain works. I'm not the right person for repeated and mundane tasks, but I do thrive on chaos. I do my best work when I am tackling things that are new or out-of-the-ordinary. Tailoring my work to match my brain is the best way to get me to do my best work.
- Give myself freedom on my personal projects. I have lots of projects, and even more ideas for them. I have so many that my current list will probably never be completed in my lifetime, and that list is still growing every day. Perhaps it's ok if some of those ideas never come to fruition if I never have the motivation to make them into reality. My personal projects should be fun, and so I shouldn't force myself to do unfun work on them.
- Be kind to myself. This is sorta obvious advice, but the fact is that my brain works differently to other people's, and so judging myself by other people's standards for productivity is not fair on me or my brain. It's ok if things that other people find easy are difficult for me. After all, there are things that other people find difficult that I am incredibly gifted at.

## ADHD is a natural human variation

Modern scientific evidence suggests that ADHD is [highly genetic](https://link.springer.com/article/10.1007/s11920-020-1141-x). As such, it makes logical sense that it has an evolutionary purpose, with [some research](https://pmc.ncbi.nlm.nih.gov/articles/PMC7248073/) indicating that it was beneficial in ancestral forager-gatherer environments. While the world we live in is vastly different from the one that we genetically adapted to, that doesn't mean that we as humans shouldn't take advantage of this additional diversity in the way our brains work. I may not be excellent at staying constantly on-task, but things like my discovery of this vulnerability show that I am capable of outside-the-box thinking and pattern-recognition in unexpected places. I believe that for our human society to be maximally successful, we must accommodate these kinds of diversities in our thinking and existing. Different brains work differently, and so when all of our different brains work together, we can accomplish incredible things.

Happy hacking,
Maddy

