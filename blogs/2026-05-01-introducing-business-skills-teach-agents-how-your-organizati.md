---
title: "Introducing business skills: Teach agents how your organization works"
url: "https://www.microsoft.com/en-us/power-platform/blog/2026/05/01/business-skills/"
date: "Fri, 01 May 2026 18:05:46 +0000"
author: "Prithvi Khosla"
feed_url: "https://www.microsoft.com/en-us/power-platform/blog/feed/"
---
<p class="wp-block-paragraph">Every organization has processes that live in people’s heads — the steps to&nbsp;qualify&nbsp;a lead, the rules for approving a discount, the checklist for onboarding a new vendor. This&nbsp;undocumented&nbsp;institutional knowledge drives consistent outcomes when experienced employees follow it, but&nbsp;it’s&nbsp;never been available to AI agents. Until now.&nbsp;</p>



<h2 class="wp-block-heading" id="business-skills-process-knowledge-that-agents-can-follow">Business skills: Process knowledge that agents can follow&nbsp;</h2>



<p class="wp-block-paragraph"><strong>Business skills</strong>&nbsp;in Dataverse&nbsp;are now in public preview!&nbsp;You can capture your organization’s processes, policies, and domain&nbsp;expertise&nbsp;as natural-language instructions that AI agents discover and follow at runtime.&nbsp;</p>



<p class="wp-block-paragraph">Each business skill describes a specific process — the&nbsp;detailed&nbsp;steps-by-step instructions&nbsp;involved, the information&nbsp;required, and the business rules that apply. Agents connected to the&nbsp;<a href="https://learn.microsoft.com/power-apps/maker/data-platform/data-platform-mcp-preview-tools" rel="noreferrer noopener" target="_blank">Dataverse MCP server</a>&nbsp;discover relevant skills automatically and use them to complete tasks according to your organization’s standards.&nbsp;</p>



<p class="wp-block-paragraph">Because skills are defined once and stored centrally in Dataverse, any agent can use them — whether&nbsp;it’s&nbsp;running in Copilot Studio, GitHub Copilot, VS Code, Azure AI Foundry, or any MCP-compatible client. When multiple agents reference the same skill, they follow the same process. Update the skill, and the change applies everywhere — no need to track down and patch individual agent configurations.</p>


<figure class="wp-block-image size-large"><img alt="Build business skill once and use across every agent " class="wp-image-134118 webp-format" src="https://www.microsoft.com/en-us/power-platform/blog/wp-content/uploads/2026/04/image-50-1024x480.webp" /></figure>



<p class="wp-block-paragraph">Skills are fully governed with built-in sharing and visibility controls, and&nbsp;they’re&nbsp;solution-aware&nbsp;—&nbsp;which means you can add them to your power platform solutions and&nbsp;move them across environments as part of your existing ALM process.&nbsp;</p>



<h2 class="wp-block-heading" id="seeing-it-in-action">Seeing it in action&nbsp;</h2>



<p class="wp-block-paragraph">Previously, asking an agent to follow a multi-step business process — like assigning vendors to open issues — meant the agent had no context for&nbsp;<em>how</em>&nbsp;your team actually handles that work.&nbsp;The result&nbsp;was generic at best&nbsp;and unable to adapt to the changing processes.&nbsp;</p>



<p class="wp-block-paragraph">With business skills, the same request produces a precise, grounded result. The agent discovers the relevant business skill, follows your documented process step by step, and completes the task across your Dataverse data — no custom code, no workflow builder, no app switching.&nbsp;</p>



<figure class="wp-block-embed is-type-video is-provider-youtube wp-block-embed-youtube wp-embed-aspect-16-9 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper">

</div></figure>



<h2 class="wp-block-heading" id="create-share-and-govern-all-from-power-apps">Create, share, and govern — all from Power Apps&nbsp;</h2>



<p class="wp-block-paragraph">Business skills live in&nbsp;Dataverse&nbsp;and you can manage them from&nbsp;<a href="https://make.powerapps.com/" rel="noreferrer noopener" target="_blank">make.powerapps.com</a>. Write your process in natural language or upload existing documentation, share it with the right people, control who can see and edit it, and deploy it across environments through solutions — all without leaving Power Apps. Update a skill and every connected agent picks up the change&nbsp;immediately,&nbsp;no republishing required.</p>


<figure class="wp-block-image size-large"><img alt="Business skills in Power Apps" class="wp-image-134119 webp-format" src="https://www.microsoft.com/en-us/power-platform/blog/wp-content/uploads/2026/04/image-51-1024x605.webp" /></figure>



<p class="wp-block-paragraph">Prefer to work conversationally? The&nbsp;<a href="https://aka.ms/dataversemcppreview" rel="noreferrer noopener" target="_blank"><strong>Dataverse MCP server</strong></a>&nbsp;lets you create and update skills by simply asking an agent.&nbsp;</p>



<h2 class="wp-block-heading" id="who-should-use-business-skills">Who should use business skills?&nbsp;</h2>



<p class="wp-block-paragraph">Business skills&nbsp;capture domain specific tasks from existing business workflows as context to further inform Copilot and agents.&nbsp;Whether&nbsp;you’re&nbsp;a maker codifying how your team&nbsp;operates, an agent builder who needs agents to follow real processes instead of generic instructions, or an admin who needs governance over how business knowledge is shared and deployed — business skills are built for you.&nbsp;</p>



<h2 class="wp-block-heading" id="velrada-enables-consistent-process-execution-for-equipment-inspections">Velrada enables consistent process execution for equipment inspections </h2>



<p class="wp-block-paragraph">Matthew Pontel, General Manager of Applied AI at <a href="https://velrada.com/" rel="noopener noreferrer" target="_blank">Velrada</a> remarks that &#8220;Velrada built Inspection Agent to help worksite supervisors and field workers track the maintenance status of their equipment – so they can trust the tools used to get the job done.</p>



<p class="wp-block-paragraph">The Inspection Agent uses business skills to perform an equipment inspection with the user. For an onsite HVAC inspection, the Inspection Agent will invoke the business skill to determine the questions to ask based on equipment class, checks the last inspection outcomes, and pull in context of any historic issues. The result: a conversational assessment that produces a consolidated inspection report on the HVAC unit’s condition and follow-up guidance for maintenance.”</p>



<h2 class="wp-block-heading" id="get-started">Get started&nbsp;</h2>



<p class="wp-block-paragraph">Business skills bring your organization’s&nbsp;expertise&nbsp;to every agent — no code, no complex tooling, just your processes written in plain language and available wherever agents run. We invite you to:&nbsp;</p>



<ol class="wp-block-list" start="1">
<li class="wp-block-list-item">Enable&nbsp;<a href="https://learn.microsoft.com/power-apps/maker/data-platform/data-platform-intelligence" rel="noreferrer noopener" target="_blank">Dataverse intelligence</a>&nbsp;in the Power Platform admin center.&nbsp;</li>
</ol>



<ol class="wp-block-list" start="2">
<li class="wp-block-list-item">Navigate to&nbsp;the&nbsp;&nbsp;<strong>Business&nbsp;skills</strong>&nbsp;page&nbsp;in&nbsp;<a href="https://make.powerapps.com/" rel="noreferrer noopener" target="_blank">Power Apps</a>&nbsp;from the left pane.&nbsp;</li>
</ol>



<ol class="wp-block-list" start="3">
<li class="wp-block-list-item">Create your first skill or upload&nbsp;an existing skill.&nbsp;</li>
</ol>



<ol class="wp-block-list" start="4">
<li class="wp-block-list-item">Connect an agent to the&nbsp;<a href="https://aka.ms/dataversemcppreview" rel="noreferrer noopener" target="_blank">Dataverse MCP server</a>&nbsp;and see it in action.&nbsp;</li>
</ol>



<p class="wp-block-paragraph">Want a head start? The&nbsp;<a href="https://aka.ms/DVBusinessSkillRepo" rel="noreferrer noopener" target="_blank">sample business skills repository on GitHub</a>&nbsp;includes production-ready examples you can install directly in your environment.&nbsp;</p>



<p class="wp-block-paragraph">Try the preview today — we&nbsp;can’t&nbsp;wait to see what you build. Learn more with&nbsp;additional&nbsp;resources:&nbsp;</p>



<ul class="wp-block-list">
<li class="wp-block-list-item"><a href="https://learn.microsoft.com/power-apps/maker/data-platform/data-platform-intelligence" rel="noreferrer noopener" target="_blank">What is Dataverse intelligence?</a>&nbsp;</li>
</ul>



<ul class="wp-block-list">
<li class="wp-block-list-item"><a href="https://learn.microsoft.com/power-apps/maker/data-platform/data-platform-business-skill-overview" rel="noreferrer noopener" target="_blank">Business skills overview</a>&nbsp;</li>
</ul>



<ul class="wp-block-list">
<li class="wp-block-list-item"><a href="https://learn.microsoft.com/power-apps/maker/data-platform/data-platform-business-skills" rel="noreferrer noopener" target="_blank">Create and use business skills</a>&nbsp;</li>
</ul>



<ul class="wp-block-list">
<li class="wp-block-list-item"><a href="https://aka.ms/DVBusinessSkillRepo" rel="noreferrer noopener" target="_blank">Sample business skills on GitHub</a>&nbsp;</li>
</ul>
<p>The post <a href="https://www.microsoft.com/en-us/power-platform/blog/2026/05/01/business-skills/">Introducing business skills: Teach agents how your organization works </a> appeared first on <a href="https://www.microsoft.com/en-us/power-platform/blog">Microsoft Power Platform Blog</a>.</p>
