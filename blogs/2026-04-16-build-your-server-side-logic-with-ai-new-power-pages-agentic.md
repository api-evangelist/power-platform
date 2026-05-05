---
title: "Build your server-side logic with AI: new Power Pages Agentic Code skills"
url: "https://www.microsoft.com/en-us/power-platform/blog/power-pages/build-your-server-side-logic-with-ai-new-power-pages-agentic-code-skills/"
date: "Thu, 16 Apr 2026 08:28:27 +0000"
author: "Neeraj Nandwana"
feed_url: "https://www.microsoft.com/en-us/power-platform/blog/feed/"
---
<p class="wp-block-paragraph">We’re introducing three new skills for the Power Pages agentic code plugin for GitHub Copilot and Claude Code CLI that together unlock a missing capability in AI‑assisted site building: server‑side logic. Until now, the plugin could scaffold sites, define data models, wire up Web APIs, configure authentication, and handle deployment but all business logic, cloud flows, and implementation decisions were still manual. These new skills change that predicament.</p>



<p class="wp-block-paragraph">Meet <strong><code>/add-server-logic</code>,<code> /add-cloud-flow</code>, </strong>and <strong><code>/integrate-backend</code></strong> &#8211; three skills that complete the application stack. They build on an already working site by introducing secure server-side logic, Power Automate cloud flows, and intelligent backend orchestration for end-to-end functionality.</p>



<h2 class="wp-block-heading" id="what-s-new">What&#8217;s new</h2>



<ul class="wp-block-list">
<li class="wp-block-list-item"><strong><code>/add-server-logic</code> </strong>generates secure server-side JavaScript endpoints for validation, secret management, external API calls, and cross-entity operations.</li>



<li class="wp-block-list-item"><code><strong>/add-cloud-flow</strong></code> integrates existing Power Automate cloud flows into your Power Pages site for approval workflows, notifications, and scheduled automation.</li>



<li class="wp-block-list-item"><code><strong>/integrate-backend</strong></code> analyzes your prototype, determines the right approach (Web API, Server Logic, and/or cloud flow) for each feature, and orchestrates the complete build sequence.</li>
</ul>



<h3 class="wp-block-heading" id="add-server-logic-secure-server-side-endpoints-generated-end-to-end">/add-server-logic: secure server-side endpoints, generated end to end</h3>



<p class="wp-block-paragraph"><a href="https://learn.microsoft.com/en-us/power-pages/configure/server-logic-overview">Server Logic</a> in Power Pages moves critical operations from the browser to the server for improved control, scalability, and security. It&#8217;s generally available, so it&#8217;s fully supported for production workloads. With server logic, your site can perform complex tasks and integrations without exposing sensitive logic or data on the client side. Server logic enables you to:</p>



<ul class="wp-block-list">
<li class="wp-block-list-item"><strong>Connect to external services</strong>. Integrate securely with REST APIs, Azure Functions, or other business systems<em>, e.g., call the Stripe API to process a payment without exposing your API key.</em> (<a href="https://learn.microsoft.com/en-us/power-pages/configure/server-logic-external-services">Tutorial: interact with external services</a>)</li>



<li class="wp-block-list-item"><strong>Perform secure data operations.</strong> Query, update, or delete Dataverse records with consistent server-side validation<em>, e.g., check inventory levels before accepting an order submission.</em> (<a href="https://learn.microsoft.com/en-us/power-pages/configure/server-logic-operations">Tutorial: interact with Dataverse tables</a>)</li>



<li class="wp-block-list-item"><strong>Run custom logic. </strong>Calculate totals, enforce business rules, or enrich data with external lookups before returning results<em>, e.g., aggregate data across multiple tables into a single global search response.</em></li>



<li class="wp-block-list-item"><strong>Manage secrets server-side.</strong> Store credentials and API keys on the server, never in client code<em>, e.g., authenticate with Microsoft Graph to upload documents to SharePoint.</em> (<a href="https://learn.microsoft.com/en-us/power-pages/configure/server-logic-graph-sharepoint">Tutorial: interact with Microsoft Graph and SharePoint</a>)</li>
</ul>



<p class="wp-block-paragraph">The <code><strong>/add-server-logic</strong></code> allows you to describe what you need in plain language, and it generates the server-side endpoint, web role assignments, table permissions, a typed client-side service, and component updates.</p>



<p class="wp-block-paragraph">Here&#8217;s an example. Say your order form needs to validate inventory before accepting a submission:</p>


<div class="wp-block-syntaxhighlighter-code "><pre class="brush: plain; title: ; notranslate">
You: "/add-server-logic Add validation that rejects orders when quantity exceeds inventory"

Plugin:
        → Creates server-logic/validate-order.js (server-side endpoint)
        → Assigns Authenticated Users web role
        → Verifies table permissions for cr_inventories
        → Creates src/services/serverLogic/validateOrder.ts (typed client)
        → Updates OrderForm.tsx to call validateOrder() before submit

</pre></div>


<p class="wp-block-paragraph">Or say your site needs a global search that queries across multiple Dataverse tables (products, orders, and knowledge articles) and returns unified results. That kind of cross-entity aggregation can&#8217;t run from the browser in a single call:</p>


<div class="wp-block-syntaxhighlighter-code "><pre class="brush: plain; title: ; notranslate">
You: "/add-server-logic Add a global search endpoint that searches across products,
      orders, and knowledge articles and returns combined results"

Plugin: 
        → Creates server-logic/global-search.js (server-side endpoint)
        → Queries cr_products, cr_orders, and cr_knowledge_articles
        → Aggregates and ranks results server-side
        → Assigns Authenticated Users web role
        → Verifies table permissions for all three tables (Read)
        → Creates src/services/serverLogic/globalSearch.ts (typed client)
        → Updates SearchPage.tsx to call globalSearch() on input

</pre></div>


<p class="wp-block-paragraph">Before generating any code, a built-in <strong>Server Logic Architect agent</strong> analyzes your use case and presents a proposal for your review.</p>



<h3 class="wp-block-heading" id="add-cloud-flow-power-automate-integration-from-your-site">/add-cloud-flow: Power Automate integration from your site</h3>



<p class="wp-block-paragraph">Not everything belongs in a server-side endpoint. Approval workflows, email notifications, and event-driven automation are better suited to Power Automate cloud flows. The <code><strong>/add-cloud-flow</strong></code> skill integrates an <strong>existing </strong>cloud flow into your Power Pages site. <em>It does not create new cloud flows. You build the flow in Power Automate, and the skill handles the integration</em>: registering the flow with your site, generating the client-side code to trigger it, and wiring up data exchange between the page and the flow.</p>


<div class="wp-block-syntaxhighlighter-code "><pre class="brush: plain; title: ; notranslate">
You: "/add-cloud-flow Connect the supplier approval flow to my application page"

Plugin: 
        → Registers the existing cloud flow with your site
        → Generates client-side code to trigger the flow
        → Handles async workflow state and callback patterns

</pre></div>


<p class="wp-block-paragraph">Whether it&#8217;s a manager approval step, an order confirmation email, or a nightly data sync, <code>/add-cloud-flow</code> handles the integration so you focus on the business process.</p>



<h3 class="wp-block-heading" id="integrate-backend-let-ai-choose-the-right-approach">/integrate-backend: let AI choose the right approach</h3>



<p class="wp-block-paragraph"><strong>Start here if you&#8217;re not sure whether a feature needs Web API, Server Logic, or a cloud flow. </strong><code><strong>/integrate-backend</strong></code> acts as your <strong>server-side architect</strong>. It analyzes your website, determines the right approach for each feature, and orchestrates the plugin skills to build everything in the correct order.</p>



<p class="wp-block-paragraph">Take a supplier portal with product listings, order submission, a global search across products and orders, and an invoice approval workflow. Without <code>/integrate-backend</code>, you&#8217;d need to figure out that product listings are standard CRUD (Web API), global search requires cross-entity aggregation on the server (Server Logic), and invoice approvals need a multi-step flow (Power Automate). You&#8217;d also need to sequence the work: Dataverse tables before Web API, web roles before Server Logic, authentication before server-side endpoints.</p>



<p class="wp-block-paragraph">The <code><strong>/integrate-backend</strong></code> skill automatically scans your entire website and recommends relevant business processes.</p>


<div class="wp-block-syntaxhighlighter-code "><pre class="brush: plain; title: ; notranslate">
You: /integrate-backend

Plugin:
  ANALYSIS
  ════════
  #   Feature              Approach         Reason
  1   Product listings     Web API          Standard CRUD on cr_products
  2   Order submission     Server Logic     Inventory validation + transaction
  3   Global search        Server Logic     Cross-entity aggregation on server
  4   Invoice approvals    Cloud Flow       Multi-step approval workflow


</pre></div>


<h2 class="wp-block-heading" id="how-it-works">How it works</h2>



<p class="wp-block-paragraph">Every skill follows a <strong>propose-then-build </strong>workflow. An AI architect agent analyzes your request, designs the solution, and presents it for approval. No code is generated, and no infrastructure is created until you approve. This keeps you in control while eliminating manual configuration.</p>



<p class="wp-block-paragraph">The decision framework is simple:</p>



<ul class="wp-block-list">
<li class="wp-block-list-item"><strong>Server Logic</strong>. Secrets or API keys, server-side validation, multi-table transactions, external or on-premises service calls, cross-entity search, rate limiting, or Dataverse plugin invocation.</li>



<li class="wp-block-list-item"><strong>Cloud flow</strong>. Approval workflows, notifications, or scheduled processing.</li>



<li class="wp-block-list-item"><strong>Web API</strong>. Everything else (standard CRUD operations).</li>
</ul>



<h2 class="wp-block-heading" id="benefits">Benefits</h2>



<ul class="wp-block-list">
<li class="wp-block-list-item"><strong>Enhanced security.</strong> Business logic, secrets, and API keys stay on the server and are never exposed in the browser.</li>



<li class="wp-block-list-item"><strong>Reduced manual configuration.</strong> Each skill generates endpoints, permissions, typed services, and component updates end to end.</li>



<li class="wp-block-list-item"><strong>Intelligent approach selection.</strong> <code>/integrate-backend</code> determines whether each feature needs Web API, Server Logic, or a cloud flow, so you don&#8217;t have to.</li>
</ul>



<h2 class="wp-block-heading" id="get-started">Get started</h2>



<h3 class="wp-block-heading" id="install-or-update-the-plugin-and-pac-cli">Install or update the plugin and PAC CLI</h3>



<p class="wp-block-paragraph"><strong>Install the latest plugin and PAC CLI, as both are required</strong>. <span style="text-decoration: underline;">Server logic support was introduced in the latest PAC CLI release, so older versions will not work</span> with <code><strong>/add-server-logic</strong></code>. For the easiest setup, use <a href="https://learn.microsoft.com/power-pages/configure/create-code-site-using-claude-code#quick-install-recommended">Quick Install (recommended)</a>, which installs all Power Platform plugins, updates PAC CLI, and enables auto-update. </p>



<p class="wp-block-paragraph"><strong><a href="https://learn.microsoft.com/en-us/power-pages/configure/create-code-site-using-claude-code" rel="noreferrer noopener" target="_blank">Get started with the Power Pages plugin for GitHub Copilot CLI and Claude Code</a>.</strong></p>



<h2 class="wp-block-heading" id="we-are-looking-for-your-feedback">We are looking for your feedback</h2>



<p class="wp-block-paragraph">Your feedback helps us improve the developer experience on Power Pages. Share your thoughts and reach out on the&nbsp;<a href="https://powerusers.microsoft.com/t5/Power-Pages-Community/ct-p/PowerPagesCommunity" rel="noreferrer noopener" target="_blank">Power Pages Community Forum</a>. You can also submit ideas through the&nbsp;<a href="https://ideas.powerpages.microsoft.com/" rel="noreferrer noopener" target="_blank">Power Pages Ideas portal</a>.</p>



<p class="wp-block-paragraph"></p>
<p>The post <a href="https://www.microsoft.com/en-us/power-platform/blog/power-pages/build-your-server-side-logic-with-ai-new-power-pages-agentic-code-skills/">Build your server-side logic with AI: new Power Pages Agentic Code skills</a> appeared first on <a href="https://www.microsoft.com/en-us/power-platform/blog">Microsoft Power Platform Blog</a>.</p>
