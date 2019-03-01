# Lights

Create your own diyHue compatible Lights!

Steps to Follow:
- Select your Platform of choice and the correct Sketch according to your Harware Setup (e.g. WS2812b)
- Edit the Number of (virtual) Lights and the number of LEDS used in your Setup within your Sketch if needed.
- Upload Firmware to Microcontroller
- Connect Hardware and Powersupply
- Configure Microcontroller by connecting to its Wifi, adding Credentials for Wifi Network.
- Add new created diyHue Lamp within APP by searching for new Devices.

More Information is available in our [documentation](https://diyhue.readthedocs.io/en/latest/lights/diylights.html)

## Contribuiting
The following is a set of guidelines for contributing to diyHue Lights. These are mostly guidelines, not rules. Use your best judgment, and feel free to propose changes to this document in a pull request.

### Building with travis
In order for your sketch to be built with travis, please upload only the `sketch.ino` file in a folder within the Arduino dir. Please make sure that the folder and sketch name are exactly the same, ignoring the extension. For example the sketch would be saved in `Lights/Arudino/Generic_Fun_Light/` and called `Generic_Fun_Light.ino`.

Also within you PR, please create a commit to `.travis.yml`, adding a line in the matrix section. This should be in the format `- SKETCH="YOUR_SKETCH_NAME_HERE"`. Following the above example, `.travis.yml` would look like:

```
...
 matrix:
    - SKETCH="Generic_RGBW_Light"
    - SKETCH="Generic_RGB_Light"
    - SKETCH="Generic_CCT_Light"
    - SKETCH="Generic_RGB_CCT_Light"
    - SKETCH="Generic_WS2812_Strip"
    - SKETCH="Generic_SK6812_Strip"
    - SKETCH="Generic_Fun_Strip"
...
```

Finaly, if your sketch requires any of the libraries not installed on [this](https://github.com/diyhue/Lights/blob/675d2693afdb5f38fd9e61fdcf21aa042a7817b4/install.sh#L94) line of `install.sh`, then please add a commit adding them.
