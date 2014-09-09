SCRATCH
=======

   * Into menus/archeos-applications.menu there is the applications 
   menu layout
   * The <Directory> entries must have a corresponding .directory entry 
   into the desktop-directories folder.
   * The <Category> tags are associated with categories into the 
   desktop-files/* files (TO BE CHECKED)
   * In the *.directory files is specified an icon. This should exist
   into menu-icons/ folder

Original readme
===============

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
