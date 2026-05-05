---
title: "Power Platform Monitor Alerts Are Now Generally Available"
url: "https://www.microsoft.com/en-us/power-platform/blog/power-apps/power-platform-monitor-alerts-are-now-generally-available/"
date: "Wed, 08 Apr 2026 17:12:51 +0000"
author: "Arjun Mayur"
feed_url: "https://www.microsoft.com/en-us/power-platform/blog/feed/"
---
<p class="wp-block-paragraph">We are excited to announce that Power Platform Monitor alerts are now generally available! Since entering public preview in August&nbsp;2025, many organizations have created alert rules to stay on top of app, agent and flow health. Reliability is critical when alerts are used to detect and respond to issues in production. Today, Monitor alerts meet the reliability and maturity standards required for general availability, following sustained investments to improve quality and simplify onboarding.</p>



<figure class="wp-block-image size-full is-resized"><img alt="This image shows the new Monitor overview page, which has become more alerts-centric. It has visuals describing the state of your triggered custom alerts in addition to triggered predefined alerts that are authored by Microsoft. " class="wp-image-133695" height="1032" src="https://www.microsoft.com/en-us/power-platform/blog/wp-content/uploads/2026/03/monitor-overview-page.jpg" width="2475" /></figure>



<h2 class="wp-block-heading" id="what-are-monitor-alerts">What are Monitor Alerts?</h2>



<p class="wp-block-paragraph">Monitor alerts&nbsp;allow tenant and environment administrators to proactively monitor the operational health of their Power Platform resources and receive notifications when health metrics fall below thresholds they define. Instead of learning about problems from end users, admins can identify and address issues before they cause disruption. This reduces downtime and improves reliability across the organization.</p>



<p class="wp-block-paragraph"><a id="_msocom_1"></a></p>



<h2 class="wp-block-heading" id="what-s-new-with-ga">What&#8217;s New with GA</h2>



<h3 class="wp-block-heading" id="predefined-alerts-protection-with-zero-configuration">Predefined alerts — protection with zero configuration</h3>



<p class="wp-block-paragraph">The biggest addition we’ve added is predefined alerts: a set of configured, Microsoft-authored alerts that are enabled by default for every tenant. These alerts automatically surface high-use canvas apps, model-driven apps, agents, desktop flows and cloud flows whose health has dropped below recommended baseline thresholds — with no setup required.</p>



<p class="wp-block-paragraph">For example, predefined alerts will flag when:</p>



<ul class="wp-block-list">
<li class="wp-block-list-item">The availability of high-use canvas apps drops below 90%</li>



<li class="wp-block-list-item">The availability of high-use model-driven apps drops below 90%</li>



<li class="wp-block-list-item">High-use cloud flows are experiencing success rate degradation</li>
</ul>



<p class="wp-block-paragraph">Predefined alerts give admins an immediate signal on what matters most in their tenant, even before they’ve configured a single custom alert rule. Items can trigger these alerts regardless if they’re in a managed environment, and predefined alerts will encourage&nbsp;users to create their own alert rules to monitor these items against their own custom thresholds. </p>



<p class="wp-block-paragraph"><a id="_msocom_1"></a></p>



<figure class="wp-block-image size-full is-resized"><img alt="This image shows the triggered alert experience for a predefined alert. In this image, it specifically shows the cloud flow predefined alert, with two cloud flows that triggered it. These cloud flows aren't in a Managed Environment." class="wp-image-133697" height="466" src="https://www.microsoft.com/en-us/power-platform/blog/wp-content/uploads/2026/03/cloud-flow-triggered-alert-.jpg" style="width: 900px;" width="1627" /></figure>



<h3 class="wp-block-heading" id="redesigned-monitor-overview-page">Redesigned Monitor overview page</h3>



<p class="wp-block-paragraph">We redesigned the Monitor overview page to be alerts-centric. When you land in Monitor, you now get an at-a-glance view of active alert conditions and resource health across your environments — making it faster to identify what needs attention and act on it.</p>



<h3 class="wp-block-heading" id="code-app-alerts">Code app alerts</h3>



<p class="wp-block-paragraph">Custom alert rules now support alerting on your code apps in addition to canvas and model-driven apps. This gives admins deeper visibility into code app performance and the ability to catch performance degradation before it affects users’ day-to-day experience.</p>



<h3 class="wp-block-heading" id="work-queue-alerts-public-preview">Work queue alerts (public preview)</h3>



<p class="wp-block-paragraph">Admins can now configure alerts for Power Automate work queues in Monitor, enabling proactive monitoring of work queue health alongside apps, flows and agents. This capability is launching in public preview alongside alerts GA. </p>



<h2 class="wp-block-heading" id="how-monitor-alerts-work">How Monitor Alerts Work </h2>



<p class="wp-block-paragraph">Admins define threshold-based rules on Monitor metrics. For example, this can look like receiving an alert when a cloud flow’s success rate drops below a custom threshold, or when a canvas app’s availability falls below an acceptable level.</p>



<p class="wp-block-paragraph">Monitor alerts evaluate alert rules daily after aggregating new metric data for your environments. When a metric breaches a threshold, admins receive an email notification with a direct link to the details that triggered the alert.</p>



<p class="wp-block-paragraph">You can scope alert rules to an environment or individual item, configure multiple recipients per rule (including security groups), and manage all active rules and review triggered alert history from the Alert Rules view in Monitor.</p>



<figure class="wp-block-image size-full is-resized"><img alt="This image shows the alert configuration panel in Monitor, where admins can create their own custom alert rule to proactively monitor the resources they care about against health thresholds they define. " class="wp-image-133699" height="1276" src="https://www.microsoft.com/en-us/power-platform/blog/wp-content/uploads/2026/03/cloud-flow-alert-rule.jpg" width="1890" /></figure>



<figure class="wp-block-image size-large is-resized"><img alt="This image shows the alert rule list in Monitor, where admins can manage their rules, like turning them on/off or editing or deleting them. " class="wp-image-133700" height="647" src="https://www.microsoft.com/en-us/power-platform/blog/wp-content/uploads/2026/03/alert-rule-list-1024x647.jpg" width="1024" /></figure>



<h2 class="wp-block-heading" id="what-s-supported">What&#8217;s Supported</h2>



<figure class="wp-block-table aligncenter"><table class="has-fixed-layout"><tbody><tr><td><strong>Product</strong></td><td></td><td><strong>Resource</strong></td></tr><tr><td>Power Apps</td><td></td><td>Code apps</td></tr><tr><td>Power Apps</td><td></td><td>Canvas apps</td></tr><tr><td>Power Apps</td><td></td><td>Model-driven apps</td></tr><tr><td>Power Automate</td><td></td><td>Cloud flows</td></tr><tr><td>Power Automate</td><td></td><td>Desktop flows</td></tr><tr><td>Power Automate</td><td></td><td>Work queues <em>(public preview)</em></td></tr><tr><td>Copilot Studio</td><td></td><td>Agents</td></tr></tbody></table></figure>



<p class="wp-block-paragraph">We&#8217;re excited for you to improve the operational health of your apps, agents and automations in Power Platform. Learn more about Monitor and how to create alerts <a href="https://learn.microsoft.com/en-us/power-platform/admin/monitoring/alerts">here</a>.</p>



<p class="wp-block-paragraph"></p>
<p>The post <a href="https://www.microsoft.com/en-us/power-platform/blog/power-apps/power-platform-monitor-alerts-are-now-generally-available/">Power Platform Monitor Alerts Are Now Generally Available</a> appeared first on <a href="https://www.microsoft.com/en-us/power-platform/blog">Microsoft Power Platform Blog</a>.</p>
