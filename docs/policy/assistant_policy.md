# Policies for Smart Assitant 

To successfully enable and operate Smart Assistant within Smart VIU, the following policies and configurations must be ensured:

## Enabling Smart Assitant 

Following policies are used to enabled Smart Assiatant:

### Enabling Smart Assistant Policy

To enable or disable the Smart Assistant feature, configure the following policy:

| polcod                  | polvar       | polval       | rtnum1                        |
|-------------------------|--------------|--------------|---------------------------------|
| USR-SMARTBASE     | UC-APP-CONG   | ENABLED            |1  | 

  -  `rtnum1=1` → enabled (ON)
-  `rtnum=0` → disabled (OFF)

### Tenant Key Setup Policy

To configure the tenant key for Smart Assistant, use the following policy:

| polcod                  | polvar       | polval       | rtstr1                       |
|-------------------------|--------------|--------------|---------------------------------|
| USR-SMARTBASE     | UC-APP-CONG   | SA-TENANT-KEY            |Tenant ID   | 

### Server Setup Policy

To configure the Smart Assistant server connection, use the following policy:

| polcod                  | polvar       | polval       | rtstr1                       |
|-------------------------|--------------|--------------|---------------------------------|
| USR-SMARTBASE     | UC-APP-CONG   | SERVER_ID            | Server id / Connection id   |

**Server Configuration**

1. Open the **Smart Apps Integration** section from [Smart Apps](https://apps.smart-is.com/). 

2. Create a new system configuration.
3. Configure the required connection settings.
4. Copy the generated connection ID.

<div style="text-align: left;">
    <img src="./Attachments/integration.png"
        alt="undirectedmenu"
        style="height: 200px; margin: auto; display: block; cursor: zoom-in;
                border: 2px solid #000000; border-radius: 4px;"
        onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
        ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
    </div>

5. Add the required service links in the API Endpoint URL section.

### URL Setup Policy 

To configure the Smart Assistant URL, use the following policy:

| polcod                  | polvar       | polval       | rtstr1                       |
|-------------------------|--------------|--------------|---------------------------------|
| USR-SMARTBASE     | UC-APP-CONG   | URL            | https://ois-ai-wms.azurewebsites.net/v1/warehouse/   |

## LLM Configuration Policies

These policies are used to configure the external Large Language Model (LLM) service. 

If these policies are not configured and enabled, the system may default to the organization's configured LLM service. 

To ensure that AI requests are routed through the client's own LLM provider, these policies must be populated with the client's credentials and endpoint details and then enabled.


### LLM_API_KEY

Stores the API key used to authenticate requests to the client's LLM service.

| polcod | polvar | polval | rtstr1 |
|---------|---------|---------|---------|
| USR-SMARTBASE | UC-APP-CONG | LLM_API_KEY | Client LLM API Key value |



### LLM_BASE_URL

Specifies the base URL of the client's LLM endpoint through which AI requests are routed.

| polcod | polvar | polval | rtstr1 |
|---------|---------|---------|---------|
| USR-SMARTBASE | UC-APP-CONG | LLM_BASE_URL |  Client LLM Endpoint URL value |


### LLM_MODEL

Defines the model that Smart Assistant will use for generating AI responses.

| polcod | polvar | polval | rtstr1 |
|---------|---------|---------|---------|
| USR-SMARTBASE | UC-APP-CONG | LLM_MODEL |  LLM Model Name |
    

### LLM_PROVIDER

Identifies the LLM provider (for example, OpenAI, Azure OpenAI, or another supported provider).

| polcod | polvar | polval | rtstr1 |
|---------|---------|---------|---------|
| USR-SMARTBASE | UC-APP-CONG | LLM_PROVIDER |  LLM Provider Name |

### Policy Enablement

The **RTNUM1** field controls whether a policy is active:

- `RTNUM1 = 1` → Enabled (ON)
- `RTNUM1 = 0` → Disabled (OFF)

> **Note:** For a policy to take effect, it must be enabled (`RTNUM1 = 1`) and the corresponding value must be populated in `RTSTR1`.

---