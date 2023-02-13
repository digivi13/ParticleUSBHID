# ParticleUSBHID
![image](https://user-images.githubusercontent.com/33264428/218349123-e2c53e30-c569-4eda-a1a1-fad27276308f.png)

A Microsoft excel sheet paired with the particle photon/electron microcontroller that can send text to one or multiple devices. Currently used to inject strings to an array of devices whos security prevents sending keystroke/device control using other methods.   

The keyboard library is only compatible with particle Gen 2 devices (photon , electron , P1). Newer particle products (Argon , Boron, P2 ) do not support the USB HID behavior due to the the components used in production.

The VBA script in Microsoft Excel is used to input data and make API requests to the Particle Cloud.
The Particle Cloud receives the API request made by the VBA script and passes the data to the Particle Photon.
The Particle Photon has firmware that is written in the Particle Web IDE, which is designed to interpret the data received from the Particle Cloud.
The firmware uses the Keyboard library to send the keystrokes specified in the data received from the VBA script.
The keystrokes are then sent to the attached USB device as if they were being typed by a user.

This process can be represented in a flow diagram as follows:

VBA Script in Excel -> API Request -> Particle Cloud -> Particle Photon (firmware) -> USB Device.

The Particle Photon acts as a bridge between the VBA script and the USB device, allowing the keystrokes to be sent from Excel to the USB device.

![image](https://user-images.githubusercontent.com/33264428/218277636-17184d09-7a9d-42f5-b5b1-b14521cbac7d.png)
