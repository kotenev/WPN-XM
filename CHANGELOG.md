### Introduction

This document is a curated, chronologically ordered list of notable changes for
each version of WPN-XM.

#### 1. Legend for the description of changes

We group changes to describe their impact on the project, as follows:

  - **NEW** for a new feature
  - **CHANGES** for changes in existing functionality
  - **UPDATES** for component updates
  - **DEPRECATED** for once-stable features removed in upcoming releases
  - **REMOVED** for deprecated features removed in this release
  - **FIXES** for any bug fixes
  - **SECURITY** to invite users to upgrade in case of vulnerabilities

#### 2. Template

This is a template for a new release section with a few changes:

```
### Unreleased - YYYY-MM-DD

#### NEW

- added a

#### FIXES

- fixed b

#### CHANGES

- removed c
```

#### 3. Unreleased Section

The "Unreleased" section at the top is for keeping track of current changes.

At release time, its just changed from "Unreleased" to the current version number.

Using the version number as a header allows to use them as links.

A new "Unreleased" section is added, when the next change is added.

## Change Log

### Unreleased

#### NEW

-  added x

#### FIXED

- fixed y

#### CHANGES

- removed z
- a

### v0.8.6 - 2015-08-21

#### FIXES

- component extractions
  * "msysgit/git for windows" extracted to "/bin/git"
  * "gogs" extracted to "/bin/gogs"
  * Imagick extracted to "/bin/imagick"
  * PHP extensions extracted to "/bin/php/ext"

#### CHANGES

- removed xdebug from PHP7 installers. no release, yet.
- switched from "msysgit" to "git for windows"

### v0.8.5 - 2015-07-12

- FIX | installers to stop to inserting global settings into the extension section in php.ini
- CHG | all "Lite Installers" ship "ConEmu"
- FIX | phpext_phalcon download URLs
- FIX | Imagick download URLs
- CHG | switched to Imagick portable zips
- NEW | added "Imagick x64" to "Full Installers x64"
- FIX | removed MoveFiles() from all installers to avoid the folder renaming problem
- FIX | fixed extraction errors of several PHP Extensions and Node
- FIX | default configuration of xdebug from installer
- FIX | fixed paths to the opcache and xdebug in php.ini
- FIX | fixed webinterface cannot redeclare class error
- CHG | removed component "junction"

### v0.8.4 - tba

- FIX | fixed uninstaller to not recursively delete reparse points
- NEW | added redis configuration
- CHG | enabled PHP extensions (by default): mysql, pdo_mysql, pdo_sqlite, sqlite, openssl
- CHG | server control panel is now released with version number

### v0.8.3 - 2015-06-26

- 2015-06-17 | NEW | added vcredist 2015 detection o LiteRC installer for PHP7
- 2015-04-26 | CHG | moved configs into subfolders
                     and updated installers accordingly
- CHG | added "COMPILE_FROM_IDE" define to allow local compiles
- 2015-04-25 | CHG | Removed Debug-Webinstallers and their build tasks
- CHG | added ExecHidden() function to installers
- CHG | moved webgrind config into "/configs/webgrind"
                     and updated installers accordingly
- 2015-04-24 | FIX | fixed another crash of the SCP
                     (when trying to start the not-installed PostgreSQL)
- CHG | use individual php.ini's per PHP version
- 2015-04-23 | NEW | improved SSL pre-configuration (added ca-bundle.crt)
                     set cainfo settings to PHP.ini
- 2015-04-15 | CHG | adjusted batch scripts: replaced %cd% with %~dp0)
                     renamed batch scripts: removed "wpnxm-" prefix
- 2015-03-22 | NEW | added Strawberry Perl x64
- CHG | x64 versions of the Full Installer include Perl x64
| 2015-03-17 | NEW | added RoboMongo
- CHG | dropped RockMongo (it's unmaintained).
- CHG | silent installation of VCREDIST

### v0.8.2 - 2015-03-14

#### FIXES

-  mariadb inital database creation failed
- updated wpn-xm.ini with missing values
- missing openssl.conf
- paths in generate-certificates.bat
- copy additional nginx config examples (domains-disabled)
- mariadb extraction error
- openssl extraction error
- run PERL relocation script hidden
- ampersand UTF-8 problem in the install wizard by using +
- rockmongo is no longer extracted to \bin but to \www\tools

#### CHANGES

-  disable deprecated PHP Extensions php_mysql in default cfg

### v0.8.1 - 2015-03-07

- Will Travis release it?
  - **The gift that he gives to me... No one knows!**
- Using Console mode, without xvfb window.

### v0.8.0 - 2014-09-20

- Renamed Installation Wizards
- There are 4 installation wizard types:
    - webinstaller
    - full (formerly bigpack)
    - standard (formerly allinone)
    - lite
- Installation wizards for multiple PHP versions (including x64):
- Each installation wizards is build for the following PHP versions:
  - PHP 5.4 x86
  - PHP 5.5 x86 & x64
  - PHP 5.6 x86 & x64
- Deployment to Github, Sourceforge and WPN-XM server

### v0.7.0 - 2014-04-12

#### NEW

- google closure comiler
- node, nodenpm,
- redis
- varnish
- php extensions: amqp, wincache, msgpack, varnish

#### FIXES

- WPN-XM SCP (icon bug fix in v0.6.1)

### v0.6.1 - tba

#### CHANGES
-  updated Inno Download Plugin v1.1.0 

### v0.6.0 - 2013-12-19

[cols="2,1,6a", width="80%"]
|===
| 2013-12-18  | FIX | This release adresses several bugs in the Server Control Panel:
                       - console/debugging popup screen removed
                       - daemons not found
                       - daemons not started
                       - logfile not opened, because wrong path
                       - webinterface button not working

|             | NEW | [server control panel]
              - executable has been renamed from "wpnxm-scp.exe" to "wpn-xm.exe"
              - reworked settings classes
              - enabled configuration dialog
              - added RunOnStartup: places SCP in Windows Autostart)
              - added StopDaemonsOnQuit:
                stops all running daemons, when user Quits the SCP in the Tray
              - added RunDaemonsOnStartup with daemon selection:
                starts daemons, when SCP starts
              - enabled all configuration buttons
                they resolve to the webinterface config section
              - splashscreen added
             [wpn-xm.ini]
              - is the global configuration file used by SCP and Webinterface
              - is auto-generated with default settings by the server control panel
              - with defaults settings is also installed with the stack
             [webinterface]
              - runs with embedded PHP server and also with Nginx (default)
              - has start & stop buttons for daemons
|===

### v0.6.4 - 2013-12-02

[cols="2,1,6a", width="80%"]
|===
| 2013-11-30 | NEW | webinterface update to work with embedded PHP server
| 2013-11-09 | NEW | added build tasks
                     prepare-downloads-lite & prepare-downloads-allinone
                     Both move downloads to a specific subfolder.
                     auto-commit-versionized-registries
| 2013-11-07 | CHG | created registry repository
                     switched from updater to registry submodule
| 2013-10-31 | FIX | fixing mariadb issue with missing performance_tables
             | UPD | NSSM v2.16
| 2013-10-30 | CHG | software registry files are now versionized
| 2013-10-28 | NEW | added "wpn-xm-lite-installer-w32"
| 2013-10-25 | CHG | renamed innosetup script files
                     each postfixed with "-w32"
                     new installer "bigpack" which ships everything (perl).
                     removed perl from "allinone"
| 2013-10-21 | NEW | added PostgreSQL
| 2013-10-18 | NEW | added Strawberry Perl, feature request/issue #125
             | UPD | Inno Download Plugin v1.0.1 - due to my bugreport :)
| 2013-10-15 | CHG | switched from InnoTools Downloader to Inno Download Plugin
                     this fixes the https download problems
                     https://github.com/WPN-XM/WPN-XM/issues/114
| 2013-08-26 | FIX | SSL Certificate Paths in Nginx Config
| 2013-07-06 | UPD | InnoSetup v5.5.3
| 2013-04-08 | CHG | renamed wpnxm-scp.exe to server-control-panel.exe
| 2013-04-05 | NEW | "shutdown blocking" process scan during deinstallation
| 2013-03-01 | NEW | Nginx loads Domain Configs from /domains-enabled folder
                     Tweaks to MariaDB settings
|            | FIX | fixed start-menu shortcuts
                     https://github.com/WPN-XM/WPN-XM/issues/89
|===

### v0.5.3 - tba

[cols="2,1,6a", width="80%"]
|===
|             | UPD | - NGINX 1.3.13
                      - PHP 5.4.12
| 2013-02-20  | FIX | dialog "Server processes still running" during uninstall
                      shutdown call was invalid
|             | FIX | removed read-only file permissions from  pthreadGC2.ddl
                      (from /bin/memcached). it was not deleted by uninstall.
|===

### v0.5.2 - 2013-02-18

Some entries are missing here...

[cols="2,1,6a", width="80%"]
|===
|            | CHG | removed debug token completely
|            | NEW | added phpmemcachedadmin
|            | FIX | removed DEBUG token on bootstrap.php
|            | NEW | added build tasks "reset-git-submodules",
                     to reset all APPVERSION token changes in git submodules
|            | NEW | added build tasks "compile-server-control-panel"
                     and "build-server-control-panel"
|            | NEW | added PHP Extension Mongo 1.3.4
| 2013-02-02 | NEW | added RockMongo 1.1.5
                     added version crawler for RockMongo
                     added RockMongo to status, download list and registry
                     added RockMongo to installation wizard
|            | NEW | registry-update add() handles now also single arrays
|            | NEW | MongoDB stripdown script and stripdown build task
| 2013-02-01 | FIX | /logs directory does not exist on startup
                     https://github.com/WPN-XM/WPN-XM/issues/75
|===

### v0.5.1 - 2013-01-21

https://github.com/WPN-XM/WPN-XM/issues?milestone=5&state=closed

[cols="2,1,6a", width="80%"]
|===
| 2013-01-20 | FIX | missing semicolon in nginx.conf
                     missing slash in webinterface/helper/phpini.php
|            | FIX | uninstall abort dialog did not abort
                     https://github.com/WPN-XM/WPN-XM/issues/71
|            | FIX | stripdown script and foldernames with spaces
                     https://github.com/WPN-XM/WPN-XM/issues/70
|            | UPD | updated NANT to v0.92 (2012-06-09)
|            | NEW | issue #74 - build tasks "stripdown-mariadb"
                     building of the AllInOne Installer is now only one-click
|            | UPD | issue #69 - software registry out-of-sync
|===

### v0.5.0 - 2013-01-19

[cols="2,1,6a", width="80%"]
|===
|            | NEW | All-In-One Installer
                     PHP 5.4.11, Nginx 1.3.9, XDebug 2.2.1, MariaDB 5.5.28
                     Adminer 3.6.2, phpMyAdmin 3.5.5, Composer, PEAR,
                     APC 3.1.14, Junction, Memadmin 1.0.12, Memcached 1.4.5,
                     MongoDB 2.2.1, OpenSSL 1.0.1c, XHProf 0.10.3,
                     Fake Sendmail, Webgrind, WPN-XM SCP 0.4.0
| 2012-12-13 | NEW | build tasks for the All-In-One Installation Wizard
|            | FIX | fixed start and stop icon names
| 2012-12-12 | UPD | InnoSetup v5.5.2
|            | REM | removed OpenCandy from Installation Wizard builds
|            | ... | some entries missing...
| 2012-09-22 | NEW | wpn-xm logo SVG :)
|            | NEW | experimental vcredistributable2008 check
| 2012-09-20 | NEW | experimental portable mode
                     (create no registry key and drop uninstallation)
|            | NEW | added additional task to innoscript for
                     creation of start stop desktop icons,
                     scp desktop and quick launch icon
| 2012-09-02 | NEW | enabled php_com_dotnet extensions by default
|===

### v0.4 - 2012-09-01

[cols="2,1,6a", width="80%"]
|===
| 2012-08-31 | CHG | sorted all URLS and FILES in the innoscript
| 2012-08-31 | NEW | handling of phpext_xhprof
|            | NEW | added FAKE-SENDMAIL
| 2012-08-31 | CHG | disabled extensions zeromq (not compat version atm)
| 2012-08-30 | NEW | server-control-panel shutdown already running processes
| 2012-08-23 | CHG | webinterface: fixed repository links
|            | UPD | twitter bootstrap v2.1.0
| 2012-08-13 | CHG | website-wpn-xm.org is own git repository now
                     server-control panel is an git submodule now
                     updater is an own git repository now
| 2012-08-07 | CHG | copy the installation wizard log into the logs folder
| 2012-08-05 | FIX | fastcgi_read_timeout increased for xdebug step debugging
| 2012-08-03 | NEW | added MEMADMIN v1.0.12 - Webinterface for Memcached
| 2012-07-23 | CHG | webinterface is an git submodule now
| 2012-07-16 | NEW | wpnxm-software-registry + get & checkversion script
                     get.php is a redirection script pointing to download urls
                     checkversion uses software registry for version compares
                     wpnxm-software-registry is an auto-updated array of
                     the software components of the stack and their urls
|            | NEW | added twitters bootstrap css framework to enhance css
                     of the webinterface; adjusted some styles
| 2012-07-05 | UPD | Rewrite of Webinterface - using frontcontroller pattern
| 2012-07-03 | UPD | Webinterface Updates - Modal Window for Reset Database PW
| 2012-07-02 | UPD | ADMINER 3.4.0
|            | FIX | CSS, font-sizes, shadows
|            | UPD | innosetup wizard image
|            | NEW | Webinterface > Configuration > Tab (PHP)
                     AJAX PHP.INI Editor
| 2012-06-26 | FIX | PHPMYADMIN default config added
| 2012-06-25 | NEW | Website - added screenshot carousel for feature screens
| 2012-06-24 | NEW | added HOSTS tool and nginx vhost creation script
                     https://github.com/WPN-XM/WPN-XM/pull/31
| 2012-06-20 | NEW | added COMPOSER 1.0 - http://getcomposer.org/
| 2012-06-19 | UPD | PHPMYADMIN 3.5.1
| 2012-06-18 | CHG | removed hardcoded URLs from Innosetup Scripts
                     download URLs point to a header redirection script
                     https://github.com/WPN-XM/WPN-XM/pull/30
| 2012-06-18 | NEW | added icons to config page (php, nginx, mariadb, xdebug)
| 2012-06-18 | FIX | getMariaDBVersion() and switched to mysqli methods
| 2012-06-16 | UPD | PHP 5.4.4
| 2012-06-15 | FIX | build.xml bootstrap.php encoding (read/write token nant)
| 2012-06-15 | FIX | installation wizard - uninstaller now working
|            | NEW | detect running processes before uninstalling
|            | NEW | dialog to warn user about deletion of projects folder
|            | FIX | report icon was fetch from the web
|            | NEW | synced the state (enabled/disabled) of tool pushbuttons
                     in the SCP with the daemon, they rely on (php+nginx)
|===

### v0.3 - 2012-06-11

[cols="2,1,6a", width="80%"]
|===
| 2012-06-11 | NEW | added WPN-XM SCP 0.3.0
| 2012-06-11 | NEW | added base for application settings management to SCP
| 2012-06-08 | UPD | MARIADB 5.5.24 w32
                     Our bugreport about inclusion of debug files was included.
                     The download size of maria.zip decreased from 180 to 130mb.
| 2012-06-08 | FIX | Status led not updated at initial start
                     https://github.com/WPN-XM/WPN-XM/issues/20
| 2012-06-05 | UPD | NGINX 1.2.1
| 2012-06-05 | NEW | php is added to environment variable PATH
| 2012-06-04 | FIX | fixed cfg edit order: config files are copied, then modified
| 2012-06-04 | FIX | installations seems stuck, while extraction of zip files
                     added two progressbars showing total progess and component
| 2012-06-01 | UPD | InnoSetup 5.5.0
| 2012-05-11 | UPD | PHP 5.4.3
                     APC 3.1.10-5.4
| 2012-05-07 | UPD | PHP 5.4.2
             | NEW | using stamped icon in installation wizard
| 2012-04-25 | FIX | renamed go-pear.php to go-pear.phar
             | NEW | added go-pear.bat to startfiles
             | NEW | added reset-db-pw.bat to startfiles
             | UPD | merged my-medium.ini of MariaDB 5.5.23 into /configs/my.ini
             | UPD | bumped version numbers on website
             | UPD | added PEAR to wizard images and WPN-XM string to icon
             | NEW | added wpn-xm debug.iss for building a debug executable
                     added build task "compile-wpnxm-debug-setup"
| 2012-04-24 | UPD | NGINX 1.2.0
                     PHP 5.4.0
                     MARIADB 5.5.23
                     XDEBUG 2.2.0RC2
| 2012-04-19 | FIX | download link to junctions was broken (case-sensitive)
             | NEW | added opencandy
             | FIX | charset problems
                     downgraded to Innosetup 5.4.3 non-unicode
                     used PChar instead of PAnsiChar in innotools downloader
             | FIX | user projects were not listed in the projects panel
             | NEW | added installation wizard images
             | FIX | renamed var Filename_zeromq to Filename_phpext_zeromq
             | NEW | added versioning of webinterface during build process
             | CHG | updated webinterface menu accordingly
| 2012-04-18 | NEW | added PEAR (go-pear.phar) to the stack
| 2012-04-16 | NEW | added Adminer 3.4.4 - Database management in one file
| 2012-04-14 | NEW | added twitter profile images to /resources dir
| 2012-04-09 | UPD | Logo
| 2012-03-12 | UPD | readme, website to reflect the ZeroMQ php/ext arrival
             | NEW | PHP Extension for ZeroMQ v2.1
|===

### v0.2 - 2012-02-06

[cols="2,1,6a", width="80%"]
|===
| 2012-02-06 | UPD | updated components:
                      - NGINX 1.1.11
                      - PHP 5.3.10
                      - MARIADB 5.3.3-rc
                      - XDEBUG 2.1.3
                      - PHPMYADMIN 3.4.9
| 2012-02-04 | NEW | added OpenCandy Ads to one version of the wizard
| 2012-01-22 | NEW | added comments with links to nant & inno setup help
             | CHG | build.xml: build directory is now "_build"
             | NEW | ISS: define wizard application title and tray message
             | NEW | ISS: added SetupLogging and logfile copying to app dir
             | NEW | ISS: added bug url to start menu folder
| 2012-01-21 | CHG | updated InnoToolsDownloader to be unicode compatible
             | NEW | added Mircosoft's junction tool for creation of symlinks
| 2012-01-17 | CHG | webinterface
                     fixed centering bugs while displaying phpinfo
                     removed menu.php, welcome.phpin favor of htmlelements.php
             | NEW | display counter for welcome message in webinterface
             | CHG | gitignore - ignores now QT and build folders
             | NEW | NANT build process automation complete
             | CHG | build.xml
                     added build command clean-builddir
                     added build command update-iss-files
                     added build command compile-wpnxm-setup
             | UPD | PHP 5.3.9
             | NEW | added build.xml - the nant buildfile
             | NEW | added build.bat - call to nant injecting the buildfile
             | NEW | added NANT 0.91 to /bin/nant for build process automation
             | NEW | added Inno Setup 5.4.3 Unicode to /bin/innosetup
             | CHG | cleanups
                     moved batch build file to /bin/build-old.bat
                     moved setup.ico to /bin/icons folder
                     moved iss files from toplevel to /innosetup folder
| 2012-01-16 | FIX | - "set PHPRC" is not working
                     - start-wpnxm.bat now changes into the php directory to find the php extensions
|            | CHG | - phpMyAdmin 3.4.8
                     - NGINX 1.1.10
|            | NEW | link for immediate redirection
| 2011-12-07 | CHG | renamed severpack to server stack
|===

### v0.1 - 2011-11-12

#### NEW

- created and set up website wpn-xm.org
- selected components for the server stack:
   * PHP 5.3.8
   * NGINX 1.1.7
   * XDebug 2.1.2 (PHP Extension)
   * MariaDB 5.3.2-beta
   * phpMyAdmin 3.4.6-english
   * Memcached 1.4.5
   * memcached (PHP Extension)
   * Webgrind
   * Xhprof
   * APC (PHP Extension)
- created base for wpn-xm server control tray application
- created base for wpn-xm webinterface
- two ISS files, for standalone and for bundled distribution
- layed out a directory structure for the project