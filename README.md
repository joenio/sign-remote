sign-remote - sign files remotely
=================================

Script to sign files remotely using `GnuPG`, the main goal of this script is
to sign `Release` files, this file is part of the structure of [Debian
Repositories][repository-format] and should be signed to avoid warnings about
packages authentication. Example of use:

     $ sign-remote p.deb.org:~/debian/Release

The common way of use is together with `dput` as a hook, take a look in an
example of dput's configuration:

     [p.deb.org]
     fqdn = p.deb.org
     method = scp
     login = *
     incoming = /home/debian/mini-dinstall/incoming
     post_upload_command = ssh p.deb.org "mini-dinstall -b" && sign-remote p.deb.org:~/debian/Release

In the example above `dput` will run `sign-remote` to sign the `Release` file
every time that a package is uploaded to the `Debian Repository`.

[repository-format]: https://wiki.debian.org/RepositoryFormat

AUTHOR
------

Joenio Costa <joenio@colivre.coop.br>

ORIGINAL AUTHOR
---------------

Stefano Zacchiroli <zack@upsilon.cc>
