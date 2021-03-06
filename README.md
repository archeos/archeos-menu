archeos-menu
============

![build-status](http://build.archeos.eu/badge.png?builder=archeos-menu)

This package contains files and script to build the archeos-menu under
Gnome/XFCE/KDE/...

Use `git-buildpackage` as usual to build the package.

For documentation see: http://doc.archeos.eu/development/menu.html

Original readme (from Kali Linux menu package)
==============================================

Providing Kali specific desktop files
-------------------------------------

You can add as many desktop files as you want in the desktop-files
sub-directory. Each desktop file must have an entry "X-Kali-Package=foo"
where foo is the name of the binary package that is associated to this
desktop file. Note that you can associate multiple binary packages to
the same desktop file if needed, just put a space-separated list of
packages in the X-Kali-Package field.

Those desktop files will be installed in /usr/share/applications
by update-kali-menu as soon as the corresponding package is installed. And
they will be removed afer the corresponding package has been removed.

If you want to override an existing desktop file instead of adding a new
one, make sure to reuse the same filename. When kali-menu detects the
conflict, it will transparently use dpkg-divert to move away the official
desktop file and put the Kali one in place.

It's possible to remove/hide an existing desktop file, by overriding it and
adding "NoDisplay=true" to the overridden desktop file.

-- Raphaël Hertzog <raphael@freexian.com>
