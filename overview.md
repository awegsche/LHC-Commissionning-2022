# 23.04 Start of Linear commissionning (Day 1)

- didn't start off with virgin optics, reusing corrections from beam test
- 2021 beam test optics verified

[plot of beta beat at injection]
[plot of disperions at injection]

## Shift Summary

### Done during shift
Optics at injection, ADT AC-Dipole, Kmod, DOROS, Chromaticity.
In more details:

- Measured the injection optics with the corrections calculated during the 2021 beam test and compared it to the nominal. It looks very similar to what we observed at that time, no corrections were re-calculated.

- The ADT AC-dipole had some issues with the settings but this was fixed together with Martin and we could then excite. The coupling correction is a bit low compared to the correct value but it converged nicely.

- K-modulation was attempted for IP1 and IP5, which worked fine. Some small issues remain in the interface between the acquisition and the analysis however. 
- Spent some time doing kicks for the BI people to look at the DOROS BPMs.
- Some kicks for many turns AC-Dipole.
- Measurements with to have a look at the chromaticity. The Q''' is significantly different than it was measured during the 2021 beam test.

### Results:

A folder with results for the day has been created at /afs/cern.ch/eng/sl/lintrack/LHC_commissioning2022/COM_2022_04_23_injection_validation
One can find there a folder with plots (and commands to reproduce them), another one with detected bad BPMs from SVD and IF cleaning, and Beam[12] symlinks to the location of analyses done for the day. See screenshot attached below.

**Follow up**: Calculation of chromaticity correction for tomorrow's shift.

**Problems**: Nothing important to report, at some point we lost the concentrator but this was later fixed

**Email to Tobias**:
what is the coupling in the ramp status? reiterated?

# 24.04 (Day 2)
## Shift Summary

### Done during the shift:

- Started with Q''' measurements to determine new Q''' corrections.

- The new MCS compensation scheme by Tobias was successfully tested for both beams. 

- The Q''' and Q'' corrections were implemented and and validated in chromaticity scans. 

- Amplitude detuning measurements were taken to validate the baseline with the new corrections in. Horizontal, vertical and diagonal kicks were performed. Small amplitude detuning is observed, but more thorough analysis will be needed to provide final values. 

- Decapolar resonance driving terms were measured for the first time at injection energy in the horizontal plane, namely H(0,±4) and H(±1,±3). A shift in Qy, was used to validate both the shift in frequency of the resonance line as well as the reduction of amplitude when moving away from the resonance.

- Removing the new Q''' correction results in the disappearance of the decapolar lines. This suggests a nonlocal correction of decapolar terms.

### Needed Follow-up:

- More thorough analysis of amplitude detuning.
- More in depth analysis will follow of the Q''' correction's impact on the decapolar lines.

# 25.04 Coupling in the ramp (Day 3)

-    We did the manual coupling measurement during the ramp because the coupling server failed to give good results (probably because of the S problem but this needs to be checked)
-    we calculated coupling corrections (verifying on the way that the selected model didn't deteriorate the calculations)
-    these were programmed in to be applied during the next ramp
-    re-measure showed that we corrected < 0.005 at every pick-up point
-    we are happy with this result

## Shift Summary

### Done during the shift:

- Analysis of kicks taken during the ramp to find out the coupling corrections. These were then trimmed in for subsequent ramps, which went better.
- Successfully got measurements at flat-top! First analysis of the machine at flat-top shows expected range of values for linear optics. 
- Had a look at local errors, tried trimming in the corrections Tobias had calculated for 2018 to see what segment-by-segment yields, and it seems the local errors are quite different this time around (corrections are too weak in IP1, too strong in IP5). Local errors seem similar to those found in 2012.

A folder in lintrack has been created that holds symlinks and plots. It is at /afs/cern.ch/eng/sl/lintrack/LHC_commissioning2022/COM_2022_04_25_flattop_optics/

### Needed Follow-up:

- Double check of the 2018 corrections calculated by Tobias.
- More in depth look at the local errors, may be worth it to try and find corrections so we can compare to the 2018 ones.

### IMPORTANT:

The models used today did not include MQTs extraction!
Felix S came back the next day to remake the analyses with correct models, helps quite a lot with the error bars. See the 2022-04-26 logbook page (tomorrow) for more information.
Attached are results analyzed that day.

Important too, the symlinks in `/afs/cern.ch/eng/sl/lintrack/LHC_commissioning2022/COM_2022_04_25_flattop_optics/` point to Results folders created on 2022-04-26 (but today is 2022-04-25) for the reason mentionned above. It is normal. There is a README there to explain this.

# 26.04. (Day 4)

## Shift Summary

### Done during the shift:

- Creation of models for yesterday's flattop measurements with correct error definitions (using fixed Beta-Beat.src) and MQTs extraction.

- Felix S did a re-analysis of yesterday's flattop measurements for B1 and B2 with correct models. 

- We took some time to cross-check the 2018 corrections that were calculated by Tobias. All seemed fine.

- Felix C (doctor Felix) and Jacqueline had a look at the local errors and tried to find some first step for phase corrections. Values are compared to the 2018 ones.

- Felix S (student Felix) had a look at local errors and tried to find some first step for coupling correction.

Relevant plots and scripts have been added to lintrack. They are available at /afs/cern.ch/eng/sl/lintrack/LHC_commissioning2022/COM_2022_04_25_flattop_optics/plots/flattop

# 27.04. (Day 5)

## Plan for the day

-    Measurements at 60cm for corrections
-    Measurements at 30cm for corrections

## Shift Summary
### Done during the shift:

- First measurements at squeezed optics have been performed. Measurements at 60 cm were done, with beta-beating to about 60%.
- Further measurements were done at 30cm. Initial analysis showed large beta-beating in the arc on the order of 150%. K-modulation measurements confirmed this large deviation of the optics and waist.
- Both turn-by-turn data and k-modulation data were used to calculate local IP5 corrections. Trimming in the corrections resulting in a very significant reduction of overall beta-beating to around 20% beta-beating in B1 (Beating measurement with Coupling of 0.03 gave initially a beating of 40%, so coupling can double beta-beating, see plot) and 30% in Beam 2.
- Further analysis produced possible IP1 correction candidates, that will be tested at a later stage.

Relevant plots and scripts have been added to lintrack. They are available at 

/afs/cern.ch/eng/sl/lintrack/LHC_commissioning2022/COM_2022_04_27_at30cm/plots


**Important** - An issue was found and resolved for the automatic matcher, where the MAD-X run would try to access memory out of range and crash. See this entry for an explanation and the solution: https://logbook.cern.ch/elogbook-server/GET/showEventInLogbook/3543202

- An important "bug" was found in the optics files that affects Segment-by-Segment since right side correctors are linked (deferred expression) to left side ones. See this entry for an explanation and the solution: https://logbook.cern.ch/elogbook-server/GET/showEventInLogbook/3543202

# 28.04 (Day 6)

## Plan for the day:
-    Ramp-up of ballistic optics
-    Measurements of ballistic optics at flattop

## Shift Summary


### Done during the shift:


- Measured during the ramp-up of ballistic optics to 6.5TeV. The coupling was enormous during the ramp so we lost half of beam 1 but beam 2 was fine.
- Measured ballistic optics but without degaussed triplet.

![img](images/day6-1.png)
![img](images/day6-2.png)
![img](images/day6-3.png)
![img](images/day6-4.png)

# 02.05. (Day 7)

## Plan for the day:

- Measurements at 133cm (end of ramp)
- Measurements at 60cm (mid-squeeze)
- Measurements at 30cm (mid-squeeze)