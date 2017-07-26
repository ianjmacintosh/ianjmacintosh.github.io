---
published: true
---
Now I've actually set up Babel for my project, which takes a few more steps than just running
```bash
$ npm install --save-dev babel-cli babel-preset-env
```

The other steps weren't a ton, but they were there and worth taking a step back to acknowledge that some of the things people used to doing dev work might ignore. People learning how to get started for their first time might get stuck easily. I had to first load up my editor (VS Code) and get it to load up my directory, I had to create a package.json file in that directory (which I copied from the Babel instructions), create a `src` and `lib` directory (although I think I prefer `src` and `dist` but I'm trying to not get stuck on stupid details), create a `.babelrc` file, create a test JS file (while remembering some simple ES2015 syntax to test with), and run `npm run build` from the shell to verify `package.json` is able to pick up babel in the `./node_modules` directory without needing to install it globally, then review the file got compiled properly.

Take a second to acknowledge that all of these steps seem so trivial that I wouldn't normally even mention them, I'd say something incredibly dismissive of them like "Well yeah of course you need to do that," as if I were shrugging off the fact that you have to be able to get into the car first in order to drive it. This seems obvious unless you're dealing with someone who either has never driven a car before, or is locked out of their car. Take a moment to acknowledge all the stupid little steps that as developers we don't even bat an eye at and just _assume_ everyone already knows how to do. Thankfully my experience today has gotten to a point where I'm so used to this kind of thing that it's all auto-pilot for me, and I can get away with it because most projects follow a similar set of standards.

So this is neat, now I've gotten through Step 2. My next step is going to be to read some articles and then type up short critiques of them and describe what I learned. The articles are all probably a little outdated in the sense that there may be better available now, but I may as well start with these. I'm also going to go over Rauschmeyer's listing and brief description of the core [ES6 features](http://exploringjs.com/es6/ch_core-features.html)

Articles to read and critique:
* [https://github.com/lukehoban/es6features](https://github.com/lukehoban/es6features)
* [http://www.2ality.com/2014/08/es6-today.html](http://www.2ality.com/2014/08/es6-today.html)
* [http://tagtree.tv/courses/expert-es6](http://tagtree.tv/courses/expert-es6)
* [http://learnharmony.org/](http://learnharmony.org/)
* [http://es6-features.org/](http://es6-features.org/)
