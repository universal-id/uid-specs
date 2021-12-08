# Data taxonomy

When it comes to data collection by apps and services, there are 5 general dimension we can look at to analyze and understand the resulting risks to the users' privacy and security.

Dimensions:

- 📀 Data storage location - This is the location where data is stored ranging from on-device to online or offline on the web service.
- 🖇 Data correlation method - This specifies how each piece of data can be linked or correlated with a specific user
- 📑 Data usage domain - This specifies the reason a piece of data is used or collected. Reasons include analytics, app functionality, personalization, advertising, etc.
- 📚 Data types - This is the breakdown of data types including categories such as contact info, identifiers, location, payment info, diagnostics, etc.
- 🗑 Data retention policy - This specifies the length of time each piece of data can be collected and stored, and overlaps with data storage location.

## 📀 Data storage location

User data can be stored in multiple tiers including on the user's device or one of the app providers servers including ones that are online or offline.

- 📲 On device - This is storage on the user's devices, and is excluded from most app privacy profiles, given the lower average risk and aggregate harm of data breach.
- ☁️ On web service - This is storage by the app provider on the web service's online systems, which can potentially be hacked and access by attackers.
- 🗄 Offline service - this is storage by the app provider on offline systems, that cannot be accessed synchronously through cyber breaches, and are otherwise accessible through asynchronous human-based processes.

## 🖇 Data correlation type

Any piece of data is often used in the context of correlation with a specific context such as a person, organization, session, place, thing, etc. As a result the correlation methods used for each piece of data reveals a lot about how it is used. In case of privacy, we want to know if that data is correlated to a specific person or not, and if it is particularly correlated with other external data about you in real time to effectively track you.

- 🙅 Not linked to you
- 🙍 Linked to you
- 👁 Used to track you

App providers have specific purposes for each piece of data. At its most harmless, they use data directly for the app's functionality, or personalization. Other categories of usage purpose is analytics for improving the product and/or extracting insights for the purpose of product development. It could also be used by app provider or third party for advertising, or for other purposes.

## 📑 Data usage domain

- 👥 Third party advertising or marketing
- 👤 First party advertising or marketing
- 🔬 Analytics
- 👒 Personalization
- 🎰 Functionality
- ? Other purposes

## 📚 Data types

- ℹ️ Contact information
- 👁 Sensitive information
- 📍 Location
- 🆔 Identifiers
- 🩺 Diagnostics
- 💳 Payments
- ❤️ Health and fitness
- 📇 Contacts
- 📸 User content
- 🕘 Browsing history
- 🔎 Search history
- 🛍 Purchases
- 📶 Usage data
- 💬 Other data

## 🗑 Data retention policy

Data retention policy = Location + Time length

Location: same as above.

🕐 Time length:

- ⏳ In-memory only - length of session - ~1 hour maximum
- ☀️ 1 day maximum
- 7️⃣ 1 week maximum
- 🌕 1 month maximum
- 📆 6 month maximum
- 📅 1 year maximum
- ⏰ 4 years maximum
- 🕰 10 years maximum
- ♾ Indefinite

## Other platforms

### Apple App Store

Apple has detailed their [data privacy taxonomy and policies](https://developer.apple.com/app-store/app-privacy-details/) to be used by their app store developers. Specifically they require app developers to specify all the data pieces they use within the context of their taxonomy.

They have defaulted and omitted a few of the dimensions we mention above, that seems to have simplified things a bit without significancy reducing the effect of their policies. Specifically, they only require reporting of data stored by the developer's service (online web-service) as it has the highest risk, and they do not mention, or allow users to specify or negotiate on data retention policies. The following dimensions are clearly featured:

- 🖇 Data correlation method
- 📑 Data usage domain
- 📚 Data types

You can for example compare the different app privacy specifications reported by the following apps:

- Facebook: https://apps.apple.com/us/app/facebook/id284882215
- Google Maps: https://apps.apple.com/us/app/google-maps/id585027354
- Apple Maps from list of Apple (1st party) apps: https://www.apple.com/privacy/labels/
