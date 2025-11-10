# lastNs2utc

I set out to research the limits of clock sync precision,
effectively chasing the "Last Nanoseconds to UTC."

Is sub-nanosecond UTC sync possible?
Literally, no.
But practically yes.

This presentation sums up my research on the topic.
Having retired from work in financial markets,
it focuses on how market participants can use GPS
or other GNSS satellite constellations to synchronize their clocks.

In a nutshell, two factors make it literally impossible to
sync clocks with precision better than about 5ns:

1. The best of the GNSS constellations still have a
standard deviation of 5ns around UTC.
Look for sigma_GPS in a recent
[Circular-T from BIPM](https://webtai.bipm.org/ftp/pub/tai/Circular-T/cirt/cirt.454) to check me on this.
2.  A national time lab like NIST may have atomic clocks that
can do better, but
[UTC is a virtual timescale](https://www.nist.gov/pml/time-and-frequency-division/time-realization/utcnist-time-scale-0/introduction-utcnist)
defined after the fact, not in real-time.

So if you're getting time from GNSS instead of from a national lab,
you can't literally get closer than 5ns.

However, my homelab tests showed that two high-quality GNSS
receiver modules could agree on time to 550ps when
tracking a single constellation.
So even if that constellation was running ahead of or
behind UTC by 5ns or more, clocks synced to it could agree sub-nanosecond.

This is the state of GNSS clock sync as I see it in late 2025.
There are promising recent developments that I haven't tested yet:

* [Galileo has added HAS](https://www.gsc-europa.eu/galileo/services/galileo-high-accuracy-service-has), which may bring down their standard deviation.
* [Fugro AtomiChron](https://www.fugro.com/expertise/satellite-positioning/atomichron)
promises sub-nanosecond sync to their own traceable reference timescale.

I delivered this presentation at the
[London STAC Summit](https://docs.stacresearch.com/fall2025LON)
and
[New York STAC Summit](https://docs.stacresearch.com/fall2025NYC).

My presentation style is heavy on visuals and light on bullets,
with my narration giving the key points verbally.
The GitHub audience necessarily misses out compared to
the live audiences.
However, the live audiences didn't have enough screen time
to savor the final slides on Takeaways and Best Practices.
