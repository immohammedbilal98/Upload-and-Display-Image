# Upload-and-Display-Image

Displaying image in HTML form field on file upload is very easy with the use of javascript. Let's add a little more effect to make it look more attractive.

Hide file upload button from HTML page and replace it with a text or icon link
If you have a look at most of the social platforms, they have one thing in common related to file upload and that's the file or image upload button which is not present in the form and a plain text or icon link does the work. It helps us get rid of the boring file upload button from our HTML page while getting the job of file upload done. Let's see, how its's done.

<input type="file"  accept="image/*" name="image" id="file" style="display: none;">
If you want to allow upload of all image types in your form, then you can leave it as shown above. You can replace the properties on the attribute accept if you want specify the image extensions to be uploaded via your form as shown below.

<input type="file"  accept="image/gif, image/jpeg, image/png" name="image" id="file" style="display: none;">
We need a name for the input field to get it added to the database, so we provided it with a name image. Provide an id to your file input form and add style display: none or visibility:hidden. Display property is better to use here as it won't occupy the space in your page.

Create a label for the file input field
Now, create a label with the same id added in for attribute to connect it to the file input field as shown below and you are done.

<p><label for="file" style="cursor: pointer;">Upload Image</label></p>
Now, if you click on the label, the file explorer will get opened as it would do on click of the button of file input.

But, once you hide those file upload buttons from your HTML page, the file information displayed by the side of the button on file upload gets hidden too which might make the users confused on whether the image is uploaded or not. In such cases, we can display the uploaded images for their convenience as well as improve the outlook of the form page too.

So, let's add an HTML <img> element to display the uploaded image.

<img id="output" width="200" />	
Here, we added an HTML <img> tag with no source but an id which will retrieve the image source from javascript and defined it's with to be 200px.

In order to activate an event defined in any javascript code, we'll need a event handler in your HTML element, so we'll add that to our file input field.

<input type="file"  accept="image/*" name="image" id="file"  onchange="loadFile(event)" style="display: none;">
Here, loadFile(event) is our event handler that'll be activated once the value in the input field is changed so the chage in that input field is our event.

Javascript to display uploaded image in html
Let's add the javascript code to display the image in the HTML element <img id="output"> then.

<script>
var loadFile = function(event) {
	var image = document.getElementById('output');
	image.src = URL.createObjectURL(event.target.files[0]);
};
</script>
Here, our event handler will hold a value which will be retrieved through the image file being uploaded via the input file button as an URL which we require to display the image in our webpage.

Entire code block as a whole required to display uploaded image in html using javascript
<p><input type="file"  accept="image/*" name="image" id="file"  onchange="loadFile(event)" style="display: none;"></p>
<p><label for="file" style="cursor: pointer;">Upload Image</label></p>
<p><img id="output" width="200" /></p>

<script>
var loadFile = function(event) {
	var image = document.getElementById('output');
	image.src = URL.createObjectURL(event.target.files[0]);
};
</script>
In this way, you can display the uploaded file in html using javascript in an attractive way.
