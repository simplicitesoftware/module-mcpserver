<!--
 ___ _            _ _    _ _    __
/ __(_)_ __  _ __| (_)__(_) |_ /_/
\__ \ | '  \| '_ \ | / _| |  _/ -_)
|___/_|_|_|_| .__/_|_\__|_|\__\___|
            |_| 
-->
![Logo](https://platform.simplicite.io/logos/standard/logo250.png)
* * *

`MCPServer` module definition
=============================

Domains
-------

_Domains organize the application's main navigation menu. Each domain groups the objects, processes, and external pages accessible to users from it. Domains can be nested: a domain may have a parent domain._

* `McpDomain`
  * `McpPrompt` _(object)_

`McpPrompt` (Prompts) business object definition
------------------------------------------------

**Physical table**: `mcp_prompt`

### Relationships

* Belongs to **Module** via `mcpProModuleId` (required)

### Fields

| Name                                                         | Type                                     | Required | Updatable | Personal | Description                                                                      |
|--------------------------------------------------------------|------------------------------------------|----------|-----------|----------|----------------------------------------------------------------------------------|
| **`mcpProModuleId`** link to **`Module`**                    | id                                       | yes*     | yes       |          | -                                                                                |
| _`mdl_name`_                                                 | _regexp(100)_                            |          |           |          | _Module name_                                                                    |
| `mcpMcppromptName`                                           | char(100)                                | yes*     | yes       |          | -                                                                                |
| `mcpMcppromptLabel`                                          | char(100)                                |          | yes       |          | -                                                                                |
| `mcpMcppromptContent`                                        | text(100000)                             | yes      | yes       |          | -                                                                                |
| `mcpMcppromptType`                                           | enum(100) using MCP_MCPPROMPT_TYPE list  | yes      | yes       |          | -                                                                                |
| `mcpMcppromptIsActive`                                       | boolean                                  | yes      | yes       |          | -                                                                                |
| `mcpMcppromptOrder`                                          | int(100)                                 |          | yes       |          | -                                                                                |

### Enumerations

* `MCP_MCPPROMPT_TYPE`
    - `STA` STARTER
    - `SYS` SYSTEM

Shared code
-----------

* `PlatformHooks` _(Server script)_

