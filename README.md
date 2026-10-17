# SIMOC — Automação de Relatórios de Vulnerabilidades a partir do Nmap

> *Nmap XML → risk-classified vulnerability reports (PDF/CSV), with CVE/CVSS correlation.*

Projeto Integrador do curso de Segurança Cibernética (SENAI), desenvolvido **em equipe**. O SIMOC simula uma avaliação de segurança completa de uma rede corporativa (Active Directory + servidores Linux/IoT), da descoberta de hosts até a correlação de vulnerabilidades.

Este repositório documenta a **minha participação** no projeto e aponta para o repositório oficial da equipe.

## 🎯 Objetivo

Reduzir o trabalho manual de triagem de vulnerabilidades: a partir da saída **XML do Nmap**, gerar automaticamente relatórios (**PDF/CSV**) com os ativos e serviços **classificados por nível de risco**, correlacionando os achados com **CVE/CVSS**.

## 🧩 Minha contribuição

- **Fase 10 — Análise de Vulnerabilidades e correlação CVE/CVSS:** levantamento das vulnerabilidades por host, atribuição de **CVSS v3.1**, classificação de criticidade e proposta de mitigação para cada achado. Consulta cruzada a **NVD/NIST**, **CVE/Mitre** e **OWASP Top 10**.
- Apoio à lógica de **classificação por risco** usada na automação em Python que consome o XML do Nmap e consolida o relatório.

A minha tabela de correlação (sanitizada para portfólio) está em [`evidencias/tabela_cvss_sanitizada.md`](evidencias/tabela_cvss_sanitizada.md): 5 vulnerabilidades críticas identificadas, incluindo Zerologon (CVE-2020-1472), serviços sem autenticação (Node-RED/MQTT) e software em EOL.

## 🛠️ Tecnologias

`Python` · `Nmap` · `XML parsing` · `CVSS v3.1` · `NVD/NIST` · `OWASP Top 10`

## 👥 Equipe e repositório oficial

Trabalho colaborativo. O repositório completo da equipe está em:
**[github.com/alefkaue/simoc-integrador](https://github.com/alefkaue/simoc-integrador)**

Créditos aos colegas de equipe pelas demais fases (descoberta de rede, enumeração SMB/LDAP/Kerberos, RPC/DNS, análise web e automação principal).

## 📚 O que aprendi

- Traduzir saída bruta de scanner em **informação acionável** classificada por risco.
- Calcular e justificar **CVSS** na prática, não só ler o número pronto.
- A diferença entre uma vulnerabilidade **teórica** e uma **explorável/mitigada** no contexto da rede.
- Trabalhar em equipe com versionamento e divisão de fases.

## 🔒 Nota de segurança

Todo o conteúdo publicado aqui foi **sanitizado**: endereços de rede do laboratório foram substituídos por rótulos genéricos. Nenhuma credencial, flag ou dado sensível é exposto. Ambiente de laboratório controlado e autorizado pelo curso.
