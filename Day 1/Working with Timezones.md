# Working with Time Zones: Everyting You Wish you Didn't Need to Know

UTC - the reference timezone. The "zero" from which all others are measured.

## Timezones vs Offsets

- UTC-6 is an offset
- America/Chicago is a timezone
- CST is a context-dependent abbreviation:
    - Central Standard time UTC-6
    - Cuba Standard Time UTC-5
    - China standard time UTC+8

## Complicated Time Zones

- Australia/Adelaide (+9:30)
- Asia/Kathmandu (+5:45)
- In the 1990s - Portugal did some weird stuff around DST because they were changing time zones (led to DST status without offset change)
- Morroco (since 2012) - went on/off daylight savings time a bunch of times (because of Ramadan)
- In 1994 and 2011 Christmas Island and Samoa lost days because of moving around which timezone they wanted to be in
- In 1969 Kwajalein Atoll - had 9/30 twice
- All of China is one timezone (for the geography it would normally have 3 timezones) - but locals in the west use UTC+6

## Why do we need to work with timezones instead of using UTC for everything?

Because you need to interact with humans and they have daylight savings, etc

(note to self: Explore the from dateutil import rrule - what does that that do?)

When storing datetimes where the wall time matters (eg meetings) you must store local time because the mapping between UTC and local time is not stable (see above examples)

## Python's time zone model: tzinfo

- tzname - the name of the time zone at a given datetime
- utcoffset - the offset from UTC at the given datetime
- dst - the size of the datetime's DST offset (USUALLY 0 or 1 hour) -> probably never want to use this. Presenter has never seen it used well

In Python 2.3 there were no time zones in the standard library

- UTC/fixed offsets added in Python 3.2

Ambiguious times - when the same wall time occurs twice -example when going from DST to STD.

Imaginzary time - the opposite - when you jump forward an hour from STD to DST

pytz and tzinfo represent thigns differently. 

Problem with pytz - requires eager calculation. Also you must normalize datetimes after doing arithmetic on them

Python 3.6 PEP495: Local Time Disambiguation - helps with ambiguious time. (Need to read more to properly understand)

Local time support came in Python 3.6

Naive datetimes are now considered system local times. You can attached a fixed fofset zone to them

Presenter has 2 blog posts: Why naive times are local times and Stop using utcnow and utcfromtimestamp

IANA Time Zones is the standard open source source for time zone information

PEP 615 - Support for the IANA Time Zone Database in the Standard Library

What does euqality mean? Depends on wall time semantics or absolute time semantics (convert to UTC first)

zoneinfo has 2038 support and is fast - faster than pytz and dateutil on all metrics

it is a breaking change to move from pytz to zoneinfo. To help with migration - pytz-deprecation-shim package can be used

