# Chrome extension for word replacement

This project is related to this tutorial  [Chrome extension in under 60 seconds] from Codingo Tuts
 
In this tutorial I will develop the simplest Chrome extension ever in under 60 seconds. This extension will look for certain word on the website and replace it with other word. No buttons, no interface, pretty straightforward. 

First I will create chrome-extension folder and inside it I will put manifest.json file. Manifest as expected is holding extension details like name, icon, permissions and many more.
 
```javascript
{
  "manifest_version": 2,

  "name": "Simple String Replace",
  "description": "This extension will replace all occurrences of word best to Codingo",
  "version": "1.0",

  "browser_action": {
    "default_icon": "chrome-codingo.png",
    "default_popup": "switcher.html"
  },
  "content_scripts": [
    {
      "matches": ["http://*/*"],
      "js": ["switcher.js"],
      "run_at": "document_end"
    }
  ]
}
```
 
Browser action array is defining icon displayed in browser and default pop-up html file.

Content scripts is where I define which js file is activated on certain urls, and when. In this example it is activated for all urls which are using http protocol.

Pop-up html is like simple web page. I loaded some css files there and js libraries.

....

For full tutorial visit [Chrome extension in under 60 seconds].

Final result is Chrome extension which replaces word best with Codingo, checkout image bellow for results.

![alt text](https://github.com/codingo-me/chrome-extension-string-replace/raw/master/bing.png "Bing Search for best shows Codingo everywhere")

 
[Chrome extension in under 60 seconds]:http://tuts.codingo.me/chrome-extension-in-under-60-seconds
