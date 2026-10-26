<!-- LOVABLE:BEGIN -->
> [!IMPORTANT]
> This project is connected to [Lovable](https://lovable.dev). Avoid rewriting
> published git history — force pushing, or rebasing/amending/squashing commits
> that are already pushed — as it rewrites history on Lovable's side and the
> user will likely lose their project history.
>
> Commits you push to the connected branch sync back to Lovable and show up in
> the editor, so keep the branch in a working state.
<!-- LOVABLE:END -->

- PowerGo now uses Supabase (Auth, Postgres, Storage) for stations, rentals and login; keep the schema in supabase/setup.sql in sync with src/integrations/supabase/types.ts.
- Keep navigation and reusable station display in shared components with separate content routes; this gives each requested page a stable URL.
- Keep the Hannover map browser-only with fixed sample coordinates and OpenStreetMap attribution; this avoids server rendering failures and implies no live station data.
