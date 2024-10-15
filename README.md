<div align="center">

![dwyl-style-guide-intro-hero-image-yellow-text](https://github.com/user-attachments/assets/1e20cfa5-94b9-4a28-8e01-8b460b4a653a)

A style guide sets standards and improves communication.
~ [wikipedia.org/Style_guide](https://en.wikipedia.org/wiki/Style_guide)

This style guide is a
[**work-in-progress**](https://en.wikipedia.org/wiki/Work_in_process)
we **need _your_ help** to _maintain_ and extend it. 🙏

[![contributions welcome](https://img.shields.io/badge/contributions-welcome-brightgreen.svg?style=flat-square)](https://github.com/dwyl/style-guide/issues)
[![HitCount](https://hits.dwyl.com/dwyl/style-guide.svg?style=flat-square)](https://hits.dwyl.com/dwyl/style-guide)

</div>

- [Why?](#why)
- [General](#general)
  - [Indentation](#indentation)
  - [_Intelligently_ Comment Code](#intelligently-comment-code)
  - [Quotes](#quotes)
- [Git](#git)
  - [Issues](#issues)
  - [Commits](#commits)
  - [Pull Requests](#pull-requests)
    - [_Reviewing_ PRs](#reviewing-prs)
  - [Naming Repos](#naming-repos)
- [Markdown](#markdown)
- [CSS](#css)
  - [General points](#general-points)
  - [Indentation](#indentation-1)
  - [Naming Conventions](#naming-conventions)
- [Grouping Properties](#grouping-properties)
  - [JavaScript](#javascript)
  - [Variable naming](#variable-naming)
- [Recommended Reading](#recommended-reading)
  
## Why?

**_Consistency_**.

Creative people often like to do things their own way.
That can often lead to projects that look wildly different from each other.
This slows down new people and wastes time.
We need **_everything_ consistent** so new people
_don't have to work through personal formatting quirks_
of previous engineers and can **focus on the code**. 🎯

## General

### Indentation

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

### _Intelligently_ Comment Code

We favour the _intelligent approach_.

Many developers (not us) believe that
[well-written code doesn't need comments](http://sublimecoding.com/blog/2015/01/12/dont-comment-your-code-rewrite-it).
Whilst it's true that
**adding too many comments to your code makes it _unreadable_**.
The key is: **put yourself in the shoes of the _next_ person who has to work with the code**.

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

### Quotes

**Use `"` _double_ quotes `"` for `Strings`**,
except
When constructing a string including properties
which are themselves denoted by single quotes:
e.g: `var str = "<a class='big' href='/mylink'>click me</a>"`;

## Git

### Issues

+ Your issue/pull request `title` should be **short but descriptive**
+ Use **`labels`** please! see:
[dwyl/labels](https://github.com/dwyl/labels?tab=readme-ov-file#our-list-of-labels--%EF%B8%8F)
+ If you want someone specific to look at your issue, **assign it to them**
+ **When referring to a file**, always do so
  within the **context of a _specific_ commit**
  (as that file could be constantly changing and your issue will quickly stop making sense)
  + Example: [https://github.com/dwyl/style-guide/blob/<b>dea0009638b7923521a13190f17090af37a7ff22</b>/README.md](https://github.com/dwyl/style-guide/blob/dea0009638b7923521a13190f17090af37a7ff22/README.md)
  + and **_not_** https://github.com/dwyl/style-guide/blob/master/README.md
  + To get this URL, go to the _History_ tab on the top right of your document and choose a commit form the list that appears    
  <img width="288" alt="history-tab-on-git-documents" src="https://cloud.githubusercontent.com/assets/4185328/9290455/55d5dc6e-438c-11e5-851d-71127213f565.png">
+ **When referring to a specific piece of code, include the line number** that code is on
  + You can either add this by add `#L` and the line number to the end of the URL (e.g. https://github.com/dwyl/hapi-socketio-redis-chat-example/blame/b26354e3f37b2bdd0414b9b01bfe45db7ee9504e/lib/chat.js#L6) **or**
  + Go to a specific commit (as above), click on 'View' and then click on 'Blame' in the top right hand corner    
  <img width="274" alt="blame-tab-on-git-documents" src="https://cloud.githubusercontent.com/assets/4185328/9290470/e46c2578-438c-11e5-95a7-19dfbcf82b00.png">
  + You can now click on any line and the line number will be added to the URL

### Commits

+ Use the **third person present tense** in your commit messages,
  as if you were finishing off the sentence _"This commit message..."_
  e.g: _"adds atm.js to index.html #420"_ or _"fixes disappearing content bug #12"_
+ **Include an issue number in _every_ commit message**
  + The commit message will then appear within that issue and ensure traceability of every contribution.
  
<img width="704" alt="commit-message-referenced-from-issue" src="https://cloud.githubusercontent.com/assets/4185328/9212670/dda6840c-4082-11e5-8e58-c4077f5ab089.png">

+ Keep your commits **'common sensibly small'**
  + A good rule of thumb is that _if you have to use the word "and"
  in your commit message, you're probably doing too much in a single commit_
  unless the things you're committing are intrinsically tied together.
+ **If you're pairing**, consider giving your pair some credit
  in your commit messages by including their initials:

<img width="723" alt="paired-commit-message" src="https://cloud.githubusercontent.com/assets/4185328/9212496/3adc19c2-4081-11e5-956c-8655c1f37946.png">

+ Did you know you can
  [use emojis in your commit messages](https://github.com/dwyl/start-here/issues/49)?

<img width="695" alt="emojis-in-commit-messages" src="https://cloud.githubusercontent.com/assets/4185328/9212573/14112b74-4082-11e5-822e-bc66250c5712.png">

### Pull Requests

A _good_ pull request (PR) reduces the back and forth
required between the person submitting the PR
and the assigned reviewer,
[saving _everyone_ time](https://github.com/dwyl/start-here/blob/63468a6bc020f88c762465823da7419478f29687/manifesto.md#your-time-should-never-be-wasted).

For our guidelines on contributing pull requests to dwyl projects,
please see:
[dwyl/contributing](https://github.com/dwyl/contributing)

#### _Reviewing_ PRs

+ [Inline comments on github](https://help.github.com/articles/commenting-on-the-diff-of-a-pull-request/)
  are very useful when reviewing pull requests,
  both for traceability and speed of review.

<img width="940" alt="add-comment-inline-in-pr-comment-box"
  src="https://cloud.githubusercontent.com/assets/4185328/9238544/0d293b20-414b-11e5-8604-15ba4f229525.png">

### Naming Repos

+ We favour one-word names for **node modules**
  (make sure the name is available)
  and _descriptive_ names for everything else
  (especially tutorials!)

## Markdown

We recommend being competent in **`Markdown`**
as we use it every day.
[markdown cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet).
For readability, we use:

+ `_` _underscores_ `_` for _italics_
+ `**` **double asterisks** `**` for **bold**
+ `+` plus signs for bullet points
  (so they're not confused with bold or italics on first glance)

## CSS

### General points

+ Learn and Use `Tailwind CSS`
  [dwyl/learn-tailwind](https://github.com/dwyl/learn-tailwind)
+ If you use a _separate_ CSS file,
  use _classes_, **not IDs** as your hooks
+ Explicitly select **what you want** rather than fumbling around
  the `HTML` structure searching for hooks - practice good
  [_selector intent_](http://csswizardry.com/2012/07/shoot-to-kill-css-selector-intent/)
  + i.e: if you're styling a site's navigation,
  style `primary-nav` instead of `header ul`
+ Pick class names that are as re-usable as possible
  (e.g. pick `primary-nav` over `site-nav`)

### Indentation

CSS indentation should mirror the `HTML` markup structure,
e.g: 

```css
.article {}
  .article-quote {}
```

### Naming Conventions

When we need to apply styles to an element, use:

+ Semantic class names (e.g. not `green-btn` but `primary-action-btn`)
+ BEM-like _modifier_ syntax (using `--`), e.g. modifying `.site-logo` to `.site-logo--xmas`

## Grouping Properties

+ Group properties **by type**
  e.g: `font` and `text-align` properties would sit together,
  as would `border`, `display`, `height` and `width` properties
+ For further organisation, favour alphabetical ordering
  (grouping by type _always_ takes precedence)


### JavaScript

+ **Use semicolons** please!
+ **No trailing commas** on object declarations:

```javascript
const example_object = {
    name: 'dwyl',
    age: 1 //<-- Having a comma after the '1' would be a 'trailing comma' 
};
```

### Variable naming

+ If you can, use a descriptive **one word** variable name
+ If one word isn't enough, **use underscores to separate words**
  ([`snake_case`](https://en.wikipedia.org/wiki/Snake_case))
  and not [`camelCase`](https://en.wikipedia.org/wiki/CamelCase),
  e.g: `let auth_token = "e2jxyz.etc.etc`

## Recommended Reading

+ 29 Well-Designed Online Style Guides
[webdesignledger.com/29-online-style-guides](https://webdesignledger.com/29-online-style-guides/)