### Useful airflow commands and advices:

#### • Command line vs python:
use command line tool to:

-Start Ariflow processes
-Manually run DAGs / Tasks
-Get logging information from airflow

Use Python to:

-data processing code itself
-Create a DAG
-Edit the individual properties of a DAG


#### • Airflow config file:
airflow.cfg


#### • See dags folder:
cd /home/repl/workspace/dags/


#### • How to run a dag:
airflow run <dag_id> <task_id> <start_date>
airflow run etl_pipeline download_file 2020-01-08

#### • Airflow sub-commands:

airflow list_dags

for checking dags
airflow scheduler 

airflow -h to get further descriptions about any command.
airflow command -h

#### • Starting the Airflow webserver:
airflow webserver -p 9090

#### • Using airflow list_dags to see the executor:

-SequentialExecutor: executes taks one by one (for debugging)
-LocalExecutor: as many processes as needed
-CeleryExecutor: Multiple worker systems can be dened


#### • Troubleshooting:

-dag won't run on schedule:

run airflow scheduler

At least one schedule_interval  hasn't passed:

Modify the aributes to meet your requirements.

Not enough tasks free within the executor to run:
Change executor typeAdd system resourcesAdd more systemsChange DAG scheduling


#### • DAG won't load:

DAG not in web UIDAG not in airflow list_dags
Possible solutionsVerify DAG le is in correct folderDetermine the DAGs folder via airflow.cfg
Note, the folder must be an absolute path


#### • Syntax errors:
The most common reason a DAG le won't appearSometimes dicult to nd errors in DAGTwo quick methods:
Run airflow list_dags
Run python3 <dagfile.py>

#### • Testing single sensors or operators:
-example:

airflow test etl_update sense_file -1








