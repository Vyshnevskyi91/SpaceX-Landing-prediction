# First Stage Landing Prediction

![](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMDeveloperSkillsNetwork-DS0701EN-SkillsNetwork/api/Images/landing_1.gif)
   
## Data mining our Data set
|   FlightNumber | Date       | BoosterVersion   |   PayloadMass | Orbit   | LaunchSite   | Outcome     |   Flights | GridFins   | Reused   | Legs   | LandingPad               |   Block |   ReusedCount | Serial   |   Longitude |   Latitude |
|---------------:|:-----------|:-----------------|--------------:|:--------|:-------------|:------------|----------:|:-----------|:---------|:-------|:-------------------------|--------:|--------------:|:---------|------------:|-----------:|
|              1 | 2010-06-04 | Falcon 9         |        nan    | LEO     | CCSFS SLC 40 | None None   |         1 | False      | False    | False  |                          |       1 |             0 | B0003    |    -80.5774 |    28.5619 |
|              2 | 2012-05-22 | Falcon 9         |        525    | LEO     | CCSFS SLC 40 | None None   |         1 | False      | False    | False  |                          |       1 |             0 | B0005    |    -80.5774 |    28.5619 |
|              3 | 2013-03-01 | Falcon 9         |        677    | ISS     | CCSFS SLC 40 | None None   |         1 | False      | False    | False  |                          |       1 |             0 | B0007    |    -80.5774 |    28.5619 |
|              4 | 2013-09-29 | Falcon 9         |        500    | PO      | VAFB SLC 4E  | False Ocean |         1 | False      | False    | False  |                          |       1 |             0 | B1003    |   -120.611  |    34.6321 |
|              5 | 2013-12-03 | Falcon 9         |       3170    | GTO     | CCSFS SLC 40 | None None   |         1 | False      | False    | False  |                          |       1 |             0 | B1004    |    -80.5774 |    28.5619 |
## Exploratory data analysis
## Calculate the number of launches on each site

|              |   LaunchSite |
|:-------------|-------------:|
| CCSFS SLC 40 |           55 |
| KSC LC 39A   |           22 |
| VAFB SLC 4E  |           13 |

