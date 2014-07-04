# cochrane_scraper

## Description

A scraper for data from the Cochrane library. This program will automatically search through a range of potential Cochrane IDs and download the data for all found meta-analyses. 

You can specify to download the Revman rm5 XML files and/or export them in csv format.

Note that this will only work where you have institutional access to the Cochrane library. I only recommend using this tool in the UK where copyright law has recently changed to allow downloading of academic data for non-commercial research purposes. See [here](http://www.legislation.gov.uk/uksi/2014/1372/regulation/3/made) (section 29A) and [here](https://www.gov.uk/government/publications/changes-to-copyright-law) for further information about the law change.

## Publications

An earlier version of this software was used in the following publications:

* [Konopantelis, Springate and Reeves (2013). A Re-Analysis of the Cochrane Library Data: The Dangers of Unobserved Heterogeneity in Meta-Analyses](http://www.plosone.org/article/info%3Adoi%2F10.1371%2Fjournal.pone.0069930)

## Installation

This software is cross-platform (tested on Windows and Linux). You need to have an up-to-date version of Java installed first.

You can download a zipped archive of Version 1.0.0 (the current jar file) from [here](http://www.datajujitsu.co.uk/misc/jars/cochrane_scraper/cochrane_scraper_v1.0.0.zip)

Alternatively, if you are a Clojure user and have [lein 2](http://leiningen.org/) installed, you can fork this repo and run:

```
lein uberjar
``` 

from the project base directory to build your jar file.

## Usage

```
$ java -jar cochrane_scraper-0.1.0-standalone.jar [args]
```

## Options

-s --start ID to start with
-e --end ID to end with
-z --sleep Number of seconds to sleep between downloads (default 2)
-d --dir Directory to save downloaded files to. 
-r --rm5 Download rm5 files?
-c --csv Export csv files

## Examples

To download all available rm5 files and export to csv for Cochrane IDs from 1 to 20. All data is stored in directory data :

```
$ java -jar cochrane_scraper-[version]-standalone.jar -s 1 -e 20 --dir data -cr
```

To see help options:

```
$ java -jar cochrane_scraper-[version]-standalone.jar --help
```


### To do

* The CSV is not a perfect clone of the output from the csv export in the Revman software.  Some of the column names will be slightly different, but the data should all be there.

* Option to log to file to get a record of corrupted or not found files (can do this on *nix by suffixing the above command with " > cochrane.log") 

Please feel free to contact me with suggestions or submit pull requrests to improve this software

## License

Copyright © 2014 David Springate

Distributed under the Eclipse Public License either version 1.0.0 or any later version.
