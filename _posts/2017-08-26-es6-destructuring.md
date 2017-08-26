---
published: false
---
## ES6: Destructuring

This morning, I sat down with my regular weekend breakfast sandwich and coffee and wanted to learn a little bit of ES6. I've decided the way I want to do it is by learning about individual features so I can use them in my code, so I went to YouTube to watch a clip while eating. I found an excellent video by MPJME: [Destructuring: What, Why and How - Part 1 of ES6 JavaScript Features](https://www.youtube.com/watch?v=PB_d3uBkQPs).

### Destructuring in my own words
Destructuring is a way of taking values from an object to work with them directly instead of having to cast them to variables individually with repetitive dot syntax. As a nice bonus, the syntax supports casting default values for the destructured properties in the object you're working with.

### Example
```js
var options = {
	"autoplay": true,
    "title": "We Never Left Tibet",
	"id": "f0f8tOPUuuGk",
	"author": "Gavin Andressen",
};
```

This part up here will stay the same. That is our `options` object, it's lovely, and it's not going anywhere. What we're going to do is play with how we work with those options to do stuff.

```js
(function (options) {
	console.log("I'd like to show you a video, titled \"" + options.title + "\" by " + options.author + ".");
})(options);
```

This could be written out more ~~simply~~ expressively as:

```js
(function ({ title, author }) {
	console.log("I'd like to show you a video, titled \"" + title + "\" by " + author + ".");
})(options);
```

This syntax takes a gamble that the reader doesn't know how to read ES6. That reader will hopefully go look up the syntax and somehow discover some wonderful documentation on destructuring. I wonder if it'd be nicer to write it out like this:

```js
(function ({ title, author }) { // ES6 technique: Destructuring
	console.log("I'd like to show you a video, titled \"" + title + "\" by " + author + ".");
})(options);
```

Better use of the technique (using defaults):

```js
(function ({ title = "Untitled", author = "an unknown author" }) { // ES6 technique: Destructuring
	console.log("I'd like to show you a video, titled \"" + title + "\" by " + author + ".");
})(options);
```

I kinda want to use some ES6 string magic here but not badly enough to look up the syntax and use it. I'm trying to focus on destructuring... and it's really nice out. I should go outside.