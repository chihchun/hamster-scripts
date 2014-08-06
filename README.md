
# Utils for Hamster - The Gnome Time Tracker

[hamster](http://projecthamster.wordpress.com/) is one the best time tracking tool on Ubuntu/Linux desktop. 

I use hamster for years, the current database is from 2009, it still works great! This repository hosted several scripts I used to tracking how much time I spent on projects and tasks. 

* [Launchpad](http://launchpad.net/)
* [Redmine](http://www.redmine.org/)
* [zim](http://zim-wiki.org/)

These scripts will retrieve the project name from the issue system, and pass the issue title into hamster via dbus.  It would be easy for later to review how much time it cost for a project or a task. You can setup a project list in *${HOME}/.config/hamster-projects.yaml* The [yaml](http://www.yaml.org/) file includes the keyword and activity/category mapping list.

It looks like

    keyboard: activity
    zim: hacking
    vim: hacking
    hamster: hacking
    openstreetmap: openstreetmap
    basecamp: openstreetmap
    canonical: Canonical
    ubuntu: Canonical
    g0v: g0v
    opendata: g0v

## Launchpad

    Usage: hamster-launchpad issue_num

The script will use project name as keyword and use issue id as tag.

## Redmine

    Usage: hamster-redmine issue_num

Please setup your hostname and credential into the script (it's hardcoded). The script will use project name as keyword, issue id as tag.

## zim

The zim script works as [custom tools](http://zim-wiki.org/manual/Help/Custom_Tools.html). Please add following settings into zim custom tool list

    ${bin}/hamster-zim %s %t

After you add it into the zim, please select any text in your note and click from the menm item. This setting will pass real page source and selected text, and try to find the related activity from it's folder name. For example, if you have a zim note named 'openstreetmap/mapping/ChinaGreatWall.txt', if will travel the filename, and partner folders to find the matched activity. In my settings, it will be mapped to openstreetmap.

