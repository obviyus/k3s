# Logging into GHCR

```bash
kubectl create secret docker-registry ghcr-login-secret --docker-server=https://ghcr.io --docker-username=$YOUR_GITHUB_USERNAME --docker-password=$YOUR_GITHUB_TOKEN --docker-email=$YOUR_EMAIL
```

I found this to be significantly easier than in Nomad.