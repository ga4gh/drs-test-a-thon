## Installations
- [Python 3.x](https://www.python.org/downloads/) is required to run DRS Compliance Suite natively or using PyPI package.
- [Docker Desktop](https://docs.docker.com/get-docker/) is required to run DRS Compliance Suite using a docker image.

## Running DRS Compliance Suite

### Method I: Using PyPI Package

Install the latest version of the `drs-compliance` PyPI package using pip3
```
pip3 install drs-compliance --upgrade
```
Run the compliance suite

```
drs-compliance --server_base_url "http://localhost:5000/ga4gh/drs/v1" --platform_name "ga4gh starter kit drs" --platform_description "GA4GH reference implementation of DRS specification" --drs_version "1.2.0" --config_file "compliance_suite/config/config_samples/config_basic.json" --serve --serve_port 56565
```
Note: This specific command is an example of running the compliance suite on a local deployment of DRS that is running on port 8085. \
When running the compliance suite, it's important to configure the command line arguments according to the specific DRS implementation you're testing.
Please refer to the [Command Line Arguments](#command-line-arguments) section for details on each of these arguments.
: