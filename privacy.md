# Privacy Policy

**ISS Repeater for iOS · Last updated 9 September 2026**

> **The short version:** ISS Repeater collects nothing. There are no accounts, no
> analytics, no advertising, no tracking, and no server belonging to this app for
> anything to be sent to. What you enter stays in the app's own storage on your
> phone.

## Information the app does not collect

ISS Repeater does not collect, transmit, sell, or share personal information. It
contains no analytics or advertising SDKs, no crash-reporting service, and no
user accounts. Nothing you enter is uploaded to any service operated by this app
or its developer.

## Permissions, and what happens if you decline

All three permissions below are optional. The app asks for each only at the
moment the feature needs it, and every one of them can be refused or revoked
later without the app becoming unusable.

| Permission | What it is used for | If you decline |
| --- | --- | --- |
| **Location**<br>(While Using the App) | Filling in STATION 01's coordinates, and pointing the sky finder from where you are actually standing. | Type coordinates, or drop a pin on the map, instead. Every feature still works. |
| **Camera** | Showing the live view behind the sky finder's overlay, so the ISS can be marked against the real sky. | The finder still works. The horizon, arc, bearings and ISS marker are drawn over a blank panel instead of the camera image. |
| **Notifications** | A local reminder ten minutes before a pass on your saved list opens. | No reminders. Everything else is unaffected. |

Motion sensors need no permission on iOS for the way this app uses them, and are
covered below.

## Location

The app requests **"While Using the App"** access only. It never requests Always
access and never runs location in the background — when the app is not on
screen, it is not reading your location. It also asks iOS for roughly 100 metre
accuracy rather than the finest fix available, because that is all pass geometry
needs.

Location is read in two places:

- **STATION 01's coordinates.** If you turn on "Use current location," the app
  asks iOS for a *single* fix and shows the resulting latitude and longitude in
  the coordinate field. That value is used on the device to compute pass
  geometry.
- **The sky finder (LIVE VIEW).** While the sky finder is open, the app reads
  your location continuously, so the ISS's position in the sky and the
  magnetic-declination correction are computed from where you are standing.
  Updates stop the moment you leave that screen. If location is off, the finder
  points from STATION 01's typed coordinates instead.

Your location is not sent to any server operated by this app, because there is
no such server. One indirect case is worth naming plainly: if you open **SELECT
FROM MAP**, the map opens centred on whatever coordinates are already in that
station's field, so Apple's map servers receive a request for imagery of that
area. See [Network requests](#network-requests) below. If you would rather that
not happen, type coordinates instead of using the map.

## Camera

The sky finder shows the rear camera's live view so the ISS can be marked on the
real sky. The preview is displayed on screen and nothing else: no photo or video
is captured, saved, analysed, or transmitted. The app installs no capture output
of any kind — frames go from the camera to an on-screen preview layer and
nowhere else, so there is nothing to store or send.

## Motion sensors

The sky finder reads the phone's gyroscope, accelerometer and magnetometer to
know which way the camera is pointing. Those readings are used on the device for
the frame being drawn and are not recorded, accumulated, or transmitted.

## Data stored on your device

Stored locally, in the app's own storage, and never sent anywhere:

- The station coordinates you entered or picked.
- Your settings — station mode, search span, time zone, minimum elevation,
  units, range limits, night mode, notification preference, and any manually
  entered element set.
- The passes you have saved, with the coordinates and settings they were
  computed from.
- A cached copy of the ISS orbital element set.

None of it is backed up to a server by the app. Deleting the app removes all of
it from the device.

## Network requests

The app makes two kinds of outbound request, neither of which carries personal
data:

- **Orbital elements.** Fetching current two-line elements for the ISS from
  [CelesTrak](https://celestrak.org/), with [AMSAT](https://www.amsat.org/) as a
  fallback. These are public, read-only feeds. The request carries no
  identifiers — not your coordinates, not your settings, nothing about you or
  your device beyond a fixed application name sent as the User-Agent, which is
  the same for every copy of the app.
- **Map tiles.** When you open SELECT FROM MAP, Apple Maps (MapKit, built into
  iOS) loads map imagery from Apple for the region shown on screen — which, as
  noted above, starts centred on the coordinates already in the field. That
  request is made by iOS itself and is governed by Apple's privacy policy; the
  app sends Apple nothing beyond the region MapKit needs in order to draw the
  map. The map does not display or request your live device location.

As with any request to any website, the operators of those services can see the
IP address a request came from. Those services are operated independently of
this app and are governed by their own privacy practices.

Once elements are cached, the app makes no network requests at all unless you
refresh them or open the map. Searching, Doppler planning and the sky finder all
work with no connection.

## Notifications

If you enable notifications, reminders are scheduled locally by iOS on your
device from the passes on your saved list. There is no push server, no
notification token, and nothing is sent anywhere in order to deliver them.

## Children

ISS Repeater is a utility for amateur radio operators and satellite observers. It
is not directed at children, and it knowingly collects no information from
anyone, of any age.

## Third-party code and data

The app links [SatelliteKit](https://github.com/gavineadie/SatelliteKit) (MIT
licence) for orbital propagation. It is compiled into the app, performs no
network activity of its own, and collects nothing. Magnetic declination is
computed on the device from the World Magnetic Model published by NOAA's
National Centers for Environmental Information and the British Geological
Survey; the model is a table of numbers bundled with the app and involves no
network access. The full licence and attribution notices are in the app, under
**Settings → Acknowledgements**.

There are no other third-party libraries, and no third-party SDK in this app
receives any data.

## Your rights

Privacy laws such as the GDPR and the CCPA give people the right to see,
correct, or delete the personal data a company holds about them, and to know
whether it has been sold or shared. This app holds none: no personal data about
you is collected, received, stored off your device, sold, or shared with anyone,
so there is nothing to request, correct, or delete, and no profile exists to be
exported. The data listed under "Data stored on your device" is under your
control and is removed by deleting the app. If you have a question about any of
this, the contact address is below.

## Changes to this policy

If this policy changes, the revised version will be posted at this address with
a new "last updated" date.

## Contact

Questions about this policy: <issrepeater@gmail.com>

---

[← Back to the app overview](README.md)

SatelliteKit is used under the MIT licence; the full notice is in the app under
Settings → Acknowledgements. The World Magnetic Model coefficients are a work of
the United States Government and are not subject to copyright protection; the
model is provided by NOAA/NCEI without warranty of any kind, and NOAA and the
British Geological Survey make no representations as to its accuracy or fitness
for any particular purpose.

ISS Repeater is not affiliated with NASA, ARISS, AMSAT, CelesTrak, NOAA or BGS.
