# The Agenterprise.ai DSL

# DSL Levels Overview

The Agenterprise DSL is structured in distinct layers as levels, each representing a core aspect of agentic, model-driven enterprise systems. The following example illustrates the main levels:

---

## 1. Environment Level
Defines the overall AI environment or context for the system.

```dsl
ai_environment "AgentMicroservice"
```

---

### 2.1 Architecture Level
Describes the architecture, including environment IDs and technology stacks for services and AI components.

```dsl
architecture{
    envid = "fb98001a0ce94c44ad091de3d2e78164"
    service-techlayer = aiurn:techlayer:local:..:templates:service-layer-fastapi-base
    ai-techlayer = aiurn:techlayer:local:..:templates:ai-layer-pydanticai
        
}
```
Read on at [Architecture Layer](architecture-layer.md)

---

### 2.2 Infrastructure Level
Specifies infrastructure resources such as LLMs, providers, endpoints, and versions.

```dsl
infrastructure {
    llm "My LLM" {
        uid = aiurn:model:id:geepeetee
        provider = aiurn:model:provider:azure 
        model = "gpt-4o"
        endpoint = "https://any.openai.azure.com/"
        version = "2025-01-01-preview"
        aiurn:var:temperature = 0.7
        aiurn:var:costid = "ewe3949" 
        aiurn:var:hello = True 
    }
}
```
Read on at [Infrastructure Layer](infrastruture-layer.md)

---

### 2.3 AI Functional Level
Defines agents, tools, and their properties, including prompts, references, variables, and endpoints.

```dsl
functional{
    agent "Cook" {
        uid = aiurn:agent:cook
        namespace = aiurn:ns:janes_diner:kitchen
        systemprompt = "You're a four star rated metre working at https://my.littlerestaurant.example"
        llmref = aiurn:model:id:geepeetee 
        toolref = aiurn:tool:cooking:v1
        toolref =aiurn:tool:crawler:v2
        aiurn:var:name = "Max Mustermann"
        aiurn:var:role = "waiter"
        aiurn:var:lifeycle = "permanent"
        aiurn:var:events = "onRestaurantOpening"
        
    }

    agent "Waiter" {
        uid = aiurn:agent:waiter
        namespace = aiurn:ns:kkweinhauschen:guestroom
        systemprompt = "Du bist ein freundlicher und aufmerksamer Oberkellner und managed das Restaurant https://my.littlerestaurant.example"
        llmref = aiurn:model:id:geepeetee 
        toolref = aiurn:tool:crawler:v2
        toolref = aiurn:tool:bmi:v1
        aiurn:var:name = "Max Mustermann"
        aiurn:var:role = "waiter"
        aiurn:var:lifeycle = "permanent"
        aiurn:var:events = "onRestaurantOpening"
    }
    tool "bmicalculator" {
        uid = aiurn:tool:bmi:v1
        in = aiurn:toolvar:weight # "The weight of the person"
        in = aiurn:toolvar:height # "The heigt of ther person"
        out = aiurn:toolvar:bmi # "The calculated BMI (Body Mass Index)"
        endpoint = "lambda weight, height: round(weight / (height ** 2), 2)"
        type = aiurn:tooltype:code
        description = "Tool calculating the bmi by weight and height"
        
    }
    tool "Mealdb" {
        uid = aiurn:tool:cooking:v1
        in = aiurn:toolvar:meal # "A meal"
        out = aiurn:toolvar:description # "A listing about ingridients"
        endpoint = "https://www.themealdb.com/api/json/v1/1/search.php?s=aiurn:tool:input:meal"
        type = aiurn:tooltype:ressource
        description = "Tool for finding a meal deescription."
        
    }
        tool "Webcrawler" {
        uid = aiurn:tool:crawler:v2
        endpoint = "https://remote.mcpservers.org/fetch/mcp"
        type = aiurn:tooltype:mcp
        description = "Tool for fetching webpages"
        
    }

}
```

Read on at [AI Functional Layer](ai-functional-layer.md)

---

Each level in the DSL enables clear separation of concerns, making it possible to model, generate, and manage complex agentic enterprise systems in a technology-neutral and flexible way.
