# Continuous Integration

_This repository is part of the **Designing Javascript Applications: A Build First Approach** book's code samples_, the full original for the code samples [can be found here](https://github.com/bevacqua/buildfirst). You can [learn more about the book itself here](http://bevacqua.io/buildfirst).

This tutorial is part of the [code samples](https://github.com/bevacqua/buildfirst/tree/master/ch04) accompanying the book in _Chapter 4_, about the release flow, deployments, and hosted application monitoring.

### Introduction

Setting up CI is _almost trivial_ in this day and age. In this repository we'll learn how to get ourselves up and running with Travis-CI. The first thing we'll need to do, is create a `.travis.yml` file at the project root. In this example, the file looks like:

```yml
language: node_js

node_js:
  - "0.10"

before_install:
  - npm install -g grunt-cli

script:
  - grunt ci --verbose --stack
```

There is even a linter for `.travis.yml` files, which you can use on [lint.travis-ci.org](http://lint.travis-ci.org/), to verify the integrity of this file. The format is pretty self-descriptive, and we've covered the basics on the book.

All there's left, then, is to set up a `ci` task for Grunt. The task just runs `jshint` for this example, which isn't very useful because it will run the same in our development environments. We should configure the `ci` task to run unit, and integration tests as we'll examine in future chapters.

### Configuring It

You'll probably want to try this example out yourself. First thing you'll need is a `git` repository that's configured to run on Travis. That's easy, you could just fork this one.

```shell
hub fork buildfirst/ci-by-example
```

Awesome! Now I need to push so I can fork and try it by myself.

For more information you can visit [the guide provided by Travis-CI](http://about.travis-ci.org/docs/user/languages/javascript-with-nodejs/).
