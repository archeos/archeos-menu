Quick howto
===========


Some notes to correctly create menu entries:

For each archeos application that need to go into the "ArcheOS" submenu, the following items must be created:

* An icon (PNG, 64x64px) into `menu-icons/64x64/apps/`
* (Optional) a svg vector icon into `menu-icons/scalable/`
* A desktop entry into `deskop-files/`. Use the `test.desktop` file as template.
   * The **Category** entry must correspond to a category used in the menu. See the `menus/archeos-applications.menu` for the complete list of categories (eg. **Category=05-cad-applications;**)
   * Multiple categories can be assigned using the `;` separator.
   * The **Icon** entry must exists somewhere into `/usr/share/icons` or must be inserted into the `menu-icons/64x64/apps/` folder.
             
To add a new submenu:
             
* Add a new `<Menuname> ... </Menuname>` like the others into the `<Layout>` section into `menus/archeos-applications.menu` file (see others).
* Add a new `<Menu> ... </Menu>` stanza into `menus/archeos-applications.menu` similar to the other. 
   * The `<Directory> ... </Directory>` tag must contain the filename of the desktop entry (see below)
   * The `<Include> ... </Include>` tag must contain a list of categories that applications files (see above) must contain. If no applications contains this category the menu **will not be displayed**.
* Add a new `.directory` file into `desktop-directories/` like the other ones
* The **Type** entry must be **Directory**
* The **Icon** entry must exists somewhere into `/usr/share/icons` or must be inserted into the `menu-icons/64x64/apps/` folder (see above).

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
