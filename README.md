# smartdown/impress

Integrate Smartdown with the [impress.js](https://github.com/impress/impress.js) presentation library. The basic idea is that a set of Smartdown docs can be assembled into a presentation. Impress.js slide attributes can be specified in `index.html` or in the frontmatter of the Smartdown documents.


## What's the deal with Manifest.md?

The idea is to move as much of the specification of the ordering of content and the content itself from the realm of `index.html` into the more comfortable Markdown format, including Markdown frontmatter. So basically, an impress.js slideshow that would ordinarily be specified in an `index.html` can instead refer to a `Manifest.md` file by adding a slide definition like the following to `index.html`:

```html
  <div
    id="manifest"
    class="step slide smartdown manifest"
    src="./Manifest.md"
  >
  </div>
```

The contents of Manifest.md will typically be only Markdown frontmatter (YAML). The important part is the `files:` section, which lists the Markdown (or Smartdown) files to be rendered as slides. The `exampleBasic/Manifest.md` file looks like this:

```markdown
---
impress:
  data-x: 1000
  data-y: 1000
  files:
    - ./Overview.md
    - ./Home.md
    - ./Multi.md
---
```

## What's the deal with Multislides?

Smartdown supports a feature called [Multicards](https://smartdown.github.io/smartdown/#Multicards) which enables an author to put the text for multiple Smartdown cards in a single file. For example, the following Smartdown text will be displayed as three separate cards in an ordinary Smartdown viewer. However, smartdown/impress will create three separate slides.

```markdown
 Apple
 ---

### All about Apples

Apples are sometimes red.

 Cherry
 ---

### All about Cherries

Cherries are sometimes red.

 Book
 ---

### All about Books

Book are sometimes read.

```


# Versions

**0.0.1** - Initial attempt at integrating Smartdown with Impress.js, including three examples. Requires Smartdown 0.0.118+. Another contribution here is the use of Manifest.md files and their frontmatter to help authors avoid HTML. Allow Smartdown tunnel syntax to be used to navigate within a presentation. Examples include a Smartdown Gallery example that demonstrates and stress-tests some Smartdown features. The exampleBasic/ example provide a pages.html to view slides one at a time without Impress.js.
**0.0.2** - Uses latest impress.js build.



