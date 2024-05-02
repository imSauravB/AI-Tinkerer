# Start from a base image with Python installed
FROM python:3.9
# Install mlflow and dependencies
RUN pip install \
    mlflow \
    psycopg2
RUN apt update
RUN apt install sqlite3

# Expose the default MLflow server port
EXPOSE 5001
# Start the MLflow server when the container starts
CMD mlflow server \
    --host 0.0.0.0 \
    --port 5001 \
    --backend-store-uri sqlite:///mlruns/mlflowdb.sqlite

