<!-- TOC -->
* [Toronto Pedestrian Volume](#toronto-pedestrian-volume)
    * [§0. Data Source](#0-data-source)
    * [§1. Data Structure](#1-data-structure)
    * [§2. Data Size](#2-data-size)
    * [§3. Map Sample Data](#3-map-sample-data)
    * [§4. Target Feature](#4-target-feature)
    * [§5. HTML Design](#5-html-design)
<!-- TOC -->

# Toronto Pedestrian Volume

### §0. Data Source

[City of Toronto Open Data Source.
](https://open.toronto.ca/dataset/traffic-volumes-at-intersections-for-all-modes/)

### §1. Data Structure

Toronto Pedestrians Traffic Count obtained from [City of Toronto Open Data Source.
](https://open.toronto.ca/dataset/traffic-volumes-at-intersections-for-all-modes/) uses the following data structure:

|         Column         |    Data Type     |
|:----------------------:|:----------------:|
|        objectid        |      bigint      |
|         tcs__          | double precision |
|          main          |       text       |
|     midblock_route     |       text       |
|      side_1_route      |       text       |
|      side_2_route      |       text       |
|    activation_date     |       date       |
|        latitude        | double precision |
|       longitude        | double precision |
|        latitude        | double precision |
|       longitude        | double precision |
|       count_date       |       date       |
|  f8hr_vehicle_volume   | double precision |
| f8hr_pedestrian_volume | double precision |
|      last_updated      |    timestamp     |
|     download_link      |       text       |
|      src_filename      |       text       |

### §2. Data Size
The number of records in the scraped table was 2,269 which were embedded into the HTML file.

### §3. Map Sample Data
| main      | latitude   | longitude          | count\_date                | f8hr\_pedestrian\_volume |
|:----------|:-----------|:-------------------|:---------------------------|:-------------------------|
| JARVIS ST | 43.649418  | -79.371446         | 2011-09-08 00:00:00.000000 | 17008                    |
| KING ST E | 43.6504606 | -79.3719239        | 2011-09-07 00:00:00.000000 | 37719                    |
| JARVIS ST | 43.6515337 | -79.37236          | 2012-08-15 00:00:00.000000 | 5679                     |
| JARVIS ST | 43.6527176 | -79.37282399999998 | 2015-12-08 00:00:00.000000 | 4369                     |
| JARVIS ST | 43.653704  | -79.373238         | 2011-05-18 00:00:00.000000 | 3622                     |


### §4. Target Feature
Only the variable of interest integrated into the HTML is _**_f8hr_pedestrian_volume_**_.

### §5. HTML Design
- The map is a heatmap for the most active intersections in terms of the observed pedestrians counts captured by _f8hr_pedestrian_volume_.  
- The Latitude, Longitude, and observed pedestrians count are loaded into mouse-hover markers.
- A colour gradient scale is given to the user between 0 and 40,000 pedestrians.