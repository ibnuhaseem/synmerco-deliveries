# Housing finance rules since 1 July 2026: three regulators' documents and open comment periods, three pulls

## Executive summary

Across three timed pulls of the Federal Register API (www.federalregister.gov, /api/v1/documents.json plus /api/v1/documents/{document_number}.json), the Consumer Financial Protection Bureau (consumer-financial-protection-bureau), the Department of Housing and Urban Development (housing-and-urban-development-department) and the Federal Housing Finance Agency (federal-housing-finance-agency) published documents on or after 2026-07-01. The last good pull (PULL 3, source time `Date: Sat, 21 Nov 2026 04:21:01 GMT`) returned raw counts of 11, 105 and 13 respectively: 129 rows (one per document and agency) covering 127 unique documents, of which 120 rows are Notices, 5 Proposed Rules and 4 Rules. On the pull 3 date (2026-11-21) 41 documents still have a comment period closing on or after that date and 1 document has an effective date on or after it. Between pulls the row count went 125 -> 126 -> 129; every change was a new key (no gone keys, no changed type, comments_close_on or effective_on values). All 386 requests across the three pulls returned HTTP 200. Rows live in the attached data files D2-D4; this report gives the tables, lists, changes and PROOF.

## Raw counts per pull

| Pull | Source time (first response Date header) | consumer-financial-protection-bureau | housing-and-urban-development-department | federal-housing-finance-agency | CSV rows | unique documents | CSV SHA-256 |
|---|---|---|---|---|---|---|---|
| PULL 1 | `Date: Thu, 19 Nov 2026 03:59:23 GMT` | `"count":11` | `"count":103` | `"count":11` | 125 | 123 | 116b9084710f06bb6b813c668a3988df98ef901e883be2ad922ab368e108afe8 |
| PULL 2 | `Date: Fri, 20 Nov 2026 04:18:49 GMT` | `"count":11` | `"count":104` | `"count":11` | 126 | 124 | f2046facb6bed6a0e2504835fe4c76cc8fdacfa0581dcce6f28a9ad478d708fc |
| PULL 3 | `Date: Sat, 21 Nov 2026 04:21:01 GMT` | `"count":11` | `"count":105` | `"count":13` | 129 | 127 | b88988731d26574d0ef09b15b13383ba53d7998d1f1daa84b9a6117a1623dfac |

## Agency tables (last good pull: PULL 3, pull date 2026-11-21)

### Documents per agency and type

| agency | type | documents |
|---|---|---|
| consumer-financial-protection-bureau | Notice | 10 |
| consumer-financial-protection-bureau | Proposed Rule | 1 |
| consumer-financial-protection-bureau | **total** | 11 |
| housing-and-urban-development-department | Notice | 99 |
| housing-and-urban-development-department | Proposed Rule | 2 |
| housing-and-urban-development-department | Rule | 4 |
| housing-and-urban-development-department | **total** | 105 |
| federal-housing-finance-agency | Notice | 11 |
| federal-housing-finance-agency | Proposed Rule | 2 |
| federal-housing-finance-agency | **total** | 13 |

### Documents per agency and publication month

| agency | publication month | documents |
|---|---|---|
| consumer-financial-protection-bureau | 2026-07 | 1 |
| consumer-financial-protection-bureau | 2026-08 | 2 |
| consumer-financial-protection-bureau | 2026-09 | 1 |
| consumer-financial-protection-bureau | 2026-10 | 4 |
| consumer-financial-protection-bureau | 2026-11 | 3 |
| consumer-financial-protection-bureau | **total** | 11 |
| housing-and-urban-development-department | 2026-07 | 20 |
| housing-and-urban-development-department | 2026-08 | 20 |
| housing-and-urban-development-department | 2026-09 | 25 |
| housing-and-urban-development-department | 2026-10 | 22 |
| housing-and-urban-development-department | 2026-11 | 18 |
| housing-and-urban-development-department | **total** | 105 |
| federal-housing-finance-agency | 2026-07 | 3 |
| federal-housing-finance-agency | 2026-08 | 4 |
| federal-housing-finance-agency | 2026-09 | 2 |
| federal-housing-finance-agency | 2026-10 | 2 |
| federal-housing-finance-agency | 2026-11 | 2 |
| federal-housing-finance-agency | **total** | 13 |

## Open comment periods (comments_close_on on or after 2026-11-21, soonest first, ties by document_number)

41 documents. Format: comments_close_on | document_number | agencies (TASK slugs of its CSV rows, joined by ';'). Each date is excerpted on that document's PULL 3 request line in PROOF.

1. 2026-11-23 | 2026-19317 | housing-and-urban-development-department
2. 2026-11-23 | 2026-19387 | housing-and-urban-development-department
3. 2026-11-24 | 2026-19650 | housing-and-urban-development-department
4. 2026-11-24 | 2026-19651 | housing-and-urban-development-department
5. 2026-11-30 | 2026-19881 | housing-and-urban-development-department
6. 2026-11-30 | 2026-22039 | housing-and-urban-development-department
7. 2026-11-30 | 2026-22128 | housing-and-urban-development-department
8. 2026-11-30 | 2026-22129 | housing-and-urban-development-department
9. 2026-11-30 | 2026-22135 | housing-and-urban-development-department
10. 2026-11-30 | 2026-22136 | housing-and-urban-development-department
11. 2026-11-30 | 2026-22219 | housing-and-urban-development-department
12. 2026-12-01 | 2026-20183 | housing-and-urban-development-department
13. 2026-12-04 | 2026-20374 | housing-and-urban-development-department
14. 2026-12-04 | 2026-22554 | housing-and-urban-development-department
15. 2026-12-07 | 2026-20679 | housing-and-urban-development-department
16. 2026-12-07 | 2026-20682 | housing-and-urban-development-department
17. 2026-12-14 | 2026-20823 | housing-and-urban-development-department
18. 2026-12-14 | 2026-21076 | consumer-financial-protection-bureau
19. 2026-12-14 | 2026-22207 | housing-and-urban-development-department
20. 2026-12-16 | 2026-23243 | housing-and-urban-development-department
21. 2026-12-21 | 2026-21426 | housing-and-urban-development-department
22. 2026-12-21 | 2026-21451 | housing-and-urban-development-department
23. 2026-12-21 | 2026-23701 | federal-housing-finance-agency
24. 2026-12-21 | 2026-23702 | federal-housing-finance-agency
25. 2026-12-22 | 2026-21660 | housing-and-urban-development-department
26. 2026-12-29 | 2026-22188 | housing-and-urban-development-department
27. 2026-12-29 | 2026-22227 | consumer-financial-protection-bureau
28. 2026-12-29 | 2026-22228 | consumer-financial-protection-bureau
29. 2027-01-04 | 2026-22570 | housing-and-urban-development-department
30. 2027-01-04 | 2026-22571 | housing-and-urban-development-department
31. 2027-01-04 | 2026-22638 | housing-and-urban-development-department
32. 2027-01-04 | 2026-22639 | housing-and-urban-development-department
33. 2027-01-08 | 2026-22770 | housing-and-urban-development-department
34. 2027-01-11 | 2026-22896 | housing-and-urban-development-department
35. 2027-01-11 | 2026-22901 | housing-and-urban-development-department
36. 2027-01-11 | 2026-23071 | housing-and-urban-development-department
37. 2027-01-12 | 2026-23069 | housing-and-urban-development-department
38. 2027-01-12 | 2026-23070 | housing-and-urban-development-department
39. 2027-01-12 | 2026-23151 | consumer-financial-protection-bureau
40. 2027-01-12 | 2026-23152 | consumer-financial-protection-bureau
41. 2027-01-19 | 2026-23565 | housing-and-urban-development-department

## Coming effective dates (effective_on on or after 2026-11-21, soonest first, ties by document_number)

1 document. Format: effective_on | document_number | agencies (joined by ';').

1. 2026-12-14 | 2026-23003 | housing-and-urban-development-department

## Rule summaries (type Rule or Proposed Rule, PULL 3; one line per document_number, written from its title only)

- 2026-13834 (Proposed Rule; consumer-financial-protection-bureau): Covers a request for information on promoting access to mortgage credit.
- 2026-13939 (Proposed Rule; housing-and-urban-development-department): Covers the rescission of floodplain management and protection of wetlands, minimum property standards for flood hazard exposure, and building to the Federal Flood Risk Management Standard.
- 2026-14035 (Proposed Rule; federal-housing-finance-agency): Covers Federal Home Loan Bank new business activities.
- 2026-14036 (Proposed Rule; federal-housing-finance-agency): Covers a suspended counterparty program.
- 2026-16228 (Proposed Rule; housing-and-urban-development-department): Covers HUD's implementation of the Fair Housing Act's disparate impact standard and amendments to HUD's Title VI regulations.
- 2026-16967 (Rule; housing-and-urban-development-department): Covers a correcting amendment revising HUD's noise abatement and control regulations.
- 2026-19743 (Rule; housing-and-urban-development-department): Covers the announcement of a fee to cover credit subsidy costs for FY 2027 under the Section 108 Loan Guarantee Program.
- 2026-20374 (Rule; housing-and-urban-development-department): Covers Section 3 benchmarks for creating economic opportunities for low- and very low-income persons and eligible businesses.
- 2026-23003 (Rule; housing-and-urban-development-department): Covers verification of eligible status under the Housing and Community Development Act of 1980.

## Changes: PULL 2 vs PULL 1 (matched by key document_number + agency; Changes columns: type, comments_close_on, effective_on)

- Counts: new = 1, gone = 0, changed = 0
- Row counts: PULL 1 = 125, PULL 2 = 126; check: 126 = 125 + 1 - 0
- New (key only in the later pull):
  - 2026-23565 + housing-and-urban-development-department (type Notice, publication_date 2026-11-19, comments_close_on 2027-01-19, effective_on empty)
- Gone (key only in the earlier pull): none
- Changed (same key, a Changes column differs): none

## Changes: PULL 3 vs PULL 2 (matched by key document_number + agency; Changes columns: type, comments_close_on, effective_on)

- Counts: new = 3, gone = 0, changed = 0
- Row counts: PULL 2 = 126, PULL 3 = 129; check: 129 = 126 + 3 - 0
- New (key only in the later pull):
  - 2026-23696 + housing-and-urban-development-department (type Notice, publication_date 2026-11-20, comments_close_on empty, effective_on empty)
  - 2026-23701 + federal-housing-finance-agency (type Notice, publication_date 2026-11-20, comments_close_on 2026-12-21, effective_on empty)
  - 2026-23702 + federal-housing-finance-agency (type Notice, publication_date 2026-11-20, comments_close_on 2026-12-21, effective_on empty)
- Gone (key only in the earlier pull): none
- Changed (same key, a Changes column differs): none

## Data files (Rule 25)

D2-D4 are attached as data files; columns, in order: document_number, agency, type, publication_date, comments_close_on, effective_on, title (key: document_number + agency).

```synmerco-data
116b9084710f06bb6b813c668a3988df98ef901e883be2ad922ab368e108afe8 housing-rules-pull1.csv
f2046facb6bed6a0e2504835fe4c76cc8fdacfa0581dcce6f28a9ad478d708fc housing-rules-pull2.csv
b88988731d26574d0ef09b15b13383ba53d7998d1f1daa84b9a6117a1623dfac housing-rules-pull3.csv
```

## Answers

1. Each pull's PROOF quotes the three raw counts, and that pull's CSV holds one row per document and agency the requests returned: Yes. Raw counts PULL 1 11/103/11, PULL 2 11/104/11, PULL 3 11/105/13 (CFPB/HUD/FHFA), quoted verbatim in the count excerpts below (see excerpts 1-9). Row counts 125, 126, 129 equal the sum of that pull's three raw counts: one row per (document_number, agency); documents returned by two agencies' queries appear once under each.
2. The three CSV files are attached with exactly the listed columns: Yes. housing-rules-pull1.csv (D2), housing-rules-pull2.csv (D3), housing-rules-pull3.csv (D4), header `document_number,agency,type,publication_date,comments_close_on,effective_on,title`, none header-only (no pull failed); SHA-256 in the synmerco-data block above.
3. The agency tables, open comment list, effective date list and summaries follow the TASK and agree with the last good pull's CSV: Yes. All are computed by script from housing-rules-pull3.csv (pull date 2026-11-21 = UTC date of PULL 3's first request); each summary restates only its title (titles are in the CSV title column); comments_close_on/effective_on values are excerpted per listed document (see the PULL 3 request log lines).
4. PLATFORM RECORD timing, row counts, SHA-256, source times and change counts: Yes. PULL 1 note recordedAt 2026-11-19 04:00:09.481109+00, PULL 2 note 2026-11-20 04:19:16.240751+00, PULL 3 note 2026-11-21 04:21:29.375654+00 (each at least 24 hours after the one before); each note gives its CSV's row count and SHA-256 as in the synmerco-data block. Source times increase: `Date: Thu, 19 Nov 2026 03:59:23 GMT` < `Date: Fri, 20 Nov 2026 04:18:49 GMT` < `Date: Sat, 21 Nov 2026 04:21:01 GMT`. Change counts agree with the CSV files: 126 = 125 + 1 - 0 and 129 = 126 + 3 - 0.

## PROOF

Every request is an HTTP GET to host www.federalregister.gov, each tried once and answered on the first attempt. One line per request: full request URL, UTC time, HTTP status (space-separated); on PULL 3, lines of documents in the two date lists add, in brackets, the verbatim comments_close_on and effective_on fields of that response. Request blocks with the raw counts (and, for PULL 3, each agency's raw first result) follow the logs.

### PULL 1 request log

Source time (first response Date header): `Date: Thu, 19 Nov 2026 03:59:23 GMT`

127 requests, one per line: full request URL, UTC time, HTTP status

```
https://www.federalregister.gov/api/v1/documents.json?conditions%5Bagencies%5D%5B%5D=consumer-financial-protection-bureau&conditions%5Bpublication_date%5D%5Bgte%5D=2026-07-01&per_page=100&page=1&fields%5B%5D=document_number&fields%5B%5D=type&fields%5B%5D=publication_date&fields%5B%5D=title&fields%5B%5D=agencies 2026-11-19T03:59:23Z 200
https://www.federalregister.gov/api/v1/documents.json?conditions%5Bagencies%5D%5B%5D=housing-and-urban-development-department&conditions%5Bpublication_date%5D%5Bgte%5D=2026-07-01&per_page=100&page=1&fields%5B%5D=document_number&fields%5B%5D=type&fields%5B%5D=publication_date&fields%5B%5D=title&fields%5B%5D=agencies 2026-11-19T03:59:23Z 200
https://www.federalregister.gov/api/v1/documents.json?conditions%5Bagencies%5D%5B%5D=housing-and-urban-development-department&conditions%5Bpublication_date%5D%5Bgte%5D=2026-07-01&per_page=100&page=2&fields%5B%5D=document_number&fields%5B%5D=type&fields%5B%5D=publication_date&fields%5B%5D=title&fields%5B%5D=agencies 2026-11-19T03:59:23Z 200
https://www.federalregister.gov/api/v1/documents.json?conditions%5Bagencies%5D%5B%5D=federal-housing-finance-agency&conditions%5Bpublication_date%5D%5Bgte%5D=2026-07-01&per_page=100&page=1&fields%5B%5D=document_number&fields%5B%5D=type&fields%5B%5D=publication_date&fields%5B%5D=title&fields%5B%5D=agencies 2026-11-19T03:59:23Z 200
https://www.federalregister.gov/api/v1/documents/2026-13378.json 2026-11-19T03:59:24Z 200
https://www.federalregister.gov/api/v1/documents/2026-13537.json 2026-11-19T03:59:24Z 200
https://www.federalregister.gov/api/v1/documents/2026-13539.json 2026-11-19T03:59:24Z 200
https://www.federalregister.gov/api/v1/documents/2026-13542.json 2026-11-19T03:59:24Z 200
https://www.federalregister.gov/api/v1/documents/2026-13543.json 2026-11-19T03:59:24Z 200
https://www.federalregister.gov/api/v1/documents/2026-13660.json 2026-11-19T03:59:24Z 200
https://www.federalregister.gov/api/v1/documents/2026-13672.json 2026-11-19T03:59:24Z 200
https://www.federalregister.gov/api/v1/documents/2026-13735.json 2026-11-19T03:59:25Z 200
https://www.federalregister.gov/api/v1/documents/2026-13760.json 2026-11-19T03:59:25Z 200
https://www.federalregister.gov/api/v1/documents/2026-13814.json 2026-11-19T03:59:25Z 200
https://www.federalregister.gov/api/v1/documents/2026-13834.json 2026-11-19T03:59:25Z 200
https://www.federalregister.gov/api/v1/documents/2026-13933.json 2026-11-19T03:59:25Z 200
https://www.federalregister.gov/api/v1/documents/2026-13934.json 2026-11-19T03:59:25Z 200
https://www.federalregister.gov/api/v1/documents/2026-13939.json 2026-11-19T03:59:25Z 200
https://www.federalregister.gov/api/v1/documents/2026-13945.json 2026-11-19T03:59:25Z 200
https://www.federalregister.gov/api/v1/documents/2026-13969.json 2026-11-19T03:59:26Z 200
https://www.federalregister.gov/api/v1/documents/2026-14035.json 2026-11-19T03:59:26Z 200
https://www.federalregister.gov/api/v1/documents/2026-14036.json 2026-11-19T03:59:26Z 200
https://www.federalregister.gov/api/v1/documents/2026-14037.json 2026-11-19T03:59:26Z 200
https://www.federalregister.gov/api/v1/documents/2026-14432.json 2026-11-19T03:59:26Z 200
https://www.federalregister.gov/api/v1/documents/2026-14873.json 2026-11-19T03:59:26Z 200
https://www.federalregister.gov/api/v1/documents/2026-15154.json 2026-11-19T03:59:26Z 200
https://www.federalregister.gov/api/v1/documents/2026-15428.json 2026-11-19T03:59:27Z 200
https://www.federalregister.gov/api/v1/documents/2026-15487.json 2026-11-19T03:59:27Z 200
https://www.federalregister.gov/api/v1/documents/2026-15643.json 2026-11-19T03:59:27Z 200
https://www.federalregister.gov/api/v1/documents/2026-15751.json 2026-11-19T03:59:27Z 200
https://www.federalregister.gov/api/v1/documents/2026-15753.json 2026-11-19T03:59:27Z 200
https://www.federalregister.gov/api/v1/documents/2026-15796.json 2026-11-19T03:59:27Z 200
https://www.federalregister.gov/api/v1/documents/2026-16042.json 2026-11-19T03:59:27Z 200
https://www.federalregister.gov/api/v1/documents/2026-16228.json 2026-11-19T03:59:27Z 200
https://www.federalregister.gov/api/v1/documents/2026-16242.json 2026-11-19T03:59:27Z 200
https://www.federalregister.gov/api/v1/documents/2026-16499.json 2026-11-19T03:59:28Z 200
https://www.federalregister.gov/api/v1/documents/2026-16535.json 2026-11-19T03:59:28Z 200
https://www.federalregister.gov/api/v1/documents/2026-16613.json 2026-11-19T03:59:28Z 200
https://www.federalregister.gov/api/v1/documents/2026-16963.json 2026-11-19T03:59:28Z 200
https://www.federalregister.gov/api/v1/documents/2026-16967.json 2026-11-19T03:59:28Z 200
https://www.federalregister.gov/api/v1/documents/2026-17051.json 2026-11-19T03:59:28Z 200
https://www.federalregister.gov/api/v1/documents/2026-17083.json 2026-11-19T03:59:28Z 200
https://www.federalregister.gov/api/v1/documents/2026-17085.json 2026-11-19T03:59:29Z 200
https://www.federalregister.gov/api/v1/documents/2026-17210.json 2026-11-19T03:59:29Z 200
https://www.federalregister.gov/api/v1/documents/2026-17291.json 2026-11-19T03:59:29Z 200
https://www.federalregister.gov/api/v1/documents/2026-17307.json 2026-11-19T03:59:29Z 200
https://www.federalregister.gov/api/v1/documents/2026-17325.json 2026-11-19T03:59:29Z 200
https://www.federalregister.gov/api/v1/documents/2026-17557.json 2026-11-19T03:59:29Z 200
https://www.federalregister.gov/api/v1/documents/2026-17558.json 2026-11-19T03:59:29Z 200
https://www.federalregister.gov/api/v1/documents/2026-17585.json 2026-11-19T03:59:29Z 200
https://www.federalregister.gov/api/v1/documents/2026-17586.json 2026-11-19T03:59:30Z 200
https://www.federalregister.gov/api/v1/documents/2026-17587.json 2026-11-19T03:59:30Z 200
https://www.federalregister.gov/api/v1/documents/2026-17777.json 2026-11-19T03:59:30Z 200
https://www.federalregister.gov/api/v1/documents/2026-17881.json 2026-11-19T03:59:30Z 200
https://www.federalregister.gov/api/v1/documents/2026-17889.json 2026-11-19T03:59:30Z 200
https://www.federalregister.gov/api/v1/documents/2026-17891.json 2026-11-19T03:59:30Z 200
https://www.federalregister.gov/api/v1/documents/2026-18163.json 2026-11-19T03:59:30Z 200
https://www.federalregister.gov/api/v1/documents/2026-18541.json 2026-11-19T03:59:31Z 200
https://www.federalregister.gov/api/v1/documents/2026-18555.json 2026-11-19T03:59:31Z 200
https://www.federalregister.gov/api/v1/documents/2026-18824.json 2026-11-19T03:59:31Z 200
https://www.federalregister.gov/api/v1/documents/2026-18827.json 2026-11-19T03:59:31Z 200
https://www.federalregister.gov/api/v1/documents/2026-19168.json 2026-11-19T03:59:31Z 200
https://www.federalregister.gov/api/v1/documents/2026-19169.json 2026-11-19T03:59:31Z 200
https://www.federalregister.gov/api/v1/documents/2026-19317.json 2026-11-19T03:59:31Z 200
https://www.federalregister.gov/api/v1/documents/2026-19387.json 2026-11-19T03:59:32Z 200
https://www.federalregister.gov/api/v1/documents/2026-19455.json 2026-11-19T03:59:32Z 200
https://www.federalregister.gov/api/v1/documents/2026-19458.json 2026-11-19T03:59:32Z 200
https://www.federalregister.gov/api/v1/documents/2026-19460.json 2026-11-19T03:59:32Z 200
https://www.federalregister.gov/api/v1/documents/2026-19489.json 2026-11-19T03:59:32Z 200
https://www.federalregister.gov/api/v1/documents/2026-19528.json 2026-11-19T03:59:32Z 200
https://www.federalregister.gov/api/v1/documents/2026-19600.json 2026-11-19T03:59:32Z 200
https://www.federalregister.gov/api/v1/documents/2026-19650.json 2026-11-19T03:59:33Z 200
https://www.federalregister.gov/api/v1/documents/2026-19651.json 2026-11-19T03:59:33Z 200
https://www.federalregister.gov/api/v1/documents/2026-19683.json 2026-11-19T03:59:33Z 200
https://www.federalregister.gov/api/v1/documents/2026-19743.json 2026-11-19T03:59:33Z 200
https://www.federalregister.gov/api/v1/documents/2026-19782.json 2026-11-19T03:59:33Z 200
https://www.federalregister.gov/api/v1/documents/2026-19784.json 2026-11-19T03:59:33Z 200
https://www.federalregister.gov/api/v1/documents/2026-19881.json 2026-11-19T03:59:34Z 200
https://www.federalregister.gov/api/v1/documents/2026-19955.json 2026-11-19T03:59:34Z 200
https://www.federalregister.gov/api/v1/documents/2026-20042.json 2026-11-19T03:59:34Z 200
https://www.federalregister.gov/api/v1/documents/2026-20086.json 2026-11-19T03:59:34Z 200
https://www.federalregister.gov/api/v1/documents/2026-20183.json 2026-11-19T03:59:34Z 200
https://www.federalregister.gov/api/v1/documents/2026-20374.json 2026-11-19T03:59:34Z 200
https://www.federalregister.gov/api/v1/documents/2026-20390.json 2026-11-19T03:59:34Z 200
https://www.federalregister.gov/api/v1/documents/2026-20679.json 2026-11-19T03:59:34Z 200
https://www.federalregister.gov/api/v1/documents/2026-20682.json 2026-11-19T03:59:35Z 200
https://www.federalregister.gov/api/v1/documents/2026-20822.json 2026-11-19T03:59:35Z 200
https://www.federalregister.gov/api/v1/documents/2026-20823.json 2026-11-19T03:59:35Z 200
https://www.federalregister.gov/api/v1/documents/2026-20826.json 2026-11-19T03:59:35Z 200
https://www.federalregister.gov/api/v1/documents/2026-20827.json 2026-11-19T03:59:35Z 200
https://www.federalregister.gov/api/v1/documents/2026-20953.json 2026-11-19T03:59:35Z 200
https://www.federalregister.gov/api/v1/documents/2026-21011.json 2026-11-19T03:59:35Z 200
https://www.federalregister.gov/api/v1/documents/2026-21076.json 2026-11-19T03:59:36Z 200
https://www.federalregister.gov/api/v1/documents/2026-21426.json 2026-11-19T03:59:36Z 200
https://www.federalregister.gov/api/v1/documents/2026-21451.json 2026-11-19T03:59:36Z 200
https://www.federalregister.gov/api/v1/documents/2026-21511.json 2026-11-19T03:59:36Z 200
https://www.federalregister.gov/api/v1/documents/2026-21660.json 2026-11-19T03:59:36Z 200
https://www.federalregister.gov/api/v1/documents/2026-21886.json 2026-11-19T03:59:36Z 200
https://www.federalregister.gov/api/v1/documents/2026-22039.json 2026-11-19T03:59:36Z 200
https://www.federalregister.gov/api/v1/documents/2026-22128.json 2026-11-19T03:59:36Z 200
https://www.federalregister.gov/api/v1/documents/2026-22129.json 2026-11-19T03:59:37Z 200
https://www.federalregister.gov/api/v1/documents/2026-22135.json 2026-11-19T03:59:37Z 200
https://www.federalregister.gov/api/v1/documents/2026-22136.json 2026-11-19T03:59:37Z 200
https://www.federalregister.gov/api/v1/documents/2026-22188.json 2026-11-19T03:59:37Z 200
https://www.federalregister.gov/api/v1/documents/2026-22207.json 2026-11-19T03:59:37Z 200
https://www.federalregister.gov/api/v1/documents/2026-22219.json 2026-11-19T03:59:37Z 200
https://www.federalregister.gov/api/v1/documents/2026-22227.json 2026-11-19T03:59:37Z 200
https://www.federalregister.gov/api/v1/documents/2026-22228.json 2026-11-19T03:59:38Z 200
https://www.federalregister.gov/api/v1/documents/2026-22357.json 2026-11-19T03:59:38Z 200
https://www.federalregister.gov/api/v1/documents/2026-22417.json 2026-11-19T03:59:38Z 200
https://www.federalregister.gov/api/v1/documents/2026-22554.json 2026-11-19T03:59:38Z 200
https://www.federalregister.gov/api/v1/documents/2026-22570.json 2026-11-19T03:59:38Z 200
https://www.federalregister.gov/api/v1/documents/2026-22571.json 2026-11-19T03:59:38Z 200
https://www.federalregister.gov/api/v1/documents/2026-22638.json 2026-11-19T03:59:38Z 200
https://www.federalregister.gov/api/v1/documents/2026-22639.json 2026-11-19T03:59:38Z 200
https://www.federalregister.gov/api/v1/documents/2026-22645.json 2026-11-19T03:59:38Z 200
https://www.federalregister.gov/api/v1/documents/2026-22770.json 2026-11-19T03:59:39Z 200
https://www.federalregister.gov/api/v1/documents/2026-22838.json 2026-11-19T03:59:39Z 200
https://www.federalregister.gov/api/v1/documents/2026-22896.json 2026-11-19T03:59:39Z 200
https://www.federalregister.gov/api/v1/documents/2026-22901.json 2026-11-19T03:59:39Z 200
https://www.federalregister.gov/api/v1/documents/2026-23003.json 2026-11-19T03:59:39Z 200
https://www.federalregister.gov/api/v1/documents/2026-23069.json 2026-11-19T03:59:39Z 200
https://www.federalregister.gov/api/v1/documents/2026-23070.json 2026-11-19T03:59:39Z 200
https://www.federalregister.gov/api/v1/documents/2026-23071.json 2026-11-19T03:59:39Z 200
https://www.federalregister.gov/api/v1/documents/2026-23151.json 2026-11-19T03:59:40Z 200
https://www.federalregister.gov/api/v1/documents/2026-23152.json 2026-11-19T03:59:40Z 200
https://www.federalregister.gov/api/v1/documents/2026-23243.json 2026-11-19T03:59:40Z 200
```

### PULL 2 request log

Source time (first response Date header): `Date: Fri, 20 Nov 2026 04:18:49 GMT`

128 requests, one per line: full request URL, UTC time, HTTP status

```
https://www.federalregister.gov/api/v1/documents.json?conditions%5Bagencies%5D%5B%5D=consumer-financial-protection-bureau&conditions%5Bpublication_date%5D%5Bgte%5D=2026-07-01&per_page=100&page=1&fields%5B%5D=document_number&fields%5B%5D=type&fields%5B%5D=publication_date&fields%5B%5D=title&fields%5B%5D=agencies 2026-11-20T04:18:49Z 200
https://www.federalregister.gov/api/v1/documents.json?conditions%5Bagencies%5D%5B%5D=housing-and-urban-development-department&conditions%5Bpublication_date%5D%5Bgte%5D=2026-07-01&per_page=100&page=1&fields%5B%5D=document_number&fields%5B%5D=type&fields%5B%5D=publication_date&fields%5B%5D=title&fields%5B%5D=agencies 2026-11-20T04:18:49Z 200
https://www.federalregister.gov/api/v1/documents.json?conditions%5Bagencies%5D%5B%5D=housing-and-urban-development-department&conditions%5Bpublication_date%5D%5Bgte%5D=2026-07-01&per_page=100&page=2&fields%5B%5D=document_number&fields%5B%5D=type&fields%5B%5D=publication_date&fields%5B%5D=title&fields%5B%5D=agencies 2026-11-20T04:18:49Z 200
https://www.federalregister.gov/api/v1/documents.json?conditions%5Bagencies%5D%5B%5D=federal-housing-finance-agency&conditions%5Bpublication_date%5D%5Bgte%5D=2026-07-01&per_page=100&page=1&fields%5B%5D=document_number&fields%5B%5D=type&fields%5B%5D=publication_date&fields%5B%5D=title&fields%5B%5D=agencies 2026-11-20T04:18:49Z 200
https://www.federalregister.gov/api/v1/documents/2026-13378.json 2026-11-20T04:18:49Z 200
https://www.federalregister.gov/api/v1/documents/2026-13537.json 2026-11-20T04:18:49Z 200
https://www.federalregister.gov/api/v1/documents/2026-13539.json 2026-11-20T04:18:50Z 200
https://www.federalregister.gov/api/v1/documents/2026-13542.json 2026-11-20T04:18:50Z 200
https://www.federalregister.gov/api/v1/documents/2026-13543.json 2026-11-20T04:18:50Z 200
https://www.federalregister.gov/api/v1/documents/2026-13660.json 2026-11-20T04:18:50Z 200
https://www.federalregister.gov/api/v1/documents/2026-13672.json 2026-11-20T04:18:50Z 200
https://www.federalregister.gov/api/v1/documents/2026-13735.json 2026-11-20T04:18:50Z 200
https://www.federalregister.gov/api/v1/documents/2026-13760.json 2026-11-20T04:18:51Z 200
https://www.federalregister.gov/api/v1/documents/2026-13814.json 2026-11-20T04:18:51Z 200
https://www.federalregister.gov/api/v1/documents/2026-13834.json 2026-11-20T04:18:51Z 200
https://www.federalregister.gov/api/v1/documents/2026-13933.json 2026-11-20T04:18:51Z 200
https://www.federalregister.gov/api/v1/documents/2026-13934.json 2026-11-20T04:18:51Z 200
https://www.federalregister.gov/api/v1/documents/2026-13939.json 2026-11-20T04:18:51Z 200
https://www.federalregister.gov/api/v1/documents/2026-13945.json 2026-11-20T04:18:51Z 200
https://www.federalregister.gov/api/v1/documents/2026-13969.json 2026-11-20T04:18:52Z 200
https://www.federalregister.gov/api/v1/documents/2026-14035.json 2026-11-20T04:18:52Z 200
https://www.federalregister.gov/api/v1/documents/2026-14036.json 2026-11-20T04:18:52Z 200
https://www.federalregister.gov/api/v1/documents/2026-14037.json 2026-11-20T04:18:52Z 200
https://www.federalregister.gov/api/v1/documents/2026-14432.json 2026-11-20T04:18:52Z 200
https://www.federalregister.gov/api/v1/documents/2026-14873.json 2026-11-20T04:18:52Z 200
https://www.federalregister.gov/api/v1/documents/2026-15154.json 2026-11-20T04:18:52Z 200
https://www.federalregister.gov/api/v1/documents/2026-15428.json 2026-11-20T04:18:52Z 200
https://www.federalregister.gov/api/v1/documents/2026-15487.json 2026-11-20T04:18:53Z 200
https://www.federalregister.gov/api/v1/documents/2026-15643.json 2026-11-20T04:18:53Z 200
https://www.federalregister.gov/api/v1/documents/2026-15751.json 2026-11-20T04:18:53Z 200
https://www.federalregister.gov/api/v1/documents/2026-15753.json 2026-11-20T04:18:53Z 200
https://www.federalregister.gov/api/v1/documents/2026-15796.json 2026-11-20T04:18:53Z 200
https://www.federalregister.gov/api/v1/documents/2026-16042.json 2026-11-20T04:18:53Z 200
https://www.federalregister.gov/api/v1/documents/2026-16228.json 2026-11-20T04:18:53Z 200
https://www.federalregister.gov/api/v1/documents/2026-16242.json 2026-11-20T04:18:53Z 200
https://www.federalregister.gov/api/v1/documents/2026-16499.json 2026-11-20T04:18:54Z 200
https://www.federalregister.gov/api/v1/documents/2026-16535.json 2026-11-20T04:18:54Z 200
https://www.federalregister.gov/api/v1/documents/2026-16613.json 2026-11-20T04:18:54Z 200
https://www.federalregister.gov/api/v1/documents/2026-16963.json 2026-11-20T04:18:54Z 200
https://www.federalregister.gov/api/v1/documents/2026-16967.json 2026-11-20T04:18:54Z 200
https://www.federalregister.gov/api/v1/documents/2026-17051.json 2026-11-20T04:18:54Z 200
https://www.federalregister.gov/api/v1/documents/2026-17083.json 2026-11-20T04:18:54Z 200
https://www.federalregister.gov/api/v1/documents/2026-17085.json 2026-11-20T04:18:55Z 200
https://www.federalregister.gov/api/v1/documents/2026-17210.json 2026-11-20T04:18:55Z 200
https://www.federalregister.gov/api/v1/documents/2026-17291.json 2026-11-20T04:18:55Z 200
https://www.federalregister.gov/api/v1/documents/2026-17307.json 2026-11-20T04:18:55Z 200
https://www.federalregister.gov/api/v1/documents/2026-17325.json 2026-11-20T04:18:55Z 200
https://www.federalregister.gov/api/v1/documents/2026-17557.json 2026-11-20T04:18:55Z 200
https://www.federalregister.gov/api/v1/documents/2026-17558.json 2026-11-20T04:18:55Z 200
https://www.federalregister.gov/api/v1/documents/2026-17585.json 2026-11-20T04:18:55Z 200
https://www.federalregister.gov/api/v1/documents/2026-17586.json 2026-11-20T04:18:56Z 200
https://www.federalregister.gov/api/v1/documents/2026-17587.json 2026-11-20T04:18:56Z 200
https://www.federalregister.gov/api/v1/documents/2026-17777.json 2026-11-20T04:18:56Z 200
https://www.federalregister.gov/api/v1/documents/2026-17881.json 2026-11-20T04:18:56Z 200
https://www.federalregister.gov/api/v1/documents/2026-17889.json 2026-11-20T04:18:56Z 200
https://www.federalregister.gov/api/v1/documents/2026-17891.json 2026-11-20T04:18:56Z 200
https://www.federalregister.gov/api/v1/documents/2026-18163.json 2026-11-20T04:18:56Z 200
https://www.federalregister.gov/api/v1/documents/2026-18541.json 2026-11-20T04:18:56Z 200
https://www.federalregister.gov/api/v1/documents/2026-18555.json 2026-11-20T04:18:56Z 200
https://www.federalregister.gov/api/v1/documents/2026-18824.json 2026-11-20T04:18:57Z 200
https://www.federalregister.gov/api/v1/documents/2026-18827.json 2026-11-20T04:18:57Z 200
https://www.federalregister.gov/api/v1/documents/2026-19168.json 2026-11-20T04:18:57Z 200
https://www.federalregister.gov/api/v1/documents/2026-19169.json 2026-11-20T04:18:57Z 200
https://www.federalregister.gov/api/v1/documents/2026-19317.json 2026-11-20T04:18:57Z 200
https://www.federalregister.gov/api/v1/documents/2026-19387.json 2026-11-20T04:18:57Z 200
https://www.federalregister.gov/api/v1/documents/2026-19455.json 2026-11-20T04:18:57Z 200
https://www.federalregister.gov/api/v1/documents/2026-19458.json 2026-11-20T04:18:57Z 200
https://www.federalregister.gov/api/v1/documents/2026-19460.json 2026-11-20T04:18:57Z 200
https://www.federalregister.gov/api/v1/documents/2026-19489.json 2026-11-20T04:18:57Z 200
https://www.federalregister.gov/api/v1/documents/2026-19528.json 2026-11-20T04:18:58Z 200
https://www.federalregister.gov/api/v1/documents/2026-19600.json 2026-11-20T04:18:58Z 200
https://www.federalregister.gov/api/v1/documents/2026-19650.json 2026-11-20T04:18:58Z 200
https://www.federalregister.gov/api/v1/documents/2026-19651.json 2026-11-20T04:18:58Z 200
https://www.federalregister.gov/api/v1/documents/2026-19683.json 2026-11-20T04:18:58Z 200
https://www.federalregister.gov/api/v1/documents/2026-19743.json 2026-11-20T04:18:58Z 200
https://www.federalregister.gov/api/v1/documents/2026-19782.json 2026-11-20T04:18:58Z 200
https://www.federalregister.gov/api/v1/documents/2026-19784.json 2026-11-20T04:18:59Z 200
https://www.federalregister.gov/api/v1/documents/2026-19881.json 2026-11-20T04:18:59Z 200
https://www.federalregister.gov/api/v1/documents/2026-19955.json 2026-11-20T04:18:59Z 200
https://www.federalregister.gov/api/v1/documents/2026-20042.json 2026-11-20T04:18:59Z 200
https://www.federalregister.gov/api/v1/documents/2026-20086.json 2026-11-20T04:18:59Z 200
https://www.federalregister.gov/api/v1/documents/2026-20183.json 2026-11-20T04:18:59Z 200
https://www.federalregister.gov/api/v1/documents/2026-20374.json 2026-11-20T04:18:59Z 200
https://www.federalregister.gov/api/v1/documents/2026-20390.json 2026-11-20T04:18:59Z 200
https://www.federalregister.gov/api/v1/documents/2026-20679.json 2026-11-20T04:19:00Z 200
https://www.federalregister.gov/api/v1/documents/2026-20682.json 2026-11-20T04:19:00Z 200
https://www.federalregister.gov/api/v1/documents/2026-20822.json 2026-11-20T04:19:00Z 200
https://www.federalregister.gov/api/v1/documents/2026-20823.json 2026-11-20T04:19:00Z 200
https://www.federalregister.gov/api/v1/documents/2026-20826.json 2026-11-20T04:19:00Z 200
https://www.federalregister.gov/api/v1/documents/2026-20827.json 2026-11-20T04:19:00Z 200
https://www.federalregister.gov/api/v1/documents/2026-20953.json 2026-11-20T04:19:00Z 200
https://www.federalregister.gov/api/v1/documents/2026-21011.json 2026-11-20T04:19:01Z 200
https://www.federalregister.gov/api/v1/documents/2026-21076.json 2026-11-20T04:19:01Z 200
https://www.federalregister.gov/api/v1/documents/2026-21426.json 2026-11-20T04:19:01Z 200
https://www.federalregister.gov/api/v1/documents/2026-21451.json 2026-11-20T04:19:01Z 200
https://www.federalregister.gov/api/v1/documents/2026-21511.json 2026-11-20T04:19:01Z 200
https://www.federalregister.gov/api/v1/documents/2026-21660.json 2026-11-20T04:19:01Z 200
https://www.federalregister.gov/api/v1/documents/2026-21886.json 2026-11-20T04:19:01Z 200
https://www.federalregister.gov/api/v1/documents/2026-22039.json 2026-11-20T04:19:02Z 200
https://www.federalregister.gov/api/v1/documents/2026-22128.json 2026-11-20T04:19:02Z 200
https://www.federalregister.gov/api/v1/documents/2026-22129.json 2026-11-20T04:19:02Z 200
https://www.federalregister.gov/api/v1/documents/2026-22135.json 2026-11-20T04:19:02Z 200
https://www.federalregister.gov/api/v1/documents/2026-22136.json 2026-11-20T04:19:02Z 200
https://www.federalregister.gov/api/v1/documents/2026-22188.json 2026-11-20T04:19:02Z 200
https://www.federalregister.gov/api/v1/documents/2026-22207.json 2026-11-20T04:19:03Z 200
https://www.federalregister.gov/api/v1/documents/2026-22219.json 2026-11-20T04:19:03Z 200
https://www.federalregister.gov/api/v1/documents/2026-22227.json 2026-11-20T04:19:03Z 200
https://www.federalregister.gov/api/v1/documents/2026-22228.json 2026-11-20T04:19:03Z 200
https://www.federalregister.gov/api/v1/documents/2026-22357.json 2026-11-20T04:19:03Z 200
https://www.federalregister.gov/api/v1/documents/2026-22417.json 2026-11-20T04:19:03Z 200
https://www.federalregister.gov/api/v1/documents/2026-22554.json 2026-11-20T04:19:03Z 200
https://www.federalregister.gov/api/v1/documents/2026-22570.json 2026-11-20T04:19:03Z 200
https://www.federalregister.gov/api/v1/documents/2026-22571.json 2026-11-20T04:19:04Z 200
https://www.federalregister.gov/api/v1/documents/2026-22638.json 2026-11-20T04:19:04Z 200
https://www.federalregister.gov/api/v1/documents/2026-22639.json 2026-11-20T04:19:04Z 200
https://www.federalregister.gov/api/v1/documents/2026-22645.json 2026-11-20T04:19:04Z 200
https://www.federalregister.gov/api/v1/documents/2026-22770.json 2026-11-20T04:19:04Z 200
https://www.federalregister.gov/api/v1/documents/2026-22838.json 2026-11-20T04:19:04Z 200
https://www.federalregister.gov/api/v1/documents/2026-22896.json 2026-11-20T04:19:04Z 200
https://www.federalregister.gov/api/v1/documents/2026-22901.json 2026-11-20T04:19:04Z 200
https://www.federalregister.gov/api/v1/documents/2026-23003.json 2026-11-20T04:19:05Z 200
https://www.federalregister.gov/api/v1/documents/2026-23069.json 2026-11-20T04:19:05Z 200
https://www.federalregister.gov/api/v1/documents/2026-23070.json 2026-11-20T04:19:05Z 200
https://www.federalregister.gov/api/v1/documents/2026-23071.json 2026-11-20T04:19:05Z 200
https://www.federalregister.gov/api/v1/documents/2026-23151.json 2026-11-20T04:19:05Z 200
https://www.federalregister.gov/api/v1/documents/2026-23152.json 2026-11-20T04:19:05Z 200
https://www.federalregister.gov/api/v1/documents/2026-23243.json 2026-11-20T04:19:05Z 200
https://www.federalregister.gov/api/v1/documents/2026-23565.json 2026-11-20T04:19:06Z 200
```

### PULL 3 request log

Source time (first response Date header): `Date: Sat, 21 Nov 2026 04:21:01 GMT`

131 requests, one per line: full request URL, UTC time, HTTP status [verbatim fields of that response]

```
https://www.federalregister.gov/api/v1/documents.json?conditions%5Bagencies%5D%5B%5D=consumer-financial-protection-bureau&conditions%5Bpublication_date%5D%5Bgte%5D=2026-07-01&per_page=100&page=1&fields%5B%5D=document_number&fields%5B%5D=type&fields%5B%5D=publication_date&fields%5B%5D=title&fields%5B%5D=agencies 2026-11-21T04:21:01Z 200
https://www.federalregister.gov/api/v1/documents.json?conditions%5Bagencies%5D%5B%5D=housing-and-urban-development-department&conditions%5Bpublication_date%5D%5Bgte%5D=2026-07-01&per_page=100&page=1&fields%5B%5D=document_number&fields%5B%5D=type&fields%5B%5D=publication_date&fields%5B%5D=title&fields%5B%5D=agencies 2026-11-21T04:21:01Z 200
https://www.federalregister.gov/api/v1/documents.json?conditions%5Bagencies%5D%5B%5D=housing-and-urban-development-department&conditions%5Bpublication_date%5D%5Bgte%5D=2026-07-01&per_page=100&page=2&fields%5B%5D=document_number&fields%5B%5D=type&fields%5B%5D=publication_date&fields%5B%5D=title&fields%5B%5D=agencies 2026-11-21T04:21:01Z 200
https://www.federalregister.gov/api/v1/documents.json?conditions%5Bagencies%5D%5B%5D=federal-housing-finance-agency&conditions%5Bpublication_date%5D%5Bgte%5D=2026-07-01&per_page=100&page=1&fields%5B%5D=document_number&fields%5B%5D=type&fields%5B%5D=publication_date&fields%5B%5D=title&fields%5B%5D=agencies 2026-11-21T04:21:02Z 200
https://www.federalregister.gov/api/v1/documents/2026-13378.json 2026-11-21T04:21:02Z 200
https://www.federalregister.gov/api/v1/documents/2026-13537.json 2026-11-21T04:21:02Z 200
https://www.federalregister.gov/api/v1/documents/2026-13539.json 2026-11-21T04:21:02Z 200
https://www.federalregister.gov/api/v1/documents/2026-13542.json 2026-11-21T04:21:02Z 200
https://www.federalregister.gov/api/v1/documents/2026-13543.json 2026-11-21T04:21:02Z 200
https://www.federalregister.gov/api/v1/documents/2026-13660.json 2026-11-21T04:21:02Z 200
https://www.federalregister.gov/api/v1/documents/2026-13672.json 2026-11-21T04:21:02Z 200
https://www.federalregister.gov/api/v1/documents/2026-13735.json 2026-11-21T04:21:03Z 200
https://www.federalregister.gov/api/v1/documents/2026-13760.json 2026-11-21T04:21:03Z 200
https://www.federalregister.gov/api/v1/documents/2026-13814.json 2026-11-21T04:21:03Z 200
https://www.federalregister.gov/api/v1/documents/2026-13834.json 2026-11-21T04:21:03Z 200
https://www.federalregister.gov/api/v1/documents/2026-13933.json 2026-11-21T04:21:03Z 200
https://www.federalregister.gov/api/v1/documents/2026-13934.json 2026-11-21T04:21:03Z 200
https://www.federalregister.gov/api/v1/documents/2026-13939.json 2026-11-21T04:21:03Z 200
https://www.federalregister.gov/api/v1/documents/2026-13945.json 2026-11-21T04:21:03Z 200
https://www.federalregister.gov/api/v1/documents/2026-13969.json 2026-11-21T04:21:04Z 200
https://www.federalregister.gov/api/v1/documents/2026-14035.json 2026-11-21T04:21:04Z 200
https://www.federalregister.gov/api/v1/documents/2026-14036.json 2026-11-21T04:21:04Z 200
https://www.federalregister.gov/api/v1/documents/2026-14037.json 2026-11-21T04:21:04Z 200
https://www.federalregister.gov/api/v1/documents/2026-14432.json 2026-11-21T04:21:04Z 200
https://www.federalregister.gov/api/v1/documents/2026-14873.json 2026-11-21T04:21:04Z 200
https://www.federalregister.gov/api/v1/documents/2026-15154.json 2026-11-21T04:21:04Z 200
https://www.federalregister.gov/api/v1/documents/2026-15428.json 2026-11-21T04:21:05Z 200
https://www.federalregister.gov/api/v1/documents/2026-15487.json 2026-11-21T04:21:05Z 200
https://www.federalregister.gov/api/v1/documents/2026-15643.json 2026-11-21T04:21:05Z 200
https://www.federalregister.gov/api/v1/documents/2026-15751.json 2026-11-21T04:21:05Z 200
https://www.federalregister.gov/api/v1/documents/2026-15753.json 2026-11-21T04:21:05Z 200
https://www.federalregister.gov/api/v1/documents/2026-15796.json 2026-11-21T04:21:05Z 200
https://www.federalregister.gov/api/v1/documents/2026-16042.json 2026-11-21T04:21:05Z 200
https://www.federalregister.gov/api/v1/documents/2026-16228.json 2026-11-21T04:21:06Z 200
https://www.federalregister.gov/api/v1/documents/2026-16242.json 2026-11-21T04:21:06Z 200
https://www.federalregister.gov/api/v1/documents/2026-16499.json 2026-11-21T04:21:06Z 200
https://www.federalregister.gov/api/v1/documents/2026-16535.json 2026-11-21T04:21:06Z 200
https://www.federalregister.gov/api/v1/documents/2026-16613.json 2026-11-21T04:21:06Z 200
https://www.federalregister.gov/api/v1/documents/2026-16963.json 2026-11-21T04:21:06Z 200
https://www.federalregister.gov/api/v1/documents/2026-16967.json 2026-11-21T04:21:06Z 200
https://www.federalregister.gov/api/v1/documents/2026-17051.json 2026-11-21T04:21:07Z 200
https://www.federalregister.gov/api/v1/documents/2026-17083.json 2026-11-21T04:21:07Z 200
https://www.federalregister.gov/api/v1/documents/2026-17085.json 2026-11-21T04:21:07Z 200
https://www.federalregister.gov/api/v1/documents/2026-17210.json 2026-11-21T04:21:07Z 200
https://www.federalregister.gov/api/v1/documents/2026-17291.json 2026-11-21T04:21:07Z 200
https://www.federalregister.gov/api/v1/documents/2026-17307.json 2026-11-21T04:21:07Z 200
https://www.federalregister.gov/api/v1/documents/2026-17325.json 2026-11-21T04:21:08Z 200
https://www.federalregister.gov/api/v1/documents/2026-17557.json 2026-11-21T04:21:08Z 200
https://www.federalregister.gov/api/v1/documents/2026-17558.json 2026-11-21T04:21:08Z 200
https://www.federalregister.gov/api/v1/documents/2026-17585.json 2026-11-21T04:21:08Z 200
https://www.federalregister.gov/api/v1/documents/2026-17586.json 2026-11-21T04:21:08Z 200
https://www.federalregister.gov/api/v1/documents/2026-17587.json 2026-11-21T04:21:08Z 200
https://www.federalregister.gov/api/v1/documents/2026-17777.json 2026-11-21T04:21:08Z 200
https://www.federalregister.gov/api/v1/documents/2026-17881.json 2026-11-21T04:21:08Z 200
https://www.federalregister.gov/api/v1/documents/2026-17889.json 2026-11-21T04:21:09Z 200
https://www.federalregister.gov/api/v1/documents/2026-17891.json 2026-11-21T04:21:09Z 200
https://www.federalregister.gov/api/v1/documents/2026-18163.json 2026-11-21T04:21:09Z 200
https://www.federalregister.gov/api/v1/documents/2026-18541.json 2026-11-21T04:21:09Z 200
https://www.federalregister.gov/api/v1/documents/2026-18555.json 2026-11-21T04:21:09Z 200
https://www.federalregister.gov/api/v1/documents/2026-18824.json 2026-11-21T04:21:09Z 200
https://www.federalregister.gov/api/v1/documents/2026-18827.json 2026-11-21T04:21:09Z 200
https://www.federalregister.gov/api/v1/documents/2026-19168.json 2026-11-21T04:21:09Z 200
https://www.federalregister.gov/api/v1/documents/2026-19169.json 2026-11-21T04:21:09Z 200
https://www.federalregister.gov/api/v1/documents/2026-19317.json 2026-11-21T04:21:10Z 200 ["comments_close_on":"2026-11-23" "effective_on":null]
https://www.federalregister.gov/api/v1/documents/2026-19387.json 2026-11-21T04:21:10Z 200 ["comments_close_on":"2026-11-23" "effective_on":null]
https://www.federalregister.gov/api/v1/documents/2026-19455.json 2026-11-21T04:21:10Z 200
https://www.federalregister.gov/api/v1/documents/2026-19458.json 2026-11-21T04:21:10Z 200
https://www.federalregister.gov/api/v1/documents/2026-19460.json 2026-11-21T04:21:10Z 200
https://www.federalregister.gov/api/v1/documents/2026-19489.json 2026-11-21T04:21:10Z 200
https://www.federalregister.gov/api/v1/documents/2026-19528.json 2026-11-21T04:21:10Z 200
https://www.federalregister.gov/api/v1/documents/2026-19600.json 2026-11-21T04:21:11Z 200
https://www.federalregister.gov/api/v1/documents/2026-19650.json 2026-11-21T04:21:11Z 200 ["comments_close_on":"2026-11-24" "effective_on":null]
https://www.federalregister.gov/api/v1/documents/2026-19651.json 2026-11-21T04:21:11Z 200 ["comments_close_on":"2026-11-24" "effective_on":null]
https://www.federalregister.gov/api/v1/documents/2026-19683.json 2026-11-21T04:21:11Z 200
https://www.federalregister.gov/api/v1/documents/2026-19743.json 2026-11-21T04:21:11Z 200
https://www.federalregister.gov/api/v1/documents/2026-19782.json 2026-11-21T04:21:11Z 200
https://www.federalregister.gov/api/v1/documents/2026-19784.json 2026-11-21T04:21:11Z 200
https://www.federalregister.gov/api/v1/documents/2026-19881.json 2026-11-21T04:21:11Z 200 ["comments_close_on":"2026-11-30" "effective_on":null]
https://www.federalregister.gov/api/v1/documents/2026-19955.json 2026-11-21T04:21:12Z 200
https://www.federalregister.gov/api/v1/documents/2026-20042.json 2026-11-21T04:21:12Z 200
https://www.federalregister.gov/api/v1/documents/2026-20086.json 2026-11-21T04:21:12Z 200
https://www.federalregister.gov/api/v1/documents/2026-20183.json 2026-11-21T04:21:12Z 200 ["comments_close_on":"2026-12-01" "effective_on":null]
https://www.federalregister.gov/api/v1/documents/2026-20374.json 2026-11-21T04:21:12Z 200 ["comments_close_on":"2026-12-04" "effective_on":"2026-11-04"]
https://www.federalregister.gov/api/v1/documents/2026-20390.json 2026-11-21T04:21:12Z 200
https://www.federalregister.gov/api/v1/documents/2026-20679.json 2026-11-21T04:21:12Z 200 ["comments_close_on":"2026-12-07" "effective_on":null]
https://www.federalregister.gov/api/v1/documents/2026-20682.json 2026-11-21T04:21:13Z 200 ["comments_close_on":"2026-12-07" "effective_on":null]
https://www.federalregister.gov/api/v1/documents/2026-20822.json 2026-11-21T04:21:13Z 200
https://www.federalregister.gov/api/v1/documents/2026-20823.json 2026-11-21T04:21:13Z 200 ["comments_close_on":"2026-12-14" "effective_on":null]
https://www.federalregister.gov/api/v1/documents/2026-20826.json 2026-11-21T04:21:13Z 200
https://www.federalregister.gov/api/v1/documents/2026-20827.json 2026-11-21T04:21:13Z 200
https://www.federalregister.gov/api/v1/documents/2026-20953.json 2026-11-21T04:21:13Z 200
https://www.federalregister.gov/api/v1/documents/2026-21011.json 2026-11-21T04:21:13Z 200
https://www.federalregister.gov/api/v1/documents/2026-21076.json 2026-11-21T04:21:13Z 200 ["comments_close_on":"2026-12-14" "effective_on":null]
https://www.federalregister.gov/api/v1/documents/2026-21426.json 2026-11-21T04:21:14Z 200 ["comments_close_on":"2026-12-21" "effective_on":null]
https://www.federalregister.gov/api/v1/documents/2026-21451.json 2026-11-21T04:21:14Z 200 ["comments_close_on":"2026-12-21" "effective_on":null]
https://www.federalregister.gov/api/v1/documents/2026-21511.json 2026-11-21T04:21:14Z 200
https://www.federalregister.gov/api/v1/documents/2026-21660.json 2026-11-21T04:21:14Z 200 ["comments_close_on":"2026-12-22" "effective_on":null]
https://www.federalregister.gov/api/v1/documents/2026-21886.json 2026-11-21T04:21:14Z 200
https://www.federalregister.gov/api/v1/documents/2026-22039.json 2026-11-21T04:21:14Z 200 ["comments_close_on":"2026-11-30" "effective_on":null]
https://www.federalregister.gov/api/v1/documents/2026-22128.json 2026-11-21T04:21:14Z 200 ["comments_close_on":"2026-11-30" "effective_on":null]
https://www.federalregister.gov/api/v1/documents/2026-22129.json 2026-11-21T04:21:15Z 200 ["comments_close_on":"2026-11-30" "effective_on":null]
https://www.federalregister.gov/api/v1/documents/2026-22135.json 2026-11-21T04:21:15Z 200 ["comments_close_on":"2026-11-30" "effective_on":null]
https://www.federalregister.gov/api/v1/documents/2026-22136.json 2026-11-21T04:21:15Z 200 ["comments_close_on":"2026-11-30" "effective_on":null]
https://www.federalregister.gov/api/v1/documents/2026-22188.json 2026-11-21T04:21:15Z 200 ["comments_close_on":"2026-12-29" "effective_on":null]
https://www.federalregister.gov/api/v1/documents/2026-22207.json 2026-11-21T04:21:15Z 200 ["comments_close_on":"2026-12-14" "effective_on":null]
https://www.federalregister.gov/api/v1/documents/2026-22219.json 2026-11-21T04:21:15Z 200 ["comments_close_on":"2026-11-30" "effective_on":null]
https://www.federalregister.gov/api/v1/documents/2026-22227.json 2026-11-21T04:21:15Z 200 ["comments_close_on":"2026-12-29" "effective_on":null]
https://www.federalregister.gov/api/v1/documents/2026-22228.json 2026-11-21T04:21:15Z 200 ["comments_close_on":"2026-12-29" "effective_on":null]
https://www.federalregister.gov/api/v1/documents/2026-22357.json 2026-11-21T04:21:16Z 200
https://www.federalregister.gov/api/v1/documents/2026-22417.json 2026-11-21T04:21:16Z 200
https://www.federalregister.gov/api/v1/documents/2026-22554.json 2026-11-21T04:21:16Z 200 ["comments_close_on":"2026-12-04" "effective_on":null]
https://www.federalregister.gov/api/v1/documents/2026-22570.json 2026-11-21T04:21:16Z 200 ["comments_close_on":"2027-01-04" "effective_on":null]
https://www.federalregister.gov/api/v1/documents/2026-22571.json 2026-11-21T04:21:16Z 200 ["comments_close_on":"2027-01-04" "effective_on":null]
https://www.federalregister.gov/api/v1/documents/2026-22638.json 2026-11-21T04:21:16Z 200 ["comments_close_on":"2027-01-04" "effective_on":null]
https://www.federalregister.gov/api/v1/documents/2026-22639.json 2026-11-21T04:21:16Z 200 ["comments_close_on":"2027-01-04" "effective_on":null]
https://www.federalregister.gov/api/v1/documents/2026-22645.json 2026-11-21T04:21:17Z 200
https://www.federalregister.gov/api/v1/documents/2026-22770.json 2026-11-21T04:21:17Z 200 ["comments_close_on":"2027-01-08" "effective_on":null]
https://www.federalregister.gov/api/v1/documents/2026-22838.json 2026-11-21T04:21:17Z 200
https://www.federalregister.gov/api/v1/documents/2026-22896.json 2026-11-21T04:21:17Z 200 ["comments_close_on":"2027-01-11" "effective_on":null]
https://www.federalregister.gov/api/v1/documents/2026-22901.json 2026-11-21T04:21:17Z 200 ["comments_close_on":"2027-01-11" "effective_on":null]
https://www.federalregister.gov/api/v1/documents/2026-23003.json 2026-11-21T04:21:17Z 200 ["comments_close_on":null "effective_on":"2026-12-14"]
https://www.federalregister.gov/api/v1/documents/2026-23069.json 2026-11-21T04:21:17Z 200 ["comments_close_on":"2027-01-12" "effective_on":null]
https://www.federalregister.gov/api/v1/documents/2026-23070.json 2026-11-21T04:21:17Z 200 ["comments_close_on":"2027-01-12" "effective_on":null]
https://www.federalregister.gov/api/v1/documents/2026-23071.json 2026-11-21T04:21:17Z 200 ["comments_close_on":"2027-01-11" "effective_on":null]
https://www.federalregister.gov/api/v1/documents/2026-23151.json 2026-11-21T04:21:18Z 200 ["comments_close_on":"2027-01-12" "effective_on":null]
https://www.federalregister.gov/api/v1/documents/2026-23152.json 2026-11-21T04:21:18Z 200 ["comments_close_on":"2027-01-12" "effective_on":null]
https://www.federalregister.gov/api/v1/documents/2026-23243.json 2026-11-21T04:21:18Z 200 ["comments_close_on":"2026-12-16" "effective_on":null]
https://www.federalregister.gov/api/v1/documents/2026-23565.json 2026-11-21T04:21:18Z 200 ["comments_close_on":"2027-01-19" "effective_on":null]
https://www.federalregister.gov/api/v1/documents/2026-23696.json 2026-11-21T04:21:18Z 200
https://www.federalregister.gov/api/v1/documents/2026-23701.json 2026-11-21T04:21:18Z 200 ["comments_close_on":"2026-12-21" "effective_on":null]
https://www.federalregister.gov/api/v1/documents/2026-23702.json 2026-11-21T04:21:18Z 200 ["comments_close_on":"2026-12-21" "effective_on":null]
```

### Request 1 (PULL 1, consumer-financial-protection-bureau, raw count)
- Request: www.federalregister.gov/api/v1/documents.json conditions[agencies][]=consumer-financial-protection-bureau, page 1 (full URL: first consumer-financial-protection-bureau line of the PULL 1 log)
- Retrieved (UTC): 2026-11-19T03:59:23Z, HTTP 200, header `Date: Thu, 19 Nov 2026 03:59:23 GMT`
- Excerpt (copied exactly as returned):

```
"count":11,"total_pages":1
```

### Request 2 (PULL 1, housing-and-urban-development-department, raw count)
- Request: www.federalregister.gov/api/v1/documents.json conditions[agencies][]=housing-and-urban-development-department, page 1 (full URL: first housing-and-urban-development-department line of the PULL 1 log)
- Retrieved (UTC): 2026-11-19T03:59:23Z, HTTP 200, header `Date: Thu, 19 Nov 2026 03:59:23 GMT`
- Excerpt (copied exactly as returned):

```
"count":103,"total_pages":2
```

### Request 3 (PULL 1, federal-housing-finance-agency, raw count)
- Request: www.federalregister.gov/api/v1/documents.json conditions[agencies][]=federal-housing-finance-agency, page 1 (full URL: first federal-housing-finance-agency line of the PULL 1 log)
- Retrieved (UTC): 2026-11-19T03:59:23Z, HTTP 200, header `Date: Thu, 19 Nov 2026 03:59:24 GMT`
- Excerpt (copied exactly as returned):

```
"count":11,"total_pages":1
```

### Request 4 (PULL 2, consumer-financial-protection-bureau, raw count)
- Request: www.federalregister.gov/api/v1/documents.json conditions[agencies][]=consumer-financial-protection-bureau, page 1 (full URL: first consumer-financial-protection-bureau line of the PULL 2 log)
- Retrieved (UTC): 2026-11-20T04:18:49Z, HTTP 200, header `Date: Fri, 20 Nov 2026 04:18:49 GMT`
- Excerpt (copied exactly as returned):

```
"count":11,"total_pages":1
```

### Request 5 (PULL 2, housing-and-urban-development-department, raw count)
- Request: www.federalregister.gov/api/v1/documents.json conditions[agencies][]=housing-and-urban-development-department, page 1 (full URL: first housing-and-urban-development-department line of the PULL 2 log)
- Retrieved (UTC): 2026-11-20T04:18:49Z, HTTP 200, header `Date: Fri, 20 Nov 2026 04:18:49 GMT`
- Excerpt (copied exactly as returned):

```
"count":104,"total_pages":2
```

### Request 6 (PULL 2, federal-housing-finance-agency, raw count)
- Request: www.federalregister.gov/api/v1/documents.json conditions[agencies][]=federal-housing-finance-agency, page 1 (full URL: first federal-housing-finance-agency line of the PULL 2 log)
- Retrieved (UTC): 2026-11-20T04:18:49Z, HTTP 200, header `Date: Fri, 20 Nov 2026 04:18:49 GMT`
- Excerpt (copied exactly as returned):

```
"count":11,"total_pages":1
```

### Request 7 (PULL 3, consumer-financial-protection-bureau, raw count, raw first result)
- Request: www.federalregister.gov/api/v1/documents.json conditions[agencies][]=consumer-financial-protection-bureau, page 1 (full URL: first consumer-financial-protection-bureau line of the PULL 3 log)
- Retrieved (UTC): 2026-11-21T04:21:01Z, HTTP 200, header `Date: Sat, 21 Nov 2026 04:21:01 GMT`
- Excerpt (copied exactly as returned):

```
"count":11,"total_pages":1
{"document_number":"2026-23152","type":"Notice","publication_date":"2026-11-13","title":"Agency Information Collection Activities: Comment Request","agencies":[{"raw_name":"Consumer Financial Protection Bureau","name":"Consumer Financial Protection Bureau","id":573,"url":"https://www.federalregister.gov/agencies/consumer-financial-protection-bureau","json_url":"https://www.federalregister.gov/api/v1/agencies/573","parent_id":null,"slug":"consumer-financial-protection-bureau"}]}
```

### Request 8 (PULL 3, housing-and-urban-development-department, raw count, raw first result)
- Request: www.federalregister.gov/api/v1/documents.json conditions[agencies][]=housing-and-urban-development-department, page 1 (full URL: first housing-and-urban-development-department line of the PULL 3 log)
- Retrieved (UTC): 2026-11-21T04:21:01Z, HTTP 200, header `Date: Sat, 21 Nov 2026 04:21:01 GMT`
- Excerpt (copied exactly as returned):

```
"count":105,"total_pages":2
{"document_number":"2026-23696","type":"Notice","publication_date":"2026-11-20","title":"Waivers and Alternative Requirements for Community Development Block Grant Disaster Recovery (CDBG-DR) and Community Development Block Grant Mitigation (CDBG-MIT) Grantees","agencies":[{"raw_name":"DEPARTMENT OF HOUSING AND URBAN DEVELOPMENT","name":"Housing and Urban Development Department","id":228,"url":"https://www.federalregister.gov/agencies/housing-and-urban-development-department","json_url":"https://www.federalregister.gov/api/v1/agencies/228","parent_id":null,"slug":"housing-and-urban-development-department"}]}
```

### Request 9 (PULL 3, federal-housing-finance-agency, raw count, raw first result)
- Request: www.federalregister.gov/api/v1/documents.json conditions[agencies][]=federal-housing-finance-agency, page 1 (full URL: first federal-housing-finance-agency line of the PULL 3 log)
- Retrieved (UTC): 2026-11-21T04:21:02Z, HTTP 200, header `Date: Sat, 21 Nov 2026 04:21:02 GMT`
- Excerpt (copied exactly as returned):

```
"count":13,"total_pages":1
{"document_number":"2026-23702","type":"Notice","publication_date":"2026-11-20","title":"Proposed Collection; Comment Request","agencies":[{"raw_name":"FEDERAL HOUSING FINANCE AGENCY","name":"Federal Housing Finance Agency","id":174,"url":"https://www.federalregister.gov/agencies/federal-housing-finance-agency","json_url":"https://www.federalregister.gov/api/v1/agencies/174","parent_id":null,"slug":"federal-housing-finance-agency"}]}
```

