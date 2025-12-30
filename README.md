# 柏林公共服务查询服务 Berlin Search Service

一个提供柏林行政服务数据的模型上下文协议服务器，允许AI助手搜索和检索柏林当局提供的1000多项公共服务信息。
A model context protocol server that provides Berlin administrative service data, allowing AI assistants to search and retrieve over 1000 public service information provided by Berlin authorities.## 工具列表 Tool List

本MCP服务封装下列工具，可让模型通过标准化接口调用以下功能。 本MCP服务封装下列工具，可让模型通过标准化接口调用以下功能。

| 工具 Tool   | 描述 Description         |
|-------|--------------------|
| search_services | Search for Berlin administrative services by name or description. Returns a list of matching services with basic information. |
| get_service_details | Get detailed information about a specific Berlin service by its ID. Returns comprehensive information including requirements, forms, fees, appointments, and more. |
| list_services | List all available Berlin administrative services. Returns a paginated list of services with their names and IDs. |
| get_services_stats | Get statistics about the Berlin services dataset (total count, last update, etc.) |


## 检查服务 ## Inspector

工具在线测试： [https://mcp.xiaobenyang.com/inspector/1777316659740675](https://mcp.xiaobenyang.com/inspector/1777316659740675)

Online Tool test [https://mcp.xiaobenyang.com/inspector/1777316659740675](https://mcp.xiaobenyang.com/inspector/1777316659740675)

## 服务配置 MCP Server Config


> #### 如何获取 XBY-APIKEY ？ How to get XBY-APIKEY ?
> 访问小笨羊科技网站 [https://xiaobenyang.com](https://xiaobenyang.com)，注册用户即可获得APIKEY
> Visit XiaoBenYang website [https://xiaobenyang.com](https://xiaobenyang.com), register and get the APIKEY.

### SSE
```json
{
  "mcpServers": {
    "柏林公共服务查询服务": {
      "headers": {
        "XBY-APIKEY": "<YOUR_XBY_APIKEY>"
      },
      "type": "sse",
      "url": "https://mcp.xiaobenyang.com/1777316659740675/sse"
    }
  }
}
```
### STREAMABLE HTTP
```json
{
  "mcpServers": {
    "柏林公共服务查询服务": {
      "headers": {
        "XBY-APIKEY": "<YOUR_XBY_APIKEY>"
      },
      "type": "streamable_http",
      "url": "https://mcp.xiaobenyang.com/1777316659740675/mcp"
    }
  }
}
```
### STDIO
```json
{
    "mcpServers": {
        "柏林公共服务查询服务": {
          "command": "npx",
          "args": [
            "-y",
            "xiaobenyang-mcp"
          ],
          "env": {
            "XBY_APIKEY": "<YOUR_XBY_APIKEY>",
            "mcpId": "1777316659740675",
          },
          "transport": "stdio"
        }
      }
}

```
