# Chrome Extension : Getting DOM Source and Posting it as AJAX

This chome extension is simple for 

- Injecting a script whenever a page is loaded 
- Injected script serializes HTML. 
- Sends the Serailzed HTML though AJAX to any Page. 
- Peform any Redirection such as reading a Next link and redirecting to it. 
- Injected CSS for adding a green border around the page. Just to let me know that Script Injections are working just fine on the domain. 

***

## Purpose

I wanted to scape data after logging into a particular site. 
And just wanted the DOM that is loaded instead of source as data
was loaded into the page through AJAX requests. 

This small Script chrome extension sloved the probelm and I could 
browse automatically page by page and get data. 

***

## How to Use. 

### Step 1 : On the Manifest file(manifest.json) change the matches URL from https://www.google.co.in/ to the URL you want the 
injection to work on. 

``` javascript
{
  "name": "Post Page Content as Ajax",
  "version": "1.0",
  "manifest_version": 2,
  "description": "Small Script that takes dom and Posts it as a AJAX Request where you desire on load. ",
  "content_scripts": [
    {
      "matches": [
      	"https://www.google.co.in/*"
      	],
      	"css": ["mystyle.css"],
        "js": ["getPagesSource.js"]
    }
  ],
  "permissions": ["tabs", "<all_urls>"]
}
```

### Step 2 Change the AJAX target URL on getPageSource.js. 

Find line similar to the following and change. 

``` javascript
xhr.open("POST", "https://iamshishir.com/");

```

### Step 3
If your are using PHP Server you can use the folloiwng code to collect data and save to file.
You can alter the file accordingly for things such as you would have to change the filename
to write different files for different URLs.  

``` php
<?php
$myfile = fopen("newfile.txt", "w") or die("Unable to open file!");
$txt = $_POST["data"];
fwrite($myfile, $txt);
fclose($myfile);
?>
```

***
If you want help in creating a similar scirpt please feel free to contact 
me at my email address shishir.raven@gmail.com 

You can also visit me on my website http://www.iamshishir.com
***
