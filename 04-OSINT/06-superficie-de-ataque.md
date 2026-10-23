# Superfície de ataque e vetor mais provável

**Superfície de ataque:** conjunto de pontos por onde alguém poderia tentar entrar.

## Método

1. Liste o que foi encontrado (documentos, painéis, e-mails, subdomínios, portas, versões).
2. Para cada item pergunte: **isso permite entrar, obter credenciais ou ganhar informação?**
3. Escolha o vetor mais provável: fácil para o atacante e de alto impacto.
4. Justifique combinando pelo menos dois achados.

> Exemplo: e-mails coletados + painel de login exposto indicam ataque de credenciais ou phishing direcionado ao painel.

## Mapeamento MITRE

| Fonte | ID e nome |
|---|---|
| Tática | TA0043 Reconnaissance |
| Google Dorks | T1593.002 Search Engines |
| theHarvester (e-mails) | T1589.002 Email Addresses |
| theHarvester (hosts) | T1590 Gather Victim Network Information |
| Shodan | T1596.005 Scan Databases |

Um achado isolado vale pouco. O valor está em **combinar** achados.
