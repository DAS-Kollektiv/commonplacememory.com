# commonplacememory.com

A one-page site for Commonplace at https://commonplacememory.com. It shows the
name and the icon and nothing else. It exists so that browsers and Google's
favicon service learn the Commonplace icon for this domain before the vault's
connector hostname moves here. No tracking, no external requests.

Served by GitHub Pages from `main` (root folder). Owner: Sam Wachtel, for
DAS-Kollektiv.

## Files

| File | Source |
|---|---|
| `favicon.ico`, `favicon.svg`, `favicon-192.png`, `app-icon-512.png` | `commonplace/src/commonplace/browser/assets/` (commonplace#383) |
| `apple-touch-icon.png` | `app-icon-180.png` from the same folder |
| `CNAME` | GitHub Pages custom domain |

To update the icon, copy the files again from the `commonplace` repository's
`main` branch.

## DNS

The domain is registered in Cloud Domains in GCP project `wachtel-us-dns` and
served by the Cloud DNS public zone `commonplacememory-com`
(`commonplacememory.com.`) in the same project. That zone is **not** managed by
Terraform. The records below were added by hand with `gcloud dns record-sets
create` on 2026-11-19. To bring them under Terraform later, import each one as
`google_dns_record_set` with ID
`projects/wachtel-us-dns/managedZones/commonplacememory-com/rrsets/<name>/<type>`.

| Name | Type | TTL | Data |
|---|---|---|---|
| `commonplacememory.com.` | A | 3600 | `185.199.108.153` `185.199.109.153` `185.199.110.153` `185.199.111.153` |
| `commonplacememory.com.` | AAAA | 3600 | `2606:50c0:8000::153` `2606:50c0:8001::153` `2606:50c0:8002::153` `2606:50c0:8003::153` |
| `www.commonplacememory.com.` | CNAME | 3600 | `das-kollektiv.github.io.` |
