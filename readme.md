# Statamic Email Form Plugin

This plugin is designed to allow you to quickly and easily create forms
that will be used to email reciepents.

## Example Form Template

Here is a full example to get you going. Please see the parameters section
for more field options:

	{{ email:form subject="Contact Form" to="test@test.com" required="name" }}
		{{ if error}}
			<h1>Error</h1>
			<ul>
			{{ errors }}
				<li>{{error}}</li>
			{{ /errors }}
			</ul>
		{{ endif }}

		{{ if success }}
			<h1>IT WORKED!</h1>
		{{ else }}
			<p>
				<label for="name">Name:</label>
				<input type="text" name="name" id="name" value="Bill">
			</p>
			<p>
				<label for="from">Email:</label>
				<input type="text" name="from" id="from" value="test@test.com">
			</p>
			<p><input type="submit"></p>
		{{ endif }}
	{{ /email:form }}

## Parameters

The `{{ email:form }}` tag accepts the following paramaters:

* **msg_header**: The top body section of the email.
* **msg_footer**: The bottom body section of the email.
* **subject**: The subject of the email.
* **to**: The form recipient's email address.
* **cc**: A cc email address.
* **bcc**: A bcc email address.
* **required**: A pipe seperated list of required fields. Example: "name|address|city". Currently this only does simple validation to check if it is an empty value.

## Issues / Gotchas - On the radar

1. The name field is hard coded as the reply name in the plugin so it is recommended you use this field in your form.
2. The plugin does have some hard coded English text and that will be fixed up in a future release. Still deciding on the best option for this.
3. Validation is currently lacking some useful features. Basically only simple checking if the field is empty.

## Contribute

If you see any issues or have ideas for improvements pull requests are gladly
accepted. ;-)
