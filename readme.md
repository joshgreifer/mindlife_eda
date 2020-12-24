# Mindlife EDA Scope

#### Installation:

1. Make sure you have [nodejs](https://nodejs.org/en/download/) installed.

1. Open a command prompt and navigate to the directory containing this readme file.

1. Run `npm install`

* If you have any issues installing node-hid, you may need to follow the  instructions to [compile it from source](https://www.npmjs.com/package/node-hid/v/0.5.2#compiling-from-source))

#### Starting the scope

1.  To launch the application, run `node app.js`,  then point your browser to [http://localhost:3050/](http://localhost:3050/).

1.  Attach the EDA device to a USB port. The plot area will show the Skin Conductance Level (top display) and Skin Conductance Response (SCR) in the bottom display.

* The scope can be zoomed with the mouse, and scrolled by scrubbing the time or value axes.

* The display will auto-scale vertically by default, until you change the vertical zoom.  To re-enable auto-scaling, click the up-down arrow indicator at the bottom-left of the scope.

* The display will stop following the EDA signal after you zoom horizontally.  To re-enable, click the right-arrow at the bottom left of the display.

* At this time, Markers can be added by holding down Alt and hitting certain keys,  or by double-clicking in the SCR display area.  To edit a Marker label, double-click on the marker in the plot area, or in its corresponding entry in the transcript area.