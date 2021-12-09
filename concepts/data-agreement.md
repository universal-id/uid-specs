# ✍ Data agreement

In our data taxonomy specifications, as well as our data collection agreement specifications (and privacy policy), we attempted to define a set of dimensions and criteria to help us describe data privacy in an objective way. However when it comes to agreements, things are subjective, and under the jurisdiction of various governments at multiple levels such as local, state, national and international. As such, the details of each legal agreement, including terms and policies, should be defined within its corresponding jurisdiction. So as much as we attempt to be objective about our data taxonomy definitions and agreement clauses, there should be room left for jurisdictional redefinitions by independent expert institutions. As such, we plan to go with the following principles:

1. Temporary pending transfer to expert institution - The data taxonomy and agreement clauses defined by these specs are for reference, and will be temporarily used, until another non-profit organization with expertise in privacy can take over the process of defining and redefining them. Until such time our definitions can be used for digital agreements.
2. Leave room for competing taxonomy definitions - There may be multiple competing interpretations of data privacy taxonomy by multiple institutions specializing in data privacy. As such, the Universal Identity protocol should allow users and/or apps to default to their own preference.
3. Leaving room for variations per jurisdiction - The experience of each user in a given jurisdiction may be different from another, as they may see different default privacy agreement clauses, reflecting the legal data definitions within that jurisdiction, as well as reflecting the privacy rules of that jurisdiction. As such, the mentioned future institutions specializing in privacy, may maintain varying copies of definitions per jurisdiction.

## Privacy exception clauses

Default exception clauses for most cases:

* No data used for third party advertising
* No high risk data collection - location data, payment data, sensitive data, contacts data
* No tracking

Categories of apps where exceptions make sense:

* Finance, banking and money apps - AML (Anti Money Laundering) and KYC (Know Your Customer)
* Mapping and logistics apps - Location data is likely collected, although it may be reasonable to ask app to not link this data to the person
* Contacts apps - Contacts data can be collected and stored if it will be searched or organized through the app
* Ad supported apps - Free apps that are clearly advertising driven - Example: free movies and videos apps, social media apps - Preventing tracking still makes sense, but using basic data for ad purposes, such as Zip code, or gender has low negative impact on privacy. It makes sense to ask for preventing contact information and device IDs being used for serving ads.
* Monthly subscription apps, retail apps - Any service requiring recurring payments may be OK to keep payment information for the purposes of app functionality.

Exception clauses that make sense in almost all contexts:

* No tracking - Apps may have to personalize experiences, and even keep some data linked to your account, but it is always reasonable to ask them not to track you by combining your data, with data from external third parties.
* No sensitive data - Sensitive information about a person's ethnicity, minority group membership, etc. that can be used to hurt that person should be an exception in almost all cases.

Some unusual agreement exception clauses for highly private users:

* No collection - Only in-memory access to data that is forgotten after each transaction
* On-device only - No off-device data collection
* No linking - No collection data linked to user
