# Okta + Netlify Authentication

This is an example of using Okta's Login Widget to provide access control for a Netlify site.

Try it out on your own account via this link:

<!-- Markdown snippet -->
[![Deploy to Netlify](https://www.netlify.com/img/deploy/button.svg)](https://app.netlify.com/start/deploy?repository=https://github.com/netlify/example-gated-content-with-okta)

You must make sure to deploy the site to an account with the JWT based visitor access control enabled.

## Setting Up

Make sure you have an Okta account and a URL for that account.

Then create a new Application inside Okta. Choose Single Page application.

Create a new API Token and keep it handy.

Then click the deploy button above. Once you've authenticated with GitHub, you will be asked to fill in the following variables:

* **OKTA_BASE_URL** this is the URL of your Okta account, ie: `https://dev-679417.oktapreview.com`
* **OKTA_API_TOKEN** this is the API token created above
* **OKTA_CLIENT_ID** the client id for the Okta application created above
* **JWT_SECRET** either the JWT_SECRET set globally for your Netlify team, or a long random token

Once the site has been created, go to site settings, and transfer the site to a team with JWT based visitor access control enabled. If you don't have a global JWT secret for the team, go to Access Control under settings and configure the JWT Secret to be the same as in the step above.

<!-- Now rename the site or configure a custom domain, and then go to your Okta application created in the steps above, edit the "General Settings" and add your new site as a redirect URL. -->

Then go to "Trusted Origins" under "API" in Okta and add a new Trusted Origin. Enter a title, the URL of your new site, and check both the CORS and Redirect boxes.
