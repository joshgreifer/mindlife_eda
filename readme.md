# Mindlife EDA Scope
Version 1.0.4

#### What's New in Version 1.0.4
* Supports both Mindlife USB (HID) EDA Device and Mind Heart Tech Bluetooth Dual Channel device
* Displays raw PPG and EDA signal from Mind Heart Tech device


#### Installation:

1. Make sure you have [nodejs](https://nodejs.org/en/download/) installed.

1. Open a command prompt and navigate to the directory containing this readme file.

1. Run `npm install`

* If you have any issues installing node-hid, you may need to follow the  instructions to [compile it from source](https://www.npmjs.com/package/node-hid/v/0.5.2#compiling-from-source))

#### Setting the serial port used by the Mind Heart Tech device

1.  Install the app as explained above.

1.  Pair the device with the computer.

1.  Open the file `settings.json` in a text editor.  The file is situated in the `public/` directory below the installation directory.

1.  Edit the `"serialport"` value to be the rfcomm port name (Windows) or virtual device path (MacOS, Linux) that was assigned by the operating system (MacOS), or manually (Linux)  when the device was paired.

1.  Save the file `settings.json`.

*   To find the port name (e.g. `COM7`) in Windows, use the Device Manager (`Windows-key R, devmgmt.msc`).
*   To find the device path in MacOS, run `ls -l /dev/tty\.*` from a terminal, and look for a device path that contains the string `Mind_Heart` The device path will probably be `/dev/tty.Mind_Heart_Tech-SerialP`.
*   For Linux, you will need to create the rfcomm serial device manually (e.g. `/dev/rfcomm0`).

#### Launching the app

1.  To launch the application, run `node app.js`,  then point your browser to [http://localhost:3050/](http://localhost:3050/).

1.  Optionally, attach the EDA device to a USB port.  The app will detect this and display `USB (HID) Device Mindlife EDA: Connected.` in the status area at the bottom of the display.

#### Zooming, Scrolling, Scaling and changing the plot signal-follow behaviour
* To Zoom the plot, drag in the plot area.

* To scrub (scroll) the plot horizontally or vertically,  drag in the axes area.

* To enable or disable signal follow behaviour, click the right-arrow in the bottom-left of the plot area.

* To enable or disable vertical (value axis) auto-scaling, click in the double-headed vertical arrow in the bottom-left of the plot area.


#### Starting a session (USB Device only)

* Click the `[Restart]` button to clear all data from the session.

#### Recording a session (USB Device only)
* The app records continuously: there is no `[Record]` button.   

* To save the session,  click the `[Save]` button.  Files are save in the same directory as the application, with the name indicated in the `Name:` input text field (default `"New Session.json"`)

* Two files get written to disk when you save a session:  A `.json` file, which is human-readable, and a `.npy` file, which is a Python numpy file containing the EDA response signal.


#### Marking and annotating a session
* Pressing a number key adds a Marker to the session at the time the key was pressed.
* If speech detection is enabled, the app adds Markers for each recognized utterance.
* You can also add a marker by double-clicking in the SCR plot.

#### Triggering 
A trigger is a special marker that causes the app to begin analysing the signal to identify an event-related skin conductance response (ER-SCR).

* To create a trigger,  hit the Space Bar.

* If the app identifies a response, it will add Markers for the trigger start time, peak start time, peak and 1/2 recovery points.

* The scope can be zoomed with the mouse, and scrolled by scrubbing the axis at the bottom and left.

* The display will auto-scale by default, until you zoom the display.  To re-enable auto-scaling, click the up-down arrow indicator at the bottom-left of the scope.

### Navigating to a Marker
* Click the marker in the transcript console.  The display will jump to the marker's time, and will no longer follow the signal until you re-enable signal following

### Editing Marker text
* Double-click a marker in the SCR plot area to edit its text.

* You can also double-click the marker in the transcript console to edit its text.

#### Editing Marker colours
The Marker Settings section of the Options page has a list of marker colours and labels.  If a marker's label matches the text in the settings, its colour will be set to the colour in the settings.

* To change the colour of all markers that match the label text in the Marker Settings section,  click the colour patch, and use the colour picker.

* A Marker matches a label if its text is the same as the label,  up to the first colon character. 
For example,  if a Marker's text is `Trigger: Clapped hands` or simply `Trigger`, its colour will be set to the colour in the marker settings for the label `Trigger`.

### Adjusting Response Analysis Parameters.
* Adjust the Response Analysis Settings section in the Options Page.
* Hover the mouse over the individual settings for a brief explanation of them.

### Gaze Detection
* Gaze detection is disabled in this version.

### Speech detection.
* Speech detection is enabled in this version.  Contact me (Josh Greifer) for a password.