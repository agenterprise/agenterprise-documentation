# The Agenterprise.ai DSL

# DSL Levels Overview

The Agenterprise DSL is structured in distinct layers as levels, each representing a core aspect of agentic, model-driven enterprise systems. The following example illustrates the main levels:

---

**1. Environment Level**
Defines the overall AI environment or context for the system.

```dsl
ai_environment "AgentMicroservice"
```

---

**2. Architecture Level**
Describes the architecture, including environment IDs and technology stacks for services and AI components.

```dsl
architecture{
    envid = "c672da0bd68f41f1b77442524cfa48c4"
    service-techstack = aiurn:techstack:github:www.github.com:agenterprise:service-layer-fastapi-base
    ai-techstack = aiurn:techstack:github:www.github.com:agenterprise:ai-layer-pydanticai
}
```

---

**3. Infrastructure Level**
Specifies infrastructure resources such as LLMs, providers, endpoints, and versions.

```dsl
infrastructure {
    llm "My LLM" {
        uid = aiurn:model:llm:geepeetee
        provider = aiurn:provider:azure
        model = "gpt-4o"
        endpoint = "https://gpt-mvo-sweden.openai.azure.com/openai/deployments/gpt-4o/chat/completions"
        version = "2025-01-01-preview"
    }
}
```

---

**4. Functional Level**
Defines agents, tools, and their properties, including prompts, references, variables, and endpoints.

```dsl
functional{
    agent "Cook" {
        uid = aiurn:agent:cook
        namespace = aiurn:ns:janes_diner:kitchen
        systemprompt = "You're a four star rated metre"
        llmref = aiurn:model:llm:geepeetee 
        toolref = aiurn:tool:cooking:v1      
        aiurn:var:name = "Jane Smith"
        aiurn:var:role = "manager"
        aiurn:var:lifeycle = "permanent"
        aiurn:var:event = "onRestaurantOpening" 
    }
    agent "Waiter" {
        uid = aiurn:agent:waiter
        namespace = aiurn:ns:janes_diner:guestroom
        systemprompt = "Du bist ein freundlicher und aufmerksamer Kellner"
        llmref = aiurn:model:llm:geepeetee 
        aiurn:var:name = "Max Mustermann"
        aiurn:var:role = "waiter"
        aiurn:var:lifeycle = "permanent"
        aiurn:var:events = "onRestaurantOpening"
    }
    tool "CookingApi" {
        uid = aiurn:tool:cooking:v1
        endpoint = "http://localhost:8000/mcp"
        type = aiurn:tooltype:mcp
        description = "Tool for finding good cooking combinations"
    }
}
```

---

Each level in the DSL enables clear separation of concerns, making it possible to model, generate, and manage complex agentic enterprise systems in a technology-neutral and flexible way.
