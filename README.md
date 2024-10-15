<div align="center">

![dwyl-style-guide-intro-hero-image-yellow-text](https://github.com/user-attachments/assets/1e20cfa5-94b9-4a28-8e01-8b460b4a653a "dwyl style guide retro game start screen")

A style guide **sets standards** and **improves communication**.
~ [wikipedia.org/Style_guide](https://en.wikipedia.org/wiki/Style_guide)

This style guide is a
[**work-in-progress**](https://en.wikipedia.org/wiki/Work_in_process)
we **need _your_ help** to _maintain_ and extend it. 🙏 <br />
If you spot something that can be improved
or have a question, please
[open an issue](https://github.com/dwyl/style-guide/issues). 💬

[![contributions welcome](https://img.shields.io/badge/contributions-welcome-brightgreen.svg?style=flat-square)](https://github.com/dwyl/style-guide/issues)
[![HitCount](https://hits.dwyl.com/dwyl/style-guide.svg?style=flat-square)](https://hits.dwyl.com/dwyl/style-guide)

</div>

- [Why? 🤷🏻‍♀️](#why-️)
- [General 👋](#general-)
  - [Indentation ✌️](#indentation-️)
  - [_Intelligently_ Comment Code 💬](#intelligently-comment-code-)
  - [Quotes 🧵](#quotes-)
- [Git 👩‍💻](#git-)
  - [Issues 📝](#issues-)
  - [Commits ✨](#commits-)
  - [Pull Requests 🚀](#pull-requests-)
    - [_Reviewing_ PRs 👀](#reviewing-prs-)
    - [Use In-line Code Suggestions in PRs! 📝](#use-in-line-code-suggestions-in-prs-)
  - [Naming Repos 🌹](#naming-repos-)
  - [Naming Files 🗄️](#naming-files-️)
- [Markdown ⬇️](#markdown-️)
  - [Use Descriptive Link Text 🔗](#use-descriptive-link-text-)
    - [Avoid One-Word Non-Semantic Link Text](#avoid-one-word-non-semantic-link-text)
  - [Semantic Line Breaks ↩](#semantic-line-breaks-)
    - [Example 💡](#example-)
    - [_Exception_? 💭](#exception-)
- [CSS 🌈](#css-)
  - [Formatting 🦄](#formatting-)
  - [Naming Conventions 🍓](#naming-conventions-)
- [Grouping Properties 👥](#grouping-properties-)
  - [JavaScript ☕](#javascript-)
  - [Variable Naming 🐍](#variable-naming-)
  - [`README` Badges? \](https://github.com/dwyl/style-guide/issues)](#readme-badges-httpsgithubcomdwylstyle-guideissues)
- [Recommended Reading 📖](#recommended-reading-)
- [Star it ⭐](#star-it-)
  
## Why? 🤷🏻‍♀️

**_Consistency_**. 😍

Creative people often like to do things their own way.
That's great if you are working _alone_
but not so good on an established team.
Many different styles leads to projects
that look wildly different from each other.
This slows down new people and wastes time.
We need **_everything_ consistent** so new people
don't have to work through _personal formatting quirks_
of previous engineers and can **focus on the feature**. 🎯

## General 👋

We follow a handful of general principals
to keep our projects running smoothly,
easy to
[onboard](https://en.wikipedia.org/wiki/Onboarding)
and
_maintain_.

### Indentation ✌️

We use
**2 spaces for indentation**
see:
[developer setup guide](https://github.com/dwyl/dev-setup?tab=readme-ov-file#basic-text-editor-setup)
for tips on setting this kind of thing up in your text editor.

This isn't up for debate.
There is no **`tab`** key on Smartphones;
which is the most ubiquitous input device.
If **we don't want to _exclude_ people**
who don't have a full-size keyboard,
we can _only_ use spaces.

> 💡 **Tip**: use the
> [`.editorconfig`](/.editorconfig)
> file to automatically define the indentation settings in your editor. 

### _Intelligently_ Comment Code 💬

We favour the _intelligent approach_ to commenting code.

Many developers (not us) believe that
[well-written code doesn't need comments](http://sublimecoding.com/blog/2015/01/12/dont-comment-your-code-rewrite-it).
Whilst it's true in a tiny hello world app where there almost no code,
it's not the case in a project with many thousands of lines
that has to be
[**_groked_**](https://en.wikipedia.org/wiki/Grok)
by several people of varying experience/skill levels.
Yes, in some cases
**adding _too many_ comments** can also make it **_unreadable_**.
The key is:
**put yourself in the shoes** of the
[**_next_ person**](https://www.goodreads.com/quotes/248194-always-code)
**who has to work with the code**.

If you feel **your code is as simple as it can be**
but what it does isn't immediately obvious, then **add a comment**.
Good examples of this are when something in your code
in one location necessarily has an impact elsewhere.

```javascript
// JavaScript example
else {
  mod = moduleName.replace('.js', '.\.js'); // escape .js for regex
}
```

```css
/* CSS example */
.article {
  position: relative; /* contains `.quote` which is positioned absolutely */
  ...
}
```

> **Note**: try not to be offended if someone reviewing your PR/code
> asks you to **please add comments**.
> It's because they have _experience_ of reading lots of code
> and want to help the _next_ person understand it the way you do _now_.

### Quotes 🧵

**Use `"` _double_ quotes `"` for `Strings`**,
except when constructing a string including properties
which are themselves denoted by single quotes:
e.g: `var str = "<a class='big' href='/mylink'>click me</a>"`;

Most programming languages we use,
e.g:
[`HTML`](https://stackoverflow.com/a/2373171/1148249),
[`JavaScript`](https://stackoverflow.com/questions/242813),
[`Dart`](https://stackoverflow.com/a/54014914/1148249)
allow single and double quotes to be used _interchangeably_.
But `Elixir` and `JSON` do not.
`String` in `Elixir` _must_ use double-quotes,
and _valid_ `JSON` keys/values _must_ be surrounded by double-quotes.
This is why we use double-quotes for `Strings`;
it makes everyone's life easier/faster when switching between code bases.

Again, this isn't a debate. 😊

## Git 👩‍💻

If you are new to `Git` and/or `GitHub`
we recommend reading our **`Git` Guide**:

### Issues 📝

**`GitHub` Issues** are how we do the vast majority
of our
[asynchronous communication](https://en.wikipedia.org/wiki/Asynchronous_communication).
We follow a simple set of rules that streamline everything:

1. Your issue/pull request `title` should be **short but descriptive**

2. Use **`labels`** please! see:
[dwyl/labels](https://github.com/dwyl/labels?tab=readme-ov-file#our-list-of-labels--%EF%B8%8F)

3. To request the input of a specific person on an Issue or PR,
   mention them in a comment
   and if you want to _delegate_ a task **assign it to them**.
   However, don't just assign issues/PRs without any explanation,
   that's called [Buck passing](https://en.wikipedia.org/wiki/Buck_passing)

4. When referring to a file, always do so
  within the **context of a _specific_ commit**
  (as that file could be constantly changing
  and your issue will quickly stop making sense)
  Example:
  [https://github.com/dwyl/style-guide/blob/dea0009638b7923521a13190f17090af37a7ff22/README.md](https://github.com/dwyl/style-guide/blob/dea0009638b7923521a13190f17090af37a7ff22/README.md)
  and **_not_** https://github.com/dwyl/style-guide/blob/master/README.md
  To get this URL, go to the _History_ tab on the top right of your document
  and choose a commit form the list that appears
  <img width="288" alt="history-tab-on-git-documents" src="https://cloud.githubusercontent.com/assets/4185328/9290455/55d5dc6e-438c-11e5-851d-71127213f565.png">

5. When referring to a specific piece of code,
  include the line number that code is on.
  Either add this by add `#L` and the line number
  to the end of the URL
  (e.g. https://github.com/dwyl/hapi-socketio-redis-chat-example/blame/b26354e3f37b2bdd0414b9b01bfe45db7ee9504e/lib/chat.js#L6) **or**
  Go to a specific commit (as above), click on 'View'
  and then click on 'Blame' in the top right hand corner:
  <img width="274" alt="blame-tab-on-git-documents" src="https://cloud.githubusercontent.com/assets/4185328/9290470/e46c2578-438c-11e5-95a7-19dfbcf82b00.png">
  You can now click on any line and the line number will be added to the URL

### Commits ✨

1. Use the **third person present tense** in your commit messages,
  as if you were finishing off the sentence _"This commit message..."_
  e.g: _"adds atm.js to index.html #420"_ or _"fixes disappearing content bug #12"_
2. **Include an issue number in _every_ commit message**
  + The commit message will then appear within that issue and ensure traceability of every contribution.
  
<img width="704" alt="commit-message-referenced-from-issue" src="https://cloud.githubusercontent.com/assets/4185328/9212670/dda6840c-4082-11e5-8e58-c4077f5ab089.png">

1. Keep your commits **'common sensibly small'**
  + A good rule of thumb is that _if you have to use the word "and"
  in your commit message, you're probably doing too much in a single commit_
  unless the things you're committing are intrinsically tied together.
1. **If you're pairing**, consider giving your pair some credit
  in your commit messages by including their initials:

<img width="723" alt="paired-commit-message" src="https://cloud.githubusercontent.com/assets/4185328/9212496/3adc19c2-4081-11e5-956c-8655c1f37946.png">

+ Did you know you can
  [use emojis in your commit messages](https://github.com/dwyl/start-here/issues/49)?

<img width="695" alt="emojis-in-commit-messages" src="https://cloud.githubusercontent.com/assets/4185328/9212573/14112b74-4082-11e5-822e-bc66250c5712.png">

### Pull Requests 🚀

A _good_ pull request (PR) reduces the back and forth
required between the person submitting the PR
and the assigned reviewer,
[saving _everyone_ time](https://github.com/dwyl/start-here/blob/63468a6bc020f88c762465823da7419478f29687/manifesto.md#your-time-should-never-be-wasted).

For our guidelines on contributing pull requests to dwyl projects,
please see:
[dwyl/contributing](https://github.com/dwyl/contributing)

#### _Reviewing_ PRs 👀

Use 
[inline comments on github](https://help.github.com/articles/commenting-on-the-diff-of-a-pull-request/)
when reviewing pull requests,
both for traceability and to help the person submitting the PR improve.

<img width="940" alt="add-comment-inline-in-pr-comment-box"
  src="https://cloud.githubusercontent.com/assets/4185328/9238544/0d293b20-414b-11e5-8604-15ba4f229525.png">

#### Use In-line Code Suggestions in PRs! 📝

When there is a simple/obvious code or copy change
that can be made in a Pull Request to save time,
simply use the code suggestion button in the PR comment.

Hover over the line of code where you'd like to add a comment,
and click the blue comment icon:

![add-comment](https://github.com/user-attachments/assets/c23e9c86-e678-4b10-a7f4-c38cb391e365)

to suggest a specific change to the line or lines, click `±`,
then edit the text within the suggestion block.

![make-code-suggestion](https://github.com/user-attachments/assets/49ee6ecf-aa63-4aca-a2d1-b03e10053fda)

See:
[docs.github.com/en/pull-requests/collaborating-with-pull-requests](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/reviewing-changes-in-pull-requests/reviewing-proposed-changes-in-a-pull-request)

### Naming Repos 🌹

We favour one-word names for repos and **node modules**
(make sure the name is available).
e.g:
+ [`fields`](https://github.com/dwyl/fields)
+ [`gcal`](https://github.com/dwyl/gcal)
+ [`link`](https://github.com/dwyl/link)
+ [`useful`](https://github.com/dwyl/useful)
+ [`quotes`](https://github.com/dwyl/quotes)

When the name we want is "taken" on the package system we are using,
we add more words to the repo/package name separated by **hyphens**.
e.g:
+ [`aws-sdk-mock`](https://github.com/dwyl/aws-sdk-mock)
+ [`elixir-auth-github`](https://github.com/dwyl/elixir-auth-github)

> **Note**: we occasionally use underscores in repo names where
> we want to match the repo name to the _module_ name e.g:
> [`auth_plug`](https://github.com/dwyl/auth_plug) or
> [`dart_multihash`](https://github.com/dwyl/dart_multihash)
> However we try to minimize this and prefer hyphens.

If a single-word name is not possible, 
use _descriptive_ names
(especially for tutorials!)
e.g:
+ [`javascript-todo-list-tutorial`](https://github.com/dwyl/javascript-todo-list-tutorial)
+ [`phoenix-liveview-counter-tutorial`](https://github.com/dwyl/phoenix-liveview-counter-tutorial)
+ [`phoenix-liveview-realtime-cursor-tracking-tutorial`](https://github.com/dwyl/phoenix-liveview-realtime-cursor-tracking-tutorial)

The more descriptive the title
the easier it will be for someone to find when searching.

### Naming Files 🗄️

Always use `lowercase` names for files and directories.
The exception to this are the files `GitHub` creates by default
e.g:
`LICENSE`, `README.md`, `CONTRIBUTING` and `CODE_OF_CONDUCT`, etc.

## Markdown ⬇️

We recommend being competent in **`Markdown`**
as we use it every day.
[markdown cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet).
For readability, we use:

+ `_` _underscores_ `_` for _italics_
+ `**` **double asterisks** `**` for **bold**
+ `+` plus signs for bullet points
  (so they're not confused with bold or italics on first glance)
+ **Section Headings** should always be **followed by** a **blank line**.

### Use Descriptive Link Text 🔗

We prefer to _either_ use **_super_ descriptive link text**
e.g:

```md
Learn how to do what you love by reading the 
[start here repo](https://github.com/dwyl/start-here).
```

Or simply use the **`URL`** as the **link text**
e.g:

```md
Read our "start here" doc to learn how to do what you love:
[dwyl/start-here](https://github.com/dwyl/start-here)
```

This is infinitely better than non-semantic link text (inaccessible!)
which should be avoided at all costs!

#### Avoid One-Word Non-Semantic Link Text

Avoid including non-semantic link text e.g:

```md
You can find more info [here](https://en.wikipedia.org/wiki/Computer_security) on Cyber Security.
```

or

```md
[Click here](https://en.wikipedia.org/wiki/Pok%C3%A9mon_the_Series:_XYZ) for more details on **XYZ**.
```

Both of these examples are _horrible_ for accessibility and should be avoided.

Read more:
[mtu.edu/accessibility/training/web/link-text/](https://www.mtu.edu/accessibility/training/web/link-text/)

### Semantic Line Breaks ↩

When writing prose in `markdown`
or documentation text blocks for code,
we try to limit the line length to **80 characters** (within reason)
to aid readability/reviewability on smaller screens e.g: Laptops, Phones, etc.

We follow the
["Semantic Linefeed"](https://rhodesmill.org/brandon/2012/one-sentence-per-line)
rule
(or "one thought per line")
whereby we line-break each time there is a "though joining word"
such as "and", "or", "but", "therefore", "because", etc.
thus our sentences are 

#### Example 💡

Avoid super long lines of text:

```md
MR. JONES, of the Manor Farm, had locked the hen-houses for the night, but was too drunk to remember to shut the popholes. With the ring of light from his lantern dancing from side to side, he lurched across the yard, kicked off his boots at the back door, drew himself a last glass of beer from the barrel in the scullery, and made his way up to bed, where Mrs. Jones was already snoring.
```

This super long line of text is un-reviewable/maintainable.

Break it out by semantic sections:

```md
MR. JONES, of the Manor Farm,
had locked the hen-houses for the night,
but was too drunk to remember to shut the popholes.
With the ring of light from his lantern dancing from side to side,
he lurched across the yard,
kicked off his boots at the back door,
drew himself a last glass of beer from the barrel in the scullery,
and made his way up to bed,
where Mrs. Jones was already snoring.
```

_Where_ you place the line breaks is not as important as _having_ them.
i.e: just break up the long lines into smaller chunks that each have a though,
and try to keep them less than **80 chars** where possible/practical.

#### _Exception_? 💭

The _obvious_ exception to this is when there is a `URL`
that is longer than **80 chars**.
In those instances we will place the URL on its' own line
which again, makes it easier to read/maintain/update.
e.g:

```md
We follow the ["Semantic Linefeed"](https://rhodesmill.org/brandon/2012/one-sentence-per-line) rule in our markdown documents.
```

> **Note**: That sentence requires horizontal scrolling, a time-suck. 😕

Becomes:

```md
We follow the
["Semantic Linefeed"](https://rhodesmill.org/brandon/2012/one-sentence-per-line)
rule in our markdown documents.
```

Use your best judgement. keep it easy for the _humans_ to read! 👩🏻‍💻

## CSS 🌈

+ Learn and _Use_ `Tailwind CSS`
  [dwyl/learn-tailwind](https://github.com/dwyl/learn-tailwind)
  **great _interface_** is essential to a **great _experience_**.
+ If you use a _separate_ CSS file,
  use _classes_, **not IDs** as your hooks
+ Explicitly select **what you want** rather than fumbling around
  the `HTML` structure searching for hooks - practice good
  [_selector intent_](http://csswizardry.com/2012/07/shoot-to-kill-css-selector-intent/)
  + i.e: if you're styling a site's navigation,
  style `primary-nav` instead of `header ul`
+ Pick class names that are as re-usable as possible
  (e.g. pick `primary-nav` over `site-nav`)

### Formatting 🦄

CSS formatting and indentation should mirror the `HTML` markup structure,
e.g: 

```css
.article {}
  .article-quote {}
```

### Naming Conventions 🍓

When we need to apply styles to an element, use:

+ Semantic class names (e.g. not `green-btn` but `primary-action-btn`)
+ BEM-like _modifier_ syntax (using `--`), e.g. modifying `.site-logo` to `.site-logo--xmas`

## Grouping Properties 👥

+ Group properties **by type**
  e.g: `font` and `text-align` properties would sit together,
  as would `border`, `display`, `height` and `width` properties
+ For further organisation, favour alphabetical ordering
  (grouping by type _always_ takes precedence)

### JavaScript ☕

+ **Use semicolons** please!
+ **No trailing commas** on object declarations:

```javascript
const example_object = {
    name: 'dwyl',
    age: 1 //<-- Having a comma after the '1' would be a 'trailing comma' 
};
```

### Variable Naming 🐍

+ If you can, use a descriptive **one word** variable name
+ If one word isn't enough, **use underscores to separate words**;
  [`snake_case`](https://en.wikipedia.org/wiki/Snake_case))
  _not_ 
  [`camelCase`](https://en.wikipedia.org/wiki/CamelCase) <br />
  e.g: `let auth_token = "e2jxyz.etc.etc`

### `README` Badges? ![repo-bades](https://img.shields.io/badge/badges-please-brightgreen.svg?style=flat-square)](https://github.com/dwyl/style-guide/issues)

See:
[dwyl/repo-badges](https://github.com/dwyl/repo-badges)

## Recommended Reading 📖

+ 29 Well-Designed Online Style Guides
[webdesignledger.com/29-online-style-guides](https://webdesignledger.com/29-online-style-guides/)
+ Tips on writing Descriptive Link Text:
[mtu.edu/accessibility/training/web/link-text](https://www.mtu.edu/accessibility/training/web/link-text/)
+ Useful tips for better commit messages:
[thoughtbot.com/5-useful-tips-for-a-better-commit-message](https://robots.thoughtbot.com/5-useful-tips-for-a-better-commit-message)
+ CSS for Software Engineers:
[speakerdeck.com/csswizardry/css-for-software-engineers](https://speakerdeck.com/csswizardry/css-for-software-engineers-for-css-developers)

## Star it ⭐

The best way to let everyone know you have read
and _understood_ this style guide is to
star the repo on `GitHub`. 🌟

Thank you! ❤️
