---
# generated by https://github.com/hashicorp/terraform-plugin-docs
page_title: "thousandeyes_bgp Resource - terraform-provider-thousandeyes"
subcategory: ""
description: |-
  
---

# thousandeyes_bgp (Resource)





<!-- schema generated by tfplugindocs -->
## Schema

### Required

- `prefix` (String) BGP network address prefix
- `test_name` (String) Name of Test

### Optional

- `alert_rules` (Block Set) Get ruleId from /alert-rules endpoint. If alertsEnabled is set to 'true' and alertRules is not included in a creation/update query, applicable defaults will be used (see [below for nested schema](#nestedblock--alert_rules))
- `alerts_enabled` (Boolean) Set to 'true' to enable alerts, or 'false' to disable alerts. Defaults to 'true'
- `bgp_monitors` (Block List) Array of BGP Monitor objects (see [below for nested schema](#nestedblock--bgp_monitors))
- `description` (String) defaults to empty string
- `enabled` (Boolean) Enable the test.
- `groups` (Block List) array of label objects (see [below for nested schema](#nestedblock--groups))
- `include_covered_prefixes` (Boolean) Include queries for subprefixes detected under this prefix.
- `shared_with_accounts` (Block List) Array of DNS Server objects {“serverName”: “fqdn of server”} (see [below for nested schema](#nestedblock--shared_with_accounts))
- `use_public_bgp` (Boolean) Automatically add all available Public BGP Monitors.

### Read-Only

- `api_links` (List of Object) Self links to endpoint to pull test metadata, and data links to endpoint for test data (see [below for nested schema](#nestedatt--api_links))
- `created_by` (String) created by user
- `created_date` (String) date of creation
- `id` (String) The ID of this resource.
- `live_share` (Boolean) Set to 'true' for a test shared with your account group, or to 'false' for a normal test
- `modified_by` (String) Last modified by user
- `modified_date` (String) Last modified by date; shown in UTC
- `saved_event` (Boolean) Set to 'true' for a saved event, or to 'false' for a normal test.
- `test_id` (Number) Unique ID of test
- `type` (String) Type of test

<a id="nestedblock--alert_rules"></a>
### Nested Schema for `alert_rules`

Optional:

- `rule_id` (Number) Rule ID


<a id="nestedblock--bgp_monitors"></a>
### Nested Schema for `bgp_monitors`

Required:

- `monitor_id` (Number) Monitor ID

Optional:

- `ip_address` (String)
- `monitor_name` (String)
- `monitor_type` (String)
- `network` (String)


<a id="nestedblock--groups"></a>
### Nested Schema for `groups`

Required:

- `group_id` (Number) Unique ID of the label

Optional:

- `agents` (Block List) agents to use (see [below for nested schema](#nestedblock--groups--agents))
- `name` (String) Name of the label
- `tests` (Block List) List of tests (see [below for nested schema](#nestedblock--groups--tests))
- `type` (String) Type of label (tests, agents, endpoint_tests, or endpoint_agents

Read-Only:

- `builtin` (Boolean) Set to 'true' to use built-in labels, or to 'false' to use user-created labels. Note that built-in labels are read-only

<a id="nestedblock--groups--agents"></a>
### Nested Schema for `groups.agents`

Optional:

- `agent_id` (Number) agent id


<a id="nestedblock--groups--tests"></a>
### Nested Schema for `groups.tests`

Optional:

- `test_id` (Number) test id



<a id="nestedblock--shared_with_accounts"></a>
### Nested Schema for `shared_with_accounts`

Required:

- `aid` (Number) Account group ID

Optional:

- `name` (String) Name of account


<a id="nestedatt--api_links"></a>
### Nested Schema for `api_links`

Read-Only:

- `href` (String)
- `rel` (String)

