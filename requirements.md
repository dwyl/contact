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

### Telephone-based Sales

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
