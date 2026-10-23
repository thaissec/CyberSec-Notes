# WHOIS

```
$ whois dominio-ficticio.com
Domain Name: DOMINIO-FICTICIO.COM
Registrar Name:  João Silva
Registrar Email: joao@empresa.com
Creation Date:   2018-03-15
Expiration Date: 2026-03-15
Name Server:     ns1.hostingprovider.com
```

| Campo | O que significa | Por que importa |
|---|---|---|
| Registrar | Empresa onde o domínio foi registrado | Onde a conta é gerenciada; alvo de golpes de suporte falso |
| Creation Date | Criação | Domínio muito novo é suspeito |
| Expiration Date | Expiração | Se vencer, pode ser sequestrado |
| Name Server | Servidores DNS | Revela o provedor de DNS |
| Status | Travas (`clientTransferProhibited`) | Dificultam transferência indevida |
| Registrant/Admin/Tech | Contatos | Úteis para phishing e engenharia social |

**Defesa:** habilitar a privacidade do WHOIS no painel do registrador. Campos "REDACTED" ou "Privacy" são bom sinal.

Ferramentas web: `who.is` e `registro.br/tecnologia/ferramentas/whois/` (para `.br`).
