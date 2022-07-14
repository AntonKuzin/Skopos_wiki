Three types of contracts are considered:
1. Demonstrate a new capability, _e.g._, show that you can provide a transatlantic television channel;
2. Maintain a capability over the long term, _e.g._, keep providing a transatlantic television channel;
3. Milestone broadcasts; examples:
   - Broadcast the Olympics ([Tokyo 1964](https://www.nict.go.jp/publication/journal/11/058/Journal_Vol11_No058_pp363-376.pdf), [Mexico 1968](https://www.britishpathe.com/video/VLVAE4K8CWE482DWY4WXCVBW4B57D-USA-OLYMPIC-TV-CLIP), [Munich 1972](https://www.ebay.fr/itm/121367372570?hash=item1c420f231a:g:5q4AAOSws65Toxj5), [Montreal 1976](https://olympics.com/en/olympic-games/montreal-1976/torch-relay));
   - Worldwide telecast [*Our World* (1967)](https://www.youtube.com/watch?v=wbWMBiz2z7k);
   - Crewed spaceflight broadcasts, for instance:
     - [first spacewalk](https://ru.wikipedia.org/wiki/%D0%92%D0%BE%D1%81%D1%85%D0%BE%D0%B4-2);
       > Человек вышел в космическое пространство! Человек вышел в космическое пространство! Находится в свободном плавании!
     - [first live telecast of a launch](https://en.wikipedia.org/wiki/Gemini_4#Launch);
     - [first live telecast of a recovery](https://en.wikipedia.org/wiki/Gemini_6A#Objective);
     - [first steps on the moon](https://www.honeysucklecreek.net/images/Apollo_11/Apollo_11_EVA_TV_links_A4.pdf);
       > That’s one small step for a man, one giant leap for mankind.
     - subsequent moon landings.

# Connections

Two types of connection are considered:
1. Duplex connection;
2. Point-to-multipoint connection (includes point-to-point).

In both cases, the data rate is fixed, and there is a maximum latency for the basic service (round-trip latency in the duplex case).
Lower latencies can be required as an improved service.

For point-to-multipoint connections, service availability at each receiver is considered independently of the others.

Connections can be exclusive or non-exclusive.

In the non-exclusive case, the service is available if it is possible to provide it in the absence of network usage.
Providing the service does not affect network usage.
This corresponds to communications over existing network, such as milestone broadcasts,
or experimental communications, such as Telstar’s duplex telephone or one-way telecast (but not both at the same time).

In the exclusive case, the service is available only if it can be provided after network usage from higher-priority services is taken into account.
Providing the service contributes to network usage.
This corresponds to requirements of infrastructure capacity.

For instance, the evolving requirements of the transatlantic link might be
described by the following sequence of exclusive and cumulative services in decreasing priority, all with a basic service with 60 s round-trip-time, and an improved service (suitable for telephony) with 800 ms round-trip time.
| Lvl | approx. date | Level requirement | Cumulative equivalents |
|---|---|---|---|
| 1 | from 1965 | 15 Mbps duplex | 240 telephone circuits (probably means one-way television is alternatively possible)
| 2 | from 1968 | 30 Mbps duplex | 720 telephone circuits or 1 TV channel each way
| 3 | from 1971 | 60 Mbps duplex | 1680 telephone circuits or 2 TV channels each way
| 4 | from 1975? | 120 Mbps duplex | 3600 telephone circuits or 4 TV channels each way
| 5 | 80s? | 240 Mbps duplex | 7440 telephone circuits
| 6 | 90s? | 480 Mbps duplex | 15120 telephone circuits

An Olympics broadcast would be expressed as a non-exclusive point-to-multipoint communication at 30 Mbps with a lenient latency requirement.

# Usage

A connection uses the lowest-latency channels available that are can sustain its data rate.
Two resources are taken into account:
- Power: on transmitting antennas, the total power consumed must not exceed the maximum transmitted power of the antenna;
- RF Spectrum: the total bandwidth received and transmitted at an antenna must not exceed the width of the band.

Power is straightforward: the more data you need to transmit and the further away your satellite,
the more power you need, and thus the beefier the satellite needs to be.
This can eventually become an incentive to focus the power in the right place using spot beams.

RF spectrum takes longer to become a limiting factor; it is also more subtle. It means that eventually communications need to go through different antennas, one way or another, whether that means additional satellites or separate antennas (spot beams) on the same satellite.

# Metrics

Service availability requirements are refer to the availability over a moving window or over a fixed period.

A short moving window is used for monitoring and alerting; a longer moving window is used for demonstrating a new capability.

Fixed periods of one calendar month are used for maintenance.

Fixed periods are also used for some milestone broadcasts such as the Olympics.

TODO(egg): Provide a way to require availability *while* performing some actions, for milestone broadcasts pertaining to space exploration (EVAs, launches, etc.)