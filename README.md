# First Stage Landing Prediction

![](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMDeveloperSkillsNetwork-DS0701EN-SkillsNetwork/api/Images/landing_1.gif)
   
## Data mining
'|   FlightNumber | Date       | BoosterVersion   |   PayloadMass | Orbit   | LaunchSite      | Outcome     |   Flights | GridFins   | Reused   | Legs   | LandingPad               |   Block |   ReusedCount | Serial   |   Longitude |   Latitude |\n|---------------:|:-----------|:-----------------|--------------:|:--------|:----------------|:------------|----------:|:-----------|:---------|:-------|:-------------------------|--------:|--------------:|:---------|------------:|-----------:|\n|              1 | 2006-03-24 | Falcon 1         |         20    | LEO     | Kwajalein Atoll | None None   |         1 | False      | False    | False  |                          |     nan |             0 | Merlin1A |    167.743  |    9.04772 |\n|              2 | 2007-03-21 | Falcon 1         |        nan    | LEO     | Kwajalein Atoll | None None   |         1 | False      | False    | False  |                          |     nan |             0 | Merlin2A |    167.743  |    9.04772 |\n|              4 | 2008-09-28 | Falcon 1         |        165    | LEO     | Kwajalein Atoll | None None   |         1 | False      | False    | False  |                          |     nan |             0 | Merlin2C |    167.743  |    9.04772 |\n|              5 | 2009-07-13 | Falcon 1         |        200    | LEO     | Kwajalein Atoll | None None   |         1 | False      | False    | False  |                          |     nan |             0 | Merlin3C |    167.743  |    9.04772 |\n|              6 | 2010-06-04 | Falcon 9         |        nan    | LEO     | CCSFS SLC 40    | None None   |         1 | False      | False    | False  |                          |       1 |             0 | B0003    |    -80.5774 |   28.5619  |\n|              8 | 2012-05-22 | Falcon 9         |        525    | LEO     | CCSFS SLC 40    | None None   |         1 | False      | False    | False  |                          |       1 |             0 | B0005    |    -80.5774 |   28.5619  |\n|             10 | 2013-03-01 | Falcon 9         |        677    | ISS     | CCSFS SLC 40    | None None   |         1 | False      | False    | False  |                          |       1 |             0 | B0007    |    -80.5774 |   28.5619  |\n|             11 | 2013-09-29 | Falcon 9         |        500    | PO      | VAFB SLC 4E     | False Ocean |         1 | False      | False    | False  |                          |       1 |             0 | B1003    |   -120.611  |   34.6321  |\n|             12 | 2013-12-03 | Falcon 9         |       3170    | GTO     | CCSFS SLC 40    | None None   |         1 | False      | False    | False  |                          |       1 |             0 | B1004    |    -80.5774 |   28.5619  |\n|             13 | 2014-01-06 | Falcon 9         |       3325    | GTO     | CCSFS SLC 40    | None None   |         1 | False      | False    | False  |                          |       1 |             0 | B1005    |    -80.5774 |   28.5619  |\n|             14 | 2014-04-18 | Falcon 9         |       2296    | ISS     | CCSFS SLC 40    | True Ocean  |         1 | False      | False    | True   |                          |       1 |             0 | B1006    |    -80.5774 |   28.5619  |\n|             15 | 2014-07-14 | Falcon 9         |       1316    | LEO     | CCSFS SLC 40    | True Ocean  |         1 | False      | False    | True   |                          |       1 |             0 | B1007    |    -80.5774 |   28.5619  |\n|             16 | 2014-08-05 | Falcon 9         |       4535    | GTO     | CCSFS SLC 40    | None None   |         1 | False      | False    | False  |                          |       1 |             0 | B1008    |    -80.5774 |   28.5619  |\n|             17 | 2014-09-07 | Falcon 9         |       4428    | GTO     | CCSFS SLC 40    | None None   |         1 | False      | False    | False  |                          |       1 |             0 | B1011    |    -80.5774 |   28.5619  |\n|             18 | 2014-09-21 | Falcon 9         |       2216    | ISS     | CCSFS SLC 40    | False Ocean |         1 | False      | False    | False  |                          |       1 |             0 | B1010    |    -80.5774 |   28.5619  |\n|             19 | 2015-01-10 | Falcon 9         |       2395    | ISS     | CCSFS SLC 40    | False ASDS  |         1 | True       | False    | True   | 5e9e3032383ecb761634e7cb |       1 |             0 | B1012    |    -80.5774 |   28.5619  |\n|             20 | 2015-02-11 | Falcon 9         |        570    | ES-L1   | CCSFS SLC 40    | True Ocean  |         1 | True       | False    | True   |                          |       1 |             0 | B1013    |    -80.5774 |   28.5619  |\n|             22 | 2015-04-14 | Falcon 9         |       1898    | ISS     | CCSFS SLC 40    | False ASDS  |         1 | True       | False    | True   | 5e9e3032383ecb761634e7cb |       1 |             0 | B1015    |    -80.5774 |   28.5619  |\n|             23 | 2015-04-27 | Falcon 9         |       4707    | GTO     | CCSFS SLC 40    | None None   |         1 | False      | False    | False  |                          |       1 |             0 | B1016    |    -80.5774 |   28.5619  |\n|             24 | 2015-06-28 | Falcon 9         |       2477    | ISS     | CCSFS SLC 40    | None ASDS   |         1 | True       | False    | True   | 5e9e3032383ecb6bb234e7ca |       1 |             0 | B1018    |    -80.5774 |   28.5619  |\n|             25 | 2015-12-22 | Falcon 9         |       2034    | LEO     | CCSFS SLC 40    | True RTLS   |         1 | True       | False    | True   | 5e9e3032383ecb267a34e7c7 |       1 |             0 | B1019    |    -80.5774 |   28.5619  |\n|             26 | 2016-01-17 | Falcon 9         |        553    | PO      | VAFB SLC 4E     | False ASDS  |         1 | True       | False    | True   | 5e9e3033383ecbb9e534e7cc |       1 |             0 | B1017    |   -120.611  |   34.6321  |\n|             27 | 2016-03-04 | Falcon 9         |       5271    | GTO     | CCSFS SLC 40    | False ASDS  |         1 | True       | False    | True   | 5e9e3032383ecb6bb234e7ca |       1 |             0 | B1020    |    -80.5774 |   28.5619  |\n|             28 | 2016-04-08 | Falcon 9         |       3136    | ISS     | CCSFS SLC 40    | True ASDS   |         1 | True       | False    | True   | 5e9e3032383ecb6bb234e7ca |       2 |             1 | B1021    |    -80.5774 |   28.5619  |\n|             29 | 2016-05-06 | Falcon 9         |       4696    | GTO     | CCSFS SLC 40    | True ASDS   |         1 | True       | False    | True   | 5e9e3032383ecb6bb234e7ca |       2 |             0 | B1022    |    -80.5774 |   28.5619  |\n|             30 | 2016-05-27 | Falcon 9         |       3100    | GTO     | CCSFS SLC 40    | True ASDS   |         1 | True       | False    | True   | 5e9e3032383ecb6bb234e7ca |       2 |             1 | B1023    |    -80.5774 |   28.5619  |\n|             32 | 2016-07-18 | Falcon 9         |       2257    | ISS     | CCSFS SLC 40    | True RTLS   |         1 | True       | False    | True   | 5e9e3032383ecb267a34e7c7 |       2 |             1 | B1025    |    -80.5774 |   28.5619  |\n|             33 | 2016-08-14 | Falcon 9         |       4600    | GTO     | CCSFS SLC 40    | True ASDS   |         1 | True       | False    | True   | 5e9e3032383ecb6bb234e7ca |       2 |             0 | B1026    |    -80.5774 |   28.5619  |\n|             34 | 2016-09-01 | Falcon 9         |       5500    | GTO     | CCSFS SLC 40    | None ASDS   |         1 | True       | False    | True   | 5e9e3032383ecb6bb234e7ca |       3 |             0 | B1028    |    -80.5774 |   28.5619  |\n|             35 | 2017-01-14 | Falcon 9         |       9600    | PO      | VAFB SLC 4E     | True ASDS   |         1 | True       | False    | True   | 5e9e3033383ecbb9e534e7cc |       3 |             1 | B1029    |   -120.611  |   34.6321  |\n|             36 | 2017-02-19 | Falcon 9         |       2490    | ISS     | KSC LC 39A      | True RTLS   |         1 | True       | False    | True   | 5e9e3032383ecb267a34e7c7 |       3 |             1 | B1031    |    -80.604  |   28.6081  |\n|             37 | 2017-03-16 | Falcon 9         |       5600    | GTO     | KSC LC 39A      | None None   |         1 | False      | False    | False  |                          |       3 |             0 | B1030    |    -80.604  |   28.6081  |\n|             38 | 2017-03-30 | Falcon 9         |       5300    | GTO     | KSC LC 39A      | True ASDS   |         2 | True       | True     | True   | 5e9e3032383ecb6bb234e7ca |       2 |             1 | B1021    |    -80.604  |   28.6081  |\n|             39 | 2017-05-01 | Falcon 9         |        nan    | LEO     | KSC LC 39A      | True RTLS   |         1 | True       | False    | True   | 5e9e3032383ecb267a34e7c7 |       3 |             1 | B1032    |    -80.604  |   28.6081  |\n|             40 | 2017-05-15 | Falcon 9         |       6070    | GTO     | KSC LC 39A      | None None   |         1 | False      | False    | False  |                          |       3 |             0 | B1034    |    -80.604  |   28.6081  |\n|             41 | 2017-06-03 | Falcon 9         |       2708    | ISS     | KSC LC 39A      | True RTLS   |         1 | True       | False    | True   | 5e9e3032383ecb267a34e7c7 |       3 |             1 | B1035    |    -80.604  |   28.6081  |\n|             42 | 2017-06-23 | Falcon 9         |       3669    | GTO     | KSC LC 39A      | True ASDS   |         2 | True       | True     | True   | 5e9e3032383ecb6bb234e7ca |       3 |             1 | B1029    |    -80.604  |   28.6081  |\n|             43 | 2017-06-25 | Falcon 9         |       9600    | PO      | VAFB SLC 4E     | True ASDS   |         1 | True       | False    | True   | 5e9e3033383ecbb9e534e7cc |       3 |             1 | B1036    |   -120.611  |   34.6321  |\n|             44 | 2017-07-05 | Falcon 9         |       6761    | GTO     | KSC LC 39A      | None None   |         1 | False      | False    | False  |                          |       3 |             0 | B1037    |    -80.604  |   28.6081  |\n|             45 | 2017-08-14 | Falcon 9         |       2910    | ISS     | KSC LC 39A      | True RTLS   |         1 | True       | False    | True   | 5e9e3032383ecb267a34e7c7 |       4 |             1 | B1039    |    -80.604  |   28.6081  |\n|             46 | 2017-08-24 | Falcon 9         |        475    | SSO     | VAFB SLC 4E     | True ASDS   |         1 | True       | False    | True   | 5e9e3033383ecbb9e534e7cc |       3 |             1 | B1038    |   -120.611  |   34.6321  |\n|             47 | 2017-09-07 | Falcon 9         |       4990    | LEO     | KSC LC 39A      | True RTLS   |         1 | True       | False    | True   | 5e9e3032383ecb267a34e7c7 |       4 |             1 | B1040    |    -80.604  |   28.6081  |\n|             48 | 2017-10-09 | Falcon 9         |       9600    | PO      | VAFB SLC 4E     | True ASDS   |         1 | True       | False    | True   | 5e9e3033383ecbb9e534e7cc |       4 |             1 | B1041    |   -120.611  |   34.6321  |\n|             49 | 2017-10-11 | Falcon 9         |       5200    | GTO     | KSC LC 39A      | True ASDS   |         2 | True       | True     | True   | 5e9e3032383ecb6bb234e7ca |       3 |             1 | B1031    |    -80.604  |   28.6081  |\n|             50 | 2017-10-30 | Falcon 9         |       3700    | GTO     | KSC LC 39A      | True ASDS   |         1 | True       | False    | True   | 5e9e3032383ecb6bb234e7ca |       4 |             0 | B1042    |    -80.604  |   28.6081  |\n|             51 | 2017-12-15 | Falcon 9         |       2205    | ISS     | CCSFS SLC 40    | True RTLS   |         2 | True       | True     | True   | 5e9e3032383ecb267a34e7c7 |       3 |             1 | B1035    |    -80.5774 |   28.5619  |\n|             52 | 2017-12-23 | Falcon 9         |       9600    | PO      | VAFB SLC 4E     | True Ocean  |         2 | True       | True     | False  |                          |       3 |             1 | B1036    |   -120.611  |   34.6321  |\n|             53 | 2018-01-08 | Falcon 9         |        nan    | LEO     | CCSFS SLC 40    | True RTLS   |         1 | True       | False    | True   | 5e9e3032383ecb267a34e7c7 |       4 |             1 | B1043    |    -80.5774 |   28.5619  |\n|             54 | 2018-01-31 | Falcon 9         |       4230    | GTO     | CCSFS SLC 40    | True Ocean  |         2 | True       | True     | True   |                          |       3 |             1 | B1032    |    -80.5774 |   28.5619  |\n|             57 | 2018-03-06 | Falcon 9         |       6092    | GTO     | CCSFS SLC 40    | None None   |         1 | True       | False    | True   |                          |       4 |             0 | B1044    |    -80.5774 |   28.5619  |\n|             58 | 2018-03-30 | Falcon 9         |       9600    | PO      | VAFB SLC 4E     | None None   |         2 | True       | True     | True   |                          |       4 |             1 | B1041    |   -120.611  |   34.6321  |\n|             59 | 2018-04-02 | Falcon 9         |       2760    | ISS     | CCSFS SLC 40    | None None   |         2 | True       | True     | True   |                          |       4 |             1 | B1039    |    -80.5774 |   28.5619  |\n|             60 | 2018-04-18 | Falcon 9         |        350    | HEO     | CCSFS SLC 40    | True ASDS   |         1 | True       | False    | True   | 5e9e3032383ecb6bb234e7ca |       4 |             1 | B1045    |    -80.5774 |   28.5619  |\n|             61 | 2018-05-11 | Falcon 9         |       3750    | GTO     | KSC LC 39A      | True ASDS   |         1 | True       | False    | True   | 5e9e3032383ecb6bb234e7ca |       5 |             3 | B1046    |    -80.604  |   28.6081  |\n|             63 | 2018-06-04 | Falcon 9         |       5383.85 | GTO     | CCSFS SLC 40    | None None   |         2 | False      | True     | False  |                          |       4 |             1 | B1040    |    -80.5774 |   28.5619  |\n|             64 | 2018-06-29 | Falcon 9         |       2410    | ISS     | CCSFS SLC 40    | None None   |         2 | False      | True     | False  |                          |       4 |             1 | B1045    |    -80.5774 |   28.5619  |\n|             65 | 2018-07-22 | Falcon 9         |       7076    | GTO     | CCSFS SLC 40    | True ASDS   |         1 | True       | False    | True   | 5e9e3032383ecb6bb234e7ca |       5 |             2 | B1047    |    -80.5774 |   28.5619  |\n|             66 | 2018-07-25 | Falcon 9         |       9600    | PO      | VAFB SLC 4E     | True ASDS   |         1 | True       | False    | True   | 5e9e3033383ecbb9e534e7cc |       5 |             4 | B1048    |   -120.611  |   34.6321  |\n|             67 | 2018-08-07 | Falcon 9         |       5800    | GTO     | CCSFS SLC 40    | True ASDS   |         2 | True       | True     | True   | 5e9e3032383ecb6bb234e7ca |       5 |             3 | B1046    |    -80.5774 |   28.5619  |\n|             68 | 2018-09-10 | Falcon 9         |       7060    | GTO     | CCSFS SLC 40    | True ASDS   |         1 | True       | False    | True   | 5e9e3032383ecb6bb234e7ca |       5 |             9 | B1049    |    -80.5774 |   28.5619  |\n|             69 | 2018-10-08 | Falcon 9         |       2800    | SSO     | VAFB SLC 4E     | True RTLS   |         2 | True       | True     | True   | 5e9e3032383ecb554034e7c9 |       5 |             4 | B1048    |   -120.611  |   34.6321  |\n|             70 | 2018-11-15 | Falcon 9         |       3000    | GTO     | KSC LC 39A      | True ASDS   |         2 | True       | True     | True   | 5e9e3032383ecb6bb234e7ca |       5 |             2 | B1047    |    -80.604  |   28.6081  |\n|             71 | 2018-12-03 | Falcon 9         |       4000    | SSO     | VAFB SLC 4E     | True ASDS   |         3 | True       | True     | True   | 5e9e3033383ecbb9e534e7cc |       5 |             3 | B1046    |   -120.611  |   34.6321  |\n|             72 | 2018-12-05 | Falcon 9         |       2573    | ISS     | CCSFS SLC 40    | False RTLS  |         1 | True       | False    | True   | 5e9e3032383ecb267a34e7c7 |       5 |             0 | B1050    |    -80.5774 |   28.5619  |\n|             73 | 2018-12-23 | Falcon 9         |       4400    | MEO     | CCSFS SLC 40    | None None   |         1 | False      | False    | False  |                          |       5 |             0 | B1054    |    -80.5774 |   28.5619  |\n|             74 | 2019-01-11 | Falcon 9         |       9600    | PO      | VAFB SLC 4E     | True ASDS   |         2 | True       | True     | True   | 5e9e3033383ecbb9e534e7cc |       5 |             9 | B1049    |   -120.611  |   34.6321  |\n|             76 | 2019-03-02 | Falcon 9         |      12259    | ISS     | KSC LC 39A      | True ASDS   |         1 | True       | False    | True   | 5e9e3032383ecb6bb234e7ca |       5 |            12 | B1051    |    -80.604  |   28.6081  |\n|             78 | 2019-05-04 | Falcon 9         |       2482    | ISS     | CCSFS SLC 40    | True ASDS   |         1 | True       | False    | True   | 5e9e3032383ecb6bb234e7ca |       5 |             3 | B1056    |    -80.5774 |   28.5619  |\n|             79 | 2019-05-24 | Falcon 9         |      13200    | VLEO    | CCSFS SLC 40    | True ASDS   |         3 | True       | True     | True   | 5e9e3032383ecb6bb234e7ca |       5 |             9 | B1049    |    -80.5774 |   28.5619  |\n|             80 | 2019-06-12 | Falcon 9         |       1425    | SSO     | VAFB SLC 4E     | True RTLS   |         2 | True       | True     | True   | 5e9e3032383ecb554034e7c9 |       5 |            12 | B1051    |   -120.611  |   34.6321  |\n|             82 | 2019-07-25 | Falcon 9         |       2227.7  | ISS     | CCSFS SLC 40    | True RTLS   |         2 | True       | True     | True   | 5e9e3032383ecb267a34e7c7 |       5 |             3 | B1056    |    -80.5774 |   28.5619  |\n|             83 | 2019-08-06 | Falcon 9         |       6500    | GTO     | CCSFS SLC 40    | None None   |         3 | False      | True     | False  |                          |       5 |             2 | B1047    |    -80.5774 |   28.5619  |\n|             84 | 2019-11-11 | Falcon 9         |      15600    | VLEO    | CCSFS SLC 40    | True ASDS   |         4 | True       | True     | True   | 5e9e3032383ecb6bb234e7ca |       5 |             4 | B1048    |    -80.5774 |   28.5619  |\n|             85 | 2019-12-05 | Falcon 9         |       5000    | ISS     | CCSFS SLC 40    | True ASDS   |         1 | True       | False    | True   | 5e9e3032383ecb6bb234e7ca |       5 |             5 | B1059    |    -80.5774 |   28.5619  |\n|             86 | 2019-12-17 | Falcon 9         |       6800    | GTO     | CCSFS SLC 40    | True ASDS   |         3 | True       | True     | True   | 5e9e3032383ecb6bb234e7ca |       5 |             3 | B1056    |    -80.5774 |   28.5619  |\n|             87 | 2020-01-07 | Falcon 9         |      15600    | VLEO    | CCSFS SLC 40    | True ASDS   |         4 | True       | True     | True   | 5e9e3032383ecb6bb234e7ca |       5 |             9 | B1049    |    -80.5774 |   28.5619  |\n|             88 | 2020-01-19 | Falcon 9         |        nan    | SO      | KSC LC 39A      | None None   |         4 | False      | True     | False  |                          |       5 |             3 | B1046    |    -80.604  |   28.6081  |\n|             89 | 2020-01-29 | Falcon 9         |      15600    | VLEO    | CCSFS SLC 40    | True ASDS   |         3 | True       | True     | True   | 5e9e3032383ecb6bb234e7ca |       5 |            12 | B1051    |    -80.5774 |   28.5619  |\n|             90 | 2020-02-17 | Falcon 9         |      15600    | VLEO    | CCSFS SLC 40    | False ASDS  |         4 | True       | True     | True   | 5e9e3032383ecb6bb234e7ca |       5 |             3 | B1056    |    -80.5774 |   28.5619  |\n|             91 | 2020-03-07 | Falcon 9         |       1977    | ISS     | CCSFS SLC 40    | True RTLS   |         2 | True       | True     | True   | 5e9e3032383ecb267a34e7c7 |       5 |             5 | B1059    |    -80.5774 |   28.5619  |\n|             92 | 2020-03-18 | Falcon 9         |      15600    | VLEO    | KSC LC 39A      | False ASDS  |         5 | True       | True     | True   | 5e9e3032383ecb6bb234e7ca |       5 |             4 | B1048    |    -80.604  |   28.6081  |\n|             93 | 2020-04-22 | Falcon 9         |      15600    | VLEO    | KSC LC 39A      | True ASDS   |         4 | True       | True     | True   | 5e9e3032383ecb6bb234e7ca |       5 |            12 | B1051    |    -80.604  |   28.6081  |\n|             94 | 2020-05-30 | Falcon 9         |       9525    | ISS     | KSC LC 39A      | True ASDS   |         1 | True       | False    | True   | 5e9e3032383ecb6bb234e7ca |       5 |            13 | B1058    |    -80.604  |   28.6081  |\n|             95 | 2020-06-04 | Falcon 9         |      15600    | VLEO    | CCSFS SLC 40    | True ASDS   |         5 | True       | True     | True   | 5e9e3033383ecbb9e534e7cc |       5 |             9 | B1049    |    -80.5774 |   28.5619  |\n|             96 | 2020-06-13 | Falcon 9         |      15600    | VLEO    | CCSFS SLC 40    | True ASDS   |         3 | True       | True     | True   | 5e9e3032383ecb6bb234e7ca |       5 |             5 | B1059    |    -80.5774 |   28.5619  |\n|             97 | 2020-06-30 | Falcon 9         |       3880    | MEO     | CCSFS SLC 40    | True ASDS   |         1 | True       | False    | True   | 5e9e3033383ecbb9e534e7cc |       5 |            12 | B1060    |    -80.5774 |   28.5619  |\n|             98 | 2020-07-20 | Falcon 9         |        nan    | GEO     | CCSFS SLC 40    | True ASDS   |         2 | True       | True     | True   | 5e9e3033383ecbb9e534e7cc |       5 |            13 | B1058    |    -80.5774 |   28.5619  |\n|            100 | 2020-08-18 | Falcon 9         |      15600    | VLEO    | CCSFS SLC 40    | True ASDS   |         6 | True       | True     | True   | 5e9e3032383ecb6bb234e7ca |       5 |             9 | B1049    |    -80.5774 |   28.5619  |\n|            101 | 2020-08-30 | Falcon 9         |       1600    | SSO     | CCSFS SLC 40    | True RTLS   |         4 | True       | True     | True   | 5e9e3032383ecb267a34e7c7 |       5 |             5 | B1059    |    -80.5774 |   28.5619  |\n|            102 | 2020-09-03 | Falcon 9         |      15600    | VLEO    | KSC LC 39A      | True ASDS   |         2 | True       | True     | True   | 5e9e3032383ecb6bb234e7ca |       5 |            12 | B1060    |    -80.604  |   28.6081  |\n|            103 | 2020-10-06 | Falcon 9         |      15600    | VLEO    | KSC LC 39A      | True ASDS   |         3 | True       | True     | True   | 5e9e3032383ecb6bb234e7ca |       5 |            13 | B1058    |    -80.604  |   28.6081  |\n|            104 | 2020-10-18 | Falcon 9         |      15600    | VLEO    | KSC LC 39A      | True ASDS   |         6 | True       | True     | True   | 5e9e3032383ecb6bb234e7ca |       5 |            12 | B1051    |    -80.604  |   28.6081  |\n|            105 | 2020-10-24 | Falcon 9         |      15600    | VLEO    | CCSFS SLC 40    | True ASDS   |         3 | True       | True     | True   | 5e9e3033383ecbb9e534e7cc |       5 |            12 | B1060    |    -80.5774 |   28.5619  |\n|            106 | 2020-11-05 | Falcon 9         |       3681    | MEO     | CCSFS SLC 40    | True ASDS   |         1 | True       | False    | True   | 5e9e3032383ecb6bb234e7ca |       5 |             8 | B1062    |    -80.5774 |   28.5619  |'
