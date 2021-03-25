# IoT Central - API client generation
> see https://aka.ms/autorest
This is the AutoRest configuration file for Azure IoT Central.
---
## Getting Started
To build the SDK for Azure IoT Central, simply [Install AutoRest](https://aka.ms/autorest/install) and in this folder, run:
> `autorest`
To see additional help and options, run:
> `autorest --help`
---

## Configuration
These are the global settings for the IoT Central API.
``` yaml
openapi-type: data-plane
tag: package-2019-10-28-preview
```

### Tag: package-2019-10-28-preview
These settings apply only when `--tag=package-2019-10-28-preview` is specified on the command line.

```yaml $(package-2019-10-28-preview-global)
input-file:
  - Microsoft.IoTCentral/preview/2019-10-28-preview/iotcentralapps.json
```
```yaml $(package-2019-10-28-preview-app)
input-file:
  - Microsoft.IoTCentral/preview/2019-10-28-preview/iotcentral.json
```

```yaml
batch:
    - package-2019-10-28-preview-global : true
    - package-2019-10-28-preview-app: true
```

```yaml
version: latest
clear-output-folder: true
# azure-validator: true
semantic-validator: true
azure-arm: true
add-credentials: true
generate-metadata: true
license-header: MICROSOFT_MIT_NO_VERSION
csharp:
    namespace: Microsoft.Azure.IotCentral
    output-folder: client/csharp/Microsoft.Azure.IotCentral
nodejs:
    package-name: azure-iotcentral
    package-version: 1.0.0
    output-folder: client/nodejs
```
## Multi-API/Profile support for AutoRest v3 generators 
AutoRest V3 generators require the use of `--tag=all-api-versions` to select api files.
This block is updated by an automatic script. Edits may be lost!
``` yaml $(tag) == 'all-api-versions' /* autogenerated */
# include the azure profile definitions from the standard location
require: $(this-folder)/../../../profiles/readme.md

# all the input files across all versions
input-file:
  - $(this-folder)/Microsoft.IoTCentral/preview/2019-10-28-preview/iotcentralapps.json
  - $(this-folder)/Microsoft.IoTCentral/preview/2019-10-28-preview/iotcentral.json

```
If there are files that should not be in the `all-api-versions` set, 
uncomment the  `exclude-file` section below and add the file paths.
``` yaml $(tag) == 'all-api-versions'
#exclude-file: 
#  - $(this-folder)/Microsoft.Example/stable/2010-01-01/somefile.json
```