---
title: "Online learning"
author: "Janno Vergara"
format:
    html:
        code-overflow: wrap
---
#  Understand Google Cloud Agents

- Describe Agentic AI, differentiate it from traditional AI, and explain its benefits and enterprise-level considerations.
- Identify and describe the essential components of an AI agent's architecture, including its memory systems and ability to use tools
- Understand the primary Google Cloud services and frameworks used for building, deploying, and managing Agentic AI solutions.
- Deploy an agent on Google Cloud and identify key use cases.

## Foundations of GenAI

Foundation models, including LLMs, are trained on a wide variety of data, allowing them to learn general patterns and relationships that can be applied to different tasks.

They can be specialized for particular domains or use cases through additional, targeted training. For example, LLMs can be customized and fine-tuned on specific, proprietary datasets to significantly improve their performance and relevance for specialized, internal business applications.

Foundation models, including LLMs, are trained on a wide variety of data, allowing them to learn general patterns and relationships that can be applied to different tasks.

They can be specialized for particular domains or use cases through additional, targeted training. For example, LLMs can be customized and fine-tuned on specific, proprietary datasets to significantly improve their performance and relevance for specialized, internal business applications.

## Grounding and RAG

Grounding is the process of limiting the AI to a specific scope and verifiable sources of information. Providing the model with access to specific data sources, tethers its output to real-world information, reducing the risk of invented content.

Grounding and RAG (retrieval augmented generation) are core mechanisms that anchor the agent's responses in factual, verifiable, real-time information. The process involves two key steps:

Retrieval: The agent searches connected data sources for the most relevant text snippets.

Augmentation: These snippets are passed to the Gemini model as explicit context, forcing the model to generate an answer based only on the verified source material.

## The evolution to agentic systems

Today’s generative AI agents can achieve a goal by observing the world and acting upon it using the tools it has at their disposal. This wasn't always the case. Early virtual agents were limited to predefined paths and lacked true understanding.

But thanks to advances like generative AI and retrieval augmented generation (RAG), today's agents can understand your intent, access relevant information, and provide much more helpful and natural interactions.

## Introducing the Cymbal Labs use case

Cymbal Labs is a fictional biotechnology company with many departments, including research, human resources, finance, IT, and sales. Like many growing firms, they are facing challenges across the organization, such as fragmented operational data, slow internal support, and complex research processes.

To accelerate its business and eliminate manual bottlenecks, Cymbal Labs implements a suite of AI Agents. The company builds its solutions using the Gemini Enterprise app, Conversational Agents, Customer Experience Agent Studio and Gemini Enterprise Agent Platform (including the Agent Development Kit).

Throughout this course, you will use Cymbal Labs' challenges as a guide for learning about building and deploying agents on Google Cloud. This lesson provides an overview of the specific business problems that AI agents help the Cymbal Labs sales team to solve.

### Challenge 1: Fragmented data sources and manual processes

Before each meeting with a major partner, sales analysts spend hours sifting through documents to summarize past interactions, identify key decision-makers, and track recent partner acquisitions. Their research is used to create a comprehensive briefing on the partner's historical relationship with Cymbal and their competitive landscape.

The lack of easily available context often leads to redundant work, as the team spends a lot of their time aggregating, formatting, and cross-checking data, instead of actively negotiating and closing deals. As a result, Cymbal Labs decides to adopt Gemini Enterprise to overcome this challenge.

### Challenge 2: Customer support overload

The core sales and support staff is essential for handling the most important and complicated client inquiries. With rapid customer acquisition, the team is overwhelmed by a massive volume of highly repetitive, low-complexity customer service requests related to order tracking, password resets, basic product troubleshooting, and return procedures.

Cymbal Labs decides to create an agent using Conversational Agents to provide customers with immediate, accurate 24/7 support for routine issues. 

### Challenge 3: Disconnected customer journeys

After creating an agent to scale routine support requests, Cymbal Labs notices that several prospective enterprise customers are dropping out of the sales funnel. This shift occurs when these large-scale accounts try to transition from basic troubleshooting inquiries to complex sales discussions.

When a hospital administrator asks a routine support question but mid-conversation shifts to requesting a bulk pricing quote or a live demo, the context is lost. With the current systems operating in silos, prospects have to repeat their requirements, leading to frustration and missed multi-million dollar deals.

To orchestrate these complex, non-linear customer journeys across multiple channels, Cymbal Labs adopts Customer Experience (CX) Agent Studio. This allows them to build advanced visual conversation flows that seamlessly manage state transitions, handle sudden topic switching, and capture critical intent data to automatically route high-value leads directly to the sales team.

### Challenge 4: Automating highly specialized workflows

Cymbal Labs' growth requires their sales team to shift from selling standard products to selling complex, high-value customized solutions involving a specific mix of hardware, proprietary diagnostic cartridges, and service tiers. The generic quote and snapshot generated by the company's existing agents are insufficient for these multi-million dollar deals.

As a result, they have decided to  use the powerful, enterprise-grade capabilities of Gemini Enterprise Platform to develop a custom solution.

### Challenge 5: Inaccurate resource allocation

At Cymbal Labs, finance managers rely on static spreadsheets that don't easily integrate with real-time operational data, including information like actual equipment usage or sudden vendor cost changes. The lack of updated information often leads to under- or over-funding projects, creating budget overruns in some areas and unnecessary delays in others. Cymbal Labs needs an agent capable of more than simple data lookups, so they select ADK to provide developers with the capabilities they need for precise control.

### Conclusion

These four scenarios illustrate the broad potential for AI agents to assist Cymbal Labs in addressing bottlenecks as it scales its business. The upcoming modules explore the specific tools and technical approaches required to build each solution on Google Cloud.

## Introduction to AI Agents on Google Cloud

- Define what an AI Agent is and its key components (models, tools, orchestration, runtime).
- List the different types of agents by business impact (customer, employee, creative, data, code, and security agents).
- Describe Google's unified AI stack and the primary Google Cloud offerings for agent development:  Gemini Enterprise app, Conversational Agents, Customer Experience Agent Studio, and Gemini Enterprise Agent Platform.

## Introduction to AI Agents

An AI Agent is a software system that uses artificial intelligence (AI), usually language models, to achieve a specific goal on behalf of a user. Agents learn how to best achieve a goal based on inputs and tools available to them.

Unlike simple chatbots or assistants that follow predefined rules, agents focus on autonomous action. This means they have a higher ability to independently set goals and carry them out within a defined environment.

- customer service
- productivity
- home assistant
- travel
- coding

AI Agents are advanced software systems defined by their capacity for autonomous action to achieve complex, specific goals, distinguishing them from simpler, rule-based assistants. Their practical applications range from managing complex logistics like travel and productivity to executing technical tasks like software development.

## AI Agent core capabilities

AI Agents are highly flexible, and their intelligence and effectiveness are driven by a few core features. These features work together to give the agent the ability to understand goals, plan steps, and interact with other systems.

While autonomous action, reasoning and planning, along with continuous learning enable a single agent to perform powerful tasks, agents often reach their maximum potential when they work together.

**Multi-agent collaboration** allows agents to share knowledge, divide complex tasks, and coordinate their actions to achieve large-scale goals that a single agent could not manage alone. This ability to chain actions and collaborate is precisely what makes them so valuable in the workplace.

### How can agents help in the workplace?

Agents analyze situations, use multiple tools, and make informed decisions without requiring constant human input. They are also capable of handling multi-step tasks that a model alone cannot, such as researching a topic, troubleshooting code, or accessing a system by chaining together actions.

### Research and analysis

Agents can perform multi-step research using web searches to gather current data, summarizing findings, and then writing a final report or drafting an email.

Example workflow for generating a market analysis report:

1. The orchestrator agent is asked to write a report.
2. It tells a specialized research agent to search the internet for relevant facts and statistics.
3. The raw data the research agent gathers goes to a data cleaning agent to be normalized and properly formatted.
4. A synthesis agent reviews the clean data and writes the first draft of the report.
5. The final report is then sent out by the orchestrator agent.

### AI Agents vs. traditional chatbots

The biggest distinction between a traditional chatbot and an agentic system is the ability to act autonomously across multiple systems to resolve a complex issue.

## The agent architecture

To understand how AI Agents accomplish such a wide variety of autonomous tasks, it's important to examine the technical architecture that governs their workflows. AI Agents rely on models, tools, and memory to work effectively. Together, these elements enable agents to observe, plan, and act in the world to achieve their goals.


Starting with the brains of the agent. Nowadays, many models are what we call thinking models, which just means that the model has some level of ability to self-reflect built in.

MCP == API

Many agents use a protocol called model context protocol or MCP to access and use tools.

MCP is kind of like an API except it provides additional instructions about how an API is actually used and what the meaning of the inputs and outputs are. This gives the agent knowledge about when and where to use a specific MCP tool or or an API in specific situations.

You can think of memory in the most simple form as the context window for an agent.

Agent patterns
- agent with no loops or other agents
- sub agent pattern
- orchestrator pattern

## Enterprise use cases for AI Agents

An agent’s value comes from the business impact it achieves, whether that means closing a sale, writing better code, or protecting data. 

### Categorizing agents by business impact

With AI, agents can move beyond simple automation to directly address bottlenecks and complexities. Organizations have been deploying agents to address a variety of use cases, which we group into six broad categories.

- **customer service agents**: highly personalized customer experiences
- **employee productivity agent**: streamlining processes, managing repetitive tasks, answering employee questions, as well as editing and translating critical content and communications
- **creative agents**: supercharge the design and creative process by generating content, images, and ideas, assisting with design, writing, personalization, and campaigns
- **code agent**: AI-enabled code generation and coding assistance, and to ramp up on new languages and code bases
- **data agent**: built for complex data analysis. They have the potential to find and act on meaningful insights from data, all while ensuring the factual integrity of their results.
- **security agent**: strengthen security posture by mitigating attacks or increasing the speed of investigations. They can oversee security across various surfaces and stages of the security life cycle: prevention, detection, and response.

The key components of an AI Agent—**models**, **tools**, **orchestration**, and **runtime**—come together to create what's known as an **agentic workflow**. This workflow is now becoming central to how major enterprises are operating.

### Key takeaway

It's important to understand the specific business impact of utilizing various AI Agents. Customer, employee, creative, data, code, and security agents can each map directly to key performance indicators (KPIs) that matter to you and your organization like developer velocity or threat response time. Understanding the problem your agents are solving and the metrics by which they can be measured helps ensure your agents are delivering business value, not just a hypothetical use case.

## Developing agents with Google Cloud

To build and scale AI Agents, you need a unified platform. This lesson will introduce you to Google's unified AI stack and the core services on Google Cloud—from the foundational models to the dedicated toolkits—that enable you to build, deploy, and govern enterprise-grade AI Agents.

Google Cloud offers several solutions for creating and deploying AI Agents which cater to different users, use cases, and complexity requirements.

## Google's AI Agent development offerings

### AI agent tools for business users
- AppSheet
- Gemini Enterprise app
    - Agent Designer
    - ADK Visual Agent Builder
- Customer Engagement Suite
- Google Cloud Contact Center as a Service
    - Conversational agents

### Building faster with assistance
- Agent Search
- Gemini Enterprise App
- Applications integration
- Agent platform
    - ADK
    - Agent runtime
    - Gemini API
- Customer Experience (CX) Agent Studio - non-linear, multi-channel user journeys

## Gemini Enterprise

Google Cloud's agentic platform that provides the AI agents, no-code tools, and governance needed to automate complex enterprise workflows using company data. 

- Explain what Gemini Enterprise is and its primary purpose as an intranet search, AI assistant, and agentic platform for knowledge workers.
- Identify the sources of agents offered in Gemini Enterprise including the default agent, Premade by Google agents, and custom agents.
- List use cases for Gemini Enterprise, including search, summarization, generation, and actions.

AI-powered platform developed by Google Cloud that unifies access to your organization's scattered information

### Core components
- intranet search
- AI assistant
- agentic capabilities

### Agents available in Gemini Enterprise
- premade agents
    - the assistant (gemini llm)
    - search engine
    - notebooklm
- no code agents
- custom agents
- partner made agents

## Automating your daily work with the Gemini Enterprise app

Gemini Enterprise can help streamline workflows and provide critical insights across different departments.

### Driving revenue and engaging external partners

- generate summaries about target companies
- streamline multi-source searches
- get reminders and manage tasks

### Streamlining technical processes and operations

- automate processes and tasks
    - can automate routine processes and repetitive tasks, from code deployment to data pipeline management
- identify bugs proactively
    - aid in the early identification and fixing of bugs before they impact users or operations
- analyze data to optimize performance
    - Whether it's identifying bottlenecks, optimizing resource allocation, or refining algorithms, Gemini Enterprise provides actionable insights that help you make informed decisions and continuously improve efficiency and user experience.

### Enhancing communication and external outreach

- personalize customer messaging
- automate campaign adjustments
- generate issue insights

### Boosting administrative efficiency and collaboration
- managing reimbursements, tracking PTO requests, and handling payslips
- verify performance review sources by helping you gather and confirm information efficiently, whether for your own team, or for cross-departmental feedback.
- Coordinate meeting scheduling

## Use case: Unifying knowledge bases with Gemini Enterprise

### The challenge: Fragmented data sources and manual processes

- Customer relationship management (CRM) tool
- Enterprise resource planning (ERP) database
- Documents
- Internal communication

**Adopting a solution**

Cymbal Labs decides to adopt Gemini Enterprise to overcome this challenge. The solution uses a custom AI agent to generate comprehensive briefings in preparation for customer calls.

This agent is grounded in proprietary enterprise data sources like the CRM and ERP via built-in connectors. The agent’s workflow executes complex steps, synthesizing data to deliver three high-value outputs

- Complete customer snapshot: one easy-to-read document
- Automated presentation deck: organizes it into a professional presentation format
- Initial quote preparation: calculate and draft a first-pass quote with recommended pricing tiers

Gemini Enterprise also ensures security by only showing sales reps the sensitive customer data they are specifically authorized to view.

### Unified knowledge access and information synthesis

- federated search and synthesis (RAG)
    - *"Who are the key contacts at Customer X, what does their support ticket history look like over the last six months, and what are the recommended next steps for our Q3 renewal discussion?"*
- multi-modal input
    - *"Recreate this chart using the latest Q3 sales numbers (from the CRM) and automatically update the corresponding text on the slide."*

### Workflow automation and action
- automated communication
    - *"Alert the internal finance team that Customer X term sheet is delayed by one week, and auto-draft an email to the partner confirming the new delivery schedule."*
- data summarization for decision making
    - *"Analyze the last two years of our deal history and summarize the reliability and financial commitment of Partner A versus Partner B, including details on past milestone payments and project completions."*

### Governance: Secure and personalized access
- Access control enforcement
- Unified interface

## Introduction to Conversational Agents on Google Cloud

Google Cloud's Conversational Agents platform enables users to build no-code, natural language agents specifically for customer experience use cases

Conversational Agents was previously known as Dialogflow CX

- improving user experience
- driving innovation
- multilingual agents
- streamlining operations

### Key platform features
- pre-set flows
- free-flowing dialog

### Structured converstations
- flows - isolated, independent conversation modules that allow you to segment a complex agent into distinct topics or use cases
- pages - core building blocks of the state machine, representing a single conversational state or checkpoint
- routes - often referred to as state handlers, are the mechanisms that explicitly define the transitions between pages or flows
- forms - a list of required parameters (also called slots) that the agent must collect from the end-user before the page's main task can be executed

### CI/CD integration and scalability
- testing and quality assurance
- version and environment management
- code and asset management
- omnichannel support

## Conversational Agents and generative AI

Conversational Agents leverages the power of Gemini and other LLMs to move beyond rigid flows and deliver fluid, human-like experiences

### Overview of generative features

**Data store agents**: Data store agents create an out of-the-box conversational experience based on information provided by a knowledge domain (such as a website or document).

**Generative responses**: Generative responses can seamlessly integrate with existing conversational AI flows to provide fallback options when standard intent or parameter matching fails. This can enhance the user experience and provide natural and contextually relevant responses. Responses can be generated by leveraging pre-existing models trained on extensive datasets, or they can be tailored to the specific data you provide.

**Playbooks**: Playbooks enable users to specify tasks in natural language, just like they would with a human agent. This intuitive approach eliminates the need for complex programming or technical expertise, making conversational AI development more accessible. Playbooks can be used to create a wide range of conversational experiences, from simple FAQ bots to complex customer support interactions.

## Use case: Improving support experiences with Conversational Agents

### The challenge: Customer support overload

- *"Where is my order? (Order 1234)"*
- *"How do I reset the password for my Cymbal Labs account?"*
- *"What are the basic troubleshooting steps for 'Error ABC' on Product X?"*
- *"I need to initiate a return. What is the process?"*

### The solution: Building an agent with Conversational Agents

- defining complex logic and controls
- workflow automation and handoff
- multilingual support for global customers

## Customer Experience (CX) Agent Studio

Customer Experience (CX) Agent Studio helps teams to rapidly build, evaluate, and deploy highly personalized conversational agents.