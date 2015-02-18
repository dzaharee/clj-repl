# clj-repl.el

This library exists for people who want to use Clojure and CLJS in Emacs with
inferior-lisp instead of nrepl, cider, etc. The purpose is to be as minimal as
possible, while still getting these benefits:

1. an in-editor REPL
1. clojure syntax highlighting
1. paredit

Drop ```clj-repl.el``` into your Emacs configuration to have these handy functions available:

1. ```clj-repl```: Starts an ```*inferior-lisp*``` buffer by executing
   ```clojure-repl``` (which must be in your ```$PATH```).
1. ```cljs-repl```: Starts an ```*inferior-lisp*``` buffer by executing ```lein
   figwheel```, which requires proper configuration in your project.
 1. ```lein new figwheel``` is a great way to get Figwheel up and running quickly.

### Dependencies

1. You must be using Emacs.
1. [leiningen](http://leiningen.org)
1. [lein-figwheel](https://github.com/bhauman/lein-figwheel)

## Installation

1. Make sure ```clj-repl.el``` is loaded into your Emacs configuration. For example, if you place this repository in your home directory you can simply add this to your Emacs init file (probably ```~/.emacs.d/init.el```): ```(load-library "~/clj-repl/clj-repl")```.
1. Either
 1. Place the ```clojure-repl``` shell script in your ```$PATH```
  1. Example: ```cp clojure-repl /usr/local/bin/```
 1. Or set ```clj-repl-helper-script``` in your Emacs configuration to the name of the program you wish to run to start your Clojure REPL.
  1. Example: ```(setq clj-repl-helper-script "my-other-program arg1 arg2")```

## Usage

1. Clojure
 1. Create a ```.classpath``` file in your project directory, so that
    ```clojure-repl``` can find it. ```lein classpath > .classpath``` should
    work well for this.
 1. ```M-x clj-repl```
1. Clojurescript
 1. Just make sure figwheel is set up, and then ```M-x cljs-repl```

## TODO

1. Make fewer assumptions and allow more configurability.
1. Refactor. I'm just learning elisp and getting things working, so many
   improvements are possible.

## License

Copyright © 2015 Dave Zaharee
Copyright © 2015 Matt Oquist

Distributed under the Eclipse Public License either version 1.0 or (at
your option) any later version.
