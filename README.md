# Disable Private Browsing in Firefox

![The Night Watch](https://upload.wikimedia.org/wikipedia/commons/thumb/3/3a/La_ronda_de_noche%2C_por_Rembrandt_van_Rijn.jpg/700px-La_ronda_de_noche%2C_por_Rembrandt_van_Rijn.jpg)

*"The Night Watch" (1642) by Rembrandt van Rijn — [Wikipedia](https://en.wikipedia.org/wiki/The_Night_Watch)*

Permanently disable private browsing (incognito mode) in Firefox on Ubuntu 20.04 using Mozilla's policy engine.

## Why

Firefox's policy system allows administrators (or individual users) to enforce browser settings system-wide. This guide uses it to disable private browsing entirely, so that `Ctrl+Shift+P` no longer opens a private window.

Learned from [mozilla/policy-templates](https://github.com/mozilla/policy-templates/blob/master/README.md#disableprivatebrowsing) by [@mkaply](https://github.com/mkaply).

## Instructions

1. Navigate to the Firefox distribution directory:

```bash
cd /usr/lib/firefox/distribution
```

> This path applies to Firefox 91.0 on Ubuntu 20.04. It may differ on other versions or distributions.

2. Create the policy file if it does not exist:

```bash
sudo touch policies.json
```

3. Set the file contents to:

```json
{
  "policies": {
    "DisablePrivateBrowsing": true
  }
}
```

4. If the file is read-only, open it with sudo:

```bash
sudo vim policies.json
```

5. Restart Firefox and verify -- `Ctrl+Shift+P` should no longer work.

## Compatibility

- **Tested on:** Ubuntu 20.04, Firefox 91.0
- **Mechanism:** Mozilla Enterprise Policy Engine
