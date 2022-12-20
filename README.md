## PCB_Ibanez_FL-9_Flanger
 An as-built schematic, PCB, and service guide to help with the repair of the Ibanez FL-9 Flanger guitar pedal.

 NOTE: At this time, the reverse-engineered PCB design is only useful for relative component location -- the design is non-functional and cannot be fabricated as-is. However, the process to convert a photograph of the traces into a copper layer was tested during this re-engineering project. Further work needs to be done to process the photograph to eliminate shadow and reflective anomolies before a practical test can be conducted. That's on the to-do list.

![PCB 3D rendered view](https://github.com/CedarGroveStudios/PCB_Ibanez_FL-9_Flanger/blob/main/PCB/Ibanez_FL-9_glam_top.png)

A thank you to [Mystic Effects Co](https://mysticeffectsco.com) for a helpful and inspiring FL9 capacitor replacement blog post. Also to Panasonic for continuing to maintain on-line datasheets for the bucket brigade delay and clock driver chip set. Let's not forget how great it is that DigiKey still stocks fresh through-hole capacitors in their produce aisle.

---
### What’s A Flanger?
Flanging is a time delay effect that originated in recording studios when a track was delayed slightly by touching the outer edge of a tape recorder reel with a finger. Mixed with the source input signal (the *dry* signal), the effect caused a filtering effect that caused different frequency bands to be enhanced or quieted slightly. When the signal delay was varied (swept), the peaks and valleys of the filtering simulated a “whoosh” effect.

The Ibanez FL9 pedal (made in Japan by Maxon) is a hybrid analog/digital delay design that uses a *bucket-brigade* integrated circuit to sample slices of the input signal then slightly delays the output of the slices. The overall time delay as well as sweep depth and width are adjustable. The feedback control helps to enhance the effect by adding a portion of the effect signal back into the input of the delay.

---

## Ibanez FL9 Flanger Guitar Pedal Repair Process

The flanger effect was sounding weak. The width and depth of the flange effect wasn’t as dynamic as when the pedal was new just 35 years ago. Replacing the battery didn’t make any difference. Even after cleaning the potentiometers, it still wasn’t working correctly. We’ll pop the covers and take a look.

Here’s what was found. Patches of the underside of the PCB were corroded. Apparently after decades of use, a few of the aluminum electrolytic capacitors leaked some of their semi-liquid dielectric fluid which quickly attacked the solder joints and copper traces. In one case, the fluid ate away all of the solder for one component, disconnecting it from the circuitry. 

It’s expected that after decades of use, some electronic components would begin to age. The first to go are usually aluminum electrolytic capacitors. And to be safe, all of the aluminum electrolytic capacitors will be replaced — not just the damaged ones — to prevent future capacitor leakage. Hopefully for at least another 30 years. 

The first step in repairing the PCB is to remove the damaged capacitors and as much of the corrosion as possible. After cleaning, the surrounding PCB traces will be tested for continuity

### Remove Damaged Capacitors and Clean the PCB
Examination of the board revealed that capacitors C130, C131, C132, C133, and C135 had caused the damage so they were removed first to permit cleaning and examination of the circuit traces. In this case the primary solder removal tool was a professional solder sucker for component leads. A flux-impregnated copper braid was very helpful for removing excess solder from larger areas.

The component side of the PCB was inspected to check for damage of surrounding components. No damage to the top side of the PCB was found.

Next, the damaged areas were thoroughly cleaned with isopropyl alcohol to remove the corrosion and any ancient solder paste.. Finally, stainless steel probes and 400 grit emory cloth were used to remove any remaining oxidation. This is a critical step in the process that requires a very light touch. Let the probes’ weight control the pressure and don’t over do the emory cloth — the copper traces are very thin and can disappear if abraded or picked at too much. It’s nearly impossible to completely recondition the copper circuit traces, so be very careful. 

The continuity test revealed five broken copper traces within the damaged areas. We’ll fix those as we replace the surrounding capacitors. 

A list of the remaining electrolytic capacitors was made by examining the schematic. In addition to those already removed, capacitors C109, C116, C120, C125 were targeted for replacement. Three non-polarized aluminum electrolytic capacitors, C110, C115, and C117 were also put on the list for a total of 11 components.

An order was placed with DigiKey for the replacements including a film capacitor upgrade for C116 and a new film capacitor to replace C121 that was damaged during the removal process. While waiting for the order to be received, a new reverse-engineered schematic and PCB component layout was prepared to help locate the capacitors that needed to be replaced. See the section, Reverse Engineer the PCB for more details. 

### Remove and Replace Remaining Capacitors
Once the targeted capacitors were located on the PCB (thanks to the reengineered board layout diagram), each component was removed. The solder sucker tool worked for most and left the traces intact. As each old capacitor is removed, the value and rating were verified with the schematic. When all were removed and new capacitor installation, another inspection of the copper traces was conducted.

Fortunately the component side of the PCB was accurately labeled with each capacitor’s polarity. For the aluminum electrolytic variety, the polarity is marked on the component indicating the negative (-) connection. And to make things easier, the marking on the PCB looked similar to that shown on the component layout legend. The negative wire of the replacement capacitors from DigiKey negative wire was also cut slightly shorter than the positive to aid in identification and insertion into PCB holes. 

Before installing each new capacitor, it was inspected for any signs of distress or leakage. The capacitance value and voltage rating were double-checked and verified with the schematic’s listed component value.

Each a new capacitor was allowed to float very slightly above the circuit board to reduce the stress on the capacitor’s lower seal, hopefully to increase its life span. Once in the holes, the leads were bent slightly to hold the capacitor in position for soldering. Only enough solder was used to cover the open hole and to spread slightly, similar to the factory’s soldering technique.

To minimize value and polarity errors, one capacitor was replaced and soldered at a time. We’ll leave en masse replacements for the more advanced folks who can flawlessly multitask.

For areas with damaged traces that should have been connected to a new capacitor, bent component leads were shaped to follow the damaged track and solder was applied along the length of the wire. This technique is an acceptable way to bridge trace damage and restore continuity. For other damaged tracks, a short leftover component wire was soldered over the break.

Don’t be tempted to apply solder to areas where copper was exposed due to corrosion. It will make repairs more difficult in the future. Instead, we protected the exposed copper traces from oxidation with a conformal coating after the pedal was completely repaired and tested. 

One more inspection was conducted after replacing all capacitors and repairing the damaged copper traces. Can’t be too careful when getting ready for applying power to test the reconditioned pedal. 

### Testing and Calibration
When a 9-volt battery was connected, the pedal started working normally. The first check was the red LED. It toggled on and off when the pedal switch was pressed and the voltage on test point CP14 changed appropriately. The static voltage test points +BATTERY, CP2, CP3, and CP10 were checked next. Everything looked nominal. Time for a signal test.

A 2.5-volt peak-to-peak 440Hz sine wave signal was applied to the input jack for further testing and calibration. The output signal was monitored first. It behaved normally in bypass and effects modes and it seemed to change as designed when effect parameters were adjusted. This was a very good sign.

The schematic identifies test points that track the progress of the input signal through stages of the effect as well the calibration of the delay clock and sweep oscillators. All waveforms, clock frequency, and sweep oscillator parameters were nominal and required no adjustments. For a full description of the calibration and adjustment process along with oscilloscope images of the expected waveforms, refer to the new FL9 Service Guide.

The pedal passed all bench tests and was ready for the final test with a guitar input signal. The pedal’s owner, a virtuoso guitar player exclaimed, “The pedal really works great! Brings back memories.” We’ll consider this project completed.

### Reverse Engineer the PCB
The schematic and board layout diagrams in the copy-of-a-copy original service manual were very difficult to discern. In the process of photo-adjusting the old page images, it was decided that starting over with a KiCAD schematic and PCB design would take about the same amount of time and would produce a high quality set of images. So while waiting for the DigiKey capacitor orders to arrive, the reverse-engineering process began.

As with any KiCAD project, it began with the schematic. The layout of the original schematic was preserved as much as possible. Many of the artifacts of the original were corrected and as-built updates to component values were noted.

The most important byproducts of the reverse engineering effort were the component placement layout graphics. This involved a multi-step approach to painstakingly reproduce the original component graphic over a new photograph of the copper traces on the bottom of the PCB. The layout diagrams were pivotal in locating and replacing components as well as finding test points for the final portion of the endeavor. 

As it turned out, the original component diagram was true to scale and once overlayed with the KiCAD PCB component layout, it provided the details needed to build a fairly accurate 3D model of the circuit board. That also meant that it would be a relatively simple exercise to add the hand-drawn copper trace layer to the PCB and send it off for manufacturing, should the need ever emerge. 

Matter of fact, a version of the PCB photo was converted to a copper layer and successfully applied to the KiCAD layout. But since the bucket-brigade delay integrated circuits are no longer manufactured and therefore difficult to source, manufacturing a new PCB would just be an educational exercise. We’ll send off an order for an OSH Park After Dark version soon.

[KiCAD PCB Design](https://github.com/CedarGroveStudios/PCB_Ibanez_FL-9_Flanger/tree/main/PCB)

### The New Service Guide 
A new service guide was compiled using the updated schematics and board layout from the reverse-engineering process along with some of the information from the original copy-of-a-copy service manual.

The new service guide includes an improved functional block diagram, readable component layout diagrams, a comprehensive troubleshooting guide, test point legend and waveform diagrams, and a reference schematic with a list of all components.

[New Service Guide](https://github.com/CedarGroveStudios/PCB_Ibanez_FL-9_Flanger/blob/main/docs/new_service_guide/Ibanez_FL9_Service_Guide.pdf)

### Tools and Materials

