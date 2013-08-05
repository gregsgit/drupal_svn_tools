drupal_svn_tools
================

Some bash scripts to update drupal in a svn friendly way.
As a rule, these scripts do _not_ actually do a 'svn commit' - that is is left to you.

In the following, suppose this set of utilities is in ~/tools/ and your drupal install is in ~/public_html

update-module
-------------

To update the source for an already-installed drupal module,

1. download the .tgz of the updated drupal into ~/module-updates (or some such named folder, not under your drupal
install). Let's call the module foo and the file foo-123.tgz
2. cd ~/module-updates. tar xzf foo-123.tgz . This creates a subfolder 'foo'.
3. cd ~/tools
4. ./update-module ~/module-updates/foo ~/public_html 
5. if all looks good, cd ~/public_html and 'svn commit'.


add-unknown
-----------

cd to folder below which may contain some files not yet under svn control.
do
  ~/tools/add-unknown

You will be prompted with a list of files the script finds (using 'svn status' piped through grep).
If this set of files looks good to you, hit <enter> and 'svn add' will be called on each file.

