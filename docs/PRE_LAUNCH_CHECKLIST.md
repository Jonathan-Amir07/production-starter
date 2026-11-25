# Pre-Launch Checklist

Run `/ship-audit` before deploying and verify these manual steps:

1. **Secrets & Auth**: Confirm all `.env` keys are set in hosting dashboard (Vercel/Railway/etc.) and no mutating endpoint works unauthenticated.
2. **Headers & CSP**: Tighten `Content-Security-Policy` in `vercel.json` for any external APIs, fonts, or images you add.
3. **Legal Pages**: Update placeholders in `public/privacy.html` and `public/terms.html` with your project name, date, and actual third-party services.
4. **Google Search Console**:
   - Replace `your-domain.com` in `public/robots.txt` and `public/sitemap.xml`.
   - Verify your domain via DNS TXT record in Google Search Console and submit `sitemap.xml`.
5. **Email Auth** (if sending emails): Verify `SPF`, `DKIM`, and `DMARC` records in your domain DNS.
6. **GitHub Polish**: Update `README.md` with live URL + screenshot, add GitHub repository Topics, and confirm CI passes.
