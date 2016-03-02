# slimmodal
A simple, flexible, responsive, flexbox-based modal. 

I wanted to create a simple modal that would not rely on a library (like <em>Foundation, Semantic, Bootstrap, etc</em>), since those can often feel bloated and/or somewhat difficult to style. This also allow you to pass <em>"data-"</em> parameters for content and a couple of settings for the modal. This example is set up to allow you to look at the JS, CSS, and html markup...and learn from it. Sure, you can use as is - but dang, think of what you can do to make it better. Add some more <em>data-attributes</em>, <em>transform effects</em>, etc.

## Using a single modal for multiple content calls
If you're looking for a way to display quick and easy content to the user, but don't need to muddy up your markup with multiple modals to call, then consider passing content through with data-attributes. Very easy to use a single "empty" modal, by merely passing in content from the element calling the modal. 

**Modal:**

> 			<div class="slim_modal" id="exampleData">
				<div class="sm_content">
				<div class="sm_header"></div>
				<div class="sm_icon_menu is_right">
					<ul>
						<li class="sm_close">
                        	<i class="fa fa-times fa-fw "></i>
                        </li>
					</ul>
				</div>
					<div class="sm_content_inner_wrap">
						<div class="sm_area_all"></div>
						<a class="sm_close sm_close_button">CLOSE</a>
					</div>
				</div>
			</div>

**Button (or whatever element) calling the modal:**

> <a class="sm_open" 
	data-modal="exampleData" 
	data-effect="pushdown" 
	data-header="#1 This header is from the link" 
	data-overlay="red"
	data-content="This is a sample HTML string being passed with a data-attribute... <p><h3>Super easy to change, simply by tweaking the button launching the modal.</h3></p>" 
	data-wrapper-color="red">Modal (Passing Data-Attributes w/Eye-Searing Red Overlay Color)
</a>

It's literally as simple as that.
