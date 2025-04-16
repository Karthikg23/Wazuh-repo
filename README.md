# Wazuh-repo
Essentials for wazuh
# Wazuh + AWS Integration Setup

This project deploys a Wazuh stack with integration to AWS services such as EC2, S3, and CloudTrail.

## Setup Guide

### 1. Edit Ansible Hosts
```
ansible/hosts
```
Add your EC2 IPs under `wazuh_manager` and `wazuh_agents`.

### 2. Deploy Wazuh Manager
```bash
ansible-playbook -i ansible/hosts ansible/install_wazuh_manager.yml
```

### 3. Install Agents
```bash
ansible-playbook -i ansible/hosts ansible/install_wazuh_agent.yml
```

### 4. Configure CloudTrail Log Ingestion
```bash
sudo bash scripts/cloudtrail_s3_wazuh_config.sh
```

### 5. Register New Agents (if not using Ansible)
```bash
sudo bash scripts/agent_registration.sh
```

### 6. View Dashboard
Open Wazuh Dashboard: `https://<WAZUH_IP>:5601`
Default login: `admin / admin`

## License
Apache 2.0

