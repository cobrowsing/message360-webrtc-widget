<h1>WebRTC Widget Documentation</h1>
<h2>Useful Information</h2>
<p>This repository contains the source code and files for WebRTC widget implementation.
The feature will enable a user to make outbound calls on an existing website or CRM platform using their Message360 account.
Please read through this document for information on how to use and setting up this feature.</p>

<h2>Set up/Installation</h2>
<h3>Files and dependencies</h3>
<p>The <b>widget.js</b> file contains the javascript code which enables call functionality and generates the HTML widget.
The widget will only work with the following javascript dependencies.</p>
<ul>
    <li>jQuery</li>
    <li>jQuery-json</li>
    <li>jQuery-verto</li>
    <li>jQuery-FSRTC</li>
    <li>jQuery-jsonrpcclient</li>
</ul>

<h3>Setting up</h3>
<h4>Downloading and including files</h4>
<p>Download this repository: <code>git clone https://gitlab.ytel.com/danielparkk/Message360-WRTC-Widget-Repository.git</code></p>
<p>There is an HTML file in the folder by the name of <b>example.html</b> which shows the order in which the dependencies should be
included in your own HTML document for your website/application.</p>
<p>Once you've copied the folder and its contents and included the dependencies and the <b>widget.js</b> script in your application, 
you will need to edit the main script file to work with your Message360 account.</p>
<h4>Editing <b>widget.js</b></h4>
<p>We need to edit the data configuration for this widget to work.
In the <b>widget.js</b> file, look for the portion of the script that looks like this:</p>

<code>//Data configuration
var data = {
    instance : null,
    connected : false,
    accessToken : null,
    tokenUrl : "",
    numberUrl : "",
    call : null,
    callState : null,
    canVideo : null,
    videoDevices : [],
    audioDevices : [],
    shareDevices : [],
    speakerDevices : [],
    selectedShare : null,
    selectedVideo : null,
    selectedAudio : null,
    selectedSpeaker : null,
    callerName : null,
    mutedMic : null,
    onHold : null,
    callerNum : null,
    hostname : "message360.com",
    wsUrl : "wss://id953la.message360.com:8082"
};</code>

<p>The properties we're interested in are the <code>tokenUrl</code> and the <code>numberUrl</code>.
The url's should be the location of the helper library files for WebRTC.</p>
<p>For example, <code>tokenUrl</code> should be the url with the location of the helper library script that generates an accessToken for
WebRTC usage on your web server. Accordingly, <code>numberUrl</code> should be the location of the script that authenticates a phone number for WebRTC use.</p>

<b>Here's an example of how a configured script's data variable should look:</b>

<code>//Data configuration
var data = {
    instance : null,
    connected : false,
    accessToken : null,
    tokenUrl : "https://yourdomain.com/accessToken.php",
    numberUrl : "https://yourdomain.com/authenticateNumber.php",
    call : null,
    callState : null,
    canVideo : null,
    videoDevices : [],
    audioDevices : [],
    shareDevices : [],
    speakerDevices : [],
    selectedShare : null,
    selectedVideo : null,
    selectedAudio : null,
    selectedSpeaker : null,
    callerName : null,
    mutedMic : null,
    onHold : null,
    callerNum : null,
    hostname : "message360.com",
    wsUrl : "wss://id953la.message360.com:8082"
};</code>

<p><i>IMPORTANT: </i> It's important to note that that due to browser restrictions and CORS issues, the helper library scripts should be 
hosted in the same application folder as the one you are implementing the widget and not on a different server.</p>

<p>After the data variable is configured, the widget should be ready for use.</p>

<h2>Usage</h2>
<p>Using the widget is pretty simple. Once the script loads on the browser, you will see a login form on the bottom right of your browser window.
Just login using a name and enter a number that is owned by your Message360 account, <b>make sure it's voice-enabled and active</b>. Once you're logged in,
you can enter a 10-digit US number and make a call. 

