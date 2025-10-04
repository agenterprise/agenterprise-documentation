# AI Functional Layer

This section covers the AI functional layer in the Agenterprise DSL. It describes how to define agents, their properties, prompts, references, and variables.

## Agent
Example
```dsl
 agent "Cook" {
    uid = aiurn:agent:cook 
    namespace = aiurn:ns:janes_diner:kitchen
    systemprompt = "You're a four star rated metre working at https://my.littlerestaurant.example"
    llmref = aiurn:model:id:geepeetee 
    toolref = aiurn:tool:cooking:v1
    toolref = aiurn:tool:crawler:v2
    aiurn:var:name = "Max Mustermann"
    aiurn:var:role = "waiter"
    aiurn:var:lifeycle = "permanent"
    aiurn:var:events = "onRestaurantOpening"
        
}
```
### Specs
Give the Agent a name by assign a name to agent %MY_NAME% { ... }

| Attribute | Assignment | Rule  | Cardinality  | Examples |
| --------  | --------   | -------- | -------- | -------- |
| uid       | aiurn:agent:%AGENT_ID% | append %AGENT_ID% to _aiurn:agent:_ the name of your agent | 1..1 | aiurn:agent:_cook_ 
| namespace | aiurn:ns:%NAMESPACE%  | append %NAMESPACE% to _aiurn:agent:ns:_ the namespace of the agent. | 1..1 | aiurn:ns:_mynamespace:subnamespace_ <br/>  aiurn:ns:_mynamespace_
| llmref    | aiurn:model:id:%LLMID% | take the uid given to the [LLM Defintion](infrastruture-layer.md) | 1..1 | aiurn:model:id:geepeetee:_myllmid_ 
| toolref   | aiurn:tool:%TOOLID% | take the uid given to the Tool Defintion (below) | 0..N | aiurn:tool:_toolid_ 
| aiurn:var | aiurn:tool:%VARNAME% = %MY_VALUE"| add a property to the agent | 0..N | aiurn:var:_name_ = _"Max Mustermann"_


## Tool
Example:
```dsl
tool "bmicalculator" {
    uid = aiurn:tool:bmi:v1
    in = aiurn:toolvar:weight # "The weight of the person"
    in = aiurn:toolvar:height # "The heigt of ther person"
    out = aiurn:toolvar:bmi # "The calculated BMI (Body Mass Index)"
    endpoint = "lambda weight, height: round(weight / (height ** 2), 2)"
    type = aiurn:tooltype:code
    description = "Tool calculating the bmi by weight and height"
    
}
```
### Specs
Give the Tool a name by assign a name to tool %MY_NAME% { ... }

| Attribute | Assignment | Rule  | Cardinality  | Examples |
| --------  | --------   | -------- | -------- | -------- |
| uid       | aiurn:tool:%TOOL_ID% | append %TOOL_ID% to _aiurn:tool:_ the name of your agent | 1..1 | aiurn:tool:_calc:bmi_ 
| in | aiurn:toolvar:%VARNAME% # %PROPERTY_DESCRIPTION% | specify a input variable with name %VARNAME% and describe the property with %PROPERTY_DESCRIPTION% | 0..N | in = aiurn:toolvar:weight # "The weight of the person"
| out | aiurn:toolvar:%VARNAME% # %PROPERTY_DESCRIPTION% | specify a output variable with name %VARNAME% and describe the property with %PROPERTY_DESCRIPTION% | 0..N | out = aiurn:toolvar:bmi # "The calculated BMI (Body Mass Index)"
| endpoint    | %ENDPOINT% | Depending on type specify: <ul><li> MCP --> a streamable https url to remote MCP server</li><li>python code --> write a custom python function</li><ul>| 1..1 | <ul><li> MCP --> https://remote.mcpservers.org/fetch/mcp</li><li>python code --> ```"lambda weight, height: round(weight / (height ** 2), 2)"```</li><ul>
| type   | aiurn:tooltype:code for custom code or <br/>aiurn:tooltype:mcp for mcp server | take the uid given to the Tool Defintion (below) | 1..1  | aiurn:tooltype:code
| description| a text |A  description of the tool | 1..1 | "Tool calculating the bmi by weight and height"