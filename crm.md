# Charter Index CRM

![crm-data-flow](https://user-images.githubusercontent.com/194400/41005719-8f83c888-6916-11e8-960b-8ee173f2ffcc.png)

Capturing, storing and processing **customer data**
is the _heart_ of Charter Index's business.

## Intro / Overview

Selecting a CRM system is decision that should be _carefully considered_.
The CRM is a business system that is "core" to sales/operations
and selecting a "full featured" product can be huge "asset" for the business.

If we need "telephone integration" and it's _not available_ in a "cheaper" CRM
provider, and then we end up having to run two separate systems one for
contact/account management and the other for making/receiving/recording calls,
it can rapidly add up to a lot of wasted time/effort which negates the point
of spending less on the "cheaper" CRM.

The best way to think of a CRM is as a "***business process automation***" tool,
not a "database" with a "drag-and-drop" UI. <br />
see: https://hbr.org/2016/10/customer-relationship-automation-is-the-new-crm

Most of the CRM providers include similar basic features,
however the way we _should_ look at them is by asking the question(s): <br />
+ "Which CRM will make my business run most effectively"?
+ "Which CRM will give the sales/support people in our team most productive?"

If the CRM wastes minutes of key team member(s) time each day this can
add up to several $$'s/day of lost time
and frustration through duplicated effort.
The _reason_ certain CRM providers _charge_ more for their product/SaaS,
is because they offer an _objectively better product_ that fits the needs
of a specific market segment.

### Telephone-based Sales ?

The web-based enquiry form is just an _initial_ way for the prospective
customer to contact us. From there most of our business is conducted by phone.

To date the phone calls are _outbound_ (_from the CEO's mobile_) to the
prospective client and then a follow-up email is sent.

If the CRM system does not have telephony integration this _manual_
(_unscalable/inefficient_) process will continue without any automation.

If the business is to _expand_ we need a clearly defined set of sales "channels"
with _one_ telephone number for inbound/outbound calls, sms and email
where the _business_ is in control of the "experience", "branding"
and "data privacy".

https://www.agilecrm.com/blog/10-advantages-integrating-telephony-crm


## Considerations

+ Is the **UI/UX _fixed_** or ***customisable***?
(_can we change it if we don't like it or find the workflow sfrustrating_?)
+ Does the system detect the "presence" of the person updating
the contact/details to avoid two people attempting to edit simultaneously?
+ Is the **UI/API updated** in **_real-time_**
or does it require "manual refresh"?
+ Can **custom fields** easily be added via UI/API and can they be used
in the workflow without lots of extra "clicks" (_for each record_)? e.g:
  + **Organise** the Kanban Board by "**departure date**"
to _prioritise_ clients who are need responses the _soonest_. <br />
  + Or **Sort** the Overview by "**budget**" so the highest value prospect
receives faster/more attention/care. <br />
  + Location-based view on Mobile device to ensure that contacts/leads
are ordered for a given geography if the _field-based sales consultant_
is near to the prospect(s) _current_ location.
+ **Integration** with **Customer Support System**? is the CRM purely focussed
on getting sales or does it manage the full "***lifecycle***" including
reviews/feedback and ***complaints***?
+ **Data protection** - where is the data stored? EU datacenter for EU-based
customers/contacts or _everything_ in a US-based datacenter?
+ Are **Transaction Processed/Logged** in the system so customer value
is _visible_ not just "status". This is _essential_ for repeat sales.

## Requirements

We have distilled the CRM requirements into the following:

1. **Lead management** (_**Kanban**-style board_) to visualise active leads
and easily "**_drag-and-drop_**" from one stage/phase to the next.

2. **API** availability so leads can be piped
in directly without having to email or perform manual data entry.
The API _must_ have "custom fields" so we can store additional data.
Ideally the API should allow for "**streaming**" so that data is updated
in "***real-time***".
>_We hate non-realtime systems that require us to manually update / refresh
  the "mailing list" before sending out every time.
  I'd like to just choose a grouping within a list and send knowing that
  all new subscribers and relevant people are being mailed including
  the automatic unsubscribes_.

3. **Email Marketing/Automation** integrated or potentially contactable
via a live API to Email service (_e.g: Mail Chimp_) which we already use

4. **Data privacy** guarantees ensure data privacy, security & reliability
(_encryption, backup, access controls & redundancy_) to avoid company liability.

5. ***GDPR Compliance***: easily see who has given consent for us to store/retain
their data. If person has _not_ given consent
(_e.g existing users or "cold" prospects_)
re-request it by sending them a tracked email
if they fail to open or click the link to confirm,
_automatically_ "_expire_" the data
(`delete` _after a pre-defined period_).

6. **Telephony integration** to allow telephone calls to be made/received
from the _same_ platform without people having to waste time "keying" in
or copy-pasting telephone numbers into a mobile/device. This will allow much
better coordination in the team and help grow a dedicated sales/support team
beyond the founders making the calls.


## API Requirements

+ `POST` requests to create/update an enquiry record:
  + contact info (_Name, Location, Phone Number, Email_)
  + product name
  + product link
  + dates (from / to)
  + estimated total budget/cost)
  + contact_id
  + **Viewed products** so customer service can see what else
  the person has looked at while browsing the site.
+ `GET` requests for:
  + **User profile** (name, contact details, email/phone verified)
  + **Enquiry details** (date, product name, product URL)
  + **Enquiry status** (latest updated date, status. e.g: Awaiting first contact,
    In progress, Closed - at the simplest level, but this could
    be made much more detailed and interesting)

### "Nice-to-have"

+ Logged in users' searches automatically `POST`ed (_appended_) to the CRM
+ Ability to analyse data across enquiries (_multiple sessions + devices_)
+ If in the CRM we have to send things like partial enquiries or
  saved products as just 'notes' in the contact because
  the CRM doesn't support custom objects for example,
  it'll make it difficult for any real data analysis to be built in
+ **Partial enquiries** e.g: someone starts a search or enquiry but doesn't
complete it or the person is logged in, presses 'request availability'
on the individual product page, but then never completes the form.

# Market Research

## Comparison Table

<!-- formatting via: http://markdowntable.com/ -->

| Product/Service Name | Open/Closed Source | Cost | Pricing Model | API | UX | Keyboard Shortcuts | Automation | Kanban / Drag+Drop | Custom Fields/Data | Custom Workflow |
| ------------- |:-------------:| ----- | --- |:--- | --- | --- | --- | --- | --- | --- |
| [Base CRM](https://getbase.com) | Closed | [$45/user/month](https://getbase.com/pricing) | 3 Tiers: Starter: $45/u/m, "Professional": $95/u/m & "Enterprise": $145/u/m | REST https://developers.getbase.com | "Traditional" | [Yes](https://support.getbase.com/hc/en-us/articles/204508995-Can-I-use-Keyboard-Shortcuts) | Yes | No | [Yes](https://developers.getbase.com/docs/rest/articles/firehose/custom_fields) | No |
| [Freshsales CRM](https://www.freshworks.com/freshsales-crm) | Closed | [$18/user/month](https://www.freshworks.com/freshsales-crm)| 4 Tiers: Blossom: $9/u/m, Garden: $18/u/m, "Estate": $36/u/m & "Forrest": $57/u/m | REST https://www.freshsales.io/api | "Kanban" | No | Yes | Yes | [Yes](https://developers.getbase.com/docs/rest/articles/firehose/custom_fields) | No |
| [Hubspot.com](https://www.hubspot.com) | Closed | [$42/user/month](https://www.hubspot.com/pricing/sales) for _first_ user | 3 Tiers: "Free", Starter: $42 for **1 user** & "Professional": $330 for 5 users = **$66/u/m** | REST https://developers.hubspot.com/ | Kanban | [**No**](https://community.hubspot.com/t5/HubSpot-Ideas/keyboard-shortcuts/idi-p/12244) | Yes | Yes | [Yes](https://api.insight.ly/v2.2/Help#!/Overview/Technical_Details) | Yes |
| [insightly.com](https://www.insightly.com) | Closed | [$49/user/month](https://www.insightly.com/pricing) | 3 Tiers: "Plus": $29/u/m, Professional: $49/user/month & "Enterprise": $99/u/m | REST https://api.insight.ly/v2.2/Help | Kanban/Outlook Inbox | [Yes](https://support.insight.ly/hc/en-us/articles/204248780-Keyboard-shortcuts) | Yes | Yes | Yes | Yes |
| [Pipedrive.com](https://www.pipedrive.com) | Closed | [$29/user/month](https://www.pipedrive.com/en-gb/plans) | 3 Tiers: Silver: 15/u/m, Gold: $29/u/m & "Platinum": $75/u/m | REST + Webhooks https://developers.pipedrive.com/docs/api/v1/ | Kanban Board | Yes | Yes | Yes | Yes | Yes |
| [Salesforce.com](https://www.salesforce.com) | Closed | [$25/user/month](https://www.salesforce.com/editions-pricing/platform) | Variable/Opaque from $25 to $300/u/m! | REST + Stream https://developer.salesforce.com/page/Salesforce_APIs | "Classic" ("Clunky") or "Lightning" (Drag-and-drop) | Yes | Yes | Yes | Yes | Yes |
| [Streak.com](https://www.streak.com) | Closed | $49/user/month | 3 Tiers: Free, Professional ($49/user/month) & "Enterprise" ($99/user/month) | REST https://streak.readme.io/ | Gmail Inbox | Yes | Yes | **No** | **No** | **No** |
| [SugarCRM.com](https://www.sugarcrm.com) | Closed | [$40/user/month](https://www.sugarcrm.com/product/pricing-editions) | 3 Tiers: Professional ($40/u/m),  "Enterprise" ($65/u/m) & "Ultimate" ($150/u/m) | REST http://support.sugarcrm.com/Documentation/?docVersion=8.0&docEdition=Pro | "Traditional CRM" (no kanban) | Yes | Yes | **No** | Yes | Yes |                                                                                        |





# Alphabetical List of CRM Systems

## Active Campaign

Active campaign is primarily focussed Email Marketing Automation,
however their CRM offers all the "standard" features you would expect
from a contact/sales system with a "Kanban" UI.
https://www.activecampaign.com/crm
![active-campaign-crm](https://user-images.githubusercontent.com/194400/41002123-c33f72fa-690a-11e8-8d0d-2f6cc2a7d644.png)

### Pricing

Active Campaign has _competitive_ pricing considering that they charge a "flat"
fee for **25 users**
however their pricing increases based on how many _contacts_ you have.
https://www.activecampaign.com/pricing
![active-campaign-pricing](https://user-images.githubusercontent.com/194400/41002011-764550dc-690a-11e8-8a3c-fb06dd4b74b8.png)

### API

https://www.activecampaign.com/api


It is _possible_ to add custom fields, but it appears that they are not _named_
rather a custom field is a numeric index!
https://community.activecampaign.com/t/where-i-can-find-the-id-of-a-custom-field-for-use-with-the-api/2515/2
https://community.activecampaign.com/t/how-to-update-a-custom-field-in-contact-with-api-v3/3603

We _can_ work with this, but I feel that there are _better_ options.
They don't have a Telephony integration; so if we need that this not an option.
But if we are only using email and SMS, the UI looks good.

<br /> <br />

## Agile CRM

Agile CRM is an "all-in-one" CRM system that has good (Kanban) UI,
REST API and integrations with 3rd party services such as Twilio
for making/receiving/recording sales calls and sending/receiving SMS.

![image](https://user-images.githubusercontent.com/194400/40984108-fdb60b74-68d8-11e8-88ae-bd695e6f4521.png)

Kanban ("_drag-and-drop_") User Interface:<br />
![agile-crm-kanban](https://user-images.githubusercontent.com/194400/40979133-cef0f198-68cc-11e8-875b-a2d602f02b14.png)

### Pricing

https://www.agilecrm.com/pricing
![agile-crm-pricing](https://user-images.githubusercontent.com/194400/40968815-586fbd88-68ae-11e8-9d0a-aa3fbb50917a.png)

$14.99/u/m (monthly) or $8.99/u/m payed 2-years up-front.
We suggest doing the "trial" and see how you get on with the UX
before a commitment.

### API

The AgileCRM API https://www.agilecrm.com/api is well documented
and has examples on GitHub (_including **custom fields**_):
https://github.com/agilecrm/rest-api#contact-json-example


### Twilio (Telephony & SMS) Integration

Twilio is a widly used telepone & SMS service provider
with great international coverage, an excellent API
and competitive pricing model. https://www.twilio.com/products

![twilio-product](https://user-images.githubusercontent.com/194400/40984319-7c0b8bc0-68d9-11e8-99bc-ee1512fd647a.png)

https://www.twilio.com/voice/pricing/gb
![twilio-pricing](https://user-images.githubusercontent.com/194400/40983725-265de84a-68d8-11e8-9579-5962a122aecb.png)

Read more: https://customers.twilio.com
![twilio-customer-stories](https://user-images.githubusercontent.com/194400/40984360-9d29ac2e-68d9-11e8-8f1c-0ba95eea744d.png)

### Automation

see: https://www.agilecrm.com/blog/4-keys-getting-inbox-control-automation

### Verdict

We _like_ the look of Agile CRM,
our _only_ reservation(s) on recommending it are:
+ their underlying technology is not great; https://builtwith.com/www.agilecrm.com
+ Their website has _many_ JavaScript errors, see: https://github.com/nelsonic/nelsonic.github.io/issues/475
which is indicative of "broken" UX.
+ Their node.js API has no tests: https://github.com/agilecrm/nodejs/blob/master/agilecrm/package.json#L7
so it could "break" without warning which will "break" our app/site.
+ No indication of how data is stored (_encryption?_)

<br />

## Base CRM

Base CRM is a general purpose CRM system with many advanced features.
https://getbase.com

![image](https://user-images.githubusercontent.com/194400/40935887-6e08c022-6831-11e8-9129-cb430bff5557.png)
The UI/UX is a "traditional" CRM and does **not _yet_ have** a "**Kanban**" UX,
therefore we have excluded it from further research/discussion.

Review of the pricing: https://getbase.com/pricing indicates that all of the
"advanced" features like "task automation" are
only available in the "Professional" tier and "Role-based Permissions"
are only in the "Enterprise"!
![base-crm-pricing](https://user-images.githubusercontent.com/194400/40936814-8032fdf0-6834-11e8-9ef1-27acf8565b32.png)

The API is good: https://developers.getbase.com
including a "firehose" which gives a "near real-time stream" of changes. <br />
![base-crm-firehose-api](https://user-images.githubusercontent.com/194400/40936946-f72dbc4c-6834-11e8-96d0-8826662d7812.png)

Overall Base CRM is _not_ a contender because the UI is "dated"
and the pricing is comparatively _high_.


## Close.io

Close.io is an "up-and-coming" CRM system that is "hot" in Silicon Valley:
https://close.io/product/
Having been through the "Y Combinator" startup accelerator in 2012,
Close.io has not wasted time building an impressive
feature-set and customer base.

![close.io-close-more-deals](https://user-images.githubusercontent.com/194400/40978357-55f08c64-68cb-11e8-9a1c-c02edc4aeafb.png)

### UI/UX

The UI is _not_ "Kanban", rather it's an "inbox" and "timeline" paradigm
and their focus is speed of interaction.

![close-io-ui-inbox](https://user-images.githubusercontent.com/194400/40987764-527ce990-68e1-11e8-895f-89f51264a2b4.png)


https://close.io/pricing
![close-io-pricing](https://user-images.githubusercontent.com/194400/40978219-eeed452a-68ca-11e8-93cc-a5bff816be20.png)

This pricing can seem "steep" on the surface, but thier workflow automation
and "single view" UI is worth considering.
Watch their "overview" video: https://close.io


### API

https://developer.close.io
http://blog.close.io/the-tech-stack-behind-close-io-sales-communication

<br />

## Freshsales CRM

General purpose CRM system with all the features you would expect.
Includes built-in phone, email and activity capture.
https://www.freshworks.com/freshsales-crm <br />
Full-list of features: https://www.freshworks.com/freshsales-crm/features/

![image](https://user-images.githubusercontent.com/194400/40937789-ad399446-6837-11e8-97a5-96d917d314d8.png)

Has a "Kanban" style drag-and-drop UI: <br />
![freshsales-kanban-ui](https://user-images.githubusercontent.com/194400/40937600-0cbbf54a-6837-11e8-8e39-23509401797e.png)

Pricing: https://www.freshworks.com/freshsales-crm/pricing/
![image](https://user-images.githubusercontent.com/194400/40938119-c82dd126-6838-11e8-8a9a-f6c0160eb405.png)

API: https://www.freshsales.io/api
![freshsales-api-custom-fields](https://user-images.githubusercontent.com/194400/40938884-093127f2-683b-11e8-8f93-4acb958b9321.png)

No "real-time" API, but if that is not a "must have"
then this could be a good option.

+ Review: https://www.capterra.com/p/156019/Freshsales


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


### Satisfies Requirements?

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
for multiple currencies is likely a ***deal breaker***.


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

<br />

## Nimble

Nimble is a "social CRM" that sources data from several _other_ platforms
(_social networks, business communication apps & email_) to
create a profile of the target customer allowing
sales people to have _far_ more insight into prospects
without needing to waste time googling before calling. https://www.nimble.com
![nimble-crm-](https://user-images.githubusercontent.com/194400/41001105-e3dfd976-6907-11e8-8387-5f04389453e0.png)

![image](https://user-images.githubusercontent.com/194400/41001068-ce5c1d8a-6907-11e8-8d60-735170578e24.png)

Good overview from the CEO: https://vimeo.com/252438241
![nimble-crm-demo](https://user-images.githubusercontent.com/194400/41001213-44d74840-6908-11e8-8612-2449bcd28e8c.png)

The value proposition for Nimble CRM is _strong_ for a business where
knowing about the prospect is essential to making the sale
or building the relationship.
However _all_ of our "leads" are "inbound",
i.e. people fill in our "inquiry form" and give us _most_ of the details
we need to make our assessment on their needs.
We _always_ end up Googling the person/company to see what comes up.

### Pricing

Their pricing is competitive https://www.nimble.com/pricing
![image](https://user-images.githubusercontent.com/194400/41003791-9db719b6-690f-11e8-89b7-23e9afcd5965.png)

If our objective is to be "social focussed", this is _easily_ the best choice.
But if we aren't reliant on "social" data, there are better options.

### API

The API looks "OK": https://nimble.readthedocs.io
Not amazingly documented, but _adequate_.

### Telephony Integration?

While Nimble does _not_ explicitly have telephony support
(_so there is no "dialer" built-in to the system_)
there is a _basic_ integartion with
call2CRM https://www.nimble.com/marketplace/call2crm
which allows you to install an app on your phone.
However this _appears_ to only be available in the USA.

<br />

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

### Integrations?

At present Pipedrive does not have an integration with any telephony providers
see: https://www.pipedrive.com/en-gb/features/integrations

If the plan is to make/receive telephone calls _separately_ from the CRM,
this is not an issue, however we _strongly_ recommend having the two systems
tightly integrated to avoid wasting time/effort especially with
"high value" clients.

<br />

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
+ Automation Is the New CRM:
https://hbr.org/2016/10/customer-relationship-automation-is-the-new-crm
(_open it in "incognito" window to avoid using up HBR article "allowance"_)

### Lists

+ 10 Best CRM Services for Small Businesses:
https://everhour.com/blog/best-crm-software
+ List of 10 Best CRM Software Tools:
https://financesonline.com/list-10-best-crm-software-tools/
+ "Long List" of available CRM systems:
https://www.capterra.com/customer-relationship-management-software/
