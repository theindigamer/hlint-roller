# hlint-roller: Lint you a Haskell for neat code!

> Only a fool learns from his own mistakes. The wise man learns from the
> mistakes of others. And the generous wise person puts their mistakes into an
> open source lint repository.
>
> &mdash;<cite>Otto von Bismarck</cite>

Hlint-roller is a community-maintained collection of [lints][lint-wikipedia]
using [Hlint][hlint].

[lint-wikipedia]: https://en.wikipedia.org/wiki/Lint_%28software%29
[hlint]: https://github.com/ndmitchell/hlint

## Setting up

Add this repository as a submodule:

```
git submodule add https://github.com/theindigamer/hlint-roller.git
git submodule update --init
```

In the usual case, you will only want to import some of the hints
(located under `data`) from this package. Say you want to use
`data/foo.yaml`. Then you should supply an additional flag
`--hint=hlint-roller/data/foo.yaml` to Hlint. For more details, consult
`hlint --help`.

## Contributing

### Contributing to the discussion

Even if you don't have any hints to contribute, please feel free to submit
questions/feature requests. For example, if you are getting a warning whose
explanation doesn't make sense to you, make a new issue describing the problem
so that someone else can add a better explanation.

### Contributing Hints

Shot yourself in the foot by not reading a package's documentation carefully?
Awesome! Now's the chance to make a lint before the wound heals and you've
forgotten about it, only to repeat the mistake two weeks later.

As written earlier, hints are located inside the `data` folder. If you're unsure
about the semantics of hints, you might find the answers to the following two
questions helpful:

1. [Why do I sometimes get a "Note" with my hint?][note-semantics]
2. [What is the difference between error/warning/suggestion?][error-warning]

[note-semantics]: https://github.com/ndmitchell/hlint#why-do-i-sometimes-get-a-note-with-my-hint
[error-warning]: https://github.com/ndmitchell/hlint#what-is-the-difference-between-errorwarningsuggestion

If you're unfamiliar with the syntax for writing hints, you have a few options:

1. Look at the already existing hint files here or in the [Hlint][hlint] repo.
2. Be unsure/confused and give up.
3. Ask a question on the issue tracker :smile:.

Don't take the second option!

## Possible issues

### Warning X should be off by default.

The extent of linting is a matter of personal taste. If we keep warnings on by
default, some users might get annoyed and consequently go in and
[ignore them][ignore-hints] turn them off on a granular basis, which is okay.
However if they are kept off by default, then the user is less likely to go in
and flip some switches on manually, which is not ideal.

In that sense, the warnings here are just like any other Haskell module; if
you're doing a unqualified import, you may need a `hiding` clause to make it
work with your code.

This policy doesn't apply to hints, which may be kept off by default.

[ignore-hints]: https://github.com/ndmitchell/hlint#ignoring-hints
