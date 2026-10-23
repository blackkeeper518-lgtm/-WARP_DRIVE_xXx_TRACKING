# WARP DRIVE parcel uploader

Static page for importing Flash/Thai carrier CSV or Excel files into `public.parcels`.

## Configure Supabase outside `index.html`

1. Copy `config.example.js` to `config.js` in the same directory as `index.html`.
2. Set `SUPABASE_URL` to the Supabase project URL and `SUPABASE_KEY` to the project's publishable (or legacy anon) key.
3. Deploy `config.js` alongside `index.html`. The file is excluded from Git by `.gitignore`; add it through your hosting/deployment configuration.
4. Do not use a `service_role` key or any secret key in this browser app. Browser configuration is visible to visitors; protect `public.parcels` with appropriate Supabase RLS policies.

If `config.js` is missing or incomplete, the page shows a setup warning and will not accept uploads. The importer still writes parcel rows to `public.parcels` in batches of 50.
