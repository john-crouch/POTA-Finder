# POTA-Finder
POTA Finder: Filter POTA ParkList CSV exports to find rarely (never) activated Parks!

![Script Help Information](/img/pota-finder-help.png)

For information, see my [Finding Local Unactivated POTAs blog post](https://www.george-smart.co.uk/2024/11/finding-local-unactivated-potas/).

Run `pota-finder.py -h` for information

## Requirements
* geopy
* maidenhead

## Exporting the ParkList CSV File
The POTA website does offer [all_parks.csv](https://pota.app/all_parks.csv) (list of all POTAs) and [all_parks_ext.csv](https://pota.app/all_parks_ext.csv) (list of all POTAs with location information), but neither of these files have activation or attempted activation counts. Disappointing. However, if you head to the [POTA ParkList](https://pota.app/#/parklist) and find your country/region of interest the activation data is presented.

![ParkList for GB-ENG showing Activation/Attempts Data](/img/parklist.png)

Just press the “DOWNLOAD” button (you may have to be logged in to see this, as it contains information personal to you) and that yields a CSV file for us. This file, as downloaded, is what you call the script with. Mine was called “England.csv”.

![ParkList Download CSV](/img/parklist_download_csv.png)

The data inside is really useful and includes the latitude and longitude of each marker. This script works out how far each site is from a given location (say, our QTH) and then sort the output by distance, and finally filter on successful activations. You can optionally limit the number of printed results to a fixed number.

![Script Result for Home](/img/pota-finder-longargs-qra.png)

![Script Result for UCL EE](/img/pota-finder-shortargs-latlon.png)