# CloudmersiveVirusScanApiClient::VirusFound

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **file_name** | **String** | Name of the file containing the virus | [optional] |
| **virus_name** | **String** | Name of the virus that was found | [optional] |

## Example

```ruby
require 'cloudmersive-virus-scan-api-client'

instance = CloudmersiveVirusScanApiClient::VirusFound.new(
  file_name: null,
  virus_name: null
)
```

