#dwyl Style Guide

>A style guide is a set of standards [which] establish and enforce style to improve communication.

<small>_https://en.wikipedia.org/wiki/Style_guide_</small>

**_This style guide is a work in progress and is being put together over the course of [#dwylsummer](https://github.com/dwyl/summer-2015)_**.

For now, the **visual** and **coding styles** [will live in the _same repo_](https://github.com/dwyl/summer-2015/issues/22). If the size of this readme gets out of hand or if we have a lot of requests to separate them, we'll do so.

##Contents Guide
+ [Why?](#why)
+ [General guidelines](#general)
  + [Indentation](#indentation)
  + [Intelligently commenting your code](#intelligently-commenting-your-code)
+ [Markdown](#markdown)
+ [ ] [CSS](#css)
+ [ ] [JavaScript](#javascript)
  

##Why?
**Consistency**.    

Every developer likes to do things their own way.    
Even though we have our own idea of what maintainable code looks like, _the important thing isn't how many spaces we indent our code with_ but that **everything is consistent** so new people _don't have to work through personal formatting quirks_ of previous developers and can **focus on the code**.
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


