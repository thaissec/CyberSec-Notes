# Shodan

Buscador de **dispositivos**: varre a internet e guarda o que cada IP expõe. Conta gratuita basta para praticar. Site: <https://www.shodan.io>

| Filtro | O que faz | Exemplo |
|---|---|---|
| `org:` | Organização | `org:"Nome da Empresa"` |
| `product:` | Software | `product:Apache country:BR` |
| `port:` | Porta | `port:22` |
| `country:` | País | `country:BR` |
| `vuln:` | CVE associada (pode exigir plano pago) | `vuln:CVE-2017-0144` |

## Como ler um resultado

| Campo | Como usar |
|---|---|
| IP e organização | Confirmar que é do alvo |
| Portas abertas | Comparar com o que deveria estar exposto |
| Banner | Software e versão → procurar CVEs |
| Vulnerabilidades | Indícios, não confirmação |
| Data da coleta | Os dados podem estar desatualizados |

## O que o Shodan mostra que um Nmap local não mostra

- A visão **de fora**, depois de firewall e NAT.
- **Escala:** milhares de dispositivos por organização, produto ou vulnerabilidade.
- **Histórico** de serviços expostos.
- **Discrição:** não envia pacotes ao alvo.
