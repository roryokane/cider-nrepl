[![Build Status](https://travis-ci.org/clojure-emacs/cider-nrepl.png?branch=master)](https://travis-ci.org/clojure-emacs/cider-nrepl)

# CIDER nREPL

A collection of nREPL middleware designed to enhance CIDER.

## Usage

Use the convenient plugin for defaults, either in your project's
`project.clj` file or in the `:user` profile in
`~/.lein/profiles.clj`.

```clojure
:plugins [[cider/cider-nrepl "0.7.0-SNAPSHOT"]]
```

Or (if you know what you're doing) add `cider-nrepl` to your `:dev :dependencies` vector plus specific
middleware to to `:nrepl-middleware` under `:repl-options`.

```clojure
:dependencies [[cider/cider-nrepl "0.7.0-SNAPSHOT"]]
:repl-options {:nrepl-middleware
                 [cider.nrepl.middleware.classpath/wrap-classpath
                  cider.nrepl.middleware.complete/wrap-complete
                  cider.nrepl.middleware.info/wrap-info
                  cider.nrepl.middleware.inspect/wrap-inspect
                  cider.nrepl.middleware.stacktrace/wrap-stacktrace
                  cider.nrepl.middleware.trace/wrap-trace]}
```

Note that you should use a `cider-nrepl` version compatible with your CIDER. Generally, if you're
using CIDER 0.x.y you should be using `cider-nrepl` 0.x.y, if you're using CIDER 0.x.y-SNAPSHOT, you should be
using `cider-nrepl` 0.x.y-SNAPSHOT, etc.


## Supplied nREPL middleware

Middleware        | Op(s)      | Description
------------------|------------|---------------------------------------------------------
`wrap-classpath`  | `classpath` | Java classpath.
`wrap-complete`   | `complete` | Simple completion. Supports both Clojure & ClojureScript.
`wrap-info`       | `info`     | File/line, arglists, docstrings and other metadata for vars.
`wrap-inspect`    |`inspect-(start/refresh/pop/push/reset)` | Inspect a Clojure expression.
`wrap-stacktrace` | `stacktrace` | Cause and stacktrace analysis for exceptions.
`wrap-trace`      | `trace` | Toggle tracing of a given var.

## Contributing

### Discussion

For questions, suggestions and support refer to our [official mailing list](https://groups.google.com/forum/#!forum/cider-emacs)
or the Freenode channel `#clojure-emacs`.
Please, don't report issues there, as this makes them harder to track.

### Issues

Report issues and suggest features and improvements on the
[GitHub issue tracker](https://github.com/clojure-emacs/cider-nrepl/issues). Don't ask
questions on the issue tracker - the mailing list and the IRC channel are the
places for questions.

### Patches

Patches under any form are always welcome! GitHub pull requests are even better! :-)

Before submitting a patch or a pull request make sure all tests are
passing and that your patch is in line with the [contribution
guidelines](CONTRIBUTING.md).

## License

Copyright © 2013-2014 Bozhidar Batsov

Distributed under the Eclipse Public License, the same as Clojure.
