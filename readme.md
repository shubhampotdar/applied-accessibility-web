# Applied Accessibility for web design:

__"Accessibility"__ generally means having web content and a user interface that can be understood, navigated, and interacted with by a broad audience. This includes people with visual, auditory, mobility, or cognitive disabilities. Websites should be open and accessible to everyone, regardless of a user's abilities or resources. Some users rely on assistive technology such as a screen reader or voice recognition software. Other users may be able to navigate through a site only using a keyboard. Keeping the needs of various users in mind when developing your project can go a long way towards creating an open web. Here are three general ideas to be kept in mind to add accessibility to your pages:

* Have well-organized code that uses __appropriate markup__

* Ensure __text alternatives__ exist for non-text and visual content

* Create an easily-navigated page that's __keyboard-friendly__

Having accessible web content is an ongoing challenge. A great resource for your projects going forward is the [W3 Consortium's Web Content Accessibility Guidelines (WCAG)](https://www.w3.org/WAI/standards-guidelines/wcag/). They set the international standard for accessibility and provide a number of criteria you can use to check your work.


### Below are a few guidelines that can be followed to add accessibility to web design:



* People with visual impairments rely on screen readers to convert web content to an audio interface. They won't get information if it's only presented visually. For images, screen readers can access the __alt__ attribute and read its contents to deliver key information.Good __alt__ text provides the reader a brief description of the image. You should always include an __alt__ attribute on your image. Per HTML5 specification, this is now considered mandatory.

	In situations when an image is already explained with text content (like captions), or does not add meaning to 	a page, the __img__ still needs an __alt__ attribute, but it can be set to an empty string.
</br></br>
* Screen readers can be set to read only the headings on a page so the user gets a summary. This means it is important for the heading tags in your markup to have semantic meaning and relate to each other, not be picked merely for their size values.

	__Semantic meaning__ means that the tag you use around content indicates the type of information it contains.

	Each page should always have one (and only one) __h1__ element, which is the main subject of your content. This 	and the other headings are used in part by search engines to understand the topic of the page.
</br></br>
* HTML5 introduced a number of new elements that give developers more options while also incorporating accessibility features. These tags include __main__, __header__, __footer__, __nav__, __article__, and __section__, among others.

	By default, a browser renders these elements similarly to __div__. However, using them where 			appropriate gives additional meaning in your markup. The tag name alone can indicate the type of 			information it contains, which adds semantic meaning to that content. Assistive technologies can access this 	information to provide better page summary or navigation options to their users.

	### Jump straight to content using __main__ element </br>
	The __main__ element is used to wrap the main content, and there should be only one per page. It's meant to 		surround the information that's related to the central topic of your page. It's not meant to include items that 		repeat across pages, like navigation links or banners.
	The __main__ tag also has an embedded landmark feature that assistive technology can use to quickly navigate 	to the main content. If you've ever seen a "Jump to Main Content" link at the top of a page, using a main tag 	automatically gives assistive devices that functionality.

	### Wrap content in the __article__ element </br>
	__article__ is a sectioning element, and is used to wrap independent, self-contained content. The tag works well 		with blog entries, forum posts, or news articles.
	Determining whether content can stand alone is usually a judgement call, but there are a couple simple tests 	you can use. Ask yourself if you removed all surrounding context, would that content still make sense? 			Similarly for text, would the content hold up if it were in an RSS feed?
	
	The __section__ element is also new with HTML5, and has a slightly different semantic meaning than __article__. An article is for standalone content, and a section is for grouping thematically related content. They can be used within each other, as needed. For example, if a book is the article, then each chapter is a section. When there's no relationship between groups of content, then use a __div__.
	
	### Make Screen Reader Navigation Easier with the header Landmark: </br>
	 The __header__ tag is used to wrap introductory information or navigation links for its parent tag and works well around content that's repeated at the top on multiple pages.

	__header__ tag shares the embedded landmark feature like __main__, allowing assistive technologies to quickly navigate 		to that content.
	
	### Make Screen Reader Navigation Easier with the nav Landmark: </br>
	The __nav__ element is another HTML5 item with the embedded landmark feature for easy screen reader navigation. This tag 	is meant to wrap around the main navigation links in your page.

	If there are repeated site links at the bottom of the page, it isn't necessary to markup those with a nav tag as well. 		Using a __footer__ is sufficient.
	
	### Make Screen Reader Navigation Easier with the footer Landmark:  </br>
	Similar to __header__ and __nav__, the __footer__ element has a built-in landmark feature that allows assistive devices to quickly navigate to it. It's primarily used to contain copyright information or links to related documents that usually sit at the bottom of a page.
	
	### Improve Accessibility of Audio Content with the audio Element </br>
	HTML5's __audio__ element gives semantic meaning when it wraps sound or audio stream content in your markup. Audio 	content also needs a text alternative to be accessible to people who are deaf or hard of hearing. This can be done with 	nearby text on the page or a link to a transcript.

	The __audio__ tag supports the `controls` attribute. This shows the browser default play, pause, and other controls, 	and supports keyboard functionality. This is a boolean attribute, meaning it doesn't need a value, its presence on the tag 	turns the setting on.

	Here's an example:

	```html
	<audio id="meowClip" controls>
	  <source src="audio/meow.mp3" type="audio/mpeg" />
	  <source src="audio/meow.ogg" type="audio/ogg" />
	</audio>
	```

	Note: Multimedia content usually has both visual and auditory components. It needs synchronized captions and a 		transcript so users with visual and/or auditory impairments can access it. Generally, a web developer is not 		responsible for creating the captions or transcript, but needs to know to include them.
	
	### Improved chart accessibility with the figure element </br>
	
	HTML5 introduced the __figure__ element, along with the related figcaption. Used together, these items wrap a visual representation (like an image, diagram, or chart) along with its caption. This gives a two-fold accessibility boost by both semantically grouping related content, and providing a text alternative that explains the figure.

	For data visualizations like charts, the caption can be used to briefly note the trends or conclusions for users with visual impairments. Another challenge covers how to move a table version of the chart's data off-screen (using CSS) for screen reader users.

	Here's an example - note that the figcaption goes inside the figure tags and can be combined with other elements:
	
	```html
	<figure>
  		<img src="roundhouseDestruction.jpeg" alt="Photo of Camper Cat executing a roundhouse kick">
 		 <br>
 	 	<figcaption>
  	  	Master Camper Cat demonstrates proper form of a roundhouse kick.
  		</figcaption>
	</figure>
	```
	
	### Improve form field accessibility with the label element </br>
	The __label__ tag wraps the text for a specific form control item, usually the name or label for a choice. This ties meaning to the item and makes the form more readable. The for attribute on a label tag explicitly associates that label with the form control and is used by screen readers.
	
	### Wrap radio buttons in a field set element for better accessibility
	Since radio buttons often come in a group where the user must choose one, there's a way to semantically show the choices are part of a set.

	The __fieldset__ tag surrounds the entire grouping of radio buttons to achieve this. It often uses a legend tag to provide a description for the grouping, which is read by screen readers for each choice in the fieldset element.

	The fieldset wrapper and legend tag are not necessary when the choices are self-explanatory, like a gender selection. Using a label with the for attribute for each radio button is sufficient.

	Here's an example:
	```html
	<form>
	  <fieldset>
	    <legend>Choose one of these three items:</legend>
	    <input id="one" type="radio" name="items" value="one">
	    <label for="one">Choice One</label><br>
	    <input id="two" type="radio" name="items" value="two">
	    <label for="two">Choice Two</label><br>
	    <input id="three" type="radio" name="items" value="three">
	    <label for="three">Choice Three</label>
	  </fieldset>
	</form>
	```
	
	### Standardize time with the HTML5 datetime attribute
	HTML5 also introduced the __time__ element along with a __datetime__ attribute to standardize times. This is an inline element that can wrap a date or time on a page. A valid format of that date is held by the datetime attribute. This is the value accessed by assistive devices. It helps avoid confusion by stating a standardized version of a time, even if it's written in an informal or colloquial manner in the text.

	Here's an example:
	```html
	<p>Master Camper Cat officiated the cage match between Goro and S
	corpion <time datetime="2013-02-13">last Wednesday</time>, which ended in a draw.</p>
	```
	
* CSS's magic can also improve accessibility on your page when you want to visually hide content meant only for screen readers. This happens when information is in a visual format (like a chart), but screen reader users need an alternative presentation (like a table) to access the data. CSS is used to position the screen reader-only elements off the visual area of the browser window.

	Here's an example of the CSS rules that accomplish this:
	```css
	.sr-only {
	  position: absolute;
	  left: -10000px;
	  width: 1px;
	  height: 1px;
	  top: auto;
	  overflow: hidden;
	}
	```
	
	Note: The following CSS approaches will NOT do the same thing:

	```display: none; or visibility: hidden;``` hides content for everyone, including screen reader users -OR-
	Zero values for pixel sizes, such as ```width: 0px; height: 0px;``` removes that element from the flow of your document, meaning screen readers will ignore it
	
* Low contrast between the foreground and background colors can make text difficult to read. Sufficient contrast improves the readability of your content.

	The Web Content Accessibility Guidelines (WCAG) recommend at least a __4.5 to 1__ contrast ratio for normal text. The ratio is calculated by comparing the relative luminance values of two colors. This ranges from 1:1 for the same color, or no contrast, to 21:1 for white against black, the strongest contrast. There are many contrast checking tools available online that calculate this ratio for you.
	
* Color is a large part of visual design, but its use introduces two accessibility issues. First, color alone should not be used as the only way to convey important information because screen reader users won't see it. Second, foreground and background colors need sufficient contrast so colorblind users can distinguish them. Colorblind users have trouble distinguishing some colors from others - usually in hue but sometimes lightness as well. 

	In practice, the 4.5:1 contrast ratio can be reached by shading (adding black to) the darker color and tinting (adding white to) the lighter color. Darker shades on the color wheel are considered to be shades of blues, violets, magentas, and reds, whereas lighter tinted colors are oranges, yellows, greens, and blue-greens.
	
* There are various forms of colorblindness. These can range from a reduced sensitivity to a certain wavelength of light to the inability to see color at all. The most common form is a reduced sensitivity to detect greens.

	For example, if two similar green colors are the foreground and background color of your content, a colorblind user may not be able to distinguish them. Close colors can be thought of as neighbors on the color wheel, and those combinations should be avoided when conveying important information.

	_Note_: Some online color picking tools include visual simulations of how colors appear for different types of colorblindness. These are great resources in addition to online contrast checking calculators.
	
* Screen reader users have different options for what type of content their device reads. This includes skipping to (or over) landmark elements, jumping to the main content, or getting a page summary from the headings. Another option is to only hear the links available on a page.

	Screen readers do this by reading the link text, or what's between the anchor (a) tags. Having a list of "click here" or "read more" links isn't helpful. Instead, you should use brief but descriptive text within the a tags to provide more meaning for these users.
	
* HTML offers the __accesskey__ attribute to specify a shortcut key to activate or bring focus to an element. This can make navigation more efficient for keyboard-only users.

	HTML5 allows this attribute to be used on any element, but it's particularly useful when it's used with interactive ones. This includes links, buttons, and form controls.

	Here's an example:
	```html
	<button accesskey="b">Important Button</button>
	```
	
* The HTML __tabindex__ attribute has three distinct functions relating to an element's keyboard focus. When it's on a tag, it indicates that element can be focused on. The value (an integer that's positive, negative, or zero) determines the behavior.

	Certain elements, such as links and form controls, automatically receive keyboard focus when a user tabs through a page. It's in the same order as the elements come in the HTML source markup. This same functionality can be given to other elements, such as div, span, and p, by placing a ```tabindex="0"``` attribute on them. Here's an example:
	```html
	<div tabindex="0">I need keyboard focus!</div>
	```
	_Note_: A negative tabindex value (typically -1) indicates that an element is focusable, but is not reachable by the keyboard. This method is generally used to bring focus to content programmatically (like when a div used for a pop-up window is activated).
	
* The __tabindex__ attribute also specifies the exact tab order of elements. This is achieved when the value of the attribute is set to a positive number of 1 or higher.

	Setting a ```tabindex="1"``` will bring keyboard focus to that element first. Then it cycles through the sequence of specified tabindex values (2, 3, etc.), before moving to default and ```tabindex="0"``` items.

	It's important to note that when the tab order is set this way, it overrides the default order (which uses the HTML source). This may confuse users who are expecting to start navigation from the top of the page. This technique may be necessary in some circumstances, but in terms of accessibility, take care before applying it.

	Here's an example:
	```html
	<div tabindex="1">I get keyboard focus, and I get it first!</div>

	<div tabindex="2">I get keyboard focus, and I get it second!</div>
	```


	
	
