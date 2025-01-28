# kinde-vue

> [!WARNING]
> This is a work in progress being developed in the open and is only partially
functional yet.  Watch this space (the warning will be removed when it is ready).

A starter kit for clients interfacing with Kinde Authentication,
using Vue components and Naive UI.

## Register an account on Kinde

Before getting started, create an account and set up your organization and
applications on [Kinde](https://app.kinde.com/register)

## Set up your local environment

Clone this repo.

Use the hosted version of the Kinde SDK (no backend install required).

Make a copy of `.env_sample` named `.env` and set the following values:

> [!NOTE] Find the correct values in your Kinde dashboard under\
> `Settings` **&gt;** `Applications` **&gt;** `Frontend App`.

<dt>VITE_KINDE_CLIENT_ID</dt>
  <dd>the alphanumeric string uniquely identifying this application</dd>

<dt>VITE_KINDE_DOMAIN</dt>
  <dd>either your kinde.com subdomain or, if you've set it up, your custom domain</dd>


## Set your callback and logout URLs

Your users will be redirected to Kinde to authenticate.  After they have logged
in or registered they will be redirected back to your Vue application.

You need to specify in your Kinde dashboard which URL you would like your users
to be redirected to in order to complete authenticating.

While still on the `settings -> application -> frontend app` page, set
`Allowed callback URLs` to the destination (e.g., `http://localhost:3000`)

You will also need to set the URL they will be redirected to when logging out.
Set the `Allowed logout redirect URLs` to that destination (e.g. `http://localhost:3000/goodbye`)

## Running, testing and deploying

### Setup your local environment

Install the dependencies:

   ```bash
   npm install
   ```

Make a copy of `.env_sample` and name it simply `.env`. Set the following values
from the Kinde `Settings -> Applications -> Backend app` page.

<dt>KINDE_ISSUER_URL</dt>
  <dd>the domain value</dd>

<dt>KINDE_CLIENT_ID</dt>
  <dd>the client id</dd>

<dt>KINDE_CLIENT_SECRET</dt>
  <dd>The client secret</dd>

<dt>KINDE_SITE_URL</dt>
  <dd>Your App's domain value</dd>

<dt>KINDE_REDIRECT_URL</dt>
  <dd>Kinde will redirect here after login</dd>

<dt>KINDE_POST_LOGOUT_REDIRECT_URL</dt>
  <dd>Kinde will redirect here after logout</dd>

e.g.:

```sh
KINDE_SITE_URL=http://localhost:3000
KINDE_ISSUER_URL=https://<your_subdomain>.kinde.com
KINDE_POST_LOGOUT_REDIRECT_URL=http://localhost:3000
KINDE_CLIENT_ID=${KINDE_CLIENT_ID}
KINDE_CLIENT_SECRET=${KINDE_CLIENT_SECRET}
KINDE_REDIRECT_URL=http://localhost:3000/kinde_callback
```

### Set your Callback and Logout URLs

Your user will be redirected to Kinde to authenticate.  After they have logged
in or registered they will be redirected back to your ExpressJS application.

You need to specify in Kinde which url you would like your user to be redirected
to in order to authenticate your app.

On the App Keys page set `Redirect url` to `http://localhost:3000/kinde_callback`

> Important! This is required for your users to successfully log in to your app.

You will also need to set the url they will be redirected to upon logout. Set the
`Logout url` to [](http://localhost:3000) while you're testing everything locally.

### Start the app

`npm start` and navigate to `http://localhost:3000`.

Click on `Sign up` and register your first user for your business! 🚀


Start your app locally:

```sh
npm run dev
```

Deploy your app to Cloudflare Pages

```sh
wrangler deploy .
```

