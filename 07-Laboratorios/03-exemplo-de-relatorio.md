# Exemplo completo de relatório (fictício)

Empresa e achados inventados, para mostrar como as seções se conectam.

## Sumário executivo (modelo)

> Foi realizada uma investigação de reconhecimento sobre os sistemas de teste da empresa X, com o objetivo de identificar informações e falhas que poderiam ser exploradas por um atacante. Foram encontrados 7 problemas, sendo 2 críticos. O principal risco é que um serviço de compartilhamento de arquivos desatualizado permite o controle remoto de um servidor. Recomenda-se, com urgência, atualizar esse serviço e restringir o acesso a ele pela rede.

## Metodologia

| # | Técnica | Ferramenta | Por que |
|---|---|---|---|
| 1 | Recon passivo (OSINT) | whois, dig, Dorks, theHarvester, Shodan | Levantar informação sem contato com o alvo |
| 2 | Varredura de portas | Nmap `-p- -T4` | Descobrir todos os serviços expostos |
| 3 | Detecção de serviços | Nmap `-sV -O -sC` | Identificar versões e SO para relacionar a CVEs |
| 4 | Enumeração | enum4linux, snmpwalk, ldapsearch | Extrair usuários, shares, processos e diretório |
| 5 | Scan de vulnerabilidades | OpenVAS | Confirmar e priorizar falhas |
| 6 | Mapeamento MITRE | attack.mitre.org | Relacionar achados a táticas e técnicas |

## Exemplo de achado

| Campo | Conteúdo |
|---|---|
| Título | Serviço FTP em versão comprometida com backdoor (porta 21) |
| CVE / CVSS | CVE-2011-2523 / 9.8 (Crítico). Confirme os números no NVD |
| Host afetado | `[IP]`, porta 21/TCP |
| Descrição | O scan identificou, via `nmap -sV` e OpenVAS, uma versão do FTP com backdoor conhecido, exposta sem restrição |
| Evidência | Print do OpenVAS (Severity e Detection Result) e do `nmap -sV` |
| Mitigação | Atualizar para a versão corrigida ou substituir por SFTP; restringir a porta 21 no firewall em até 7 dias |

## Superfície de ataque

| Vetor | Serviço | Risco | MITRE |
|---|---|---|---|
| E-mails corporativos coletados | Padrão nome.sobrenome@ | Phishing direcionado | T1589.002 / T1566 |
| Painel administrativo exposto | `/admin` | Tentativa de senha | T1190 / T1110 |
| FTP vulnerável | Porta 21 | Execução remota de comandos | T1190 |
| SMB com senhas fracas | Porta 445 | Adivinhação sem bloqueio | T1110 |
| SNMP com community padrão | 161/UDP | Mapeamento do ambiente | T1602.001 |
| LDAP anônimo | Porta 389 | Lista de usuários e cargos | T1087 |

## Sequência de ataque

| Passo | Ação | Baseado em | MITRE |
|---|---|---|---|
| 1 | Coleta e-mails, subdomínios e documentos públicos | theHarvester e Dorks | TA0043 / T1593.002 |
| 2 | Varre portas e identifica versões | Nmap `-p-` e `-sV` | T1595 |
| 3 | Consulta LDAP e SNMP para listar usuários e processos | LDAP anônimo e `public` | T1087 / T1602.001 |
| 4 | Acessa por serviço vulnerável ou senhas fracas | FTP e política sem bloqueio | T1190 / T1110 |
| 5 | Acessa dados e os envia para fora | Shares com permissões amplas | T1005 / T1041 |

**Narrativa (modelo):** O atacante começa de forma passiva, coletando e-mails, subdomínios e documentos públicos, sem contato direto. Em seguida, varre as portas e identifica versões, o que revela um FTP desatualizado. Consultas anônimas ao LDAP e ao SNMP fornecem usuários, cargos e processos, e a política de senhas fraca torna viável adivinhar credenciais. Com acesso a um servidor, alcança compartilhamentos com permissões amplas e copia os dados para fora. Cada etapa só foi possível porque a anterior entregou informação ou acesso.

## Recomendações

| Prior. | Vulnerabilidade | Ação | Prazo |
|---|---|---|---|
| 1° | FTP com backdoor (9.8) | Atualizar ou substituir por SFTP; bloquear a 21 exceto IPs autorizados | 7 dias |
| 2° | SMB com senhas fracas | 12+ caracteres com complexidade, bloqueio após 5 tentativas, desabilitar SMBv1 | 15 dias |
| 3° | SNMP `public` | Trocar a community, limitar ao IP de monitoramento, migrar para SNMPv3 | 15 dias |
| 4° | LDAP anônimo | Desabilitar consulta anônima, exigir autenticação e TLS | 30 dias |
| 5° | Exposição no WHOIS e documentos | Ativar privacidade do WHOIS e remover metadados | 30 dias |

> Recomendação **vaga** ("atualizar o sistema") não vale. **Específica:** "Atualizar o Apache 2.2.8 para uma versão suportada da série 2.4 e desativar módulos não utilizados, em até 15 dias".
