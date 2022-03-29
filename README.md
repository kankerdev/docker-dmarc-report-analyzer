# Open DMARC Analyzer

This is Open DMARC Analyzer version 0 alpha-8 (0-α8) by John Bradley (john@systemanomaly.com). Open DMARC Analyzer is an Open Source DMARC Report Analyzer to be used with DMARC reports that have been parsed by [John Levine's rrdmarc script](http://www.taugh.com/rddmarc/) or [techsneeze's dmarcts-report-parser](https://github.com/techsneeze/dmarcts-report-parser).

Open DMARC Analyzer was written because there didn't seem to be a full-featured self-hosted report analyzer that provided enough details to make heads or tails of a large volume of DMARC reports that come into medium to large-sized organizations. While other solutions required paid subscriptions or have part of it hosted on AWS, Open DMARC Analyzer will run on any webserver that supports PHP 7.4+ and MySQL 15.1+.

# System Requirements
- http webserver
- php 7.4+
- mysql 15.1+ or equivalent

# Dependencies

## Required - [jsmitty12/phpWhois](https://github.com/jsmitty12/phpWhois/)
It is highly recommended that you install this package using composer. Instructions are found on the package's git page. This is required, and will replace most GeoIP data if you disable the MaxMind DB reader package.

## Optional - [MaxMind DB Reader PHP API](https://github.com/maxmind/MaxMind-DB-Reader-php)
A note on this dependency - I've tried to write the one refrence to this external project as optional as possible, and it can almost completely be configured from config.php, due to the limitation of php namespace, I haven't come across a way that won't require you to dig deeper into the code if you happen to chose a compatible library to replace this MaxMind one. If you do wish to replace this library with another compatible one, the line in question is located in `includes\functions.php`:
```php
$reader = new MaxMind\Db\Reader(GEO_DB);
```

It is highly recommended that you install this package using composer. Instructions are found on the package's git page.

You will also need the GeoLite2 database from MaxMind (or any other compatible DB). It can be obtained from [here](https://dev.maxmind.com/geoip/geoip2/geolite2/). Open DMARC Analyzer makes use of the GeoLite2 City database.

The MaxMind library is not distributed with this project, and is ultimately an optional feature to the project as a whole.

# Latest Changes

## 0-α8.1

- Added `CODE_OF_CONDUCT`, `CONTRIBUTING`, pull request template, issue templates, and organized documents into docs folder.

See `CHANGELOG` under `docs` for full details of all changes.

# Release Cycle and Versioning

This project regular release cycle is not yet determined. Versioning is under the Anomaly Versioning Scheme (2022), as outlined in `VERSIONING` under `docs`.

# Contributing

Public contributions are encouraged. Please review `CONTRIBUTING` under `docs` for contributing procedures. Additionally, please take a look at our `CODE_OF_CONDUCT`. By participating in this project you agree to abide by the Code of Conduct.

# Contributors

Primary Contributors
- John Bradley - Initial Work

Thanks to [all who contributed](https://github.com/userjack6880/Open-DMARC-Analyzer/graphs/contributors) and [have given feedback](https://github.com/userjack6880/Open-DMARC-Analyzer/issues?q=is%3Aissue).

# Licenses

Open DMARC Analyzer is released under GNU GPLv3. See `LICENSE`.