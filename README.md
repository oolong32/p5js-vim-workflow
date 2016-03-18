# Working with p5.js in Vim (from the command-line)

I find the p5.js editor great, it’s just that I have gotten so used to editing text in Vim, that I find it awkward to work in text editors that rely on the use of a mouse or a touchpad. So here’s what I did.

##Browser-Sync

In order not only to run your p5.js sketches, but also to autoupdate them when saving any changes, you can use [browser-sync](https://browsersync.io/).

### Installation

```
$ npm install -g browser-sync
```

### Configuration

You can add an alias to your .zshrc (or .bashrc or .bash_profile).

``` 
# alias for browser-sync (with p5.js)
alias bs='browser-sync start --server --files "*.js, *.html, *.css"'
``` 

Now you can start browser-sync in the p5.js project folder by typing ‘bs’. Whenever you save a .js, .html, or a .css file, a browser window will open or, when already open, refresh (don’t forget to source the file or to restart your shell in order to make it work).

To turn browser-sync off, you hit Ctrl-c.

## Vim

Vim is hard to set-up properly on the command-line. You can try installing it with [homebrew](http://brew.sh) or use [macVim](http://macvim-dev.github.io/macvim/) instead. Or not use it at all.

### Syntax-Highlighting

I use the [vim-javascript](https://github.com/pangloss/vim-javascript) bundle for syntax highlighting. p5.js is not really supported, but it’s ok.

## Set up a new p5.js project

In the p5.js editor, I saved an new p5.js project under the name empty. When starting to work on a new p5.js sketch, I make a new instance of this folder. And yes, I am fully aware of the fact that this could be done more elegantly.

```
~/p5js/ $ cp -r empty new_p5.js_project
~/p5js/ $ cd new_p5.js_project
~/p5js/ $ vim sketch.js
```

You need to open a second shell in order to run browser-sync, of course.

Of course all of this could be simplified by means of shell script etc. Let me know of any possible improvements you can think of.
