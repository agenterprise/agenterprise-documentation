# Agenterprise:  ⚓ + 🪽

 <div class="mybody">
<main class="chat-container" role="main" aria-label="Atari Chat Terminal">
    <header class="chat-header">== Give your AI project ⚓ anchors and 🪽 wings ==</header>

    <div class="line user-line">Define clearly separated AI Envs with abstract DSL</div>
    <div class="line bot-line">Generate techlayers in a framework/service intended way.</div>
    <div class="line user-line">Build  custom layer on top of it</div>
    <div class="line bot-line">Still here? Read on below .... </div>
  </main>
  </div>
  <style>
    :root {
      --color-bg: #000;
      --color-text: #29c20eff;
      --color-border: #ee6509ff;
      --color-accent: #00cc66;
    }

    .    {
      color: var(--color-text);
      font-family: 'Press Start 2P', monospace;
      font-size: 14px;
      line-height: 1.8;
      margin: 0;
      padding: 20px;
      display: flex;
      justify-content: center;
      align-items: flex-start;
      min-height: 100vh;
    }

    .chat-container {
      width: 100%;
      max-width: 800px;
      border: 2px solid var(--color-border);
      border-radius: 12px;
      padding: 32px;
      box-shadow: 0 0 20px var(--color-accent);
      overflow-x: auto;
      white-space: nowrap;
    }

    .chat-header {
      text-align: center;
      margin-bottom: 30px;
      text-transform: uppercase;
      border-bottom: 1px solid var(--color-border);
      padding-bottom: 12px;
      letter-spacing: 2px;
      font-size: 16px;
      color: var(--color-accent);
      white-space: normal;
    }

    .line {
      display: block;
      white-space: nowrap;
      overflow: hidden;
      text-overflow: ellipsis;
      margin-bottom: 10px;
    }

    .user-line::before,
    .bot-line::before {
      display: inline-block;
      min-width: 180px; /* vorher 130px — jetzt größerer Abstand */
      margin-right: 20px; /* zusätzlicher Raum zwischen Label und Text */
      text-align: right;
      opacity: 0.8;
    }

    .user-line::before {
      content: "[Enterprise Dev]";
      color: var(--color-accent);
    }

    .bot-line::before {
      content: "[Agenterprise.ai]";
      color: var(--color-border);
    }

    @media (max-width: 600px) {
      .chat-container {
        padding: 20px;
      }
      .user-line::before,
      .bot-line::before {
        min-width: 120px;
        margin-right: 12px;
      }
      body {
        font-size: 12px;
      }
    }

    .chat-container {
      animation: fadeIn 0.8s ease-out;
    }

    @keyframes fadeIn {
      from { opacity: 0; transform: translateY(10px); }
      to { opacity: 1; transform: translateY(0); }
    }
  </style>

  <br/>
# Still here?
NOTE: Agenterprise is currently in Alpha Phase

- Model-driven, agentic enterprise software meets GenAI
- Architecture decoupled from technology
- Liveline from PoC to Enterprise Setups
- Open source stability reduces technology and vendor logi

Agenterprise is an open source project focused on model-driven software development for agentic enterprise architectures and beyond. The goal is to enable intelligent solutions that remain independent of specific libraries and frameworks, by decoupling architecture from technology choices.

With Agenterprise's domain-specific language (DSL), you can describe your AI and agentic architectures in a technology-neutral way. This makes it possible to generate different tech stacks or service stacks from the same model, adapting flexibly to changing requirements or platforms.

This approach allows:

- Separation of business logic and technical implementation
- Decoupling enterprise architecture from vendor or framework dependencies
- Integration with various AI and agent technologies

Generative AI is rapidly accelerating software development. However, if you need a stable, enterprise-ready foundation that can be combined with GenAI features, Agenterprise provides a robust and flexible base to build on.

Agenterprise invites everyone interested in flexible, scalable, and sustainable software to explore model-driven development and DSLs for agentic enterprise solutions.
