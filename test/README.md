# Run AWS Lambda function on local machine

## Usage

* install [python-lambda-local](https://github.com/HDE/python-lambda-local)

```
pip install python-lambda-local
```

* create event test data

```
{
  "region": "ap-southeast-2"
}
```

* test locally

```
export DB_INSTANCE_IDENTIFIER="postgresqldev"
export INITIAL_DAYS_TO_INGEST=1
export LOG_GROUP="/aws/lambda/rds_logs"
python-lambda-local -l lib/ -f lambda_handler -t 60 ../source/main.py event.json
```