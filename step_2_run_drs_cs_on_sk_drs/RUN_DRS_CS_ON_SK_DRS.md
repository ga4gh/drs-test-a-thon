## Installations
- [Python 3.x](https://www.python.org/downloads/) is required to run DRS Compliance Suite natively or using PyPI package.
- [Docker Desktop](https://docs.docker.com/get-docker/) is required to run DRS Compliance Suite using a docker image.

## Running DRS Compliance Suite

## 1. Verify the following details

```
cd ../step_2_run_drs_cs_on_sk_drs
```

- input parameters in the `command` section of the [docker-compose](./docker-compose.yml) file.
- [config file](./config/config_starter_kit_drs.json) must have DRS Objects and authorization details.

## 2. Execute DRS Compliance Suite on the DRS Starter Kit using docker-compose
```
docker-compose up -d
```

- You can find the output JSON report file at [output/drs-cs-report.json](./output/drs-cs-report.json)
- You can find the html report at `http:0.0.0.0:57568/`

---

## NOTE:
when you are done using the DRS CS, to bring down the docker containers use the following commands
```
cd step_2_run_drs_cs_on_sk_drs
```
```
docker-compose down
```