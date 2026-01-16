# ludus_wazuh_n8n

Ludus role that deploys:

- Wazuh single-node stack (Docker)
- n8n + Postgres (Docker)

## Behavior

- Installs Docker and Docker Compose plugin (if needed).
- Configures `vm.max_map_count=262144` for Wazuh indexer stability.
- Deploys n8n with a dedicated Postgres database.
- Sets `N8N_SECURE_COOKIE=false` so learners can use `http://VM_IP:5678` without TLS in the lab.
- Deploys Wazuh 4.9.0 single-node via the `wazuh-docker` repository.
- Connects the n8n container to the Wazuh Docker network so it can query the Wazuh indexer over HTTPS.
