Control Firmware
================

Each control board runs the OSU Robotics Club's `aerial control`_ firmware.

State Machine
-------------

The rocket controller implements a simple state machine to track the flight and
manage staging events. The following is a summary of the primary states:

+------------------+----------------------------------------------------------+
| State            | Description                                              |
+==================+==========================================================+
| DISARMED         | All output signals zeroed or deasserted under all        |
|                  | circumstances.                                           |
+------------------+----------------------------------------------------------+
| PRE_ARM          | Intermediate state attainable only via physical          |
|                  | interaction with control board, ideally on the pad.      |
+------------------+----------------------------------------------------------+
| ARMED            | Data logging starts. Controller waits for 1.1g on        |
|                  | positive X to transition to FLIGHT.                      |
+------------------+----------------------------------------------------------+
| FLIGHT           | Noop                                                     |
+------------------+----------------------------------------------------------+
| APOGEE           | Rocket: deploys drogue.                                  |
|                  | Payload: waits for zero gyration, then performs micro-g  |
|                  | maneuver and deploys drogue.                             |
+------------------+----------------------------------------------------------+
| DROGUE_DESCENT   | Main chute deploys at 1500ft AGL.                        |
+------------------+----------------------------------------------------------+
| MAIN_DESCENT     | Noop                                                     |
+------------------+----------------------------------------------------------+
| RECOVERY         | Reduce telemetry transmit rate to conserve power.        |
|                  |                                                          |
|                  |                                                          |
|                  |                                                          |
|                  |                                                          |
|                  |                                                          |
|                  |                                                          |
+------------------+----------------------------------------------------------+

.. _`aerial control`: https://github.com/OSURoboticsClub/aerial_control
