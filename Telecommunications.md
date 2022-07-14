# Telecommunications

## Connections

Two types of services are considered:
1. Duplex connection;
2. Point-to-multipoint connection (includes point-to-point).

In both cases, the data rate is fixed, and there is a maximum latency for the basic service (round-trip latency in the duplex case).
Lower latencies can be required as an improved service.

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
| Level | approx. date | Level requirement | Cumulative equivalents |
|---|---|---|---|
| 1 | from 1965 | 30 Mbps duplex | 240 telephone circuits (probably means one-way television is alternatively possible)
| 2 | from 1968 | 60 Mbps duplex | 720 telephone circuits or 1 TV channel each way
| 3 | from 1971 | 120 Mbps duplex | 1680 telephone circuits or 2 TV channels each way
| 4 | from 1975? | 240 Mbps duplex | 3600 telephone circuits or 4 TV channels each way
| 5 | from the 1980s? | 480 Mbps duplex | 7440 telephone circuits
| 6 | from the 1990s? | 960 Mbps duplex | 15120 telephone circuits

An Olympics broadcast would be expressed as a non-exclusive point-to-multipoint communication at 60 Mbps with a lenient latency requirement.

## Usage

A connection uses the lowest-latency channels available that are can sustain its data rate.
Two resources are taken into account:
- Power: on transmitting antennas, the total power consumed must not exceed the maximum transmitted power of the antenna;
- RF Spectrum: on receiving antennas, the total bandwidth received must not exceed the width of the band.