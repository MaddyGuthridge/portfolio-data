# Representing gender programmatically

<small>Maddy Guthridge --- September 30th, 2023</small>

Gender is a property that is central to many people's identities, but representing it in software isn't as simple as it initially may seem. In this extremely serious blog post, I explore the complexity of representing identity programmatically, and discuss best-practices for inclusive software design.

<!--more-->

## Gender is complicated

So as I'd hope you know, gender isn't a simple binary.

```rust
let gender: bool = false;  // male
let gender: bool = true;  // female
```

First of all, trans people exist so that variable needs to be mutable.

```rust
let mut gender: bool = false;
```

But additionally, this doesn't allow for non-binary folks to express their identity. A naive approach would be to simply use some kind of enum, such as the following:

```rust
enum Gender {
    Male,
    Female,
    Other,
};
```

But even then, this doesn't account for those who only partially identify with a label, or those that identify with multiple.

```rust
enum GenderComponent {
    Male(f32),
    Female(f32),
    Other(f32),
}

type Gender = Vec<GenderComponent>;
```

In the above implementation, users can specify any combination of "gender components" with each component including a value to represent the "strength" of that identification (ranging from `-inf` to `inf`. I have elected to use an `f32` to represent this data with the hope that 32 bits of floating point precision will be enough to satisfy most individuals, although ideally one would use a hypothetically infinite-precision number type, perhaps with a library such as [rug](https://docs.rs/rug/latest/rug/) (which conveniently also supports imaginary numbers to represent the $\mathbb{C}omplex$ relationship some people have with these components of their identity).

Unfortunately, even then, our type definitions don't even come close to satisfying the complexity of gender identity.

## Abandoning static typing

While we could continue to add more and more complexity to our type system, the difficulty of representing it gets exponentially more complex as more nuance is introduced. As such, it is with a heavy heart that we are forced to abandon the safety of Rust.

When considering the design requirements, I was initially drawn to JavaScript due to the distinction it makes between `undefined` and `null`, which could be useful for encapsulating the similar distinction between [agender](https://nonbinary.wiki/wiki/Agender) and [neutrois](https://nonbinary.wiki/wiki/Neutrois) identities, respectively. JavaScript also offers a powerful object literal syntax that could prove to be a powerful way to represent and interpret the many aspects of gender identity.

```js
let gender = {
  presentAs: "masculine",
  pronouns: ["they", "them"],
  internal: null,
}
```

However, as a JavaScript hater, I was dissatisfied with this answer. Considering Python, we find a much more clearly-defined type system, which will help make our definitions easier to write and maintain. Of particular interest is the `...` ellipsis type, which is the semantic equivalent of a shoulder shrug. This could be especially useful to people who identify as [gender neutral](https://nonbinary.wiki/wiki/Gender_neutral).

```python
gender = ...
```

## Gender isn't constant

However, one critical oversight of our current system is the assumption of a static, rarely-changing identity. For [genderfluid](https://nonbinary.wiki/wiki/Genderfluid) folks, this is not the case - their identities can change frequently, even minute-to-minute. The cleanest way to represent this complexity is by making our gender data structure contain methods for fetching the latest available information. For example, one could represent such an identity as follows:

```js
let gender = {
  label: "gender-fluid",
  pronouns: async () => {
    const res = await fetch("api.miguelguthridge.com/pronouns");
    const data = await res.json();
    return data["pronouns"];
  }
};
```

Such a data structure would be extremely effective for allowing users to declare their identity in a way that best reflects them, with the added flexibility of duck-typed code allowing for them to add or remove data points to fully encapsulate their identity. A simple implementation of the required server route could be written in Express.

```js
import express, { json, cors } from "express";

const app = express();
app.use(json());
app.use(cors());

app.get("/pronouns", (req, res) => {
  res.json({
    // Modify as required
    pronouns: ["they", "them"],
  });
});

app.listen();
```

This solution is especially well-suited for representing gender identity, as peoples' self-expression is only limited by their programming ability. Additionally, it can easily be self-hosted by any tech-savvy non-binary individual, only requiring a Linux server, ownership of a domain, and a stable internet connection to function correctly.

## Sharing data structures

While our design of a flexible and adaptable data structure design provides an excellent medium for gender-diverse folks to express themselves, only requiring a year or two of a software engineering degree to understand, a solution for allowing identities to be shared is less apparent. Fortunately, many interpreted languages offer a simple solution. Here is a simple implementation for a backend route updating a user's gender identity, written in Python with the Flask framework.

```python
@app.post("/profile/gender")
def update_gender():
    # Additional validation would be performed to ensure
    # validity of session token etc
    user = user_lookup(request.headers["Authorization"])
    body = json.loads(request.data)
    user.gender = eval(body["gender"])
```

The use of the [`eval` function](https://docs.python.org/3/library/functions.html#eval) provides a simple way to accept any kind of complex data that users may require to fully represent their identity. To further improve this design, one could even consider serving the code that users upload to other users' machines in order to allow one's identity to be presented differently to different individuals - the possibilities are endless!

## Explaining the joke

The unfortunate risk of writing satire at 1:30 AM is the chance that one's work will be misinterpreted, either due to deficiencies in my own writing ability, or due to malicious interpretations from those for whom the humour wasn't intended for them. As such, I'm also including a quick explanation of what I meant by this post.

Essentially, gender identity is infinitely complex, and nuanced. The more I've learnt about it over the past few months, the more I've realised there is to learn. I don't believe that it is possible to capture this complexity in something as simple as some computer software. While labelling things is important as a way to find connections and understand others, the idea that this can completely represent the full depth and scope of someone's identity is laughable. I certainly haven't found a label that properly encapsulates my own identity yet.

Instead, it's far better to give users the tools to convey the information they choose to disclose in a clear, accessible manner. Some design decisions that can help to facilitate this are:

- Allow for custom inputs in "gender" fields - "man", "woman" and "non-binary" simply cannot represent the full diversity of identities.
- Offer a diverse range of pronoun choices, and ensure that they all read correctly within the context of your software (if I have to read one more sentence that includes "they has..." I will have a stroke). It is be even better to allow users to enter their own pronouns, and choose the variants of surrounding words (eg "is" vs "are") to allow them to fully express themselves.
- Include an "explanation" field where users can (optionally) provide more information about their identity, to help them share and explain their gender identity to others, allowing for much more nuance than a single label could ever provide.
- Offer powerful privacy options, so that users can control who sees what with regards to their identity. An excellent example of this is Discord which lets you choose different pronouns for each community you are a member of.
- Ensure that users can easily opt out of sharing information about their gender identity at all. It can be a sensitive subject for some, so letting people choose not to disclose information is an essential part of supporting diversity.
- Finally, consider whether you even need to collect information on gender identity, and if you don't need to, don't collect it. While it can be useful for letting users flesh out their profiles on social media, declaring one's gender identity is completely unnecessary for most other systems, such as online shopping accounts. Of course, data brokers would disagree with me here, but they can deal with it.

Of course, I'm only one person, and I'm pretty new to learning about gender at this level of depth. I sincerely apologise if I've gotten anything wrong or misunderstood anything (please get in touch if you think there are edits I could make that would improve this post). If anything about this post upset you please let me know, and I'll do my best to make things right, unless you're a transphobe in which case go away. 

Regardless, I hope you enjoyed this byproduct of my brain performing a meta-analysis on itself.

Until next time,
<br>
Miguel (they/them?)

