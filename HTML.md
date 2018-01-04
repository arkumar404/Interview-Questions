* What does a `doctype` do?
-> The declaration is used to inform a website visitor's browser that the document being rendered is an HTML document. Its sole purpose is to prevent a browser from switching into so-called “quirks mode” and make it compliant with HTML standards.

* What's the difference between full standards mode, almost standards mode and quirks mode?
-> In quirks mode, layout emulates nonstandard behavior in Navigator 4 and Internet Explorer 5. This is essential in order to support websites that were built before the widespread adoption of web standards.
In full standards mode, the behavior is (hopefully) the behavior described by the HTML and CSS specifications.
In almost standards mode, there are only a very small number of quirks implemented.

* What's the difference between HTML and XHTML?
-> HTML is SGML(Standard Generalized Markup Language)-based while XHTML is XML(Extensible Markup Language)-based. XHTML is strict when compared to HTML and does not allow user to get away with lapses in coding and structure. XML needs to be parsed with standard XML parsers while HTML needs flexible framework requiring lenient HTML specific parser.

* Are there any problems with serving pages as `application/xhtml+xml`?
-> It will more than likely mess up the page for anyone still using older versions of IE. When a browser reads XML it uses an XML parser, not an HTML parser. IE < 8 will show a download dialog for the pages, instead of rendering them properly.

* How do you serve a page with content in multiple languages?
-> By changing the lang attribute on the html element. <html lang="en"> 
Elements can also be wrapped in a lang tag if you have more than one language on the same page. 
<div lang="es">Yo no hablo español</div>  
<div lang="fr">Je ne parle pas français</div>

* What kind of things must you be wary of when design or developing for multilingual sites?
-> Properly localizing content for different audiences based on their location, as well as allowing for a user to easily change their country/language.
dir attr indicating language direction, such as rtl
<meta charset='UTF-8'>

* What are `data-` attributes good for?
-> data can be stored on markups that not visible to end users, also not violating the standard HTML5. JavaScript can easily access by dataset. It is intended to store custom data private to the page or application.

* Consider HTML5 as an open web platform. What are the building blocks of HTML5?
-> Semantics — Allowing you to describe more precisely what your content is.
Connectivity — Allowing you to communicate with the server in new and innovative ways.
Offline and storage — Allowing webpages to store data on the client-side locally and operate offline more efficiently.
Multimedia — Making video and audio first-class citizens in the Open Web.
2D/3D graphics and effects — Allowing a much more diverse range of presentation options.
Performance and integration — Providing greater speed optimization and better usage of computer hardware.
Styling — Letting authors write more sophisticated themes.

* Describe the difference between a `cookie`, `sessionStorage` and `localStorage`.
-> All the above mentioned technologies are key-value storage mechanisms on the client side. They are only able to store values as strings.
Cookie
    Initiator — Client or server. Server can use Set-Cookie header.
    Expiry — Manually set.
    Persistent across browser sessions — Depends on whether expiration is set.
    Have domain associated — Yes
    Sent to server with every HTTP request — Yes
    Capacity (per domain) — 4kb
    Accessibility — Any window

localStorage
    Initiator — Client
    Expiry — Forever
    Persistent across browser sessions — Yes
    Have domain associated — No
    Sent to server with every HTTP request — No
    Capacity (per domain) — 5MB
    Accessibility — Any window

sessionStorage
    Initiator — Client
    Expiry — On tab close
    Persistent across browser sessions — No
    Have domain associated — No
    Sent to server with every HTTP request — No
    Capacity (per domain) — 5MB
    Accessibility — Same tab

* Describe the difference between `<script>`, `<script async>` and `<script defer>`.
-> <script> stops rendering process, and download and run a script.
<script async> don't stop rendering process while asynchronously downloading a script. When finishing download, it stops rendering and runs the script.
<script defer> don't stop rendering process while asynchronously downloading a script. When finished rendering, it runs the script. A deferred script must not contain document.write.
Note: The async and defer attrib­utes are ignored for scripts that have no src attribute.

* Why is it generally a good idea to position CSS `<link>`s between `<head></head>` and JS `<script>`s just before `</body>`? Do you know any exceptions?
-> Putting <link>s in the head is part of the specification. Besides that, placing at the top allows the page to render progressively which improves user experience. It prevents the flash of unstyled contents.

Downloading the scripts at the bottom will allow the HTML to be parsed and displayed to the user first. An exception for positioning of <script>s at the bottom is when your script contains document.write(). Another one is putting <script>in the <head> and use the defer attribute.

* What is progressive rendering?
-> Progressive rendering is the name given to techniques used to improve performance of a webpage (in particular, improve perceived load time) to render content for display as quickly as possible. This can be done asynchronously with different components being loaded as they finish. A HTTP response is flushed multiple times, a browser doesn't wait until the whole content is loaded and renders each part earlier.


