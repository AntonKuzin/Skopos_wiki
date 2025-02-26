# Tips for RP-1 telecommunications contracts

## Constellation design

A single satellite in MEO (at a sufficiently high altitude to be above the horizon for the stations to be linked) should be sufficient to satisfy all of the experimental contracts. However, bear in mind that once sustained connections are required, more satellites are needed. The following are possible:
- A constellation of satellites in inclined MEO,
- A GEO satellite for each link (e.g., one above the Atlantic, one above the Pacific, etc.),
- A Молния constellation.

Other options are possible; for instance, an MEO constellation providing some basic global level of service could be complemented by GEO or Молния satellites providing additional capacity in some regions.

The ground stations for the telecommunications contracts up the mid-seventies are large dishes with a lot of transmission power. It is therefore viable to use relatively modest antennas on the satellites for ground-to-satellite and satellite-to-ground communications.  In contrast, intersatellite communications are for all practical purposes outside the reach of the technology available in that timeframe. If a link cannot be established directly, it is best to bounce the signal between the ground and relay satellites in space.

Always keep geometry in mind when designing your constellations. Satellites can only serve as a relay between two ground stations if they are visible from both, and, all other things being equal, perform better when they are higher above the horizon. A 5000 km orbit with a 50° inclination will provide some coverage on the North Atlantic link, and can form the basis for a useful constellation; an equatorial 5000 km orbit will be useless, as it will always be either under the horizon or very low above it for the ground stations near 50° N.

## Spacecraft design

The following transmitter powers are viable for experimental and level 1 contracts on the transatlantic link:
* 2 W (33 dBm) for an omnidirectional antenna in MEO;
* y W for an omnidirectional antenna in GEO;
* z W for [dish type] in a Молния orbit.

The ground stations of the Монлиня network are smaller, so more power is required; for experimental and level 1, the following are appropriate:
* x W for an omnidirectional antenna in MEO;
* y W for an omnidirectional antenna in GEO;
* 20 W (43 dBm) for a RA-2 1 m parabolic antenna in a Молния orbit.
