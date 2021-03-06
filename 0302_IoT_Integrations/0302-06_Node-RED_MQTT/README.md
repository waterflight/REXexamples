Node-RED + MQTT example
=======================

The source files located in this folder illustrate how to communicate with REX REST API
using popular tool Node-red and MQTT communication protocol in order to pass data from
the Rex to devices listening on the MQTT topic and vica versa to store data flowing from
the MQTT topic in the Rex.

In the *nodered_flow.txt* file is a flow of nodes which represents configuration of the
Node-RED framework.
The node named as *GET data from REX API* is set up to receive value of the CNR_OUT block.
This value is then passed to the MQTT topic in the node *rex_topic* output node. There is
also an *rex_topic* input node that is listening to the same topic and is therefor notified
with all the values that flow through the topic. Every value is then passed to the CNR_IN
block in the *POST data to REX API*.

Nodes *Parse data* are simple functions that preproccess data for the REX API requests.

## Note ##
Nodes that communicate with the REST API are required to use basic authentification that
can be set in the properties of the block.

## Timing of the project ##
The algorithm runs each 5 seconds. Edit the *Clock* node in the flow for different timing options.

## Prerequisites ##
- Node.js and Node-RED must be installed and running on the target (e.g.:Debian Jessie -
*apt-get install nodered* will install all required packages).
- RexCore must be installed and running on the target device.

## Running the example ##
- The **exec.mdl* file is the project main file.
- Open it with *RexDraw*.
- Compile and download it to the target device.
- Start node-red on the target and use web browser to navigate to the address of the node-red's
webserver. (default address is http://127.0.0.1:1880/)
- Import flow from OpenWeatherMapAPI_flow.txt. You can use either import from clipboard or you
can copy the file to the */lib/flows* in your installation and then import the flow as a Library.
- Open the *Get weather info* node and specify your unique OpenWeatherMap API ID in parameter URL:
http://api.openweathermap.org/data/2.5/weather?q=Pilsen&units=metric&appid=your_API_ID
- Open nodes with POST requests and *Get CNDR heating curve* node with GET request from the
REX and specify target URL with corresponding credentials.
- Deploy the flow. If everything is done correctly you should see data about the weather stored
in the REX execution and as a result of GET request you should see adequate supply water temperature
printed in the debug console of Node-RED.

## Documentation ##
- **Press F1 for help** on the selected function block in the *RexDraw* program.
- [Node.js documentation](https://nodejs.org/en/docs/)
- [Node-RED documentation](http://nodered.org/docs/)
- [RexDraw User Guide](https://www.rexcontrols.com/media/2.50.4/doc/ENGLISH/MANUALS/RexDraw/RexDraw_ENG.html)
- [Complete documentation of REX](http://www.rexcontrols.com/documentation-and-support)

## Additional information ##
- Visit the [REX Controls company webpage](http://www.rexcontrols.com) 
for more information about the example projects and developing advanced 
automation and control solutions using REX.