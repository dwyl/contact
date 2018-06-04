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

2. **API** availability (_preferablly "streaming"_) so leads can be piped
in directly without having to email or perform manual data entry.

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

>_We hate non-realtime systems that require us to manually update / refresh
  the "mailing list" before sending out every time.
  I'd like to just choose a grouping within a list and send knowing that
  all new subscribers and relevant people are being mailed including
  the automatic unsubscribes_.

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
