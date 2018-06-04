## Considerations

+ Is the **UI/UX _fixed_** or ***customisable***?
(_can we change it if we don't like it or find the workflow slow/frustrating_?)
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

## Requirements

We have distilled the CRM requirements into the following:

+ **Lead management** (_**Kanban**-style board_) to visualise active leads
and easily "**_drag-and-drop_**" from one stage/phase to the next.
+ **API** so leads can be piped in direct without having to email the system.
+ **Email Marketing/Automation** integrated or potentially contactable
via a live API to Email service (_e.g: Mail Chimp_) which we already use
+ **Data privacy** guarantees ensure data privacy, security & reliability
(_encryption, backup, access controls & redundancy_) to avoid company liability.
+ ***GDPR Compliance***: easily see who has given consent for us to store/retain
their data. If person has _not_ given consent
(_e.g existing users or "cold" prospects_)
re-request it by sending them a tracked email
if they fail to open or click the link to confirm,
_automatically_ "_expire_" the data
(`delete` _after a pre-defined period_).

(_we hate non live integrations though when you have to update / refresh
  the mailing list before sending out every time.
  I'd like to just choose a grouping within a list and send knowing that
  all new subscribers and relevant people are being mailed including
  the automatic unsubscribes_)

API requirements:
+ `POST` requests for an enquiry with basic info:
  + contact info (_Name, Location, Phone Number, Email_)
  + product name
  + product link
  + dates (from / to)
  + estimated total budget/cost)
  + contact_id
  + **Viewed products** so customer service can see what else
  the person has looked at while browsing the site.
+ `GET` requests for individual user's record.
  + **User profile** (name, contact details)
  + **Enquiry details** (date, yacht name, yacht URL)
  + **Enquiry status** (latest updated date, status. e.g: Awaiting first contact,
    In progress, Closed - at the simplest level, but this could
    be made much more detailed and interesting)
  + **Saved data**

Nice-to-haves:
+ Logged in users' searches `POST`ed to the CRM
+ Ability to analyse data across enquiries
  + If in the CRM we have to send things like partial enquiries or
  saved products as just 'notes' in the contact because
  the CRM doesn't support custom objects for example,
  it'll make it difficult for any real data analysis to be built in
+ **Partial enquiries** (i.e. someone creates their account but doesn't
press 'send' on the enquiry after they've seen the summary _or_ someone
is logged in, presses 'request availability' on the individual yacht page,
but doesn't press send after they've seen the summary)

A custom CRM would definitely be the best thing for them from a data
analysis perspective, but the expectation is that an 'off-the-shelf'
option will also be proposed.
