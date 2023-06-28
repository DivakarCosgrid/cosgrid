<!DOCTYPE html>
<html>

<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Configuring OpenVPN to run automatically on system startup</title>
  <link rel="stylesheet" href="https://stackedit.io/style.css" />
</head>

<body class="stackedit">
  <div class="stackedit__left">
    <div class="stackedit__toc">
      
<ul>
<li><a href="#configuring-openvpn-to-run-automatically-on-system-startup">Configuring OpenVPN to run automatically on system startup</a>
<ul>
<li></li>
<li><a href="#openvpn-run-as-a-service-in-windows-">OPENVPN RUN AS A SERVICE IN WINDOWS :</a></li>
<li><a href="#sign-tool-for-windows-">SIGN TOOL FOR WINDOWS :</a></li>
<li><a href="#alternative-for-creating-the-wix-installer-enter-link-description-here">Alternative for creating the wix Installer :enter link description here</a></li>
</ul>
</li>
</ul>

    </div>
  </div>
  <div class="stackedit__right">
    <div class="stackedit__html">
      <h1 id="configuring-openvpn-to-run-automatically-on-system-startup">Configuring OpenVPN to run automatically on system startup</h1>
<ol>
<li>We need to create a seperate Windows Service exe file</li>
<li>Inside the exe file we have to write a script which we have to configure the ovpn files that has to automatically start</li>
<li>We can create a service using the node-windows <a href="https://github.com/coreybutler/node-windows">https://github.com/coreybutler/node-windows</a></li>
<li>We can create using the node windows when we install we can set our service in the background which is automatic</li>
</ol>
<h3 id="set-the-script-of-the-exe-file-to-the-windows-service">Set The script of the exe file to the Windows Service:</h3>
<ol>
<li>We can use the nssm.exe to configure the window service. It is prefered by pritunl client electron where the follow these steps to configure their services</li>
</ol>
<h2 id="openvpn-run-as-a-service-in-windows-">OPENVPN RUN AS A SERVICE IN WINDOWS :</h2>
<p>The Step they Followed to configure as a service:<br>
<a href="https://openvpn.net/community-resources/running-openvpn-as-a-windows-service/">https://openvpn.net/community-resources/running-openvpn-as-a-windows-service/</a></p>
<p>Here they given the information how they really works as a ovpn service</p>
<ol>
<li>Inside the openvpnservice.exe they configure the ovpn directory path and ovpn execution path and also the log path. They were registered in the REGISTRY DIRECTORY too.</li>
<li>This is the simplest approach when compared to others.</li>
<li>It will be complex when there is a multiple connfiguration file.</li>
</ol>
<h2 id="sign-tool-for-windows-">SIGN TOOL FOR WINDOWS :</h2>
<p>Its was taken from pritunl client electron<br>
This configuration is used for the certification of our application in the windows<br>
<a href="https://codesigningstore.com/what-is-microsoft-signtool-how-to-use-it">https://codesigningstore.com/what-is-microsoft-signtool-how-to-use-it</a><br>
Here is the details regarding the sign the app</p>
<h2 id="alternative-for-creating-the-wix-installer-enter-link-description-here">Alternative for creating the wix Installer :<a href="https://drive.google.com/file/d/16VZBlZLiCrvrnAGJk78QQa7ynLk-_61m/view">enter link description here</a></h2>
<p>It was taken from pritunl client electron <a href="https://github.com/pritunl/pritunl-client-electron/blob/dependabot/npm_and_yarn/client/terser-5.14.2/resources_win/setup.iss">INNO Setup</a></p>
<p>Here is the example for creating installer setup</p>
<p>The Approach which we gonna use</p>
<ol>
<li>Printunl followed running the ovpn command directly not running the (net start opevnpnservice)</li>
<li>VPNHT followed the same method which they copied from the pritunl…Before they followed the Openvpn as a Service</li>
<li>They were running as we did but they the execution of the child process is hide<br>
<img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTXPj6HazmcTol-zTUopYBToSyLMH52NX5otYZb3cUe5vvbC2SNIgYxilbRwAmpWCtA-VA&amp;usqp=CAU" alt="enter image description here"></li>
</ol>

    </div>
  </div>
</body>

</html>
