
**Minixed** is a minimal but nice-looking PHP directory indexer.  
You can see it as a replacement for the Apache `mod_autoindex`.

> *«How does it look?»* Like [**this**](http://www.lorenzostanco.com/minixed_demo/).  
> *«I don't like it.»* You are a CSS master, right? Good, you know what to do.

How to use
----------

Just drop the [**`index.php`**](https://github.com/lorenzos/Minixed/blob/master/index.php) 
script in the same directory that contains files you want to index.

	wget https://raw.githubusercontent.com/lorenzos/Minixed/master/index.php

> *«Really? One single file?»* Yes, really. Glad you asked.  
> *«If so, where are icon files?»* They are hard coded into the source, thanks Base-64.  
> *«Was it really necessary?»* I don't know, I just loved the idea you need only one file.

If you want Minixed to work also in subfolders, edit `index.php` setting:

	$browseDirectories = true; // Navigate into sub-folders

Configuration
-------------

The script works well out-of-the-box, and generally you want to leave it as it is.
However if you have some particular needs, there are some PHP variables placed 
in the first lines of `index.php` you can edit.

You can enable navigation into subfolders using:

	$browseDirectories = true; // Navigate into sub-folders

You can change the page title (and subtitle) providing strings that can contains
some placeholders that will be *parsed* at runtime:

	$title = 'Index of {{path}}';
	$subtitle = '{{files}} objects in this folder, {{size}} total'; // Empty to disable

You can make breadcrumb links if titles contain `{{path}}`, useful when navigating into subfolders:

	$breadcrumbs = true; // Make links in {{path}}

You can tell the script how to build the files list using:
	
	$showParent = false; // Display a (parent directory) link
	$showDirectories = true;
	$showDirectoriesFirst = true; // Lists directories first when sorting by name
	$showHiddenFiles = false; // Display files starting with "." too
	
And how that list should look:

	$alignment = 'left'; // You can use 'left' or 'center'
	$showIcons = true;
	$dateFormat = 'dd/mm/yyyy HH:ii'; // Used in date() function
	$sizeDecimals = 1;
	
Finally, you can customize the content of the meta-tag "robots" 
if you want to give some search engine hints:

	$robots = 'noindex, nofollow'; // Avoid robots by default
	
Of course, if PHP is a friend of yours you can easily
understand the whole script source code, so the only limit to
customization is your imagination.

Bug tracking and developing
---------------------------

If you find bugs, if you have suggestions, if you modified the script adding 
features or improvements, feel free to contribute by opening 
[**Issues**](https://github.com/lorenzos/Minixed/issues) or 
[**Pull Requests**](https://github.com/lorenzos/Minixed/pulls).
