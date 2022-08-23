# GettingStartedWithAxibo

![](../.gitbook/assets/0)

### Work in Progress <a href="#_toc112094461" id="_toc112094461"></a>

* Add github link to python library

### Contents

Work in Progress 2

Contents 2

What is AXIBO? 3

Connecting to AXIBO 4

Development API 5

Performing an API Request using Postman 8

Setting up the Python Library 10

Changing Camera Resolution 13

### What is AXIBO? <a href="#_toc112094463" id="_toc112094463"></a>

AXIBO is a robotic cinematography system that enables the studio crew to automate production and leverage computer vision to autonomously track the subject.

![A screenshot of a computer

Description automatically generated with low confidence](../.gitbook/assets/1)

### Connecting to AXIBO <a href="#_toc112094464" id="_toc112094464"></a>

The AXIBO edge node performs communication with a variety of peripheral devices and accessories. It hosts a dashboard that can be viewed at the following address:

IP: **10.42.0.1**

![Graphical user interface

Description automatically generated with low confidence](../.gitbook/assets/2) ![](../.gitbook/assets/3)

It must be connected to a power source using the provided 12 V 1.5 A centre positive power supply.

The slider is one such accessory for the AXIBO system. It is connected to the edge node through ethernet.

Once connected, the user will be able to interact with a web dashboard to update, configure, and run the AXIBO system.

![](../.gitbook/assets/4)

Navigate to the **Feed** tab and ensure that the camera is transmitting.

![](../.gitbook/assets/5)

### Development API <a href="#_toc112094465" id="_toc112094465"></a>

The AXIBO edge node hosts an HTTP server which can be communicated with using web sockets. Data containing accessory configurations, and device instructions that are formatted as JSON strings can be published to this webserver.

A tool that can be used during application development to demonstrate and test API requests is called Postman. The desktop app can be downloaded from the following website:

Website: [https://www.postman.com/](https://www.postman.com/)

![Graphical user interface, application

Description automatically generated](../.gitbook/assets/6)

To link the collection of testing API requests to your desktop application, navigate to **Import > Link** and paste the following url:

Postman Collection: [https://www.getpostman.com/collections/32be12d1d41785101895](https://www.getpostman.com/collections/32be12d1d41785101895)

![Graphical user interface, text, application

Description automatically generated](../.gitbook/assets/7)

Press **Continue**, then press **Import**.

![Graphical user interface, application, table

Description automatically generated](../.gitbook/assets/8)

You will see that a new collection has been added to your left toolbar named **axibo\_opensource**.

![Graphical user interface, application

Description automatically generated](../.gitbook/assets/9)

Before any requests are sent, it is crucial that the URL **environment variable** is set to the URL of the AXIBO edge node in use.

Click on **axibo\_opensource** and select the **Variables** tab. Ensure that a variable named **base\_url** is set to the correct URL of your edge node.

In our case, this is **10.42.0.1**.

![Graphical user interface, application

Description automatically generated](../.gitbook/assets/10)

**Save** the configuration by pressing **CTRL** + **S**.

### Performing an API Request using Postman <a href="#_toc112094466" id="_toc112094466"></a>

Ensure that you are connected to the AXIBO edge node access point.

![](../.gitbook/assets/11)

Navigate to the **Get Camera Image** request in the **axibo\_opensource** collection.

![](../.gitbook/assets/12)

Press **Send** and await a response from the edge node.

The edge node will take a picture and append it to the response of the route.

![](../.gitbook/assets/13)

### Setting up the Python Library <a href="#_toc112094467" id="_toc112094467"></a>

Ensure that **Python 3.8** is installed on your system.

The library can be cloned form the following repository:

GitHub:

Extract the **zip** file.

![Graphical user interface, application

Description automatically generated](../.gitbook/assets/14)

Open **Visual Studio Code**.

![Graphical user interface, application

Description automatically generated](../.gitbook/assets/15)

Open the extracted library.

![Graphical user interface, text, application

Description automatically generated](../.gitbook/assets/16)

Use either PowerShell or the built-in terminal and navigate to the root of the library.

![Text

Description automatically generated](../.gitbook/assets/17)

Install the following dependencies.

![](../.gitbook/assets/18)

Run pip install on that directory.

![Text

Description automatically generated](../.gitbook/assets/19)

Ensure that no errors present themselves.

### Changing Camera Resolution <a href="#_toc112094468" id="_toc112094468"></a>

Navigate to and open **src/camera\_example.py**.

![A screenshot of a computer

Description automatically generated with medium confidence](../.gitbook/assets/20)

Modify the IP address string that is passed in with the object constructor to match your own.

Set your desired resolution using the set\_resolution method.

Navigate to the **settings** panel on the web dashboard and notice the **resolution** in the **AXIBO Camera Settings** section.

If this is already 1920 x 1080, modify it from here so that we will notice a change.

The resolution can be modified using the dropdown.

Then pressing **Set.**

A notice at the top will display if it has been set correctly.

Navigate back to **Visual Studio Code** and open the **terminal** window.

Navigate to the **src/** directory.

Run the **camera\_example.py** script.

Navigate back to the web dashboard and notice that the **resolution** has been updated. Refresh the page if you run into any issues.

End.
