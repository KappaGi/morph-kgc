<p align="center">
<img src="https://github.com/ArenasGuerreroJulian/morph-kgc/blob/main/docs/assets/logo.png" height="100" alt="morph">
</p>

[![License](https://img.shields.io/pypi/l/morph-kgc.svg)](https://github.com/oeg-upm/morph-kgc/blob/main/LICENSE)
[![DOI](https://zenodo.org/badge/311956260.svg?style=flat)](https://zenodo.org/badge/latestdoi/311956260)
[![Latest PyPI version](https://img.shields.io/pypi/v/morph-kgc?style=flat)](https://pypi.python.org/pypi/morph-kgc)
[![Python Version](https://img.shields.io/pypi/pyversions/morph-kgc.svg)](https://pypi.python.org/pypi/morph-kgc)
[![PyPI status](https://img.shields.io:/pypi/status/morph-kgc?)](https://pypi.python.org/pypi/morph-kgc)
[![build](https://github.com/oeg-upm/morph-kgc/actions/workflows/continuous-integration.yml/badge.svg)](https://github.com/oeg-upm/morph-kgc/actions/workflows/continuous-integration.yml)

**Morph-KGC** is an engine that constructs **[RDF](https://www.w3.org/TR/rdf11-concepts/)** knowledge graphs from heterogeneous data sources with the **[R2RML](https://www.w3.org/TR/r2rml/)**, **[RML](https://rml.io/specs/rml/)** and **[RML-star](https://kg-construct.github.io/rml-star-spec/)** mapping languages. Morph-KGC is built on top of [pandas](https://pandas.pydata.org/) and it leverages *mapping partitions* to significantly reduce execution times and memory consumption for large data sources.

## Main Features

- Supports **[R2RML](https://www.w3.org/TR/r2rml/)**, **[RML](https://rml.io/specs/rml/)** and **[RML-star](https://kg-construct.github.io/rml-star-spec/)** mapping languages.
- Input data formats:
    - **Relational databases**: **[MySQL](https://www.mysql.com/)**, **[PostgreSQL](https://www.postgresql.org/)**, **[Oracle](https://www.oracle.com/database/)**, **[Microsoft SQL Server](https://www.microsoft.com/sql-server)**, **[MariaDB](https://mariadb.org/)**, **[SQLite](https://www.sqlite.org/index.html)**.
    - **Tabular files**: **[CSV](https://en.wikipedia.org/wiki/Comma-separated_values)**, **[TSV](https://en.wikipedia.org/wiki/Tab-separated_values)**, **[Excel](https://www.microsoft.com/en-us/microsoft-365/excel)**, **[Parquet](https://parquet.apache.org/documentation/latest/)**, **[Feather](https://arrow.apache.org/docs/python/feather.html)**, **[ORC](https://orc.apache.org/)**, **[Stata](https://www.stata.com/)**, **[SAS](https://www.sas.com)**, **[SPSS](https://www.ibm.com/analytics/spss-statistics-software)**, **[ODS](https://en.wikipedia.org/wiki/OpenDocument)**.
    - **Hierarchical files**: **[JSON](https://www.json.org/json-en.html)**, **[XML](https://www.w3.org/TR/xml/)**.
- Output RDF serializations: **[N-Triples](https://www.w3.org/TR/n-triples/)**, **[N-Quads](https://www.w3.org/TR/n-quads/)**.
- Runs on **Linux**, **Windows** and **macOS** systems.
- Compatible with **Python** 3.7 or higher.
- **Optimized** to materialize large knowledge graphs.

## Getting Started

**[PyPi](https://pypi.org/project/morph-kgc/)** is the fastest way to install Morph-KGC:
```
pip install morph-kgc
```

We recommend to use **[virtual environments](https://docs.python.org/3/library/venv.html#)** to install Morph-KGC.

To run the engine via **command line** you just need to execute the following:
```
python3 -m morph_kgc config.ini
```

Check the **[documentation](https://oeg-upm.github.io/morph-kgc/documentation/#configuration)** to can see how to generate the configuration **INI file**. **[Here](https://github.com/oeg-upm/morph-kgc/blob/main/examples/configuration-file-examples/default_config.ini)** you can also see an example INI file.

It is also possible to run Morph-KGC as a **library** with **[RDFlib](https://rdflib.readthedocs.io/en/stable/)** and **[Oxigraph](https://oxigraph.org/pyoxigraph/stable/index.html)**:
```python
import morph_kgc

# generate the triples and load them to an RDFlib graph
g_rdflib = morph_kgc.materialize('/path/to/config.ini')
# work with the RDFlib graph
q_res = g_rdflib.query(' SELECT DISTINCT ?classes WHERE { ?s a ?classes } ')

# generate the triples and load them to Oxigraph
g_oxigraph = morph_kgc.materialize_oxigraph('/path/to/config.ini')
# work with Oxigraph
q_res = graph.query(' SELECT DISTINCT ?classes WHERE { ?s a ?classes } ')

# the methods above also accept the config as a string
config = """
            [DataSource1]
            mappings=/path/to/mapping/mapping_file.rml.ttl
            db_url=mysql+pymysql://user:password@localhost:3306/db_name
         """
g_rdflib = morph_kgc.materialize(config)
```

## Documentation

**[Read the documentation](https://oeg-upm.github.io/morph-kgc/documentation/)**.

## License

**Morph-KGC** is available under the permissive **[Apache License 2.0](https://github.com/oeg-upm/Morph-KGC/blob/main/LICENSE)**.

## Author

- **[Julián Arenas-Guerrero](https://github.com/ArenasGuerreroJulian/) - [julian.arenas.guerrero@upm.es](mailto:julian.arenas.guerrero@upm.es)**

*[Ontology Engineering Group](https://oeg.fi.upm.es/index.php/en/index.html)*, *[Universidad Politécnica de Madrid](https://www.upm.es/internacional)*.

## Contributors

See the full list of contributors **[here](https://github.com/oeg-upm/morph-kgc/graphs/contributors)**.
