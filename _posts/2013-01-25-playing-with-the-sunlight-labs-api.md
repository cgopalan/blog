---
layout: post
title: "Playing with the Sunlight Labs API"
date: 2013-01-25
categories: misc
tags: python sunlight
---

The folks at Sunlight Labs have done some brilliant work which allows
us to write a bit of code and get information about our legislators and
government. Here's a piece of code that tells us which legislators were
talking about gun control since December 2012. Additional data like the
speaker, party, chamber, etc are also available.

```
import requests
import json

party = {'D':'Democrat', 'R':'Republican'}
query_params = { 'apikey': '8247eaddc2544488909bea51c41dcc7c',
                                    'phrase': 'gun control',
                                    'start_date': '2012-12-01',
                            }
endpoint = 'http://capitolwords.org/api/text.json'

response = requests.get( endpoint, params=query_params)
data = json.loads(response.content.decode('utf-8'))

for v_dict in data['results']:
    print(", ".join([v_dict.get('title'), v_dict.get('chamber'),
                    party.get(v_dict.get('speaker_party')),
                    v_dict.get('speaker_first') + ' ' +
                    v_dict.get('speaker_last'),
                    v_dict.get('pages')]))
```

As of Jan 25, 2013 the result reads:

```
RIGHT OF GUN OWNERSHIP, House, Republican, Doug Collins, H76
SANDY HOOK TRAGEDY, House, Democrat, Albio Sires, H6835
REINSTATE THE ASSAULT WEAPONS BAN, House, Democrat, Janice Hahn, H6836
CONDEMNING THE HORRIFIC ATTACKS IN NEWTOWN, CONNECTICUT, AND EXPRESSING SUPPORT AND PRAYERS FOR ALL THOSE IMPACTED BY THIS TRAGEDY,
Extensions, Democrat, Laura Richardson, E1952-E1953
THE SHOOTING TRAGEDY IN NEWTOWN, CONNECTICUT, House, Democrat, Gerald Connolly, H6833-H6834
113TH CONGRESS OPENING DAY STATEMENT, Extensions, Democrat, Yvette Clarke, E14
DEPARTMENT OF DEFENSE APPROPRIATIONS ACT, Senate, Democrat, Charles Schumer, S8051-S8063
DEPARTMENT OF DEFENSE APPROPRIATIONS ACT, Senate, Democrat, Barbara Mikulski, S8051-S8063
RULES CHANGES, Senate, Republican, Michael Enzi, S8615-S8620
IN THE CLOSING OF THE 112TH CONGRESS, House, Republican, Robert Dold, H6758-H6761
TRIBUTES TO DEPARTING SENATORS, Senate, Democrat, Benjamin Cardin, S8498-S8504
```

There's also a direct Python API available which I will definitely be
checking out. But for now, the simple HTTP-based API can be used to get
a lot of useful information. Check out more of it here.