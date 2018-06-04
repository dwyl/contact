# Market Research

The purpose of this doc is to have _comprehensive_
[Market research](https://en.wikipedia.org/wiki/Market_research)
of CRM systems for the following reasons:

1. To know **what** `else` is available and ***why*** people/teams would
want to use the product/service.
2. To _understand_ what **features** are considered ***essential***
vs. "***nice to have***".
3. **Test UX** of the widest possible range of products/services
to determine which is **most intuitive/user-friendly**.



## Comparison Table

<!--
Should we make this a "real" HTML table for sorting/filtering?
-->

| Product/Service Name | Open/Closed Source | Cost | Pricing Model | API | UX | Keyboard Shortcuts | Automation | Kanban / Drag+Drop | Custom Fields/Data | Custom Workflow |
| ------------- |:-------------:| ----- | --- |:--- | --- | --- | --- | --- | --- | --- |
| [hubspot.com](https://www.hubspot.com) | Closed | [$42/user/month](https://www.hubspot.com/pricing/sales) for _first_ user | 3 Tiers: "Free", Starter: $42 for **1 user** & "Professional": $330 for 5 users = **$66/u/m** | REST https://developers.hubspot.com/ | Kanban | [**No**](https://community.hubspot.com/t5/HubSpot-Ideas/keyboard-shortcuts/idi-p/12244) | Yes | Yes | [Yes](https://api.insight.ly/v2.2/Help#!/Overview/Technical_Details) | Yes |
| [insightly.com](https://www.insightly.com) | Closed | [$49/user/month](https://www.insightly.com/pricing) | 3 Tiers: "Plus": $29/u/m, Professional: $49/user/month & "Enterprise": $99/u/m | REST https://api.insight.ly/v2.2/Help | Kanban/Outlook Inbox | [Yes](https://support.insight.ly/hc/en-us/articles/204248780-Keyboard-shortcuts) | Yes | Yes | Yes | Yes |
| [Pipedrive.com](https://www.pipedrive.com) | Closed | [$29/user/month](https://www.pipedrive.com/en-gb/plans) | 3 Tiers: Silver: 15/u/m, Gold: $29/u/m & "Platinum": $75/u/m | REST + Webhooks https://developers.pipedrive.com/docs/api/v1/ | Kanban Board | Yes | Yes | Yes | Yes | Yes |
| [Salesforce.com](https://www.salesforce.com) | Closed | [$25/user/month](https://www.salesforce.com/editions-pricing/platform) | Variable/Opaque from $25 to $300/u/m! | REST + Stream https://developer.salesforce.com/page/Salesforce_APIs | "Classic" ("Clunky") or "Lightning" (Drag-and-drop) | Yes | Yes | Yes | Yes | Yes |
| [Streak.com](https://www.streak.com) | Closed | $49/user/month | 3 Tiers: Free, Professional ($49/user/month) & "Enterprise" ($99/user/month) | REST https://streak.readme.io/ | Gmail Inbox | Yes | Yes | **No** | **No** | **No** |
| [SugarCRM.com](https://www.sugarcrm.com) | Closed | [$40/user/month](https://www.sugarcrm.com/product/pricing-editions) | 3 Tiers: Professional ($40/u/m),  "Enterprise" ($65/u/m) & "Ultimate" ($150/u/m) | REST http://support.sugarcrm.com/Documentation/?docVersion=8.0&docEdition=Pro | "Traditional CRM" (no kanban) | Yes | Yes | **No** | Yes | Yes |


# List (Alphabetical)

> Meta: should this list be Alphabetical or in order of Popularity?
(_I get the feeling that Alphabetical will make locating an entry easier
and thus aid maintenance ..._)

## HubSpot CRM

Hubspot is a modern CRM system with _good_ UI.
![hubspot-crm-ui](https://user-images.githubusercontent.com/194400/40930403-83396116-681f-11e8-9602-aebb516a3398.png)

On the _surface_ the cost _appears_ to be
["Free"](https://www.hubspot.com/pricing/crm ...
  (_a more accurate description would be "freemium"_)<br />
![hubspot-crm-no-features](https://user-images.githubusercontent.com/194400/40932720-312dcbca-6827-11e8-8bc1-4aa42f09fd1a.png)

The HubSpot CRM system is _deliberately disabled_
 (_is missing key features like email tracking_):
 ![hubspot-crm-free-but-has-pricing](https://user-images.githubusercontent.com/194400/40930212-f609c7cc-681e-11e8-934d-800fca718e0f.png)
 ![hubspot-crm-no-features](https://user-images.githubusercontent.com/194400/40932759-4e9e2f10-6827-11e8-9ba3-f40b3d185072.png)
 a bit of digging in the "legal" section of the website, shows the "Free" CRM
 is actually a  “lite” version with "select features":
 https://legal.hubspot.com/hubspot-product-and-services-catalog
 ![hubspot-lite-version](https://user-images.githubusercontent.com/194400/40933116-72f64f86-6828-11e8-8e7f-acc90a73adc6.png)
 so that they can "_up-sell_" to the "Sales Hub" service ...
![hubspot-sales-hub-pricing](https://user-images.githubusercontent.com/194400/40930720-62f201c8-6820-11e8-9706-acadf9264fd7.png)


> **No** support on the free plan, for CRM users or API users
(_the whole point of the "Free CRM" is to up-sell people_)


### Satisfices Requirements?
Full features here: https://www.hubspot.com/products/crm
 and https://knowledge.hubspot.com/getting-started-with-the-hubspot-crm-free/
+ Provides a kanban board style deal pipeline
  + Customisable pipeline stages and [fields](https://knowledge.hubspot.com/getting-started-with-the-hubspot-crm-free/a-quick-tour-of-deals-and-deal-properties)
+ No _native_ Mailchimp integration, but looks like there are
a few alternatives you would need to try out to see if they
meet the details of your needs:
https://zapier.com/apps/hubspot-crm/integrations/mailchimp
or https://automate.io/integration/hubspot/mailchimp
  + Note: https://www.youtube.com/watch?v=NuftV4sp99M
  shows this kind of integration in action
+ **Does not support multiple currencies**

The API in general looks to support the majority of the requirements
but we didn't dig into the detail level here as the lack of support
for multiple currencies is likely a deal breaker.


## Insightly

Found by Chris, custom kanban sales pipeline.
![insightly-ui](https://user-images.githubusercontent.com/194400/40928360-0dcaa3be-6819-11e8-8c75-c0332b920709.png)

**Cost**: Mid-range: https://www.insightly.com/pricing/
![insightly-pricing](https://user-images.githubusercontent.com/194400/40928269-cd8e9968-6818-11e8-8620-a448181712a8.png)
(note that custom dashboards - different from kanban board -
  and workflow automation are on the middle pricing tier)


### Satisfices Requirements?
Full features here:
+ Provides customisable kanban pipeline
  + 50 custom fields included with the lightest plan
+  Probably the tightest integration with Mailchimp (aside from using Pipechimp with Pipedrive), though appears that you might have to export your contacts manually when you use mailchimp (https://www.insightly.com/product/connect-to-apps/mailchimp-crm/) - this will need to be tested

### API
+ API is a bit more complex than the others and the documentation is understandable but not great https://api.insight.ly/v2.2/Help
  + There are multiple types of deals - i.e. starts as a `lead` and moves on to become an `opportunity` so we would need to agree the business process here in detail so that the site knew where to pick up updated status, etc.
  + [`Contacts`](https://api.insight.ly/v2.2/Help#!/Contacts/) can only be found via ID (not email) which means slightly more complex (not insurmountable) operations to ensure we're storing data correctly on the application
  + Retrieving the opportunities and their statuses looks to be straightforward 👍 https://api.insight.ly/v2.2/Help#!/Opportunities/GetOpportunitiesBySearch
  + Adding/updating [custom fields](https://api.insight.ly/v2.2/Help#!/Overview/Technical_Details) is possible both in the app and in the API
+ No developer community



## Pipedrive

Highly regarded, Kanban-based tool with a simple UI and well documented API.

**Cost**: Mid-range https://www.pipedrive.com/en-gb/plans

<img width="1228" alt="screen shot 2018-06-01 at 06 14 20" src="https://user-images.githubusercontent.com/4185328/40822214-17afe97e-6563-11e8-90ed-c2b0ef2708bf.png">

### Satisfices Requirements?

Full features here: https://www.pipedrive.com/en-gb/features/
+ Built around the kanban board concept
  + Customisable pipeline stages and fields
+ Mailchimp integration, see article and importantly comments for details: https://blog.pipedrive.com/2015/05/introducing-an-easier-pipedrive-and-mailchimp-integration/
  + It's _possible_ that Pipedrive may not _entirely_ satisfy requirements without adding in the use of Pipechimp; see https://blog.pipedrive.com/2018/04/mailchimp-pipedrive-pipechimp/
  + Mid-level pricing plan does include email integration and tracking of its own

### API

+ Decently documented API and relatively simple: https://developers.pipedrive.com/docs/api/v1/#/
  + Deals well with multiple currencies
  + Each contact would be a [`Person`](https://developers.pipedrive.com/docs/api/v1/#!/Persons/get_persons_find) with each enquiry being a [`Deal`](https://developers.pipedrive.com/docs/api/v1/#!/Deals)
    + Can [find people by email address](https://developers.pipedrive.com/docs/api/v1/#!/Persons/get_persons_find) and therefore check whether they already exist in the DB before sending through the enquiry
  + Limited status of deals from initial investigation (needs further investigation): https://developers.pipedrive.com/docs/api/v1/#!/Deals/post_deals
  + Adding/updating [custom fields](https://pipedrive.readme.io/v1.0/docs/core-api-concepts-custom-fields#section-types-of-custom-fields) is possible both in the app and in the API
+ _Some_ activity in the community, not a whole lot https://devcommunity.pipedrive.com/ (telephone support available on higher plans)

Video Walkthrough (_official_): https://youtu.be/tjN0BxyrqOk (_Jan 11, 2017_)
Customer "getting started": https://youtu.be/pzs5hTa3Uxs (_Mar 27, 2017_)

API: https://www.pipedrive.com/en/features/api
Custom Fields: https://pipedrive.readme.io/docs/core-api-concepts-custom-fields





## Salesforce

Goliath. By _far_ the biggest CRM provider.

![salesforce-lightnight-ui](https://user-images.githubusercontent.com/194400/40925765-5977db08-6812-11e8-939a-3b8305ce2b3a.png)

Pricing: https://www.salesforce.com/editions-pricing/platform/
![salesforce-pricing](https://user-images.githubusercontent.com/194400/40926797-0b0bf21c-6815-11e8-9bee-5236c24fd0d7.png)

https://www.salesforce.com/form/conf/overview-demo
![salesforce-sales-cloud-overview](https://user-images.githubusercontent.com/194400/40899981-7453b9a2-67c1-11e8-91e7-9788c9280cc0.png)
Salesforce Lightning Demo: https://youtu.be/s_sHeac3gfo

API:
+ List of APIs: https://developer.salesforce.com/page/Salesforce_APIs
+ REST: https://developer.salesforce.com/page/REST_API
+ Streaming: https://developer.salesforce.com/page/Streaming_API
![image](https://user-images.githubusercontent.com/194400/40904712-7e120144-67d3-11e8-84c4-632880541f9a.png)

+ "Hidden costs":
https://www.contactmonkey.com/blog/salesforce-pricing-hidden-costs <br />
(_note "contact monkey" is a basic CRM, i.e. they compete with Salesforce!_)

## Streak

GMail based CRM: https://www.streak.com
![image](https://user-images.githubusercontent.com/194400/40925131-e03e4b7e-6810-11e8-8950-3a4bdb6ccf00.png)
![image](https://user-images.githubusercontent.com/194400/40924543-634250ee-680f-11e8-9a77-a83269bf2439.png)

Streak is a great product for a very **_specific_ use case**.
It makes the assumption that people _already_ use Email
for managing their sales, and gives those people the tools
to "manage" their inbox collaboratively.

On the basis that the Streak UI is email-based (not "Kanban")
we are not researching it further.
However, we feel that for email-based business the immediately familiar UX
is good! And the _limited_ feature set could actually be a _benefit_.


https://streak.readme.io/v1/reference#create-a-field
![image](https://user-images.githubusercontent.com/194400/40926368-f4572b00-6813-11e8-9fe1-a0af917dee8e.png)

The pricing _feels_ "steep" for what the product _does_,
but sometimes "less is more" is worth _paying_ for!
https://www.streak.com/pricing
![streak-pricing](https://user-images.githubusercontent.com/194400/40926512-475d1544-6814-11e8-815b-f5e97974c22d.png)

Also worth checking out are the "Zapier" integrations:
https://zapier.com/apps/streak/integrations

## SugarCRM

Slow, "clunky" and grosely over-priced!

The _latest_ SugarCRM UI looks "dated" when compared to virtually _any_ other
provider. watch _any_ of their videos:
https://www.youtube.com/user/DiscoverSugarCRM/videos
e.g: the "Sugar Spring '18 version 8": https://youtu.be/aMjAzFZJD0g

Their _cheapest_ "plan" is the "Sugar Professional" which is **$40/month**
_however_ the _minimum_ is 10 "user licenses" and a **1 year contract**!
https://www.sugarcrm.com/product/pricing-editions
![sugarcrm-pricing-overview](https://user-images.githubusercontent.com/194400/40916514-e2400674-67f7-11e8-8822-aded603b865a.png)
![sugarcrm-pricing-minimum](https://user-images.githubusercontent.com/194400/40916562-136daf8a-67f8-11e8-8107-b3654adc0fe3.png)

This might be "fine" for businesses who have 10 employees that will _use_
the product from "day 1" but that immediately excludes 96% potential clients
according to the most recent data from both OECD and Gov.uk.
https://data.oecd.org/entrepreneur/enterprises-by-business-size.htm
http://researchbriefings.files.parliament.uk/documents/SN06152/SN06152.pdf
![96-percent-biz-fewer-than-10-employees](https://user-images.githubusercontent.com/194400/40917165-2a76a68a-67fa-11e8-8022-66a1e6937c1d.png)

Read: https://community.sugarcrm.com/thread/20471

## Background Reading + Useful Links

+ Basic intro: https://en.wikipedia.org/wiki/Customer_relationship_management
+ Comparison of CRM Systmes:
https://en.wikipedia.org/wiki/Comparison_of_CRM_systems
(_incomplete but has the most popular..._)
+ Sales force management system (_general info_):
https://en.wikipedia.org/wiki/Sales_force_management_system

### Lists

+ 10 Best CRM Services for Small Businesses:
https://everhour.com/blog/best-crm-software
+ List of 10 Best CRM Software Tools:
https://financesonline.com/list-10-best-crm-software-tools/
