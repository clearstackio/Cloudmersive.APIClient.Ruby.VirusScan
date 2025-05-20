# CloudmersiveVirusScanApiClient::AdditionalAdvancedScanInformation

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **contains_json** | **Boolean** | True if the input file contains JSON data, false otherwise; this is not a threat signal | [optional] |
| **contains_xml** | **Boolean** | True if the input file contains XML data, false otherwise; this is not a threat signal | [optional] |
| **contains_image** | **Boolean** | True if the input file contains an image | [optional] |
| **relevant_subfile_name** | **String** | Relevant subfile name in an archive format for identified threats, if any | [optional] |

## Example

```ruby
require 'cloudmersive-virus-scan-api-client'

instance = CloudmersiveVirusScanApiClient::AdditionalAdvancedScanInformation.new(
  contains_json: null,
  contains_xml: null,
  contains_image: null,
  relevant_subfile_name: null
)
```

