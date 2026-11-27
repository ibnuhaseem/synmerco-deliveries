# SEC second-quarter revenue growth, 2025 against 2024: growth league and state view, three pulls

## Executive summary

This sample screens every SEC filer reporting the us-gaap Revenues tag for the second quarter, 2025 against 2024, from the XBRL frames API (data.sec.gov), in three timed pulls about 24 hours apart. The last good pull is PULL 3 (source time `Date: Fri, 27 Nov 2026 06:05:23 GMT`): 2226 filers appear in either frame, 1735 in both years and 491 in one year only (208 in 2025 only, 283 in 2024 only); 1634 have a growth value (both years and a 2024 value above zero). Among filers with a 2024 value of at least 100,000,000 dollars, the highest growth is EXPAND ENERGY CORPORATION (cik 895126) at 630.69% and the lowest is United States Natural Gas Fund, LP (cik 1376227) at -168.69%; the state view ranks US-CA first with 188 filers and a median growth of 9.17%. Between PULL 1 and PULL 2 and between PULL 2 and PULL 3 no filer was added or dropped and no `val 2024` or `val 2025` changed, so all three CSVs hold 2226 rows.

## Filer counts per pull

| Pull | Source time (first response Date header) | CY2025Q2 entries | CY2024Q2 entries | CSV rows | matched (both years) | 2025 only | 2024 only | growth values | CSV SHA-256 |
|---|---|---|---|---|---|---|---|---|---|
| PULL 1 | `Date: Wed, 25 Nov 2026 05:46:18 GMT` | 1943 | 2018 | 2226 | 1735 | 208 | 283 | 1634 | e6cea90b0cb35bfb5659b7b1d2b000c5271646a77b8b359ecc279231abd72a54 |
| PULL 2 | `Date: Thu, 26 Nov 2026 05:57:33 GMT` | 1943 | 2018 | 2226 | 1735 | 208 | 283 | 1634 | 38c5bb845e98b988aa9ce15662533a77259d8b5c2799bd1cd307db41555e752c |
| PULL 3 | `Date: Fri, 27 Nov 2026 06:05:23 GMT` | 1943 | 2018 | 2226 | 1735 | 208 | 283 | 1634 | 38c5bb845e98b988aa9ce15662533a77259d8b5c2799bd1cd307db41555e752c |

Rows are one per cik present in either frame (no cik appeared twice in a frame, so the latest-end rule was never needed); each count is traceable to the `"pts"` excerpts and request lines in the PROOF.

## Growth table: 25 highest (PULL 3)

Growth = 2025 val over 2024 val minus 1, in percent, 2 decimals half away from zero, from unrounded values. Filers with a 2024 val of at least 100000000 and a growth value; ties by cik ascending.

| Rank | cik | entityName | loc | val 2024 | val 2025 | growth % |
|---|---|---|---|---|---|---|
| 1 | 895126 | EXPAND ENERGY CORPORATION | US-TX | 505000000 | 3690000000 | 630.69 |
| 2 | 1070412 | CNX Resources Corporation | US-PA | 321443000 | 962422000 | 199.41 |
| 3 | 33213 | EQT CORPORATION | US-PA | 952512000 | 2557719000 | 168.52 |
| 4 | 874499 | Gulfport Energy Corp | US-OK | 181117000 | 447616000 | 147.14 |
| 5 | 1710366 | Core Natural Resources, Inc | US-PA | 490720000 | 1102361000 | 124.64 |
| 6 | 921638 | SSR Mining Inc. | US-CO | 184841000 | 405455000 | 119.35 |
| 7 | 1210677 | First Advantage Corporation | GA- | 184546000 | 390633000 | 111.67 |
| 8 | 1647639 | Upstart Holdings, Inc. | US-CA | 127630000 | 257291000 | 101.59 |
| 9 | 1796022 | STEPSTONE GROUP INC. | US-NY | 186401000 | 364287000 | 95.43 |
| 10 | 1609253 | California Resources Corp | US-CA | 514000000 | 978000000 | 90.27 |
| 11 | 776867 | WHITE MOUNTAINS INSURANCE GROUP, LTD | US-NH | 395400000 | 689200000 | 74.30 |
| 12 | 314489 | FIRST BUSEY CORPORATION | US-KS | 116235000 | 198046000 | 70.38 |
| 13 | 1997350 | ACCELERANT HOLDINGS | KY- | 130100000 | 219100000 | 68.41 |
| 14 | 873303 | SAREPTA THERAPEUTICS, INC. | US-MA | 362931000 | 611091000 | 68.38 |
| 15 | 1507605 | MARA HOLDINGS, INC. | US-FL | 145139000 | 238485000 | 64.31 |
| 16 | 1999001 | Six Flags Entertainment Corporation/NEW | US-NC | 571616000 | 930390000 | 62.76 |
| 17 | 315852 | RANGE RESOURCES CORPORATION | US-TX | 530109000 | 856275000 | 61.53 |
| 18 | 1454938 | Teads Holding Co. | US-NY | 214148000 | 343096000 | 60.21 |
| 19 | 1862461 | THE REAL BROKERAGE INC. | US-FL | 340778000 | 540747000 | 58.68 |
| 20 | 1045810 | NVIDIA CORP | US-CA | 30040000000 | 46743000000 | 55.60 |
| 21 | 1761312 | Palomar Holdings, Inc. | US-CA | 131069000 | 203311000 | 55.12 |
| 22 | 858470 | COTERRA ENERGY INC. | US-TX | 1271000000 | 1965000000 | 54.60 |
| 23 | 1876042 | CIRCLE INTERNET GROUP, INC. | US-NY | 430030000 | 658078000 | 53.03 |
| 24 | 1590364 | FTAI AVIATION LTD. | US-NY | 443594000 | 676237000 | 52.45 |
| 25 | 46765 | HELMERICH & PAYNE, INC. | US-OK | 697724000 | 1040924000 | 49.19 |

## Growth table: 25 lowest (PULL 3)

Same filter and rounding; ties by cik ascending.

| Rank | cik | entityName | loc | val 2024 | val 2025 | growth % |
|---|---|---|---|---|---|---|
| 1 | 1376227 | United States Natural Gas Fund, LP | US-CA | 176585785 | -121294698 | -168.69 |
| 2 | 1822993 | Jackson Financial Inc. | US-MI | 1247000000 | -471000000 | -137.77 |
| 3 | 1679688 | DigitalBridge Group, Inc. | US-FL | 390336000 | -3207000 | -100.82 |
| 4 | 1393726 | Tiptree Inc. | US-CT | 546673000 | 92000 | -99.98 |
| 5 | 821130 | ARRAY DIGITAL INFRASTRUCTURE, INC. | US-IL | 927000000 | 28529000 | -96.92 |
| 6 | 1621227 | ADAPTIMMUNE THERAPEUTICS PLC | GB- | 128231000 | 13677000 | -89.33 |
| 7 | 1051512 | TELEPHONE AND DATA SYSTEMS, INC. | US-IL | 1238000000 | 298541000 | -75.89 |
| 8 | 777917 | PRUCO LIFE INSURANCE CO | US-NJ | 1782544000 | 557075000 | -68.75 |
| 9 | 1822359 | DocGo Inc. | US-NY | 164949716 | 80417622 | -51.25 |
| 10 | 1839341 | Core Scientific, Inc./tx | US-DE | 141102000 | 78628000 | -44.28 |
| 11 | 733076 | Brighthouse Life Insurance Company | US-NC | 1246000000 | 697000000 | -44.06 |
| 12 | 1000694 | NOVAVAX, INC. | MD- | 415484000 | 239240000 | -42.42 |
| 13 | 1577437 | Ardmore Shipping Corp | - | 121325000 | 72046000 | -40.62 |
| 14 | 99780 | TRINITY INDUSTRIES INC | US-TX | 841400000 | 506200000 | -39.84 |
| 15 | 1685040 | Brighthouse Financial, Inc. | US-NC | 1427000000 | 871000000 | -38.96 |
| 16 | 1712189 | TARGET HOSPITALITY CORP. | US-TX | 100721000 | 61606000 | -38.83 |
| 17 | 1521332 | APTIV PLC | CH- | 5051000000 | 3199000000 | -36.67 |
| 18 | 1825024 | Offerpad Solutions Inc. | US-AZ | 251122000 | 160315000 | -36.16 |
| 19 | 1333986 | Equitable Holdings, Inc. | US-NY | 3507000000 | 2362000000 | -32.65 |
| 20 | 1704715 | ALPHA METALLURGICAL RESOURCES, INC. | US-TN | 803969000 | 550274000 | -31.56 |
| 21 | 1770561 | Coronado Global Resources Inc. | AU- | 673828000 | 467879000 | -30.56 |
| 22 | 807882 | JACK IN THE BOX INC. | US-CA | 369171000 | 262401000 | -28.92 |
| 23 | 1749723 | New Fortress Energy Inc. | US-NY | 427174000 | 304100000 | -28.81 |
| 24 | 1677703 | CONDUENT INC | US-NJ | 828000000 | 603000000 | -27.17 |
| 25 | 1889539 | Corebridge Financial, Inc. | US-TX | 3710000000 | 2726000000 | -26.52 |

## State view (PULL 3)

The 10 loc values with the most filers having a growth value (ties by loc ascending); median growth of those filers (all filers with a growth value, not only the 2024 val >= 100000000 ones); even count = mean of the two middle values; computed from unrounded growth.

| Rank | loc | filers with growth value | median growth % |
|---|---|---|---|
| 1 | US-CA | 188 | 9.17 |
| 2 | US-TX | 177 | 3.52 |
| 3 | US-NY | 175 | 6.68 |
| 4 | US-FL | 125 | 7.63 |
| 5 | US-IL | 64 | 5.53 |
| 6 | US-MA | 56 | 3.59 |
| 7 | US-NJ | 55 | 1.36 |
| 8 | US-PA | 52 | 3.29 |
| 9 | US-CO | 48 | 4.88 |
| 10 | US-VA | 40 | 3.41 |

## Changes: PULL 2 vs PULL 1

Matched by key cik; Changes columns: `val 2024`, `val 2025`. **No change**: PULL 1 has 2226 rows, PULL 2 has 2226 rows (new 0, gone 0, changed 0).

Note: the only cell that differs between the two CSVs is `accn 2025` of cik 926617 (0000926617-26-000054 in PULL 1, 0000926617-26-000066 in PULL 2); `accn` is not a Changes column, so it is not counted.

## Changes: PULL 3 vs PULL 2

Matched by key cik; Changes columns: `val 2024`, `val 2025`. **No change**: PULL 2 has 2226 rows, PULL 3 has 2226 rows (new 0, gone 0, changed 0).

## Data files (Rule 25)

D2-D4 are attached as data files; columns in order: cik, entityName, loc, val 2024, val 2025, growth, accn 2024, accn 2025 (key: cik; sorted by cik as a number).

```synmerco-data
e6cea90b0cb35bfb5659b7b1d2b000c5271646a77b8b359ecc279231abd72a54 q2-revenue-pull1.csv
38c5bb845e98b988aa9ce15662533a77259d8b5c2799bd1cd307db41555e752c q2-revenue-pull2.csv
38c5bb845e98b988aa9ce15662533a77259d8b5c2799bd1cd307db41555e752c q2-revenue-pull3.csv
```

## PROOF

All requests are HTTP GET to host data.sec.gov, each answered on the first attempt (no retry needed). One line per request: full request, UTC time, HTTP status. Under each pull: its first response's Date header line, copied exactly.

### PULL 1 requests

GET https://data.sec.gov/api/xbrl/frames/us-gaap/Revenues/USD/CY2025Q2.json 2026-11-25T05:46:18Z HTTP 200
GET https://data.sec.gov/api/xbrl/frames/us-gaap/Revenues/USD/CY2024Q2.json 2026-11-25T05:46:19Z HTTP 200

PULL 1 source time (first response Date header): `Date: Wed, 25 Nov 2026 05:46:18 GMT`

Frame header lines (verbatim):

- CY2025Q2 pull 1: `"pts":1943` (entries in `data`: 1943)
- CY2024Q2 pull 1: `"pts":2018` (entries in `data`: 2018)

### PULL 2 requests

GET https://data.sec.gov/api/xbrl/frames/us-gaap/Revenues/USD/CY2025Q2.json 2026-11-26T05:57:32Z HTTP 200
GET https://data.sec.gov/api/xbrl/frames/us-gaap/Revenues/USD/CY2024Q2.json 2026-11-26T05:57:34Z HTTP 200

PULL 2 source time (first response Date header): `Date: Thu, 26 Nov 2026 05:57:33 GMT`

Frame header lines (verbatim):

- CY2025Q2 pull 2: `"pts":1943` (entries in `data`: 1943)
- CY2024Q2 pull 2: `"pts":2018` (entries in `data`: 2018)

### PULL 3 requests

GET https://data.sec.gov/api/xbrl/frames/us-gaap/Revenues/USD/CY2025Q2.json 2026-11-27T06:05:22Z HTTP 200
GET https://data.sec.gov/api/xbrl/frames/us-gaap/Revenues/USD/CY2024Q2.json 2026-11-27T06:05:24Z HTTP 200

PULL 3 source time (first response Date header): `Date: Fri, 27 Nov 2026 06:05:23 GMT`

Frame header lines (verbatim):

- CY2025Q2 pull 3: `"pts":1943` (entries in `data`: 1943)
- CY2024Q2 pull 3: `"pts":2018` (entries in `data`: 2018)

## Raw frame entries of the 5 highest-growth filers (last good pull: PULL 3)

The 5 highest-growth filers are the first five rows of the 25-highest table (same filter and tie rule). Each entry is copied verbatim from the PULL 3 response of the frame it came from.

### Raw entries 1: cik 895126 EXPAND ENERGY CORPORATION (PULL 3, growth 630.69%)

CY2025Q2 entry (verbatim from the PULL 3 response):

```
{"accn":"0000895126-26-000047","cik":895126,"entityName":"EXPAND ENERGY CORPORATION","loc":"US-TX","start":"2025-04-01","end":"2025-06-30","val":3690000000}
```

CY2024Q2 entry (verbatim from the PULL 3 response):

```
{"accn":"0000895126-25-000084","cik":895126,"entityName":"EXPAND ENERGY CORPORATION","loc":"US-OK","start":"2024-04-01","end":"2024-06-30","val":505000000}
```

### Raw entries 2: cik 1070412 CNX Resources Corporation (PULL 3, growth 199.41%)

CY2025Q2 entry (verbatim from the PULL 3 response):

```
{"accn":"0001070412-26-000058","cik":1070412,"entityName":"CNX Resources Corporation","loc":"US-PA","start":"2025-04-01","end":"2025-06-30","val":962422000}
```

CY2024Q2 entry (verbatim from the PULL 3 response):

```
{"accn":"0001070412-25-000090","cik":1070412,"entityName":"CNX Resources Corporation","loc":"US-PA","start":"2024-04-01","end":"2024-06-30","val":321443000}
```

### Raw entries 3: cik 33213 EQT CORPORATION (PULL 3, growth 168.52%)

CY2025Q2 entry (verbatim from the PULL 3 response):

```
{"accn":"0000033213-26-000043","cik":33213,"entityName":"EQT CORPORATION","loc":"US-PA","start":"2025-04-01","end":"2025-06-30","val":2557719000}
```

CY2024Q2 entry (verbatim from the PULL 3 response):

```
{"accn":"0000033213-25-000033","cik":33213,"entityName":"EQT CORPORATION","loc":"US-PA","start":"2024-04-01","end":"2024-06-30","val":952512000}
```

### Raw entries 4: cik 874499 Gulfport Energy Corp (PULL 3, growth 147.14%)

CY2025Q2 entry (verbatim from the PULL 3 response):

```
{"accn":"0001628280-26-052313","cik":874499,"entityName":"Gulfport Energy Corp","loc":"US-OK","start":"2025-04-01","end":"2025-06-30","val":447616000}
```

CY2024Q2 entry (verbatim from the PULL 3 response):

```
{"accn":"0001628280-25-038172","cik":874499,"entityName":"Gulfport Energy Corp","loc":"US-OK","start":"2024-04-01","end":"2024-06-30","val":181117000}
```

### Raw entries 5: cik 1710366 Core Natural Resources, Inc (PULL 3, growth 124.64%)

CY2025Q2 entry (verbatim from the PULL 3 response):

```
{"accn":"0001710366-25-000017","cik":1710366,"entityName":"Core Natural Resources, Inc","loc":"US-PA","start":"2025-04-01","end":"2025-06-30","val":1102361000}
```

CY2024Q2 entry (verbatim from the PULL 3 response):

```
{"accn":"0001710366-25-000017","cik":1710366,"entityName":"Core Natural Resources, Inc","loc":"US-PA","start":"2024-04-01","end":"2024-06-30","val":490720000}
```

### Raw entries for the 25 highest table filers not shown above (PULL 3, verbatim)

```
cik 921638 CY2025Q2: {"accn":"0000921638-26-000081","cik":921638,"entityName":"SSR Mining Inc.","loc":"US-CO","start":"2025-04-01","end":"2025-06-30","val":405455000}
cik 921638 CY2024Q2: {"accn":"0000921638-25-000161","cik":921638,"entityName":"SSR MINING INC.","loc":"US-CO","start":"2024-04-01","end":"2024-06-30","val":184841000}
cik 1210677 CY2025Q2: {"accn":"0001193125-26-338063","cik":1210677,"entityName":"First Advantage Corporation","loc":"GA-","start":"2025-04-01","end":"2025-06-30","val":390633000}
cik 1210677 CY2024Q2: {"accn":"0001193125-25-175442","cik":1210677,"entityName":"First Advantage Corporation","loc":"GA-","start":"2024-04-01","end":"2024-06-30","val":184546000}
cik 1647639 CY2025Q2: {"accn":"0001647639-26-000063","cik":1647639,"entityName":"Upstart Holdings, Inc.","loc":"US-CA","start":"2025-04-01","end":"2025-06-30","val":257291000}
cik 1647639 CY2024Q2: {"accn":"0001647639-25-000100","cik":1647639,"entityName":"Upstart Holdings, Inc.","loc":"US-CA","start":"2024-04-01","end":"2024-06-30","val":127630000}
cik 1796022 CY2025Q2: {"accn":"0001628280-26-054818","cik":1796022,"entityName":"STEPSTONE GROUP INC.","loc":"US-NY","start":"2025-04-01","end":"2025-06-30","val":364287000}
cik 1796022 CY2024Q2: {"accn":"0001796022-25-000060","cik":1796022,"entityName":"STEPSTONE GROUP INC.","loc":"US-NY","start":"2024-04-01","end":"2024-06-30","val":186401000}
cik 1609253 CY2025Q2: {"accn":"0001609253-26-000130","cik":1609253,"entityName":"California Resources Corp","loc":"US-CA","start":"2025-04-01","end":"2025-06-30","val":978000000}
cik 1609253 CY2024Q2: {"accn":"0001609253-25-000069","cik":1609253,"entityName":"California Resources Corp","loc":"US-CA","start":"2024-04-01","end":"2024-06-30","val":514000000}
cik 776867 CY2025Q2: {"accn":"0001628280-26-053932","cik":776867,"entityName":"WHITE MOUNTAINS INSURANCE GROUP, LTD","loc":"US-NH","start":"2025-04-01","end":"2025-06-30","val":689200000}
cik 776867 CY2024Q2: {"accn":"0000776867-25-000014","cik":776867,"entityName":"WHITE MOUNTAINS INSURANCE GROUP, LTD","loc":"US-NH","start":"2024-04-01","end":"2024-06-30","val":395400000}
cik 314489 CY2025Q2: {"accn":"0000314489-26-000055","cik":314489,"entityName":"FIRST BUSEY CORPORATION","loc":"US-KS","start":"2025-04-01","end":"2025-06-30","val":198046000}
cik 314489 CY2024Q2: {"accn":"0000314489-25-000284","cik":314489,"entityName":"FIRST BUSEY CORPORATION","loc":"US-KS","start":"2024-04-01","end":"2024-06-30","val":116235000}
cik 1997350 CY2025Q2: {"accn":"0001997350-26-000015","cik":1997350,"entityName":"ACCELERANT HOLDINGS","loc":"KY-","start":"2025-04-01","end":"2025-06-30","val":219100000}
cik 1997350 CY2024Q2: {"accn":"0001997350-25-000004","cik":1997350,"entityName":"ACCELERANT HOLDINGS","loc":"KY-","start":"2024-04-01","end":"2024-06-30","val":130100000}
cik 873303 CY2025Q2: {"accn":"0001193125-26-335003","cik":873303,"entityName":"SAREPTA THERAPEUTICS, INC.","loc":"US-MA","start":"2025-04-01","end":"2025-06-30","val":611091000}
cik 873303 CY2024Q2: {"accn":"0001193125-26-084144","cik":873303,"entityName":"Sarepta Therapeutics, Inc.","loc":"US-MA","start":"2024-04-01","end":"2024-06-30","val":362931000}
cik 1507605 CY2025Q2: {"accn":"0001507605-26-000022","cik":1507605,"entityName":"MARA HOLDINGS, INC.","loc":"US-FL","start":"2025-04-01","end":"2025-06-30","val":238485000}
cik 1507605 CY2024Q2: {"accn":"0001507605-25-000018","cik":1507605,"entityName":"MARA HOLDINGS, INC.","loc":"US-FL","start":"2024-04-01","end":"2024-06-30","val":145139000}
cik 1999001 CY2025Q2: {"accn":"0001999001-26-000096","cik":1999001,"entityName":"Six Flags Entertainment Corporation/NEW","loc":"US-NC","start":"2025-03-31","end":"2025-06-29","val":930390000}
cik 1999001 CY2024Q2: {"accn":"0001999001-25-000154","cik":1999001,"entityName":"Six Flags Entertainment Corporation/NEW","loc":"US-NC","start":"2024-04-01","end":"2024-06-30","val":571616000}
cik 315852 CY2025Q2: {"accn":"0001193125-26-310446","cik":315852,"entityName":"RANGE RESOURCES CORPORATION","loc":"US-TX","start":"2025-04-01","end":"2025-06-30","val":856275000}
cik 315852 CY2024Q2: {"accn":"0000950170-25-097592","cik":315852,"entityName":"RANGE RESOURCES CORPORATION","loc":"US-TX","start":"2024-04-01","end":"2024-06-30","val":530109000}
cik 1454938 CY2025Q2: {"accn":"0001454938-26-000054","cik":1454938,"entityName":"Teads Holding Co.","loc":"US-NY","start":"2025-04-01","end":"2025-06-30","val":343096000}
cik 1454938 CY2024Q2: {"accn":"0001454938-25-000132","cik":1454938,"entityName":"Teads Holding Co.","loc":"US-NY","start":"2024-04-01","end":"2024-06-30","val":214148000}
cik 1862461 CY2025Q2: {"accn":"0001493152-25-011674","cik":1862461,"entityName":"THE REAL BROKERAGE INC.","loc":"US-FL","start":"2025-04-01","end":"2025-06-30","val":540747000}
cik 1862461 CY2024Q2: {"accn":"0001493152-25-011674","cik":1862461,"entityName":"THE REAL BROKERAGE INC.","loc":"US-FL","start":"2024-04-01","end":"2024-06-30","val":340778000}
cik 1045810 CY2025Q2: {"accn":"0001045810-26-000075","cik":1045810,"entityName":"NVIDIA CORP","loc":"US-CA","start":"2025-04-28","end":"2025-07-27","val":46743000000}
cik 1045810 CY2024Q2: {"accn":"0001045810-25-000209","cik":1045810,"entityName":"NVIDIA CORP","loc":"US-CA","start":"2024-04-29","end":"2024-07-28","val":30040000000}
cik 1761312 CY2025Q2: {"accn":"0001193125-26-335508","cik":1761312,"entityName":"Palomar Holdings, Inc.","loc":"US-CA","start":"2025-04-01","end":"2025-06-30","val":203311000}
cik 1761312 CY2024Q2: {"accn":"0000950170-25-103234","cik":1761312,"entityName":"Palomar Holdings, Inc.","loc":"US-CA","start":"2024-04-01","end":"2024-06-30","val":131069000}
cik 858470 CY2025Q2: {"accn":"0000858470-25-000165","cik":858470,"entityName":"COTERRA ENERGY INC.","loc":"US-TX","start":"2025-04-01","end":"2025-06-30","val":1965000000}
cik 858470 CY2024Q2: {"accn":"0000858470-25-000165","cik":858470,"entityName":"COTERRA ENERGY INC.","loc":"US-TX","start":"2024-04-01","end":"2024-06-30","val":1271000000}
cik 1876042 CY2025Q2: {"accn":"0001876042-26-000248","cik":1876042,"entityName":"CIRCLE INTERNET GROUP, INC.","loc":"US-NY","start":"2025-04-01","end":"2025-06-30","val":658078000}
cik 1876042 CY2024Q2: {"accn":"0001628280-25-039781","cik":1876042,"entityName":"CIRCLE INTERNET GROUP, INC.","loc":"US-NY","start":"2024-04-01","end":"2024-06-30","val":430030000}
cik 1590364 CY2025Q2: {"accn":"0001628280-26-051412","cik":1590364,"entityName":"FTAI AVIATION LTD.","loc":"US-NY","start":"2025-04-01","end":"2025-06-30","val":676237000}
cik 1590364 CY2024Q2: {"accn":"0001590364-25-000023","cik":1590364,"entityName":"FTAI AVIATION LTD.","loc":"US-NY","start":"2024-04-01","end":"2024-06-30","val":443594000}
cik 46765 CY2025Q2: {"accn":"0000046765-26-000042","cik":46765,"entityName":"HELMERICH & PAYNE, INC.","loc":"US-OK","start":"2025-04-01","end":"2025-06-30","val":1040924000}
cik 46765 CY2024Q2: {"accn":"0000046765-25-000051","cik":46765,"entityName":"HELMERICH & PAYNE, INC.","loc":"US-OK","start":"2024-04-01","end":"2024-06-30","val":697724000}
```

### Raw entries for the 25 lowest table filers not shown above (PULL 3, verbatim)

```
cik 1376227 CY2025Q2: {"accn":"0001104659-26-021507","cik":1376227,"entityName":"United States Natural Gas Fund, LP","loc":"US-CA","start":"2025-04-01","end":"2025-06-30","val":-121294698}
cik 1376227 CY2024Q2: {"accn":"0001104659-26-021507","cik":1376227,"entityName":"United States Natural Gas Fund, LP","loc":"US-CA","start":"2024-04-01","end":"2024-06-30","val":176585785}
cik 1822993 CY2025Q2: {"accn":"0001822993-26-000124","cik":1822993,"entityName":"Jackson Financial Inc.","loc":"US-MI","start":"2025-04-01","end":"2025-06-30","val":-471000000}
cik 1822993 CY2024Q2: {"accn":"0001822993-25-000030","cik":1822993,"entityName":"Jackson Financial Inc.","loc":"US-MI","start":"2024-04-01","end":"2024-06-30","val":1247000000}
cik 1679688 CY2025Q2: {"accn":"0001679688-26-000115","cik":1679688,"entityName":"DigitalBridge Group, Inc.","loc":"US-FL","start":"2025-04-01","end":"2025-06-30","val":-3207000}
cik 1679688 CY2024Q2: {"accn":"0001679688-25-000084","cik":1679688,"entityName":"DigitalBridge Group, Inc.","loc":"US-FL","start":"2024-04-01","end":"2024-06-30","val":390336000}
cik 1393726 CY2025Q2: {"accn":"0001393726-26-000048","cik":1393726,"entityName":"Tiptree Inc.","loc":"US-CT","start":"2025-04-01","end":"2025-06-30","val":92000}
cik 1393726 CY2024Q2: {"accn":"0001393726-25-000076","cik":1393726,"entityName":"Tiptree Inc.","loc":"US-CT","start":"2024-04-01","end":"2024-06-30","val":546673000}
cik 821130 CY2025Q2: {"accn":"0000821130-26-000046","cik":821130,"entityName":"ARRAY DIGITAL INFRASTRUCTURE, INC.","loc":"US-IL","start":"2025-04-01","end":"2025-06-30","val":28529000}
cik 821130 CY2024Q2: {"accn":"0000821130-25-000051","cik":821130,"entityName":"ARRAY DIGITAL INFRASTRUCTURE, INC.","loc":"US-IL","start":"2024-04-01","end":"2024-06-30","val":927000000}
cik 1621227 CY2025Q2: {"accn":"0001558370-25-011307","cik":1621227,"entityName":"ADAPTIMMUNE THERAPEUTICS PLC","loc":"GB-","start":"2025-04-01","end":"2025-06-30","val":13677000}
cik 1621227 CY2024Q2: {"accn":"0001558370-25-011307","cik":1621227,"entityName":"ADAPTIMMUNE THERAPEUTICS PLC","loc":"GB-","start":"2024-04-01","end":"2024-06-30","val":128231000}
cik 1051512 CY2025Q2: {"accn":"0001051512-26-000063","cik":1051512,"entityName":"TELEPHONE AND DATA SYSTEMS, INC.","loc":"US-IL","start":"2025-04-01","end":"2025-06-30","val":298541000}
cik 1051512 CY2024Q2: {"accn":"0001051512-25-000062","cik":1051512,"entityName":"TELEPHONE AND DATA SYSTEMS, INC.","loc":"US-IL","start":"2024-04-01","end":"2024-06-30","val":1238000000}
cik 777917 CY2025Q2: {"accn":"0000777917-25-000110","cik":777917,"entityName":"PRUCO LIFE INSURANCE CO","loc":"US-NJ","start":"2025-04-01","end":"2025-06-30","val":557075000}
cik 777917 CY2024Q2: {"accn":"0000777917-25-000110","cik":777917,"entityName":"PRUCO LIFE INSURANCE CO","loc":"US-NJ","start":"2024-04-01","end":"2024-06-30","val":1782544000}
cik 1822359 CY2025Q2: {"accn":"0001628280-26-057394","cik":1822359,"entityName":"DocGo Inc.","loc":"US-NY","start":"2025-04-01","end":"2025-06-30","val":80417622}
cik 1822359 CY2024Q2: {"accn":"0001822359-25-000074","cik":1822359,"entityName":"DocGo Inc.","loc":"US-NY","start":"2024-04-01","end":"2024-06-30","val":164949716}
cik 1839341 CY2025Q2: {"accn":"0001839341-26-000014","cik":1839341,"entityName":"Core Scientific, Inc./tx","loc":"US-DE","start":"2025-04-01","end":"2025-06-30","val":78628000}
cik 1839341 CY2024Q2: {"accn":"0001628280-26-013294","cik":1839341,"entityName":"Core Scientific, Inc./tx","loc":"US-DE","start":"2024-04-01","end":"2024-06-30","val":141102000}
cik 733076 CY2025Q2: {"accn":"0000733076-26-000009","cik":733076,"entityName":"Brighthouse Life Insurance Company","loc":"US-NC","start":"2025-04-01","end":"2025-06-30","val":697000000}
cik 733076 CY2024Q2: {"accn":"0000733076-25-000012","cik":733076,"entityName":"Brighthouse Life Insurance Company","loc":"US-NC","start":"2024-04-01","end":"2024-06-30","val":1246000000}
cik 1000694 CY2025Q2: {"accn":"0001000694-26-000018","cik":1000694,"entityName":"NOVAVAX, INC.","loc":"MD-","start":"2025-04-01","end":"2025-06-30","val":239240000}
cik 1000694 CY2024Q2: {"accn":"0001000694-25-000029","cik":1000694,"entityName":"NOVAVAX, INC.","loc":"MD-","start":"2024-04-01","end":"2024-06-30","val":415484000}
cik 1577437 CY2025Q2: {"accn":"0001104659-26-087834","cik":1577437,"entityName":"Ardmore Shipping Corp","loc":"-","start":"2025-04-01","end":"2025-06-30","val":72046000}
cik 1577437 CY2024Q2: {"accn":"0001558370-25-009775","cik":1577437,"entityName":"Ardmore Shipping Corp","loc":"-","start":"2024-04-01","end":"2024-06-30","val":121325000}
cik 99780 CY2025Q2: {"accn":"0000099780-26-000119","cik":99780,"entityName":"TRINITY INDUSTRIES INC","loc":"US-TX","start":"2025-04-01","end":"2025-06-30","val":506200000}
cik 99780 CY2024Q2: {"accn":"0000099780-26-000014","cik":99780,"entityName":"TRINITY INDUSTRIES INC","loc":"US-TX","start":"2024-04-01","end":"2024-06-30","val":841400000}
cik 1685040 CY2025Q2: {"accn":"0001685040-26-000028","cik":1685040,"entityName":"Brighthouse Financial, Inc.","loc":"US-NC","start":"2025-04-01","end":"2025-06-30","val":871000000}
cik 1685040 CY2024Q2: {"accn":"0001685040-25-000048","cik":1685040,"entityName":"Brighthouse Financial, Inc.","loc":"US-NC","start":"2024-04-01","end":"2024-06-30","val":1427000000}
cik 1712189 CY2025Q2: {"accn":"0001104659-26-093264","cik":1712189,"entityName":"TARGET HOSPITALITY CORP.","loc":"US-TX","start":"2025-04-01","end":"2025-06-30","val":61606000}
cik 1712189 CY2024Q2: {"accn":"0001558370-25-010732","cik":1712189,"entityName":"TARGET HOSPITALITY CORP.","loc":"US-TX","start":"2024-04-01","end":"2024-06-30","val":100721000}
cik 1521332 CY2025Q2: {"accn":"0001521332-26-000061","cik":1521332,"entityName":"APTIV PLC","loc":"CH-","start":"2025-04-01","end":"2025-06-30","val":3199000000}
cik 1521332 CY2024Q2: {"accn":"0001521332-25-000040","cik":1521332,"entityName":"APTIV PLC","loc":"CH-","start":"2024-04-01","end":"2024-06-30","val":5051000000}
cik 1825024 CY2025Q2: {"accn":"0001193125-26-330713","cik":1825024,"entityName":"Offerpad Solutions Inc.","loc":"US-AZ","start":"2025-04-01","end":"2025-06-30","val":160315000}
cik 1825024 CY2024Q2: {"accn":"0000950170-25-102132","cik":1825024,"entityName":"Offerpad Solutions Inc.","loc":"US-AZ","start":"2024-04-01","end":"2024-06-30","val":251122000}
cik 1333986 CY2025Q2: {"accn":"0001333986-26-000040","cik":1333986,"entityName":"Equitable Holdings, Inc.","loc":"US-NY","start":"2025-04-01","end":"2025-06-30","val":2362000000}
cik 1333986 CY2024Q2: {"accn":"0001333986-25-000049","cik":1333986,"entityName":"Equitable Holdings, Inc.","loc":"US-NY","start":"2024-04-01","end":"2024-06-30","val":3507000000}
cik 1704715 CY2025Q2: {"accn":"0001704715-26-000031","cik":1704715,"entityName":"ALPHA METALLURGICAL RESOURCES, INC.","loc":"US-TN","start":"2025-04-01","end":"2025-06-30","val":550274000}
cik 1704715 CY2024Q2: {"accn":"0001704715-25-000027","cik":1704715,"entityName":"ALPHA METALLURGICAL RESOURCES, INC.","loc":"US-TN","start":"2024-04-01","end":"2024-06-30","val":803969000}
cik 1770561 CY2025Q2: {"accn":"0001562762-26-000094","cik":1770561,"entityName":"Coronado Global Resources Inc.","loc":"AU-","start":"2025-04-01","end":"2025-06-30","val":467879000}
cik 1770561 CY2024Q2: {"accn":"0001562762-25-000208","cik":1770561,"entityName":"Coronado Global Resources Inc.","loc":"AU-","start":"2024-04-01","end":"2024-06-30","val":673828000}
cik 807882 CY2025Q2: {"accn":"0000807882-26-000091","cik":807882,"entityName":"JACK IN THE BOX INC.","loc":"US-CA","start":"2025-04-14","end":"2025-07-06","val":262401000}
cik 807882 CY2024Q2: {"accn":"0000807882-25-000043","cik":807882,"entityName":"JACK IN THE BOX INC.","loc":"US-CA","start":"2024-04-15","end":"2024-07-07","val":369171000}
cik 1749723 CY2025Q2: {"accn":"0001749723-26-000106","cik":1749723,"entityName":"New Fortress Energy Inc.","loc":"US-NY","start":"2025-04-01","end":"2025-06-30","val":304100000}
cik 1749723 CY2024Q2: {"accn":"0001749723-26-000032","cik":1749723,"entityName":"New Fortress Energy Inc.","loc":"US-NY","start":"2024-04-01","end":"2024-06-30","val":427174000}
cik 1677703 CY2025Q2: {"accn":"0001677703-26-000092","cik":1677703,"entityName":"CONDUENT INC","loc":"US-NJ","start":"2025-04-01","end":"2025-06-30","val":603000000}
cik 1677703 CY2024Q2: {"accn":"0001677703-25-000126","cik":1677703,"entityName":"CONDUENT INC","loc":"US-NJ","start":"2024-04-01","end":"2024-06-30","val":828000000}
cik 1889539 CY2025Q2: {"accn":"0001889539-26-000141","cik":1889539,"entityName":"Corebridge Financial, Inc.","loc":"US-TX","start":"2025-04-01","end":"2025-06-30","val":2726000000}
cik 1889539 CY2024Q2: {"accn":"0001889539-25-000053","cik":1889539,"entityName":"Corebridge Financial, Inc.","loc":"US-TX","start":"2024-04-01","end":"2024-06-30","val":3710000000}
```

### Raw entries for the accn note (cik 926617, CY2025Q2 frame, verbatim)

```
PULL 1: {"accn":"0000926617-26-000054","cik":926617,"entityName":"Aspira Women’s Health Inc.","loc":"US-TX","start":"2025-04-01","end":"2025-06-30","val":169000}
PULL 2: {"accn":"0000926617-26-000066","cik":926617,"entityName":"Aspira Women’s Health Inc.","loc":"US-TX","start":"2025-04-01","end":"2025-06-30","val":169000}
```

