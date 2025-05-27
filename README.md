
# 🛡️ Threat Intelligence Feeds – evdsecops

Bem-vindo ao repositório de **Threat Feeds públicos** mantido por [evdsecops](https://github.com/evdsecops), dedicado a fornecer **indicadores de comprometimento (IOCs)** atualizados e validados para integração com dispositivos de segurança como FortiGate, SIEMs e outras soluções de defesa.

## 🚀 Por que este repositório existe?

O cenário atual de ameaças exige que as organizações **automatizem a coleta, validação e disseminação de inteligência de ameaças**. Este projeto foi criado com os seguintes objetivos:

- 🌐 **Centralizar fontes de IOCs confiáveis** em formatos simples e integráveis.
- 🔄 **Automatizar atualizações e validações** via GitHub Actions.
- 📡 **Facilitar a integração direta com firewalls e outras soluções de segurança**, como o FortiGate, por meio de `external-resource`.
- 🔎 **Oferecer rastreabilidade e versionamento** dos dados, algo fundamental para governança e auditoria.

## 🧠 Estratégia CTI aplicada

A construção destes feeds segue práticas de **Cyber Threat Intelligence (CTI)**, com ênfase no ciclo de inteligência:

### 1. **Coleta**
- Fontes utilizadas:
  - [AbuseIPDB](https://abuseipdb.com)
  - [MalwareBazaar](https://bazaar.abuse.ch)
  - Honeypots próprios (scripts em Python)
- Coletas automatizadas via APIs e processadas diariamente.

### 2. **Processamento**
- Validação de formato (IP, domínio, hash).
- Filtragem por reputação mínima e tipos de ameaça.
- Remoção de duplicatas e entradas obsoletas.

### 3. **Análise**
- Enriquecimento de dados (em andamento).
- Priorização com base em frequência e categoria de ameaça.
- Roteamento por tipo de IOC (IPs, domínios, arquivos).

### 4. **Distribuição**
- Distribuição via arquivos `.txt` e `.json` em:
  - [`feeds/malicious_ips.txt`](feeds/malicious_ips.txt)
  - [`feeds/malicious_domains.txt`](feeds/malicious_domains.txt)
  - [`feeds/malicious_hashes.txt`](feeds/malicious_hashes.txt)

### 5. **Feedback e Melhoria**
- Logs de uso nos ambientes corporativos.
- Pull Requests são bem-vindos para sugerir novas fontes ou melhorias.

## 📂 Formato dos Feeds

| Tipo       | Arquivo                      | Descrição                              |
|------------|------------------------------|----------------------------------------|
| IPs        | `malicious_ips.txt`          | Lista de IPs identificados com má reputação. |
| Domínios   | `malicious_domains.txt`      | Domínios utilizados para C2 e phishing. |
| Hashes     | `malicious_hashes.txt`       | Hashes SHA256 de amostras maliciosas.  |

> ⚠️ Todos os feeds são formatados com **um IOC por linha**, sem cabeçalho, compatível com FortiGate (`external-resource`), SIEMs e scripts de automação.

## 🔐 Segurança e Governança

- Commits assinado digitalmente.
- Histórico de mudanças auditável.
- Branch principal protegida.

## 🤝 Contribuições

Este projeto é aberto para **colaborações da comunidade de segurança**. Sugestões, novas fontes e melhorias são bem-vindas via Issues ou Pull Requests.
