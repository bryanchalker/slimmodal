# slimmodal
A simple, flexible, responsive, flexbox-based modal. 

I wanted to create a simple modal that would not rely on a library (like <em>Foundation, Semantic, Bootstrap, etc</em>), since those can often feel bloated and/or somewhat difficult to style. This also allow you to pass <em>"data-"</em> parameters for content and a couple of settings for the modal. This example is set up to allow you to look at the JS, CSS, and html markup...and learn from it. Sure, you can use as is - but dang, think of what you can do to make it better. Add some more <em>data-attributes</em>, <em>transform effects</em>, etc.

## Modal with a little more to it
This is just a modal with a slide up header and slide out icon menu. A simple way to have a little more intereaction with a modal, other than reading it or filling out a form. 

> 		<div class="slim_modal" id="exampleAdvanced">
				<div class="sm_content">
				<div class="sm_header">Hi. I'm a Header.</div>
				<div class="sm_icon_menu">
					<ul>
						<li class="sm_close"><i class="fa fa-times fa-fw "></i></li>
						<li><i class="fa fa-gear fa-fw"></i></li>
						<li><i class="fa fa-plus fa-fw"></i></li>
						<li><i class="fa fa-sitemap fa-fw"></i></li>
						<li><i class="fa fa-user fa-fw"></i></li>
					</ul>
				</div>
				<div class="sm_content_inner_wrap">
					<div class="sm_area_top">
						<h3>Example Modal Content
							<span>...for this CSS Demo</span>
						</h3>
					</div>
					<div class="sm_area_bottom">
						<p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Deserunt nihil asperiores recusandae odio distinctio earum voluptatibus, quisquam repellendus voluptas quaerat quis est totam, optio quia, molestias voluptatum error libero pariatur!</p>
					</div>
					<div class="sm_close sm_close_button">CLOSE</div>
				</div>
				</div>
			</div>


## Using a single modal for multiple content calls
If you're looking for a way to display quick and easy content to the user, but don't need to muddy up your markup with multiple modals to call, then consider passing content through with data-attributes. Very easy to use a single "empty" modal, by merely passing in content from the element calling the modal. 

**Modal:**

> 			<div class="slim_modal" id="exampleData">
				<div class="sm_content">
				<div class="sm_header"></div>
				<div class="sm_icon_menu is_right">
					<ul>
						<li class="sm_close"><i class="fa fa-times fa-fw "></i></li>
					</ul>
				</div>
					<div class="sm_content_inner_wrap">
						<div class="sm_area_all"></div>
						<a class="sm_close sm_close_button">CLOSE</a>
					</div>
				</div>
			</div>

**Button (or whatever element) calling the modal:**

>			<a class="sm_open" 
				data-modal="exampleData" 
				data-effect="pushdown" 
				data-header="#1 This header is from the link" 
				data-overlay="red"
				data-content="This is a sample HTML string being passed with a data-attribute... <p><h3>Super easy to change, simply by tweaking the button launching the modal.</h3></p>" 
				data-wrapper-color="red">Modal (Passing Data-Attributes w/Eye-Searing Red Overlay Color)
			</a>

It's literally as simple as that. Data-attributes are passed (add to or edit this mapping via the [slimmodal.js](js/slimmodal.js) file) to the modal on launch.

**Quick overview of the mapping taking place:**
- _data-modal_ : ID for the modal
- _data-effect_ : adds this class to ".sm_content" to apply the loading effect on the modal. ".pushdown" and ".pushup" are defined in the [styles.css](css/styles.css) file, and are basic 2D transform with associated box-shadow.
- _data-header_ : This string populates the ".sm_header" class...typically a short title over the modal.
- _data-overlay_ : adds this class to ".slim_modal", which is defined in the [styles.css](css/styles.css) file. This allows you to have different colors for the overlay easily. Several are already included: **green**, **red**, **tan**, and **none**. All are easily customizable in the css. 
- _data-content_ : This string populates the ".sm_area_all" section. 
- _data-wrapper-color_ : Adds this class to ".sm_content", to allow you to add a but of color to the outer modal easily. 

Remember, this project is set up with a pre-set group of data-attributes, but can be expanded very easily, with only minor tweaks to the js, css, and markup. 

For example, you make want to add a "data-shadow" attribute to the elelment calling, which might remove the box-shadow applied by default. To do this:
- CSS: Add a class to the css file (such as "**.noshadow {box-shadow: none;}**").
- JS: Add "**var modalshadow = $(this).attr('data-shadow');**" then map to the corresponding element on the modal as "**$('#' + modal + ' .sm_content').addClass(modalshadow);**"
- HTML: Finally, add **data-shadow="noshadow"** to the element calling the modal. 

That's it :)






