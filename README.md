# ESP32-S3 / IR360 Enclosure Prototype

Adjustable, unverified-fit prototype for an Espressif ESP32-S3-DevKitC-1
and the Jessinie 38 kHz IR transmitter/receiver linked below.

## Files

- [Editable SolidCraft design](esp32_s3_ir360_prototype.solidcraft)
- [Base STL](base.stl)
- [Lid with IR through-window STL](lid_ir_deck.stl)
- [STEP, both parts in print layout](esp32_s3_ir360_prototype.step)
- [Preview](preview.png)
- [Assembly with ESP32 reference, editable JSON](esp32_s3_ir360_with_reference.json)
- [Reference assembly preview](reference_preview.png)
- [Downloaded YD-ESP32-S3 reference STEP](YD-ESP32-S3.step)
- [Reference repository licence](YD-ESP32-S3-LICENSE.txt)

## ESP32 Reference Assembly

Both the native SolidCraft design and the reference JSON assembly now include
the downloaded YD-ESP32-S3 model inside the base. The lid remains beside the
base for visibility. The enclosure-only STEP and printable STLs are unchanged.
The imported component is named ESP32_S3_REFERENCE_NOT_FOR_PRINT: exclude it
from any print export. Open the reference JSON as a SolidCraft design, not as
a command script.

This is an approximate dual-USB-C DevKitC-clone reference, not a confirmed
model of the purple ESP32-S3 N16R8 board shown in the user's photo. Its main
PCB measures 57.15 x 27.94 x 1.02 mm including modeled surface details; the
antenna extends beyond that PCB. Do not substitute these measurements for
measurements of the actual board. The STEP includes fitted pin headers,
whereas the photo shows the headers separately.

Placement is a 90-degree world-X rotation followed by a 180-degree world-Z
rotation and translation [0, 0, 11.01]. The PCB underside is Z = 10 mm,
2 mm above the existing support pads for nonconductive foam tape. Reference
bounds are approximately [-29.2088, -13.975, 2.31] to
[34.815, 13.975, 14.22]. The modeled header pins clear the 2 mm floor by
0.31 mm; highest modeled components clear the lid underside by 5.78 mm.
These are geometric reference clearances, not manufacturing tolerances or
a complete interference assessment with the unmodeled IR board and wiring.

Both USB-C sockets face the negative-X access opening. Their fronts are
approximately 9.79 mm behind the outside wall, so actual cable plug reach
must be checked. The reference has deliberately not been slid into the wall
or used to silently change the support locations or enclosure. A future
fit revision may need to move the board, change supports, or recess the wall.

The imported STEP has one open-body warning and several small-detail
face-wrapping warnings. There are no failed timeline features, but this
third-party import is for visual reference rather than precision collision
or mass calculations. The PCB volume is preserved through the rigid moves
(1555.390290 mm^3). Enclosure volumes remain 21118.191621 mm^3 for Base and
6370.019247 mm^3 for Lid.

Model by David Scambell, originally published at
[GrabCAD](https://grabcad.com/library/yd-esp32-s3-1), downloaded from
[shkuznetsov/YD-ESP32-S3](https://github.com/shkuznetsov/YD-ESP32-S3) at commit
bb410449c3d5ee20096ff273d6c1081c5dd6228f. The repository publishes an MIT
licence with a manufacturer-licensing caveat and credits the original model
author. Its licence is retained alongside the unmodified STEP.

Source STEP SHA-256:
EDC0685479A0C1A91ABD1ADF4516EC2784258A58095663B3F4272A125D5CF624.

## Dimensions And Assumptions

All dimensions are millimetres.

| Item | Value | Status |
| --- | --- | --- |
| Base outside | 78 x 52 x 20 | Modeled and measured |
| Wall / floor / lid plate | 2 | Modeled |
| Exterior corner radius | 4 | Modeled |
| Closed case height, excluding IR deck | 22 | Derived |
| Maximum plastic height when assembled | 22 | Derived; IR optics protrude through the opening |
| ESP32 PCB envelope | Approximately 62.8 x 25.4 | Nominal assumption; verify actual revision |
| ESP32 support tops | Z = 8 inside base | Four foam-tape pads, not PCB screw holes |
| USB access, negative-X end | 26 wide x 8 high; Z = 7 to 15 | Cable and connector fit unverified |
| IR PCB | 30 x 20 | ESTIMATED, not supplied by seller |
| IR hole spacing | 24 x 14 | ESTIMATED, not supplied by seller |
| IR hole diameter | Approximately 3.2 | ESTIMATED; not represented as PCB geometry |
| IR mounting | Flush beneath lid | Four 4 mm-wide fingers with 2.8 mm clearance holes |
| IR optical window envelope | 36 x 26 | Through-cut, except for the four mounting fingers |

The listing photographs show four emitters, a receiver, and four corner
mounting holes, but contain no mechanical dimensions. Its linked PDF could
not be extracted. No fitted IR model or full interference simulation was
used. An approximate ESP32 reference is available in the separate assembly
described above. This is not a guaranteed-fit enclosure.

The corrected lid has a real through-window: the former solid deck, raised
guard, and raised mounting posts have been removed. Mount the IR PCB beneath
the lid, component side facing out through the opening. Four narrow mounting
fingers remain at the estimated PCB hole positions. The board is inside the
case, while the LEDs and receiver must protrude through the window. Verify
their clearance from the mounting fingers and the 2 mm lid thickness, along
with clearance to the ESP32 and wiring below. Exact component positions and
heights are not verified, so unobstructed optical coverage must be checked
with the actual module. The case is not waterproof, dustproof, or certified
for unattended installation.

## Assembly And Printing

1. Check actual IR PCB dimensions, mounting-hole pitch and diameter, header
   position, and component heights before committing to a full print.
2. Print both parts with their flat Z = 0 undersides on the bed. The lid STL
   retains its print-layout X offset; use the slicer's arrange/center command.
   PETG, 0.2 mm layers, and four perimeters are reasonable starting settings.
   Check the 26 mm USB bridge in the slicer; local supports may be needed.
3. Orient the ESP32 length along X with both USB connectors toward negative X.
   Use thin nonconductive foam tape on the four support pads. Check that pads
   do not contact underside components, that pin tails clear the floor, and
   that the antenna and wiring have adequate clearance. Reposition the support
   features if your board requires it. Board retention is adhesive, not screws.
4. Keep the IR wiring inside the case. The former separate wiring slot is
   absorbed into the larger optical opening. Check header and wire clearance.
5. Mount the IR PCB flush beneath the four lid fingers, with its LEDs and
   receiver facing outward through the window. Use four M2.5 through-bolts
   with washers and nuts, approximately 8 mm long for a 1.6 mm PCB; verify
   actual stack thickness and avoid contact with circuitry. The lid holes
   are 2.8 mm through-clearances, not self-tapping pilot holes. Check that
   component bodies and screw heads do not obstruct the optics. If they do,
   adjust the window or mounting fingers to measured component positions.
6. Close the lid with four suitable plastic-thread-forming M2.5 x 10 screws.
   Lid clearance holes are 2.8 mm and base pilots are 2.1 mm x 12 mm deep.
   Check a pilot-hole coupon with your material and screws; do not overtighten.

In CAD, assemble the lid by translating it [-92, 0, 20] from the default
print layout. The general translation is [-lid_X, 0, case_H]. No locating lip
is provided; the four screws align the lid.

## Parameters And Checks

Favourite driving parameters have these tested endpoint ranges:

| Parameter | Default | Tested range |
| --- | --- | --- |
| case_L | 78 | 78 to 82 |
| IR_pitch_X | 24 | 24 to 26 |
| IR_pitch_Y | 14 | 14 to 16 |

Other driving dimensions are documented as fixed. IR_PCB_L and IR_PCB_W are
reference-only estimates: changing them does not resize the window.
IR_window_L = 36, IR_window_W = 26, and IR_tab_W = 4 are fixed dimensions.
Changing IR mounting pitches moves the clearance holes and mounting fingers,
rather than providing physical slots. Larger changes require a new clearance
and geometry check. Earlier deck features remain in the timeline, but the
final named removal and window features replace their geometry.

Endpoint changes and returns rebuilt without errors. The single sketch has
zero degrees of freedom. The checked timeline has no errors or warnings.
The corrected lid was checked at the same parameter endpoints and restored
to defaults. The base geometry is unchanged.

| State | Analytic volume, mm^3 | Measured volume, mm^3 |
| --- | --- | --- |
| Base, case_L = 78 | 21118.2955 | 21118.1916 |
| Corrected lid, case_L = 78 | 6370.0106 | 6370.0192 |
| Base, case_L = 82 | 21822.2955 | 21822.1960 |
| Corrected lid, case_L = 82 | 6786.0106 | 6786.0202 |
| Corrected lid, IR_pitch_X = 26 | 6370.0106 | 6370.0192 |
| Corrected lid, IR_pitch_Y = 16 | 6338.0106 | 6338.0192 |

Differences are below 0.001 percent. The default base bounding box is
[-39, -26, 0] to [39, 26, 20]; the lid is [53, -26, 0] to [131, 26, 2].
The predicted default X centers of mass are 0.748545 and 92;
measurements are 0.748549 and 92. The lid Z center of mass is 1.
Top views were checked for the through-window and mounting fingers.
Physical fit, IR performance, and
slicer/manufacturing validation remain outstanding.

Independent volume formulas, with P = pi and L = case_L:

```text
A = 52*L - (4-P)*16
B = 48*(L-4) - (4-P)*4
Base = 20*A - 18*B + 18*(256-4*(4-P))
       + 4*P*2.5^2*6 - 4*P*1.05^2*12 - 416 - 288
WindowArea = IR_window_L*IR_window_W
             - 4*IR_tab_W*(IR_window_W/2 - (IR_pitch_Y-IR_tab_W)/2)
Lid = 2*A - 2*WindowArea - 8*P*1.4^2*2
```

## Sources

- [IR module listing](https://de.aliexpress.com/item/1005013021929851.html)
- [Espressif DevKitC-1 v1.1 documentation](https://docs.espressif.com/projects/esp-dev-kits/en/latest/esp32s3/esp32-s3-devkitc-1/user_guide_v1.1.html)
- [Espressif mechanical drawing](https://dl.espressif.com/dl/schematics/esp_idf/DXF_ESP32-S3-DevKitC-1_V1.1_20220429.pdf)