## Examples

### Tutorial

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1ByFx_NOEfTZeaJ1Wtw3UwTH3H3-Sye2O?usp=sharing)

The tutorial in **[Google Colaboratory](https://colab.research.google.com/drive/1ByFx_NOEfTZeaJ1Wtw3UwTH3H3-Sye2O?usp=sharing)** is the easiest way to learn how to use Morph-KGC. Some relevant files for the tutorial can be found in the [`tutorial`](https://github.com/morph-kgc/morph-kgc/tree/main/examples/tutorial) directory.


### Relational Databases
An example with _MySQL_ using [GTFS-Madrid-Bench](https://github.com/oeg-upm/gtfs-bench) data can be found in the [`rdb`](https://github.com/morph-kgc/morph-kgc/tree/main/examples/rdb) directory. The directory contains:
- The `mapping` file.
- The `configuration` file that has to be provided to Morph-KGC.

To start a docker container with the MySQL instance containing the data, run the following:
```
docker run --name mysql-gtfs1 -p 3306:3306 -d -e MYSQL_ROOT_PASSWORD=gtfs oegdataintegration/mysql-gtfs1:1.0
```

Note that the MySQL driver needs to be installed, as detailed in the **[documentation](https://morph-kgc.readthedocs.io/en/latest/documentation/#relational-databases_1)**. You just need to run the following:
```
pip install pymysql
pip install cryptography
```
Also, **update the _paths_ parameters in the configuration file** accordingly.

### JSON and XML
Examples for _JSON_ and _XML_ can be found in [`json`](https://github.com/morph-kgc/morph-kgc/tree/main/examples/json) and [`xml`](https://github.com/morph-kgc/morph-kgc/tree/main/examples/xml) directories. The directories contain:
- The `data` file.
- The `mapping` file.
- The `configuration` file that has to be provided to Morph-KGC.
- The mapping file in [YARRRML](https://rml.io/yarrrml/spec/) format. This is **not** necessary, but allows to inspect the mapping in a human-readable format.

Note that the **_paths_ parameters in the configuration file need to be updated** accordingly.

### CSV
An example for _CSV_ can be found in the [`csv`](https://github.com/morph-kgc/morph-kgc/tree/main/examples/csv) directory. The directory contains:
- The `data` directory with several CSV files.
- The `mapping` file.
- The `configuration` file that has to be provided to Morph-KGC.

Note that the **_paths_ parameters in the configuration file need to be updated** accordingly. Given that this example involves multiple CSV files, the paths to these files are provided in the mapping file with the `rml:source` property. The values of this property have to be updated with the correct _paths_ to the CSV files in your system.

### Configuration Files
The directory [`configuration-file`](https://github.com/morph-kgc/morph-kgc/tree/main/examples/configuration-file) contains some configuration files to run Morph-KGC with. [`default_config.ini`](https://github.com/morph-kgc/morph-kgc/blob/main/examples/configuration-file/default_config.ini) contains all possible configuration options along with their default values. Options that are not provided in the `CONFIGURATION` section will use the default values. You can see all the information about configuration files in the **[documentation](https://morph-kgc.readthedocs.io/en/latest/documentation/#configuration)**.
