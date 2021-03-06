
<h2 id="enable-token-authentication">How to turn on token based authentication in AVChat</h2>


Starting with [build 900](http://avchat.net/blog/the-avchat-3-build-for-september-896/), AVChat 3 introduces a new security feature called **token based authentication**.

When enabled this feature prevents 3'rd party swf files (hosted on other web sites than your own or by malicious users) to connect to your media server. There are other security measures in place to prevent this, however, token based authentication is the most secure.

This feature is turned off by default because with it enabled:

* we can't make it work out of the box, it needs to be configured manually
* it takes slightly more time for users to connect to the media server

{% highlight xml %}
<watermarkForOtherPeoplesStreams>
  <title>watermarkForOtherPeoplesStreams</title>
  <name>Watermark for other people streams</name>
  <type>string</type>
  <desc>path to a png, gif or jpeg file to show over other peoples cameras, this feature has been introduced for blocking users from rebroadcasting other peoples stream using screen sharing software. Use this to put your logo over the video streams.</desc>
  <default>fullStar.png</default>
  <value>fullStar.png</value>
</watermarkForOtherPeoplesStreams>
{% endhighlight %}

### How to enable it

Once you have AVChat installed, enabling this feature is simple:

1. Edit the settings file on the media server:
  * on Red5 its `Red5/webapps/avchat30/avchat3.properties`
  * on Wowza its `Wowza/conf/avchat30/avchat3.properties`
  * on AMS its `AMS/applications/avchat30/settings.asc`
2. Set the value of the `tokenUrlLocation` variable to the absolute url/path to `token_verify.php` (`token_verify.php` is located in the AVChat installation folder on your webserver). Good example: http://avchat.net/demos/av30/token_verify.php . If your AVChat installation uses ASPX instead of PHP put the path to `token_verify.aspx` instead.
3. Restart the media server.



<h2 id="protection-against-rebroadcasting">Protection against video streams being rebroadcasted (watermarking)</h2>



Some of our clients had issues with users joining their video chat rooms and re-broadcasting streams to other sites using screen sharing software.

To protect against that we ended up putting the logo of our client (a watermark) over all the video streams.

By default AVChat uses a little star (`fullStar.png`). You can view it in our AVChat demo and on your (default) installation. To change the star with your own logo edit `avc_settings.xml` and change the value of the `watermarkForOtherPeoplesStreams` xml tag.

The watermark will be added to the top left of all the video streams.


<h2 id="rtmps-and-rtmpe">RTMPS and RTMPE for encrypted communications</h2>


AVChat supports both RTMPS and RTMPE for encrypted data transfer between the users and the media server but depending on your media server you can use one or both:

* Red5 supports only RTMPS
* AMS and Wowza support both RTMPS and RTMPE

To enable RTMPS or RTMPE check with your media server documentation. We can also enable it for you through the AVChat Securitization service.


<h2 id="enable-swf-verification">Enabling SWF Verification on AMS</h2>


Adobe Media Server, starting with Flash Media Server 3, has this very cool security feature called *SWF Verification* where you can tell it to only accept connections from known swf files. How does he know the swf files? Well... you upload them to the AMS server. Simple and brilliant!

This feature can protect you from custom made swf files attempting to connect to your media server. Together with token based authentication it would make the most secure setup someone can wish for.

To to turn it on you need to do two things:

* First, change the `<SWFVerification enabled="false">` to `"true"` in your `applications/avchat30/Application.xml` file to turn on the feature.
* Create a new folder: `applications/avchat30/SWFs` and put the `index.swf` and `admin.swf` with which AVChat ships.
* Having changed the server configuration, you are going to need to restart your media server.

If you're passionate about this stuff there's a more detailed article explaining SWF Verification in more depth on the adobe.com web site: [adobe.com/devnet/flashmediaserver/articles/](http://www.adobe.com/devnet/flashmediaserver/articles/beginner_security_fms3.html)

Unfortunately SWF Verification is only available with FMS3 or later. Red5 and Wowza do not have this feature.


<h2 id="limiting-ips-for-admins">Limiting IPs from which admins can connect and execute admin functions</h2>


Because we give free trials to just about anyone, our script gets into a lot of hands, some of them are not well intended.

One of the easiest ways to protect your AVChat from malicious users is to limit the ip's from which admins can connect through the admin interface (`admin.swf`) and execute admin functions.

You just have to edit the settings file on the media server:

* on Red5 its `Red5/webapps/avchat30/avchat3.properties`
* on Wowza its `Wowza/conf/avchat30/avchat3.properties`
* on AMS its `AMS/applications/avchat30/settings.asc`

And search for the `adminsAllowedFromTheseIps` variable. Set its value to your IP or to the range of IPs from which admins will be allowed to connect.

Starting with build 1144 the verification is done every time an admin executes an admin function (kick, ban, change license key, etc.) not just on connection.

<div class="alert alert-info" role="alert">There are more comments in the above mentioned settings files that will explain exactly how to add individual ips and ip ranges. After editing those files don't forget to restart the media server.</div>


<h2 id="allowing-localhost-connections">Allowing connections from AVChat files installed on localhost</h2>


Because of security reasons you can not connect to the `avchat30` application on the media server with AVChat client side files (html/swf) hosted on `localhost`. When you try to do that you will get a connection error.

To allow connections from AVChat installed on `localhost` you need to edit the settings file on the media server:

* on Red5 its `Red5/webapps/avchat30/avchat3.properties`
* on Wowza its `Wowza/conf/avchat30/avchat3.properties`
* on AMS its `AMS/applications/avchat30/settings.asc`

And search for the `allowLocalhostConnections` variable. Set it to `true` and restart the media server.

<h2 id="manually-removing-banned-ips-file">Manually removing the banned IPs file</h2>

If you've banned yourself (by ip or username) out of the video chat you will need to manually delete the banned IPs and usernames file and restart the media server.

**Red5**

Delete the `bannedips.red5` and `bannedusernames.red5` files from the following folder:

 * Red5 0.8: `Red5/webapps/avchat30/persistence/SharedObject/_definst_`
 * Red 1.0.5: `Red5/webapps/avchat30/persistence/persistence/SHARED_OBJECT/avchat30/_definst_`

**Adobe Media Server**

Delete the `bannedips.fso` and `bannedusernames.fso` files from `AMS/applications/avchat30/sharedobjects/_definst_`.

**Wowza**

Delete the `bannedips.rso` and `bannedusernames.rso` files from `Wowza/applications/avchat30/sharedobjects/_definst_`.
