* Sun  4 Mar 19:52:58 GMT 2018

Moved over to the new version (date) format, and the norm will now be to have a --version|-v flag which displays this. The reason for this change, is that I got sick of updating the header's timestamp (courtesy of a shortcut I added to VIM), and then having to change the --help output's version as well!

Now when I use the aforementioned shortcut, it updates the _VERSION_ variable as well as the header, plus it clears out any stranded tabs and spaces. See miscellaneous/.vimrc for how I did this. Lastly, as an added bonus, this --version|-v flag allows for easy parsing of tfl programs, open the doors for later tfl program update checks via insit; this is something I've been thinking of incorporating for a while now. Feedback welcome.

* Sun 25 Feb 19:45:34 GMT 2018

Logging is now more aggressive, to further assist any debugging endeavors. I've also added the ability to view the logging output while using insit, using the `--verbose` or `-v` flags; this should work whether logging is enabled or not, but of course the intended result is that logging won't be saved, just shown.

Uninstalling items available using insit, now supports gvfs-trash, meaning insit will send files to trash, rather than permanently deleting them. This is only done if gvfs-trash is detected by insit. The user will be informed, as usual.

* Fri 23 Feb 18:23:01 GMT 2018

At long last, insit now support wget version 1.19.2.

* Thu 15 Feb 03:02:47 GMT 2018

The file APT_Update_Cron now gets correctly added to /etc/cron.hourly when notify-upgrade is installed, instead of /etc/cron.daily.

* Mon 12 Feb 18:37:22 GMT 2018

Using -L and --ignore-root results in admittedly excessive amounts of ERRORs (L0141).

* Fri  2 Feb 15:22:14 GMT 2018

The small lsbins shell program has been moved to miscellaneous; it doesn't really merit having a repository of its own, since it's so small and basic, with little need for any big updates.

If you'd like to install lsbins, or update an existing installation thereof, then please *update* insit beforehand.

* Fri  2 Feb 13:28:57 GMT 2018

Sometimes, while it works as expected, updating insit still yields this result:

```
$ sudo insit -S
File '/usr/bin/insit' downloaded and updated.
File '/usr/bin/insit' ownership re-set.
File '/usr/bin/insit' mode re-set.
File '/usr/share/bash-completion/completions/insit' downloaded and updated.
File '/usr/share/bash-completion/completions/insit' ownership re-set.
File '/usr/share/bash-completion/completions/insit' mode re-set.
/usr/bin/insit: line 227: it: command not found
/usr/bin/insit: line 228: syntax error near unexpected token `fi'
/usr/bin/insit: line 228: `fi'
```

I'm hoping the latest commit(s) will fix this. As a result of this hopefully-a-fix, it'll no longer be possible to update insit _and_ install and/or update something. This will likely be revised at a later date.
