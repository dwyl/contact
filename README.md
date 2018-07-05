<!--
# `Cream`

The Open Source CRM System of your _Dreams_!
-->
## What is CRM?

![crm-intro-image](https://user-images.githubusercontent.com/194400/41077294-c1b837ec-6a0d-11e8-98c8-459d061d1cda.png)


Customer Relationship Management (CRM) Systems are the place
organisations store contact data, communication history and
"status" or "sales progression" for current and potential customers.

All CRMs store personal data _by definition_
and in general the data is stored in a _relational_ database;
that part is _solved_<sup>1</sup>.

The key differences from one CRM to the next are:
+ **User Interface**: ease/speed of use
+ **API**: how to programatically insert/retrieve/update data use the customer
data in other applications or present it in "dashboards"
+ **Workflow**: defining the internal (business) "process" for processing data.
+ **Integrations** with other business/IT systems
+ **Communication Channels**: e.g: email, Phone, SMS, Twitter, AdWords, Chat Bots, etc.

In our experience, _many_ companies large and small that have a CRM
use it ineffectively because of inadequate business process definition,
insufficient training given to people using the system and
sheer volume of "features" nobody sees the need for.

This is the "***Dark side of CRM***" no SaaS Vendor will talk about.
See: https://www.emeraldinsight.com/doi/abs/10.1108/07363761311290812

To achieve "success" with CRM there are a few steps that should be taken:
+ ***Define*** the ***problem*** you are solving _before_
beginning the search for a "solution". e.g:
  + Is the problem poor _internal_ communication (_within your team_)
  or _external_ communication with existing/potential customers?
  + Is data stored in several places e.g: spreadsheets, email,
  "dropbox" and a "wiki"?
  + Is communication with prospects _structured_ or ad hoc/haphazard?
  + What are the key metrics in your business/organisation and do
  your _existing_ business systems streamline tracking/visualising them?
+ **Document _existing_ business process** and identify the inefficiency;
quantify the number of inputs, steps to perform a process, interactions with data and outcomes.
  + The more "friction" in the process,
  the less likely people will follow it.
and corresponding "workflow"  (_if possible_)
  + **All _duplicate_ manual data entry** should **_eliminated_**;
otherwise the entire system comes crumbling down!
+ **Clarify** who "_owns_" the data and relationships.
Is the customer in _control_ (_of their personal data_),
or does the data "belong" to "the business"?<sup>2</sup>
  + Who "owns" the relationship? e.g: is it an "account manager"?
  + How easy is it for the prospect/customer to view all the data
  you have for them, can they edit/update or `delete` it?
+ **List** your preferred communication "channels" and the _reason(s)_
why they are the best for your business objective(s)
or organisational mission. e.g: high value sales are typically
done through in-person meetings whereas mass-communication is done
through email.


<br />
<sup>1</sup><small>
The subject of _how_ data is stored is technically,
still a topic of "debate". While _most_ CRMs use RDBMs,
a few use "document storage" such as MongoDB
in order to store "semi-structured" free-text data.
I favour the _structured_ approach
combined with "append-only log" as a way of building
a CRM because it lends itself to better guarantees
and arguably a simpler message-based architecture which will
allow for more innovation; more on that later!
</small>

<sup>2</sup>
<small>
With GDPR the EU has enacted a law to help put the _customer_
in control of their personal data; we think this is _excellent_!
What it means for any company that captures and _stores_ customer
is they need to _re-think_ how data is acquired,
and is appropriate consent sought?
Exactly what data they store and why it's needed,
how it's protected while it's in your "care" and what the process
is for _deleting_ it when the customer no longer wants to have
a "relationship" with you.

</small>

## Why?

We need to store the data from our web enquiries
(_people who contact us to **work with** or **for** dwyl_)
in a database and have a clearly defined workflow for
managing/progressing the data.

At present we are using an "MVP" solution for this:
an HTML form that posts to a Google Spreadsheet.
This has worked "OK" for us,
and it's even one of our [most popular tutorials](https://github.com/dwyl/learn-to-send-email-via-google-script-html-no-server)
but we have come up against **3 issues**:

1. **Data stored** in a **spreadsheets** is ***not*** "**secure**" even if it's
**restricted** to a handful of **_trusted_ people**,
it's still a ton of personal data stored in
`plaintext` without fine-grained access controls or restrictions on exporting.
> Note: we are big proponents of Hyper Transparency in dwyl;
we believe that everyone in the team should be able to see our "pipeline".
But this is not really "compatible" with data protection (GDPR)
because if for _any_ reason someone on our team were to
leave their device unattended in a public place (e.g. coffee shop or co-working space)
a "bad person" could "steal" our entire customer "database"
in seconds with only a few clicks; Google spreadsheets makes it easy to "share"
the spreadsheet with a random G-Account
or even make the sheet `public` without approval process.
This is a _massive_ risk we should not (_and don't need to_) take
even if the probability is _low_ the impact is super high and we should just avoid it!

2. A **spreadsheet** "**workflow**" is _not_ effective/optimised at _all_,
the communication history (_email, phone calls, SMS, instant messages_)
is not stored in the spreadsheet
which means that only the one person who engaged in the conversation
is aware of the full history
thus that person becomes a "bottleneck" in the system
or worse the "single point of failure". <br />
  **a**. **Activity** of people editing/updating the spreadsheet
  is not _automatically_ tracked.
  If someone sees an enquiry come in and follows up
  (_by email or phone_) and the _forgets_ to update
  the relevant row/cell there can be duplicated effort. <br />
  **b**. **Business Process _Automation_** is non-existent;
  it's ***all manual***.
  For example scheduling a proposed time
  for a call/meeting is all manual. <br />
  **c**. **Contacts** become "stale" over time as people change jobs,
  our spreadsheet does not reflect this without manual update.
  **d** **Date Prioritisation** is very _manual_ in the spreadsheet
  and in general _ineffective_. We don't _capture_
  the urgency of the inquiry/request,
  so we have "_missed out_" on interesting opportunities,
  which is frustrating!<br />

3. Spam! last, but not least, spam. In the last month we've had over 50 SPAM requests.
(_in fact this is a catalyst for us wanting to re-think our enquiry process
  in recent weeks we've had an increasing volume of Spam submissions
  through our "contact us" html form which pollute our Google spreadsheet
  and clog up our inbox! and because the "origin" of the email is our script,
  Gmail does not know how to intelligently filter the messages as junk!_)
> **Note**: we consider unsolicited messages from "recruiters"
wanting to sell us "talent" to be "Spam" and we want to eliminate it.


We need to "fix" this!
It's costing us time/money every day
and risking personal data loss _unnecessarily_.


## What?

We need to be _focussed_
on "***workflow automation***"
to be more effective
at handling our enquiries.

### _Inbound_ Enquiries

We receive several types of inbound enquiries, the list of enquiry "sources"
in (descending) order of _frequency_ is:
1. Web-to-Lead (_via "contact-us" web form_)
2. Telephone (_via having our mobile phone number `public` on the website_!)
3. Email ("_direct-to-inbox_") via word of mouth.
4. Twitter
5. Web-based Instant Chat - currently "Gitter", considering other options.


#### 1. Web-to-Lead "Contact-Us" Form

This is where we will be spending the _bulk_ of our time for the next few weeks.


#### 2. Telephone

Our plan is to use a Twilio to handle our both our inbound and outbound voice
calls with a telephone number people can call when they need our help.

#### 3. Email

At present we receive email directly to our Gmail inbox.
This "works" for now so we don't _need_ to change it.
But as soon as we have our "web-to-lead" process nailed,
we will be tackling "email-to-lead" from _scratch_.

#### 4. Twitter

At present we don't have any "_process_" or "_workflow_" for Twitter.
We need to have alerts for both mentions and specific topics/hashtags.
TBD once we have "Web-to-Lead" working.


#### 5. Web-based Instant Messaging ("Chat")

> We intend to solve this by _building_ something.
But we feel that it needs to "feed" into our "Web-to-Lead" workflow
if none of us are online to help the person wanting to chat.
So we will return to this once we have the first few elements working.



### Outbound Communications ?

We are in the _fortunate_ position that we have not _needed_
to do any "outbound" marketing to get work.
All of our clients have come to us
through word of mouth or inquiry form.

_However_, we are planning to begin publishing our "blog" posts
and weekly newsletter once we are focussing on our ***SaaS Product***.

We do not consider this to be "marketing",
rather it's "sharing updates" with our community.




## Who?

For the foreseeable future, our "internal" team of people who _already_
handle the enquiries will be using the "CRM".

## How?

Our goal is to find (_or build_) a CRM that _any_ business can use
to _safely/securely_ store the details of the prospective customers.

+ [x] Security by `default` not as "after though".
  + [x] App does not _start_ if API keys are not present.
+ [x] Easy to use for quick/focussed interactions.


In addition to having encryption of all sensitive/personal data


## Requirements / Roadmap

### Mobile UI for On-the-go Access

+ Mobile-first for on-the-go at-your-fingertips access and real-time updates.
+ Drag-and-drop interface on desktop
+ Collaborative
+ Access Controls restrict access to data for security & privacy.
+ Anonymised data

### Access Controls

By default each "instance" should have

+ Super Admin
+ Admin
+ Regular "User"
+ Read-only access (_for audit and training purposes_)

### Data Ingress

For "MVP++" we will be using a Web (HTML) form to capture data
and store it in a Database.

### Data Export

+ [] Easy data export (SQL Dump) of complete data to _authorised_ person.

> Note" we will require a "GDPR form" to be completed by the data controller
  and **evidence** that the person is registered
  with the relevant data protection authority
  before we run the `export` script for their data.


## One-Click Start (Zero "Setup")

Use "deploy to Heroku" button?
Or "Terraform" to AWS Lambda...?


## Keyboard Shortcuts in UI?

While we need to make the CRM as user-friendly and intuitive as possible
for _first-time_ and _casual_ users, it's the "_power users_" who will
be interacting with the system _most_ and need the _fastest_ UX day-to-day.



## Background Reading & Research

### General

+ https://en.wikipedia.org/wiki/Customer_relationship_management

### Commercial CRM Systems

See:
[`market-research.md`](https://github.com/nelsonic/contact/blob/master/market-research.md)

### Open Source CRM Systems

We have tried:
+ https://suitecrm.com
+ https://civicrm.org

Both are PHP-MySQL and both get _painfully_ slow with any volume of data ...

<!--
## Name?

https://english.stackexchange.com/questions/41325/origin-of-cream-of-the-crop

Cream will use our "fields" module to manage all custom fields.
CreamFields ... ;-)  https://youtu.be/SRPGgjk7lKk
-->
