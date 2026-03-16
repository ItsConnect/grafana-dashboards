# Grafana Dashboards — ITS Connect

Production-ready Grafana dashboards for Linux server monitoring with Zabbix datasource integration.

Designed for infrastructure teams that use **Zabbix** as their primary monitoring backend and **Grafana** for visualization. These dashboards provide comprehensive visibility into system health, container workloads, and database performance.

## Dashboards

| Dashboard | Description |
|-----------|-------------|
| [Linux Server Overview](dashboards/linux-overview.json) | CPU, RAM, disk, network, uptime, load average, top processes, and Nginx metrics |
| [Docker Monitoring](dashboards/docker-monitoring.json) | Container status, per-container CPU/memory, network and disk I/O |
| [MySQL Performance](dashboards/mysql-performance.json) | QPS, connections, slow queries, buffer pool, InnoDB operations, replication |

## Screenshots

> Screenshots coming soon.

## Requirements

- **Grafana** 11.0 or later
- **Zabbix plugin for Grafana** ([alexanderzobnin-zabbix-app](https://grafana.com/grafana/plugins/alexanderzobnin-zabbix-app/))
- A configured Zabbix datasource in Grafana

## Installation

1. Download the desired JSON file from the `dashboards/` directory.
2. In Grafana, navigate to **Dashboards → New → Import**.
3. Click **Upload dashboard JSON file** and select the downloaded file.
4. In the import screen, select your Zabbix datasource when prompted.
5. Click **Import**.

> **Note:** The dashboards reference a datasource UID of `zabbix-ds`. If your Zabbix datasource has a different UID, either update it during import or edit the JSON before importing.

## Datasource Configuration

These dashboards expect a Zabbix datasource configured with:

- **Type:** Zabbix
- **URL:** Your Zabbix API endpoint (e.g., `https://zabbix.example.com/api_jsonrpc.php`)
- **Authentication:** Username/password or API token with read access

## Customization

All dashboards use template variables where applicable. After importing, you can adjust:

- **Host groups** and **hosts** via the dropdown selectors at the top of each dashboard
- **Time range** — defaults to last 24 hours
- **Thresholds** — gauge panels include sensible defaults (green/yellow/red) that can be modified per your environment

## License

This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.

## Links

- **ITS Connect** — [https://itsconnect.com.br](https://itsconnect.com.br)
