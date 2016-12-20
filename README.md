# **Overview**
This repository holds the source code for the message360° WebRTC widget. The widget is an option for WebRTC users that do not want to utilize the full platform. 
The widget is can be loaded onto another site following the instructions down below.

# **Installation**
The widget is dependent on a set up of the WebRTC platform. Even if you do not plan on using the full site, you need to set one up and have it active and running.
This is because the widget will be loading content through the platform via iFrame. If you have some experience with iFrames and their uses, you can read more here: [http://www.w3schools.com/html/html_iframe.asp](W3 iFrame).
If you don't have a WebRTC platform for you message360° account up and running, follow this link: [https://github.com/danielpark-ytel/message360-webrtc](WebRTC repository)

### **Setup**
##### 1. Download the code for the widget
1. Navigate to your desired install directory and perform a `git clone git@gitlab.ytel.com:danielparkk/message360-widget.git`

2. This will download the source code into a folder containing an `index.html` and a javascript file `iframeResizer.min.js`.

##### 2. Implementation on a website.
1. The `index.html` file gives a pretty clear example of how the widget can be implemented into another site.

2. You can place the `iframe` tag from the html file you downloaded onto an html file for your website:
```html
<body>
    <iframe id="wrtc-m360-iframe" src="https://webrtc-client-dev.message360.com/widget.html" scrolling="no"
                frameborder="0" style="width:240px;
                position: absolute;
                bottom: 0;
                right: 16px;
                box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);"></iframe>
</body>
```

3. You also need to load the script into the head of your html file:
```html
<head>
    <script type='text/javascript' src='/path/to/iframeResizer.min.js'></script>
</head>
```

4. Finally you need to write a very small line of javascript code to enable the resizing of the widget.
```html
<body>
    <!--Site Content-->
    <script type='text/javascript'>
        iframeResize();
    </script>
</body>
```

5. After you do all these parts, your HTML page should look something like this.
```html
<html>
    <head>
        <script type='text/javascript' src='path/to/iframeResizer.min.js'></script>
    </head>
    <body>
        <iframe id="wrtc-m360-iframe" src="https://webrtc-client-dev.message360.com/widget.html" scrolling="no"
                frameborder="0" style="width:240px;
                position: absolute;
                bottom: 0;
                right: 16px;
                box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);"></iframe>
        <script type='text/javascript'>
            iframeResize();
        </script>
    </body>
</html>
```
This will look a little different depending on the content on your site, but you can use this as a general skeleton/outline.

### **Usage**
As stated before, the widget is content from the WebRTC platform loaded via iFrame.
You just need to enter a username and caller ID number (Verified on the message360° account that was configured with the platform.) into the widget an proceed to use the dialpad to make calls.
