# ludus_wazuh_n8n

Ludus role repo that deploys:

- Wazuh single-node stack (Docker)
- n8n + Postgres (Docker)

Author: Howard Mukanda (@ITSecurityLabs on YouTube and X)
<img width="1351" height="719" alt="image" src="https://github.com/user-attachments/assets/4e35d382-6d1a-4622-affb-a1fda4bbb531" />

<img width="2554" height="1320" alt="image" src="https://github.com/user-attachments/assets/09137f1a-63fa-4e2a-a57b-07faa80f6a8c" />


## What it does

- Installs Docker and Docker Compose plugin (if needed).
- Sets `vm.max_map_count=262144` for Wazuh indexer.
- Deploys n8n with a dedicated Postgres database (as per n8n Docker docs).
- Disables secure cookie so learners can use `http://VM_IP:5678`.
- Deploys Wazuh 4.9.0 single-node via `wazuh-docker`.
- Connects n8n container to the Wazuh Docker network so it can query the indexer.

## Usage with Ludus

1. Add this repo as a Ludus role (see https://docs.ludus.cloud).
2. Assign the `ludus_wazuh_n8n` role to a Linux VM in your range YAML under `roles:`.
3. Apply the environment; the VM will install Docker, Wazuh, and n8n automatically.
