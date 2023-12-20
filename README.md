# cnc_plasma
Plans and such for my CNC plasma project, https://www.runstenracing.se/?cat=61

To see the plasma in action, https://www.youtube.com/watch?v=OwQSaWDesY0

The plasma is using 2 Nema24 motors to run the Y axis, and Nema17 motors on X and Z.
I'm using a SKR controller for a 3D printer to run the stepper motors and a Raspberry Pi with Klipper for the software interface.
I've configured klipper to trick the software into running the scrape start for the plasma on each start and I've written a custom POST processor for Fusion360 to export the gcode to the cutter.

I'll supply the STEP file for the hardware and the POST processor now and I'll add the customization for the klipper software later on.
