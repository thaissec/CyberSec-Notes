# theHarvester

Coleta **e-mails, subdomínios, hosts e IPs** de um domínio em várias fontes públicas.

```bash
theHarvester -d [alvo] -b google,bing,linkedin
```

| Opção | Significado |
|---|---|
| `-d` | Domínio alvo |
| `-b` | Fontes. Variam por versão; algumas exigem chave de API |

| Dado | Como um atacante usaria |
|---|---|
| E-mails | Phishing, tentativas de senha; revela o padrão `nome.sobrenome@` |
| Subdomínios | Amplia a superfície: ambientes de teste costumam ser mais fracos |
| Hosts/IPs | Onde estão os servidores; aprofundar com Shodan e Nmap |

## Exemplo ilustrativo

```
[*] Emails found: 3
maria.silva@exemplo.com
joao.souza@exemplo.com
contato@exemplo.com

[*] Hosts found: 4
www.exemplo.com:203.0.113.10
homolog.exemplo.com:203.0.113.30
vpn.exemplo.com:203.0.113.40
```

- Padrão `nome.sobrenome@`: dá para deduzir o e-mail de qualquer funcionário.
- `homolog` sugere ambiente de testes; `vpn` é alvo de ataques de credenciais.
