<!--
title: Project - DHA Slot Sniper
date: 2026-05-24
-->

# DHA Slot Sniper

There was a time when South Africa's Department of Home Affairs systems were on a path to becoming automated and efficient. It was short-lived. The systems have since regressed further back to a point where resorting to manual processes are likely to be better. In particular is the appointment booking system which is notoriously difficult to work with. 

After months of trying to book a slot to apply for a passport, I realised that it's just broken and that most people just resort to giving up a day of work and committing to standing in the walk-in line. I gave up and did the same, took a day off work, even though I couldn't, and ended up joining an online meeting in the queue. The queue at 7am at the Cresta Home Affairs branch stretched all the way around outside and into the shopping mall. The staff made it known to everyone that they had no interest or care to deal with anyone in particular and preferred that the herd just behaved as such, ignoring anyone that dared try to ask for any assistance. 

An hour in, they came around to inform everyone, matter-of-factly, that "the system is down". The advice: go home and try another day. There were people muttering how this was the 3rd day in a row that this had happened.

I returned home frustrated and realised that I would need to take off another day and try again. I decided to spend the rest of the day figuring out what the issue was with the booking system instead.

## The problem

The DHA's `services.dha.gov.za` system requires booking an appointment for passport applications. Slots are released unpredictably, presumably early morning and are somehow snapped up instantly by people. The web interface is slow, requires CAPTCHA on the old system, and gives no notification when slots open.

## The solution

My solution was to create a [DHA Slot Sniper](https://github.com/yusufk/dha-slot-sniper) that polls the booking API , checks multiple branches simultaneously, and can auto-book when a slot appears. As sone as one is found it sends Telegram alerts so that it doesn't need to be watched.

### Features

- Multi-branch polling (check Randburg, Cresta, Roodepoort simultaneously)
- Auto-book mode - grabs the first available slot
- `--check-only` mode for monitoring without booking
- `--city` selection for filtering branches
- Telegram notifications on slot detection
- Web frontend at [yusuf.kaka.co.za/dha-slot-sniper](https://yusuf.kaka.co.za/dha-slot-sniper/)
- Cloudflare Worker CORS proxy for browser-based access

## Key API findings

- Product filter `"IDs / Travel Documents"` is required for passport-specific slots
- Short date ranges (4-day windows) return better results than full month queries
- Slots tend to appear 7-8am SAST
- Auth requires: ID type, ID number, forenames, surname, contact number

## Result

I was able to find a booking that evening for the next week and I was able to get my passport application done and get to work after. I've since open-sourced the project and built a front-end web interface so that it's more accessible.

## Links

- [GitHub](https://github.com/yusufk/dha-slot-sniper)
- [Web frontend](https://yusuf.kaka.co.za/dha-slot-sniper/)

#python #automation #southafrica #opensource
