---
layout: post
title: "Initial post"
date: 2015-05-08 05:30:00 -0400
comments: false
---

I have covered some ground on the 2-dimensional case in Python, so far I have this running:

![Example Earth-Mars transfer](/images/expsin_a.png)

'''
radius of origin (day 0) = 0.983314 AU
radius of target (day 700) = 1.398643 AU
traversed angle = 452 degrees
calculated dT = 699.999988 days
solving ExpoSin: k0 = 183296841527.917328, k1 = -0.221646, k2 = 0.500000, phi = 1.693382
origin v1, target v2 = 30.285919, 26.198085 km/s
esv1, esv2 = 30.897807, 24.781400 km/s
'''

I put all of this in a separate github repository [here](https://github.com/ChrisAndre/expsin).

This output came from running [TestLambert.py](https://github.com/ChrisAndre/expsin/blob/master/TestLambert.py)
