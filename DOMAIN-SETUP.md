# Connect dastanverse.nl to GitHub Pages

These instructions use GitHub account `highelf` and repository `dastanverse`. Adjust the account if publishing elsewhere. Setup is not performed automatically by these files.

1. Publish and confirm https://highelf.github.io/dastanverse/ works first.
2. In GitHub account Settings → Pages, use “Add a domain” to verify dastanverse.nl. GitHub supplies a TXT record; add that exact record in GoDaddy DNS and verify on GitHub.
3. In the website repository Settings → Pages → Custom domain, enter `dastanverse.nl` and Save **before changing the website DNS records**. GitHub adds a `CNAME` file to the source branch. Run `git pull` locally to keep that file.
4. Open GoDaddy Domain Portfolio → dastanverse.nl → DNS. Keep the existing nameservers. Review existing records and save a copy before editing. If GoDaddy does not host your nameservers, edit DNS at the authoritative provider instead.
5. Replace only the conflicting website A records for host `@` with these four A records (one address per record). Use the default TTL:

   - `185.199.108.153`
   - `185.199.109.153`
   - `185.199.110.153`
   - `185.199.111.153`

6. Set a CNAME record with name `www` and value `highelf.github.io` (no https and no repository path). Review and replace only conflicting website records at `www`.
7. If old AAAA records at `@` point elsewhere, replace them with GitHub's IPv6 records, or remove those obsolete website-only AAAA records when using IPv4 only. GitHub IPv6 addresses are `2606:50c0:8000::153`, `2606:50c0:8001::153`, `2606:50c0:8002::153`, and `2606:50c0:8003::153`.
8. Preserve email MX records, SPF/DKIM/DMARC TXT records, and mail-related CNAME/SRV records so marketing@dastanverse.nl continues working. Do not replace the whole DNS zone. Do not use GoDaddy forwarding for this setup.
9. Wait for GitHub's DNS check and HTTPS certificate. Changes and HTTPS availability can take up to 24 hours. Enable “Enforce HTTPS” in repository Pages settings when available.
10. Confirm https://dastanverse.nl shows the site and https://www.dastanverse.nl redirects to it. Test email separately.

## Official references

- GitHub custom domain setup: https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site
- GitHub domain verification: https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/verifying-your-custom-domain-for-github-pages
- GoDaddy A records: https://www.godaddy.com/en-uk/help/add-or-edit-an-a-record-42546

DNS has not been inspected or changed for this project. These are the intended records; existing conflicts must be checked during setup.
