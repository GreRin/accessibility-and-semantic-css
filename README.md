# Presentation-Accessibility-and-semantic-CSS
---
# Transcript of presentation
---
Link to the presentation: [https://grerin.github.io/accessibility-and-semantic-css/](https://grerin.github.io/accessibility-and-semantic-css/)
---
Link to the video: [https://www.youtube.com/watch?v=e6G_kBQe_xM](https://www.youtube.com/watch?v=e6G_kBQe_xM)
---
1. **Introduction in accessibility**

Accessibility is the practice of making your websites usable by as many people as possible. We traditionally think of this as being about people with disabilities, but the practice of making sites accessible also benefits other groups such as those using mobile devices, or those with slow network connections.

You might also think of accessibility as treating everyone the same, and giving them equal opportunities, no matter what their ability or circumstances. In the same way that excluding someone from a physical building because they are in a wheelchair it is also not right to exclude someone from a website because they have a visual impairment. We are all different, but we are all human, and therefore have the same human rights.

Building accessible sites benefit everyone:

*	Semantic HTML, which improves accessibility, also improves SEO, making your site more findable.

*	Caring about accessibility demonstrates good ethics and morals, which improves your public image.

*	Other good practices that improve accessibility also make your site more usable by other groups, such as mobile phone users or those on low network speed. In fact, everyone can benefit from many such improvements.

*	Did we mention it is also the law in some places?

For a start, the W3C has published a large and very detailed document that includes very precise, technology-agnostic criteria for accessibility conformance. These are called the Web Content Accessibility Guidelines (WCAG), and they are not a short read by any means. The criteria are split up into four main categories, which specify how implementations can be made perceivable, operable, understandable, and robust. There is no need to learn WCAG off by heart — be aware of the major areas of concern, and use a variety of techniques and tools to highlight any areas that don't conform to the WCAG criteria. Different progressive country have specific legislation governing the need for websites serving their population to be accessible. For example such documents are in Australia, UK, Germany, the US.

---
2.	**Introduction in HTML**

As you learn more about HTML — read more resources, look at more examples, etc. — you'll keep seeing a common theme: the importance of using semantic HTML (sometimes called POSH, or Plain Old Semantic HTML). This means using the correct HTML elements for their intended purpose as much as possible.
You might wonder why this is so important. After all, you can use a combination of CSS and JavaScript to make just about any HTML element behave in whatever way you want. For example, a control button to play a video on your site could be marked up like this:div. But as you'll see in greater detail later on, it makes sense to use the correct element for the job:button. 
Not only do HTML <button>s have some suitable styling applied by default (which you will probably want to override), they also have built-in keyboard accessibility — users can navigate from button to button using the Tab key, and activated using Return or Enter.
Semantic HTML doesn't take any longer to write than non-semantic (bad) markup if you do it consistently from the start of your project. Even better, semantic markup has other benefits beyond accessibility:
  
1.	Easier to develop with — as mentioned above, you get some functionality for free, plus it is arguably easier to understand.
2.	Better on mobile — semantic HTML is arguably lighter in file size than non-semantic spaghetti code, and easier to make responsive.
3.	Good for SEO — search engines give more importance to keywords inside headings, links, etc., than keywords included in non-semantic <div>s, etc., so your documents will be more findable by customers.
  
---
3. **Good semantic**
  
We've already talked about the importance of good semantics, and why we should use the right HTML element for the job. This cannot be ignored, as it is one of the main places that accessibility is badly broken if not handled properly.
Text content
People sometimes write headings, paragraphs, etc. using presentational HTML and line breaks, something like the following:
One of the best accessibility aids a screenreader user can have is a good content structure with headings, paragraphs, lists, etc. A good semantic example might look something like the following
Here we can see right TABs, clear structure.

3.1 **DOM structure**

Page layouts

In the bad old days, people used to create page layouts using HTML tables — using different table cells to contain the header, footer, side bar, main content column, etc. This is not a good idea because a screenreader will likely give out confusing readouts, especially if the layout is complex and has many nested tables.
Table layouts are a relic of the past.
In present we build DOM by use tegs header, nav, main, article, aside, footer.
The link below the example provide us all the HTML elements, which are created using tags. They are grouped by function to help you find what you have in mind easily. An alphabetical list of all elements is provided in the sidebar on every element's page as well as this one.

3.2 **UI controlsSection**

3.2.1 By UI controls, we mean the main parts of web documents that users interact with — most commonly buttons, links, and form controls. One key aspect to the accessibility of UI controls is that by default, browsers allow them to be manipulated by the keyboard. By pressing tab focus start to move through the different focusable elements; the focused elements are given a highlighted default style in every browser (it differs slightly between different browsers) so that you can tell what element is focused.

3.2.2 Building keyboard accessibility back in

If we give teg <div> attribute tabindex="0" <div> get the ability to be focused (including via tab). There are two other options for tabindex:
  
*	tabindex="0" — as indicated above, this value allows elements that are not normally tabbable to become tabbable. This is the most useful value of tabindex.
*	tabindex="-1" — this allows not normally tabbable elements to receive focus programmatically, e.g. via JavaScript, or as the target of links.

3.2.3 Meaningful text labels

We need to be sure your labels make sense out of context, read on their own, as well as in the context of the paragraph they are in. For example, the following shows an example of good link text:
Form labels are also important, for giving you a clue what you need to enter into each form input. The following seems like a reasonable enough example:
The following is a much better example:

3.2.4 HTML table advanced features and accessibility

You can give your table a caption by putting it inside a <caption> element and nesting that inside the table element. You should put it just below the opening table tag.
As your tables get a bit more complex in structure, it is useful to give them more structural definition. One clear way to do this is by using <thead>, <tfoot>, and <tbody>, which allow you to mark up a header, footer, and body section for the table.
These elements don't make the table any more accessible to screenreader users, and don't result in any visual enhancement on their own. They are however very useful for styling and layout — acting as useful hooks for adding CSS to your table.
  
3.2.5 Text alternativesSection

The first image, when viewed by a screen reader, doesn't really offer the user much help — VoiceOver for example reads out "/dinosaur.png, image". It reads out the filename to try to provide some help. In this example the user will at least know it is a dinosaur of some kind, but often files may be uploaded with machine generated file names and these file names would likely provide no context to the image's content.
Note: This is why you should never include text content inside an image — screen readers simply can't access it. There are other disadvantages too — you can't select it and copy/paste it. Just don't do it!
When a screen reader encounters the second image, it reads out the full alt attribute.
This highlights the importance of not only using meaningful file names in case so-called alt text is not available, but also making sure that alt text is provided in alt attributes wherever possible. Note that the contents of the alt attribute should always provide a direct representation of the image and what it conveys visually. Any personal knowledge or extra description shouldn't be included here, as it is not useful for people who have not come across the image before.
One thing to consider is whether your images have meaning inside your content, or whether they are purely for visual decoration, so have no meaning. If they are decorational, it is better to write an empty text as a value for alt attribute or to just include them in the page as CSS background images. If you do want to provide extra contextual information, you should put it in the text surrounding the image, or inside a title attribute, as shown above. In this case, most screenreaders will read out the alt text, the title attribute, and the filename. In addition, browsers display title text as tooltips when moused over.
Let's have another quick look at the fourth method:
In this case, we are not using the alt attribute at all — instead, we have presented our description of the image as a regular text paragraph, given it an id, and then used the aria-labelledby attribute to refer to that id, which causes screenreaders to use that paragraph as the alt text/label for that image. This is especially useful if you want to use the same text as a label for multiple images — something that isn't possible with alt.
Note: aria-labelledby is part of the WAI-ARIA spec, which allows developers to add in extra semantics to their markup to improve screenreader accessibility where needed.

3.2.6 HTML5 includes two new elements — figure and figcaption — which are supposed to associate a figure of some kind (it could be anything, not necessarily an image) with a figure caption:
Unfortunately, most screenreaders don't seem to associate figure captions with their figures yet, but the element structure is useful for CSS styling, plus it provides a way to place a description of the image next to it in the source.

3.2.7 Empty alt attributesSection

There may be times where an image is included in a page's design, but its primary purpose is for visual decoration. You'll notice in the code example above that the image's alt attribute is empty — this is to make screen readers recognize the image, but not attempt to describe the image (instead they'd just say "image", or similar). 
The reason to use an empty alt instead of not including it is because many screen readers announce the whole image URL if no alt is provided.  In the above example, the image is acting as a visual decoration to the heading it's associated with.
Note: if possible you should use CSS to display images that are only decorative.

3.2.8 New tags in HTML5

As I talked before there are new tags in HTML5 which are help developers with semantics, connectivity, multimedia, 2D/3D graphics, effects and ect.

---
4. **CSS semantic**

4.1 "Standard" text content structure

The rule of thumb is that you can update the styling of a page feature to fit in your design, but don't change it so much that it no longer looks or behaves as expected. The following sections summarize the main HTML features to consider.

4.2 Emphasised text

You will however rarely need to style emphasis elements in any significant way. The standard conventions of bold and italic text are very recognisable, and changing the style can cause confusion.

4.3 Abbreviations

The recognised styling convention for abbreviations is a dotted underline, and it is unwise to significantly deviate from this.

4.4 Links

The standard link conventions are underlined and a different color (default: blue) in their standard state, another color variation when the link has previously been visited (default: purple), and yet another color when the link is activated (default: red). In addition, the mouse pointer changes to a pointer icon when links are moused over, and the link receives a highlight when focused (e.g. via tabbing) or activated.

4.5 Form elements

Most of the CSS you'll write for forms will be for sizing the elements, lining up labels and inputs, and getting them looking neat and tidy.

4.6 Tables

When choosing a color scheme for your website, make sure that the text color contrasts well with the background color. Your design might look cool, but it is no good if people with visual impairments like color blindness can't read your content.

---
5. **END**
This presentation should have given you a useful high-level overview of accessibility, shown you why it's important, and looked at how you can fit it into your workflow. You should now also have a thirst to learn about the implementation details that can make sites accessible.
