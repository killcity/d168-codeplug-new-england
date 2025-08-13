# Anytone D‑168 / Airiton DM-168 New England Codeplug Overview - v1.07 FW

This repository contains a **codeplug** for the **Anytone D‑168** / **Airiton DM-168**  handheld radio.  The configuration is tuned for ham operators in the New England area and was built by combining several data sets of repeater information and talkgroups.  The resulting `.rdt` file programs the radio with hundreds of digital repeaters and a small set of analog FM channels, organised into zones for easy navigation.

The codeplug focuses on **digital DMR repeaters** connected to the New England Digital Emergency Communications Network (NEDECN) and other BrandMeister talkgroups, but it also includes analog FM repeaters for local nets.

**DO THIS FIRST: Set your DMR ID and Callsign in the Radio ID option under "Digital"**

If you get a mode error, create a new empty codeplug, choose the Model menu dropdown, then choose Commercial Europe as the mode. Save and write to the radio. Then open and load this .rdt file, write to radio.

## Channel overview

The codeplug defines **1585 channels**.  Each channel specifies the receive frequency, transmit frequency, timeslot (for DMR), colour code and a target talkgroup.  Channels fall into two categories:

| Mode | Count | Description |
|---|---|---|
| **Digital (DMR)** | **1561 channels** | These channels program every NEDECN and BrandMeister repeater within range of New England.  Each entry sets a *Colour Code* (values from 0 to 13) and Time Slot 1 or 2.  The radio transmits at either *Turbo* or *High* power with a 12.5 kHz bandwidth.  Repeater settings are derived from authoritative sources; for example, Shapleigh’s **K1DQ** repeater uses Colour Code 4, while the Sagamore/Bourne **K1RK** repeater uses Colour Code 10. |
| **Analog (FM)** | **24 channels** | A small set of conventional FM repeaters are included for local nets and simplex work.  Each analog channel sets a CTCSS tone for encode/decode, high power and either 12.5 kHz or 25 kHz bandwidth.  Examples include **W1XM MIT (449.725 MHz)**, **W1GLO Gloucester (145.130 MHz)** and **K1BOS Boston (146.820 MHz)**.  These analog channels are collected in a dedicated “Analog R” zone. |

### Colour codes

Digital repeaters in the codeplug use colour codes from **0** through **13**.  These codes are critical for opening the correct timeslot on each repeater.  Colour codes were assigned according to the official NEDECN listings—for instance, the Shapleigh repeater uses **4** and the Sagamore/Bourne site uses **10**.

### Talkgroups

The DMR channels reference **29 unique talkgroup IDs**, all set up as **Group Calls**.  The most frequently used talkgroups in the codeplug are:

| Talkgroup ID | Name | Channels using it |
|---|---|---|
| **1** | WorldWide 1 | 97 |
| **9** | Local 9 | 96 |
| **3172** | Northeast | 95 |
| **3181** | New England | 95 |
| **8801** | NE TAC 1 | 93 |
| **310** | TAC 310 | 92 |
| **311** | TAC 311 | 92 |
| **3** | North America 3 | 92 |
| **8802** | NE TAC 2 | 91 |
| **9998** | Parrot/Echo test | 89 |

Other talkgroups include WW English, WorldWide Portuguese, national calling channels and several TAC channels.  Each talkgroup has been defined with the appropriate call type and alias.

## Zones

To make the large channel set manageable, the codeplug organises channels into **99 zones**.  Each zone can hold up to sixteen channels and designates “A” and “B” channels that appear on the radio’s dual‑display.  Zones are grouped geographically or by function.  A few examples:

* **Analog R** – a catch‑all zone containing all 24 analog FM repeaters for quick access.
* **COVENTRY CT**, **KILLINGLY CT**, **MONROE CT**, **NORTHFORD CT**, etc. – zones for individual towns in Connecticut.
* **ACTON MA 2M**, **ANDOVER MA**, **BARNSTABLE MA**, etc. – Massachusetts zones arranged by town or county.
* **MAINE** and **NEW HAMPSHIRE** – state‑wide zones that combine multiple NEDECN repeaters.

If a channel is not assigned to a zone, it will not appear on the channel knob, so these zone definitions are essential for navigation.

## Talkgroups and contacts

All transmissions in this codeplug use **Group Call**; there is no per‑user digital contact list defined.  The radio’s built‑in contacts database or dynamic talker alias is used to display call signs.  Likewise, no separate receive group lists are programmed—each digital channel receives only the talkgroup that it transmits on.

## Other settings

The codeplug also defines the radio’s behaviour outside of channel programming:

* **Global settings** – backlight behaviour, key beeps, time‑out timer, power‑on display, battery saver and other options are tuned for field use.  APRS is disabled on most channels but can be enabled if needed.
* **FM broadcast** – a single commercial FM preset (88.0 MHz) is included so the radio can tune FM broadcast radio during emergencies.
* **Signalling** – Two‑tone, five‑tone, DTMF and encryption tables are present but largely unused; the codeplug does not employ voice encryption or selective calling.

## Summary

This D‑168 codeplug aims to be a complete solution for amateur radio operators in New England.  It programmes **over 1 500 DMR channels**, each with the correct colour code and time slot for its repeater, and organises them into **99 zones** for easy selection.  The most common talkgroups—including WorldWide, Local 9, Northeast and New England—are available on every repeater, and analog FM channels ensure compatibility with local nets.  To use it, load the provided `.rdt` file into Anytone’s CPS and write it to your radio; no CSV files are required when deploying the final codeplug.
