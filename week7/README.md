# Project 7 - WordPress Pentesting

Time spent: **10** hours spent in total

> Objective: Find, analyze, recreate, and document **five vulnerabilities** affecting an old version of WordPress

## Pentesting Report

1. (Required) **Authenticated Stored Cross_Site Scripting (XSS) CVE-2015-5622/5623**
  - [ ] Summary: A user or author type account is required.  A post or comment can contain HTML Javascropt which will trigger a XSS     attack.
    - Vulnerability types: XSS
    - Tested in version: 4.2
    - Fixed in version: 4.2.3
  - [ ] GIF Walkthrough: [GIF Here](https://github.com/bjmotox/week7/blob/master/AuthenticatedStoredXSS.gif)
  
  - [ ] Steps to recreate:
  * Contributor or Author submits post or comment that includes code like: `<a href="[caption code=">]</a><a title=" onmouseover=alert('test')  ">link</a>`
  * Page is approved
  * Exploit is live and will be executed when users mouseover link
        
  - [ ] Affected source code:
    - [Link 1](https://core.trac.wordpress.org/browser/tags/version/src/source_file.php)
    
1. (Required) **User Enumeration**
  - [ ] Summary: The login page for the site lists users as incorrect or correct.
    - Vulnerability types:User Enumeration
    - Tested in version:4.2
    - Fixed in version: -
  - [ ] GIF Walkthrough: [GIF Here](https://github.com/bjmotox/week7/blob/master/UsernameEnumeration.gif)
  - [ ] Steps to recreate: 
  * Click login site on the bottome of the page
  * Enter assorted Usernames and fill password
  * Map result to see what Users are connected to this site
  - [ ] Affected source code:
    - [Link 1](https://core.trac.wordpress.org/browser/tags/version/src/source_file.php)
    
1. (Required)   **Application Denial of Service CVE-2018-6389**
  - [ ] Summary: An application level DOS attack is possible.  The `'load-scripts.php'` can be forced to call all possible Javascript files, and make the site unusable by consuming large amounts of computing resources.  
    - Vulnerability types: DOS
    - Tested in version: 4.2
    - Fixed in version: 4.9.2
  - [ ] GIF Walkthrough: [GIF Here](https://github.com/bjmotox/week7/blob/master/DOSattack.gif)
  - [ ] Steps to recreate: 
  * Download Doser.py `https://github.com/Quitten/doser.py`
  * Attack site using terminal command `python doser.py -t 999 -g 'https://targeted.site.com'`
  * Navigate site to confirm DOS
  - [ ] Affected source code:
    - [Link 1](https://core.trac.wordpress.org/browser/tags/version/src/source_file.php)
    
1. (Optional) **Fingerprinting**
  - [ ] Summary: A readme file is available, exposing the version of wordpress being used.  
    - Vulnerability types:Fingerprinting
    - Tested in version: 4.2
    - Fixed in version: 4.8.1
  - [ ] GIF Walkthrough: [Gif](https://github.com/bjmotox/week7/blob/master/Fingerprinting.gif)
  - [ ] Steps to recreate: 
  * enter `/readme.html` to the end of the site URL
  * view contents of the readme file
  - [ ] Affected source code:
    - [Link 1](https://core.trac.wordpress.org/browser/tags/version/src/source_file.php)


## Assets

[Doser](https://github.com/Quitten/doser.py)


## Resources

- [WordPress Source Browser](https://core.trac.wordpress.org/browser/)
- [WordPress Developer Reference](https://developer.wordpress.org/reference/)

GIFs created with [LiceCap](http://www.cockos.com/licecap/).

## Notes

Describe any challenges encountered while doing the work

## License

    Copyright [2018] [Brendan Crow]

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
