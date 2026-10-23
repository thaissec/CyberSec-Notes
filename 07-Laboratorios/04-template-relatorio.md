# Template de relatório de reconhecimento

Copie este arquivo, preencha com seus achados reais e apague as instruções.

| | |
|---|---|
| Nome | |
| Data | |
| Alvo web | `[ENDEREÇO]` |
| Alvo sistema | `[IP]` |

## 1. Sumário executivo
*Para leitor não técnico. Máximo 1 página, sem jargão.*

- **Objetivo e escopo:**
- **Resumo dos achados** (quantos, o mais crítico, risco principal):
- **Recomendação principal** (a ação mais urgente):

## 2. Metodologia

| # | Técnica | Ferramenta | Por que foi aplicada |
|---|---|---|---|
| 1 | Recon passivo (OSINT) | | |
| 2 | Varredura de portas | | |
| 3 | Detecção de serviços | | |
| 4 | Enumeração detalhada | | |
| 5 | Scan de vulnerabilidades | | |
| 6 | | | |

## 3. OSINT e reconhecimento passivo

### 3.1 Google Dorks
| Dork | Resultado | Impacto |
|---|---|---|
| | | |

### 3.2 theHarvester
| Tipo | Dado | Impacto |
|---|---|---|
| E-mails | | |
| Subdomínios | | |
| Hosts / IPs | | |

### 3.3 Shodan
Filtro usado e resultados:

### 3.4 WHOIS e DNS
| | |
|---|---|
| Registradora | |
| E-mail de contato | |
| Nameservers | |
| Registros DNS | A: / MX: / TXT-SPF: |

## 4. Enumeração ativa

### 4.1 Nmap
| Porta | Estado | Serviço / Versão | Observação |
|---|---|---|---|
| | | | |

### 4.2 SMB (enum4linux)
| | |
|---|---|
| Usuários | |
| Compartilhamentos | |
| Política de senhas | |
| Workgroup / Domínio | |

### 4.3 SNMP (snmpwalk)
| OID | Nome | Valor |
|---|---|---|
| sysDescr | Descrição do sistema | |
| sysName | Nome do host | |
| hrSWRunName | Processos | |
| ifDescr | Interfaces | |

### 4.4 LDAP
Estrutura encontrada (se a porta 389 estiver fechada, registre isso):

## 5. Vulnerabilidades identificadas
*Do CVSS mais alto ao mais baixo. Mínimo 3 achados.*

### 5.1 Resumo por severidade
| Crítico (9.0 a 10.0) | Alto (7.0 a 8.9) | Médio (4.0 a 6.9) | Baixo (0.1 a 3.9) |
|---|---|---|---|
| | | | |

### 5.2 Achado 1
| | |
|---|---|
| Título | |
| CVE | CVE- |
| CVSS | |
| Host afetado | |
| Descrição | |
| Evidência | *(inserir print)* |
| Mitigação | |

*(repita para os achados 2, 3 e seguintes)*

## 6. Superfície de ataque
| Vetor | Serviço / Tecnologia | Risco | Técnica MITRE |
|---|---|---|---|
| | | | |

## 7. Sequência de ataque proposta
| Passo | Ação do atacante | Baseado no achado | Técnica MITRE |
|---|---|---|---|
| 1 | | | |
| 2 | | | |
| 3 | | | |

**Narrativa (3 a 5 frases):**

## 8. Recomendações
*Específicas e acionáveis, em ordem de prioridade.*

| Prior. | Vulnerabilidade | Ação recomendada | Prazo |
|---|---|---|---|
| 1° | | | |
