# cnc_plasma
Plans and such for my CNC plasma project, https://www.runstenracing.se/?cat=61

To see the plasma in action, https://www.youtube.com/watch?v=OwQSaWDesY0

The plasma is using 2 Nema24 motors to run the Y axis, and Nema17 motors on X and Z.<br>
I'm using a SKR controller for a 3D printer to run the stepper motors and a Raspberry Pi with Klipper for the software interface.<br>
I've configured klipper to trick the software into running the scrape start for the plasma on each start and I've written a custom POST processor for Fusion360 to export the gcode to the cutter.

I'll supply the STEP file for the hardware and the POST processor now and I'll add the customization for the klipper software later on.

Bill of materials
-----------------

**Frame**

- 2x1000mm 40x40 aluminium extrusion
- 3x1000mm 20x40 aluminium extrusion
- 1x300mm 20x40 aluminium extrusion for z-axis (?)
- 9x v-slot wheel with bearings for M5 bolt
- 3x offset adjusting nut for v-slot wheel
- 3x 2100mm GT2 6mm belt
- 1x 700mm GT2 6mm belt
- 4x 16T GT2 6mm pulleys with matching hole diameter to the chosen stepper motors
- 4x GT2 6mm idlers with bearings for M5 bolt
- 4x 9mm (?) magnets for the torch holder

**Electronics**

- SKR or similar 3D printer control board
  - Compatible with klipper
  - Supporting at least 4 separate axis/stepper motors
  - At least one digital output channel
  - At least one digital input channel
- Raspberry pi or similar able to run Klipper with Moonraker frontend
- 5v relay or similar FET to drive the plasma cutter trigger
- Microswitch for z sensing (will add details later)
- 2x Nema24 or similar steppers motors for Z axis (other sizes work just as well but need new design for mount)
- 2x Nema17 or similar steppers for X and Z axis

**Mounting hardware**

- M5 bolts, details to be added later
- M5 t-slot nuts, details to be added later
- 4xM12 bolts for mounting the 40x40 extrusions
- Printed or milled mounting hardware as per the CAD file
- Suitable cable chains for cable routing, at least 2m

**Plasma cutter**

The requirements of the plasma cutter depends on what material you want to cut. I'm using a Cut60 with a maximum power of 60A and touch start.<br>
The benefit of using touch instead of HF start is that it's less prone to causing problems with the electronics due to RF noise. Still I have some problems of the controller getting brown-outs at more than 42A power which I'm sure can be remedied with shielding and better cable routing but so far I have managed to cut what I've needed as it is.

I've installed a straight plasma torch on my cutter which is nice but not necessary. To use the standard torch a new holder needs to be designed though.<br>
I've cut the trigger feed to the torch and installed a connector to route it to the relay instead of the trigger on the torch. The relay is controlled by a digital output pin on the SKR control board to start and stop the plasma.

**TODO::**

Check the size of the magnets on the torch holder<br>
Count M5 bolts and lengths<br>
Count M5 t-slot nuts<br>
Get the details of the micro switch for the z-limit<br>
Measure the length of the Z extrusion<br>
Rip the config from klipper and post he<br>
