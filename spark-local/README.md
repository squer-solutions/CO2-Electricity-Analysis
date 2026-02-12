# Local Spark with Docker Compose

Minimal Apache Spark setup for local development.

## Start Spark

```bash
docker-compose up -d
```

## Access

- **Spark Web UI**: http://localhost:8080
- **Spark Master**: spark://localhost:7077

## Connect from Jupyter Notebook

**Critical:** PySpark client version must match server version exactly!

```bash
pip install pyspark==3.5.0
```

Then open [spark_jupyter_example.ipynb](spark_jupyter_example.ipynb) for examples.

### Version Compatibility Issue

If you get `InvalidClassException` errors, your local PySpark version doesn't match the Docker Spark version (3.5.0). Always install the matching version:
```bash
pip uninstall pyspark
pip install pyspark==3.5.0
```

## Stop Spark

```bash
docker-compose down
```

## Image Info

Uses `apache/spark:3.5.0` - official Apache Foundation image
- Updated regularly on Docker Hub
- Default ports: 7077 (master), 8080 (web UI)
- Based on Spark standalone mode
