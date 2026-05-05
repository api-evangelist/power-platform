---
title: "Custom tools and rich UI for app-based conversations are now in Public Preview"
url: "https://www.microsoft.com/en-us/power-platform/blog/2026/04/22/custom-tools-and-rich-ui-for-app-based-conversations-are-now-in-public-preview/"
date: "Wed, 22 Apr 2026 19:11:22 +0000"
author: "Hemant Gaur"
feed_url: "https://www.microsoft.com/en-us/power-platform/blog/feed/"
---
<p class="wp-block-paragraph">Earlier this month, we announced that <a href="https://www.microsoft.com/en-us/power-platform/blog/power-apps/public-preview-your-business-apps-now-part-of-every-conversation/" id="https://www.microsoft.com/en-us/power-platform/blog/power-apps/public-preview-your-business-apps-now-part-of-every-conversation/">Microsoft Power Apps applications can now be part of your Microsoft 365 Copilot conversations</a> &#8211; letting users interact with their model-driven apps directly from Copilot. Today, we&#8217;re unlocking the next phase with <strong>custom tools</strong> and <strong>rich app-powered UI</strong>, giving customers the flexibility to build and shape experiences their own way.</p>



<p class="wp-block-paragraph">These capabilities let you go beyond the built-in app tools for <a href="https://aka.ms/appskills/grid">grids </a>and <a href="https://aka.ms/appskills/form">forms </a>that you can already <a href="https://learn.microsoft.com/en-us/power-apps/maker/model-driven-apps/enable-your-app-copilot#set-up-power-apps-in-copilot">enable with a few clicks for any model-driven app</a>. Taking the next step in this journey, makers can now create tailored business actions, combined with immersive, interactive experiences, powered by Copilot and Microsoft Work IQ. Custom tools and rich UI components get added to the same app&#8217;s MCP server that also includes the built‑in app tools. With these new capabilities, Copilot experiences can feel less like requests and more like collaboration &#8211; visual, contextual, and action‑ready. Whether tracking case progress over time, spotting friction in a business process, or staying aligned on customer outcomes, insights can be presented in ways that naturally guide the next step.</p>



<figure class="wp-block-image size-full"><img alt="Custom tools and UX for Model apps - App MCP" class="wp-image-134077" height="654" src="https://www.microsoft.com/en-us/power-platform/blog/wp-content/uploads/2026/04/M365CustomToolsDemo1.4.gif" width="1171" /></figure>



<h3 class="wp-block-heading" id="custom-tools-your-app-s-logic-in-copilot">Custom tools: Your app&#8217;s logic in Copilot</h3>



<p class="wp-block-paragraph">Your <strong>app&#8217;s MCP server</strong> already includes built-in app tools for querying, creating, viewing, and editing records in Microsoft Dataverse. Custom tools let you extend the app agent with your own MCP-powered actions, authored directly inside Power Apps using a prompt builder designer.</p>



<p class="wp-block-paragraph">Each tool has a name, description, and instructions that tell the AI model what data to produce, and Copilot uses the tool metadata to decide when to invoke it.</p>



<figure class="wp-block-image size-full"><img alt="Animated Gif Image" class="wp-image-134059" height="636" src="https://www.microsoft.com/en-us/power-platform/blog/wp-content/uploads/2026/04/blog-create-custom-tool.gif" width="1127" /></figure>



<p class="wp-block-paragraph">Copilot can dynamically chain multiple tools together using the tool input parameters. For example, a “Sankey Chart Visualizer” tool can accept data which could be sourced from a natural language Dataverse query. The tool can then transform it into a weighted flow structure, and pass it to a widget for visualization &#8211; all triggered by a single natural-language prompt.</p>



<h3 class="wp-block-heading" id="app-powered-ui-widgets">App-powered UI widgets</h3>



<p class="wp-block-paragraph">Widgets are self-contained, MCP-compliant HTML files built on Fluent UI that automatically adapt to light and dark Copilot themes. As part of this release, we are also introducing the <code>generate-mcp-app-ui</code> skill in Claude Code and GitHub Copilot CLI to help you quickly build widgets using natural language.</p>



<figure class="wp-block-image size-full"><img alt="Animated Gif Image" class="wp-image-134061" height="636" src="https://www.microsoft.com/en-us/power-platform/blog/wp-content/uploads/2026/04/blog-create-custom-tool-ui.gif" width="1126" /></figure>



<p class="wp-block-paragraph">The skill produces a polished, theme-aware widget, ready to drop into your custom tool&#8217;s UX field.</p>



<h3 class="wp-block-heading" id="how-to-get-started">How to get started</h3>



<p class="wp-block-paragraph"><strong>Step 1 &#8211; Enable your app&#8217;s MCP server</strong> &#8211; Open your model-driven app in&nbsp;<a href="https://make.preview.powerapps.com/">Power Apps</a>, select the&nbsp;<strong>App MCP</strong>&nbsp;icon in the left nav, and choose&nbsp;<strong>Set up MCP</strong>.</p>



<p class="wp-block-paragraph"><strong>Step 2 &#8211; Add custom tools</strong> &#8211; In the&nbsp;<strong>Tools</strong>&nbsp;section of the&nbsp;<strong>App MCP</strong> tab, select&nbsp;<strong>Create custom tool</strong>. Give your tool a clear name and description (Copilot uses these to decide when to invoke it), write the Dataverse query instructions, or prompt using input parameter, and finally test the JSON output.</p>



<p class="wp-block-paragraph"><strong>Step 3 &#8211; Attach a widget (optional)</strong>&nbsp;&#8211; Generate a widget for your tool using the&nbsp;<code>/generate-mcp-app-ui</code>&nbsp;skill and JSON tool output above. Test locally and then paste it into the tool&#8217;s UI field on step 2 of the tool editor.</p>



<p class="wp-block-paragraph"><strong>Step 4 &#8211; Deploy</strong>&nbsp;&#8211; Download the updated app package and upload it to Microsoft Teams or publish it through the Microsoft 365 admin center for your organization.</p>



<h3 class="wp-block-heading" id="under-the-hood"><strong>Under the hood</strong></h3>



<p class="wp-block-paragraph">This feature uses the Microsoft 365 Copilot extensibility platform and its <a href="https://devblogs.microsoft.com/microsoft365dev/mcp-apps-now-available-in-copilot-chat/">MCP Apps</a> capability. Power Apps generates an MCP server and a declarative agent from your model-driven app, and custom tools and widgets plug directly into that agent &#8211; no separate infrastructure required.</p>



<h3 class="wp-block-heading" id="documentation"><strong>Documentation</strong></h3>



<ul class="wp-block-list">
<li class="wp-block-list-item"><a href="https://learn.microsoft.com/en-us/power-apps/maker/model-driven-apps/enable-your-app-copilot">Enable your app in Microsoft 365 Copilot</a></li>



<li class="wp-block-list-item"><a href="https://learn.microsoft.com/en-us/power-apps/maker/model-driven-apps/generate-mcp-app-widgets">Generate MCP app widgets with AI code generation tools&nbsp;</a></li>
</ul>



<p class="wp-block-paragraph"><em>Prerequisites: a model-driven app, a Microsoft 365 Copilot license, and permission to upload custom apps in Microsoft Teams. This is a preview feature  &#8211; available for model-driven apps only at this time</em> starting with early release stations.</p>



<p class="wp-block-paragraph">We&#8217;d love to hear about what you build. Share your feedback and ideas through the&nbsp;<a href="https://powerusers.microsoft.com/t5/Power-Apps-Community/ct-p/PowerApps">Power Apps Community</a>.</p>



<p class="wp-block-paragraph"></p>
<p>The post <a href="https://www.microsoft.com/en-us/power-platform/blog/2026/04/22/custom-tools-and-rich-ui-for-app-based-conversations-are-now-in-public-preview/">Custom tools and rich UI for app-based conversations are now in Public Preview</a> appeared first on <a href="https://www.microsoft.com/en-us/power-platform/blog">Microsoft Power Platform Blog</a>.</p>
