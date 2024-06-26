# CBLEmbedded

## Prerequisite

In order for the application to run properly you should first set up some user secrets, even though
this configuration part is not really secret it is an easier way to pass configuration parameters
for different platforms. Namely, when we do testing and development of the Arduino board, we need
to test the WebApi server localy and have windows configuration with COM ports, but when it is deployed
on the Raspberry Pi, which is running Raspberry Pi OS the name of the port there is usually /dev/ttyACM0
and setting up a simple user-secrets environment on both devices makes testing seamless.

```plaintext
    dotnet user-secrets init
    dotnet user-secrets set "SerialPort:Port" "{COM5}/{/dev/ttyACM0}"
    dotnet user-secrets set "SerialPort:BaudRate" "115200"
    dotnet user-secrets set "SerialPort:Retries" "3"
    dotnet user-secrets set "SerialPort:Timeout" "500"
```