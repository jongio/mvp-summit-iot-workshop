# MVP Summit 2016 IoT Workshop 

Welcome to the MVP Summit 2016 IoT Workshop! 

Prueba de Jira

We are so glad to have you with us today. We put together this workshop to share some new and exciting features coming to Azure IoT. Our goal is to get you up-to-speed on the latest developments so you can take the knowledge back to your office and start implementing IoT solutions with them.

We are presenting two labs today, one for **Azure IoT Device Management** and 
one for the **Azure IoT Gateway SDK**.  The Azure IoT Device Management lab will introduce you to the new Device Twins and Direct Methods. The Azure IoT Gateway SDK lab will introduce you to our brand new SDK for building IoT Gateway devices that enables non-internet connected device to send data to Azure IoT. 

> Proctors from DX and Azure IoT are available to help you work through these workshops, answer questions or talk tech.

## Getting Started
Each workshop participant has been provided with a Raspberry Pi 3, a pre-configured MicroSD card, a Texas Instruments(TI) 
Bluetooth Low Energy (BLE) Sensor Tag, and an Azure Subscription.  

- All required code packages noted below have been pre-loaded and/or built for 
your convenience; so you may skip running any commands for setting up the Raspberry Pi dependencies.  
- You'll find 
the Azure IoT Hub SDK, Azure IoT Gateway SDK and our bonus IoT Sample library on your Pi in the home directory(`~/code`) of the `pi` user.
- All required Node.js packages have been installed globally. If you have any issues with npm packages, you can link them directly by executing the following command: `npm link {packageName}`
- The Azure IoT Gateway SDK has been built with the Node.js bindings. .NET and Java are also available, but we will not be touching on those today.  

## Azure IoT Device Management Lab

This lab will bring you through the new **Device Twins** and **Direct Methods** features. 

The Azure IoT Device Management lab is available [here](https://github.com/Azure/azure-iot-sdks/tree/mvp_summit/c/serializer/samples/devicetwin_configupdate#how-to-update-configuration-and-reboot-an-iot-device-with-azure-iot-device-twins). 


## Azure IoT Gateway SDK Lab 

This lab will bring you through the new **Azure IoT Gateway SDK** using a Bluetooth Low Energy (BLE) Sensor Tag, Raspberry Pi and Node.js.

The Azure IoT Gateway SDK lab is available [here](iot-hub-gateway-sdk-physical-device.md).


>Please read the architectural introduction before jumping to the "Enable connectivity to the Sensor Tag device from your Raspberry Pi 3 device"
section to configure your TI BLE Sensor Tag.

## Bonus Challenges

You are likely an overachiever, so we've included a few extra challenges!  Please make sure you complete the Azure IoT Gateway SDK lab first.

> Note: Your Raspberry Pi has been setup with the required tooling 
to run the [Azure IoT Gateway SDK Examples in Node.js](https://github.com/Azure/azure-iot-gateway-sdk/blob/master/doc/nodejs_how_to.md#linux-1).

### Manually Batching Messages
- Create a Node.js Module that concatenates messages from the `node_sensor` using 
a `|` delimiter and then posts them to the Gateway's internal message bus. 

### Compress Batched Messages  
- Develop a Node.js Module that compresses the batched messages and posts them to 
the Gateway's internal message bus.

### Implement an IoT Hub Writer
- Copy and configure the IoT Writer Node.js from the Azure IoT Gateway SDK Sample Project [here](https://github.com/Azure/azure-iot-gateway-sdk/blob/master/samples/nodejs_simple_sample/nodejs_modules/iothub_writer.js).

### Create an Azure Function to Decompress & Shred Messages
- Wire up an Azure Function using your IoT Hub's Event Hub endpoint and utilize 
the IoT Samples -> DecompressShred -> NodeJs Azure Function to decompress and 
shred your IoT Hub messages, posting each individual message to an Event Hub for 
processing by Azure Stream Analytics.

### Create an Azure Stream Analytics Query
- Create an Azure Stream Analytics query that simply selects all the data from your 
Event Hub and outputs the results to Power BI, displaying aggregate metrics.

### Create a Power BI Dashboard
- Create a [Power BI](http://app.powerbi.com) Dashboard that visualizes your TI Sensor Tag data in creative ways.  Feel free to use any of the Power BI Custom Visuals available [here](http://visuals.powerbi.com). You can learn how to create Power BI Dashboards from a Stream Analytics Output [here](https://azure.microsoft.com/en-us/documentation/articles/stream-analytics-power-bi-dashboard/).
