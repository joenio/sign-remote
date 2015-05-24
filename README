sign-remote - sign files remotely
=================================

Script to sign files remotely using GNUPG, the main goal is to sign `Release`
files, the `Release` file is part of any Debian Repository Packages and it
should be signed to avoid complaints about the secure of packages. Example of
use:

     $ sign-remote p.deb.org:~/html/debian/zack/Release

The commom way to use this is in conjunction with `dput` as a hook, take a
look in a examples of dput configuration:

     [p.deb.org]
     fqdn = p.deb.org
     method = scp
     login = *
     incoming = /home/zack/html/debian/mini-dinstall/incoming
     post_upload_command = ssh p.deb.org "mini-dinstall -b" && sign-remote p.deb.org:~/html/debian/zack/Release

In the example above dput will run `sign-remote` to sign the `Release` file
every time that a package is uploaded to the Debian Repository.

AUTHOR
------

Joenio Costa <joenio@colivre.coop.br>

ORIGINAL AUTHOR
---------------

Stefano Zacchiroli <zack@upsilon.cc>
