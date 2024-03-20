---
layout: category
title: Architect overlay
permalink: /overlays/role/architect
---

# Architect

As an architect you can exert significant influence on a company's tech carbon emissions. You might be a technical/solutions/enterprise/other architect and although the scope may vary across architecture roles there's many common activities where you can have a positive impact on carbon emissions including: 

 1. Setting the tech strategy
 2. Promoting best practice
 3. Leading technical selection, e.g. of a cloud vendor or a SaaS product
 4. Designing architecture (from enterprise to technical) 
 5. Setting NFRs

The first couple are high level activities that can vary from setting the cloud vs on-prem strategy through to promoting technical principles around resilience or serverless vs container or data retention.

The remaining 3 are actually all about NFRs to some degree. Tech selection will be done against a set of functional and non-functional requirements and architecture design choices will be done against a set of NFRs, e.g. to promote availability or low cost. Let's see then how strategy and setting NFRs can be used to influence low carbon. 

{% include linkedHeading.html heading="Setting strategy and best practice" level=2 %}

The diagram below gives takes the standard and overlays on the categories some examples of how you might influence them:
![embodied-carbon](/assets/images/overlays/arch_strat_overlay.png)

We'll now provide a bit more detail on each of these:

{% include linkedHeading.html heading="Upstream" level=3 %}

{% include linkedHeading.html heading="Commercial" level=4 %}

All software creation comes with a cost and the first thing you might decide to do is to trade off open source and COTS software against in-house. Some of the in-house software carbon costs are out of the scope in this standard because they are non-technology items like buildings and transport for employees. Still you may wish to increase your emissions within the standard by using existing software rather than creating your own as existing software is sharing the carbon impact across many orgs, not just yours. 

You may also wish to prefer vendors who report on their emissions and follow sustainability best practices in order to push software and machine learning model creators to be more sustainable. e.g. training models with renewable electricity. 
{% include linkedHeading.html heading="Hardware Manufacture, Transport and Installation" level=2 %}

Any hardware you buy in or acquire from data centre servers to employee laptops required energy produced emissions in manufacture and transport. Not all architects will get involved in hardware selection - servers and network equipment may fall under data centre architects for example. Where you do though you can apply pressure to ensure there is a low carbon strategy for:
 * Renewal cycles, i.e. how often we should replace hardware. Less hardware bought per year is less emissions
 * Recycling. Check the criteria under which your current disposal partners were selected and if recycling and low energy usage were not considerations make sure they are next time the contrcats come around. 
 * Procurement. Do the procurement teams understand the emissions with each item they supply? If not kick-off an initiative to look at this and ensure equipment is bought with a known embodied carbon and ideally a target to keep it under. 

{% include linkedHeading.html heading="Operational emissions" level=3 %}

Whether you are running in the cloud or on-prem architects can promote architectural patterns and ways of using resources to minimise day to day energy usage. This might include requiring use of efficient APIs such as gRPC, sharing resources as much as possible, carbon aware computing and having data dormancy strategies so data isn't held and stored later than needed. These may also have benefits on resilience, cost and compliance and the architect should take a holistic view.

They will work with dev-ops or developers or date centre engineers on tech strategies and should ensure carbon emissions are parts of those strategies. 

Observability is a key part of technical strategy that requires a joined up apprach between dev-ops, development and operations and architects should promote energy observability as part of this. 

{% include linkedHeading.html heading="Direct (Category O)" level=4 %}
In the embodied section we talked about hardware selection maximising lifetime and having low manufacture emissions. Procurement strategy should also include observability and emissions in use. Accurate energy obserability (and thus carbon monitoring) is not possible without hardware support and so this must be a consideration when selecting hardware for the data centre. 

Servers: As well as the general application design patterns senior architects can drive virtualisation strategy for on-prem. For example they could create a plan for containerisation of workloads (e.g. to Kubernetes) and a migration plan in order to maximise the utilisation of on-prem hardware. 

Networks:
As with servers, architects can add usage emissions to the procurement evaluation criteria. 
Architects can help translate business growth requirements into expected data transfer needs and ensure the correct size of networking hardware is selected that is well utilised. Typically networking hardware doesn't scale down in power in the way standard servers do and so under utilised hardware will have a heavier cost. 

Where there's virtual networking functions running purely as software the same utilisation concerns apply as with any application - maximise software, albeit traded off against maximum latency and contention needs, i.e. promote the virtualisation (in software sense of the word) of the software networking appliances. 

Having application principles to minimise data transfer can reduce the amount of network traffic and even if this makes only a small reduction to the energy usage of switches and routers it may slow the need to add more hardware during growth. e.g. gRPC, persistent TCP connections

Patterns like multi-cast for video can be pursued to reduce network capacity needs in the data centre (and ISP). Similarly large file transfers can be architected to take the most direct route without intermediary systems reducing network emissions and costs.
A preference for larger more monolithic applications may also reduce network traffic - but can be other costs.  

User devices:
Where architects are involved in workforce IT like employee devices there's a few of areas they can influence:
 1. Like servers and other infra prefer devices with low operational power, e.g. an ARM chip device if an option
 2. Put requirements on device power management. Ensure there is proper testing of device configuration such that laptops run in low power modes when with low activity and go to sleep quickly
 3. Device a strategy for device power monitoring which would make carbon reporting much easier and allow improvements in devices or their configuration to be observed over time. 

{% include linkedHeading.html heading="Indirect (Category C)" level=4 %}

All the indirect solutions involve a vendor and so it is important that archtects, where involved in vendor selection include carbon non functional requirements. This should include both how the vendor reports emissions but also the level of their emissions and how "green" their electricity is. 

Cloud:
The architect can set principles and present patterns for sustainable application development as per on-prem. In addition they may require the use of cloud spefific patterns where applicable such as the use of serverless for infrequently used applications. 

The principle of observability remains the same and should be a key technical principle pushed down from architects. For cloud the architect must find different models to assess cloud energy usage in the absence of hardware monitoring and may recruit data science teams to support this. 

SaaS:
The main levers here for the architect are in the aforementioned vendor selection.

Technical principles should also apply for the use of a vendor service as much as for an internal service, e.g. around not calling APIs unnecessarily or caching.  

Managed services:
As well as vendor selection and good software design patterns there may be options to improve utilisation as with on-prem, e.g. devising a containerisation strategy to better utilise vendor provided virtualisation. Where the service is data related principles around data retention can reduce emissions. 

{% include linkedHeading.html heading="Downstream" level=3 %}

## Setting Non-functional-requriements (NFRs)

In this section we'll look at some of the NFRs (also known as Quality Attributes) that could be set by architects in order to promote energy efficiency and low carbon emissions. 

These will typically derive from the principles and strategy set by the  architects that were discussed in the previous section; they are one of the outputs of the strategy. The diagram below overlays these onto the Tech Carbon Standard according. Actually some NFRs may have benefits in more than one area, but this gives you an idea of where they most impact. For example energy efficency code may require less hardware which means less manufacturing energy as well as usage    

![embodied-carbon](/assets/images/overlays/arch_strat_nfrs.png)

{% include linkedHeading.html heading="Upstream" level=3 %}

{% include linkedHeading.html heading="Commercial" level=4 %}

<ul>
<li><b>Prefer vendor with a sustainability strategy:</b> When choosing a vendor adding a selection criteria favouring a company with a sustainability strategy and measured emissions creates market pressure for vendors to be reporting and reducing emissions. </li>

<li><b>Prefer higher user base:</b> Adding NFR around user base size means you'll be getting something well tested and more likely to be supported but can also influence carbon emissions. If you pay an organisation to create bespoke software for you or train a bespoke model for you teh incurred emissions will only benefit your user base. On the other hand adopting open source software used by 100 companies and their users means there's a small attribution to you and there's less duplicated work. The same applies for internal build vs buy although in this case there's category O emissions and other non tech ones like buildings. 
</li>
</ul>

{% include linkedHeading.html heading="Hardware Manufacture, Transport and Installation" level=2 %}

NFRs here fall easily out of the strategy above and can include:

<ul>
<li><b>Lifetime (inc. support) &gt;= 5 years: </b> puts a clear requirement on procurement.</li> 

<li><b>Laptop/Switch/Server should have &lt;x embodied kgCO2.</b>You can relate embodied carbon to a scale factor like throughput or number of ports of network equipment. </li>
</ul>

A software implementation NFR may also drive reduce embodied carbon. e.g. around reducing resource used per service or an NFR like:

<ul>
<li><b>New service should add no embodied emissions:</b> requiring a new service to use no additional embodied carbon means it must run on existing hardware. </li>
</ul>


{% include linkedHeading.html heading="Operational emissions" level=3 %}
For operational emissions you can directly target energy or emissions with your NFRs or proxy measures that will still promote reduced emissions. An obvious example of the latter is utilisation of a physical or virtual server, e.g. <b>utilisation should be > 50%</b>. 


TODO expand here
<li><b>Energy per service or even per API REST endpoint call should be &lt;x gCO2:</b> Such an NFR pushes development teams to optimise their apps. </li>

{% include linkedHeading.html heading="Direct (Category O)" level=4 %}
At the level of the data centre NFRs could include the following. 
<ul>
<li><b>Data centre PUE should be &lt; 1.3:</b> When building out a new data centre you can set a maximum Power Usage Effectiveness.</li>
<li><b>Carbon intensity should be &lt;x kgCO2/kWh:</b> Setting an NFR around the carbon intensity of the electricty influences choices on location or installation of wind turbines or solar. </li>
</ul>

<b>Servers:</b> You can set utilisation targets for each server as per above but also go more granular. e.g. 
<ul>
<li><b>Utilisation should be > 50%</b></li>
<li><b>Energy per service or even per API REST endpoint call should be &lt;x gCO2:</b> Such an NFR pushes development teams to optimise their apps. </li>
<li><b>Servers must be energy observable via the network: </b>Really a function requirement but allows monitoring of progress in energy efficiency</li>
</ul>


<b>Networks:</b> 
Again utilisation or power/carbon usage tarrgets can be set:
<ul>
<li><b>Network switch utilisation should be &gt;40%</b></li>
<li><b>Power per port should be &lt; 2W</b>Power per Gbps throughput or per port could be targetted just as an embodied carbon can be also. 
</li></ul>

Some application targetted NFRs may also reduce network traffic and so reduce the need to have more network hardware - benfits operational and embodied. e.g.
<ul>
<li><b>Data compression of 50% vs raw text in API payloads</b>: promote zipping and/or efficient protocols like gRPC</li>
<li><b>normalise async messages, no one:many entity to message mappings</b>avoids one entity change causing a storm of messages</li>
</ul>
 

<b>User devices:</b>
In the strategy section there were suggestions around selecting laptops with low energy usage and ensuring they switch to low power, sleep etc. A target average daily kWh energy usage could be set with these policies designed to meet it e.g.
<ul>
<li><b>Average energy consumption per 24 hours &lt;x gCO2</b>: promote zipping and/or efficient protocols like gRPC</li>
</ul>

{% include linkedHeading.html heading="Indirect (Category C)" level=4 %}

When vendors are used then you can set NFRs around their electricity e.g. 
<ul>
<li>30% electricity from renewable sources.</li>
</ul>
You may also set NFRs for carbon per unit of compute or request as well see below. Exactly what you can do will be very much dependent on the amount of information provided. This may itself be a criteria, who gives the most transparent information about their emissions. 

<b>Cloud:</b> Be careful when comparising vendors as reporting norms may vary. NFRs could include:
<ul>
<li><b>Prefer compute with &lt;g CO2 per core: </b> Pushes CPUs with lower power, e.g. ARM or CPUs powered by more renewable energy, e.g. in a different region. Be careful to weight according to CPU power though - clock requencies and processing capacity will vary</li> 
<li><b>Create  no emissions when no requests are being handled:</b> Pushes the use of scale down or lambdas whilst not forcing an implementation</li>
</ul>
Note: When targetting regions or times of day via NFRs be aware of the risks - if everyone does it then it'll result in dispatchable power like gas being used. 

SaaS:
Ideally when selecting a service you'd have a criteria like "level of CO2 per end user API request &lt;x gCO2". 
Otherwise you may just have to look at their total emissions vs customer base.

<ul>
<li></li>
<li></li>
</ul>

<ul>
<li></li>
<li></li>
</ul>

<ul>
<li></li>
<li></li>
</ul>

Managed services:
PUE< 1.3
Utilisation &lt;= 50%, You can set NFRs for the utilisation of resources as with on-prem and the cloud. 


{% include linkedHeading.html heading="Downstream" level=3 %}

We have no control over the end user devices like customer laptops but we can set NFRs to ensure that web pages are not using unnessary power and data transfer is limited, which will also have benefits on battery life in many cases. 

Device:
  
 * page view &lt; x kWh
    * Promote pages that don't uneccessarily use energy
 * 0 energy usage when user not on page
    * Ensure no energy used when user not on a webpage. Note modern browsers will help enforce this anyway

Network:
 * Follow-up calls to the API should use &lt 80% energy of first call