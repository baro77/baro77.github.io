---
layout: post
title: Monero's RingCT Cheatsheet
categories: [Monero, Privacy, RingCT, Pedersen Commitment, Bulletproof]
---

![](/images/monero-ringct.png)

After investigating Monero addresses types and signatures schemas, I have spent some time exploring how everything is put together in transactions. My attention has been focused on the standard, common TX (at the time of writing, Q2-2021): RingCT Type 5 (the CLSAG-based one).

So here it is where you can get this brand new stuff:

- on my GitHub repo [https://github.com/baro77/RctCS](https://github.com/baro77/RctCS){:target="_blank"}

- on [Medium](https://baro77.medium.com/monero-ringct-cheatsheet-8a9fcf580600?source=friends_link&sk=4504b16263b3beb4152498662bd4b9ae){:target="_blank"}, where a companion article briefly introduces strong (if any) and weak points of the cheatsheet

- on the library section of Monero official site [https://www.getmonero.org/library/](https://www.getmonero.org/library/){:target="_blank"}, together with my previous cheatsheets and part of the sources I have been learning from