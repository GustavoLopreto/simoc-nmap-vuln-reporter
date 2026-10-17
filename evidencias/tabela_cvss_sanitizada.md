# CYMAG — Análise de Vulnerabilidades e CVEs
# Fase 10 — Correlação CVE / NVD / OWASP | CVSS v3.1
# Analista: Gustavo Lopreto | Rede: <rede do laboratório>
# Data: junho/2026

> Evidência sanitizada para portfólio: endereços de laboratório substituídos por rótulos genéricos.

## Fontes consultadas
- NVD NIST: https://nvd.nist.gov
- OWASP Top 10 2021: https://owasp.org/Top10
- CVE Mitre: https://cve.mitre.org

## Domain Controller — `<host-dc do laboratório>`

| CVE / CWE | Vulnerabilidade | CVSS v3.1 | Criticidade | Mitigação |
|---|---|---|---|---|
| CWE-300 / CVE-2017-0144 | SMB Signing desabilitado / NTLM Relay | 7.5 | Alta | GPO: habilitar SMB Signing obrigatório |
| CVE-2017-0144 | EternalBlue SMBv1 (já desabilitado) | 10.0 | MITIGADO | SMBv1 já off — manter monitoramento |
| CVE-2020-1472 | Zerologon — Netlogon RCE | 10.0 | Crítica | Verificar patch MS-NRPC ago/2020 |
| CWE-284 | RPC Endpoint Mapper exposto | 5.3 | Média | Restringir acesso RPC por firewall |
| CWE-200 | NetBIOS — LLMNR poisoning possível | 5.3 | Média | Desabilitar LLMNR via GPO |

## Host Desconhecido — `<host-2 do laboratório>`

| CVE / CWE | Vulnerabilidade | CVSS v3.1 | Criticidade | Mitigação |
|---|---|---|---|---|
| CWE-284 | RPC exposto — enumeração possível | 5.3 | Média | Restringir acesso RPC por firewall |

## Servidor Linux IoT — `<host-iot do laboratório>`

| CVE / CWE | Vulnerabilidade | CVSS v3.1 | Criticidade | Mitigação |
|---|---|---|---|---|
| CWE-306 | Node-RED sem autenticação (p.1880) | 9.1 | Crítica | Habilitar adminAuth no settings.js |
| CWE-306 | MQTT sem autenticação e sem TLS (1883) | 9.1 | Crítica | password_file + TLS no mosquitto.conf |
| CVE-2012-5627 | MySQL 5.5.62 — EOL desde 2018 (3307) | 9.8 | Crítica | Migrar para MySQL 8.x ou MariaDB |
| CWE-319 | HTTP nginx sem HTTPS (p.80) | 5.3 | Média | Configurar TLS/HTTPS no nginx |
| N/A | SSH exposto sem restrição de origem | 3.7 | Baixa | Restringir por IP + chave pública apenas |

## Resumo de Criticidade

| Nível | Quantidade |
|---|---|
| Crítica | 5 |
| Alta | 1 |
| Média | 4 |
| Baixa | 1 |
| Mitigado | 1 |
