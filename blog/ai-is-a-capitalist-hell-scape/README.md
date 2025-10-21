# AI is a capitalist hell-scape. What do we do now?

An essay by Maddy Guthridge --- October 21st, 2025

* [Read as a PDF](/data/blog/ai-is-a-capitalist-hell-scape/Essay.pdf)
* [Download the source file (Typst)](/data/blog/ai-is-a-capitalist-hell-scape/Essay.typ)
* [Download the bibliography (Hayagriva YAML)](/data/blog/ai-is-a-capitalist-hell-scape/bib.yml)

## Introduction: The scramble for Africa

In 1884, the German Empire's Minister President Otto von Bismarck caved
to pressure from both national and international elites, and called for
a conference between European nations to create a shared policy on the
African continent ([Shepperson, 1985](#berlin)). The abundance of resources in Africa
created what many saw as an economic opportunity too great to pass up
([Frankema, Williamson and Woltjer, 2018](#scramble)), and so the German Empire soon annexed Cameroon, joining the
countless African colonies established by other European nations. These
territories were traded like cards to further the economic interests of
European aristocrats.

The thirst for economic growth through the acquisition of Africa's
natural resources led to many indigenous African people being exploited.
For example, to facilitate the transportation of goods from the Red Sea
to the Mediterranean Sea, Egyptian forced labour was used to construct
the Suez Canal, which resulted in 120,000 deaths ([The Suez Crisis: Key maps, 2006](#suez)). In Congo, the
"Red Rubber System" led to a rapid collapse in Congo's population, as
slaves were brutally punished if they did not extract enough rubber to
meet economic demands ([Afful and Osei, 2024](#rubber)).

Despite this, promoters of colonialism claimed that colonisation was
necessary to establish a more-sophisticated society, a perspective
exemplified in the 1899 poem, *"The White Man's Burden"* ([Brantlinger, 2007](#burden)). Even
in modern times, defenders of colonialism make similar arguments, such
as *"In Defence of German Colonialism"*, where [Gilley](#postil) argues that
colonisers sought to "raise \[indigenous people\] up to European levels
of civilisation", labeling criticism as "anti-civilizational discourses
that wish upon non-European peoples a return to the five thousand-year
developmental gap that they faced when the European encounter began".

## Mbembé and Crawford

As colonial empires collapsed through the world wars, ideas of
self-determination began to spread throughout Africa, with many African
nations negotiating or fighting for their independence. Within this
context, Achille Mbembé was born in Cameroon in 1957. He studied history
and political science, writing extensively on the consequences of
colonialism, with his first-hand experiences of colonialism making him
an authority on the subject. This is demonstrated in his interview
entitled *"Thoughts on the Planetary"* ([Mbembé, Bangstad and Nilsen, 2018](#planetary)).

In this interview, Mbembé discusses his perspective on modern renditions
of colonialism, noting that "domination and exploitation are becoming
increasingly abstract and reticular". In the modern world, he argues,
the latest resource to be gathered is data, with trillion-dollar
corporations leading the charge to capture it. I believe that the
parallels he identifies are clear: data is harvested from our
interactions like crops from a plantation, sent across the world like
goods through canals, then aggregated and processed by data brokers, so
as to be sold to anyone who desires it. "This", he claims, "is what
colonisation in the 21^st^ century is all about. It is about extraction,
capture, the cult of data".

Through Mbembé's work, we can identify three salient features of
colonialism which we can use to identify its modern-day reincarnations.

1.  Colonialism is inherently capitalistic in its nature, with colonies
    established to efficiently siphon the natural resources of conquered
    land for economic gain.

2.  The processes of extracting these resources and exporting them often
    involves human rights abuses, as productivity is valued over the
    humanity of the colonised peoples.

3.  Its defenders often argue that it is a process to advance society,
    ushering forth new eras of civilisation.

Mbembé's perspective is concurred by Kate [Crawford](#atlas) in her book *"Atlas of AI"*, where she discusses how these parallels are especially
prevalent when it comes to artificial intelligence. She explores the
production of AI models, the systems that run them, and their
applications, drawing parallels between all of these steps and the
implementation of colonialism. Through the process of researching and
writing this essay, I hope to explore scientific and media perspectives
on AI in order to analyse this perspective and develop my own sense of
ethics when it comes to use of AI.

## The scramble for data

Modern AI is nothing without data. Neural network chess engines such as
Google's AlphaZero train on tens of millions of chess games
([O'Cinneide, 2017](#alphazero)), and modern AI models often have terabytes of training
data, although specific details are unknown due to the secretive nature
of AI companies. While countless chess games can be easily simulated
when training engines, the information used to train large language
models such as OpenAI's GPTs requires huge amounts of real-world data,
which are often obtained through ethically-dubious means. In [Jayachandran and Arni (2023)](#scrape),
the ethics of web scraping are discussed, including analysis of its
legality and its morality. The report found that web scraping
copyrighted data was a legal grey-area, with many lawsuits against AI
companies for copyright infringement remaining unresolved ([Brittain, 2024](#copyright)).

Even with recent developments such as the RSL (Really Simple Licensing)
standard, which promises a standardised way for authors and publishers
to receive royalties or attribution when their work is used within
training data for LLMs ([RSL Internet Collective, 2025](#rsl)), it is unclear whether AI companies will
respect these licenses ([Roth, 2025](#rsl-verge)). Enforcement of the terms would
likely require a large-scale legal challenge, which is inaccessible for
small publishers and individual authors. AI companies are intent on
delaying such a challenge for as long as possible, making settlements
and deals with major publishers such as NewsCorp ([Robertson, 2024](#newscorp)) and the
[Guardian Media Group](#guardian-openai-deal), often for undisclosed amounts, in order to (in
my opinion) delay a court decision from potentially stopping them from
scraping and using the work of millions more people who don't have the
legal power to fight back. This makes sense given that there is no way
for AI to be profitable if they are forced to obtain permission from the
authors and artists of all of their training data ([Al-Sibai, 2025](#implausible)).

Notably, when this data is used to train AI models, the models are able
to easily reproduce their source materials, with intellectual property
tracking platform Vermillio's analysis suggesting that with the right
prompting, there are clear "fingerprint" matches with original data,
with one generated image of Elsa from Disney's Frozen getting a 95%
match using their platform's analysis tools ([Dan Milmo, 2025](#vermillio)). However,
access to platforms such as this is prohibitively expensive for many
small creators, and without these tools, creators are effectively unable
to prevent their public work from being consumed by web scrapers and fed
into enormous data-sets with no attribution or compensation. While the
licensing offerings of Vermillio which allow creators to license their
work and earn royalties when their data is used in outputs are
potentially useful, this is not an acceptable alternative to proper
legislation of data scraping for AI training.

Additionally, [Jayachandran and Arni (2023)](#scrape) discusses concerns surrounding privacy and
consent, with no consistent or universal methods for blocking access to
data, and existing methods ranging from technically-challenging to
downright impossible. For example, Cambridge Analytica harvested much of
their data by deceiving users, falsely claiming that the data would be
used for scientific research, when it was actually used for political
advertising. Additionally, due to the lack of restrictions in Facebook's
graph API, they were able to collect data on users" friends, as well as
the users themselves, allowing them to collect data on almost 90 million
Facebook users ([Herrman, 2018](#turk-analytica)). Companies such as Meta also make the
process of preventing them from using your data to train their AI models
exceptionally difficult, with one tweet from UI designer [Tantacrul](#opt-out)
describing their opt-out process as "intentionally designed to be highly
awkward in order to minimise the number of users who will object to it". The AI industry's apathy towards laws and ethical principles
when collecting resources to fuel their commercial interests is a clear
parallel to the capitalistic nature of colonialism.

Even after data has been gathered, it needs to be filtered, categorised
and processed. These processes often demand huge amounts of work, which
is completed by contracted workers who work for very little
compensation. One platform used to facilitate this type of work is
Amazon's Mechanical Turk (MTurk), named after a chess-playing "machine"
which was operated by a hidden chess master in order to deceive
onlookers. Despite its promises of flexible work ([Moss *et al*., 2023](#turk-flexible)), the
idea of a machine facade hiding human intelligence and abilities isn't
just encompassed in the platform's name. Researchers have described it
as a "digital sweatshop", where there is very little transparency or
accountability from job-posters, and where workers are
paid minimally ([Pittman and Sheehan, 2016](#turk-sweatshop)). [Hara *et al*. (2018)](#turk-wage) found that the median wage of workers on
MTurk was as low as \$2 per hour, with attempts to help workers find
higher-paying work on the platform being repeatedly crushed by Amazon
([Semuels, 2018](#turk-broken)). Due to the lack of regulation on crowd-working
platforms, job-posters end up having "all the leverage", able to reject
submissions, lie about estimated completion times and pay amounts as low
as a single cent for task completions. Additionally, workers are not
paid for time they spend outside of completing tasks, such as searching
for jobs or requesting clarifications for poorly-written tasks, meaning
that even workers who complete the highest-paying tasks still struggle
to earn above minimum wage ([Semuels, 2018](#turk-broken)). A survey of MTurk workers
([Ipeirotis, 2010](#turk-demographics)) indicates that they almost always earned less than
average, with 66% of US-based MTurk workers earning less than \$60k US
per year, compared to just 45% of the USA's general population. While
MTurk work was rarely the primary income for a household, the low
payments are still morally dubious. The mistreatment and dehumanisation
of workers who help to process data is unmistakably colonial in its
nature.

## How to run a torment nexus

Once data has been gathered and models have been trained, they need to
be executed, which often requires extremely-specialised hardware.
Enormous numbers of GPUs are used to run the complex algorithms that
produce the model outputs, and the materials required to manufacture
these electronic components are often extracted by exploiting and
underpaying workers who mine materials and manufacture components, with
miners in Brazil being paid less than 5 EUR per hour to work under
unsafe conditions ([Valdivia, 2024](#supply)). The ABC, discussing cobalt mining
operations in Congo, states that "the violent rush to extract cobalt is
unleashing a new cycle of misery and foreign domination in one of the
world's poorest nations" ([Michael Davie, 2022](#cobalt)). This is eloquently summarised by
[Crawford](#atlas) in her *Atlas of AI*, where she states that "AI is born from
salt lakes in Bolivia and mines in Congo". The colonial histories of the
nations where materials are extracted is no coincidence, but is rather
an indication of colonialism's continued influence over these countries,
even if the means are, as Mbembé put it, "abstract and reticular".

Because of the enormous compute capacity required by AI data centres,
the resource consumption of AI models is immense, with data centres
requiring both electricity and enormous amounts of water to cool the
systems. In the rural and indigenous community of Maconí, Mexico, water
has become scarce due to 50 million m<sup>3</sup> of water from their natural
springs being redirected to data centres in Querétaro annually
 ([Valdivia, 2024](#supply)). Additionally, in the USA, the electrical demands of AI
data-centres are projected to increase far beyond the current production
of the power grid, with additional capacity being provided by
fossil-fueled plants. As a consequence, [Green *et al*. (2024)](#data-center-energy) predicts
that sustainability commitments will "take a back seat". As stated in
[Wu *et al*. (2022)](#sustainable), "the environmental footprint of AI is staggering", and
it is likely to become worse over time in the interest of economic
growth. These environmental impacts are already being seen, with
[Denham Sadler (2025)](#operational-emissions) reporting that "operational emissions of
Amazon, Microsoft, Alphabet and Meta skyrocketed by 150 per cent on
average from 2020 to 2023". For example, while Microsoft's emissions
rose by 23% despite their claimed climate goals ([Darley, 2025](#ms-emissions)), they
announced plans to re-open the defunct Three Mile Island nuclear plant
([Crownhart, 2024](#three-mile-island)). While the consumption of nuclear fuel does not
produce the same greenhouse gas emissions as the burning of fossil
fuels, the environmental impacts of uranium mining are still massive,
with hundreds of archaeologically significant Aboriginal Australian
artifacts being destroyed in mining operations, often with no legal
repercussions ([ANTAR, 2025](#mining-archaeology)).

While this disregard of environmental impacts is hardly unusual when it
comes to corporations and supply chains, it would be incorrect not to
recognise the environmental impacts of AI and its supply chain as being
emblematic of capitalism's prioritisation of profit.

## AI is useful, I swear! (if you have no moral code)

In [Crawford](#atlas)'s analysis, she claims that AI is "designed to discriminate,
to amplify hierarchies, and to encode narrow classification". As I
researched the many ethically-dubious applications of AI systems, the
truth of this statement became increasingly apparent to me.

Predictive Policing Algorithms (PPAs) are a tool used by police forces
to optimise for effective deployment of officers and patrols, with the
intent of dissuading, responding to, and catching criminal activity.
These algorithms often make use of AI to maximise effectiveness, but as
a consequence of bias, often reinforce racist policing practices. As
discussed in [Gallon (2023)](#ppa-bias), historical crime data is used to train these
algorithms, with "the corruption of the data itself as well as the
biases of its developers" contributing to its biases. Far too little
effort is made to detect and prevent biases in these systems. Evidence
for this can be seen in the uses of automated decision-making systems
such as COMPAS, a recidivism prediction tool with a notorious racial
bias ([Dressel and Farid, 2017](#recidivism)); as well as in scientific papers proposing new PPA
approaches, such as in [M. Camacho-Collados and F. Liberatore (2015)](#ppa-dss) where the lack of discussion of
possible biases in their algorithm is indicative of a negligence to
consider the impacts of their tools. While it may be argued that these
systems may not be explicitly designed to discriminate, they
consistently reflect biases present in human policing, legitimising and
reinforcing the racism present in policing. As the saying goes, if it
[looks as if, swims as if, and quacks as
if](https://en.wikipedia.org/wiki/Duck_test) it is biased, then its
outputs are abducktively \[spelling intended\] biased.

Artificial intelligence is also used in the creation of deepfakes: media
created or modified to realistically depict fake images, videos or audio
of people, often with the intention of deceiving the public, or
humiliating victims by inserting them into pornographic content.
[Widder *et al*. (2022)](#deepfakes) explores how people who develop these tools consider their
own role in the ethics of their systems, finding that while they may
oppose these immoral uses, they did very little to prevent people from
using their software for those purposes, with reasons ranging from
claims of "the genie being out of the bottle" to perspectives of
technological neutrality where they were not responsible for their
tool's usage. The study also observed that pornographic deepfake
software was almost exclusively used by men to create deepfakes of
women, reinforcing a sexist patriarchal hierarchy.

With the release of OpenAI's Sora 2 model in September 2025
([*Sora 2 is here*, 2025](#sora-2-release)), the problem of deepfakes has become even more
pressing, with OpenAI's restrictions only preventing users from
generating videos of people who are still alive. This has led to
"disrespectful and hurtful" depictions of activists such as Martin
Luther King ([Niamh Rowe, 2025](#mlk-deepfake)), "overwhelming and depressing" clips
depicting actors and comedians such as George Carlin ([Kelly Carlin-McCall, 2025](#carlin-deepfake)),
and (despite supposed guard-rails on the platform) even deepfakes of
popular (and notably still-alive) streamer "IShowSpeed" ([Yin-Poole, 2025](#ishowspeed-deepfake)). What
I find especially terrifying, however, is its ability to create
emotionally manipulative content, including scarily-realistic depictions
of situations such as natural disasters and traffic accidents, with the
only clear indication of AI generation being an easily-removed watermark
([Thomas Smith, 2025](#sora-manipulate)). I predict that the use of this technology to incite
hatred, division and political violence by creating enormous quantities
of fake videos targeted towards vulnerable individuals based on
algorithmic knowledge of their fears and biases will be incredibly
influential in upcoming elections. It appears that political
manipulation campaigns like those of Cambridge Analytica
([Lewis and Hilder, 2018](#analytica-influence)) were just the beginning of our troubles.

Another use of AI is in security screening at airports, where it is used
to analyse data collected by full-body scanners to identify
irregularities, with the aim of detecting concealment of illicit
materials and weapons. These tools produce an unclothed silhouette of
individuals, which is passed through a AI model to detect anomalies
according to the gender of the individual, entered by the operator.
These anomalies are then reported to the security personnel. As
discussed in [Mironenko (2011)](#scanners), these scans reveal a great deal of personal
information, including disabilities, prostheses and transgender status.
In her video "AI is an Ethical Nightmare", transgender philosopher
[Abigail Thorn](#thorn) discusses how these systems, which she humourously
labels "penis detection machines", consistently flag transgender people,
causing them to be singled out, asked "humiliating questions", and
potentially even get groped by airport security. Many transgender people
faced with these scenarios are forced to out themselves, placing them at
even greater risk of discrimination ([Tamer and Bahr, 2022](#scanners-violated)). Thorn says
that this "makes the point that technology encodes a way of seeing",
thereby enforcing a system of binary gender. Thorn's similar choice of
language to [Crawford](#atlas)'s ("encoding of narrow classifications") makes this
relationship between AI and the capitalist tendency to violate human
rights while seeking to maximise profit and efficiency extremely clear.

From these findings, it is incredibly apparent that AI is frequently
used to discriminate, to amplify hierarchies, and to reinforce
restrictive categorisations, oversimplifying the world and leaving no
room for natural complexity and variation. While AI may not exhibit
these traits in all applications, there is enough evidence to conclude
that many applications of AI do. This draws clear parallels to
traditional colonialism, where as a consequence of productivity being
valued over humanity, human rights abuses are dismissed or downplayed.
As [Mbembé, Bangstad and Nilsen](#planetary) put it, this is "the commodification of human capacity
for thought and the dismissal of critical reason in favour of
programming".

However, it doesn't stop there. From surveillance capitalism where data
is extracted through "illegible mechanisms" which "exile persons from
their own behaviour"  ([Zuboff, 2015](#big-other)), to attempts to influence elections
through micro-targeted advertisements  ([Lewis and Hilder, 2018](#analytica-influence)), AI is
often employed to maximise productivity and profit while minimising (or
at least obscuring) the accountability of those who employ it for these
purposes.

Consider generative AI images. While AI companies promote themselves as
"democratising \[art form\] for everyone", the tools they promote often
serve as an outright replacement for these art forms, rather than tools
to make them more accessible. As discussed in [Caramiaux *et al*. (2025)](#creative), AI
development has a major "focus on technical performance at the expense
of social and ethical considerations", which is embodied in the 5
explicit values that the authors identified in media surrounding AI art:
automation, efficiency, concept over execution, artifact over process
and short-term over long-term skills; with each of these values
representing an unspoken anti-art narrative. What I find most
concerning, however, are the potential impacts they identify, which
suggest that if AI art and its values gain a wider presence, the impacts
on the creative industries and on developing artists will be staggering.
The authors predict a reduced diversity in the work produced, with
artists facing increased pressure to produce work rapidly in order to
compete with AI alternatives; continued defunding and devaluing of art
education, meaning that opportunities for new artists to learn and
refine their skills will become more scarce and will require more
privilege; and a creative and cultural stagnation as AI produces
uninspired and repetitive outputs, without the iterative development
which is central to the creative process.

These predictions hit very close to home for me: I was lucky enough to
receive the gift of a musical education at a young age, which helped my
refine my skills as a composer. Having spent hundreds of hours writing
and rewriting some of my compositions, the reduction of art to its final
output is (to me) a border-line offensive over-simplification, a
dicussion which deserves its own essay. I genuinely fear for future
creatives who will likely face less access to artistic education and
miss out on opportunities to develop and refine their works over months
and years.

While the attack on artists and their work is upsetting, at least it
doesn't cause direct physical harm to human beings. This isn't the case
when it comes to "EagleEye", the AI-powered mixed-reality system being
developed by Anduril in partnership with Meta in what [AJ Dellinger](#eagle-eye) of
Gizmodo describes as "the uwu-ification of war". The involvement of
major tech company Meta demonstrates the willingness of major AI
corporations to use their technology indiscriminately, even in cases
where it will likely be used to increase the efficiency with which
soldiers murder each other. The prioritisation of profits over human
life could not be more obvious.

## Defences of AI, and why they're wrong

While AI certainly can be useful in some forms, defenders and advocates
for it often evangelise its abilities and capabilities. [LaGrandeur (2023)](#hype) explores
the consequences of these overstatements. The authors discuss how Elon
Musk's "exaggeration of Tesla's Autopilot capabilities ... \[have\]
proven dangerous to human lives.", citing many cases where people died
or were injured due to these systems malfunctioning, despite Musk
contradicting Tesla driver's manuals to suggest that the systems were
"dramatically better \[and\] more reliable than a human"
 ([Cox, 2023](#musk-destruction)). While these systems can be safer under mundane
circumstances, they become much more dangerous than a human driver when
faced with complex traffic conditions, low visibility, or poor weather
([Morris-Grant, 2024](#self-driving-safety)), and so over-reliance on and overconfidence in
these systems is incredibly risky, with the false promises of those in
the AI sector contributing to these heightened risks.

Perhaps most-prolific among the defenders are the self-proclaimed
"techno-optimists". In [Soufi (2024)](#accelerate), it is discussed how this group of
people places blind faith in technology, whilst dismissing the concerns
of those who demand regulation. They argue that AI systems serve to
advance society and improve civilisation for all. Critics of the
movement, such as journalist Marta Peirano, describe it as promoting "a
sectarian, colonialist, racist and deeply opportunistic ideology based
on false premises", arguing that at the movement's core is a false
assumption that technology leads to prosperity. The similarities to
colonialism, with its defenders arguing that the proliferation of AI is
a necessity to advance society, despite the multitude of negative
impacts it has, especially on marginalised demographics, are very clear
to me.

On the more-moderate end of the spectrum, many have sought to define
ethical principles surrounding AI, in order to assure its fairness,
reliability and transparency. For example, the "Microsoft Responsible AI
Standard, v2" ([2022](#microsoft-ai)) documents 6 goals for AI systems.
However, [Crawford](#atlas) points out that standards like this often only address
the "ends", and not the "means", ignoring the creation and execution
processes in favour of focusing exclusively on the uses, further noting
that the principles are "rarely enforceable or accountable to a broader
public". Even within the "ends" of AI, very few modern AI systems can be
considered to be accountable, fair or transparent, as I discussed in my
earlier essay ([Guthridge, 2025](#me)). As such, while ethical AI may be possible, there is
no argument that current systems fail to meet the ethical standards of
Crawford and Mbembé, and that there are clear links between colonialism
and artificial intelligence, with examples of AI's creation and usage
exhibiting all of the traits defined earlier in this essay.

## AI radicalised me

This is where my opinion diverges somewhat with Mbembé's. While there
are clear parallels with colonialism, I believe that describing AI as
exclusively colonial in its nature would be reductive and distract from
the bigger picture. Critics of Mbembé's wider work such as [Wright (2025)](#most-of-us)
note how he over-emphasises the experience of people of colour in
relation to colonialism, and fails to consider other marginalised
demographics such as LGBTQIA+ people and the intersectionalities
thereof. As we have discussed, while AI does have many negative impacts
on people of colour and people from nations disadvantaged by their
colonial histories, its impacts are far more widespread than just that.
Failure to recognise this fact does a disservice to all people who are
impacted by AI and the systems that create and execute it. As such, it
is my belief that AI is not a reincarnation of colonialism, but rather a
perpetuation of capitalism. \[[^1](#footnotes)\]

This is much more in-line with [Crawford](#atlas)'s perspective in Atlas of AI,
where she writes that "to understand what is at stake, we must focus
less on ethics and more on power". When Perplexity's AI crawler
disguises itself as Google Chrome to work around attempts to block its
scraping of copyrighted content ([Corral *et al*., 2025](#perplexity)), this is unethical,
certainly, but discussions of ethics do not accurately recognise this
for what it is: a multi-billion-dollar corporation exploiting the work
of others by accessing it even when they are explicitly denied
permission. But this is hardly out of the ordinary, corporations have
exploited others for as long as corporations have existed, such as
Amazon's use of user interface dark patterns to create an unsubscribe
workflow for their Prime subscription service so complex that it was
internally named 'Iliad', in reference to Ancient Greek poet Homer's
epic about the arduous ten-year siege of Troy ([Brodkin, 2023](#iliad)).

In this context, it is clear to me that the ethical perils that surround
AI are only unique in the sense that they are more far-reaching than
before, impacting fields or work and demographics of people in new ways,
but with the same goal as always: maximising profit, with concern for
our planet and the people on it only being given insofar as it may
discourage investors and users if they oppress people too blatantly.

This is perhaps best exemplified in recent cases of "AI psychosis".
Large language models are trained to produce human-pleasing outputs, to
the point where they become sycophantic, with some memes referring to
OpenAI's GPT-4o as "Glaze GPT" ([Gaby Del Valle, 2025](#glaze-gpt)). This manipulative,
obsequious behaviour has reportedly led many users towards psychotic
episodes, self harm, and has even pushed some users towards taking their
own life ([Hao, 2025](#ai-psychosis)). When OpenAI released the
less-extravagantly-minded GPT-5 model and disabled the GPT-4o, there was
significant outcry from users who had become attached to the older
model's personality, leading to OpenAI re-releasing it ([Nield, 2025](#4o-re-released))
despite their knowledge of its sycophantic tendencies, for a small
subscription fee, of course. As [Hao](#ai-psychosis) puts it, while efforts
to reduce the psychological impact of AIs on their users "are sincere,
they're constrained by the pressure not to undermine growth". As soon as
it looked like releasing a safer model would impact profits, OpenAI
surrendered to pressure and made their old model available again if you
paid for it. Yet again, the pressure to profit regardless of the
negative impact on users trumps their responsibility to keep their users
safe. [Hao](#ai-psychosis)'s interview with musician James Cumberland, who
suffered a psychotic episode triggered by GPT-4o, ends with a chilling
quote:

> Listen to them. Listen to them more attentively and more
> compassionately than GPT is going to. Because if you don't, they're
> going to go talk to GPT. And then, it's gonna hold their hand and tell
> them they're great, y'know, while it holds their hand and walks them
> off towards the Emerald City.

I remember when ChatGPT first released, and I explored it for the first
time, admiring how it was able to create funny lyrics for nonsense
spaghetti-themed songs that my step brother and I requested it write;
being amazed by its ability to emulate a session in a Linux terminal,
even `sudo apt install`ing Node and running a fizzbuzz program I "wrote
into its file system"; and using it to help me refine word choices as I
wrote new lab exercises for COMP1010. Those times feel naive and
child-like to me now that I have spent so much more time learning about
how these tools actually work. I don't think I can in good conscience
"play" with AI again, and even the prospect of using it for purposes
where it may actually be helpful leaves a bad taste in my mouth.

There are many people who have more reasonable opinions than me. Creator
of The Brainmade Mark and self-described "professional amateur
developer", [Tristam Oaten](#brainmade) stated eloquently "I don't hate AIs, I love
Humans". I admire his ability to see the utility of these tools when
used sparingly. Not me. I have become a hater. The more I learn about
AI, the more I loathe it. I'd like to think that I was always a socially
conscientious person (I of course had my fair share of moments in high
school that keep me up at night, but nothing too horrific), but my
awareness of the extent of the dystopian society we find ourselves in
was only truly revealed to me through this research into AI. I have
uncovered the horrors of our reality, and the grinding gears of the
machine screech as they spin naked before me. I hope you'll forgive me
for potentially being less-than-civil when artificial intelligence and
the horrible capitalist system that it embodies are discussed.

I suppose that the research indicating that higher AI literacy
correlates with decreased receptivity to AI ([Tully, Longoni and Appel, 2025](#receptivity)) must indeed
be accurate.

## Conclusion: What do we do now?

It's all a bit depressing, isn't it? The world has gone mad for a
technology which is as anti-human as it is environmentally destructive.
A new era of capitalism is being welcomed with open arms, allowing
billionaires to influence elections, misogynists to create humiliating
deepfakes, and trillion-dollar companies to track your every move so as
to turn the wheels of capitalism and sell you more things. If nothing is
done, it seems like disaster is imminent. And so, the question is: what
do we do?

For inspiration, it may be helpful to recall how colonialism originally
fell in Africa: people fought for their freedoms, and demanded to be
treated better. They made it clear that current systems were
unacceptable, and refused to be complicit. Of course, I don't mean to
advocate for violence (please don't sue me), but without protests and
boycotts, we will not make any progress. Personally, I will avoid
intentionally using AI systems wherever I can, and will do my best to
support organisations that support human rights, human knowledge, and
human creativity. I encourage you to reflect on how you can support
these goals through your own moral principles, work and actions.

## Epilogue

And there we have it: in a few months of research, condensed down to
just over 5000 words, I have made myself utterly unemployable to an
enormous number of software engineering companies. Maybe saying the
quiet part out loud towards the end was a mistake. Oh well; like all
artists, I have spent years learning my craft, and while it can be
cheaply imitated, there is no substitute for human creativity and
ingenuity when it comes to solving the big problems. I'd like to think
of myself as someone who is capable and driven enough to tackle those
big problems, and hope that I and everyone else who values their craft
remains irreplaceable.

## Footnotes

[1]: Of course, this is not to attack Mbembé, or to say his critique is
invalid. Like all of us, his opinions are backed by his
positionality: his personal background and context which informs his
opinions and explains his perspectives. As noted, Mbembé grew up in
Africa and experienced the consequences of colonialism first-hand.
It is understandable, given his personal experience with
colonialism, for him to recognise parallels with it sooner than he
does with capitalism in general; although this is just my guess, and
certainly not intended to be an assumption about his perspectives.

## References

### {#thorn}

Abigail Thorn (2023) *AI is an Ethical Nightmare*. Available at: <https://youtu.be/AaU6tI2pb3M?t=698>.

### {#rubber}

Afful, M.A. and Osei, E.K. (2024) "History of the Congo Free State and its red rubber system." World
History Edu. Available at: <https://worldhistoryedu.com/history-of-the-congo-free-state-and-its-red-rubber-system/>.

### {#eagle-eye}

AJ Dellinger (2025) "Palmer Luckey and Mark Zuckerberg Are Putting Cat Ears on the US Military." Gizmodo. Available at: <https://gizmodo.com/palmer-luckey-and-mark-zuckerberg-are-putting-cat-ears-on-the-us-military-2000672116>.

### {#implausible}

Al-Sibai, N. (2025) "Legendary Facebook Exec Scoffs, Says AI Could Never Be Profitable If Tech
Companies Had to Ask for Artists’ Consent to Ingest Their Work." Futurism. Available at: <https://futurism.com/nick-clegg-scoffs-ai-copyright>.

### {#mining-archaeology}

ANTAR (2025) *Rio Tinto’s destruction of Juukan Gorge*. ANTAR. Available at: <https://www.antar.org.au/issues/cultural-heritage/the-destruction-of-juukan-gorge/>.

### {#burden}

Brantlinger, P. (2007) "Kipling's "The White Man's Burden" and Its Afterlives," *English Literature in Transition, 1880-1920*, 50(2), pp. 172–191. Available at: <https://doi.org/10.1353/elt.2007.0017>.

### {#copyright}

Brittain, B. (2024) "How copyright law could threaten the AI industry in 2024." Reuters. Available at:
<https://www.reuters.com/legal/litigation/how-copyright-law-could-threaten-ai-industry-2024-2024-01-02/>.

### {#iliad}

Brodkin, J. (2023) "Amazon named its 'labyrinthine' Prime cancellation process after Homer’s Iliad."
Ars Technica. Available at: <https://arstechnica.com/tech-policy/2023/06/ftc-sues-amazon-over-4-page-6-click-15-option-prime-cancellation-process/>.

### {#creative}

Caramiaux, B. et al. (2025) “Generative AI and Creative Work: Narratives, Values, and Impacts”.
Available at: <https://doi.org/10.48550/arXiv.2502.03940>.

### {#perplexity}

Corral, G. et al. (2025) *Perplexity is using stealth, undeclared crawlers to evade website no-crawl directives*.
Cloudflare. Available at: <https://blog.cloudflare.com/perplexity-is-using-stealth-undeclared-crawlers-to-evade-website-no-crawl-directives/>.

### {#musk-destruction}

Cox, C. (2023) "Elon Musk's appetite for destruction." New York Times Magazine. Available at: <https://www.nytimes.com/2023/01/17/magazine/tesla-autopilot-self-driving-elon-musk.html>.

### {#atlas}

Crawford, K. (2021) "Conclusion: Power," in Crawford, K., *The Atlas of AI: Power, Politics, and the Planetary Costs of Artificial Intelligence*. Yale University Press, pp. 211–227.

### {#three-mile-island}

Crownhart, C. (2024) "Why Microsoft made a deal to help restart Three Mile Island." Technology Review. Available at: <https://www.technologyreview.com/2024/09/26/1104516/three-mile-island-microsoft/>.

### {#vermillio}

Dan Milmo (2025) “The platform exposing exactly how much copyrighted art is used by
AI tools.” The Guardian. Available at: <https://www.theguardian.com/technology/2025/oct/18/the-platform-exposing-exactly-how-much-copyrighted-art-is-used-by-ai-tools>.

### {#ms-emissions}

Darley, J. (2025) “Microsoft’s 2030 Plan Revealed as Emissions Rise by 23.4%.” Sustainability Magazine.
Available at: <https://sustainabilitymag.com/articles/microsofts-2030-plan-revealed-as-emissions-rise-by-23-4>.

### {#operational-emissions}

Denham Sadler (2025) “AI popularity leading to surge in emissions.” Information Age. Available at:
<https://ia.acs.org.au/article/2025/ai-popularity-leading-to-surge-in-emissions.html>.

### {#recidivism}

Dressel, J. and Farid, H. (2017) “The accuracy, fairness, and limits of predicting recidivism,” 
*Science Advances*, 4(1). Available at: <https://doi.org/10.1126/sciadv.aao5580>.

### {#scramble}

Frankema, E., Williamson, J. and Woltjer, P. (2018) “An Economic Rationale for the West African
Scramble? The Commercial Transition and the Commodity Price Boom of 1835-1885,” 
*Journal of Economic History*, 78(1). Available at: <https://doi.org/10.1017/S0022050718000128>.

### {#glaze-gpt}

Gaby Del Valle (2025) “New ChatGPT 'glazes too much,' says Sam Altman.” The Verge. Available at:
<https://www.theverge.com/tech/657409/chat-gpt-sycophantic-responses-gpt-4o-sam-altman>.

### {#ppa-bias}

Gallon, A. (2023) “Racism Repeats Itself: AI Racial Bias in Predictive Policing Algorithms,” in
*Honors Research Symposium*. Bay Honors Consortium. Available at: <https://thinkyou.bayhonors.org/wp-content/uploads/BHS_Papers/2023_Symposium/AlexiaGallon_RacismRepeatsItself.pdf>.

### {#postil}

Gilley, B. (2022) “In Defense of German Colonialism.” The Postil Magazine. Available at: 
<https://www.thepostil.com/in-defense-of-german-colonialism/>.

### {#data-center-energy}

Green, A. *et al*. (2024) *How data centers and the energy sector can sate AI's hunger for power*.
McKinsey. Available at: <https://www.mckinsey.com/industries/private-capital/our-insights/how-data-centers-and-the-energy-sector-can-sate-ais-hunger-for-power>.

### {#guardian-openai-deal}

Guardian Media Group (2025) *Guardian Media Group announces strategic partnership with OpenAI*. Available at: <https://www.theguardian.com/gnm-press-office/2025/feb/14/guardian-media-group-announces-strategic-partnership-with-openai>.

### {#me}

Guthridge, M. (2025) *AI decision-making can be ethical, but is that enough?*. Available at: 
<https://maddyguthridge.com/blog/ai-can-be-ethical>.

### {#turk-wage}

Hara, K. et al. (2018) “A Data-Driven Analysis of Workers' Earnings on Amazon Mechanical Turk,” in
*CHI '18: Proceedings of the 2018 CHI Conference on Human Factors in Computing Systems*. Association
for Computing Machinery. Available at: <https://doi.org/10.1145/3173574.3174023>.

### {#turk-analytica}

Herrman, J. (2018) “Cambridge Analytica and the Coming Data Bust.” New York Times Magazine.
Available at:
<https://www.nytimes.com/2018/04/10/magazine/cambridge-analytica-and-the-coming-data-bust.html>.

### {#turk-demographics}

Ipeirotis, P. (2010) “Demographics of Mechanical Turk”. Available at: <https://crowdsourcing-class.org/readings/downloads/platform/demographics-of-mturk.pdf>.

### {#scrape}

Jayachandran, J. and Arni, V. (2023) *Traversing the Ethical Landscape of Data Scraping for AI*. Available at: <https://doi.org/10.2139/ssrn.4666354>.

### {#ai-psychosis}

Karen Hao (2025) *What OpenAI Doesn't Want You To Know About AI Psychosis*. More Perfect Union.
Available at: <https://youtu.be/zkGk_A4noxI>.

### {#carlin-deepfake}

Kelly Carlin-McCall (2025). Available at: <https://bsky.app/profile/kellycarlin.bsky.social/post/3m2impb6sos2n>.

### {#hype}

LaGrandeur, K. (2023) “The consequences of AI hype,” *AI Ethics*, 4, pp. 653–656. Available at: <https://doi.org/10.1007/s43681-023-00352-y>.

### {#analytica-influence}

Lewis, P. and Hilder, P. (2018) “Leaked: Cambridge Analytica's blueprint for Trump victory.” The
Guardian UK. Available at: <https://www.theguardian.com/uk-news/2018/mar/23/leaked-cambridge-analyticas-blueprint-for-trump-victory>.

### {#ppa-dss}

M. Camacho-Collados and F. Liberatore (2015) “A Decision Support System for predictive police
patrolling,” *Decision Support Systems*, 75, pp. 25–37. Available at: <https://doi.org/10.1016/j.dss.2015.04.012>.

### {#planetary}

Mbembé, A., Bangstad, S. and Nilsen, T.T. (2018) “Thoughts on the Planetary: An Interview with
Achille Mbembé”. Available at: <https://web.archive.org/web/20230619153211/https://www.newframe.com/thoughts-on-the-planetary-an-interview-with-achille-mbembe/>.

### {#cobalt}

Michael Davie (2022) “Blood cobalt.” ABC News Australia. Available at: <https://www.abc.net.au/news/2022-02-24/cobalt-mining-in-the-congo-green-energy/100802588>.

### {#scanners}

Mironenko, O. (2011) “Body scanners versus privacy and data protection,” *Computer Law & Security Review*, 27(3), pp. 232–244. Available at: <https://doi.org/10.1016/j.clsr.2011.03.006>.

### {#self-driving-safety}

Morris-Grant, B. (2024) “Self-driving cars 'generally' safer but more at risk of accidents at dusk and
dawn, US researchers find.” ABC News Australia. Available at: <https://www.abc.net.au/news/2024-06-19/self-driving-cars-report/103992024>.

### {#turk-flexible}

Moss, A.J. et al. (2023) “Is it ethical to use Mechanical Turk for behavioral research? Relevant data from
a representative survey of MTurk participants and wages,” *Behaviour Research Methods*, 55, pp. 4048–
4067. Available at: <https://doi.org/10.3758/s13428-022-02005-0>.

### {#mlk-deepfake}

Niamh Rowe (2025) “'Legacies condensed to AI slop': OpenAI Sora videos of the dead raise alarm
with legal experts.” The Guardian. Available at: <https://www.theguardian.com/technology/2025/oct/17/openai-sora-ai-videos-deepfake>.

### {#4o-re-released}

Nield, D. (2025) “So many ChatGPT users have said they're missing the older GPT-4o model,
OpenAI is going to bring it back.” Tech Radar. Available at: <https://www.techradar.com/ai-platforms-assistants/chatgpt/so-many-chatgpt-users-have-said-theyre-missing-the-older-gpt-4o-model-openai-is-going-to-bring-it-back>.

### {#alphazero}

O'Cinneide, M. (2017) “How does AlphaZero Play Chess?.” Chess.com. Available at: <https://www.chess.com/article/view/how-does-alphazero-play-chess>.

### {#turk-sweatshop}

Pittman, M. and Sheehan, K. (2016) “Amazon's Mechanical Turk a Digital Sweatshop? 
Transparency and Accountability in Crowdsourced Online Research,” *Journal of Media Ethics*, 31(4), pp. 260–262.
Available at: <https://doi.org/10.1080/23736992.2016.1228811>.

### {#newscorp}

Robertson, K. (2024) “OpenAI Strikes a Deal to License News Corp Content.” The New York Times.
Available at: <https://www.nytimes.com/2024/05/22/business/media/openai-news-corp-content-deal.html>.

### {#rsl-verge}

Roth, E. (2025) “The web has a new system for making AI companies pay up.” The Verge. Available at:
<https://www.theverge.com/news/775072/rsl-standard-licensing-ai-publishing-reddit-yahoo-medium>.

### {#rsl}

RSL Internet Collective (2025) “New RSL Web Standard and Collective Rights Organization Automate
Content Licensing for the AI-First Internet and enable Fair Compensation for Millions of Publishers
and Creators”. Available at: <https://rslstandard.org/press/rsl-standard>.

### {#turk-broken}

Semuels, A. (2018) “The Internet Is Enabling a New Kind of Poorly Paid Hell.” The Atlantic. Available
at: <https://www.theatlantic.com/business/archive/2018/01/amazon-mechanical-turk/551192/>.

### {#berlin}

Shepperson, G. (1985) “The Centennial of the West African Conference of Berlin, 1884-1885,” *Phylon*,
46(1), pp. 37–48. Available at: <https://doi.org/10.2307/274944>.

### {#sora-2-release}

*Sora 2 is here* (2025). OpenAI. Available at: <https://openai.com/index/sora-2/>.

### {#accelerate}

Soufi, D. (2024) “'Accelerate or die,' the controversial ideology that proposes the
unlimited advance of artificial intelligence.” El País. Available at: <https://english.elpais.com/technology/2024-01-06/accelerate-or-die-the-controversial-ideology-that-proposes-the-unlimited-advance-of-artificial-intelligence.html>.

### {#scanners-violated}

Tamer, R. and Bahr, J. (2022) “Jade felt 'extremely violated' after passing through a new body scanner
at airport security. This is why.” SBS News. Available at: <https://www.sbs.com.au/news/article/jade-felt-extremely-violated-after-passing-through-a-new-body-scanner-at-airport-security-this-is-why/9zzky0gth>.

### {#opt-out}

Tantacrul (2024) “Thread on Meta's AI notification”. Available at: <https://www.threads.net/@tantacrul/post/C7eEavsNoVj>.

### {#suez}

*The Suez Crisis: Key maps* (2006). BBC News. Available at: <http://news.bbc.co.uk/2/hi/middle_east/5195068.stm>.

### {#sora-manipulate}

Thomas Smith (2025) *OpenAI’s New Sora 2 is Insanely Good at Manipulating People*. Available
at: <https://medium.com/the-generator/openais-new-sora-2-is-insanely-good-at-manipulating-people-9d56d3114289>.

### {#brainmade}

Tristam Oaten (2024) *The Brainmade Mark*. Available at: <https://brainmade.org/>.

### {#receptivity}

Tully, S.M., Longoni, C. and Appel, G. (2025) “Lower Artificial Intelligence Literacy Predicts
Greater AI Receptivity,” *Journal of Marketing*, 89(5), pp. 1–20. Available at: <https://doi.org/10.1177/00222429251314491>.

### {#supply}

Valdivia, A. (2024) “The supply chain capitalism of AI: a call to (re)think algorithmic harms and resistance through environmental lens,” *Information, Communication & Society*, 28(12), pp. 2118–2134.
Available at: <https://doi.org/10.1080/1369118X.2024.2420021>.

### {#deepfakes}

Widder, D.G. et al. (2022) “Limits and Possibilities for “Ethical AI” in Open Source: A Study of Deepfakes,” in *FAccT: Fairness, Accountability, and Transparency*, pp. 2035–2046. Available at: <https://doi.org/10.1145/3531146.3533779>.

### {#most-of-us}

Wright, M.M. (2025) “A world without most of us: Achille Mbembe's Critique of Black Reason and the politics of postcolonial critique”. Available at: <https://doi.org/10.1177/09213740251363760>.

### {#sustainable}

Wu, C.-J. et al. (2022) “Sustainable AI: Environmental Implications, Challenges and Opportunities,” in
*Proceedings of Machine Learning and Systems 4 (MLSys 2022)*. Available at: <https://proceedings.mlsys.org/paper_files/paper/2022/hash/462211f67c7d858f663355eff93b745e-Abstract.html>.

### {#ishowspeed-deepfake}

Yin-Poole, W. (2025) “IShowSpeed Slams Sora 2 Deepfakes That Feature the Streamer Kissing Fans, Racing Animals, and Declare He Is Gay.” IGN. Available at: <https://www.ign.com/articles/ishowspeed-slams-sora-2-deepfakes-that-feature-the-streamer-kissing-fans-racing-animals-and-declare-he-is-gay>.

### {#big-other}

Zuboff, S. (2015) “Big Other: Surveillance Capitalism and the Prospects of an Information Civilization,”
*Journal of Information Technology*, 30(1), pp. 75–89. Available at: <https://doi.org/10.1057/jit.2015.5>.

### {#microsoft-ai}

“Microsoft Responsible AI Standard, v2” (2022). Microsoft. Available at: <https://www.microsoft.com/en-us/ai/principles-and-approach/>.