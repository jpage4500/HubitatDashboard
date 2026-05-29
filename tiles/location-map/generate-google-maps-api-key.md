# Generate Google Maps API Key

This guide shows how to get a Google Maps API Key in 2026

#### Step 1: Set Up a Google Cloud Project

Everything in Google Cloud revolves around projects. You need to create one to house your Maps integration.



1. Navigate to the Google Cloud Console ([console.cloud.google.com](https://console.cloud.google.com)) and sign in.
2. Click the Project Selector dropdown menu in the top navigation bar.
3. Click New Project in the top-right corner of the pop-up window.
4. Enter a Project Name (e.g., "HD+ Maps") and click Create.
5. Wait a few seconds for the project to be created, then ensure it is selected in the top navigation bar.

#### Step 2: Enable Billing

Google Maps Platform operates on a pay-as-you-go pricing model and requires a valid billing account to function. However, Google provides a recurring $200 monthly credit that covers most basic to moderate usage entirely for free.

1. Open the left-hand navigation menu (the hamburger icon) and select Billing.
2. Click Link a Billing Account if you have an existing one, or Manage Billing Accounts to set up a new one.
3. Follow the on-screen prompts to enter your payment information. You will not be charged unless your traffic exceeds the generous free monthly tier.

#### Step 3: Enable the Required APIs

By default, APIs are turned off. You must explicitly tell your project which APIs it is allowed to use.

1. Open the left-hand navigation menu and navigate to **APIs & Services > Library**.
2. In the search bar, type **Maps JavaScript API**.
3. Click on the result and click the blue **Enable** button.
4. Return to the API Library and search for **Maps Static API**.
5. Click on the result and hit **Enable**.

#### Step 4: Generate Your API Key

Now that the APIs are turned on, you can generate the actual key used to access them.

1. Navigate to **APIs & Services > Credentials** using the left-hand menu.
2. Click the + **Create Credentials** button at the top of the page.
3. Select **API Key** from the dropdown menu.
4. A dialog box will appear displaying your new API key. Copy this string of text and keep it handy.

#### Step 5: Set API Quotas to Prevent Unexpected Billing

While restricting your key to specific websites prevents unauthorized people from stealing it, setting a quota is the best way to ensure your own website's traffic doesn't accidentally exceed Google's $200 monthly free tier. By capping the maximum number of times the API can be called per day, you guarantee you won't be charged.

1. Open the left-hand navigation menu and navigate to APIs & Services > **Enabled APIs & services**.
2. Scroll down your list of enabled APIs and click on **Maps JavaScript API**.
3. Select the Quotas & System Limits tab near the top of the page.
4. Scroll down to the Map loads section. You will see a metric for **Map loads per day**.
5. Click the Edit icon (the pencil) next to the daily limit.
6. Enter your desired maximum daily limit. _(Note: The $200 free monthly credit covers exactly 28,500 Maps JavaScript API loads per month. To stay completely free, divide this by 31 days and set your daily quota to roughly **900**)._
7. Click Save or Submit.
8. Return to the Enabled APIs & services page, click on **Maps Static API**, and repeat this process. _(Note: The static maps are cheaper, and the free tier covers 100,000 static map loads per month, which is about **3,200 per day**)._

> Extra Protection: For added peace of mind, you can also navigate to Billing > Budgets & alerts in the Google Cloud Console. Here, you can set a budget of $0.00 or $1.00 and have Google email you automatically if your usage ever starts approaching a threshold where you would be charged.
