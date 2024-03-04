<!-- TOC -->
* [Toronto Pedestrian Volume](#toronto-pedestrian-volume)
    * [§ Data Source](#-data-source)
    * [§ Data Structure](#-data-structure)
    * [§ Target Feature](#-target-feature)
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

### 3. Data Size
The number of records in the scraped table was 2,269 which were embedded into the HTML file.

### §2. Target Feature
Only the variable of interest integrated into the HTML is _**_f8hr_pedestrian_volume_**_.

### §3. HTML Design
- The map is a heatmap for the most active intersections in terms of the observed pedestrians counts captured by _f8hr_pedestrian_volume_.  
- The Latitude, Longitude, and observed pedestrians count are loaded into mouse-hover markers.
- A colour gradient scale is given to the user between 0 and 40,000 pedestrians.