---
layout: post
title: Wazuh decoders for Aruba ClearPass Policy Manager
categories: [Wazuh, decoder, Aruba, Clearpass, ELK]
---

Aruba's ClearPass Policy Manager logs can be easily exported to ELK thanks to the great work done by @njohnsn with his [ClearPassAndELK](https://github.com/njohnsn/ClearPassAndELK){:target="_blank"} - thanks Neil :+1:

Once you have got the events lines, you still need to parse them to let Elasticsearch doing all its magic; one of the common solutions is to augment ELK prepending a Wazuh (formerly OSSEC) stage: roughly speaking, this way you can write **Decoders** to parse the events and **Rules** to take following actions (usually related to alerts triggering and log severities/conservation policies). Dealing with processes, Rules can be very organization-specific so to discourage their sharing due to low reusability and disclosures worries; however Decoders are definitely more geeky :wink: being nothing more that huge regexes, so I think [the ones I have written for CPPM](https://github.com/baro77/CPPM2Wazuh/blob/main/clearpass.xml){:target="_blank"} as part of my job duties could be useful to someone else: check it out!
