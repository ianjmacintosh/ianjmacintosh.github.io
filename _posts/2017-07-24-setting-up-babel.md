---
published: true
---
Following the steps listed in Lindley's article about [Learning ES2015](http://developer.telerik.com/featured/six-steps-for-approaching-the-next-javascript/), I started by skipping over step 1 -- I _think_ I know enough ES5 to get started with learning ES2015. Then comes setting up a local ES6 development environment. My first thought is "Babel" and that this article seems a little out of date if it's even mentioning Traceur and JSPM. So sure enough I go to Babel's site, run the npm install command, and am immediately faced with the question of whether or not I should set up some kind of task runner to watch and transpile Babel as I write it. Seems like a typical problem I run into learning JS stuff today -- one thing leads immediately into another, and before I know it I'm trying to think of a good directory structure and tooling setup for easily transpiling. Options now seem to be Grunt, gulp, npm run-scripts, and a [taskfile](https://hackernoon.com/introducing-the-taskfile-5ddfe7ed83bd) format that sounded really appealing.

I'm crunched on time and have to go do other stuff, but I wanted to make sure to get a quick post out of the way and make a little bit of headway on my learning thing.

```bash
Ians-MacBook-Pro:learning-es2015 ian$ npm install --save-dev babel-cli babel-preset-env
\
> fsevents@1.1.2 install /Users/ian/projects/personal/learning-es2015/node_modules/babel-cli/node_modules/chokidar/node_modules/fsevents
> node install

[fsevents] Success: "/Users/ian/projects/personal/learning-es2015/node_modules/babel-cli/node_modules/chokidar/node_modules/fsevents/lib/binding/Release/node-v46-darwin-x64/fse.node" already installed
Pass --update-binary to reinstall or --build-from-source to recompile
babel-preset-env@1.6.0 node_modules/babel-preset-env
├── babel-plugin-syntax-trailing-function-commas@6.22.0
├── semver@5.4.1
├── invariant@2.2.2 (loose-envify@1.3.1)
├── browserslist@2.2.2 (electron-to-chromium@1.3.16, caniuse-lite@1.0.30000704)
├── babel-plugin-transform-es2015-block-scoped-functions@6.22.0 (babel-runtime@6.23.0)
├── babel-plugin-transform-es2015-spread@6.22.0 (babel-runtime@6.23.0)
├── babel-plugin-check-es2015-constants@6.22.0 (babel-runtime@6.23.0)
├── babel-plugin-transform-es2015-literals@6.22.0 (babel-runtime@6.23.0)
├── babel-plugin-transform-es2015-arrow-functions@6.22.0 (babel-runtime@6.23.0)
├── babel-plugin-transform-es2015-template-literals@6.22.0 (babel-runtime@6.23.0)
├── babel-plugin-transform-es2015-for-of@6.23.0 (babel-runtime@6.23.0)
├── babel-plugin-transform-es2015-destructuring@6.23.0 (babel-runtime@6.23.0)
├── babel-plugin-transform-es2015-typeof-symbol@6.23.0 (babel-runtime@6.23.0)
├── babel-plugin-transform-es2015-modules-systemjs@6.24.1 (babel-template@6.25.0, babel-helper-hoist-variables@6.24.1, babel-runtime@6.23.0)
├── babel-plugin-transform-es2015-modules-amd@6.24.1 (babel-template@6.25.0, babel-runtime@6.23.0)
├── babel-plugin-transform-es2015-object-super@6.24.1 (babel-helper-replace-supers@6.24.1, babel-runtime@6.23.0)
├── babel-plugin-transform-es2015-modules-umd@6.24.1 (babel-template@6.25.0, babel-runtime@6.23.0)
├── babel-plugin-transform-es2015-computed-properties@6.24.1 (babel-template@6.25.0, babel-runtime@6.23.0)
├── babel-plugin-transform-es2015-unicode-regex@6.24.1 (regexpu-core@2.0.0, babel-helper-regex@6.24.1, babel-runtime@6.23.0)
├── babel-plugin-transform-es2015-shorthand-properties@6.24.1 (babel-types@6.25.0, babel-runtime@6.23.0)
├── babel-plugin-transform-es2015-duplicate-keys@6.24.1 (babel-types@6.25.0, babel-runtime@6.23.0)
├── babel-plugin-transform-es2015-modules-commonjs@6.24.1 (babel-plugin-transform-strict-mode@6.24.1, babel-template@6.25.0, babel-types@6.25.0, babel-runtime@6.23.0)
├── babel-plugin-transform-es2015-sticky-regex@6.24.1 (babel-helper-regex@6.24.1, babel-types@6.25.0, babel-runtime@6.23.0)
├── babel-plugin-transform-es2015-function-name@6.24.1 (babel-types@6.25.0, babel-helper-function-name@6.24.1, babel-runtime@6.23.0)
├── babel-plugin-transform-es2015-block-scoping@6.24.1 (babel-template@6.25.0, babel-types@6.25.0, babel-traverse@6.25.0, lodash@4.17.4, babel-runtime@6.23.0)
├── babel-plugin-transform-exponentiation-operator@6.24.1 (babel-plugin-syntax-exponentiation-operator@6.13.0, babel-helper-builder-binary-assignment-operator-visitor@6.24.1, babel-runtime@6.23.0)
├── babel-plugin-transform-async-to-generator@6.24.1 (babel-plugin-syntax-async-functions@6.13.0, babel-helper-remap-async-to-generator@6.24.1, babel-runtime@6.23.0)
├── babel-plugin-transform-es2015-parameters@6.24.1 (babel-helper-get-function-arity@6.24.1, babel-helper-call-delegate@6.24.1, babel-template@6.25.0, babel-types@6.25.0, babel-traverse@6.25.0, babel-runtime@6.23.0)
├── babel-plugin-transform-es2015-classes@6.24.1 (babel-helper-replace-supers@6.24.1, babel-messages@6.23.0, babel-helper-optimise-call-expression@6.24.1, babel-helper-function-name@6.24.1, babel-helper-define-map@6.24.1, babel-template@6.25.0, babel-types@6.25.0, babel-traverse@6.25.0, babel-runtime@6.23.0)
└── babel-plugin-transform-regenerator@6.24.1 (regenerator-transform@0.9.11)

babel-cli@6.24.1 node_modules/babel-cli
├── slash@1.0.0
├── path-is-absolute@1.0.1
├── fs-readdir-recursive@1.0.0
├── commander@2.11.0
├── convert-source-map@1.5.0
├── v8flags@2.1.1 (user-home@1.1.1)
├── source-map@0.5.6
├── output-file-sync@1.1.2 (object-assign@4.1.1, graceful-fs@4.1.11, mkdirp@0.5.1)
├── glob@7.1.2 (inherits@2.0.3, fs.realpath@1.0.0, inflight@1.0.6, once@1.4.0, minimatch@3.0.4)
├── babel-core@6.25.0 (babel-messages@6.23.0, babel-template@6.25.0, private@0.1.7, babel-helpers@6.24.1, json5@0.5.1, babylon@6.17.4, minimatch@3.0.4, babel-types@6.25.0, debug@2.6.8, babel-code-frame@6.22.0, babel-traverse@6.25.0, babel-generator@6.25.0)
├── lodash@4.17.4
├── babel-register@6.24.1 (source-map-support@0.4.15, home-or-tmp@2.0.0, mkdirp@0.5.1, core-js@2.4.1)
├── babel-polyfill@6.23.0 (regenerator-runtime@0.10.5, core-js@2.4.1)
├── babel-runtime@6.23.0 (regenerator-runtime@0.10.5, core-js@2.4.1)
└── chokidar@1.7.0 (inherits@2.0.3, async-each@1.0.1, glob-parent@2.0.0, is-glob@2.0.1, is-binary-path@1.0.1, readdirp@2.1.0, anymatch@1.3.0, fsevents@1.1.2)
Ians-MacBook-Pro:learning-es2015 ian$ 
```
