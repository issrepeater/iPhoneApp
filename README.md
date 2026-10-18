<!-- This page describes version 1.1 (final text 2026-10-18). Upload it to
     the repo's README.md when 1.1 is live on the App Store; until then the
     live README should keep describing 1.0. -->

# ISS Repeater

**Plan and work contacts through the International Space Station's cross-band FM
repeater — for iPhone.**

Most satellite trackers tell you when the ISS passes over *you*. If you want to
talk to someone through it, that isn't quite the question. The station has to be
above your horizon **and** above the other operator's at the same moment, and
that shared window is usually a good deal shorter than either of your own
passes. ISS Repeater finds those windows, gives you a Doppler tuning schedule
for each one, and then helps you point an antenna at the pass.

**Questions, bug reports, or a pass that didn't line up?**
📧 **[issrepeater@gmail.com](mailto:issrepeater@gmail.com)**
Send the station coordinates and the date and time you were expecting, and it
can be reproduced exactly.

[**Privacy policy**](privacy.md) · No accounts, no analytics, no tracking,
nothing collected.

---

## Getting started

1. **Set STATION 01.** Type coordinates as `latitude,longitude` — for example
   `36.0834,-115.1539` — or tap **SELECT FROM MAP** to drop a pin, or turn on
   **Use current location** to use your phone's GPS fix. You can add an optional
   third value for altitude: `latitude,longitude,altitude`.
2. **Planning a contact with someone else?** Open **SETTINGS**, set **Station
   mode** to **DUAL**, and a STATION 02 field appears. Enter their coordinates
   the same way. Leave it on **SINGLE** if you just want to know when the ISS is
   overhead for you.
3. **Tap Calculate.** The app propagates the orbit and returns every window in
   your search span — 1, 3 or 7 days, set in Settings.
4. **Read the cards.** Each one is a single window. More on that below.
5. **Tap SAVE** on a window to keep it, or **LIVE VIEW** to open the sky finder
   and point at the pass.

> A fresh install starts with an example location (Las Vegas) so you can see
> what the app produces straight away. A notice under STATION 01 says so, and it
> disappears as soon as you set your own coordinates.

---

## Reading a window card

Each card is one pass window. The header gives the date and the start and end
times; the table underneath is the tuning schedule.

| Column | What it means |
| --- | --- |
| **MHz** (or **CHANNEL**) | The downlink channel to be **receiving** on — as a frequency, or as whatever you have named that memory on your radio (see *Channel display* below). |
| Under each station | Two stacked times: when to move to that channel, and when to leave it. |
| **ε₁ / ε₂** | The highest the ISS climbs above that station's horizon while it is parked on that channel. Higher means a stronger, cleaner signal. |

While a window is open, the active row is highlighted and the status bar at the
top counts down to STATION 01's next frequency change.

In **DUAL** mode you get a column for each station, because the two operators
are at different points on the pass and their Doppler shift differs. Both of you
can work from the same card.

### Channel names instead of frequencies

If your radio has the five downlink channels stored as memories, you can have
the app show your names for them instead of the numbers. In **Settings → Channel
display** choose **NAME**, tap **EDIT CHANNEL NAMES**, and type a name beside
each frequency. Names then appear on the cards, in the status bar, on the sky
finder and in reminders. A channel you leave blank keeps showing its frequency.

---

## Working a pass

The app tells you *when* and *what to receive on*. Here is how that fits into
actually making the contact.

1. **Before the pass.** Check the element set is current — the line at the top
   of the main screen shows its age. Pull down to refresh. Elements a few days
   old are fine; weeks old will drift, especially after a reboost, and the app
   says "stale" when it is time to worry.
2. **A few minutes out.** Open the window card, or open **LIVE VIEW** if you are
   pointing a directional antenna by hand.
3. **As the window opens.** Set your radio to the first channel on the card.
   The ISS is approaching, so it arrives high in frequency and drifts down as it
   passes — the schedule is already built around that.
4. **Through the pass.** Move to the next channel at each time the card gives.
   The status bar counts you down to the next change so you are not doing
   arithmetic in your head, and in LIVE VIEW the ISS marker — or the arrow,
   if the ISS is out of frame — flashes five times around each change.
5. **Peak elevation** is the best part of the window. If the pass is low
   (ε below about 20°) expect a weak, short contact.

### About the uplink

**The app schedules receive frequencies only.** Transmitting is your own
responsibility, per your licence class and national regulations.

For reference, the ISS cross-band FM repeater has generally used a **145.990 MHz
uplink with a 67.0 Hz CTCSS tone**, downlinking on 437.800 MHz. Configurations
change, and the repeater is not always the active mode — check
[ARISS](https://www.ariss.org/) for the current setup before you rely on it.

---

## The sky finder (LIVE VIEW)

Tap **LIVE VIEW** on any window card and hold the phone up. The camera fills the
screen, with the clock and the window countdown in a translucent bar across the
top, and over the sky:

- the horizon and the N/S/E/W bearing lines, with their letters,
- the whole arc of that pass across the sky, with the channel to be on written
  along each stretch of it,
- a marker on where the ISS is right now, with a box beside it showing the
  channel to be on — from five minutes before the window opens, and on any
  other pass whenever the ISS is above your horizon,
- an arrow pointing which way to turn when the ISS is out of frame,
- azimuth, elevation and range along the bottom.

**At each frequency change, the ISS marker flashes five times** — a second
before, half a second before, on the change, half a second after and a second
after — so you can keep your eyes on the sky and still catch the retune. If the
ISS is out of frame at that moment, the pointing arrow flashes instead.

**All bearings are TRUE, not magnetic.** The app carries the World Magnetic
Model and corrects for declination at your own coordinates, so what it shows
lines up with a rotator readout or a paper map. The correction in use is printed
under the readout.

### Live view settings

Tap **SETTINGS** in the sky finder's header for switches that control what is
drawn over the camera. Everything is optional except the ISS marker itself, and
everything starts switched on:

| Switch | What it shows |
| --- | --- |
| **Crosshair** | A fixed crosshair at the centre of the screen, for sighting a beam. |
| **HDG/EL for crosshair** | The true heading and elevation the crosshair is pointing at. |
| **N/S/E/W bearing lines** | The north–south and east–west lines across the sky. |
| **N/S/E/W labels** | The letters on those lines. |
| **Horizon** | The horizon line. |
| **Flight path** | The pass arc itself. |
| **Frequency labels** | The channel written along each stretch of the path. |
| **Frequency box at ISS** | The channel box beside the ISS marker, shown whenever the ISS is up. |
| **Window and retune marks** | The rings at the window's edges and the chevrons at each retune, on the arc — kept even with the path hidden. |
| **Status bar** | The clock and countdown bar across the top. |
| **Station position** | The azimuth / elevation / range readout along the bottom. |

#### Presets

Four buttons at the top of that page hold whole arrangements of switches:

- **ALL ON** and **ALL OFF** set every switch at once (ALL OFF leaves just the
  ISS marker and the arrow — the bare sky).
- **CUSTOM 1** and **CUSTOM 2** are two arrangements of your own. Pick one,
  set the switches the way you want them, and they are remembered under that
  button; pick the other and set it up differently. Each remembers whatever
  you last left it at — there is no separate save step.

**Tap to declutter.** Turn on the switch above the buttons and a tap anywhere
on the sky steps through the presets — ALL ON, CUSTOM 1, CUSTOM 2, ALL OFF,
round again — with the preset's name shown briefly at the top of the screen.
Useful with gloves, or with the phone held up at arm's length. A long press on
any preset button adds it to or removes it from that rotation; a tick in front
of the name shows which are in.

### If the compass says "Calibrating"

- Wave the phone in a figure-8 and step away from anything metal.
- A MagSafe case is a ring of magnets held against the back of your phone.
  Expect a few degrees of error with one fitted, and take it off if you need
  precision.
- If it never clears, iOS may not be permitted to calibrate. Check
  **Settings → Privacy & Security → Location Services → System Services →
  Compass Calibration** is on. It is near the bottom of that list.
- Bearings still work while calibrating; they are just less exact.

The finder also works with camera access switched off — you get the overlay on a
blank panel, and the bearings are just as accurate.

---

## Settings

| Setting | What it does |
| --- | --- |
| **Station mode** | SINGLE plans around the repeater from one station. DUAL finds mutual windows for two. |
| **Time zone** | LOCAL, ZULU (UTC), or any zone you pick. Drives the clock and every time in the results. |
| **Search span** | How many days ahead to look: 1, 3 or 7. |
| **Minimum elevation** | Ignore passes that never get this high. Starts at 0°; raise it if low passes are blocked by terrain or buildings. |
| **Altitude units** | Feet or metres — how the optional third coordinate value is read. |
| **Range units** | Nautical miles, statute miles, or kilometres. |
| **Range measured** | SLANT is the straight-line distance to the ISS; GROUND is measured along the surface. |
| **Max range from ISS** | How far from the ISS a station can be and still count as "in range," set on a slider. The top of the slider is the furthest anyone on Earth can see the ISS from — even from a mountain summit — so leaving it there means every pass; bring it down to keep only the closer, higher ones. Switching units converts the value. |
| **Channel display** | FREQUENCY shows the five downlink channels as numbers; NAME shows the names you give them under **EDIT CHANNEL NAMES**. |
| **Night mode** | Black background, red text — for use at the radio without wrecking your dark adaptation. |
| **Notifications** | A local reminder 10 minutes before each pass on your saved list opens. |
| **Enter TLE manually** | Paste your own two-line element set instead of the fetched one. |
| **Acknowledgements** | Licence and attribution notices for the third-party work the app is built on. |

The sky finder has its own settings page — see *Live view settings* above.

---

## Saved passes and reminders

Tap **SAVE** on any window card to add it to your saved list, reachable from
**SAVED** in the header. Saved passes keep their numbers current — when fresher
orbital elements arrive, the times are recalculated rather than left to go
stale.

Turn on **Notifications** in Settings and you get a local alert ten minutes
before each saved pass opens, naming the duration, the peak elevation, and the
channel to start on. Nothing is sent to a server; iOS schedules the reminders on
your device.

Swipe left on a saved pass to remove it, or use **CLEAR EXPIRED PASSES** to tidy
up ones that have already happened.

---

## Common questions

### Why did it find no windows?

In DUAL mode the two stations may simply be too far apart. The ISS has to be
above both horizons at once, which caps the usable separation at roughly 2,000
miles even for a perfect overhead pass. A too-high minimum elevation or a
too-short search span will also empty the list.

### Why are all the passes at similar times of day?

That's real, and it is correct physics rather than a 12/24-hour mix-up. The
ISS's orbit precesses slowly, so for several days at a stretch it passes over a
given site at similar local times, then those times drift earlier.

### How current are the orbital elements?

The app fetches a fresh two-line element set for the ISS on launch from
[CelesTrak](https://celestrak.org/), with [AMSAT](https://www.amsat.org/) as a
fallback, and caches it. Pull down on the main screen to refresh. The line at
the top of the screen reports two ages: how long ago the app last downloaded,
and how old the elements themselves are. The second is the one that decides
accuracy.

### Does it need a network connection?

Only to refresh the orbital elements, and to draw map tiles if you use SELECT
FROM MAP. Once elements are cached, searching, Doppler planning and the sky
finder all work entirely offline.

### The repeater didn't come up during a window.

The app predicts **geometry**, not the state of the equipment. The repeater is
powered down during some crew operations, EVAs and school contacts, and the ISS
occasionally runs other modes such as APRS packet or SSTV. A window means the
station is mutually visible — not that it is transmitting.

### Which frequencies does it schedule?

The downlink is centred on 437.800 MHz, and the app schedules five receive
channels spanning 437.790–437.810 MHz to track the Doppler shift across a pass.
See [About the uplink](#about-the-uplink) for transmitting.

---

## Privacy

ISS Repeater collects nothing. There are no accounts, no analytics, no
advertising, and no server belonging to this app. Your coordinates, settings and
saved passes stay in the app's own storage on your phone.

Full details: [**Privacy policy**](privacy.md).

---

## Acknowledgements

Orbit propagation uses [SatelliteKit](https://github.com/gavineadie/SatelliteKit)
by Gavin Eadie, under the MIT licence. Magnetic declination is computed from the
World Magnetic Model published by NOAA's National Centers for Environmental
Information and the British Geological Survey; the WMM coefficients are a work
of the United States Government and are not subject to copyright protection, and
the model is provided without warranty of any kind. Orbital elements come from
CelesTrak and AMSAT, who publish them freely for public use.

The complete licence texts are in the app, under **Settings →
Acknowledgements**.

---

*ISS Repeater is not affiliated with NASA, ARISS, AMSAT, CelesTrak, NOAA or the
British Geological Survey.*
