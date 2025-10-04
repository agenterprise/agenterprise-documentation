## Installation

### PyPI

```bash
pip install agenterprise
```

### For developlment
Follow these steps to install it from source
```bash
git clone https://github.com/agenterprise/agenterprise.git
cd agenterprise
pip install -e .
```

## Usage Example

### Create a DSL File
You can either start with a DSL File from scratch (see http://www.agenterprise.ai) or generate a sample file with:
```bash
agenterprise --dsl-template --dsl mydsl.dsl     
```
### Generate a project
Whith your created DSL File you can now generate a project:
```bash
agenterprise --code-generation --dsl mydsl.dsl --target target/mydsl
```