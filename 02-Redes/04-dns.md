# DNS

Traduz nomes de domínio em endereços IP.

## Como um nome é resolvido

1. O navegador e o sistema verificam o **cache**.
2. A consulta vai ao **resolvedor** (do provedor ou `8.8.8.8`).
3. O resolvedor pergunta aos **servidores raiz**, depois ao **TLD** (`.com`, `.br`) e ao **servidor autoritativo** do domínio.
4. A resposta volta e fica em cache pelo tempo do **TTL**.

## Tipos de registro

| Tipo | Função |
|---|---|
| **A** | Nome → IPv4 |
| **AAAA** | Nome → IPv6 |
| **MX** | Servidores de e-mail (menor número = maior prioridade) |
| **NS** | Servidores DNS do domínio |
| **TXT** | Texto livre; SPF, DKIM, DMARC, verificações |
| **CNAME** | Apelido: um nome aponta para outro |
| **SOA** | Dados administrativos da zona |
| **PTR** | Resolução reversa: IP → nome |

## Como ler uma linha do `dig`

```
dominio-ficticio.com.   300   IN   A   203.0.113.10
```

| Parte | Significado |
|---|---|
| `dominio-ficticio.com.` | Nome consultado |
| `300` | TTL em segundos (5 min) |
| `IN` | Classe Internet |
| `A` | Tipo do registro |
| `203.0.113.10` | Valor |

> Muitos servidores modernos não respondem completamente a `ANY`. Consulte cada tipo: `dig dominio.com A`, `MX`, `TXT`, `NS`.

## SPF, DKIM e DMARC

| Mecanismo | O que faz | Exemplo |
|---|---|---|
| **SPF** | Lista quem pode enviar e-mail pelo domínio | `v=spf1 include:_spf.google.com ~all` |
| **DKIM** | Assina o e-mail; a chave pública fica no DNS | `seletor._domainkey.dominio.com` |
| **DMARC** | Define o que fazer quando SPF/DKIM falham | `v=DMARC1; p=reject` |

- SPF: `~all` (softfail) é "suspeito, mas aceite"; `-all` manda rejeitar.
- DMARC: `p=none` só monitora; `p=quarantine` manda para spam; `p=reject` rejeita.
- Sem DMARC (ou com `p=none`), o domínio pode ser falsificado com facilidade.
