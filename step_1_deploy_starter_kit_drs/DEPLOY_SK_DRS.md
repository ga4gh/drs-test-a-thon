# Deploy a DRS Starter Kit

## 1. Set Up Environment
- Install [Docker Desktop](https://docs.docker.com/get-docker/)
- Install [Python 3.x](https://www.python.org/downloads/)

## Create a virtual environment

```
python3 -m virtualenv drs_cs_venv
```

## Activate the virtual environment
```
source drs_cs_venv/bin/activate
```

## 2. Install requirements
```
cd step_1_deploy_starter_kit_drs
```
```
pip3 install -r requirements.txt
```

## 3: Delete any databases and temporary files
```
rm -f resources/drs/db/drs.db tmp/drs_dataset.ndjson
```

## 4. Deploy DRS Starter Kit using docker-compose
```
docker-compose up -d
```
You should now have DRS Starter Kit running on port 5000


## 5. Confirm that the DRS Starter Kit is running on port 5000 
**HTTP METHOD:**
```
GET
```
**REQUEST URL:**
```
http://localhost:5000/ga4gh/drs/v1/service-info
```
**Expected Response Status Code:** 200

## 6. Populate data into Starter Kit DRS
```
python3 resources/drs/db-scripts/populate-drs.py
```

## 7. Confirm that the data is populated
**HTTP METHOD:**
```
GET
```
**REQUEST URL:**
```
http://localhost:5000/ga4gh/drs/v1/objects/8e18bfb64168994489bc9e7fda0acd4f
```
**Expected Response Status Code:** 200


## 8. Execute the DRS Compliance Suite on the Starter Kit
Refer to the instructions provided [here](../step_2_run_drs_cs_on_sk_drs/RUN_DRS_CS.md).

## NOTE: 
when you are done using the DRS Starter Kit, to bring down the docker containers use the following commands
```
cd step_1_deploy_starter_kit_drs
```
```
docker-compose down
```