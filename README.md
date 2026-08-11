# Soulmate Cyber V2 — VirusTotal IP Reputation Scanner

A static, client-side IP reputation scanner powered by the VirusTotal API.
Upload an Excel file of IP addresses, enter your own VirusTotal API key(s),
and get a live-scanning console plus downloadable Excel/ZIP reports —
all running in the browser, no backend required.

## Files

- `index.html` — the entire app (HTML + CSS + JS in one file). This is the only file GitHub Pages needs.

## Deploy to GitHub Pages

1. Create a new GitHub repository (public).
2. Upload `index.html` to the repo root.
3. Go to **Settings → Pages**.
4. Under "Build and deployment," set **Source** to `Deploy from a branch`, branch `main`, folder `/ (root)`.
5. Save. Your app will be live at:
   `https://<your-username>.github.io/<repo-name>/`

## Using the app

1. Prepare an `.xlsx` file with a column named exactly **`IP Address`**.
2. Open the deployed page.
3. Upload the Excel file.
4. Paste one or more VirusTotal API keys (each visitor uses their own key — nothing is stored or sent anywhere except VirusTotal).
5. Adjust cooldown/retries if needed, then click **[ EXECUTE ] SCAN IP FILE**.
6. Watch the live console and KPI dashboard.
7. Download results as Excel or a combined ZIP from the Export Center once the scan finishes.

## Known limitation: CORS

VirusTotal's API does not always send CORS headers permitting direct
browser requests from arbitrary origins. If you see `Network/CORS error`
messages in the console panel, direct calls are being blocked by the
browser. The fix is to route requests through a small serverless proxy
(e.g., a Cloudflare Worker or Vercel Edge Function) that forwards the
request server-side and adds the `x-apikey` header. This isn't included
here since it requires its own hosting — ask if you'd like one built.

## Sample test IPs

For quick testing, an `.xlsx` with an `IP Address` column containing a mix
of known-clean DNS IPs, duplicates, invalid entries, and IPv6 addresses
will exercise all the app's code paths (validation, dedup, clean/malicious
classification, and error handling).

#Link
https://khadijaz8.github.io/Soulmate_cyber_VT3/
