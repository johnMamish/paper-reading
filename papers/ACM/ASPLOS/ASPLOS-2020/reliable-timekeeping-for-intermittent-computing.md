Keeping time between power losses is a critical enabling technique for batteryless systems; current methods do this by using an RC remanence circuit whose R and C values are chosen to suit the range of timekeeping required for the specific application. If R*C is big, longer times can be measured, but precision for shorter times is degraded, for many applications a single value of R*C isn't sufficient. The authors introduce a novel circuit which consists of several cascaded remanence timekeepers which is accurate for both short and long durations (design described in Fig 5). The timekeeper is shown to be accurate over many time ranges. They evaluate the timekeeping performance of a real prototype (Fig 7) and implement several test applications. They also design (but don't fabricate) an integrated circit as it consumes much less power (according to Cadence Virtuoso) when fabricated in 180nm TSMC process than discrete components.

Hot takes:
personal interest: 8/10
Cool paper, and I think I had an almost identical idea when I first read Josiah's older remanence timekeeper paper

paper quality / novelty: 8/10
Great idea, well-presented. It's not much material to stretch into a whole ASPLOS paper, but it does indeed solve a real problem for batteryless systems.
