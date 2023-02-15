# Ansible Monitoring setup

### Steps:

- a) - Install Prometheus on Target system.
- b) - Install Grafana on Target system.
- c) - Install Node exporter for exposing system data.
- d) - Install Alertmanager for sending alerts to Pagerduty/Slack etc
- e) - Create everything as a service so starting stopping and handling will be easy.

```bash
├── hosts
├── playbook1.yml
├── README.md
└── roles
    ├── alertmanager
    │   ├── files
    │   │   └── alertmanager.yml
    │   ├── handlers
    │   │   └── main.yml
    │   ├── tasks
    │   │   └── main.yml
    │   ├── templates
    │   │   └── init.service.j2
    │   └── vars
    │       └── main.yml
    ├── grafana
    │   ├── handlers
    │   │   └── main.yml
    │   ├── README.md
    │   ├── tasks
    │   │   └── main.yml
    │   ├── templates
    │   │   └── grafana.conf.j2
    │   └── vars
    │       └── main.yml
    ├── prometheus
    │   ├── files
    │   │   └── alertrules.yml
    │   ├── handlers
    │   │   └── main.yml
    │   ├── tasks
    │   │   └── main.yml
    │   ├── templates
    │   │   ├── init.service.j2
    │   │   └── prometheus.conf.j2
    │   └── vars
    │       └── main.yml
    └── prometheus_node_exporter
        ├── tasks
        │   └── main.yml
        ├── templates
        │   └── init.service.j2
        └── vars
            └── main.yml

```
