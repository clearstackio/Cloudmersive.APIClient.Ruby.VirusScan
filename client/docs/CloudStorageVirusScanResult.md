# CloudmersiveVirusScanApiClient::CloudStorageVirusScanResult

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **successful** | **Boolean** | True if the operation of retrieving the file, and scanning it were successfully completed, false if the file could not be downloaded from cloud storage, or if the file could not be scanned.  Note that successful completion does not mean the file is clean; for the output of the virus scanning operation itself, use the CleanResult and FoundViruses parameters. | [optional] |
| **clean_result** | **Boolean** | True if the scan contained no viruses, false otherwise | [optional] |
| **found_viruses** | [**Array&lt;CloudStorageVirusFound&gt;**](CloudStorageVirusFound.md) | Array of viruses found, if any | [optional] |
| **error_detailed_description** | **String** | Detailed error message if the operation was not successful | [optional] |
| **file_size** | **Integer** | Size in bytes of the file that was retrieved and scanned | [optional] |
| **contains_content_moderation_rejection** | **Boolean** | Set to true when using NSFW Content Moderation in the Cloudmersive Storage Protect product (disabled by default) | [optional] |

## Example

```ruby
require 'cloudmersive-virus-scan-api-client'

instance = CloudmersiveVirusScanApiClient::CloudStorageVirusScanResult.new(
  successful: null,
  clean_result: null,
  found_viruses: null,
  error_detailed_description: null,
  file_size: null,
  contains_content_moderation_rejection: null
)
```

