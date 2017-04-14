# HTML Console SDK

This repository contains sample code for the VMware HTML Console SDK.

## Prerequisites

In addition to the HTML and Javascript files in this repository,
you need the CSS files and the `wmks.min.js` library from the 
[VMWare HTML Console SDK](https://www.vmware.com/support/developer/html-console/index.html)
freely available on the Web.

The HTML Console SDK is based on the jQuery and jQueryUI libraries,
available from several Web sites, such as code.jquery.com and ajax.googleapis.com.
To run without the public Web, you can download these libraries for access inside your firewall.

To connect from one host to another, a valid security certificate is required.
If any host lacks a valid certificate authority signed certificate,
you must agree to have your browser accept that host's self-signed certificate.

After placing the sample code in the same folder as the HTML Console SDK,
open `wmks-sdk-example.html` in your Web browser.

## With VMware Workstation

If you have a VM running on VMware Workstation,
and your browser has a valid security certificate from that VM,
you can connect to it using the loopback host 127.0.0.1 at port 8180,
which is the default in the sample HTML file.

Click the *createWMKS* button, then the *connect* button.

## With vCenter Server and ESXi Host

To connect with a VM running on an ESXi host managed by vCenter Server, 
a *webmks* ticket is required to locate the VM and authorize the connection.
You can obtain a *webmks* ticket in several different ways
(see VMware HTML Console SDK documentation for details):

 - Log into vCenter Server's Managed Object Browser (MOB), find vmFolder, acquire ticket.
 - Enable MOB on the ESXi host, log into MOB, find vmFolder, acquire ticket.
 - Once you know the VM's managed object ID, visit URL with method=acquireTicket.
 - Write a Java or C# program that authenticates with vSphere; call the `acquireTicket` method.

Click the *createWMKS* button.
In the host field, type the ESXi host's IP address, and in the port field, 443.
Copy and paste the *webmks* ticket that you obtained from the MOB or otherwise.
The *webmks* ticket can only be used once, and expires after several minutes if not used.
Click the *connect* button.

You can use the *sendInputString* field and Enter button to supply login and password
if required for VM access.

Mobile controls and options are for use with an iPad, iPhone, or Android device.

