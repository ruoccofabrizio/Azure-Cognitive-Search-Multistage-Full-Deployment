# Azure-Cognitive-Search-Multistage-Full-Deployment

Azure DevOps YAML pipeline to deploy all Azure Cognitive Search artifacts (data source, index, indexers, skillset) in multiple environments (DEV, TEST, PROD)
The scripts creates specified artifacts or updates existing resources. Field removal for indexes is not allowed.

![Azure DevOps Stages](https://github.com/ruoccofabrizio/Azure-Cognitive-Search-DevOps-Multistage-Index/blob/main/images/stages.PNG)
![Azure DevOps Jobs](https://github.com/ruoccofabrizio/Azure-Cognitive-Search-DevOps-Multistage-Index/blob/main/images/jobs.PNG)



| Azure DevOps Variable                          | Value                                                      | Note                                           |
|------------------------------------------------|---------------------------------------------------------|------------------------------------------|
| --ENV_RESOURCE_GROUP          			| Azure Cognitive Search Resource Group              								 | Required					    |
| --ENV_SERVICE_NAME      			| Azure Cognitive Search Service  								 | Required                        |
| --ENV_CONNECTION_STRING            			| Connection string to the datasource to be created			 | Required|
| --ENV_COGNITIVE_SERVICES_KEY          			| Cognitive Services key for content enrichment | Required if using Skillset with Cognitive Services|
| --DATA_SOURCE      			| Data source for Azure Cognitive Search processing  								 | Required |
| --INDEX_NAME      			| Index for Azure Cognitive Search  								 | Required |
| --INDEXER      			| Indexer for Azure Cognitive Search processing  								 | Optional - Set variable to empty value to skip indexer deployment |
| --SKILLSET_NAME      			| Skillset for Azure Cognitive Search processing  								 | Optional - Set variable to empty value to skip skillset deployment|

Please substitute ENV with required environment when setting up the variables in the Azure DevOps YAML Pipeline editor (ENV -> DEV / ENV -> TEST / ENV -> PROD)
