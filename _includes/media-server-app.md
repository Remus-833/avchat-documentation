<ul class="nav nav-tabs" id="serversTab">
  <li class="active"><a data-target="#red5" data-toggle="tab">Red5</a></li>
  <li><a data-target="#ams" data-toggle="tab">Adobe Media Server</a></li>
  <li><a data-target="#wowza" data-toggle="tab">Wowza</a></li>
</ul>

<div class="tab-content">

<div class="tab-pane active" id="red5">
<div class="panel panel-default">
<div class="panel-body">

<p>Upload the <code class="highlighter-rouge">avchat30</code> folder from the <b>Files to upload to your media server (Red5)</b> folder to your Red5's <b>webapps</b> folder (<code class="highlighter-rouge">C:\Program Files\Red5\webapps</code> on Win, <code class="highlighter-rouge">/opt/red5/webapps/</code> on Linux).</p>

<p>On Linux, chmod the new <code class="highlighter-rouge">avchat30</code> folder to 777.</p>

<p>Restart the Red5 server.</p>

</div>
</div>
</div>

<div class="tab-pane" id="ams">
<div class="panel panel-default">
<div class="panel-body">
<p>Upload the <code class="highlighter-rouge">avchat30</code> folder (you will find it in your AVChat archive in the <b>Files to upload to your media server (FMS) folder)</b> to the <b>applications</b> folder of your AMS installation.</p>

<p>On Linux, chmod the new <code class="highlighter-rouge">avchat30</code> folder to 777.</p>

</div>
</div>
</div>

<div class="tab-pane" id="wowza">
<div class="panel panel-default">
<div class="panel-body">
<p>Upload the <code class="highlighter-rouge">applications</code>, <code class="highlighter-rouge">lib</code> and <code class="highlighter-rouge">conf</code> folders from the <b>Files to upload to your media server (Wowza)</b> folder to the root folder of your Wowza Media Server installation.</p>

<p>Restart the Wowza server.</p>

<!--Starting with Wowza Streaming Engine 4, a new GUI has been added that allows you to control the server and individual applications. This can be accessed using a browser by going to <b>http://WOWZA_SERVER_ADDRESS:8088/enginemanager</b>-->
</div>
</div>
</div>

</div>

<script>
jQuery(function () {
    jQuery('#serversTab a:last').tab('show')
})
</script>
