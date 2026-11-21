# New vulnerabilities in six network edge vendors since 1 October 2026: severity, status and newcomers, three pulls

Delivery for escrow `esc_4dec1bd706e34fd6a81514f5` (intent `83a8dd90-48bf-4074-993b-7077e3694bdb`), seller `did:key:z6MkmKVqLtHb5J14jqcFmpCafvmHspkqGgJEcENoDXBE2APN`. Source: National Vulnerability Database (host `services.nvd.nist.gov`), endpoint `/rest/json/cves/2.0`. Last good pull: PULL 3. The three pull CSVs are attached as data files (see Data files).

## Executive summary

Three pulls of the National Vulnerability Database API on 18, 20 and 21 November 2026, one request per keyword (fortinet, ivanti, cisco, citrix, sonicwall, juniper) with publication window 1 October to 31 December 2026, each returned the same 437 vulnerabilities (fortinet 112, ivanti 21, cisco 96, citrix 33, sonicwall 4, juniper 171), with no id added or removed between pulls and only two rows changing at all (one lastModified value in PULL 2, and one lastModified value plus one vulnStatus value in PULL 3); median CVSS v3.1 baseScore runs from 6.70 (ivanti) to 8.60 (cisco), citrix has 33 vulnerabilities and none of them carries a CVSS v3.1 score, and no vulnerability id appears under more than one keyword, so the newcomer and shared-id lists are empty.

## Raw totalResults per pull

Quoted raw from the NVD API (`/rest/json/cves/2.0`, `pubStartDate 2026-10-01T00:00:00.000`, `pubEndDate 2026-12-31T23:59:59.999`, one request per keyword, paged by `startIndex` until `totalResults`).

| Keyword | PULL 1 | PULL 2 | PULL 3 |
| --- | --- | --- | --- |
| fortinet | 112 | 112 | 112 |
| ivanti | 21 | 21 | 21 |
| cisco | 96 | 96 | 96 |
| citrix | 33 | 33 | 33 |
| sonicwall | 4 | 4 | 4 |
| juniper | 171 | 171 | 171 |
| **Total rows** | **437** | **437** | **437** |

| Pull | CSV | Rows | SHA-256 |
| --- | --- | --- | --- |
| PULL 1 | edge-cves-pull1.csv | 437 | 6865aefcfe5bdbc8e8176369b41eefc092e44f999435f25ae62c4824432d6cb8 |
| PULL 2 | edge-cves-pull2.csv | 437 | 88cb3f1e912a1fb5ffe107569b2f8095ac1ef158d3711f853f06e9b72fc05db1 |
| PULL 3 | edge-cves-pull3.csv | 437 | 500243a88378e6cf1318702216899b9c54c292358c2b6ccf6f7b7a4436abb842 |

## Per-keyword results (last good pull: PULL 3)

Figures are 2 decimals, half away from zero, from unrounded values; even-count median is the mean of the two middle values. Top 5 is the 5 highest baseScore, ties by id (year, then sequence number, compared as numbers); fewer than 5 scored means all of them. Severity and status counts are per value as returned, with none for unscored rows.

### Fortinet

- Vulnerabilities: 112
- Scored (CVSS v3.1): 112; unscored: 0
- Median baseScore of those scored: 7.50

Top 5 by baseScore:

| Rank | Id | baseScore |
| --- | --- | --- |
| 1 | CVE-2026-104286 | 9.80 |
| 2 | CVE-2026-106173 | 9.80 |
| 3 | CVE-2026-107656 | 9.80 |
| 4 | CVE-2026-126147 | 9.80 |
| 5 | CVE-2026-126148 | 9.80 |

Count per baseSeverity value as returned (and with none):

| baseSeverity | Count |
| --- | --- |
| CRITICAL | 21 |
| HIGH | 81 |
| MEDIUM | 7 |
| LOW | 3 |
| none | 0 |

Count per vulnStatus value:

| vulnStatus | Count |
| --- | --- |
| Analyzed | 1 |
| Awaiting Analysis | 111 |

### Ivanti

- Vulnerabilities: 21
- Scored (CVSS v3.1): 21; unscored: 0
- Median baseScore of those scored: 6.70

Top 5 by baseScore:

| Rank | Id | baseScore |
| --- | --- | --- |
| 1 | CVE-2026-106042 | 9.90 |
| 2 | CVE-2026-109412 | 9.90 |
| 3 | CVE-2026-121653 | 9.80 |
| 4 | CVE-2026-121683 | 9.40 |
| 5 | CVE-2026-106047 | 7.70 |

Count per baseSeverity value as returned (and with none):

| baseSeverity | Count |
| --- | --- |
| CRITICAL | 4 |
| HIGH | 4 |
| MEDIUM | 13 |
| LOW | 0 |
| none | 0 |

Count per vulnStatus value:

| vulnStatus | Count |
| --- | --- |
| Analyzed | 2 |
| Awaiting Analysis | 19 |

### Cisco

- Vulnerabilities: 96
- Scored (CVSS v3.1): 95; unscored: 1
- Median baseScore of those scored: 8.60

Top 5 by baseScore:

| Rank | Id | baseScore |
| --- | --- | --- |
| 1 | CVE-2026-76482 | 10.00 |
| 2 | CVE-2026-76299 | 9.90 |
| 3 | CVE-2026-76302 | 9.90 |
| 4 | CVE-2026-76531 | 9.90 |
| 5 | CVE-2026-76284 | 9.80 |

Count per baseSeverity value as returned (and with none):

| baseSeverity | Count |
| --- | --- |
| CRITICAL | 33 |
| HIGH | 37 |
| MEDIUM | 25 |
| LOW | 0 |
| none | 1 |

Count per vulnStatus value:

| vulnStatus | Count |
| --- | --- |
| Analyzed | 4 |
| Awaiting Analysis | 86 |
| Modified | 5 |
| Received | 1 |

### Citrix

- Vulnerabilities: 33
- Scored (CVSS v3.1): 0; unscored: 33
- Median baseScore of those scored: none

Top 5 by baseScore:

none

Count per baseSeverity value as returned (and with none):

| baseSeverity | Count |
| --- | --- |
| CRITICAL | 0 |
| HIGH | 0 |
| MEDIUM | 0 |
| LOW | 0 |
| none | 33 |

Count per vulnStatus value:

| vulnStatus | Count |
| --- | --- |
| Awaiting Analysis | 33 |

### Sonicwall

- Vulnerabilities: 4
- Scored (CVSS v3.1): 4; unscored: 0
- Median baseScore of those scored: 8.00

Top 5 by baseScore:

| Rank | Id | baseScore |
| --- | --- | --- |
| 1 | CVE-2026-109593 | 9.10 |
| 2 | CVE-2026-96540 | 8.80 |
| 3 | CVE-2026-100232 | 7.20 |
| 4 | CVE-2026-109594 | 6.80 |

Count per baseSeverity value as returned (and with none):

| baseSeverity | Count |
| --- | --- |
| CRITICAL | 1 |
| HIGH | 2 |
| MEDIUM | 1 |
| LOW | 0 |
| none | 0 |

Count per vulnStatus value:

| vulnStatus | Count |
| --- | --- |
| Awaiting Analysis | 4 |

### Juniper

- Vulnerabilities: 171
- Scored (CVSS v3.1): 171; unscored: 0
- Median baseScore of those scored: 7.50

Top 5 by baseScore:

| Rank | Id | baseScore |
| --- | --- | --- |
| 1 | CVE-2026-33789 | 9.80 |
| 2 | CVE-2026-33792 | 9.80 |
| 3 | CVE-2026-33796 | 9.80 |
| 4 | CVE-2026-101950 | 9.80 |
| 5 | CVE-2026-101954 | 9.80 |

Count per baseSeverity value as returned (and with none):

| baseSeverity | Count |
| --- | --- |
| CRITICAL | 17 |
| HIGH | 83 |
| MEDIUM | 68 |
| LOW | 3 |
| none | 0 |

Count per vulnStatus value:

| vulnStatus | Count |
| --- | --- |
| Analyzed | 2 |
| Awaiting Analysis | 169 |

## Shared ids across keywords (PULL 3)

None. No id was found under two or more keywords.

## Ids new since PULL 1 (per keyword)

- fortinet: none
- ivanti: none
- cisco: none
- citrix: none
- sonicwall: none
- juniper: none

## Changes — PULL 2 vs PULL 1

Matched by key (keyword and id together). New: 0; gone: 0; changed keys: 1 (1 changed cells). Row counts: PULL 1 437 rows, PULL 2 437 rows; 437 = 437 + 0 - 0.

Changed keys (same key, a Changes column differs):

| Key | Column | Earlier | Later |
| --- | --- | --- | --- |
| cisco, CVE-2026-91575 | lastModified | 2026-11-17T22:19:25.433 | 2026-11-19T03:17:24.053 |


## Changes — PULL 3 vs PULL 2

Matched by key (keyword and id together). New: 0; gone: 0; changed keys: 1 (2 changed cells). Row counts: PULL 2 437 rows, PULL 3 437 rows; 437 = 437 + 0 - 0.

Changed keys (same key, a Changes column differs):

| Key | Column | Earlier | Later |
| --- | --- | --- | --- |
| cisco, CVE-2026-76466 | vulnStatus | Awaiting Analysis | Analyzed |
| cisco, CVE-2026-76466 | lastModified | 2026-10-22T23:19:07.397 | 2026-11-20T20:27:15.120 |


## PROOF

### PULL 1

First response Date header (pull source time): Wed, 18 Nov 2026 23:58:39 GMT

One line per request (full request, UTC time, HTTP status):

- 2026-11-18T23:58:36Z UTC | https://services.nvd.nist.gov/rest/json/cves/2.0?keywordSearch=fortinet&pubStartDate=2026-10-01T00%3A00%3A00.000&pubEndDate=2026-12-31T23%3A59%3A59.999&resultsPerPage=2000&startIndex=0 | HTTP 200
- 2026-11-18T23:58:45Z UTC | https://services.nvd.nist.gov/rest/json/cves/2.0?keywordSearch=ivanti&pubStartDate=2026-10-01T00%3A00%3A00.000&pubEndDate=2026-12-31T23%3A59%3A59.999&resultsPerPage=2000&startIndex=0 | HTTP 200
- 2026-11-18T23:58:54Z UTC | https://services.nvd.nist.gov/rest/json/cves/2.0?keywordSearch=cisco&pubStartDate=2026-10-01T00%3A00%3A00.000&pubEndDate=2026-12-31T23%3A59%3A59.999&resultsPerPage=2000&startIndex=0 | HTTP 200
- 2026-11-18T23:59:02Z UTC | https://services.nvd.nist.gov/rest/json/cves/2.0?keywordSearch=citrix&pubStartDate=2026-10-01T00%3A00%3A00.000&pubEndDate=2026-12-31T23%3A59%3A59.999&resultsPerPage=2000&startIndex=0 | HTTP 200
- 2026-11-18T23:59:11Z UTC | https://services.nvd.nist.gov/rest/json/cves/2.0?keywordSearch=sonicwall&pubStartDate=2026-10-01T00%3A00%3A00.000&pubEndDate=2026-12-31T23%3A59%3A59.999&resultsPerPage=2000&startIndex=0 | HTTP 200
- 2026-11-18T23:59:18Z UTC | https://services.nvd.nist.gov/rest/json/cves/2.0?keywordSearch=juniper&pubStartDate=2026-10-01T00%3A00%3A00.000&pubEndDate=2026-12-31T23%3A59%3A59.999&resultsPerPage=2000&startIndex=0 | HTTP 200

### PULL 2

First response Date header (pull source time): Fri, 20 Nov 2026 00:08:00 GMT

One line per request (full request, UTC time, HTTP status):

- 2026-11-20T00:07:57Z UTC | https://services.nvd.nist.gov/rest/json/cves/2.0?keywordSearch=fortinet&pubStartDate=2026-10-01T00%3A00%3A00.000&pubEndDate=2026-12-31T23%3A59%3A59.999&resultsPerPage=2000&startIndex=0 | HTTP 200 (attempt 1)
- 2026-11-20T00:08:06Z UTC | https://services.nvd.nist.gov/rest/json/cves/2.0?keywordSearch=ivanti&pubStartDate=2026-10-01T00%3A00%3A00.000&pubEndDate=2026-12-31T23%3A59%3A59.999&resultsPerPage=2000&startIndex=0 | HTTP 200 (attempt 1)
- 2026-11-20T00:08:14Z UTC | https://services.nvd.nist.gov/rest/json/cves/2.0?keywordSearch=cisco&pubStartDate=2026-10-01T00%3A00%3A00.000&pubEndDate=2026-12-31T23%3A59%3A59.999&resultsPerPage=2000&startIndex=0 | HTTP 200 (attempt 1)
- 2026-11-20T00:08:23Z UTC | https://services.nvd.nist.gov/rest/json/cves/2.0?keywordSearch=citrix&pubStartDate=2026-10-01T00%3A00%3A00.000&pubEndDate=2026-12-31T23%3A59%3A59.999&resultsPerPage=2000&startIndex=0 | HTTP 200 (attempt 1)
- 2026-11-20T00:08:31Z UTC | https://services.nvd.nist.gov/rest/json/cves/2.0?keywordSearch=sonicwall&pubStartDate=2026-10-01T00%3A00%3A00.000&pubEndDate=2026-12-31T23%3A59%3A59.999&resultsPerPage=2000&startIndex=0 | HTTP 200 (attempt 1)
- 2026-11-20T00:08:39Z UTC | https://services.nvd.nist.gov/rest/json/cves/2.0?keywordSearch=juniper&pubStartDate=2026-10-01T00%3A00%3A00.000&pubEndDate=2026-12-31T23%3A59%3A59.999&resultsPerPage=2000&startIndex=0 | HTTP 200 (attempt 1)

### PULL 3

First response Date header (pull source time): Sat, 21 Nov 2026 00:15:36 GMT

One line per request (full request, UTC time, HTTP status):

- 2026-11-21T00:15:34Z UTC | https://services.nvd.nist.gov/rest/json/cves/2.0?keywordSearch=fortinet&pubStartDate=2026-10-01T00%3A00%3A00.000&pubEndDate=2026-12-31T23%3A59%3A59.999&resultsPerPage=2000&startIndex=0 | HTTP 200 (attempt 1)
- 2026-11-21T00:15:43Z UTC | https://services.nvd.nist.gov/rest/json/cves/2.0?keywordSearch=ivanti&pubStartDate=2026-10-01T00%3A00%3A00.000&pubEndDate=2026-12-31T23%3A59%3A59.999&resultsPerPage=2000&startIndex=0 | HTTP 200 (attempt 1)
- 2026-11-21T00:15:52Z UTC | https://services.nvd.nist.gov/rest/json/cves/2.0?keywordSearch=cisco&pubStartDate=2026-10-01T00%3A00%3A00.000&pubEndDate=2026-12-31T23%3A59%3A59.999&resultsPerPage=2000&startIndex=0 | HTTP 200 (attempt 1)
- 2026-11-21T00:16:41Z UTC | https://services.nvd.nist.gov/rest/json/cves/2.0?keywordSearch=citrix&pubStartDate=2026-10-01T00%3A00%3A00.000&pubEndDate=2026-12-31T23%3A59%3A59.999&resultsPerPage=2000&startIndex=0 | HTTP 200 (attempt 1)
- 2026-11-21T00:16:50Z UTC | https://services.nvd.nist.gov/rest/json/cves/2.0?keywordSearch=sonicwall&pubStartDate=2026-10-01T00%3A00%3A00.000&pubEndDate=2026-12-31T23%3A59%3A59.999&resultsPerPage=2000&startIndex=0 | HTTP 200 (attempt 1)
- 2026-11-21T00:16:57Z UTC | https://services.nvd.nist.gov/rest/json/cves/2.0?keywordSearch=juniper&pubStartDate=2026-10-01T00%3A00%3A00.000&pubEndDate=2026-12-31T23%3A59%3A59.999&resultsPerPage=2000&startIndex=0 | HTTP 200 (attempt 1)

### Raw excerpts — last good pull (PULL 3), first entry of each keyword's top 5

Each excerpt is the raw id, published, lastModified, vulnStatus and first cvssMetricV31 entry of that keyword's highest-scored vulnerability (ties: id), copied from the raw NVD response, pretty-printed, at most 30 lines each.

#### Fortinet

```json
{
  "id": "CVE-2026-104286",
  "published": "2026-10-01T20:17:24.010",
  "lastModified": "2026-10-28T20:09:29.257",
  "vulnStatus": "Analyzed",
  "cvssMetricV31": [
    {
      "source": "psirt@fortinet.com",
      "type": "Secondary",
      "cvssData": {
        "version": "3.1",
        "vectorString": "CVSS:3.1/AV:N/AC:L/PR:N/UI:N/S:U/C:H/I:H/A:H",
        "baseScore": 9.8,
        "baseSeverity": "CRITICAL",
        "attackVector": "NETWORK",
        "attackComplexity": "LOW",
        "privilegesRequired": "NONE",
        "userInteraction": "NONE",
        "scope": "UNCHANGED",
        "confidentialityImpact": "HIGH",
        "integrityImpact": "HIGH",
        "availabilityImpact": "HIGH"
      },
      "exploitabilityScore": 3.9,
      "impactScore": 5.9
    }
  ]
}
```

#### Ivanti

```json
{
  "id": "CVE-2026-106042",
  "published": "2026-10-13T17:17:16.273",
  "lastModified": "2026-10-14T16:08:15.347",
  "vulnStatus": "Awaiting Analysis",
  "cvssMetricV31": [
    {
      "source": "3c1d8aa1-5a33-4ea4-8992-aadd6440af75",
      "type": "Secondary",
      "cvssData": {
        "version": "3.1",
        "vectorString": "CVSS:3.1/AV:N/AC:L/PR:L/UI:N/S:C/C:H/I:H/A:H",
        "baseScore": 9.9,
        "baseSeverity": "CRITICAL",
        "attackVector": "NETWORK",
        "attackComplexity": "LOW",
        "privilegesRequired": "LOW",
        "userInteraction": "NONE",
        "scope": "CHANGED",
        "confidentialityImpact": "HIGH",
        "integrityImpact": "HIGH",
        "availabilityImpact": "HIGH"
      },
      "exploitabilityScore": 3.1,
      "impactScore": 6.0
    }
  ]
}
```

#### Cisco

```json
{
  "id": "CVE-2026-76482",
  "published": "2026-10-07T17:17:00.773",
  "lastModified": "2026-11-07T18:17:27.353",
  "vulnStatus": "Awaiting Analysis",
  "cvssMetricV31": [
    {
      "source": "psirt@cisco.com",
      "type": "Secondary",
      "cvssData": {
        "version": "3.1",
        "vectorString": "CVSS:3.1/AV:N/AC:L/PR:N/UI:N/S:C/C:H/I:H/A:H",
        "baseScore": 10.0,
        "baseSeverity": "CRITICAL",
        "attackVector": "NETWORK",
        "attackComplexity": "LOW",
        "privilegesRequired": "NONE",
        "userInteraction": "NONE",
        "scope": "CHANGED",
        "confidentialityImpact": "HIGH",
        "integrityImpact": "HIGH",
        "availabilityImpact": "HIGH"
      },
      "exploitabilityScore": 3.9,
      "impactScore": 6.0
    }
  ]
}
```

#### Citrix

none (no scored vulnerabilities, so no top 5 and no raw item).

#### Sonicwall

```json
{
  "id": "CVE-2026-109593",
  "published": "2026-11-03T17:17:53.690",
  "lastModified": "2026-11-03T20:32:50.687",
  "vulnStatus": "Awaiting Analysis",
  "cvssMetricV31": [
    {
      "source": "134c704f-9b21-4f2e-91b3-4a467353bcc0",
      "type": "Secondary",
      "cvssData": {
        "version": "3.1",
        "vectorString": "CVSS:3.1/AV:N/AC:L/PR:N/UI:N/S:U/C:H/I:N/A:H",
        "baseScore": 9.1,
        "baseSeverity": "CRITICAL",
        "attackVector": "NETWORK",
        "attackComplexity": "LOW",
        "privilegesRequired": "NONE",
        "userInteraction": "NONE",
        "scope": "UNCHANGED",
        "confidentialityImpact": "HIGH",
        "integrityImpact": "NONE",
        "availabilityImpact": "HIGH"
      },
      "exploitabilityScore": 3.9,
      "impactScore": 5.2
    }
  ]
}
```

#### Juniper

```json
{
  "id": "CVE-2026-33789",
  "published": "2026-10-14T17:18:27.763",
  "lastModified": "2026-10-15T16:24:19.073",
  "vulnStatus": "Awaiting Analysis",
  "cvssMetricV31": [
    {
      "source": "sirt@juniper.net",
      "type": "Secondary",
      "cvssData": {
        "version": "3.1",
        "vectorString": "CVSS:3.1/AV:N/AC:L/PR:N/UI:N/S:U/C:H/I:H/A:H",
        "baseScore": 9.8,
        "baseSeverity": "CRITICAL",
        "attackVector": "NETWORK",
        "attackComplexity": "LOW",
        "privilegesRequired": "NONE",
        "userInteraction": "NONE",
        "scope": "UNCHANGED",
        "confidentialityImpact": "HIGH",
        "integrityImpact": "HIGH",
        "availabilityImpact": "HIGH"
      },
      "exploitabilityScore": 3.9,
      "impactScore": 5.9
    }
  ]
}
```

## Data files

Attached under Rule 25 as data files (one row per keyword and vulnerability returned, sorted by keyword then id; fields, in order: keyword, id, published, lastModified, vulnStatus, baseScore, baseSeverity; key column keyword and id together):

```synmerco-data
6865aefcfe5bdbc8e8176369b41eefc092e44f999435f25ae62c4824432d6cb8 edge-cves-pull1.csv
88cb3f1e912a1fb5ffe107569b2f8095ac1ef158d3711f853f06e9b72fc05db1 edge-cves-pull2.csv
500243a88378e6cf1318702216899b9c54c292358c2b6ccf6f7b7a4436abb842 edge-cves-pull3.csv
```

## Sources

- National Vulnerability Database, host services.nvd.nist.gov, endpoint /rest/json/cves/2.0. Only the source listed here was used. The six request URLs per pull are the full request lines in PROOF above (keywordSearch set to each keyword, pubStartDate 2026-10-01T00:00:00.000, pubEndDate 2026-12-31T23:59:59.999, resultsPerPage 2000, startIndex 0).
