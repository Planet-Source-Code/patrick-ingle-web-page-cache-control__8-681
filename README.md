<div align="center">

## Web Page Cache Control


</div>

### Description

Is your PHP/HTML output being cached on the client? My output was especially during development and I got tired of always pressing the browser reload/refresh button.

Therefore, I discovered using the PHP header function and the HTML keyword Expires prevents my browser from caching the resultant HTML output.

See the code below. Very simple and easy to include and will ensure that your clients will always invoke the server-side PHP script each the page is accessed.
 
### More Info
 
See purpose above

A formatted HTML output

None known


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Patrick Ingle](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/patrick-ingle.md)
**Level**          |Beginner
**User Rating**    |5.0 (10 globes from 2 users)
**Compatibility**  |PHP 4\.0
**Category**       |[Internet/ Browsers/ HTML](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/internet-browsers-html__8-9.md)
**World**          |[PHP](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/php.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/patrick-ingle-web-page-cache-control__8-681/archive/master.zip)





### Source Code

```
<?php
	// This script is one way to prevent/control caching of a
	// web page.
	//
	// Example of What Happens without an expires:
	// Your web page is saved to your local hard drive and if
	// you want to reload it, you must click the Refresh/Reload
	// button on the browser. If you just press Return while the
	// URL line has focus, the cache copy is only loaded.
	// This is probably fine for normal pages which do not change
	// but is a headache when developing pages and constantly pressing
	// the Reload/Refresh browser button.
	//
	// Using the Expires and setting the date and time to the current
	// instantenous time, will prevent caching and permit the reload
	// of the page from server just by pressing return while the URL
	// address line is in focus.
	//
	// Another purpose is when you have dynamic content or for PHP
	// when you are referencing a database table. Good pratice would
	// be to expire that page immediately so the next time the client
	// loads the page, any new data is retrieved without any extra
	// effort on the user.
	//
	// IMPORTANT:
	// The Expires: time stamp must be GMT. PHP has a function to
	// format the date in GMT.
	$nowGMT = gmdate("M d Y H:i:s");
	// This is header information and needs to be in the
	// header portion of the client page.
	// If displaying other than graphics, the Content-type
	// needs updating to reflect the content being displayed.
	$header = "Content-type: text/plain\nExpires: $nowGMT\n\n";
	header($header);
	// NOTE:
	// I've discovered, I needed to include the HTML <body> tags
	// when I use the PHP header() function, otherwise the
	// HTML tags are not interpreted properly and are displayed
	// as normal text.
	echo "<body>\n";
	echo "<b>$nowGMT</b>";
	echo "</body>\n";
?>
```

