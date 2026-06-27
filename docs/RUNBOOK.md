# Runbook

## Service

- Name: `billing-api`
- Team: `Payments`
- Owner: `mooref068@gmail.com`
- Cost center: `payments`

## First Checks

```bash
kubectl get rollout billing-api -n billing-api-dev
kubectl get pods -l app.kubernetes.io/name=billing-api -n billing-api-dev
kubectl logs -l app.kubernetes.io/name=billing-api -n billing-api-dev
```

## Health

```bash
curl https://billing-api.dev.platform.ohanyere.internal/healthz
curl https://billing-api.dev.platform.ohanyere.internal/readyz
curl https://billing-api.dev.platform.ohanyere.internal/livez
```

## Rollback

```bash
kubectl argo rollouts undo billing-api -n billing-api-dev
```

Escalate to `Payments` through `mooref068@gmail.com` if rollback does not restore service.
