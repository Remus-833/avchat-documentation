---
layout: default
title: Home
description: Simple documentation template for Github pages
isHome: true
---

<section class="bs-docs-section">
  <h1 id="overview" class="page-header">Overview</h1>

  <blockquote>
    All the AVChat Standalone documentation is on this page.
  </blockquote>

  <h3 id="features">Features</h3>

  <ul>
    <li>Responsive Bootstrap theme</li>
    <li>Automatic syntax highlight</li>
    <li>Multi-page</li>
    <li>Automatic menu</li>
    <li>Configurable additional links</li>
    <li>Github counters</li>
    <li>Twitter &amp; Facebook buttons</li>
  </ul>

  <h3 id="examples">Examples</h3>

  <ul>
    <li><a href="http://mistic100.github.io/jQuery-highlightTextarea/">jQuery highlightTextarea</a></li>
    <li><a href="http://mistic100.github.io/angular-smilies">AngularJS Smilies</a></li>
    <li><a href="http://mistic100.github.io/jQuery-QueryBuilder">jQuery QueryBuilder</a></li>
    <li><a href="http://mistic100.github.io/Bootstrap-Confirmation/">Bootstrap Confirmation</a></li>
  </ul>
</section>


<section class="bs-docs-section">
  <h1 id="installation" class="page-header">Installation Instructions</h1>
  <h2 id="install-avchat">Standalone Installation</h2>
  {% include standalone.md %}

  <h2 id="switch-to-aspx">Switch to ASPX/.NET</h2>
  <p>Adapt the <code>_config.yml</code> file to your project.</p>

{% highlight text %}
apt-get install ruby ruby-dev
gem install bundler
git clone git://github.com/mistic100/jekyll-bootstrap-doc
bundle install
bundle exec jekyll serve
{% endhighlight %}

  <h2 id="change-license-key">Changing the license key</h2>
  <p>Adapt the <code>_config.yml</code> file to your project.</p>
  <h2 id="reset-license-key">Resetting the license key</h2>
  <p>Adapt the <code>_config.yml</code> file to your project.</p>
  <h2 id="switch-trial-to-purchased">Switching from trial to non trial</h2>
  <p>If you have a trial version of AVChat installed and purchased a licensed version, switching to production is very easy:</p>

<ol>
<li>Download the licensed version of AVChat</li>
<li>Extract the archive</li>
<li>Copy and replace <code>index.swf</code> and <code>admin.swf</code> from the extracted archive to your trial AVChat installation folder.</li>
</ol>
</p>
  <h2 id="mobile">Installing the mobile version</h2>
  <h3>AVChat 3.6 and newer</h3>
  <p>Starting with AVChat 3.6 the mobile version of AVChat only works on Red5 1.0.5 and up. The new mobile HTML 5 client introduced in AVChat 3.6 uses WebSockets to communicate and Red5 is the only media server supporting this technology.</p>
  <p>Here's how to set it up:</p>
  <p>On the media server/Red5:</p>
  <ol>
    <li>Download Json-smart library from here and put in the <code>Red5/libs</code> folder</li>
    <li>Open <code>Red5/conf/red5.properties</code></li>
    <li>Search for the <code># WebSocket section</code>.</li>
    <li>Change the <code>ws.host</code> variable and replace the default value <code>0.0.0.0</code> with your media server's IP address</li>
    <li>Save and restart Red5</li>
  </ol>
  <p>On the webserver:</p>
  <ol>
    <li>Download the mobile archive from your private client area at https://nusofthq.com</li>
    <li>Unzip and copy the <code>ws</code> folder to your AVChat installation directory.</li>
  </ol>
  <h3>AVChat 3.5 and older</h3>

 {% include content.md %}

  <h2 id="multiple-installation">Multiple Installations</h2>
  <h3>Multiple apps</h3>
  <p>Adapt the <code>_config.yml</code> file to your project.</p>
  <div class="table-responsive">
    <table class="table table-bordered table-striped">
      <thead>
        <tr>
          <th style="width: 130px;">Name</th>
          <th>description</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>name</td>
          <td>Name of the project.</td>
        </tr>
        <tr>
          <td>version</td>
          <td>Current version of the project</td>
        </tr>
        <tr>
          <td>downloadUrl</td>
          <td>URL of the download button</td>
        </tr>
        <tr>
          <td>license</td>
          <td>License of the project</td>
        </tr>
        <tr>
          <td>licenseUrl</td>
          <td>URL of the license text</td>
        </tr>
        <tr>
          <td>headerLinks</td>
          <td>List of links to display on the right of the top menu. Each item must contain <code>title</code> and <code>url</code> keys</td>
        </tr>
        <tr>
          <td>footerLinks</td>
          <td>List of links to display on the bottom of the page. Each item must contain <code>title</code> and <code>url</code> keys</td>
        </tr>
        <tr>
          <td>header</td>
          <td>Configuration of the header, two colors gradient and boolean to activate or deactivate <a href="http://qrohlf.com/trianglify/">Trianglify</a> generator</td>
        </tr>
        <tr>
          <td>analytics</td>
          <td>Google analytics identifiers. Provide <code>account</code> and <code>domain</code> or leave empty to deactivate</td>
        </tr>
      </tbody>
    </table>
  </div>

  <h3>Multiple instances of the same app</h3>
  <p>Adapt the <code>_config.yml</code> file to your project.</p>
  <div class="table-responsive">
    <table class="table table-bordered table-striped">
      <thead>
        <tr>
          <th style="width: 130px;">Name</th>
          <th>description</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>githubButton</td>
          <td>Data used to generate <a href="http://ghbtns.com/">GitHub Buttons</a>. Provide <code>user</code> and <code>repo</code></td>
        </tr>
        <tr>
          <td>twitter.enabled</td>
          <td>Enable or disable Twitter "Tweet" button</td>
        </tr>
        <tr>
          <td>twitter.via</td>
          <td>Account linked to "Tweet" button</td>
        </tr>
        <tr>
          <td>twitter.hash</td>
          <td>Default hashtags for the "Tweet" button</td>
        </tr>
        <tr>
          <td>twitter.account</td>
          <td>Account for Twitter "Follow" button. Leave empty to deactivate</td>
        </tr>
        <tr>
          <td>facebook.enabled</td>
          <td>Enable or disable Facebook "Like" &amp; "Share" buttons</td>
        </tr>
        <tr>
          <td>facebook.profileUrl</td>
          <td>Profile for Facebook "Follow" button. Leave empty to deactivate</td>
        </tr>
      </tbody>
    </table>
  </div>
</section>


<section class="bs-docs-section">
  <h1 id="usage" class="page-header">Design</h1>

  <h2 id="pages">Background color</h2>
  <p>The main page is the <code>index.html</code> file. You can also add additional pages by creating <code>.html</code> files in the root folder or in any sub-folder. Each page file must begins with a template declaration:</p>

{% highlight html %}
---
layout: default
title: Home
description: Simple documentation template for Github pages
---

<!-- content -->
{% endhighlight %}

  <p>Set <code>isHome</code> to <code>true</code> on the main page file, the homepage will have a bigger header with a central download button.</p>

{% highlight html %}
---
..........
isHome: true
---
{% endhighlight %}

  <p>Set <code>hide</code> to <code>true</code> to hide a page from the main menu, the page will still be accessible with direct link. <a href="hidden.html">Example</a>.</p>

{% highlight html %}
---
..........
hide: true
---
{% endhighlight %}

  <h2 id="titles">Background image</h2>
  <p>In order to get the right menu automatically generated you must respect some conventions.</p>

{% highlight html %}
<!-- wrap each main section with "bs-docs-section" class -->
<section class="bs-docs-section">
  <!-- each section must contain ONE h1 with an id and optionally a "page-header" class -->
  <h1 id="first-level" class="page-header">Audio and Video Quality</h1>

  <!-- you can optionally declare sub-sections with h2/h3 with an id -->
  <h2 id="sub-section">Quality files</h2>

  <h3 id="another-sub-section">Still second level</h3>
</section>
{% endhighlight %}

  <h2 id="highlight">Syntax highlight</h2>
  <p>The powerful Pygments highlighter is activated on the template, just wrap your unescaped source code with the <code>{{ "{% highlight ... " }}%}</code> directive.</p>

{% highlight text %}
{{ "{% highlight html " }}%}
<div>Some <b>HTML</b></div>
{{ "{% endhighlight " }}%}

{{ "{% highlight javascript " }}%}
alert('Some javascript');
{{ "{% endhighlight " }}%}
{% endhighlight %}

  <h2 id="resources">Resources &amp; links</h2>
  <p>If you need to create internal links between your pages, or include resources (JS &amp; CSS), always start your URLs with <code>{{ "{{site.github.url" }}}}</code>.</p>

{% highlight html %}
<script src="{{ "{{site.github.url" }}}}/dist/my-script.js"></script>

<a href="{{ "{{site.github.url" }}}}/about/index.html">About</a>
{% endhighlight %}

  <h2 id="bootbox">Bootbox</h2>
  <p><a href="http://bootboxjs.com/">Bootbox</a> is installed with a syntax sugar to easily create pop-in content. To use this sugar you must create a clickable element with a <code>data-bootbox</code> attribute and an hidden content holder with a corresponding <code>id</code> attribute.</p>

{% highlight html %}
<button class="btn btn-primary btn-xs" data-bootbox="my-content">Button title</button>

<div id="my-content" class="hidden" title="Pop-in title">
  Pop-in content
</div>
{% endhighlight %}

  <h2 id="gems">Plugins</h2>
  <p>All available Jekyll plugins are installed by default, you can remove them by modifying the <code>gems</code> parameter in <code>_config.yml</code>. See the documentation on <a href="https://help.github.com/articles/using-jekyll-plugins-with-github-pages/">GitHub Help</a> pages.</p>

  <h2 id="bower">Bower</h2>
  <p>Fell free to use the <code>bower.json</code> to manage your front dependencies. Bower packages are added the <code>dist</code> directory and <b>MUST</b> be pushed to the repository. jQuery and Bootstrap are ignored by <code>.gitignore</code> as already loaded from a CDN.</p>
</section>