# CloudmersiveVirusScanApiClient::CloudStorageAdvancedVirusScanResult

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **successful** | **Boolean** | True if the operation of retrieving the file, and scanning it were successfully completed, false if the file could not be downloaded from cloud storage, or if the file could not be scanned.  Note that successful completion does not mean the file is clean; for the output of the virus scanning operation itself, use the CleanResult and FoundViruses parameters. | [optional] |
| **clean_result** | **Boolean** | True if the scan contained no viruses, false otherwise | [optional] |
| **contains_executable** | **Boolean** | True if the scan contained an executable (application code), which can be a significant risk factor | [optional] |
| **contains_invalid_file** | **Boolean** | True if the scan contained an invalid file (such as a PDF that is not a valid PDF, Word Document that is not a valid Word Document, etc.), which can be a significant risk factor | [optional] |
| **contains_script** | **Boolean** | True if the scan contained a script (such as a PHP script, Python script, etc.) which can be a significant risk factor | [optional] |
| **contains_password_protected_file** | **Boolean** | True if the scan contained a password protected or encrypted file, which can be a significant risk factor | [optional] |
| **contains_restricted_file_format** | **Boolean** | True if the uploaded file is of a type that is not allowed based on the optional restrictFileTypes parameter, false otherwise; if restrictFileTypes is not set, this will always be false | [optional] |
| **contains_macros** | **Boolean** | True if the uploaded file contains embedded Macros of other embedded threats within the document, which can be a significant risk factor | [optional] |
| **contains_xml_external_entities** | **Boolean** | True if the uploaded file contains embedded XML External Entity threats of other embedded threats within the document, which can be a significant risk factor | [optional] |
| **contains_insecure_deserialization** | **Boolean** | True if the uploaded file contains embedded Insecure Deserialization threats of other embedded threats within the document, which can be a significant risk factor | [optional] |
| **contains_html** | **Boolean** | True if the uploaded file contains HTML, which can be a significant risk factor | [optional] |
| **contains_unsafe_archive** | **Boolean** | True if the uploaded file contains unsafe archive (e.g. zip) content, such as a Zip Bomb, or other configurations of a zip file that could lead to an unsafe extraction | [optional] |
| **contains_ole_embedded_object** | **Boolean** | True if the uploaded file contains an OLE embedded object, which can be a significant risk factor | [optional] |
| **verified_file_format** | **String** | For file format verification-supported file formats, the contents-verified file format of the file.  Null indicates that the file format is not supported for contents verification.  If a Virus or Malware is found, this field will always be set to Null. | [optional] |
| **found_viruses** | [**Array&lt;CloudStorageVirusFound&gt;**](CloudStorageVirusFound.md) | Array of viruses found, if any | [optional] |
| **error_detailed_description** | **String** | Detailed error message if the operation was not successful | [optional] |
| **file_size** | **Integer** | Size in bytes of the file that was retrieved and scanned | [optional] |
| **content_information** | [**AdditionalAdvancedScanInformation**](AdditionalAdvancedScanInformation.md) |  | [optional] |

## Example

```ruby
require 'cloudmersive-virus-scan-api-client'

instance = CloudmersiveVirusScanApiClient::CloudStorageAdvancedVirusScanResult.new(
  successful: null,
  clean_result: null,
  contains_executable: null,
  contains_invalid_file: null,
  contains_script: null,
  contains_password_protected_file: null,
  contains_restricted_file_format: null,
  contains_macros: null,
  contains_xml_external_entities: null,
  contains_insecure_deserialization: null,
  contains_html: null,
  contains_unsafe_archive: null,
  contains_ole_embedded_object: null,
  verified_file_format: null,
  found_viruses: null,
  error_detailed_description: null,
  file_size: null,
  content_information: null
)
```

