---
date: 2017-03-13T14:32:26Z
title: Create a Security Policy
weight: 3
menu:
    main: 
        parent: "Tutorials"
---


A security policy encapsulates several options that can be applied to a key. It acts as a template that can override individual sections of an API key (or identity) in Tyk.

See [What is a Security Policy?](/docs/getting-started/key-concepts/what-is-a-security-policy/) for more details.

{{< tabs_start >}}
{{< tab_start "Cloud" >}}
{{< include "create-security-policy-include" >}}

{{< tab_end >}}
{{< tab_start "Multi-Cloud" >}}

> **NOTE**: Tyk Multi-Cloud has superseded our Hybrid offering. See [Tyk Multi-Cloud](https://tyk.io/api-gateway/cloud/#multi-cloud) for more details. You can get a free 30 day trial of Tyk Multi-Cloud.

A security policy for Tyk Multi-Cloud is the same as one with Tyk Cloud and will be mirrored in your Multi-Cloud Gateways, follow the instructions below to generate a policy, within a few seconds, that policy will be available in your Multi-Cloud Gateways locally.

{{< include "create-security-policy-include" >}}
{{< tab_end >}}
{{< tab_start "On-Premises" >}}
{{< include "create-security-policy-include" >}}
{{< tab_end >}}
{{< tab_start "Community Edition" >}}
## <a name="create-a-file-based-policy"></a>Tutorial: Create a Policy with the Gateway API

Adding a policy to a Community Edition Tyk Gateway is very easy. Polices are loaded into memory on load and so need to be specified in advanced in a file called `policies.json`. To add a policy, simply create or edit the `/policies/policies.json` file and add the policy object to the object array:

```{.copyWrapper}
{
  "POLICYID": {
    "access_rights": {
      "{API-ID}": {
        "allowed_urls": [],
        "api_id": "{API-ID}",
        "api_name": "{API-NAME}",
        "versions": [
            "Default"
        ]
    }
  },
  "active": true,
  "name": "POLICY NAME",
  "rate": 100,
  "per": 1,
  "quota_max": 10000,
  "quota_renewal_rate": 3600,
  "tags": ["Startup Users"]
  }
}
```

The above creates a new policy with a policy ID that you can define, with the rate limits, and security profile that grants access to the APIs listed in the `access_rights` section.
{{< tab_end >}}
{{< tabs_end >}}

