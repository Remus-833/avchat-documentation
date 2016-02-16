---
layout: default
title: AVChat Module for Drupal 7
description: The documentation for the AVChat module for Drupal.
isHome: false
hide: true
---

<section class="bs-docs-section" markdown="1">
  <h1 id="overview" class="page-header">Overview</h1>
  <p class="lead">The AVChat Module for Drupal 7 handles the integration between a Drupal 7 web site and the AVChat video chat software.</p>

  If you're looking for something specific just hit <kbd>Ctrl+F</kbd> on your browser.
</section>

<section class="bs-docs-section" markdown="1">
  <h1 id="installation-instructions" class="page-header">Installation Instructions</h1>
<h2 id="installing-the-module">Download & extract archives</h2>
Download these 2 archives from your [private client/trial area](https://nusofthq.com/c/) to your computer:

1. `AVChat 3.0.zip` contains AVChat
2. `avchat3_drupal_modules.zip` contains the Drupal modules

Extract the 2 archives somewhere on your computer.

<h2 id="installing-the-module">Media Server Application</h2>
Once we've downloaded everything the 1st thing we need to do is to setup the media server app to which AVChat will connect to.

AVChat uses a media server to send all the audio video and text data between users. AVChat supports the 3 major media servers:

* Red5
* Adobe Media Server
* Wowza

Here's how to install the `avchat30` app on each one of them:

{% include media-server-app.md %}

<h2 id="installing-the-module">Module & AVChat installation</h2>
Connect using an FTP client to your website and:

1. upload the `avchat3` folder from `avchat3_drupal_modules.zip/drupal7.x_module` to `/sites/all/modules/`
2. upload the contents of the `Files to upload to your web site` folder from  the AVChat archive to `/sites/all/modules/avchat3/`

<div class="bs-callout bs-callout-info" id="callout-tables-responsive-overflow"> <h4>Folder permissions</h4> <p markdown="1">If your website's hosted on a Linux server CHMOD the `uploadedFiles` and `tokens` folders to 777.</p> </div>

Edit `/sites/default/settings.php` and search for `# $cookie_domain = '.example.com';` (line 340 on Drupal 7.42).
Remove the `#` sign and replace `.example.com` with your domain name. Save.

After making the change the file should look like this:
<pre>
/**
 * Drupal automatically generates a unique session cookie name for each site
 * based on its full domain name. If you have multiple domains pointing at the
 * same Drupal site, you can either redirect them all to a single domain (see
 * comment in .htaccess), or uncomment the line below and specify their shared
 * base domain. Doing so assures that users remain logged in as they cross
 * between your various domains. Make sure to always start the $cookie_domain
 * with a leading dot, as per RFC 2109.
 */
$cookie_domain = 'yourwebsite.com';
</pre>

<h2 id="installing-the-module">Complete installation</h2>
Now open your Drupal's admin area in a web browser, click on `Modules` in the top menu and scroll down to the `CHAT` section where you need to enable the new `AVChat3` module by clicking the empty checkbox at the left of it and then on <kbd>[Save Configuration]</kbd>.

Two new menu items will show up in your Drupal menus:

* `Flash Video Chat` in the main menu
* `AVChat 3 Module Settings` in the top admin menu

Click on `AVChat 3 Module Settings`, a list of AVChat 3 settings will show up including the `RTMP Connectionstring` field.

Set it to the connection string for your new media server app like this:

* `rtmp://media-server-ip/avchat30/_definst_`

scroll to the bottom and press <kbd>Save configuration</kbd>.

Now close the Modules modal and click on `Flash Video Chat` link in the main menu to open the page with AVChat on it. The pre-filled AVChat login screen will show up, click `[Connect]`. AVChat will now connect to the media server and ask you for the license key.

Enter the key (It's in your [private client/trial area](https://nusofthq.com/c/)) and press `[Submit]`.


<div class="bs-callout bs-callout-info" id="callout-tables-responsive-overflow"> <h4>Deep integration</h4> <p markdown="1">When accessing AVChat logged in to the website the user name in the AVChat login section will be automatically filled with your Drupal username. If the user role you belong to has the permission to access AVChat 3 as admin, the admin interface of AVChat 3 will be loaded.</p> </div>
</section>


<section class="bs-docs-section" markdown="1">
  <h1 id="installation-instructions" class="page-header">Module Features</h1>
  <h2 id="accessing-the-avchat-admin-area">Access the AVChat admin area</h2>
The AVChat admin interface allows you to kick and ban users, view private discussions, log in as hidden, close, open and delete rooms, change the license key, etc. .

To give other people access to the AVChat admin interface do the following:

1. Go to `Modules -> AVChat3` (it's in the CHAT section at the bottom)
2. Click on the `Permissions` link to the right
3. Tick the checkboxes for the roles you want to give access to in the `Allow this user role to access the chat as admins` line.
4. Scroll to the bottom and click <kbd>Save permissions</kbd>

Unce a user has access to the admin area of AVChat he just has to log in your website and click on the `Flash Video Chat` link. AVChat's admin interface is automatically loaded.

<h2 id="open-avchat-in-a-popup-window">Open AVChat in a pop up</h2>

You might want AVChat to open in a pop up window to make it easier for your users to browse your website while in the chat.

1. In the top admin menu click on `AVChat 3 Module Settings`
2. In the `Chat will open` section check the `In popup` option
4. Scroll to the bottom and click <kbd>Save configuration</kbd>

  <h2 id="permissions">Limiting features to certain user roles</h2>
  By default Drupal 7 comes with 3 user roles:

  * *anonymous users* or visitors
  * *authenticated users* or logged in users
  * *administrator*

On top of that you can add your own custom user roles from `People -> PERMISSIONS -> Roles`.
<h3>Limiting AVChat features</h3>

To control what AVChat features (creating rooms, sending PM's, viewing webcams, etc.) are available to each user role go to the Permissions page `Admin Menu -> People -> Permissions` .

All user roles will be shown horizontally while all the AVChat features you can turn on and off will be shown vertically.

<h2 id="location-of-avchat-files">Allowing visitors to enter AVChat</h2>
1. Go to `Modules -> AVChat3` (it's in the CHAT section at the bottom)
2. Click on the `Permissions` link to the right
3. Tick the checkbox for the ANONYMOUS USER role in the `Allow this user role to access the chat as admins` line.
4. Scroll to the bottom and click <kbd>Save permissions</kbd>


<h2 id="location-of-avchat-files">Location of AVChat files</h2>
All the AVChat  files including:

* all the module files
* index.swf and admin.swf
* language files
* audio/video quality profile files
* avc_settings.xml


are located in `sites/all/modules/avchat3`.

<h2 id="location-of-avchat-files">GPL License</h2>
The AVChat Module for Drupal is licensed under the GNU General Public License, version 2.

Once you purchase the module you can modify it and distribute it as long as you keep it under the GPL.

We are not affiliated with or endorsed by the Drupal Project or its trademark owners.
</section>
