# terraform-mcp-model


ReadMe
🔗 What’s Already Built
✅ gRPC based MCP server for scraping and serving TFE release data
✅ LLaMA-based local integration for summarization with API endpoint/ask-llama  
✅ gRPC client which can present the data returned from gRPC server 
✅ Protobuf-defined data model (MCP-style)
✅ Basic API tested and functional 
Added this-
✅ Integration with Hugging Face API for Text Summarization

🛠️ What We Plan to Build
REST endpoint /ask-llama or /summarize/:version
Cache layer for LLM results(optional)
Optional IBM Granite/OpenAI-based LLM alternative
Webhook/Slack/Email integration for proactive alerts
History tracking / conversational context
Optional UI frontend (React)
Interactive Speech to Text AI BOT.




Steps:

#Install local llama with model version 3.2 ,

make sure it is running on http://localhost:11434/
 ollama list   

#MCP server 
#go to terraform-mcp/server
#go run main.go 
MCP server is running 9090 and HTTPServer connecting to local Llama is on 8081


for MCP client
go run client/main.g


to geenrate the llama reponse connectd to MCP server
curl -X POST http://localhost:8081/ask-llama \
  -H "Content-Type: application/json" \
  -d '{"prompt": "what is ther in Terraform  Version: v202405-1"}'




=======================================================
response on client will be

{"response":"Terraform version `v202405-1` includes several new features, improvements, and bug fixes compared to the previous versions. Here are some key changes:\n\n**New Features**\n\n1. **Support for Azure Kubernetes Service (AKS) management**: Terraform now supports managing AKS clusters using the `azurerm_kubernetes_cluster` resource.\n2. **Improved support for Amazon Web Services (AWS)**: The AWS provider has been updated to provide better support for AWS services, including improved support for EC2 instances, S3 buckets, and more.\n3. **Support for Google Cloud Platform (GCP) Service Directory**: Terraform now supports creating and managing Service Directory resources in GCP.\n4. **Support for Microsoft Azure Storage Blobs**: The `azurerm_storage_blob` resource has been updated to support blob storage in Azure.\n5. **Improved support for Kubernetes**: The `kubernetes` provider has been updated to provide better support for Kubernetes clusters, including improved support for node pools and more.\n\n**Improvements**\n\n1. **Performance improvements**: Terraform is now optimized for better performance, particularly when working with large numbers of resources.\n2. **Bug fixes**: Several bug fixes have been applied to address issues related to resource creation, state management, and more.\n3. **Improved error handling**: Terraform now provides improved error handling and reporting to help users diagnose issues more easily.\n\n**Changes**\n\n1. **Removed the `azurerm_resource_group` provider**: The `azurerm_resource_group` provider has been removed from Terraform, as it is no longer needed.\n2. **Updated the `aws_s3_bucket` resource**: The `aws_s3_bucket` resource now supports bucket policies and more.\n3. **Updated the `kubernetes` provider**: The `kubernetes` provider has been updated to provide better support for node pools and more.\n\n**Compatibility**\n\nTerraform version `v202405-1` is backwards compatible with previous versions, but users may encounter issues when working with older resources or providers that have changed significantly."}


======================================================= 
response from server
 - payload data for prompt  what is ther in Terraform  Version: v202405-1:


 ==========Summarization result from Hugging Face Summary API call  :======
 Terraform version `v202405-1 includes several new features, improvements, and bug fixes compared to the previous versions. The new features include support for Azure Kubernetes Service (AKS) management and improved support for Amazon Web Services (AWS)







 ---- Response from LLAMA :  ----
 Terraform version `v202405-1` includes several new features, improvements, and bug fixes compared to the previous versions. Here are some key changes:

**New Features**

1. **Support for Azure Kubernetes Service (AKS) management**: Terraform now supports managing AKS clusters using the `azurerm_kubernetes_cluster` resource.
2. **Improved support for Amazon Web Services (AWS)**: The AWS provider has been updated to provide better support for AWS services, including improved support for EC2 instances, S3 buckets, and more.
3. **Support for Google Cloud Platform (GCP) Service Directory**: Terraform now supports creating and managing Service Directory resources in GCP.
4. **Support for Microsoft Azure Storage Blobs**: The `azurerm_storage_blob` resource has been updated to support blob storage in Azure.
5. **Improved support for Kubernetes**: The `kubernetes` provider has been updated to provide better support for Kubernetes clusters, including improved support for node pools and more.

**Improvements**

1. **Performance improvements**: Terraform is now optimized for better performance, particularly when working with large numbers of resources.
2. **Bug fixes**: Several bug fixes have been applied to address issues related to resource creation, state management, and more.
3. **Improved error handling**: Terraform now provides improved error handling and reporting to help users diagnose issues more easily.

**Changes**

1. **Removed the `azurerm_resource_group` provider**: The `azurerm_resource_group` provider has been removed from Terraform, as it is no longer needed.
2. **Updated the `aws_s3_bucket` resource**: The `aws_s3_bucket` resource now supports bucket policies and more.
3. **Updated the `kubernetes` provider**: The `kubernetes` provider has been updated to provide better support for node pools and more.

**Compatibility**

Terraform version `v202405-1` is backwards compatible with previous versions, but users may encounter issues when working with older resources or providers that have changed significantly.:



  
  
