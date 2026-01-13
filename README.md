# ingowebsite_v2

Deployt eine statische Website (Storage Static Website) per GitHub Actions. Die Logic App wird manuell deployed.

## Workflow
Der Workflow liegt hier: `.github/workflows/deploy-azure-static-website.yml`

Er macht:
- aktiviert Static Website am Storage Account (Index/Error)
- laedt `*.html` nach `$web`
- ersetzt die Logic-App-URL in `index.html` ueber ein Secret

## Benotigte GitHub Secrets/Vars
Secrets:
- `AZURE_STORAGE_CONNECTION_STRING`
- `LOGIC_APP_URL` (wird beim Deploy in `index.html` eingesetzt)

## Logic App (manuell)
`logic_app.json` liegt nur als Referenz/Asset im Repo. Deployment/Updates erfolgen manuell ueber das Azure Portal oder die CLI.

## Hinweis
Wenn du CSS/JS/Bilder deployen willst, passe im Workflow das Upload-Pattern an (aktuell nur `*.html`).
