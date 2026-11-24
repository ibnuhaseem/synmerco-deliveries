# Texas banks of 1 to 20 billion dollars: commercial real estate concentration screen, 20230630 to 20260630, three pulls

## Executive summary

This report screens the 84 active Texas banks with assets of 1 to 20 billion dollars that FDIC BankFind (api.fdic.gov, /banks/institutions and /banks/financials) returned at pull 1, fixed by CERT, for real estate concentration at REPDTE 20260630 against REPDTE 20230630, over three timed pulls (source times `Date: Sat, 21 Nov 2026 21:34:43 GMT`, `Date: Sun, 22 Nov 2026 23:14:20 GMT`, `Date: Mon, 23 Nov 2026 23:17:14 GMT`). Each CSV holds 168 rows (two per bank, none missing). On 20260630, 21 banks are above the construction threshold (LNRECONS at or above RBCT1J), 18 above the CRE threshold (CRE ratio of 300% or more) and 2 above the growth threshold (CRE flag and CRE loan sum up 50% or more since 20230630); 11 banks carry two or more flags. The median construction ratio is 75.39% and the median CRE ratio is 238.98%. The three pulls returned identical data: PULL 2 vs PULL 1 and PULL 3 vs PULL 2 both show no change (168 vs 168 rows, 168 vs 168 rows). Tier 1 capital (RBCT1J) stands in for the guidance's total capital, and flags are thresholds, not findings.

## Method

- Construction ratio = LNRECONS / RBCT1J x 100; CRE ratio = (LNRECONS + LNREMULT + LNRENROT) / RBCT1J x 100 (LNRENROW left out). An RBCT1J of 0 or empty gives empty ratio cells. All figures use Python Decimal from unrounded values, 2 decimals, half away from zero.
- Flags for 20260630: construction = LNRECONS >= RBCT1J; CRE = CRE loan sum >= 3 x RBCT1J; growth = CRE flag and (CRE sum 20260630 - CRE sum 20230630) >= 0.5 x CRE sum 20230630. CRE loan sum growth % = (sum 20260630 / sum 20230630 - 1) x 100; n/a when the 20230630 sum is 0.
- Loan and capital values are as FDIC returned them; RBCRWAJ is shown as returned.
- Medians use banks with available ratios (N/A excluded); an even count takes the mean of the two middle values.

## 1. Bank list (banks returned at pull 1, fixed by CERT)

84 banks (`meta.total` 84); CERT and NAME, sorted by CERT (ASSET is in the raw excerpt below):

1209 Commercial Bank of Texas, National Association; 1213 Cornerstone Capital Bank, SSB; 1497 Security State Bank; 3066 First Financial Bank; 3067 Clear Fork Bank, National Association; 3091 The First National Bank of Bastrop; 3108 Legend Bank, N.A.; 3210 The Moody National Bank; 3250 VeraBank, National Association; 3256 Horizon Bank, SSB; 3276 Austin Bank, Texas National Association; 3285 First National Bank Texas; 3325 First National Bank of Central Texas; 3330 The First National Bank of McGregor; 3337 Texas National Bank; 3387 FirstBank Southwest; 3389 Pointbank; 3405 Vantage Bank Texas; 4767 Sunflower Bank, National Association; 5146 Wells Fargo Bank South Central, National Association; 5544 The City National Bank of Sulphur Springs; 5551 Extraco Banks, National Association; 5574 Citizens National Bank of Texas; 9978 First State Bank of Uvalde; 11569 Alliance Bank; 11935 First Texas Bank; 12299 SouthStar Bank, S.S.B.; 12769 First United Bank; 14531 Amarillo National Bank; 15511 First State Bank; 15657 Alliance Bank Central Texas; 15797 Broadway National Bank; 15809 Security State Bank & Trust; 16470 Jefferson Bank; 16753 Citizens State Bank; 17491 PlainsCapital Bank; 17612 Central Bank; 17842 Texas Bank and Trust Company; 18185 Community National Bank & Trust of Texas; 18297 Southside Bank; 18344 UBank; 18355 North Dallas Bank & Trust Co.; 18609 American Bank of Commerce; 19080 Inwood National Bank; 19215 Benchmark Bank; 19559 TexasBank; 19629 International Bank of Commerce; 20099 Texas Exchange Bank; 20231 Pinnacle Bank; 20845 Wallis Bank; 22373 American National Bank & Trust; 22396 Central National Bank; 22957 West Texas National Bank; 23220 Woodforest National Bank; 23474 The American National Bank of Texas; 23498 TBK BANK, SSB; 23647 TIB National Association; 23799 Texas First Bank; 24347 Lone Star National Bank; 24563 Texas Community Bank; 24897 Community National Bank; 25103 City Bank; 25679 International Bank of Commerce; 25886 Rio Bank; 26223 Golden Bank, National Association; 26626 United Texas Bank, National Association; 26856 Falcon International Bank; 26906 Texas Regional Bank; 27074 State Bank of Texas; 29209 NexBank; 32574 Monet Bank; 32941 WestStar Bank; 34319 Southwestern National Bank; 34415 First Command Bank; 34656 American First National Bank; 34885 Susser Bank; 57703 T Bank, National Association; 58309 American Momentum Bank; 58483 Pegasus Bank; 58509 Frontier Bank of Texas; 58716 Third Coast Bank; 58739 Texas Security Bank; 58935 R Bank; 59108 Charles Schwab Trust Bank

Raw institutions excerpt, PULL 1 first request (the whole response, verbatim, as returned):

```
{"meta":{"total":84,"parameters":{"filters":"STALP:TX AND ACTIVE:1 AND ASSET:[1000000 TO 20000000]","fields":"NAME,CERT,ASSET","limit":"200"},"index":{"name":"institutions_20261120100008","createTimestamp":"2026-11-20T12:56:44Z"}},"data":[{"data":{"ASSET":1389330,"CERT":11569,"NAME":"Alliance Bank","ID":"11569"},"score":0},{"data":{"ASSET":1309968,"CERT":11935,"NAME":"First Texas Bank","ID":"11935"},"score":0},{"data":{"ASSET":1685806,"CERT":1209,"NAME":"Commercial Bank of Texas, National Association","ID":"1209"},"score":0},{"data":{"ASSET":3666532,"CERT":1213,"NAME":"Cornerstone Capital Bank, SSB","ID":"1213"},"score":0},{"data":{"ASSET":1369693,"CERT":12299,"NAME":"SouthStar Bank, S.S.B.","ID":"12299"},"score":0},{"data":{"ASSET":2409073,"CERT":12769,"NAME":"First United Bank","ID":"12769"},"score":0},{"data":{"ASSET":10380511,"CERT":14531,"NAME":"Amarillo National Bank","ID":"14531"},"score":0},{"data":{"ASSET":1138646,"CERT":1497,"NAME":"Security State Bank","ID":"1497"},"score":0},{"data":{"ASSET":1851537,"CERT":15511,"NAME":"First State Bank","ID":"15511"},"score":0},{"data":{"ASSET":1323064,"CERT":15657,"NAME":"Alliance Bank Central Texas","ID":"15657"},"score":0},{"data":{"ASSET":5422636,"CERT":15797,"NAME":"Broadway National Bank","ID":"15797"},"score":0},{"data":{"ASSET":2176648,"CERT":15809,"NAME":"Security State Bank & Trust","ID":"15809"},"score":0},{"data":{"ASSET":2875424,"CERT":16470,"NAME":"Jefferson Bank","ID":"16470"},"score":0},{"data":{"ASSET":1219362,"CERT":16753,"NAME":"Citizens State Bank","ID":"16753"},"score":0},{"data":{"ASSET":12684839,"CERT":17491,"NAME":"PlainsCapital Bank","ID":"17491"},"score":0},{"data":{"ASSET":1416138,"CERT":17612,"NAME":"Central Bank","ID":"17612"},"score":0},{"data":{"ASSET":4339112,"CERT":17842,"NAME":"Texas Bank and Trust Company","ID":"17842"},"score":0},{"data":{"ASSET":1681828,"CERT":18185,"NAME":"Community National Bank & Trust of Texas","ID":"18185"},"score":0},{"data":{"ASSET":8758892,"CERT":18297,"NAME":"Southside Bank","ID":"18297"},"score":0},{"data":{"ASSET":1046394,"CERT":18344,"NAME":"UBank","ID":"18344"},"score":0},{"data":{"ASSET":1809980,"CERT":18355,"NAME":"North Dallas Bank & Trust Co.","ID":"18355"},"score":0},{"data":{"ASSET":1862140,"CERT":18609,"NAME":"American Bank of Commerce","ID":"18609"},"score":0},{"data":{"ASSET":4260043,"CERT":19080,"NAME":"Inwood National Bank","ID":"19080"},"score":0},{"data":{"ASSET":1649360,"CERT":19215,"NAME":"Benchmark Bank","ID":"19215"},"score":0},{"data":{"ASSET":2479690,"CERT":19559,"NAME":"TexasBank","ID":"19559"},"score":0},{"data":{"ASSET":10194733,"CERT":19629,"NAME":"International Bank of Commerce","ID":"19629"},"score":0},{"data":{"ASSET":4490496,"CERT":20099,"NAME":"Texas Exchange Bank","ID":"20099"},"score":0},{"data":{"ASSET":2721044,"CERT":20231,"NAME":"Pinnacle Bank","ID":"20231"},"score":0},{"data":{"ASSET":1384007,"CERT":20845,"NAME":"Wallis Bank","ID":"20845"},"score":0},{"data":{"ASSET":2536428,"CERT":22373,"NAME":"American National Bank & Trust","ID":"22373"},"score":0},{"data":{"ASSET":1474092,"CERT":22396,"NAME":"Central National Bank","ID":"22396"},"score":0},{"data":{"ASSET":2881219,"CERT":22957,"NAME":"West Texas National Bank","ID":"22957"},"score":0},{"data":{"ASSET":8984913,"CERT":23220,"NAME":"Woodforest National Bank","ID":"23220"},"score":0},{"data":{"ASSET":5505445,"CERT":23474,"NAME":"The American National Bank of Texas","ID":"23474"},"score":0},{"data":{"ASSET":7399039,"CERT":23498,"NAME":"TBK BANK, SSB","ID":"23498"},"score":0},{"data":{"ASSET":2960509,"CERT":23647,"NAME":"TIB National Association","ID":"23647"},"score":0},{"data":{"ASSET":2345157,"CERT":23799,"NAME":"Texas First Bank","ID":"23799"},"score":0},{"data":{"ASSET":3283357,"CERT":24347,"NAME":"Lone Star National Bank","ID":"24347"},"score":0},{"data":{"ASSET":2204656,"CERT":24563,"NAME":"Texas Community Bank","ID":"24563"},"score":0},{"data":{"ASSET":2541691,"CERT":24897,"NAME":"Community National Bank","ID":"24897"},"score":0},{"data":{"ASSET":5388227,"CERT":25103,"NAME":"City Bank","ID":"25103"},"score":0},{"data":{"ASSET":4561812,"CERT":25679,"NAME":"International Bank of Commerce","ID":"25679"},"score":0},{"data":{"ASSET":1423994,"CERT":25886,"NAME":"Rio Bank","ID":"25886"},"score":0},{"data":{"ASSET":2277487,"CERT":26223,"NAME":"Golden Bank, National Association","ID":"26223"},"score":0},{"data":{"ASSET":1053439,"CERT":26626,"NAME":"United Texas Bank, National Association","ID":"26626"},"score":0},{"data":{"ASSET":2249533,"CERT":26856,"NAME":"Falcon International Bank","ID":"26856"},"score":0},{"data":{"ASSET":2949812,"CERT":26906,"NAME":"Texas Regional Bank","ID":"26906"},"score":0},{"data":{"ASSET":2585922,"CERT":27074,"NAME":"State Bank of Texas","ID":"27074"},"score":0},{"data":{"ASSET":14159389,"CERT":29209,"NAME":"NexBank","ID":"29209"},"score":0},{"data":{"ASSET":15234117,"CERT":3066,"NAME":"First Financial Bank","ID":"3066"},"score":0},{"data":{"ASSET":1025678,"CERT":3067,"NAME":"Clear Fork Bank, National Association","ID":"3067"},"score":0},{"data":{"ASSET":1180522,"CERT":3091,"NAME":"The First National Bank of Bastrop","ID":"3091"},"score":0},{"data":{"ASSET":1271315,"CERT":3108,"NAME":"Legend Bank, N.A.","ID":"3108"},"score":0},{"data":{"ASSET":1543622,"CERT":3210,"NAME":"The Moody National Bank","ID":"3210"},"score":0},{"data":{"ASSET":4582833,"CERT":3250,"NAME":"VeraBank, National Association","ID":"3250"},"score":0},{"data":{"ASSET":2553778,"CERT":3256,"NAME":"Horizon Bank, SSB","ID":"3256"},"score":0},{"data":{"ASSET":3160448,"CERT":32574,"NAME":"Monet Bank","ID":"32574"},"score":0},{"data":{"ASSET":3331259,"CERT":3276,"NAME":"Austin Bank, Texas National Association","ID":"3276"},"score":0},{"data":{"ASSET":4644738,"CERT":3285,"NAME":"First National Bank Texas","ID":"3285"},"score":0},{"data":{"ASSET":3279902,"CERT":32941,"NAME":"WestStar Bank","ID":"32941"},"score":0},{"data":{"ASSET":1774437,"CERT":3325,"NAME":"First National Bank of Central Texas","ID":"3325"},"score":0},{"data":{"ASSET":1075946,"CERT":3330,"NAME":"The First National Bank of McGregor","ID":"3330"},"score":0},{"data":{"ASSET":1216298,"CERT":3337,"NAME":"Texas National Bank","ID":"3337"},"score":0},{"data":{"ASSET":1876348,"CERT":3387,"NAME":"FirstBank Southwest","ID":"3387"},"score":0},{"data":{"ASSET":1161379,"CERT":3389,"NAME":"Pointbank","ID":"3389"},"score":0},{"data":{"ASSET":5137149,"CERT":3405,"NAME":"Vantage Bank Texas","ID":"3405"},"score":0},{"data":{"ASSET":1391657,"CERT":34319,"NAME":"Southwestern National Bank","ID":"34319"},"score":0},{"data":{"ASSET":1081696,"CERT":34415,"NAME":"First Command Bank","ID":"34415"},"score":0},{"data":{"ASSET":2886145,"CERT":34656,"NAME":"American First National Bank","ID":"34656"},"score":0},{"data":{"ASSET":2990330,"CERT":34885,"NAME":"Susser Bank","ID":"34885"},"score":0},{"data":{"ASSET":15653917,"CERT":4767,"NAME":"Sunflower Bank, National Association","ID":"4767"},"score":0},{"data":{"ASSET":2590233,"CERT":5146,"NAME":"Wells Fargo Bank South Central, National Association","ID":"5146"},"score":0},{"data":{"ASSET":1374878,"CERT":5544,"NAME":"The City National Bank of Sulphur Springs","ID":"5544"},"score":0},{"data":{"ASSET":2574832,"CERT":5551,"NAME":"Extraco Banks, National Association","ID":"5551"},"score":0},{"data":{"ASSET":2188815,"CERT":5574,"NAME":"Citizens National Bank of Texas","ID":"5574"},"score":0},{"data":{"ASSET":1102281,"CERT":57703,"NAME":"T Bank, National Association","ID":"57703"},"score":0},{"data":{"ASSET":2845758,"CERT":58309,"NAME":"American Momentum Bank","ID":"58309"},"score":0},{"data":{"ASSET":1458168,"CERT":58483,"NAME":"Pegasus Bank","ID":"58483"},"score":0},{"data":{"ASSET":1076630,"CERT":58509,"NAME":"Frontier Bank of Texas","ID":"58509"},"score":0},{"data":{"ASSET":6728468,"CERT":58716,"NAME":"Third Coast Bank","ID":"58716"},"score":0},{"data":{"ASSET":1375315,"CERT":58739,"NAME":"Texas Security Bank","ID":"58739"},"score":0},{"data":{"ASSET":1032360,"CERT":58935,"NAME":"R Bank","ID":"58935"},"score":0},{"data":{"ASSET":10508989,"CERT":59108,"NAME":"Charles Schwab Trust Bank","ID":"59108"},"score":0},{"data":{"ASSET":1684362,"CERT":9978,"NAME":"First State Bank of Uvalde","ID":"9978"},"score":0}],"totals":{"count":84}}
```

## 2. Flags at 20260630

| Flag | Banks |
|---|---|
| Construction (LNRECONS >= RBCT1J) | 21 |
| CRE (CRE ratio >= 300%) | 18 |
| Growth (CRE flag and CRE sum up >= 50%) | 2 |
| Two or more flags | 11 |
| Any flag (distinct banks) | 28 |

Banks with two or more flags: 3405 Vantage Bank Texas (construction, CRE); 15657 Alliance Bank Central Texas (construction, CRE); 18185 Community National Bank & Trust of Texas (construction, CRE); 18344 UBank (construction, CRE, growth); 18609 American Bank of Commerce (construction, CRE, growth); 20231 Pinnacle Bank (construction, CRE); 20845 Wallis Bank (construction, CRE); 22373 American National Bank & Trust (construction, CRE); 22396 Central National Bank (construction, CRE); 26856 Falcon International Bank (construction, CRE); 26906 Texas Regional Bank (construction, CRE)

### Construction flag (21)

| CERT | NAME | construction ratio % | CRE ratio % | CRE sum growth % | RBCRWAJ |
|---|---|---|---|---|---|
| 3337 | Texas National Bank | 105.00 | 268.40 | 84.79 | 16.325050546488118 |
| 3389 | Pointbank | 110.86 | 185.49 | 41.32 | 16.353599587853772 |
| 3405 | Vantage Bank Texas | 122.90 | 352.93 | 11.34 | 11.378636463582637 |
| 12299 | SouthStar Bank, S.S.B. | 111.72 | 154.56 | -0.55 | 0 |
| 15657 | Alliance Bank Central Texas | 107.10 | 302.09 | 18.13 | 0 |
| 15809 | Security State Bank & Trust | 142.47 | 266.39 | -4.37 | 0 |
| 18185 | Community National Bank & Trust of Texas | 122.63 | 349.95 | 40.04 | 0 |
| 18344 | UBank | 203.60 | 489.14 | 80.57 | 0 |
| 18609 | American Bank of Commerce | 146.85 | 365.07 | 70.44 | 0 |
| 19215 | Benchmark Bank | 132.66 | 280.57 | 50.24 | 13.113613224447013 |
| 19559 | TexasBank | 136.61 | 239.10 | 31.68 | 18.6418458311484 |
| 20231 | Pinnacle Bank | 143.20 | 379.74 | 21.86 | 15.18664564639286 |
| 20845 | Wallis Bank | 121.28 | 419.46 | 12.76 | 0 |
| 22373 | American National Bank & Trust | 113.70 | 421.56 | 26.12 | 13.76699824968518 |
| 22396 | Central National Bank | 119.60 | 301.04 | 29.31 | 13.796223720192993 |
| 23799 | Texas First Bank | 124.93 | 247.05 | 64.98 | 0 |
| 25886 | Rio Bank | 106.85 | 261.28 | 143.02 | 14.870687743061204 |
| 26856 | Falcon International Bank | 121.26 | 301.07 | 42.60 | 20.95322882000298 |
| 26906 | Texas Regional Bank | 121.93 | 319.74 | 21.85 | 13.080879760624113 |
| 34885 | Susser Bank | 105.75 | 268.91 | 19.46 | 12.898717025607612 |
| 58716 | Third Coast Bank | 118.92 | 251.68 | 58.70 | 12.914733172543555 |

### CRE flag (18)

| CERT | NAME | construction ratio % | CRE ratio % | CRE sum growth % | RBCRWAJ |
|---|---|---|---|---|---|
| 3405 | Vantage Bank Texas | 122.90 | 352.93 | 11.34 | 11.378636463582637 |
| 15657 | Alliance Bank Central Texas | 107.10 | 302.09 | 18.13 | 0 |
| 18185 | Community National Bank & Trust of Texas | 122.63 | 349.95 | 40.04 | 0 |
| 18297 | Southside Bank | 61.28 | 303.47 | 25.19 | 17.103380202341885 |
| 18344 | UBank | 203.60 | 489.14 | 80.57 | 0 |
| 18355 | North Dallas Bank & Trust Co. | 43.76 | 338.61 | 24.79 | 0 |
| 18609 | American Bank of Commerce | 146.85 | 365.07 | 70.44 | 0 |
| 19080 | Inwood National Bank | 60.23 | 341.11 | 5.85 | 16.9781501957153 |
| 20231 | Pinnacle Bank | 143.20 | 379.74 | 21.86 | 15.18664564639286 |
| 20845 | Wallis Bank | 121.28 | 419.46 | 12.76 | 0 |
| 22373 | American National Bank & Trust | 113.70 | 421.56 | 26.12 | 13.76699824968518 |
| 22396 | Central National Bank | 119.60 | 301.04 | 29.31 | 13.796223720192993 |
| 26223 | Golden Bank, National Association | 71.06 | 352.81 | 47.88 | 16.84865885984296 |
| 26856 | Falcon International Bank | 121.26 | 301.07 | 42.60 | 20.95322882000298 |
| 26906 | Texas Regional Bank | 121.93 | 319.74 | 21.85 | 13.080879760624113 |
| 27074 | State Bank of Texas | 33.86 | 483.77 | 19.33 | 0 |
| 32941 | WestStar Bank | 84.08 | 368.84 | 24.54 | 14.069087184838299 |
| 34319 | Southwestern National Bank | 40.48 | 348.16 | 21.40 | 15.787595491030576 |

### Growth flag (2)

| CERT | NAME | construction ratio % | CRE ratio % | CRE sum growth % | RBCRWAJ |
|---|---|---|---|---|---|
| 18344 | UBank | 203.60 | 489.14 | 80.57 | 0 |
| 18609 | American Bank of Commerce | 146.85 | 365.07 | 70.44 | 0 |

## 3. Top 15 CRE ratios at 20260630 (ties by CERT)

| Rank | CERT | NAME | CRE ratio % | construction ratio % | CRE sum growth % |
|---|---|---|---|---|---|
| 1 | 18344 | UBank | 489.14 | 203.60 | 80.57 |
| 2 | 27074 | State Bank of Texas | 483.77 | 33.86 | 19.33 |
| 3 | 22373 | American National Bank & Trust | 421.56 | 113.70 | 26.12 |
| 4 | 20845 | Wallis Bank | 419.46 | 121.28 | 12.76 |
| 5 | 20231 | Pinnacle Bank | 379.74 | 143.20 | 21.86 |
| 6 | 32941 | WestStar Bank | 368.84 | 84.08 | 24.54 |
| 7 | 18609 | American Bank of Commerce | 365.07 | 146.85 | 70.44 |
| 8 | 3405 | Vantage Bank Texas | 352.93 | 122.90 | 11.34 |
| 9 | 26223 | Golden Bank, National Association | 352.81 | 71.06 | 47.88 |
| 10 | 18185 | Community National Bank & Trust of Texas | 349.95 | 122.63 | 40.04 |
| 11 | 34319 | Southwestern National Bank | 348.16 | 40.48 | 21.40 |
| 12 | 19080 | Inwood National Bank | 341.11 | 60.23 | 5.85 |
| 13 | 18355 | North Dallas Bank & Trust Co. | 338.61 | 43.76 | 24.79 |
| 14 | 26906 | Texas Regional Bank | 319.74 | 121.93 | 21.85 |
| 15 | 18297 | Southside Bank | 303.47 | 61.28 | 25.19 |

## 4. Medians at 20260630

| Ratio | Median % | Banks used |
|---|---|---|
| Construction ratio | 75.39 | 84 |
| CRE ratio | 238.98 | 84 |

## 5. Changes: PULL 2 vs PULL 1

Matched by key CERT + REPDTE; Changes columns: all columns after REPDTE (LNRECONS, LNREMULT, LNRENROT, LNRENROW, RBCT1J, RBCRWAJ, EQTOT, construction ratio, CRE ratio).

no change: PULL 1 has 168 rows, PULL 2 has 168 rows (new 0, gone 0, changed 0; 168 = 168 + 0 - 0).

## 6. Changes: PULL 3 vs PULL 2

Matched by key CERT + REPDTE; Changes columns: all columns after REPDTE (LNRECONS, LNREMULT, LNRENROT, LNRENROW, RBCT1J, RBCRWAJ, EQTOT, construction ratio, CRE ratio).

no change: PULL 2 has 168 rows, PULL 3 has 168 rows (new 0, gone 0, changed 0; 168 = 168 + 0 - 0).

## 7. Data files (Rule 25)

D2-D4 are attached as data files; columns in order: CERT, NAME, REPDTE, LNRECONS, LNREMULT, LNRENROT, LNRENROW, RBCT1J, RBCRWAJ, EQTOT, construction ratio, CRE ratio (key: CERT + REPDTE).

```synmerco-data
8b4d5c4dca9ec8abfcf7b0be1fad25710fa3817c9ec148cc092cc9ece70707fa tx-cre-pull1.csv
8b4d5c4dca9ec8abfcf7b0be1fad25710fa3817c9ec148cc092cc9ece70707fa tx-cre-pull2.csv
8b4d5c4dca9ec8abfcf7b0be1fad25710fa3817c9ec148cc092cc9ece70707fa tx-cre-pull3.csv
```

## Answers

1. The report lists the banks FDIC BankFind returned at pull 1 with a raw excerpt, and every CSV holds two rows per CERT: Yes. 84 banks listed in section 1 with the full raw institutions response (see excerpt 1); each of the three CSVs has 168 rows = 2 x 84, one per CERT and quarter 20230630 and 20260630, 0 missing bank-quarters, none header-only.
2. The three CSV files are attached with exactly the listed columns and ratios as the TASK says: Yes. tx-cre-pull1.csv (D2), tx-cre-pull2.csv (D3), tx-cre-pull3.csv (D4), header `CERT,NAME,REPDTE,LNRECONS,LNREMULT,LNRENROT,LNRENROW,RBCT1J,RBCRWAJ,EQTOT,construction ratio,CRE ratio`; SHA-256 in the synmerco-data block; ratios recomputed independently from the unrounded values for all 168 rows and match.
3. Every flagged bank is backed by its raw financials excerpt for both quarters, and flags, lists and medians follow the TASK and agree with the CSV: Yes. 28 flagged banks, each with a raw excerpt showing 20230630 and 20260630 in the PROOF (excerpts 2 to 29); flags, lists, top 15 and medians computed by one script from tx-cre-pull3.csv (identical bytes to pulls 1 and 2).
4. The PLATFORM RECORD shows PULL 1, PULL 2 and PULL 3 notes at least 24 hours apart, each with its CSV's row count and SHA-256, increasing source times and matching change counts: Yes. Note recordedAt (UTC): PULL 1 2026-11-21 21:35:56.361554+00, PULL 2 2026-11-22 23:15:00.417919+00 (25h 39m 4s later), PULL 3 2026-11-23 23:17:50.207259+00 (24h 2m 49s later). Each note gives rows=168 and sha256=8b4d5c4dca9ec8abfcf7b0be1fad25710fa3817c9ec148cc092cc9ece70707fa. Source times increase: `Date: Sat, 21 Nov 2026 21:34:43 GMT` < `Date: Sun, 22 Nov 2026 23:14:20 GMT` < `Date: Mon, 23 Nov 2026 23:17:14 GMT`. Change counts: 168 vs 168 rows, new 0, gone 0, changed 0, for both comparisons; no pull failed.

## PROOF

One line per request, from each pull's run log (raw/pull*/run.json): CERT (or `institutions`), UTC time, HTTP status, and `attempt 2` where it is the single retry after the first failed. Every financials request is an HTTP GET to host api.fdic.gov, endpoint /banks/financials, with the full request:

```
https://api.fdic.gov/banks/financials?filters=CERT%3A<CERT>+AND+%28REPDTE%3A20230630+OR+REPDTE%3A20260630%29&fields=CERT%2CREPDTE%2CLNRECONS%2CLNREMULT%2CLNRENROT%2CLNRENROW%2CRBCT1J%2CRBCRWAJ%2CEQTOT&limit=10
```

The institutions request is, each pull:

```
https://api.fdic.gov/banks/institutions?filters=STALP%3ATX+AND+ACTIVE%3A1+AND+ASSET%3A%5B1000000+TO+20000000%5D&fields=NAME%2CCERT%2CASSET&limit=200
```

### PULL 1 request log

Source time (first response Date header):

```
Date: Sat, 21 Nov 2026 21:34:43 GMT
```

88 lines, one per request (including retries): CERT | UTC time | HTTP status

```
institutions | 2026-11-21T21:34:43Z | 200
1209 | 2026-11-21T21:34:43Z | 200
1213 | 2026-11-21T21:34:44Z | 200
1497 | 2026-11-21T21:34:44Z | 200
3066 | 2026-11-21T21:34:44Z | 200
3067 | 2026-11-21T21:34:45Z | 200
3091 | 2026-11-21T21:34:45Z | 200
3108 | 2026-11-21T21:34:45Z | 200
3210 | 2026-11-21T21:34:46Z | 200
3250 | 2026-11-21T21:34:46Z | 200
3256 | 2026-11-21T21:34:46Z | 200
3276 | 2026-11-21T21:34:47Z | 200
3285 | 2026-11-21T21:34:47Z | 200
3325 | 2026-11-21T21:34:47Z | 200
3330 | 2026-11-21T21:34:48Z | 200
3337 | 2026-11-21T21:34:48Z | 200
3387 | 2026-11-21T21:34:48Z | 200
3389 | 2026-11-21T21:34:49Z | 200
3405 | 2026-11-21T21:34:49Z | 429
3405 | 2026-11-21T21:34:51Z | 200 | attempt 2
4767 | 2026-11-21T21:34:52Z | 200
5146 | 2026-11-21T21:34:52Z | 200
5544 | 2026-11-21T21:34:52Z | 200
5551 | 2026-11-21T21:34:53Z | 200
5574 | 2026-11-21T21:34:53Z | 200
9978 | 2026-11-21T21:34:53Z | 200
11569 | 2026-11-21T21:34:54Z | 200
11935 | 2026-11-21T21:34:54Z | 200
12299 | 2026-11-21T21:34:54Z | 200
12769 | 2026-11-21T21:34:55Z | 200
14531 | 2026-11-21T21:34:55Z | 200
15511 | 2026-11-21T21:34:55Z | 200
15657 | 2026-11-21T21:34:56Z | 200
15797 | 2026-11-21T21:34:56Z | 200
15809 | 2026-11-21T21:34:56Z | 200
16470 | 2026-11-21T21:34:57Z | 200
16753 | 2026-11-21T21:34:57Z | 200
17491 | 2026-11-21T21:34:57Z | 200
17612 | 2026-11-21T21:34:58Z | 429
17612 | 2026-11-21T21:35:00Z | 200 | attempt 2
17842 | 2026-11-21T21:35:00Z | 200
18185 | 2026-11-21T21:35:01Z | 429
18185 | 2026-11-21T21:35:03Z | 200 | attempt 2
18297 | 2026-11-21T21:35:03Z | 200
18344 | 2026-11-21T21:35:04Z | 200
18355 | 2026-11-21T21:35:04Z | 200
18609 | 2026-11-21T21:35:04Z | 200
19080 | 2026-11-21T21:35:05Z | 200
19215 | 2026-11-21T21:35:05Z | 200
19559 | 2026-11-21T21:35:05Z | 200
19629 | 2026-11-21T21:35:06Z | 200
20099 | 2026-11-21T21:35:06Z | 200
20231 | 2026-11-21T21:35:06Z | 200
20845 | 2026-11-21T21:35:07Z | 200
22373 | 2026-11-21T21:35:07Z | 200
22396 | 2026-11-21T21:35:07Z | 200
22957 | 2026-11-21T21:35:08Z | 200
23220 | 2026-11-21T21:35:08Z | 200
23474 | 2026-11-21T21:35:08Z | 200
23498 | 2026-11-21T21:35:09Z | 200
23647 | 2026-11-21T21:35:09Z | 200
23799 | 2026-11-21T21:35:09Z | 200
24347 | 2026-11-21T21:35:10Z | 200
24563 | 2026-11-21T21:35:10Z | 200
24897 | 2026-11-21T21:35:10Z | 200
25103 | 2026-11-21T21:35:11Z | 200
25679 | 2026-11-21T21:35:11Z | 200
25886 | 2026-11-21T21:35:11Z | 200
26223 | 2026-11-21T21:35:12Z | 200
26626 | 2026-11-21T21:35:12Z | 200
26856 | 2026-11-21T21:35:12Z | 200
26906 | 2026-11-21T21:35:13Z | 200
27074 | 2026-11-21T21:35:13Z | 200
29209 | 2026-11-21T21:35:13Z | 200
32574 | 2026-11-21T21:35:13Z | 200
32941 | 2026-11-21T21:35:14Z | 200
34319 | 2026-11-21T21:35:14Z | 200
34415 | 2026-11-21T21:35:14Z | 200
34656 | 2026-11-21T21:35:15Z | 200
34885 | 2026-11-21T21:35:15Z | 200
57703 | 2026-11-21T21:35:15Z | 200
58309 | 2026-11-21T21:35:16Z | 200
58483 | 2026-11-21T21:35:16Z | 200
58509 | 2026-11-21T21:35:16Z | 200
58716 | 2026-11-21T21:35:17Z | 200
58739 | 2026-11-21T21:35:17Z | 200
58935 | 2026-11-21T21:35:17Z | 200
59108 | 2026-11-21T21:35:18Z | 200
```

### PULL 2 request log

Source time (first response Date header):

```
Date: Sun, 22 Nov 2026 23:14:20 GMT
```

86 lines, one per request (including retries): CERT | UTC time | HTTP status

```
institutions | 2026-11-22T23:14:19Z | 200
1209 | 2026-11-22T23:14:20Z | 200
1213 | 2026-11-22T23:14:20Z | 200
1497 | 2026-11-22T23:14:20Z | 200
3066 | 2026-11-22T23:14:21Z | 200
3067 | 2026-11-22T23:14:21Z | 200
3091 | 2026-11-22T23:14:21Z | 200
3108 | 2026-11-22T23:14:22Z | 200
3210 | 2026-11-22T23:14:22Z | 200
3250 | 2026-11-22T23:14:22Z | 200
3256 | 2026-11-22T23:14:23Z | 200
3276 | 2026-11-22T23:14:23Z | 200
3285 | 2026-11-22T23:14:23Z | 200
3325 | 2026-11-22T23:14:24Z | 200
3330 | 2026-11-22T23:14:24Z | 200
3337 | 2026-11-22T23:14:25Z | 200
3387 | 2026-11-22T23:14:25Z | 200
3389 | 2026-11-22T23:14:25Z | 200
3405 | 2026-11-22T23:14:26Z | 200
4767 | 2026-11-22T23:14:26Z | 200
5146 | 2026-11-22T23:14:26Z | 200
5544 | 2026-11-22T23:14:27Z | 200
5551 | 2026-11-22T23:14:27Z | 200
5574 | 2026-11-22T23:14:27Z | 200
9978 | 2026-11-22T23:14:27Z | 200
11569 | 2026-11-22T23:14:28Z | 200
11935 | 2026-11-22T23:14:28Z | 200
12299 | 2026-11-22T23:14:28Z | 200
12769 | 2026-11-22T23:14:29Z | 200
14531 | 2026-11-22T23:14:29Z | 200
15511 | 2026-11-22T23:14:29Z | 200
15657 | 2026-11-22T23:14:30Z | 200
15797 | 2026-11-22T23:14:30Z | 200
15809 | 2026-11-22T23:14:30Z | 200
16470 | 2026-11-22T23:14:31Z | 200
16753 | 2026-11-22T23:14:31Z | 200
17491 | 2026-11-22T23:14:31Z | 200
17612 | 2026-11-22T23:14:32Z | 200
17842 | 2026-11-22T23:14:32Z | 200
18185 | 2026-11-22T23:14:32Z | 200
18297 | 2026-11-22T23:14:33Z | 200
18344 | 2026-11-22T23:14:33Z | 200
18355 | 2026-11-22T23:14:33Z | 200
18609 | 2026-11-22T23:14:34Z | 200
19080 | 2026-11-22T23:14:34Z | 200
19215 | 2026-11-22T23:14:34Z | 200
19559 | 2026-11-22T23:14:35Z | 200
19629 | 2026-11-22T23:14:35Z | 200
20099 | 2026-11-22T23:14:35Z | 200
20231 | 2026-11-22T23:14:36Z | 200
20845 | 2026-11-22T23:14:36Z | 200
22373 | 2026-11-22T23:14:36Z | 200
22396 | 2026-11-22T23:14:37Z | 200
22957 | 2026-11-22T23:14:37Z | 200
23220 | 2026-11-22T23:14:37Z | 200
23474 | 2026-11-22T23:14:38Z | 200
23498 | 2026-11-22T23:14:38Z | 200
23647 | 2026-11-22T23:14:38Z | 200
23799 | 2026-11-22T23:14:39Z | 200
24347 | 2026-11-22T23:14:39Z | 200
24563 | 2026-11-22T23:14:39Z | 200
24897 | 2026-11-22T23:14:40Z | 200
25103 | 2026-11-22T23:14:40Z | 200
25679 | 2026-11-22T23:14:40Z | 200
25886 | 2026-11-22T23:14:41Z | 200
26223 | 2026-11-22T23:14:41Z | 200
26626 | 2026-11-22T23:14:41Z | 200
26856 | 2026-11-22T23:14:42Z | 200
26906 | 2026-11-22T23:14:42Z | 429
26906 | 2026-11-22T23:14:44Z | 200 | attempt 2
27074 | 2026-11-22T23:14:45Z | 200
29209 | 2026-11-22T23:14:45Z | 200
32574 | 2026-11-22T23:14:45Z | 200
32941 | 2026-11-22T23:14:46Z | 200
34319 | 2026-11-22T23:14:46Z | 200
34415 | 2026-11-22T23:14:46Z | 200
34656 | 2026-11-22T23:14:47Z | 200
34885 | 2026-11-22T23:14:47Z | 200
57703 | 2026-11-22T23:14:48Z | 200
58309 | 2026-11-22T23:14:48Z | 200
58483 | 2026-11-22T23:14:48Z | 200
58509 | 2026-11-22T23:14:48Z | 200
58716 | 2026-11-22T23:14:49Z | 200
58739 | 2026-11-22T23:14:49Z | 200
58935 | 2026-11-22T23:14:49Z | 200
59108 | 2026-11-22T23:14:50Z | 200
```

### PULL 3 request log

Source time (first response Date header):

```
Date: Mon, 23 Nov 2026 23:17:14 GMT
```

85 lines, one per request (including retries): CERT | UTC time | HTTP status

```
institutions | 2026-11-23T23:17:13Z | 200
1209 | 2026-11-23T23:17:14Z | 200
1213 | 2026-11-23T23:17:14Z | 200
1497 | 2026-11-23T23:17:14Z | 200
3066 | 2026-11-23T23:17:15Z | 200
3067 | 2026-11-23T23:17:15Z | 200
3091 | 2026-11-23T23:17:15Z | 200
3108 | 2026-11-23T23:17:16Z | 200
3210 | 2026-11-23T23:17:16Z | 200
3250 | 2026-11-23T23:17:16Z | 200
3256 | 2026-11-23T23:17:17Z | 200
3276 | 2026-11-23T23:17:17Z | 200
3285 | 2026-11-23T23:17:17Z | 200
3325 | 2026-11-23T23:17:18Z | 200
3330 | 2026-11-23T23:17:18Z | 200
3337 | 2026-11-23T23:17:18Z | 200
3387 | 2026-11-23T23:17:19Z | 200
3389 | 2026-11-23T23:17:19Z | 200
3405 | 2026-11-23T23:17:20Z | 200
4767 | 2026-11-23T23:17:20Z | 200
5146 | 2026-11-23T23:17:20Z | 200
5544 | 2026-11-23T23:17:21Z | 200
5551 | 2026-11-23T23:17:21Z | 200
5574 | 2026-11-23T23:17:21Z | 200
9978 | 2026-11-23T23:17:22Z | 200
11569 | 2026-11-23T23:17:22Z | 200
11935 | 2026-11-23T23:17:22Z | 200
12299 | 2026-11-23T23:17:23Z | 200
12769 | 2026-11-23T23:17:23Z | 200
14531 | 2026-11-23T23:17:23Z | 200
15511 | 2026-11-23T23:17:24Z | 200
15657 | 2026-11-23T23:17:24Z | 200
15797 | 2026-11-23T23:17:24Z | 200
15809 | 2026-11-23T23:17:25Z | 200
16470 | 2026-11-23T23:17:25Z | 200
16753 | 2026-11-23T23:17:26Z | 200
17491 | 2026-11-23T23:17:26Z | 200
17612 | 2026-11-23T23:17:26Z | 200
17842 | 2026-11-23T23:17:27Z | 200
18185 | 2026-11-23T23:17:27Z | 200
18297 | 2026-11-23T23:17:27Z | 200
18344 | 2026-11-23T23:17:28Z | 200
18355 | 2026-11-23T23:17:28Z | 200
18609 | 2026-11-23T23:17:28Z | 200
19080 | 2026-11-23T23:17:29Z | 200
19215 | 2026-11-23T23:17:29Z | 200
19559 | 2026-11-23T23:17:29Z | 200
19629 | 2026-11-23T23:17:30Z | 200
20099 | 2026-11-23T23:17:30Z | 200
20231 | 2026-11-23T23:17:30Z | 200
20845 | 2026-11-23T23:17:31Z | 200
22373 | 2026-11-23T23:17:31Z | 200
22396 | 2026-11-23T23:17:31Z | 200
22957 | 2026-11-23T23:17:32Z | 200
23220 | 2026-11-23T23:17:32Z | 200
23474 | 2026-11-23T23:17:32Z | 200
23498 | 2026-11-23T23:17:33Z | 200
23647 | 2026-11-23T23:17:33Z | 200
23799 | 2026-11-23T23:17:33Z | 200
24347 | 2026-11-23T23:17:34Z | 200
24563 | 2026-11-23T23:17:34Z | 200
24897 | 2026-11-23T23:17:34Z | 200
25103 | 2026-11-23T23:17:35Z | 200
25679 | 2026-11-23T23:17:35Z | 200
25886 | 2026-11-23T23:17:35Z | 200
26223 | 2026-11-23T23:17:35Z | 200
26626 | 2026-11-23T23:17:36Z | 200
26856 | 2026-11-23T23:17:36Z | 200
26906 | 2026-11-23T23:17:36Z | 200
27074 | 2026-11-23T23:17:37Z | 200
29209 | 2026-11-23T23:17:37Z | 200
32574 | 2026-11-23T23:17:37Z | 200
32941 | 2026-11-23T23:17:38Z | 200
34319 | 2026-11-23T23:17:38Z | 200
34415 | 2026-11-23T23:17:38Z | 200
34656 | 2026-11-23T23:17:39Z | 200
34885 | 2026-11-23T23:17:39Z | 200
57703 | 2026-11-23T23:17:39Z | 200
58309 | 2026-11-23T23:17:40Z | 200
58483 | 2026-11-23T23:17:40Z | 200
58509 | 2026-11-23T23:17:40Z | 200
58716 | 2026-11-23T23:17:41Z | 200
58739 | 2026-11-23T23:17:41Z | 200
58935 | 2026-11-23T23:17:41Z | 200
59108 | 2026-11-23T23:17:42Z | 200
```

### Raw financials excerpts, one per flagged bank, both quarters (PULL 3 raw response, verbatim; request line in the PULL 3 log above)

#### Excerpt 2: CERT 3337 Texas National Bank (flags: construction)
- Request: GET api.fdic.gov /banks/financials CERT 3337 (full URL as in the template above)
- Retrieved (UTC): 2026-11-23T23:17:18Z
```
{"meta":{"total":2,"parameters":{"filters":"CERT:3337 AND (REPDTE:20230630 OR REPDTE:20260630)","fields":"CERT,REPDTE,LNRECONS,LNREMULT,LNRENROT,LNRENROW,RBCT1J,RBCRWAJ,EQTOT","limit":"10"},"index":{"name":"risview_20261116221646","createTimestamp":"2026-11-16T22:16:48Z"}},"data":[{"data":{"LNRENROT":46151,"RBCRWAJ":18.77558311530728,"RBCT1J":80428,"REPDTE":"20230630","LNREMULT":27177,"CERT":3337,"LNRENROW":47935,"LNRECONS":105987,"EQTOT":67409,"ID":"3337_20230630"},"score":0},{"data":{"LNRENROT":142758,"RBCRWAJ":16.325050546488118,"RBCT1J":123453,"REPDTE":"20260630","LNREMULT":58964,"CERT":3337,"LNRENROW":105762,"LNRECONS":129626,"EQTOT":114884,"ID":"3337_20260630"},"score":0}],"totals":{"count":2}}
```
#### Excerpt 3: CERT 3389 Pointbank (flags: construction)
- Request: GET api.fdic.gov /banks/financials CERT 3389 (full URL as in the template above)
- Retrieved (UTC): 2026-11-23T23:17:19Z
```
{"meta":{"total":2,"parameters":{"filters":"CERT:3389 AND (REPDTE:20230630 OR REPDTE:20260630)","fields":"CERT,REPDTE,LNRECONS,LNREMULT,LNRENROT,LNRENROW,RBCT1J,RBCRWAJ,EQTOT","limit":"10"},"index":{"name":"risview_20261116221646","createTimestamp":"2026-11-16T22:16:48Z"}},"data":[{"data":{"LNRENROT":62648,"RBCRWAJ":14.949989165835495,"RBCT1J":82822,"REPDTE":"20230630","LNREMULT":5246,"CERT":3389,"LNRENROW":131222,"LNRECONS":69846,"EQTOT":40800,"ID":"3389_20230630"},"score":0},{"data":{"LNRENROT":73846,"RBCRWAJ":16.353599587853772,"RBCT1J":104938,"REPDTE":"20260630","LNREMULT":4472,"CERT":3389,"LNRENROW":152966,"LNRECONS":116335,"EQTOT":82502,"ID":"3389_20260630"},"score":0}],"totals":{"count":2}}
```
#### Excerpt 4: CERT 3405 Vantage Bank Texas (flags: construction, CRE)
- Request: GET api.fdic.gov /banks/financials CERT 3405 (full URL as in the template above)
- Retrieved (UTC): 2026-11-23T23:17:20Z
```
{"meta":{"total":2,"parameters":{"filters":"CERT:3405 AND (REPDTE:20230630 OR REPDTE:20260630)","fields":"CERT,REPDTE,LNRECONS,LNREMULT,LNRENROT,LNRENROW,RBCT1J,RBCRWAJ,EQTOT","limit":"10"},"index":{"name":"risview_20261116221646","createTimestamp":"2026-11-16T22:16:48Z"}},"data":[{"data":{"LNRENROT":790650,"RBCRWAJ":11.745107164599007,"RBCT1J":360093,"REPDTE":"20230630","LNREMULT":154706,"CERT":3405,"LNRENROW":456358,"LNRECONS":485464,"EQTOT":330468,"ID":"3405_20230630"},"score":0},{"data":{"LNRENROT":958336,"RBCRWAJ":11.378636463582637,"RBCT1J":451373,"REPDTE":"20260630","LNREMULT":79948,"CERT":3405,"LNRENROW":559734,"LNRECONS":554748,"EQTOT":439690,"ID":"3405_20260630"},"score":0}],"totals":{"count":2}}
```
#### Excerpt 5: CERT 12299 SouthStar Bank, S.S.B. (flags: construction)
- Request: GET api.fdic.gov /banks/financials CERT 12299 (full URL as in the template above)
- Retrieved (UTC): 2026-11-23T23:17:23Z
```
{"meta":{"total":2,"parameters":{"filters":"CERT:12299 AND (REPDTE:20230630 OR REPDTE:20260630)","fields":"CERT,REPDTE,LNRECONS,LNREMULT,LNRENROT,LNRENROW,RBCT1J,RBCRWAJ,EQTOT","limit":"10"},"index":{"name":"risview_20261116221646","createTimestamp":"2026-11-16T22:16:48Z"}},"data":[{"data":{"LNRENROT":77454,"RBCRWAJ":15.441243966637991,"RBCT1J":137092,"REPDTE":"20230630","LNREMULT":2514,"CERT":12299,"LNRENROW":106598,"LNRECONS":198264,"EQTOT":123607,"ID":"12299_20230630"},"score":0},{"data":{"LNRENROT":75091,"RBCRWAJ":0,"RBCT1J":179029,"REPDTE":"20260630","LNREMULT":1592,"CERT":12299,"LNRENROW":106685,"LNRECONS":200020,"EQTOT":170807,"ID":"12299_20260630"},"score":0}],"totals":{"count":2}}
```
#### Excerpt 6: CERT 15657 Alliance Bank Central Texas (flags: construction, CRE)
- Request: GET api.fdic.gov /banks/financials CERT 15657 (full URL as in the template above)
- Retrieved (UTC): 2026-11-23T23:17:24Z
```
{"meta":{"total":2,"parameters":{"filters":"CERT:15657 AND (REPDTE:20230630 OR REPDTE:20260630)","fields":"CERT,REPDTE,LNRECONS,LNREMULT,LNRENROT,LNRENROW,RBCT1J,RBCRWAJ,EQTOT","limit":"10"},"index":{"name":"risview_20261116221646","createTimestamp":"2026-11-16T22:16:48Z"}},"data":[{"data":{"LNRENROT":205948,"RBCRWAJ":15.888030469080611,"RBCT1J":109256,"REPDTE":"20230630","LNREMULT":14612,"CERT":15657,"LNRENROW":67437,"LNRECONS":172067,"EQTOT":104049,"ID":"15657_20230630"},"score":0},{"data":{"LNRENROT":286002,"RBCRWAJ":0,"RBCT1J":153525,"REPDTE":"20260630","LNREMULT":13366,"CERT":15657,"LNRENROW":137037,"LNRECONS":164423,"EQTOT":150840,"ID":"15657_20260630"},"score":0}],"totals":{"count":2}}
```
#### Excerpt 7: CERT 15809 Security State Bank & Trust (flags: construction)
- Request: GET api.fdic.gov /banks/financials CERT 15809 (full URL as in the template above)
- Retrieved (UTC): 2026-11-23T23:17:25Z
```
{"meta":{"total":2,"parameters":{"filters":"CERT:15809 AND (REPDTE:20230630 OR REPDTE:20260630)","fields":"CERT,REPDTE,LNRECONS,LNREMULT,LNRENROT,LNRENROW,RBCT1J,RBCRWAJ,EQTOT","limit":"10"},"index":{"name":"risview_20261116221646","createTimestamp":"2026-11-16T22:16:48Z"}},"data":[{"data":{"LNRENROT":220171,"RBCRWAJ":0,"RBCT1J":189152,"REPDTE":"20230630","LNREMULT":26111,"CERT":15809,"LNRENROW":107559,"LNRECONS":448249,"EQTOT":161838,"ID":"15809_20230630"},"score":0},{"data":{"LNRENROT":232422,"RBCRWAJ":0,"RBCT1J":249330,"REPDTE":"20260630","LNREMULT":76541,"CERT":15809,"LNRENROW":198949,"LNRECONS":355230,"EQTOT":234839,"ID":"15809_20260630"},"score":0}],"totals":{"count":2}}
```
#### Excerpt 8: CERT 18185 Community National Bank & Trust of Texas (flags: construction, CRE)
- Request: GET api.fdic.gov /banks/financials CERT 18185 (full URL as in the template above)
- Retrieved (UTC): 2026-11-23T23:17:27Z
```
{"meta":{"total":2,"parameters":{"filters":"CERT:18185 AND (REPDTE:20230630 OR REPDTE:20260630)","fields":"CERT,REPDTE,LNRECONS,LNREMULT,LNRENROT,LNRENROW,RBCT1J,RBCRWAJ,EQTOT","limit":"10"},"index":{"name":"risview_20261116221646","createTimestamp":"2026-11-16T22:16:48Z"}},"data":[{"data":{"LNRENROT":224761,"RBCRWAJ":15.446394224866793,"RBCT1J":140264,"REPDTE":"20230630","LNREMULT":2231,"CERT":18185,"LNRENROW":146674,"LNRECONS":210190,"EQTOT":129969,"ID":"18185_20230630"},"score":0},{"data":{"LNRENROT":384923,"RBCRWAJ":0,"RBCT1J":174952,"REPDTE":"20260630","LNREMULT":12786,"CERT":18185,"LNRENROW":239959,"LNRECONS":214535,"EQTOT":196056,"ID":"18185_20260630"},"score":0}],"totals":{"count":2}}
```
#### Excerpt 9: CERT 18297 Southside Bank (flags: CRE)
- Request: GET api.fdic.gov /banks/financials CERT 18297 (full URL as in the template above)
- Retrieved (UTC): 2026-11-23T23:17:27Z
```
{"meta":{"total":2,"parameters":{"filters":"CERT:18297 AND (REPDTE:20230630 OR REPDTE:20260630)","fields":"CERT,REPDTE,LNRECONS,LNREMULT,LNRENROT,LNRENROW,RBCT1J,RBCRWAJ,EQTOT","limit":"10"},"index":{"name":"risview_20261116221646","createTimestamp":"2026-11-16T22:16:48Z"}},"data":[{"data":{"LNRENROT":1378452,"RBCRWAJ":15.54890961377054,"RBCT1J":828749,"REPDTE":"20230630","LNREMULT":338052,"CERT":18297,"LNRENROW":356017,"LNRECONS":657354,"EQTOT":907977,"ID":"18297_20230630"},"score":0},{"data":{"LNRENROT":1729967,"RBCRWAJ":17.103380202341885,"RBCT1J":979280,"REPDTE":"20260630","LNREMULT":641811,"CERT":18297,"LNRENROW":362390,"LNRECONS":600080,"EQTOT":1083738,"ID":"18297_20260630"},"score":0}],"totals":{"count":2}}
```
#### Excerpt 10: CERT 18344 UBank (flags: construction, CRE, growth)
- Request: GET api.fdic.gov /banks/financials CERT 18344 (full URL as in the template above)
- Retrieved (UTC): 2026-11-23T23:17:28Z
```
{"meta":{"total":2,"parameters":{"filters":"CERT:18344 AND (REPDTE:20230630 OR REPDTE:20260630)","fields":"CERT,REPDTE,LNRECONS,LNREMULT,LNRENROT,LNRENROW,RBCT1J,RBCRWAJ,EQTOT","limit":"10"},"index":{"name":"risview_20261116221646","createTimestamp":"2026-11-16T22:16:48Z"}},"data":[{"data":{"LNRENROT":140012,"RBCRWAJ":0,"RBCT1J":60032,"REPDTE":"20230630","LNREMULT":24366,"CERT":18344,"LNRENROW":43817,"LNRECONS":86094,"EQTOT":57090,"ID":"18344_20230630"},"score":0},{"data":{"LNRENROT":179627,"RBCRWAJ":0,"RBCT1J":92464,"REPDTE":"20260630","LNREMULT":84399,"CERT":18344,"LNRENROW":99996,"LNRECONS":188254,"EQTOT":90795,"ID":"18344_20260630"},"score":0}],"totals":{"count":2}}
```
#### Excerpt 11: CERT 18355 North Dallas Bank & Trust Co. (flags: CRE)
- Request: GET api.fdic.gov /banks/financials CERT 18355 (full URL as in the template above)
- Retrieved (UTC): 2026-11-23T23:17:28Z
```
{"meta":{"total":2,"parameters":{"filters":"CERT:18355 AND (REPDTE:20230630 OR REPDTE:20260630)","fields":"CERT,REPDTE,LNRECONS,LNREMULT,LNRENROT,LNRENROW,RBCT1J,RBCRWAJ,EQTOT","limit":"10"},"index":{"name":"risview_20261116221646","createTimestamp":"2026-11-16T22:16:48Z"}},"data":[{"data":{"LNRENROT":368653,"RBCRWAJ":0,"RBCT1J":175561,"REPDTE":"20230630","LNREMULT":33251,"CERT":18355,"LNRENROW":240443,"LNRECONS":110730,"EQTOT":160523,"ID":"18355_20230630"},"score":0},{"data":{"LNRENROT":472481,"RBCRWAJ":0,"RBCT1J":188925,"REPDTE":"20260630","LNREMULT":84573,"CERT":18355,"LNRENROW":248457,"LNRECONS":82666,"EQTOT":187785,"ID":"18355_20260630"},"score":0}],"totals":{"count":2}}
```
#### Excerpt 12: CERT 18609 American Bank of Commerce (flags: construction, CRE, growth)
- Request: GET api.fdic.gov /banks/financials CERT 18609 (full URL as in the template above)
- Retrieved (UTC): 2026-11-23T23:17:28Z
```
{"meta":{"total":2,"parameters":{"filters":"CERT:18609 AND (REPDTE:20230630 OR REPDTE:20260630)","fields":"CERT,REPDTE,LNRECONS,LNREMULT,LNRENROT,LNRENROW,RBCT1J,RBCRWAJ,EQTOT","limit":"10"},"index":{"name":"risview_20261116221646","createTimestamp":"2026-11-16T22:16:48Z"}},"data":[{"data":{"LNRENROT":170368,"RBCRWAJ":12.874251497005988,"RBCT1J":130410,"REPDTE":"20230630","LNREMULT":61945,"CERT":18609,"LNRENROW":187996,"LNRECONS":156029,"EQTOT":70652,"ID":"18609_20230630"},"score":0},{"data":{"LNRENROT":299774,"RBCRWAJ":0,"RBCT1J":181299,"REPDTE":"20260630","LNREMULT":95865,"CERT":18609,"LNRENROW":256448,"LNRECONS":266232,"EQTOT":147542,"ID":"18609_20260630"},"score":0}],"totals":{"count":2}}
```
#### Excerpt 13: CERT 19080 Inwood National Bank (flags: CRE)
- Request: GET api.fdic.gov /banks/financials CERT 19080 (full URL as in the template above)
- Retrieved (UTC): 2026-11-23T23:17:29Z
```
{"meta":{"total":2,"parameters":{"filters":"CERT:19080 AND (REPDTE:20230630 OR REPDTE:20260630)","fields":"CERT,REPDTE,LNRECONS,LNREMULT,LNRENROT,LNRENROW,RBCT1J,RBCRWAJ,EQTOT","limit":"10"},"index":{"name":"risview_20261116221646","createTimestamp":"2026-11-16T22:16:48Z"}},"data":[{"data":{"LNRENROT":1137411,"RBCRWAJ":13.992442766254035,"RBCT1J":393473,"REPDTE":"20230630","LNREMULT":72435,"CERT":19080,"LNRENROW":371756,"LNRECONS":289415,"EQTOT":423957,"ID":"19080_20230630"},"score":0},{"data":{"LNRENROT":1211542,"RBCRWAJ":16.9781501957153,"RBCT1J":465233,"REPDTE":"20260630","LNREMULT":95221,"CERT":19080,"LNRENROW":403120,"LNRECONS":280193,"EQTOT":495717,"ID":"19080_20260630"},"score":0}],"totals":{"count":2}}
```
#### Excerpt 14: CERT 19215 Benchmark Bank (flags: construction)
- Request: GET api.fdic.gov /banks/financials CERT 19215 (full URL as in the template above)
- Retrieved (UTC): 2026-11-23T23:17:29Z
```
{"meta":{"total":2,"parameters":{"filters":"CERT:19215 AND (REPDTE:20230630 OR REPDTE:20260630)","fields":"CERT,REPDTE,LNRECONS,LNREMULT,LNRENROT,LNRENROW,RBCT1J,RBCRWAJ,EQTOT","limit":"10"},"index":{"name":"risview_20261116221646","createTimestamp":"2026-11-16T22:16:48Z"}},"data":[{"data":{"LNRENROT":104243,"RBCRWAJ":15.585874799357946,"RBCT1J":106321,"REPDTE":"20230630","LNREMULT":24705,"CERT":19215,"LNRENROW":68375,"LNRECONS":129526,"EQTOT":106321,"ID":"19215_20230630"},"score":0},{"data":{"LNRENROT":177576,"RBCRWAJ":13.113613224447013,"RBCT1J":138410,"REPDTE":"20260630","LNREMULT":27137,"CERT":19215,"LNRENROW":81017,"LNRECONS":183621,"EQTOT":138410,"ID":"19215_20260630"},"score":0}],"totals":{"count":2}}
```
#### Excerpt 15: CERT 19559 TexasBank (flags: construction)
- Request: GET api.fdic.gov /banks/financials CERT 19559 (full URL as in the template above)
- Retrieved (UTC): 2026-11-23T23:17:29Z
```
{"meta":{"total":2,"parameters":{"filters":"CERT:19559 AND (REPDTE:20230630 OR REPDTE:20260630)","fields":"CERT,REPDTE,LNRECONS,LNREMULT,LNRENROT,LNRENROW,RBCT1J,RBCRWAJ,EQTOT","limit":"10"},"index":{"name":"risview_20261116221646","createTimestamp":"2026-11-16T22:16:48Z"}},"data":[{"data":{"LNRENROT":224814,"RBCRWAJ":16.582340436623554,"RBCT1J":211744,"REPDTE":"20230630","LNREMULT":33246,"CERT":19559,"LNRENROW":104120,"LNRECONS":315196,"EQTOT":207940,"ID":"19559_20230630"},"score":0},{"data":{"LNRENROT":254452,"RBCRWAJ":18.6418458311484,"RBCT1J":315706,"REPDTE":"20260630","LNREMULT":69106,"CERT":19559,"LNRENROW":125808,"LNRECONS":431280,"EQTOT":313634,"ID":"19559_20260630"},"score":0}],"totals":{"count":2}}
```
#### Excerpt 16: CERT 20231 Pinnacle Bank (flags: construction, CRE)
- Request: GET api.fdic.gov /banks/financials CERT 20231 (full URL as in the template above)
- Retrieved (UTC): 2026-11-23T23:17:30Z
```
{"meta":{"total":2,"parameters":{"filters":"CERT:20231 AND (REPDTE:20230630 OR REPDTE:20260630)","fields":"CERT,REPDTE,LNRECONS,LNREMULT,LNRENROT,LNRENROW,RBCT1J,RBCRWAJ,EQTOT","limit":"10"},"index":{"name":"risview_20261116221646","createTimestamp":"2026-11-16T22:16:48Z"}},"data":[{"data":{"LNRENROT":527058,"RBCRWAJ":14.510096825436575,"RBCT1J":249006,"REPDTE":"20230630","LNREMULT":59578,"CERT":20231,"LNRENROW":233441,"LNRECONS":315341,"EQTOT":288203,"ID":"20231_20230630"},"score":0},{"data":{"LNRENROT":542588,"RBCRWAJ":15.18664564639286,"RBCT1J":289433,"REPDTE":"20260630","LNREMULT":142050,"CERT":20231,"LNRENROW":257397,"LNRECONS":414467,"EQTOT":359464,"ID":"20231_20260630"},"score":0}],"totals":{"count":2}}
```
#### Excerpt 17: CERT 20845 Wallis Bank (flags: construction, CRE)
- Request: GET api.fdic.gov /banks/financials CERT 20845 (full URL as in the template above)
- Retrieved (UTC): 2026-11-23T23:17:31Z
```
{"meta":{"total":2,"parameters":{"filters":"CERT:20845 AND (REPDTE:20230630 OR REPDTE:20260630)","fields":"CERT,REPDTE,LNRECONS,LNREMULT,LNRENROT,LNRENROW,RBCT1J,RBCRWAJ,EQTOT","limit":"10"},"index":{"name":"risview_20261116221646","createTimestamp":"2026-11-16T22:16:48Z"}},"data":[{"data":{"LNRENROT":291089,"RBCRWAJ":12.50657417663418,"RBCT1J":117599,"REPDTE":"20230630","LNREMULT":24612,"CERT":20845,"LNRENROW":310358,"LNRECONS":192796,"EQTOT":120455,"ID":"20845_20230630"},"score":0},{"data":{"LNRENROT":405148,"RBCRWAJ":0,"RBCT1J":136695,"REPDTE":"20260630","LNREMULT":2449,"CERT":20845,"LNRENROW":350373,"LNRECONS":165781,"EQTOT":137828,"ID":"20845_20260630"},"score":0}],"totals":{"count":2}}
```
#### Excerpt 18: CERT 22373 American National Bank & Trust (flags: construction, CRE)
- Request: GET api.fdic.gov /banks/financials CERT 22373 (full URL as in the template above)
- Retrieved (UTC): 2026-11-23T23:17:31Z
```
{"meta":{"total":2,"parameters":{"filters":"CERT:22373 AND (REPDTE:20230630 OR REPDTE:20260630)","fields":"CERT,REPDTE,LNRECONS,LNREMULT,LNRENROT,LNRENROW,RBCT1J,RBCRWAJ,EQTOT","limit":"10"},"index":{"name":"risview_20261116221646","createTimestamp":"2026-11-16T22:16:48Z"}},"data":[{"data":{"LNRENROT":599082,"RBCRWAJ":13.313532557895144,"RBCT1J":196286,"REPDTE":"20230630","LNREMULT":52317,"CERT":22373,"LNRENROW":161321,"LNRECONS":203716,"EQTOT":192828,"ID":"22373_20230630"},"score":0},{"data":{"LNRENROT":709481,"RBCRWAJ":13.76699824968518,"RBCT1J":255839,"REPDTE":"20260630","LNREMULT":78139,"CERT":22373,"LNRENROW":180304,"LNRECONS":290892,"EQTOT":257506,"ID":"22373_20260630"},"score":0}],"totals":{"count":2}}
```
#### Excerpt 19: CERT 22396 Central National Bank (flags: construction, CRE)
- Request: GET api.fdic.gov /banks/financials CERT 22396 (full URL as in the template above)
- Retrieved (UTC): 2026-11-23T23:17:31Z
```
{"meta":{"total":2,"parameters":{"filters":"CERT:22396 AND (REPDTE:20230630 OR REPDTE:20260630)","fields":"CERT,REPDTE,LNRECONS,LNREMULT,LNRENROT,LNRENROW,RBCT1J,RBCRWAJ,EQTOT","limit":"10"},"index":{"name":"risview_20261116221646","createTimestamp":"2026-11-16T22:16:48Z"}},"data":[{"data":{"LNRENROT":154823,"RBCRWAJ":14.053069753411265,"RBCT1J":116286,"REPDTE":"20230630","LNREMULT":22457,"CERT":22396,"LNRENROW":83719,"LNRECONS":158071,"EQTOT":98911,"ID":"22396_20230630"},"score":0},{"data":{"LNRENROT":246975,"RBCRWAJ":13.796223720192993,"RBCT1J":144045,"REPDTE":"20260630","LNREMULT":14373,"CERT":22396,"LNRENROW":122833,"LNRECONS":172279,"EQTOT":133669,"ID":"22396_20260630"},"score":0}],"totals":{"count":2}}
```
#### Excerpt 20: CERT 23799 Texas First Bank (flags: construction)
- Request: GET api.fdic.gov /banks/financials CERT 23799 (full URL as in the template above)
- Retrieved (UTC): 2026-11-23T23:17:33Z
```
{"meta":{"total":2,"parameters":{"filters":"CERT:23799 AND (REPDTE:20230630 OR REPDTE:20260630)","fields":"CERT,REPDTE,LNRECONS,LNREMULT,LNRENROT,LNRENROW,RBCT1J,RBCRWAJ,EQTOT","limit":"10"},"index":{"name":"risview_20261116221646","createTimestamp":"2026-11-16T22:16:48Z"}},"data":[{"data":{"LNRENROT":156101,"RBCRWAJ":15.595871254384166,"RBCT1J":201207,"REPDTE":"20230630","LNREMULT":15754,"CERT":23799,"LNRENROW":297288,"LNRECONS":180233,"EQTOT":175909,"ID":"23799_20230630"},"score":0},{"data":{"LNRENROT":272804,"RBCRWAJ":0,"RBCT1J":235120,"REPDTE":"20260630","LNREMULT":14313,"CERT":23799,"LNRENROW":324510,"LNRECONS":293745,"EQTOT":228055,"ID":"23799_20260630"},"score":0}],"totals":{"count":2}}
```
#### Excerpt 21: CERT 25886 Rio Bank (flags: construction)
- Request: GET api.fdic.gov /banks/financials CERT 25886 (full URL as in the template above)
- Retrieved (UTC): 2026-11-23T23:17:35Z
```
{"meta":{"total":2,"parameters":{"filters":"CERT:25886 AND (REPDTE:20230630 OR REPDTE:20260630)","fields":"CERT,REPDTE,LNRECONS,LNREMULT,LNRENROT,LNRENROW,RBCT1J,RBCRWAJ,EQTOT","limit":"10"},"index":{"name":"risview_20261116221646","createTimestamp":"2026-11-16T22:16:48Z"}},"data":[{"data":{"LNRENROT":91586,"RBCRWAJ":16.768828912335678,"RBCT1J":81071,"REPDTE":"20230630","LNREMULT":12759,"CERT":25886,"LNRENROW":58606,"LNRECONS":45568,"EQTOT":63126,"ID":"25886_20230630"},"score":0},{"data":{"LNRENROT":178093,"RBCRWAJ":14.870687743061204,"RBCT1J":139432,"REPDTE":"20260630","LNREMULT":37242,"CERT":25886,"LNRENROW":131450,"LNRECONS":148979,"EQTOT":150733,"ID":"25886_20260630"},"score":0}],"totals":{"count":2}}
```
#### Excerpt 22: CERT 26223 Golden Bank, National Association (flags: CRE)
- Request: GET api.fdic.gov /banks/financials CERT 26223 (full URL as in the template above)
- Retrieved (UTC): 2026-11-23T23:17:35Z
```
{"meta":{"total":2,"parameters":{"filters":"CERT:26223 AND (REPDTE:20230630 OR REPDTE:20260630)","fields":"CERT,REPDTE,LNRECONS,LNREMULT,LNRENROT,LNRENROW,RBCT1J,RBCRWAJ,EQTOT","limit":"10"},"index":{"name":"risview_20261116221646","createTimestamp":"2026-11-16T22:16:48Z"}},"data":[{"data":{"LNRENROT":580052,"RBCRWAJ":15.694126152670924,"RBCT1J":212454,"REPDTE":"20230630","LNREMULT":47556,"CERT":26223,"LNRENROW":413231,"LNRECONS":115025,"EQTOT":208936,"ID":"26223_20230630"},"score":0},{"data":{"LNRENROT":801859,"RBCRWAJ":16.84865885984296,"RBCT1J":311278,"REPDTE":"20260630","LNREMULT":75164,"CERT":26223,"LNRENROW":601378,"LNRECONS":221197,"EQTOT":308756,"ID":"26223_20260630"},"score":0}],"totals":{"count":2}}
```
#### Excerpt 23: CERT 26856 Falcon International Bank (flags: construction, CRE)
- Request: GET api.fdic.gov /banks/financials CERT 26856 (full URL as in the template above)
- Retrieved (UTC): 2026-11-23T23:17:36Z
```
{"meta":{"total":2,"parameters":{"filters":"CERT:26856 AND (REPDTE:20230630 OR REPDTE:20260630)","fields":"CERT,REPDTE,LNRECONS,LNREMULT,LNRENROT,LNRENROW,RBCT1J,RBCRWAJ,EQTOT","limit":"10"},"index":{"name":"risview_20261116221646","createTimestamp":"2026-11-16T22:16:48Z"}},"data":[{"data":{"LNRENROT":341897,"RBCRWAJ":19.520835906080126,"RBCT1J":233688,"REPDTE":"20230630","LNREMULT":60810,"CERT":26856,"LNRENROW":175503,"LNRECONS":255812,"EQTOT":192438,"ID":"26856_20230630"},"score":0},{"data":{"LNRENROT":440982,"RBCRWAJ":20.95322882000298,"RBCT1J":311903,"REPDTE":"20260630","LNREMULT":119849,"CERT":26856,"LNRENROW":218924,"LNRECONS":378223,"EQTOT":275291,"ID":"26856_20260630"},"score":0}],"totals":{"count":2}}
```
#### Excerpt 24: CERT 26906 Texas Regional Bank (flags: construction, CRE)
- Request: GET api.fdic.gov /banks/financials CERT 26906 (full URL as in the template above)
- Retrieved (UTC): 2026-11-23T23:17:36Z
```
{"meta":{"total":2,"parameters":{"filters":"CERT:26906 AND (REPDTE:20230630 OR REPDTE:20260630)","fields":"CERT,REPDTE,LNRECONS,LNREMULT,LNRENROT,LNRENROW,RBCT1J,RBCRWAJ,EQTOT","limit":"10"},"index":{"name":"risview_20261116221646","createTimestamp":"2026-11-16T22:16:48Z"}},"data":[{"data":{"LNRENROT":262174,"RBCRWAJ":12.884704445941395,"RBCT1J":229977,"REPDTE":"20230630","LNREMULT":81555,"CERT":26906,"LNRENROW":247797,"LNRECONS":356203,"EQTOT":193071,"ID":"26906_20230630"},"score":0},{"data":{"LNRENROT":400859,"RBCRWAJ":13.080879760624113,"RBCT1J":266733,"REPDTE":"20260630","LNREMULT":126764,"CERT":26906,"LNRENROW":279167,"LNRECONS":325219,"EQTOT":271206,"ID":"26906_20260630"},"score":0}],"totals":{"count":2}}
```
#### Excerpt 25: CERT 27074 State Bank of Texas (flags: CRE)
- Request: GET api.fdic.gov /banks/financials CERT 27074 (full URL as in the template above)
- Retrieved (UTC): 2026-11-23T23:17:37Z
```
{"meta":{"total":2,"parameters":{"filters":"CERT:27074 AND (REPDTE:20230630 OR REPDTE:20260630)","fields":"CERT,REPDTE,LNRECONS,LNREMULT,LNRENROT,LNRENROW,RBCT1J,RBCRWAJ,EQTOT","limit":"10"},"index":{"name":"risview_20261116221646","createTimestamp":"2026-11-16T22:16:48Z"}},"data":[{"data":{"LNRENROT":1539031,"RBCRWAJ":0,"RBCT1J":308367,"REPDTE":"20230630","LNREMULT":1361,"CERT":27074,"LNRENROW":16572,"LNRECONS":193069,"EQTOT":303178,"ID":"27074_20230630"},"score":0},{"data":{"LNRENROT":1923769,"RBCRWAJ":0,"RBCT1J":427587,"REPDTE":"20260630","LNREMULT":0,"CERT":27074,"LNRENROW":1821,"LNRECONS":144786,"EQTOT":424986,"ID":"27074_20260630"},"score":0}],"totals":{"count":2}}
```
#### Excerpt 26: CERT 32941 WestStar Bank (flags: CRE)
- Request: GET api.fdic.gov /banks/financials CERT 32941 (full URL as in the template above)
- Retrieved (UTC): 2026-11-23T23:17:38Z
```
{"meta":{"total":2,"parameters":{"filters":"CERT:32941 AND (REPDTE:20230630 OR REPDTE:20260630)","fields":"CERT,REPDTE,LNRECONS,LNREMULT,LNRENROT,LNRENROW,RBCT1J,RBCRWAJ,EQTOT","limit":"10"},"index":{"name":"risview_20261116221646","createTimestamp":"2026-11-16T22:16:48Z"}},"data":[{"data":{"LNRENROT":647765,"RBCRWAJ":13.01408735371991,"RBCT1J":299607,"REPDTE":"20230630","LNREMULT":118368,"CERT":32941,"LNRENROW":251256,"LNRECONS":402245,"EQTOT":247177,"ID":"32941_20230630"},"score":0},{"data":{"LNRENROT":857119,"RBCRWAJ":14.069087184838299,"RBCT1J":394502,"REPDTE":"20260630","LNREMULT":266269,"CERT":32941,"LNRENROW":373518,"LNRECONS":331693,"EQTOT":383432,"ID":"32941_20260630"},"score":0}],"totals":{"count":2}}
```
#### Excerpt 27: CERT 34319 Southwestern National Bank (flags: CRE)
- Request: GET api.fdic.gov /banks/financials CERT 34319 (full URL as in the template above)
- Retrieved (UTC): 2026-11-23T23:17:38Z
```
{"meta":{"total":2,"parameters":{"filters":"CERT:34319 AND (REPDTE:20230630 OR REPDTE:20260630)","fields":"CERT,REPDTE,LNRECONS,LNREMULT,LNRENROT,LNRENROW,RBCT1J,RBCRWAJ,EQTOT","limit":"10"},"index":{"name":"risview_20261116221646","createTimestamp":"2026-11-16T22:16:48Z"}},"data":[{"data":{"LNRENROT":390916,"RBCRWAJ":15.36391536803951,"RBCT1J":123187,"REPDTE":"20230630","LNREMULT":22425,"CERT":34319,"LNRENROW":269224,"LNRECONS":77359,"EQTOT":120579,"ID":"34319_20230630"},"score":0},{"data":{"LNRENROT":470077,"RBCRWAJ":15.787595491030576,"RBCT1J":171099,"REPDTE":"20260630","LNREMULT":56371,"CERT":34319,"LNRENROW":406793,"LNRECONS":69257,"EQTOT":169779,"ID":"34319_20260630"},"score":0}],"totals":{"count":2}}
```
#### Excerpt 28: CERT 34885 Susser Bank (flags: construction)
- Request: GET api.fdic.gov /banks/financials CERT 34885 (full URL as in the template above)
- Retrieved (UTC): 2026-11-23T23:17:39Z
```
{"meta":{"total":2,"parameters":{"filters":"CERT:34885 AND (REPDTE:20230630 OR REPDTE:20260630)","fields":"CERT,REPDTE,LNRECONS,LNREMULT,LNRENROT,LNRENROW,RBCT1J,RBCRWAJ,EQTOT","limit":"10"},"index":{"name":"risview_20261116221646","createTimestamp":"2026-11-16T22:16:48Z"}},"data":[{"data":{"LNRENROT":284595,"RBCRWAJ":11.639317441409894,"RBCT1J":184247,"REPDTE":"20230630","LNREMULT":57450,"CERT":34885,"LNRENROW":154830,"LNRECONS":289725,"EQTOT":205566,"ID":"34885_20230630"},"score":0},{"data":{"LNRENROT":406567,"RBCRWAJ":12.898717025607612,"RBCT1J":280664,"REPDTE":"20260630","LNREMULT":51381,"CERT":34885,"LNRENROW":205151,"LNRECONS":296796,"EQTOT":306700,"ID":"34885_20260630"},"score":0}],"totals":{"count":2}}
```
#### Excerpt 29: CERT 58716 Third Coast Bank (flags: construction)
- Request: GET api.fdic.gov /banks/financials CERT 58716 (full URL as in the template above)
- Retrieved (UTC): 2026-11-23T23:17:41Z
```
{"meta":{"total":2,"parameters":{"filters":"CERT:58716 AND (REPDTE:20230630 OR REPDTE:20260630)","fields":"CERT,REPDTE,LNRECONS,LNREMULT,LNRENROT,LNRENROW,RBCT1J,RBCRWAJ,EQTOT","limit":"10"},"index":{"name":"risview_20261116221646","createTimestamp":"2026-11-16T22:16:48Z"}},"data":[{"data":{"LNRENROT":547120,"RBCRWAJ":12.989255888475268,"RBCT1J":485175,"REPDTE":"20230630","LNREMULT":41280,"CERT":58716,"LNRENROW":513934,"LNRECONS":595601,"EQTOT":502889,"ID":"58716_20230630"},"score":0},{"data":{"LNRENROT":932147,"RBCRWAJ":12.914733172543555,"RBCT1J":746567,"REPDTE":"20260630","LNREMULT":59017,"CERT":58716,"LNRENROW":583989,"LNRECONS":887805,"EQTOT":806644,"ID":"58716_20260630"},"score":0}],"totals":{"count":2}}
```

## SOURCES

- FDIC BankFind institutions: https://api.fdic.gov/banks/institutions (host api.fdic.gov, /banks/institutions)
- FDIC BankFind financials: https://api.fdic.gov/banks/financials (host api.fdic.gov, /banks/financials)
