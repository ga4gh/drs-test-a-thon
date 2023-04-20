# Deploy a mock DRS server

## 1. Set Up Environment
- Install [Python 3.x](https://www.python.org/downloads/)

## If you haven't already create and activate a virtual environment

```
python3 -m virtualenv drs_cs_venv
```
**Activate:** \
Mac:
```
source drs_cs_venv/bin/activate
```

Windows:
```
source .\\drs_cs_venv\\scripts\\activate
```

## 2. Install requirements
```
cd step_1_deploy_starter_kit_drs/bkup
```
```
pip3 install -r requirements.txt
```
## 3. Deploy mock DRS server natively
```
python3 good_mock_server_v1.2.0.py --app_host "0.0.0.0" --app_port "5000" --auth_type "none"
```

`auth_type` could be one of `none`,`basic`, `bearer` or `passport`. 
Depending on the `auth_type` provided, the good_mock_server code uses corresponding `auth_token` value which is hard-coded  

| **auth_type** | **auth_token** |
| ----------- | ------------ |
| `none` | N/A |
| `basic` | "dXNlcm5hbWU6cGFzc3dvcmQ=" |
| `bearer` | "secret-bearer-token-1" |
| `passport` | (see below for drs_id + passport map)|


| **drs_id** | **passport** |
| ---------- | ------------ |
| "697907bf-d5bd-433e-aac2-1747f1faf366" | "passport-366" |
| "0bb9d297-2710-48f6-ab4d-80d5eb0c9eaa" | "passport-eaa" |
| "1af6b862-7fc8-411a-86c5-d8e280e5b77a" | "passport-77a" |
| "41898242-62a9-4129-9a2c-5a4e8f5f0afb" | "passport-afb" |
| "a1dd4ae2-8d26-43b0-a199-342b64c7dff6" | "passport-cc7" |

You should now have DRS mock server running on port 5000

## 4. Confirm that the DRS Starter Kit is running on port 5000
**HTTP METHOD:**
```
GET
```
**REQUEST URL:**
```
http://localhost:5000/ga4gh/drs/v1/service-info
```
**Expected Response Status Code:** 200

## 5. Confirm that the data is populated
**HTTP METHOD:**
```
GET
```
**REQUEST URL:**
```
http://localhost:5000/ga4gh/drs/v1/objects/697907bf-d5bd-433e-aac2-1747f1faf366
```
**Expected Response Status Code:** 200


## 8. Execute the DRS Compliance Suite on the mock DRS server
Refer to the instructions provided [here](../step_2_run_drs_cs_on_sk_drs/RUN_DRS_CS_ON_SK_DRS.md).