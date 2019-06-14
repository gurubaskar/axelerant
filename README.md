# Site API key integration

Created a custom module to update Site API key field in the Site information page.

Before creating the custom module, the system has default Drupal 8 core modules were installed.

As per the requirement, below task are created using this custom module:

* A text field named "Site API key" created in "Site Information" page/form. Displayed "No API Key yet" placeholder text displayed. This field will accept varchar.
* When the form is submitted, entered value will be saved in the system using "siteapikey".
* Drupal status message informed when the data entered in the text field. Empty and same value condition has been validated.
* "Save Configuration" button changed to "Update Configuration".
* Once the value saved, "Site API key" will populate the entered value.
* Module provide a URL to respond JSON content using the API key and node id. Using content type "page" it will respond or it will response with "access denied".
* Created menu "/nodevalidate/{siteapikey}/{nid}" to response JSON value.
* If the key doesn't match, access dened will return.
* If the key matches and nid is wrong, 'not a node' will return.
* If both key and nid matches, it will return the JSON object of the node.

Demo:

* http://localhost/<foldername>/nodevalidate/{siteapikey}/{nid}.
* Node URL: http://localhost/page/nodevalidate/axe123/1 (axe123: Site API key, 1: nid created)
* Access denied : http://localhost/page/nodevalidate/axe321/1
* Wrong node : http://localhost/page/nodevalidate/axe123/123

Reference:

https://www.drupal.org/

https://stackoverflow.com/

Total time:

4hrs
