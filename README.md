# mlflow-mysql-minio
Set up a MLFlow instance with MySQL and MinIO backends using Docker compose for development and testing purposes.

## References
1. https://github.com/clemens33/mlflow

## How to use
1. Clone the repo
2. Create and update the paths as mentioned with the #TODO in the docker-compose file
3. Navigate inside mlflow_mysql_minio folder and type `docker-compose up --build --remove-orphans -d`. Assuming Docker and Docker compose are installed and running.
4. To stop the the containers type `docker-compose down`

## Access the different services
1. MLFlow
    - Purpose: To track metrics and artifacts generated from ML experiments
    - Access URL: http://127.0.0.1:5000

2. MYSQL Adminer
    - Purpose: To view contents of the MySQL database which contains the entity related data for MLFlow e.g. metrics
    - Access URL: http://127.0.0.1:8080
    - Access details:
        * System: MySQL
        * Server: mlflow-db
        * Username: mlflow
        * Password: mlflow123
        * Database: mlflow

3. MinIO web console
    - Purpose: To view artifacts that are stored in MLFlow e.g. models, images, etc.
    - Access URL: http://127.0.0.1:9001
    - Access details (root):
        * Username: mlflow_artifacts
        * Password: mlflow_artifacts_secret
        * Bucket name: ml/
        * MLFlow artifacts path: ml/mlflow/