# Elasticsearch CSV plugin

This plugin offers CSV format for REST search responses.

It uses a REST endpoint `_search_csv` which is equivalent to REST endpoint `_search` except the result set format.

With the parameter `keys` you can optionally pass a string array with the field names to include in the rows.
Note, because of the JSON structure of documents, you might not always obtain regular tabular data. 
It is recommended to use `keys` with field names that appear throughout the result set.

CSV values are escaped with quotes if they contain quotes or commas.

## Example

    curl 0:9200/ezbxml/_search_csv?keys=ezb:zdbid,ezb:license_period.ezb:available,ezb:isil,ezb:sigel,ezb:license_entry_id,ezb:ill_relevance.ezb:ill_code
    ezb:isil,ezb:zdbid,ezb:ill_relevance.ezb:ill_code,ezb:sigel,ezb:license_entry_id,ezb:license_period.ezb:available
    DE-929,14808092,copy,929,EZB6279175,Nationallizenz
    DE-290,14808092,,290,EZB6279178,
    DE-464,14808092,copy,464,EZB3137771,Nationallizenz
    DE-386,14808092,,386,EZB352248,
    DE-467,14808092,copy,467,EZB3137774,Nationallizenz
    DE-38M,20284512,copy,38 M,EZB932535,Nationallizenz
    DE-467,14808092,,467,EZB6279182,
    DE-465,14808092,copy,465,EZB3137777,Nationallizenz
    DE-5,14808092,,5,EZB352272,
    DE-61,14808092,,61,EZB6279185,

## Versions

| Elasticsearch version    | Plugin      | Release date |
| ------------------------ | ----------- | -------------|
| 1.2.1                    | 1.2.1.0     | Jul 15, 2014 |

## Installation

```
./bin/plugin -install csv -url http://xbib.org/repository/org/xbib/elasticsearch/plugin/elasticsearch-csv/1.2.1.0/elasticsearch-csv-1.2.1.0-plugin.zip
```

Do not forget to restart the node after installing.

## Checksum

| File                                  | SHA1                                     |
| ------------------------------------- | -----------------------------------------|
| elasticsearch-csv-1.2.1.0-plugin.zip  | 2963a11148dd975e7d6bdec00320af04bfe5c2ad |

## Project docs

The Maven project site is available at [Github](http://jprante.github.io/elasticsearch-csv)

## Issues

All feedback is welcome! If you find issues, please post them at [Github](https://github.com/jprante/elasticsearch-csv/issues)

# License

Elasticsearch CSV Plugin

Copyright (C) 2014 Jörg Prante

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.