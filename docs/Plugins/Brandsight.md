title: Brandsight

# How To Use the Brandsight DNS Plugin

This plugin works against the [Brandsight DNS](https://gcd.com/brandsight/) provider, which is part of GoDaddy Corporate Domains.


## Setup

As of writing this, Brandsight API keys must be requested from their support team. See their [API docs](https://developer.brandsight.com/#section/Getting-Started/API-Key-and-Secret) for the current process to obtain an API key. You will also need your Customer ID which they will usually provide at the same time as the API key if you don't already know it.

## Using the Plugin

The Key is used with the `BSKey` string parameter, the Secret is used with the `BSSecret` SecureString parameter, the Customer ID is used with the `BSSecret` parameter.

```powershell
$pArgs = @{
    BSKey = 'xxxxxxxxxxxxxxxx'
    BSSecret = (Read-Host 'Secret' -AsSecureString)
    BSCustomerID = 'xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx'
}
New-PACertificate example.com -Plugin Brandsight -PluginArgs $pArgs
```
