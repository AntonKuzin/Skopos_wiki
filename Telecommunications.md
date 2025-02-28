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

### How to choose the optimal antenna
First off, let's cover some basic terminology. An omnidirectional antenna transmits in all directions equally. It's like a candle - it provides light in all directions, but this light isn't very bright. A directional antenna, on the other hand, transmits primarily in one direction - just like a flashlight. Omnidirectional antenna is never the best choice, unless you know exactly what are you doing.

Next term is beamwidth. The beamwidth forms a transmission cone - all radio energy is getting focused inside this cone, but not equally distributed. This is the angle $\alpha$ between the cone axis and the half-lines.

![image](https://github.com/user-attachments/assets/eeb14c57-615a-4218-8331-2da9b707fa4b)

Now let's bring in some math.
![image](https://github.com/user-attachments/assets/862c3a1c-4e97-4a4b-83b0-1d96f602d5a0)

$$H=SG\geq\frac{R}{sin(\alpha)}-R=R\left(\frac{1}{sin(\alpha)} -1\right) $$ - this equation is used to calculate the minimum orbit's heigth for a given beamwidth, which allows to cover the whole visible Earth's disk.

$$\alpha \geq arcsin\left(\frac{R}{H+R}\right)$$ - this equation is used to calculate the minimum antenna's beamwidth for a given altitude(for example, when designing a geostationary satellite)

$$\beta = arccos\left(\frac{R}{H+R}\right)$$ - this equation is used to calculate the angular radius of the visible Earth's disk. For equatorial plane this angle is the maximum latitude visible from the satellite.

If you did everything right, this is how your antenna cones should look like - the 10dB(outer) cone just barely touches the Earth.
![image](https://github.com/user-attachments/assets/e0d412fd-6f50-462b-bb21-5867304b4456)


### Power requirements

Now let's talk power. In order to figure out how much transmit power our antenna should have, we need to use the antenna planner.
![image](https://github.com/user-attachments/assets/37ae3f74-3fd5-4a37-9efb-af788c67f327)

Click the Antenna planner button(1), choose the desired ground station and set the desired orbit's altitude. First, crank the transmit power slider(2) all the way to the right to get an idea about the upper theoretical bandwidth limit(check the achieved rate (3)). After that, adjust the power slider to the lowest value still allowing to transmit at max rate(or the rate of your preference). Done!? Not yet. The problem is, the antenna planner doesn't take into account pointing losses. For example, if we want to transmit to Moscow from an equatorial satellite aimed at the center of the Earth, we're gonna experience significant pointing losses, thus never achieving the planned rate. What should we do? Add more power! How much? Remember the 10dB cone mentioned earlier? It's called that for a reason - any station located at the very edge of the transmission cone, will experience exactly 10dB of pointing losses! So, all we need to do is to add 10 dBm(+1 for margins) of transmit power and we're done!

It's worth noting that not all ground stations are equal. If your satellite serves a connection for a station weaker than planned, it's gonna need to use more power than expected. But I'm sure now you'll be able to deal with such kind of issues.

It's also worth noting that the transmit power distribution inside the cone is not uniform. The outer(white) cone is a 10dB cone, the inner one(pink) - 3dB. So the losses are >3x lower, but the angle for 3dB cone is only half of the outer one. So it may be beneficial to use a lower gain antenna with lower pointing losses if you're short on power.
