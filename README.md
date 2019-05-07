# ![LOGO](logo.png) ResourceManagementClient **flow**ground Connector

## Description

A generated **flow**ground connector for the ResourceManagementClient API (version 2018-05-01).

Generated from: https://api.apis.guru/v2/specs/azure.com/resources/2018-05-01/swagger.json<br/>
Generated at: 2019-05-07T17:38:48+03:00

## API Description

Provides operations for working with resources and resource groups.

## Authorization

Supported authorization schemes:
- OAuth2

For OAuth 2.0 you need to specify OAuth Client credentials as environment variables in the connector repository:
* `OAUTH_CLIENT_ID` - your OAuth client id
* `OAUTH_CLIENT_SECRET` - your OAuth client secret

## Actions

### Lists all of the available Microsoft.Resources REST API operations.

*Tags:* `Operations`

#### Input Parameters
* `api-version` - _required_ - The API version to use for this operation.

### Gets all resource providers for a subscription.

*Tags:* `Providers`

#### Input Parameters
* `$top` - _optional_ - The number of results to return. If null is passed returns all deployments.
* `$expand` - _optional_ - The properties to include in the results. For example, use &$expand=metadata in the query string to retrieve resource provider metadata. To include property aliases in response, use $expand=resourceTypes/aliases.
* `api-version` - _required_ - The API version to use for this operation.
* `subscriptionId` - _required_ - The ID of the target subscription.

### Get all the deployments for a subscription.

*Tags:* `Deployments`

#### Input Parameters
* `$filter` - _optional_ - The filter to apply on the operation. For example, you can use $filter=provisioningState eq '{state}'.
* `$top` - _optional_ - The number of results to get. If null is passed, returns all deployments.
* `api-version` - _required_ - The API version to use for this operation.
* `subscriptionId` - _required_ - The ID of the target subscription.

### Deletes a deployment from the deployment history.

> A template deployment that is currently running cannot be deleted. Deleting a template deployment removes the associated deployment operations. This is an asynchronous operation that returns a status of 202 until the template deployment is successfully deleted. The Location response header contains the URI that is used to obtain the status of the process. While the process is running, a call to the URI in the Location header returns a status of 202. When the process finishes, the URI in the Location header returns a status of 204 on success. If the asynchronous request failed, the URI in the Location header returns an error-level status code.

*Tags:* `Deployments`

#### Input Parameters
* `deploymentName` - _required_ - The name of the deployment to delete.
* `api-version` - _required_ - The API version to use for this operation.
* `subscriptionId` - _required_ - The ID of the target subscription.

### Gets a deployment.

*Tags:* `Deployments`

#### Input Parameters
* `deploymentName` - _required_ - The name of the deployment to get.
* `api-version` - _required_ - The API version to use for this operation.
* `subscriptionId` - _required_ - The ID of the target subscription.

### Checks whether the deployment exists.

*Tags:* `Deployments`

#### Input Parameters
* `deploymentName` - _required_ - The name of the deployment to check.
* `api-version` - _required_ - The API version to use for this operation.
* `subscriptionId` - _required_ - The ID of the target subscription.

### Deploys resources at subscription scope.

> You can provide the template and parameters directly in the request or link to JSON files.

*Tags:* `Deployments`

#### Input Parameters
* `deploymentName` - _required_ - The name of the deployment.
* `api-version` - _required_ - The API version to use for this operation.
* `subscriptionId` - _required_ - The ID of the target subscription.

### Cancels a currently running template deployment.

> You can cancel a deployment only if the provisioningState is Accepted or Running. After the deployment is canceled, the provisioningState is set to Canceled. Canceling a template deployment stops the currently running template deployment and leaves the resources partially deployed.

*Tags:* `Deployments`

#### Input Parameters
* `deploymentName` - _required_ - The name of the deployment to cancel.
* `api-version` - _required_ - The API version to use for this operation.
* `subscriptionId` - _required_ - The ID of the target subscription.

### Exports the template used for specified deployment.

*Tags:* `Deployments`

#### Input Parameters
* `deploymentName` - _required_ - The name of the deployment from which to get the template.
* `api-version` - _required_ - The API version to use for this operation.
* `subscriptionId` - _required_ - The ID of the target subscription.

### Gets all deployments operations for a deployment.

*Tags:* `DeploymentOperations`

#### Input Parameters
* `deploymentName` - _required_ - The name of the deployment with the operation to get.
* `$top` - _optional_ - The number of results to return.
* `api-version` - _required_ - The API version to use for this operation.
* `subscriptionId` - _required_ - The ID of the target subscription.

### Gets a deployments operation.

*Tags:* `DeploymentOperations`

#### Input Parameters
* `deploymentName` - _required_ - The name of the deployment.
* `operationId` - _required_ - The ID of the operation to get.
* `api-version` - _required_ - The API version to use for this operation.
* `subscriptionId` - _required_ - The ID of the target subscription.

### Validates whether the specified template is syntactically correct and will be accepted by Azure Resource Manager..

*Tags:* `Deployments`

#### Input Parameters
* `deploymentName` - _required_ - The name of the deployment.
* `api-version` - _required_ - The API version to use for this operation.
* `subscriptionId` - _required_ - The ID of the target subscription.

### Gets the specified resource provider.

*Tags:* `Providers`

#### Input Parameters
* `$expand` - _optional_ - The $expand query parameter. For example, to include property aliases in response, use $expand=resourceTypes/aliases.
* `resourceProviderNamespace` - _required_ - The namespace of the resource provider.
* `api-version` - _required_ - The API version to use for this operation.
* `subscriptionId` - _required_ - The ID of the target subscription.

### Registers a subscription with a resource provider.

*Tags:* `Providers`

#### Input Parameters
* `resourceProviderNamespace` - _required_ - The namespace of the resource provider to register.
* `api-version` - _required_ - The API version to use for this operation.
* `subscriptionId` - _required_ - The ID of the target subscription.

### Unregisters a subscription from a resource provider.

*Tags:* `Providers`

#### Input Parameters
* `resourceProviderNamespace` - _required_ - The namespace of the resource provider to unregister.
* `api-version` - _required_ - The API version to use for this operation.
* `subscriptionId` - _required_ - The ID of the target subscription.

### Get all the resources for a resource group.

*Tags:* `ResourceGroups`

#### Input Parameters
* `resourceGroupName` - _required_ - The resource group with the resources to get.
* `$filter` - _optional_ - The filter to apply on the operation.<br><br>The properties you can use for eq (equals) or ne (not equals) are: location, resourceType, name, resourceGroup, identity, identity/principalId, plan, plan/publisher, plan/product, plan/name, plan/version, and plan/promotionCode.<br><br>For example, to filter by a resource type, use: $filter=resourceType eq 'Microsoft.Network/virtualNetworks'<br><br>You can use substringof(value, property) in the filter. The properties you can use for substring are: name and resourceGroup.<br><br>For example, to get all resources with 'demo' anywhere in the name, use: $filter=substringof('demo', name)<br><br>You can link more than one substringof together by adding and/or operators.<br><br>You can filter by tag names and values. For example, to filter for a tag name and value, use $filter=tagName eq 'tag1' and tagValue eq 'Value1'<br><br>You can use some properties together when filtering. The combinations you can use are: substringof and/or resourceType, plan and plan/publisher and plan/name, identity and identity/principalId.
* `$expand` - _optional_ - The $expand query parameter. You can expand createdTime and changedTime. For example, to expand both properties, use $expand=changedTime,createdTime
* `$top` - _optional_ - The number of results to return. If null is passed, returns all resources.
* `api-version` - _required_ - The API version to use for this operation.
* `subscriptionId` - _required_ - The ID of the target subscription.

### Moves resources from one resource group to another resource group.

> The resources to move must be in the same source resource group. The target resource group may be in a different subscription. When moving resources, both the source group and the target group are locked for the duration of the operation. Write and delete operations are blocked on the groups until the move completes.

*Tags:* `Resources`

#### Input Parameters
* `sourceResourceGroupName` - _required_ - The name of the resource group containing the resources to move.
* `api-version` - _required_ - The API version to use for this operation.
* `subscriptionId` - _required_ - The ID of the target subscription.

### Validates whether resources can be moved from one resource group to another resource group.

> This operation checks whether the specified resources can be moved to the target. The resources to move must be in the same source resource group. The target resource group may be in a different subscription. If validation succeeds, it returns HTTP response code 204 (no content). If validation fails, it returns HTTP response code 409 (Conflict) with an error message. Retrieve the URL in the Location header value to check the result of the long-running operation.

*Tags:* `Resources`

#### Input Parameters
* `sourceResourceGroupName` - _required_ - The name of the resource group containing the resources to validate for move.
* `api-version` - _required_ - The API version to use for this operation.
* `subscriptionId` - _required_ - The ID of the target subscription.

### Gets all the resource groups for a subscription.

*Tags:* `ResourceGroups`

#### Input Parameters
* `$filter` - _optional_ - The filter to apply on the operation.<br><br>You can filter by tag names and values. For example, to filter for a tag name and value, use $filter=tagName eq 'tag1' and tagValue eq 'Value1'
* `$top` - _optional_ - The number of results to return. If null is passed, returns all resource groups.
* `api-version` - _required_ - The API version to use for this operation.
* `subscriptionId` - _required_ - The ID of the target subscription.

### Deletes a resource group.

> When you delete a resource group, all of its resources are also deleted. Deleting a resource group deletes all of its template deployments and currently stored operations.

*Tags:* `ResourceGroups`

#### Input Parameters
* `resourceGroupName` - _required_ - The name of the resource group to delete. The name is case insensitive.
* `api-version` - _required_ - The API version to use for this operation.
* `subscriptionId` - _required_ - The ID of the target subscription.

### Gets a resource group.

*Tags:* `ResourceGroups`

#### Input Parameters
* `resourceGroupName` - _required_ - The name of the resource group to get. The name is case insensitive.
* `api-version` - _required_ - The API version to use for this operation.
* `subscriptionId` - _required_ - The ID of the target subscription.

### Checks whether a resource group exists.

*Tags:* `ResourceGroups`

#### Input Parameters
* `resourceGroupName` - _required_ - The name of the resource group to check. The name is case insensitive.
* `api-version` - _required_ - The API version to use for this operation.
* `subscriptionId` - _required_ - The ID of the target subscription.

### Updates a resource group.

> Resource groups can be updated through a simple PATCH operation to a group address. The format of the request is the same as that for creating a resource group. If a field is unspecified, the current value is retained.

*Tags:* `ResourceGroups`

#### Input Parameters
* `resourceGroupName` - _required_ - The name of the resource group to update. The name is case insensitive.
* `api-version` - _required_ - The API version to use for this operation.
* `subscriptionId` - _required_ - The ID of the target subscription.

### Creates or updates a resource group.

*Tags:* `ResourceGroups`

#### Input Parameters
* `resourceGroupName` - _required_ - The name of the resource group to create or update. Can include alphanumeric, underscore, parentheses, hyphen, period (except at end), and Unicode characters that match the allowed characters.
* `api-version` - _required_ - The API version to use for this operation.
* `subscriptionId` - _required_ - The ID of the target subscription.

### Gets all deployments operations for a deployment.

*Tags:* `DeploymentOperations`

#### Input Parameters
* `resourceGroupName` - _required_ - The name of the resource group. The name is case insensitive.
* `deploymentName` - _required_ - The name of the deployment with the operation to get.
* `$top` - _optional_ - The number of results to return.
* `api-version` - _required_ - The API version to use for this operation.
* `subscriptionId` - _required_ - The ID of the target subscription.

### Gets a deployments operation.

*Tags:* `DeploymentOperations`

#### Input Parameters
* `resourceGroupName` - _required_ - The name of the resource group. The name is case insensitive.
* `deploymentName` - _required_ - The name of the deployment.
* `operationId` - _required_ - The ID of the operation to get.
* `api-version` - _required_ - The API version to use for this operation.
* `subscriptionId` - _required_ - The ID of the target subscription.

### Captures the specified resource group as a template.

*Tags:* `ResourceGroups`

#### Input Parameters
* `resourceGroupName` - _required_ - The name of the resource group to export as a template.
* `api-version` - _required_ - The API version to use for this operation.
* `subscriptionId` - _required_ - The ID of the target subscription.

### Get all the deployments for a resource group.

*Tags:* `Deployments`

#### Input Parameters
* `resourceGroupName` - _required_ - The name of the resource group with the deployments to get. The name is case insensitive.
* `$filter` - _optional_ - The filter to apply on the operation. For example, you can use $filter=provisioningState eq '{state}'.
* `$top` - _optional_ - The number of results to get. If null is passed, returns all deployments.
* `api-version` - _required_ - The API version to use for this operation.
* `subscriptionId` - _required_ - The ID of the target subscription.

### Deletes a deployment from the deployment history.

> A template deployment that is currently running cannot be deleted. Deleting a template deployment removes the associated deployment operations. Deleting a template deployment does not affect the state of the resource group. This is an asynchronous operation that returns a status of 202 until the template deployment is successfully deleted. The Location response header contains the URI that is used to obtain the status of the process. While the process is running, a call to the URI in the Location header returns a status of 202. When the process finishes, the URI in the Location header returns a status of 204 on success. If the asynchronous request failed, the URI in the Location header returns an error-level status code.

*Tags:* `Deployments`

#### Input Parameters
* `resourceGroupName` - _required_ - The name of the resource group with the deployment to delete. The name is case insensitive.
* `deploymentName` - _required_ - The name of the deployment to delete.
* `api-version` - _required_ - The API version to use for this operation.
* `subscriptionId` - _required_ - The ID of the target subscription.

### Gets a deployment.

*Tags:* `Deployments`

#### Input Parameters
* `resourceGroupName` - _required_ - The name of the resource group. The name is case insensitive.
* `deploymentName` - _required_ - The name of the deployment to get.
* `api-version` - _required_ - The API version to use for this operation.
* `subscriptionId` - _required_ - The ID of the target subscription.

### Checks whether the deployment exists.

*Tags:* `Deployments`

#### Input Parameters
* `resourceGroupName` - _required_ - The name of the resource group with the deployment to check. The name is case insensitive.
* `deploymentName` - _required_ - The name of the deployment to check.
* `api-version` - _required_ - The API version to use for this operation.
* `subscriptionId` - _required_ - The ID of the target subscription.

### Deploys resources to a resource group.

> You can provide the template and parameters directly in the request or link to JSON files.

*Tags:* `Deployments`

#### Input Parameters
* `resourceGroupName` - _required_ - The name of the resource group to deploy the resources to. The name is case insensitive. The resource group must already exist.
* `deploymentName` - _required_ - The name of the deployment.
* `api-version` - _required_ - The API version to use for this operation.
* `subscriptionId` - _required_ - The ID of the target subscription.

### Cancels a currently running template deployment.

> You can cancel a deployment only if the provisioningState is Accepted or Running. After the deployment is canceled, the provisioningState is set to Canceled. Canceling a template deployment stops the currently running template deployment and leaves the resource group partially deployed.

*Tags:* `Deployments`

#### Input Parameters
* `resourceGroupName` - _required_ - The name of the resource group. The name is case insensitive.
* `deploymentName` - _required_ - The name of the deployment to cancel.
* `api-version` - _required_ - The API version to use for this operation.
* `subscriptionId` - _required_ - The ID of the target subscription.

### Exports the template used for specified deployment.

*Tags:* `Deployments`

#### Input Parameters
* `resourceGroupName` - _required_ - The name of the resource group. The name is case insensitive.
* `deploymentName` - _required_ - The name of the deployment from which to get the template.
* `api-version` - _required_ - The API version to use for this operation.
* `subscriptionId` - _required_ - The ID of the target subscription.

### Validates whether the specified template is syntactically correct and will be accepted by Azure Resource Manager..

*Tags:* `Deployments`

#### Input Parameters
* `resourceGroupName` - _required_ - The name of the resource group the template will be deployed to. The name is case insensitive.
* `deploymentName` - _required_ - The name of the deployment.
* `api-version` - _required_ - The API version to use for this operation.
* `subscriptionId` - _required_ - The ID of the target subscription.

### Deletes a resource.

*Tags:* `Resources`

#### Input Parameters
* `resourceGroupName` - _required_ - The name of the resource group that contains the resource to delete. The name is case insensitive.
* `resourceProviderNamespace` - _required_ - The namespace of the resource provider.
* `parentResourcePath` - _required_ - The parent resource identity.
* `resourceType` - _required_ - The resource type.
* `resourceName` - _required_ - The name of the resource to delete.
* `api-version` - _required_ - The API version to use for the operation.
* `subscriptionId` - _required_ - The ID of the target subscription.

### Gets a resource.

*Tags:* `Resources`

#### Input Parameters
* `resourceGroupName` - _required_ - The name of the resource group containing the resource to get. The name is case insensitive.
* `resourceProviderNamespace` - _required_ - The namespace of the resource provider.
* `parentResourcePath` - _required_ - The parent resource identity.
* `resourceType` - _required_ - The resource type of the resource.
* `resourceName` - _required_ - The name of the resource to get.
* `api-version` - _required_ - The API version to use for the operation.
* `subscriptionId` - _required_ - The ID of the target subscription.

### Checks whether a resource exists.

*Tags:* `Resources`

#### Input Parameters
* `resourceGroupName` - _required_ - The name of the resource group containing the resource to check. The name is case insensitive.
* `resourceProviderNamespace` - _required_ - The resource provider of the resource to check.
* `parentResourcePath` - _required_ - The parent resource identity.
* `resourceType` - _required_ - The resource type.
* `resourceName` - _required_ - The name of the resource to check whether it exists.
* `api-version` - _required_ - The API version to use for the operation.
* `subscriptionId` - _required_ - The ID of the target subscription.

### Updates a resource.

*Tags:* `Resources`

#### Input Parameters
* `resourceGroupName` - _required_ - The name of the resource group for the resource. The name is case insensitive.
* `resourceProviderNamespace` - _required_ - The namespace of the resource provider.
* `parentResourcePath` - _required_ - The parent resource identity.
* `resourceType` - _required_ - The resource type of the resource to update.
* `resourceName` - _required_ - The name of the resource to update.
* `api-version` - _required_ - The API version to use for the operation.
* `subscriptionId` - _required_ - The ID of the target subscription.

### Creates a resource.

*Tags:* `Resources`

#### Input Parameters
* `resourceGroupName` - _required_ - The name of the resource group for the resource. The name is case insensitive.
* `resourceProviderNamespace` - _required_ - The namespace of the resource provider.
* `parentResourcePath` - _required_ - The parent resource identity.
* `resourceType` - _required_ - The resource type of the resource to create.
* `resourceName` - _required_ - The name of the resource to create.
* `api-version` - _required_ - The API version to use for the operation.
* `subscriptionId` - _required_ - The ID of the target subscription.

### Get all the resources in a subscription.

*Tags:* `Resources`

#### Input Parameters
* `$filter` - _optional_ - The filter to apply on the operation.<br><br>The properties you can use for eq (equals) or ne (not equals) are: location, resourceType, name, resourceGroup, identity, identity/principalId, plan, plan/publisher, plan/product, plan/name, plan/version, and plan/promotionCode.<br><br>For example, to filter by a resource type, use: $filter=resourceType eq 'Microsoft.Network/virtualNetworks'<br><br>You can use substringof(value, property) in the filter. The properties you can use for substring are: name and resourceGroup.<br><br>For example, to get all resources with 'demo' anywhere in the name, use: $filter=substringof('demo', name)<br><br>You can link more than one substringof together by adding and/or operators.<br><br>You can filter by tag names and values. For example, to filter for a tag name and value, use $filter=tagName eq 'tag1' and tagValue eq 'Value1'<br><br>You can use some properties together when filtering. The combinations you can use are: substringof and/or resourceType, plan and plan/publisher and plan/name, identity and identity/principalId.
* `$expand` - _optional_ - The $expand query parameter. You can expand createdTime and changedTime. For example, to expand both properties, use $expand=changedTime,createdTime
* `$top` - _optional_ - The number of results to return. If null is passed, returns all resource groups.
* `api-version` - _required_ - The API version to use for this operation.
* `subscriptionId` - _required_ - The ID of the target subscription.

### Gets the names and values of all resource tags that are defined in a subscription.

*Tags:* `Tags`

#### Input Parameters
* `api-version` - _required_ - The API version to use for this operation.
* `subscriptionId` - _required_ - The ID of the target subscription.

### Deletes a tag from the subscription.

> You must remove all values from a resource tag before you can delete it.

*Tags:* `Tags`

#### Input Parameters
* `tagName` - _required_ - The name of the tag.
* `api-version` - _required_ - The API version to use for this operation.
* `subscriptionId` - _required_ - The ID of the target subscription.

### Creates a tag in the subscription.

> The tag name can have a maximum of 512 characters and is case insensitive. Tag names created by Azure have prefixes of microsoft, azure, or windows. You cannot create tags with one of these prefixes.

*Tags:* `Tags`

#### Input Parameters
* `tagName` - _required_ - The name of the tag to create.
* `api-version` - _required_ - The API version to use for this operation.
* `subscriptionId` - _required_ - The ID of the target subscription.

### Deletes a tag value.

*Tags:* `Tags`

#### Input Parameters
* `tagName` - _required_ - The name of the tag.
* `tagValue` - _required_ - The value of the tag to delete.
* `api-version` - _required_ - The API version to use for this operation.
* `subscriptionId` - _required_ - The ID of the target subscription.

### Creates a tag value. The name of the tag must already exist.

*Tags:* `Tags`

#### Input Parameters
* `tagName` - _required_ - The name of the tag.
* `tagValue` - _required_ - The value of the tag to create.
* `api-version` - _required_ - The API version to use for this operation.
* `subscriptionId` - _required_ - The ID of the target subscription.

### Deletes a resource by ID.

*Tags:* `Resources`

#### Input Parameters
* `resourceId` - _required_ - The fully qualified ID of the resource, including the resource name and resource type. Use the format, /subscriptions/{guid}/resourceGroups/{resource-group-name}/{resource-provider-namespace}/{resource-type}/{resource-name}
* `api-version` - _required_ - The API version to use for the operation.

### Gets a resource by ID.

*Tags:* `Resources`

#### Input Parameters
* `resourceId` - _required_ - The fully qualified ID of the resource, including the resource name and resource type. Use the format, /subscriptions/{guid}/resourceGroups/{resource-group-name}/{resource-provider-namespace}/{resource-type}/{resource-name}
* `api-version` - _required_ - The API version to use for the operation.

### Checks by ID whether a resource exists.

*Tags:* `Resources`

#### Input Parameters
* `resourceId` - _required_ - The fully qualified ID of the resource, including the resource name and resource type. Use the format, /subscriptions/{guid}/resourceGroups/{resource-group-name}/{resource-provider-namespace}/{resource-type}/{resource-name}
* `api-version` - _required_ - The API version to use for the operation.

### Updates a resource by ID.

*Tags:* `Resources`

#### Input Parameters
* `resourceId` - _required_ - The fully qualified ID of the resource, including the resource name and resource type. Use the format, /subscriptions/{guid}/resourceGroups/{resource-group-name}/{resource-provider-namespace}/{resource-type}/{resource-name}
* `api-version` - _required_ - The API version to use for the operation.

### Create a resource by ID.

*Tags:* `Resources`

#### Input Parameters
* `resourceId` - _required_ - The fully qualified ID of the resource, including the resource name and resource type. Use the format, /subscriptions/{guid}/resourceGroups/{resource-group-name}/{resource-provider-namespace}/{resource-type}/{resource-name}
* `api-version` - _required_ - The API version to use for the operation.

## License

**flow**ground :- Telekom iPaaS / azure-com-resources-connector<br/>
Copyright © 2019, [Deutsche Telekom AG](https://www.telekom.de)<br/>
contact: flowground@telekom.de

All files of this connector are licensed under the Apache 2.0 License. For details
see the file LICENSE on the toplevel directory.
