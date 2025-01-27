# kinde-vue

A starter kit for clients interfacing with Kinde Authentication.  Using Vue components and Naive UI.

## Register an account on Kinde

Before getting started, create an account and set up your organization and applications on [Kinde](https://app.kinde.com/register)

## Set up your local environment

Clone this repo.

Use the hosted version of the Kinde SDK (no install required).

Make a copy of `.env.example` named `.env` and set the following values (find the correct values in your Kinde dashboard under settings -> Applications -> Frontend app page.

- VITE_KINDE_CLIENT_ID
- VITE_KINDE_DOMAIN (either your kinde.com subdomain or, if you've set it up, your custom domain)

## Set your callback and logout URLs

Your users will be redirected to Kinde to authenticate.  After they have logged in or registered they will be redirected back to your Vue application.

You need to specify in your Kinde dashboard which URL you would like your users to be redirected to in order to complete authenticating.

While still on the `settings -> application -> frontend app` page, set `Allowed callback URLs` to the destination (e.g., `http://localhost:3000`

You will also need to set the URL they will be redirected to when logging out.  Set the `Allowed logout redirect URLs` to that destination (e.g. `http://localhost:3000/goodbye`)

## Running, testing and deploying

Start your app locally:

```sh
npm run dev
```

Deploy your app to Cloudflare Pages

```
wrangler deploy .
```

