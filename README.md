# mvp-suummit-iot-workshop

We are presenting two primary workshops today, one for Azure IoT Hub's Device Mangement feature set and 
one for the Azure IoT Gateway SDK and you may start with either.  We encourage you to cover as much 
ground as you have time for and proctors are available to help keep you on track, answer questions or 
talk tech.  Lastly, please don't hesistate to ask questions! 

## Getting Started
Each workshop participant has been provided a Raspberry Pi 3, a pre-configured uSD card and a Texas Instruments(TI) 
[BLE](#ble) Sensor Tag.  All required code packages noted in the tutorial have been pre-loaded and/or built for 
your conveience; so you may skip running any commands for setting up the Raspberry Pi dependencies.  You'll find 
the Azure IoT Hub SDK, Azure IoT Field Gateway SDK and our bonus IoT Sample library (still under construction) 
in the home directory(`~/code`) of the `pi` user.

Prebuilt Software Notes:
- All required NodeJS packages have been installed globally and can be pulled into your project with 
the command `npm link {express}`
- The Azure IoT Hub Field Gateway has been built with the NodeJS bindings.  Please note that if you 
are interested in building the Java or .Net bindings, they can take upwards of an hour to compile on the Pi device.


## Azure Device Management Tutorial

The tutorial for Device Management is available [here](https://github.com/Azure/azure-iot-sdks/tree/mvp_summit/c/serializer/samples/devicetwin_configupdate#run-the-device-twin-config-update-sample)
and you may skip forward to to the instruction beginning with `Edit the file ./c/serializer/samples/devicetwin_configupdate/devicetwin_configupdate.c and replace`

## Azure IoT Gateway SDK Tutorial 

The tutorial for the IoT Gateway SDK is available [here](https://azure.microsoft.com/en-us/documentation/articles/iot-hub-gateway-sdk-physical-device/#prepare-your-hardware)
and you are encouraged to read the architectural preamble before jumping to  the `Enable connectivity to the SensorTag device from your Raspberry Pi 3 device`
section to configure your TI BLE Sensor Tag.

## Additional Bonus Workshop Content

For extra credit, the Raspberry Pi has been setup with the reqired tooling to run the [NodeJs Gateway Examples](https://github.com/Azure/azure-iot-gateway-sdk/blob/master/doc/nodejs_how_to.md#linux-1).
Once you have the GatewaySample running, try performing the following changes:
- Create a NodeJS Module that concatinates messages from the `node_sensor` using a `|` delimiter and then posts them to the Gateway's internal message bus
- Develop a NodeJS Module that compresses the batched messages and posts them to the Gateway's internal message bus.
- Copy and configure the IoT Writer NodeJS module from the Iot Samples -> Field Gateway project to send the compressed mesages to your IoT Hub.
- Wire up an Azure Function using your IoT Hub's Event Hub endpoint and utilize the IoT Samples -> DecompressShred -> NodeJs Azure Function to decompress and shred your IoT Hub messages, posting each individual message to an Event Hub for processing by Azure Stream Analytics
- Create an Azure Stream Analytics query that simply selects all the data from your Event Hub and outputs the results to PowerBi, displaying aggregate metrics.