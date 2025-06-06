# CloudmersiveVirusScanApiClient::ScanApi

All URIs are relative to *https://testapi.cloudmersive.com*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**scan_file**](ScanApi.md#scan_file) | **POST** /virus/scan/file | Scan a file for viruses |
| [**scan_file_advanced**](ScanApi.md#scan_file_advanced) | **POST** /virus/scan/file/advanced | Advanced Scan a file for viruses |
| [**scan_website**](ScanApi.md#scan_website) | **POST** /virus/scan/website | Scan a website for malicious content and threats |


## scan_file

> <VirusScanResult> scan_file(input_file)

Scan a file for viruses

Scan files and content for viruses. Leverage continuously updated signatures for millions of threats, and advanced high-performance scanning capabilities.  Over 17 million virus and malware signatures.  Continuous cloud-based updates.  Wide file format support including Office, PDF, HTML, Flash.  Zip support including .Zip, .Rar, .DMG, .Tar, and other archive formats.  Multi-threat scanning across viruses, malware, trojans, ransomware, and spyware.  High-speed in-memory scanning delivers subsecond typical response time.

### Examples

```ruby
require 'time'
require 'cloudmersive-virus-scan-api-client'
# setup authorization
CloudmersiveVirusScanApiClient.configure do |config|
  # Configure API key authorization: Apikey
  config.api_key['Apikey'] = 'YOUR API KEY'
  # Uncomment the following line to set a prefix for the API key, e.g. 'Bearer' (defaults to nil)
  # config.api_key_prefix['Apikey'] = 'Bearer'
end

api_instance = CloudmersiveVirusScanApiClient::ScanApi.new
input_file = File.new('/path/to/some/file') # File | Input file to perform the operation on.

begin
  # Scan a file for viruses
  result = api_instance.scan_file(input_file)
  p result
rescue CloudmersiveVirusScanApiClient::ApiError => e
  puts "Error when calling ScanApi->scan_file: #{e}"
end
```

#### Using the scan_file_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<VirusScanResult>, Integer, Hash)> scan_file_with_http_info(input_file)

```ruby
begin
  # Scan a file for viruses
  data, status_code, headers = api_instance.scan_file_with_http_info(input_file)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <VirusScanResult>
rescue CloudmersiveVirusScanApiClient::ApiError => e
  puts "Error when calling ScanApi->scan_file_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **input_file** | **File** | Input file to perform the operation on. |  |

### Return type

[**VirusScanResult**](VirusScanResult.md)

### Authorization

[Apikey](../README.md#Apikey)

### HTTP request headers

- **Content-Type**: multipart/form-data
- **Accept**: application/json, text/json, application/xml, text/xml


## scan_file_advanced

> <VirusScanAdvancedResult> scan_file_advanced(input_file, opts)

Advanced Scan a file for viruses

Advanced Scan files with 360-degree Content Protection across Viruses and Malware, executables, invalid files, scripts, and even restrictions on accepted file types with complete content verification. Customize threat rules to your needs. Leverage continuously updated signatures for millions of threats, and advanced high-performance scanning capabilities.  Over 17 million virus and malware signatures.  Continuous cloud-based updates.  Block threats beyond viruses including executables, scripts, invalid files, and more.  Optionally limit input files to a specific set of file types (e.g. PDF and Word Documents only).  Wide file format support including Office, PDF, HTML, Flash, MSG, and a wide range of image file formats.  Zip support including .Zip, .Rar, .DMG, .Tar, and other archive formats.  Multi-threat scanning across viruses, malware, trojans, ransomware, and spyware.  High-speed in-memory scanning delivers subsecond typical response time.

### Examples

```ruby
require 'time'
require 'cloudmersive-virus-scan-api-client'
# setup authorization
CloudmersiveVirusScanApiClient.configure do |config|
  # Configure API key authorization: Apikey
  config.api_key['Apikey'] = 'YOUR API KEY'
  # Uncomment the following line to set a prefix for the API key, e.g. 'Bearer' (defaults to nil)
  # config.api_key_prefix['Apikey'] = 'Bearer'
end

api_instance = CloudmersiveVirusScanApiClient::ScanApi.new
input_file = File.new('/path/to/some/file') # File | Input file to perform the operation on.
opts = {
  file_name: 'file_name_example', # String | Optional: specify the original file name of the file being scanned.  By default the file name is taken from inputFile parameter, but if this is not provided, or you wish to override it, you can specify the original file name using this parameter.
  allow_executables: true, # Boolean | Set to false to block executable files (program code) from being allowed in the input file.  Default is false (recommended).
  allow_invalid_files: true, # Boolean | Set to false to block invalid files, such as a PDF file that is not really a valid PDF file, or a Word Document that is not a valid Word Document.  Default is false (recommended).
  allow_scripts: true, # Boolean | Set to false to block script files, such as a PHP files, Python scripts, BAT scripts, JS scripts, and other malicious content or security threats that can be embedded in the file.  Set to true to allow these file types.  Default is false (recommended).
  allow_password_protected_files: true, # Boolean | Set to false to block password protected and encrypted files, such as encrypted zip and rar files, and other files that seek to circumvent scanning through passwords.  Set to true to allow these file types.  Default is false (recommended).
  allow_macros: true, # Boolean | Set to false to block macros and other threats embedded in document files, such as Word, Excel and PowerPoint embedded Macros (including support for .DOCX, .XLSX, .PPTX, .DOC and .XLS), and other files that contain embedded content threats.  Set to true to allow these file types.  Default is false (recommended).
  allow_xml_external_entities: true, # Boolean | Set to false to block XML External Entities and other threats embedded in XML files, and other files that contain embedded content threats.  Set to true to allow these file types.  Default is false (recommended).
  allow_insecure_deserialization: true, # Boolean | Set to false to block Insecure Deserialization and other threats embedded in JSON and other object serialization files, and other files that contain embedded content threats.  Set to true to allow these file types.  Default is false (recommended).
  allow_html: true, # Boolean | Set to false to block HTML input in the top level file; HTML can contain XSS, scripts, local file accesses and other threats.  Set to true to allow these file types.  Default is false (recommended) [for API keys created prior to the release of this feature default is true for backward compatability].  If set to true, HTML files containing script tags will be allowed, but ContainsScript will be set to true if script tags are present.
  allow_unsafe_archives: true, # Boolean | Set to false to block unsafe archives such as Zip Bombs, and other archives that can cause unsafe extraction outcomes.  Default is false (recommended).  If set to true, unsafe archives will be allowed.
  allow_ole_embedded_object: true, # Boolean | Set to false to block OLE embedded objects, which can contain vulnerabilities and executable code.  Default is false (recommended).  If set to true, OLE embedded objects will be allowed.
  options: 'options_example', # String | Comma separated set of configuration operations.  Include permitJavascriptAndHtmlInPDFs to allow JavaScript and HTML in PDF files.  Include blockOfficeXmlOleEmbeddedFile to block embedded OLE files in Office Documents using the modern file format.  Include blockInvalidUris to block invalid URIs in Office documents.  Default is no options.
  restrict_file_types: 'restrict_file_types_example' # String | Specify a restricted set of file formats to allow as clean as a comma-separated list of file formats, such as .pdf,.docx,.png would allow only PDF, PNG and Word document files.  All files must pass content verification against this list of file formats, if they do not, then the result will be returned as CleanResult=false.  Set restrictFileTypes parameter to null or empty string to disable; default is disabled.
}

begin
  # Advanced Scan a file for viruses
  result = api_instance.scan_file_advanced(input_file, opts)
  p result
rescue CloudmersiveVirusScanApiClient::ApiError => e
  puts "Error when calling ScanApi->scan_file_advanced: #{e}"
end
```

#### Using the scan_file_advanced_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<VirusScanAdvancedResult>, Integer, Hash)> scan_file_advanced_with_http_info(input_file, opts)

```ruby
begin
  # Advanced Scan a file for viruses
  data, status_code, headers = api_instance.scan_file_advanced_with_http_info(input_file, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <VirusScanAdvancedResult>
rescue CloudmersiveVirusScanApiClient::ApiError => e
  puts "Error when calling ScanApi->scan_file_advanced_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **input_file** | **File** | Input file to perform the operation on. |  |
| **file_name** | **String** | Optional: specify the original file name of the file being scanned.  By default the file name is taken from inputFile parameter, but if this is not provided, or you wish to override it, you can specify the original file name using this parameter. | [optional] |
| **allow_executables** | **Boolean** | Set to false to block executable files (program code) from being allowed in the input file.  Default is false (recommended). | [optional] |
| **allow_invalid_files** | **Boolean** | Set to false to block invalid files, such as a PDF file that is not really a valid PDF file, or a Word Document that is not a valid Word Document.  Default is false (recommended). | [optional] |
| **allow_scripts** | **Boolean** | Set to false to block script files, such as a PHP files, Python scripts, BAT scripts, JS scripts, and other malicious content or security threats that can be embedded in the file.  Set to true to allow these file types.  Default is false (recommended). | [optional] |
| **allow_password_protected_files** | **Boolean** | Set to false to block password protected and encrypted files, such as encrypted zip and rar files, and other files that seek to circumvent scanning through passwords.  Set to true to allow these file types.  Default is false (recommended). | [optional] |
| **allow_macros** | **Boolean** | Set to false to block macros and other threats embedded in document files, such as Word, Excel and PowerPoint embedded Macros (including support for .DOCX, .XLSX, .PPTX, .DOC and .XLS), and other files that contain embedded content threats.  Set to true to allow these file types.  Default is false (recommended). | [optional] |
| **allow_xml_external_entities** | **Boolean** | Set to false to block XML External Entities and other threats embedded in XML files, and other files that contain embedded content threats.  Set to true to allow these file types.  Default is false (recommended). | [optional] |
| **allow_insecure_deserialization** | **Boolean** | Set to false to block Insecure Deserialization and other threats embedded in JSON and other object serialization files, and other files that contain embedded content threats.  Set to true to allow these file types.  Default is false (recommended). | [optional] |
| **allow_html** | **Boolean** | Set to false to block HTML input in the top level file; HTML can contain XSS, scripts, local file accesses and other threats.  Set to true to allow these file types.  Default is false (recommended) [for API keys created prior to the release of this feature default is true for backward compatability].  If set to true, HTML files containing script tags will be allowed, but ContainsScript will be set to true if script tags are present. | [optional] |
| **allow_unsafe_archives** | **Boolean** | Set to false to block unsafe archives such as Zip Bombs, and other archives that can cause unsafe extraction outcomes.  Default is false (recommended).  If set to true, unsafe archives will be allowed. | [optional] |
| **allow_ole_embedded_object** | **Boolean** | Set to false to block OLE embedded objects, which can contain vulnerabilities and executable code.  Default is false (recommended).  If set to true, OLE embedded objects will be allowed. | [optional] |
| **options** | **String** | Comma separated set of configuration operations.  Include permitJavascriptAndHtmlInPDFs to allow JavaScript and HTML in PDF files.  Include blockOfficeXmlOleEmbeddedFile to block embedded OLE files in Office Documents using the modern file format.  Include blockInvalidUris to block invalid URIs in Office documents.  Default is no options. | [optional] |
| **restrict_file_types** | **String** | Specify a restricted set of file formats to allow as clean as a comma-separated list of file formats, such as .pdf,.docx,.png would allow only PDF, PNG and Word document files.  All files must pass content verification against this list of file formats, if they do not, then the result will be returned as CleanResult&#x3D;false.  Set restrictFileTypes parameter to null or empty string to disable; default is disabled. | [optional] |

### Return type

[**VirusScanAdvancedResult**](VirusScanAdvancedResult.md)

### Authorization

[Apikey](../README.md#Apikey)

### HTTP request headers

- **Content-Type**: multipart/form-data
- **Accept**: application/json, text/json, application/xml, text/xml


## scan_website

> <WebsiteScanResult> scan_website(input)

Scan a website for malicious content and threats

Operation includes scanning the content of the URL for various types of malicious content and threats, including viruses and threats (including Phishing).

### Examples

```ruby
require 'time'
require 'cloudmersive-virus-scan-api-client'
# setup authorization
CloudmersiveVirusScanApiClient.configure do |config|
  # Configure API key authorization: Apikey
  config.api_key['Apikey'] = 'YOUR API KEY'
  # Uncomment the following line to set a prefix for the API key, e.g. 'Bearer' (defaults to nil)
  # config.api_key_prefix['Apikey'] = 'Bearer'
end

api_instance = CloudmersiveVirusScanApiClient::ScanApi.new
input = CloudmersiveVirusScanApiClient::WebsiteScanRequest.new # WebsiteScanRequest | 

begin
  # Scan a website for malicious content and threats
  result = api_instance.scan_website(input)
  p result
rescue CloudmersiveVirusScanApiClient::ApiError => e
  puts "Error when calling ScanApi->scan_website: #{e}"
end
```

#### Using the scan_website_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<WebsiteScanResult>, Integer, Hash)> scan_website_with_http_info(input)

```ruby
begin
  # Scan a website for malicious content and threats
  data, status_code, headers = api_instance.scan_website_with_http_info(input)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <WebsiteScanResult>
rescue CloudmersiveVirusScanApiClient::ApiError => e
  puts "Error when calling ScanApi->scan_website_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **input** | [**WebsiteScanRequest**](WebsiteScanRequest.md) |  |  |

### Return type

[**WebsiteScanResult**](WebsiteScanResult.md)

### Authorization

[Apikey](../README.md#Apikey)

### HTTP request headers

- **Content-Type**: application/json, text/json, application/xml, text/xml, application/x-www-form-urlencoded
- **Accept**: application/json, text/json, application/xml, text/xml

