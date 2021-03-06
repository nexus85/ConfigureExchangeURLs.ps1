#Exchange Server URL Configuration Scripts

This repository contains two scripts that are useful for reviewing or configuring the URLs for the various Client Access services on Exchange Servers.

##GetExchangeURLs.ps1

The **GetExchangeURLs.ps1** script will return a list of the URLs configured on a Client Access server. This can be used to quickly review the existing configuration.

Example:

```
.\Get-ExchangeURLs.ps1 -Server sydex1
```

##ConfigureExchangeURLs.ps1

The **ConfigureExchangeURLs.ps1** script will configure one or more Client Access servers for the namespaces you specify. All Client Access server
URLs will be set to the same namespace.

If you are using separate namespaces for each CAS service this script will not handle that.

The script sets Outlook Anywhere to use NTLM with SSL required by default. If you have different auth requirements for Outlook Anywhere  use the optional
parameters to set those.

Parameters:
- **-Server** - The name(s) of the server(s) you are configuring.
- **-InternalURL** - The internal namespace you are using.
- **-ExternalURL** - The external namespace you are using.
- **-DefaultAuth** - The default authentication method to set for Outlook Anywhere. Defaults to NTLM.
- **-InternalSSL** - Specifies the internal SSL requirement for Outlook Anywhere. Defaults to True (SSL required).
- **-ExternalSSL** - Specifies the external SSL requirement for Outlook Anywhere. Defaults to True (SSL required).

Examples:

```
.\ConfigureExchangeURLs.ps1 -Server sydex1 -InternalURL mail.exchangeserverpro.net -ExternalURL mail.exchangeserverpro.net
```

```
.\ConfigureExchangeURLs.ps1 -Server sydex1,sydex2 -InternalURL mail.exchangeserverpro.net -ExternalURL mail.exchangeserverpro.net
```

##More Info

http://exchangeserverpro.com/powershell-script-configure-exchange-urls/

##Credits

Written by: Paul Cunningham

For more Exchange Server tips, tricks and news
check out Exchange Server Pro.

* Website:	http://exchangeserverpro.com
* Twitter:	http://twitter.com/exchservpro

Find me on:

* My Blog:	http://paulcunningham.me
* Twitter:	https://twitter.com/paulcunningham
* LinkedIn:	http://au.linkedin.com/in/cunninghamp/
* Github:	https://github.com/cunninghamp
