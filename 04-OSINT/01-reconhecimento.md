# Reconhecimento e footprinting

Primeira fase de qualquer ataque, e a mais subestimada pela defesa.

| | Passivo | Ativo |
|---|---|---|
| Contato com o alvo | Nenhum | Direto |
| Rastro | Não gera log no alvo | Pode ser detectado e registrado |
| Fontes/ferramentas | WHOIS, DNS, Shodan, redes sociais | Nmap, ping, traceroute |
| Exemplo | Consultar quem registrou um domínio | Varredura de portas |

## O que está publicamente disponível

| Fonte | O que revela |
|---|---|
| **WHOIS** | Dono do domínio, registradora, contatos, datas |
| **DNS** | Registros A, MX, TXT (SPF/DKIM), NS |
| **Shodan** | Dispositivos e serviços expostos, com versões |
| **Redes sociais / OSINT** | Funcionários, tecnologias, estrutura, projetos |

## Tática MITRE TA0043 (Reconnaissance)

| ID | Nome | Significado |
|---|---|---|
| T1590 | Gather Victim Network Information | IPs, ASN, blocos de rede |
| T1591 | Gather Victim Org Information | Estrutura, funcionários, parceiros |
| T1596 | Search Open Technical Databases | Shodan, WHOIS, Certificate Transparency |
| T1598 | Phishing for Information | Coletar credenciais por e-mail falso, usando dados do WHOIS |

## Como registrar

Para cada consulta anote: **fonte consultada → informação encontrada → o que revela a um atacante**. Feche com um resumo de 3 a 5 linhas.

DNS é detalhado em [02-Redes/04-dns.md](../02-Redes/04-dns.md).
