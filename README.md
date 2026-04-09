# Joern CPG to Neo4j

This repository contains code to import CPG extracted from Joern (neo4jcsv format) into Neo4j.
https://github.com/joernio/joern `docker run --rm -it -v /tmp:/tmp -v $(pwd):/app:rw -w /app -t ghcr.io/joernio/joern joern` 
run in docker -> `joern-parse /src/directory` -> `joern-export --out /app/outdir_all --repr=all --format=neo4jcsv` (https://docs.joern.io/export/)

**Note**: Please refer to the [Joern documentation](https://docs.joern.io) for more information on how to use Joern.

## Usage

1. Use Python 3.10 or newer, then create and activate a virtual environment:
   `python3 -m venv .venv`
   `source .venv/bin/activate`

2. Install dependencies from `requirements.txt`:
   `pip install -r requirements.txt`

3. Create `config.py` based on `config_example.yml`, then update it with the path to the csv files and the Neo4j database information.

4. Start your Neo4j database.

5. Run the `main.py` file to import the CPG into Neo4j.

## Alt usage

If you're importing nodes and edges from a large project, importing via Cypher, as suggested by Joern, can be very slow. For a significant speedup, you can use the Neo4j data import instructions - https://neo4j.com/docs/operations-manual/current/import/#import-tool-examples .

Modify the import parameters in the file `import_args.txt` and run the command `HEAP_SIZE=3G ./bin/neo4j-admin @import_args.txt` (the database must be stopped while the command is running) in the directory with your Neo4j database `/home/user/.config/neo4j-desktop/Application/Data/dbmss/dbms-fb8e0921-28fd-4ce9-8bee-1e7862e47bf1` (for linux). First, move all the CSS files to import/ in the specified directory (or specify the current path to the CSS files in the `import_args.txt` file).

## Dependencies

- neo4j (https://pypi.org/project/neo4j/)
- pyyaml (https://pypi.org/project/pyyaml/)

## Contributing

Please feel free to open an issue or a pull request if you find any bugs, have any questions or want to make any suggestions.