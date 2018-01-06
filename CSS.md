* What's the difference between "resetting" and "normalizing" CSS? Which would you choose, and why?
->  Resetting: Remove all the native styles provided by browsers
    Normalizing: Make the browser styles consistent

    Normalize.css preserves useful defaults rather than "unstyling" everything.
    Normalize.css corrects some common bugs that are out of scope for reset.css.
    Normalize.css doesn't clutter your dev tools.
    Normalize.css has better documentation.

* Describe Floats and how they work.
->  Float is a CSS positioning property. Floated elements remain a part of the flow of the page, and will affect the positioning of other           elements. If a parent element contains nothing but floated elements, its height will be collapsed to nothing. It can be fixed by clearing       the float after the floated elements in the container but before the close of the container. The .clearfix hack uses a clever CSS pseudo        selector (:after) to clear floats.
    Alternatively, give overflow: auto or overflow: hidden property to the parent element which will establish a new block formatting context inside the children and it will expand to contain its children.

* Describe z-index and how stacking context is formed.
->  The z-index property in CSS controls the vertical stacking order of elements that overlap. z-index only effects elements that have a            position value which is not static.
    A stacking context is an element that contains a set of layers. Within a local stacking context, the z-index values of its children are set relative to that element rather than to the document root.
    A handful of CSS properties trigger a new stacking context, such as opacity less than 1, filter that is not none, and transform that is notnone`.

* Describe BFC(Block Formatting Context) and how it works.
->  A block formatting context is a part of a visual CSS rendering of a Web page. It is the region in which the layout of block boxes occurs        and in which floats interact with other elements.
    A block formatting context is created by one of the following:

        the root element or something that contains it.
        floats (elements where float is not none).
        absolutely positioned elements.
        inline-blocks.
        block elements where overflow has a value other than visible.

    A block formatting context contains everything inside of the element creating it.

* What are the various clearing techniques and which is appropriate for what context?
->  Empty div method - <div style="clear:both;"></div>.
    Clearfix method — Refer to the .clearfix class above.
    overflow: auto or overflow: hidden method - Parent will establish a new block formatting context and expand to contains its floated children. A utility .clearfix class can be created and use them in places where needed.

* Explain CSS sprites, and how you would implement them on a page or site.
->  CSS sprites combine multiple images into one single larger image. It is commonly used technique for icons.
        1. Use a sprite generator that packs multiple images into one and generate the appropriate CSS for it.
        2. Each image would have a corresponding CSS class with background-image, background-position and background-size properties defined.
        3. To use that image, add the corresponding class to your element.

* How would you approach fixing browser-specific styling issues?
->  After identifying the issue and the offending browser, use a separate style sheet that only loads when that specific browser is being used.     This technique requires server-side rendering though.
    Use libraries like Bootstrap that already handles these styling issues for you.
    Use autoprefixer to automatically add vendor prefixes to your code.
    Use Reset CSS or Normalize.css.

* How do you serve your pages for feature-constrained browsers?
->  Graceful degradation — The practice of building an application for modern browsers while ensuring it remains functional in older browsers.
    Progressive enhancement — The practice of building an application for a base level of user experience, but adding functional enhancements when a browser supports it.
    Use caniuse.com to check for feature support.

* Have you ever used a grid system, and if so, what do you prefer?
* Have you used or implemented media queries or mobile specific layouts/CSS?
* Are you familiar with styling SVG?

* What are some of the "gotchas" for writing efficient CSS?
-> Firstly, understand that browsers match selectors from rightmost (key selector) to left. Browsers filter out elements in the DOM according       to the key selector, and traverse up its parent elements to determine matches. The shorter the length of the selector chain, the faster the     browser can determine if that element matches the selector. Hence avoid key selectors that are tag and universal selectors. They match a        large numbers of elements and browsers will have to do more work in determining if the parents do match.

    BEM (Block Element Modifier) methodology recommends that everything has a single class, and, where you need hierarchy, that gets baked into the name of the class as well, this naturally makes the selector efficient and easy to override.

    Be aware of which CSS properties trigger reflow, repaint and compositing. Avoid writing styles that change the layout (trigger reflow) where possible.  

* What are the advantages/disadvantages of using CSS preprocessors?
->  CSS is made more maintainable.
    Easy to write nested selectors.
    Variables for consistent theming. Can share theme files across different projects.
    Mixins to generate repeated CSS.
    Splitting your code into multiple files. CSS files can be split up too but doing so will require a HTTP request to download each CSS file.

    Requires tools for preprocessing. Re-compilation time can be slow.

* Describe pseudo-elements and discuss what they are used for.
->  