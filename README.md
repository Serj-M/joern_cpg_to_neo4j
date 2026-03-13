# Joern CPG to Neo4j

This repository contains code to import CPG extracted from Joern (neo4jcsv format) into Neo4j.

**Note**: Please refer to the [Joern documentation](https://docs.joern.io) for more information on how to use Joern.

## Usage

1. Modify the `config.py` file to set the path to the csv files and the Neo4j database information.

2. Start your Neo4j database.

3. Run the `main.py` file to import the CPG into Neo4j.

## Alt usage

If you're importing nodes and edges from a large project, importing via Cypher, as suggested by Joern, can be very slow. For a significant speedup, you can use the Neo4j data import instructions - https://neo4j.com/docs/operations-manual/current/import/#import-tool-examples .

Modify the import parameters in the file `import_args.txt` and run the command `HEAP_SIZE=3G ./bin/neo4j-admin @import_args.txt` (the database must be stopped while the command is running) in the directory `/home/serj/.config/neo4j-desktop/Application/Data/dbmss/dbms-fb8e0921-28fd-4ce9-8bee-1e7862e47bf1`

## Dependencies

- neo4j (https://pypi.org/project/neo4j/)

## Contributing

Please feel free to open an issue or a pull request if you find any bugs, have any questions or want to make any suggestions.