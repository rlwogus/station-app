# PowerGo – Setup mit eigenem Supabase-Projekt

## 1. Supabase-Projekt erstellen
1. https://supabase.com → Sign up → **New project** (Region z. B. Frankfurt, Passwort merken).
2. Warten, bis das Projekt bereit ist.

## 2. Datenbank einrichten
1. Linke Leiste → **SQL Editor** → **New query**.
2. Den kompletten Inhalt von `supabase/setup.sql` einfügen → **Run**.
   (Erstellt: profiles, stations, rentals, Storage-Bucket `station-images`, Sicherheitsregeln und die 4 Hannover-Beispielstationen.)

## 3. Anmeldung einstellen (für Tests einfacher)
**Authentication → Sign In / Providers → Email** → "Confirm email" **ausschalten** → Save.

## 4. Schlüssel eintragen
**Project Settings → API**: `Project URL` und den `anon` / `publishable` Key kopieren.
Datei `.env.example` nach `.env` kopieren und beide Werte eintragen.
Den `service_role`-Key NIE verwenden oder teilen.

## 5. Lokal starten
```
bun install      # oder: npm install --legacy-peer-deps
bun run dev      # oder: npm run dev
```
Testen: Registrieren → Station eintragen (mit Foto) → Meine Stationen → Bearbeiten → Löschen → Ausleihen → Rückgabe → Abmelden.

## 6. Veröffentlichen (Cloudflare)
Beim Build/Deploy dieselben zwei Variablen setzen:
`VITE_SUPABASE_URL` und `VITE_SUPABASE_PUBLISHABLE_KEY`.
