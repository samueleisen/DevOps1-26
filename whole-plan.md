### The Implementation Roadmap

To avoid getting stuck, we will build this from inside-out:

* **Phase 1: Local Stack Prototype (30-45 mins - $0, no AWS needed yet)**
  * Build a clean `docker-compose.yml` locally with Gatus, Node Exporter, Prometheus, and Grafana.
  * Verify the status page probes and Grafana dashboards look great on `localhost`.
* **Phase 2: The GitHub Incident Webhook (30 mins)**
  * Configure Gatus/Alertmanager to send an alert webhook to a GitHub repository dispatch event.
  * Write a simple GitHub Actions workflow that creates an automated Issue when a probe fails.
* **Phase 3: AWS Free Tier Provisioning & Cloudflare Tunnel (1 hour)**
  * Spin up the free EC2 instance.
  * Setup Cloudflare Tunnel so `status.yourdomain` and `metrics.yourdomain` route cleanly with automatic HTTPS and 0 open ports.
* **Phase 4: GitOps CI/CD Deployment**
  * Set up GitHub Actions to deploy config changes automatically on push to `main`.
