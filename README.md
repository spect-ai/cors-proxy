# rlp-proxy

This is the source code for the proxy used in <a href='https://github.com/dhaiwat10/react-link-preview'>react-link-preview</a>.

Feel free to fork both the main package and this proxy and deploy your own copy of the project.

[![Deploy](https://www.herokucdn.com/deploy/button.svg)](https://heroku.com/deploy)

## Environment variables

1. `SERVER_URL`: The URL where your server is runnning (used for static file serving). For example, if you are running the server locally it will be `localhost:3000` and if your server is live at `abc.xyz`, the value for this variable will be `abc.xyz`. This variable is necessary to serve static files correctly.
2. `SUPABASE_KEY`: Your Supabase project's anon key. This proxy uses Supabase to cache query results. 
- If you don't need this, you can safely remove everything inside [cache.ts](src/lib/cache.ts) & its references.
- If you do plan on using the included caching functionality, you will need to 1. Create a new project on [Supabase](https://app.supabase.io), 2. Create a new table called `meta-cache` and create the following columns: `url` (text), `title` (text), `description` (text), `siteName` (text), `image` (text), `hostname` (text).
