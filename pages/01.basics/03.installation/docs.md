---
title: Installation
taxonomy:
    category: docs
---

Installation of Grav is a trivial process. In fact, there is no real installation.  You have **two** options for installing Grav.  The first, and simplicity way is simply grab the **zip**, the other way is to install the source from **GitHub** and run a command to install dependencies:

## Option 1: Install with ZIP package

The easiest way to install Grav is to use the ZIP package and install it:

1. Download the latest-and-greatest **Grav Base** package from the [Downloads][downloads]
2. Extract the ZIP file in your [webroot][webroot] of your web server, e.g. `~/webroot/grav`

>>>> If you downloaded the ZIP file and then plan to move it to your webroot, please move the **ENTIRE FOLDER** because it contains several hidden files (such as .htaccess) that will not be selected by default. The omission of these hidden files can cause problems when running Grav.

## Option 2: Install from GitHub

The alternative method is to install Grav from the GitHub repository and then run a simple dependency installation script:

1. Clone the Grav repository from [GitHub](https://github.com/getgrav/grav) to a folder in the webroot of your server, e.g. `~/webroot/grav`. Launch a **terminal** or **console** and navigate to the webroot folder:
   ```
   $ cd ~/webroot
   $ git clone https://github.com/getgrav/grav.git
   ```

2. Install the **plugin** and **theme dependencies** by using the [Grav CLI application][grav-cli] `bin/grav`:
   ```
   $ cd ~/webroot/grav
   $ bin/grav install
   ```

   This will automatically **clone** the required dependencies from GitHub directly into this Grav installation.

## Webserver

#### Apache/IIS/Nginx

Using Grav with a web server such as Apache, IIS, or Nginx is as simple as extracting Grav into a folder under the [webroot][webroot]. All it requires to function is PHP 5.4 or higher, so you should make sure that your server instance meets that requirement. More information about Grav requirements can be found in the [requirements](requirements) chapter of this guide.

If your web root is, for example, `~/public_html` then you could extract it into this folder and reach it via `http://localhost`.  If you extracted it into `~/public_html/grav` you would reach it via `http://localhost/grav`.

##### PHP's built-in Web Server

Grav is incredibly easy to set up and get running. You can do this without even installing or configuring a web server!  Be sure you have at least PHP version 5.4 by going to the terminal and typing:

```bash
$ php -v
```

This should report the version and build information.  For example:

```bash
PHP 5.4.24 (cli) (built: Jan 19 2014 21:32:15)
Copyright (c) 1997-2013 The PHP Group
Zend Engine v2.4.0, Copyright (c) 1998-2013 Zend Technologies
```


To try Grav, simply navigate to the folder where you extracted your **Grav Base** package file in your terminal and type:

```bash
$ php -S localhost:8000
```

This runs the built-in PHP web server.  Then, point your browser to `http://localhost:8000` and you should see your Grav site.

>>>> Using the built-in PHP web server is not intended for production environments.  It is intended for development environments only.

## Successful Installation

The first time it loads, there is some compilation happening. Refresh your browser and you will get a faster, cached version.

![Grav Installed](install.png?cropResize=600,600)  {.border}

>>> In the previous examples, **$** represents the command prompt.  This may look different on various platforms.

By default, Grav comes with some sample pages to give you something to get started with.  Your site is already fully functional and you can configure it, add content, extend it, or customize it as much as you like.

## Installation & Setup Problems

If any issues are discovered during the initial page load (or after a cache-flush event) you may see an error page:

![Grav with Problems](problems.png?cropResize=600,600)  {.border}

Please consult the [Troubleshooting](../troubleshooting) section for help regarding specific issues.

## Grav Updates

We plan on providing an improved update solution including **automatic updates** via the upcoming **Admin Panel** plugin - as well as updating via the [Grav CLI Application][grav-cli].  Until then, you should download the [Update Package][update] from our [Downloads section][downloads].

You can extract the update package over the top of your existing Grav installation and it will copy over any updates in the `core system folder`.

After having copied over the files it is a good idea to also update the vendors. You can do so by running the command `composer update` from the root of your Grav instance.

[downloads]: http://getgrav.org/downloads
[webroot]: https://www.wordnik.com/words/webroot
[update]: http://getgrav.org/downloads
[grav-cli]: ../advanced/grav-cli
