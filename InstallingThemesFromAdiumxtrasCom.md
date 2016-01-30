# Introduction #

To install themes directly, your must enable adiumxtra:// protocol handling in your browser to handle links like this:

`adiumxtra://www.adiumxtras.com/download/6227`

This tutorial consume, that adium2pidgin conventor place in `/usr/local/bin/adium2pidgin-theme-convert.py` on your system

# Gnome #
Run in terminal:
```
gconftool-2 -t string -s /desktop/gnome/url-handlers/adiumxtra/command "/usr/local/bin/adium2pidgin-theme-convert.py %s"
gconftool-2 -t bool -s /desktop/gnome/url-handlers/adiumxtra/enabled true
gconftool-2 -t bool -s /desktop/gnome/url-handlers/adiumxtra/needs_terminal false
```

# Firefox #

Go to `about:config`, right-click, select 'Add', select 'String', type: `network.protocol-handler.app.adiumxtra` click 'Ok', type /usr/local/bin/adium2pidgin-theme-convert.py

Then right-click, select 'Boolean', type `network.protocol-handler.external.adiumxtra`, then select 'true'

[More information](http://kb.mozillazine.org/Register_protocol#Linux_and_Mac) (about Windows), and [more information](http://support.mozilla.com/ru/kb/The+protocol+is+not+associated+with+any+program)

# Epiphany #

Add:
```
pref("network.protocol-handler.app.adiumxtra","/usr/local/bin/adium2pidgin-theme-convert.py");
pref("network.protocol-handler.warn-external.adiumxtra",false);
```
to `/usr/share/epiphany-browser/default-prefs.js`