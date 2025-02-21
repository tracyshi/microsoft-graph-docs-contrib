---
title: "appliedConditionalAccessPolicy resource type"
description: "Indicates the attributes related to applied conditional access policy or policies that are triggered by the corresponding sign-in activity."
ms.localizationpriority: medium
author: "egreenberg14"
ms.prod: "identity-and-access-reports"
doc_type: resourcePageType
---

# appliedConditionalAccessPolicy resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Indicates the attributes related to applied conditional access policy or policies that are triggered by the corresponding sign-in activity.

## Properties

| Property     | Type        | Description |
|:-------------|:------------|:------------|
|authenticationStrength|[authenticationStrength](authenticationstrength.md)| The custom authentication strength enforced in a Conditional Access policy.|
|conditionsNotSatisfied|conditionalAccessConditions|Refers to the conditional access policy conditions that are not satisfied. The possible values are: `none`, `application`, `users`, `devicePlatform`, `location`, `clientType`, `signInRisk`, `userRisk`, `time`, `deviceState`, `client`,`ipAddressSeenByAzureAD`,`ipAddressSeenByResourceProvider`,`unknownFutureValue`,`servicePrincipals`,`servicePrincipalRisk`, `authenticationFlows`, `insiderRisk` . Note that you must use the `Prefer: include-unknown-enum-members` request header to get the following values in this [evolvable enum](/graph/best-practices-concept#handling-future-members-in-evolvable-enumerations): `servicePrincipals`,`servicePrincipalRisk`, `authenticationFlows`, `insiderRisk`. **conditionalAccessConditions** is a multi-valued enumeration and the property can contain multiple values in a comma-separated list.|
|conditionsSatisfied|conditionalAccessConditions|Refers to the conditional access policy conditions that are satisfied. The possible values are: `none`, `application`, `users`, `devicePlatform`, `location`, `clientType`, `signInRisk`, `userRisk`, `time`, `deviceState`, `client`,`ipAddressSeenByAzureAD`,`ipAddressSeenByResourceProvider`,`unknownFutureValue`,`servicePrincipals`,`servicePrincipalRisk`, `authenticationFlows`, `insiderRisk`. Note that you must use the `Prefer: include-unknown-enum-members` request header to get the following values in this [evolvable enum](/graph/best-practices-concept#handling-future-members-in-evolvable-enumerations): `servicePrincipals`,`servicePrincipalRisk`, `authenticationFlows`, `insiderRisk`. **conditionalAccessConditions** is a multi-valued enumeration and the property can contain multiple values in a comma-separated list.|
|displayName|String|Name of the conditional access policy.|
|enforcedGrantControls|String collection|Refers to the grant controls enforced by the conditional access policy (example: "Require multi-factor authentication").|
|enforcedSessionControls|String collection|Refers to the session controls enforced by the conditional access policy (example: "Require app enforced controls").|
|excludeRulesSatisfied|[conditionalAccessRuleSatisfied](conditionalaccessrulesatisfied.md) collection|List of key-value pairs containing each matched exclude condition in the conditional access policy. Example: `[{"devicePlatform" : "DevicePlatform"}]` means the policy didn't apply, because the DevicePlatform condition was a match.|
|id|String|Identifier of the conditional access policy.|
|includeRulesSatisfied|[conditionalAccessRuleSatisfied](conditionalaccessrulesatisfied.md) collection|List of key-value pairs containing each matched include condition in the conditional access policy. Example: `[{ "application" : "AllApps"}, {"users": "Group"}]`, meaning Application condition was a match because AllApps are included *and* Users condition was a match because the user was part of the included Group rule.|
|result|appliedConditionalAccessPolicyResult| Indicates the result of the CA policy that was triggered. Possible values are: `success`, `failure`, `notApplied` (Policy isn't applied because policy conditions were not met),`notEnabled` (This is due to the policy in disabled state), `unknown`, `unknownFutureValue`, `reportOnlySuccess`, `reportOnlyFailure`, `reportOnlyNotApplied`, `reportOnlyInterrupted`. Note that you must use the `Prefer: include-unknown-enum-members` request header to get the following values in this [evolvable enum](/graph/best-practices-concept#handling-future-members-in-evolvable-enumerations): `reportOnlySuccess`, `reportOnlyFailure`, `reportOnlyNotApplied`, `reportOnlyInterrupted`.|
|sessionControlsNotSatisfied|String collection|Refers to the session controls that a sign-in activity did not satisfy. (Example: `Application enforced Restrictions`).|




## JSON representation

The following is a JSON representation of the resource.

<!-- {
  "blockType": "resource",
  "optionalProperties": [
  ],
  "@odata.type": "microsoft.graph.appliedConditionalAccessPolicy"
}-->

```json
{
  "@odata.type": "#microsoft.graph.appliedConditionalAccessPolicy",
  "id": "String (identifier)",
  "authenticationStrength": {"@odata.type": "microsoft.graph.authenticationStrength"},
  "displayName": "String",
  "enforcedGrantControls": [
    "String"
  ],
  "enforcedSessionControls": [
    "String"
  ],
  "conditionsSatisfied": "String",
  "conditionsNotSatisfied": "String",
  "includeRulesSatisfied": [
    {
      "@odata.type": "microsoft.graph.conditionalAccessRuleSatisfied"
    }
  ],
  "excludeRulesSatisfied": [
    {
      "@odata.type": "microsoft.graph.conditionalAccessRuleSatisfied"
    }
  ],
  "result": "String"
}
```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "appliedConditionalAccessPolicy resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->
