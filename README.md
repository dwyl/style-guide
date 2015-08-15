#dwyl Style Guide 

>A style guide is a set of standards [which] establish and enforce style to improve communication.

<small>_https://en.wikipedia.org/wiki/Style_guide_</small>

**_This style guide is a work in progress and is being put together over the course of [#dwylsummer](https://github.com/dwyl/summer-2015)_**.

[![contributions welcome](https://img.shields.io/badge/contributions-welcome-brightgreen.svg?style=flat)](https://github.com/dwyl/style-guide/issues) Please open an issue if you have an questions or comments at all!

For now, the **visual** and **coding styles** [will live in the _same repo_](https://github.com/dwyl/summer-2015/issues/22). If the size of this readme gets out of hand or if we have a lot of requests to separate them, we'll do so.

##Contents Guide
+ [Why?](#why)
+ [General guidelines](#general)
  + [2 Space indentation](#indentation)
  + [Intelligently commenting your code](#intelligently-commenting-your-code)
  + [Single quotes](#quotes)
+ [Git](#git) 
  + [Issues](#issues)
  + [Commits](#commits)
  + [Pull requests](#pull-requests)
  + [Naming repositories](#naming-repos)
+ [Markdown](#markdown)
+ [ ] [CSS](#css)
+ [ ] [JavaScript](#javascript)
  

##Why?
**Consistency**.    

Every developer likes to do things their own way.    
Even though we have our own idea of what maintainable code looks like, _the important thing_ isn't how many spaces we indent our code with but that **everything is consistent** so new people _don't have to work through personal formatting quirks_ of previous developers and can **focus on the code**.
<br/>
<br/>

##General

###Indentation
**2 space indentation**.    
You can usually set this up in the _Preferences_ of your favourite text editor so you never have to think about it again (example below on [Atom editor](https://atom.io/)).

<img width="507" alt="atom-soft-tab-preferences-menu" src="https://cloud.githubusercontent.com/assets/4185328/9154618/a6598690-3e91-11e5-939b-2c03cf3c7ffc.png">

###Intelligently commenting your code
We favour the _intelligent approach_.

Many developers (not us) believe that [well-written code doesn't need comments](http://sublimecoding.com/blog/2015/01/12/dont-comment-your-code-rewrite-it).
Whilst it's true that **adding too many comments to your code makes it unreadable**. The key is to **put yourself in the shoes of the next person who has to work with your code**. 

If you feel **your code is as simple as it can be** but what it doesn't isn't immediately obvious, then add a comment.    
Good examples of this are when something in your code in one location necessarily has an impact elsewhere.

```javascript
//JavaScript example
else {
  mod = moduleName.replace('.js', '.\.js'); //escape .js for regex
}
```

```css
/*CSS example*/
.article {
  position: relative; /*contains `.quote` which is positioned absolutely*/
  ...
}
```
###Quotes
**Use `'` single quotes `'` everywhere**, except: 
+ When constructing a string including properties which are themselves denoted by single quotes:   
e.g: `var str = "<a class='big' href='/mylink'>click me</a>"`;
+ When *manually* creating a **JSON** object/file (as these [are not valid JSON](https://github.com/dwyl/style-guide/issues/5#issuecomment-130252764))

<br/>

##Git

###Issues
+ Your issue title should be **short but descriptive**
+ Use **labels** please!
+ If you want someone specific to look at your issue, **assign it to them**
+ **When referring to a file**, always do so within the **context of a specific commit** (as that file could be constantly changing and your issue will quickly stop making sense)
  + Example: [https://github.com/dwyl/style-guide/blob/<b>dea0009638b7923521a13190f17090af37a7ff22</b>/README.md](https://github.com/dwyl/style-guide/blob/dea0009638b7923521a13190f17090af37a7ff22/README.md) and _not_ https://github.com/dwyl/style-guide/blob/master/README.md
  + To get this URL, go to the _History_ tab on the top right of your document and choosing a commit form the list that appears    
  <img width="288" alt="history-tab-on-git-documents" src="https://cloud.githubusercontent.com/assets/4185328/9290455/55d5dc6e-438c-11e5-851d-71127213f565.png">
+ **When referring to a specific piece of code, include the line number** that code is on
  + You can either add this by add `#L` and the line number to the end of the URL (e.g. https://github.com/dwyl/hapi-socketio-redis-chat-example/blame/b26354e3f37b2bdd0414b9b01bfe45db7ee9504e/lib/chat.js#L6) **or**
  + Go to a specific commit (as above), click on 'View' and then click on 'Blame' in the top right hand corner    
  <img width="274" alt="blame-tab-on-git-documents" src="https://cloud.githubusercontent.com/assets/4185328/9290470/e46c2578-438c-11e5-95a7-19dfbcf82b00.png">
  + You can now click on any line and the line number will be added to the URL

###Commits
+ Use the **third person present tense** in your commit messages, as if you were finishing off the sentence _"This commit message..."_
  + For example _"adds riot.js to index"_ or _"fixes #12 disappearing content bug"_
+ **Include an issue number in _every commit message_**
  + The commit message will then appear within that issue and ensure traceability of every contribution    
  
<img width="704" alt="commit-message-referenced-from-issue" src="https://cloud.githubusercontent.com/assets/4185328/9212670/dda6840c-4082-11e5-8e58-c4077f5ab089.png">
+ Keep your commits **'common sensibly small'**
  + A good rule of thumb is that _if you have to use the word 'and' in your commit message, you're probably doing too much in a single commit_ unless the things you're committing are intrinsically tied together.
+ **If you're pairing**, consider giving your pair some credit in your commit messages by including their initials:

<img width="723" alt="paired-commit-message" src="https://cloud.githubusercontent.com/assets/4185328/9212496/3adc19c2-4081-11e5-956c-8655c1f37946.png">
+ Did you know you can [use emojis in your commit messages](https://github.com/dwyl/start-here/issues/49)? It's totally a thing.
<img width="695" alt="emojis-in-commit-messages" src="https://cloud.githubusercontent.com/assets/4185328/9212573/14112b74-4082-11e5-822e-bc66250c5712.png">



###Pull Requests
Good pull requests (PR) reduce the back and forth required between the person submitting the PR and the assigned reviewer, saving everyone time.
+ Before submitting a PR, **open a new issue** so you can _confirm the need_ for the functionality you are intending to add (like in [this example](https://github.com/indexzero/ps-tree/issues/10))
+ When you submit your pull request, include:
  + A **descriptive title** that answers the question "What does this PR do?"
  + A reference to the issue that the PR solves
  + An explanation of what the PR includes (**bullet pointed lists** are sometimes helpful to make things clearer) and the _implementation detail_
  + An **update to the documentation** (often the repo's readme)
  + **Assign your pull request** to someone for review (this person will be the first point of contact if the PR merges a bug into the production environment)
  
A good example is this one: https://github.com/indexzero/ps-tree/pull/12

####Reviewing pull requests
+ [Inline comments on github](https://help.github.com/articles/commenting-on-the-diff-of-a-pull-request/) are very useful when reviewing pull requests, both for traceability and speed of review.

<img width="940" alt="add-comment-inline-in-pr-comment-box" src="https://cloud.githubusercontent.com/assets/4185328/9238544/0d293b20-414b-11e5-8604-15ba4f229525.png">

###Naming repos
+ We favour one-word names for **node modules** (make sure the name is available [on npm](http://www.npmjs.com)) and descriptive names for everything else (especially tutorials!)

<br/>

##Markdown
[This is a good reference for markdown syntax](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet).    
For readability, we use `_` _underscores_ `_` for _italics_ and `**` **double asterisks** `**` for **bold**.

<br/>

##CSS
###General points
+ Use _classes_, **not IDs** as your hooks
+ Explicitly select **what you want** rather than fumbling around the HTML structure searching for hooks - practice good [_selector intent_](http://csswizardry.com/2012/07/shoot-to-kill-css-selector-intent/)
  + i.e. if you're styling a site's navigation, style `primary-nav` instead of `header ul`
+ Pick class names that are as re-usable as possible (e.g. pick `primary-nav` over `site-nav`)

###Indentation
CSS indentation should mirror the HTML structure.
```css
.article {}
  .article-quote {}
```

###Naming conventions
**_For now_**, we _don't_ use [BEM CSS naming conventions](https://github.com/dwyl/start-here/issues/41) as it doesn't provide the _flexibility_ we feel we need during the early stages of our work.     
Here's what we _do_ use:
+ Semantic class names
+ BEM-like _modifier_ syntax (using `--`), e.g. modifying `.site-logo` to `.site-logo--xmas`




<br/>
##JavaScript
Semicolons please!

https://github.com/dwyl/summer-2015/issues/22


