# Open Zaak Helm Chart

Install PostgreSQL:

```bash
helm repo add bitnami https://charts.bitnami.com/bitnami
helm upgrade --install postgresql bitnami/postgresql \
    --set postgresqlUsername=open-zaak \
    --set postgresqlPassword=SUPER-SECRET \
    --set postgresqlDatabase=open-zaak \
    --set postgresqlPostgresPassword=SUPER-SECRET
```

Install Open Zaak with:

```bash
helm repo add open-zaak https://bartjkdp.github.io/open-zaak-charts/
helm upgrade --install open-zaak open-zaak/open-zaak \
    --set settings.secretKey=SOME-RANDOM-SECRET \
    --set settings.allowedHosts=open-zaak.gemeente.nl \
    --set settings.database.username=postgres \
    --set settings.database.password=SUPER-SECRET \
    --set settings.database.name=open-zaak \
    --set ingress.enabled=true \
    --set ingress.hosts={open-zaak.gemeente.nl}
```
