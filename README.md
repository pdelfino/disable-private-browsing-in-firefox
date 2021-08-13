# How to disable private browsing in Firefox

Disable private browsing (incognito mode) permanently in Firefox (Ubuntu 20.04)

Follow the recipe:

- 1. In terminal, go to:
 `/usr/lib/firefox/distribution`

Obs.: This is the correct directory if you are using Firefox version 91.0 and Ubuntu 20.04. Depending on the Firefox version and/or OS this might be different.

- 2. If there is no `policies.json` file, then create one: 
```bash
 $ sudo touch policies.json
```

- 3. The file's content needs to be:
```json
{
  "policies": {
    "DisablePrivateBrowsing": true
  }
}
```

- 4. If you are facing problems with "read-only", invoke your favorite editor using **sudo**, such as:

```bash
$ sudo emacs policies.json 
$ sudo vim policies.json 
$ sudo gedit policies.json 
```

- 5. Re-start firefox and try using `Control-Shift-P`. Hopefully, it won't work.
