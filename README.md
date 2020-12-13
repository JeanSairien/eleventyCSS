# eleventyCOnfig 
**allow add custom css js fonts files into eleventy**

for add an new type of files / folders for acceptation of eleventy follow this exemple: 

```
module.exports = function(eleventyConfig) {
  eleventyConfig.addPassthroughCopy('css')
  eleventyConfig.addPassthroughCopy('fonts')
  eleventyConfig.addPassthroughCopy('js')
  eleventyConfig.addPassthroughCopy('what-u-want-like-img')
  return {
    passthroughFileCopy: true
  }
}
```

_thanks to **Michael Lee** for the tips_

[the tips come from this site](https://michaelsoolee.com/add-css-11ty/)


**For allow to write markdown code**
```
module.exports = function(eleventyConfig) {
  let markdownIt = require("markdown-it");
  let markdownItEmoji = require("markdown-it-emoji");
  let options = {
    html: true
  };
  let markdownLib = markdownIt(options).use(markdownItEmoji);
  
  eleventyConfig.setLibrary("md", markdownLib);
};

```

_From the official doc: [read the doc...](https://www.11ty.dev/docs/languages/markdown/)
