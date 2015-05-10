=== Contact Form 7 - Dynamic Select Extension ===
Contributors: Hube2
Tags: contact form 7 dynamic select drop down menu
Requires at least: 4.0
Tested up to: 4.2
Stable tag: 1.0.0
Donate link:
License: GPLv2 or later
License URI: http://www.gnu.org/licenses/gpl-2.0.html

Add Dynamic Select Fields in Contact Form 7.


== Description ==

Create dynamic select fields in contact form 7. Requires Contact Form 7.

Field values of dynamic select field are populated by using filters.


How To Use
----------

1) Create a filter to be called from your CF7 Dynamic Select Field.

Example Filter:

`function cf7_dynamic_select_do_example1($choices, $args=array()) {
	// this function returns an array of 
	// label => value pairs to be used in
	// a the select field
	$choices = array(
		'-- Make a Selection --' => '',
		'Choice 1' => 'Choice 1',
		'Choice 2' => 'Choice 2',
		'Choice 3' => 'Choice 3',
		'Choice 4' => 'Choice 4',
		'Choice 5' => 'Choice 5'
	);
	return $choices;
} // end function cf7_dynamic_select_do_example1
add_filter('wpcf7_dynamic_select_example1', 
             'cf7_dynamic_select_do_example1', 10, 2);`

2) Enter the filter name and any arguments into the Filter Field when adding a Dynamic Select Field.
For example, if we need to supply a term_id so that the filter can get the posts in a category the
filter value entered would look something like this:

`my-filter term_id=9`

***Do Not Include any extra spaces or quotes arround values, names or the =***

You can pass any number are arguments to your filter and they will be converted into an array. For example the
following:

`my-filter product-type=101 brand=500`

This will call the function assocaited with the filter hook 'my-filter' with an arguments the argument array of:
`$args = array(
    'product-type' => 101,
    'brand'        => 500
)`

Your filter must return an array. The array must be a list of "Label" => "Value" pairs.
For more information see the example in cf7-dynamic-select-examples.php included in the plugin folder.

[Also on GitHub](https://github.com/Hube2/contact-form-7-dynamic-select-extension)

== Installation ==

1. Upload the files to the plugin folder of your site
2. Activate it from the Plugins Page


== Screenshots ==

1. Create Dynamic Select Field


== Frequently Asked Questions ==


== Changelog ==

= 1.0.0 =

* initial release