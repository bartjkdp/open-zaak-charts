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
cd charts/open-zaak
helm upgrade --install open-zaak ./open-zaak \
    --set allowedHosts=open-zaak.gemeente.nl \
    --set settings.database.username=postgres \
    --set settings.database.password=SUPER-SECRET \
    --set settings.database.name=open-zaak \
    --set ingress.enabled=true \
    --set ingress.hosts={open-zaak.gemeente.nl}
```
