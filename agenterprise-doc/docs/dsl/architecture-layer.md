# Architecture Layer

## Architecture
Example
```dsl
 architecture{
    envid = "fb98001a0ce94c44ad091de3d2e78164"
    service-techlayer = aiurn:techlayer:local:..:templates:service-layer-fastapi-base
    ai-techlayer = aiurn:techlayer:local:..:templates:ai-layer-pydanticai
        
}
```
### Specs

| Attribute | Assignment | Rule  | Cardinality  | Examples |
| --------  | --------   | -------- | -------- | -------- |
| envid       | %UID% | a unique id as %UID% representing the project | 1..1 | envid = "fb98001a0ce94c44ad091de3d2e78164"
| service-techlayer | aiurn:techlayer:local:%RELATIVE_LOCAL_PATH% <br/>  aiurn:techlayer:github:%GITHUB_DOMAIN%:%PROFILE%:%TEMPLATE% | <ul><li>set your path %RELATIVE_LOCAL_PATH% in an urn style </li><li> %GITHUB_DOMAIN%:%PROFILE%:%TEMPLATE% specifies a public template to a github project in urn style.</li></ul> | 1..1 | service-techlayer = aiurn:techlayer:local:..:templates:service-layer-fastapi-base <br/> service-techlayer = aiurn:techlayer:github:www.github.com:agenterprise:service-layer-fastapi-base
| ai-techlayer | aiurn:techlayer:local:%RELATIVE_LOCAL_PATH% <br/>  aiurn:techlayer:github:%GITHUB_DOMAIN%:%PROFILE%:%TEMPLATE% | <ul><li>set your path %RELATIVE_LOCAL_PATH% in an urn style </li><li> %GITHUB_DOMAIN%:%PROFILE%:%TEMPLATE% specifies a public template to a github project in urn style.</li></ul> | 1..1 | service-techlayer = aiurn:techlayer:local:..:templates:ai-layer-pydanticai <br/> service-techlayer = aiurn:techlayer:github:www.github.com:agenterprise:ai-layer-pydanticai


### Ressources
Find currated lists for agenterprise layer at 
* [Agenterprise AI-Layers List](https://github.com/stars/agenterprise/lists/ai-layers)
* [Agenterprise Service-Layers List](https://github.com/stars/agenterprise/lists/service-layers)

Feel free to 
* clone templates for your own purposes. 
* get in contact with agenterprise to add these to the above lists