# CloudmersiveVirusScanApiClient::VirusScanResult

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **clean_result** | **Boolean** | True if the scan contained no viruses, false otherwise | [optional] |
| **found_viruses** | [**Array&lt;VirusFound&gt;**](VirusFound.md) | Array of viruses found, if any | [optional] |

## Example

```ruby
require 'cloudmersive-virus-scan-api-client'

instance = CloudmersiveVirusScanApiClient::VirusScanResult.new(
  clean_result: null,
  found_viruses: null
)
```

