# Applied Accessibility for web design:

* People with visual impairments rely on screen readers to convert web content to an audio interface. They won't get information if it's only presented visually. For images, screen readers can access the __alt__ attribute and read its contents to deliver key information.Good __alt__ text provides the reader a brief description of the image. You should always include an __alt__ attribute on your image. Per HTML5 specification, this is now considered mandatory.

	In situations when an image is already explained with text content (like captions), or does not add meaning to 	a page, the __img__ still needs an __alt__ attribute, but it can be set to an empty string.
</br></br>
* Screen readers can be set to read only the headings on a page so the user gets a summary. This means it is important for the heading tags in your markup to have semantic meaning and relate to each other, not be picked merely for their size values.

	__Semantic meaning__ means that the tag you use around content indicates the type of information it contains.

	Each page should always have one (and only one) __h1__ element, which is the main subject of your content. This 	and the other headings are used in part by search engines to understand the topic of the page.
</br></br>
* HTML5 introduced a number of new elements that give developers more options while also incorporating accessibility features. These tags include __main__, __header__, __footer__, __nav__, __article__, and __section__, among others.

	By default, a browser renders these elements similarly to __div__. However, using them where 			appropriate gives additional meaning in your markup. The tag name alone can indicate the type of 			information it contains, which adds semantic meaning to that content. Assistive technologies can access this 	information to provide better page summary or navigation options to their users.

	### Jump straight to content using __main__ element: </br>
	The __main__ element is used to wrap the main content, and there should be only one per page. It's meant to 		surround the information that's related to the central topic of your page. It's not meant to include items that 		repeat across pages, like navigation links or banners.
	The __main__ tag also has an embedded landmark feature that assistive technology can use to quickly navigate 	to the main content. If you've ever seen a "Jump to Main Content" link at the top of a page, using a main tag 	automatically gives assistive devices that functionality.

	### Wrap content in the __article__ element: </br>
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
	
	
