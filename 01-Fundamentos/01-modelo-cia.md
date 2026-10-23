# Modelo CIA

CIA é o tripé da segurança da informação. Toda medida de segurança protege pelo menos um destes pilares.

| Pilar | Pergunta | Exemplo de proteção |
|---|---|---|
| **Confidencialidade** | Quem pode acessar a informação? | Senha guardada com segurança no banco de dados |
| **Integridade** | A informação foi alterada sem autorização? | Log de transações que não pode ser editado |
| **Disponibilidade** | O sistema está acessível quando preciso? | Site no ar 24 horas por dia |

## Como reconhecer o pilar violado

| Situação | Pilar comprometido | Continua intacto |
|---|---|---|
| Hacker baixa a base de clientes, os dados seguem corretos e o sistema funciona | Confidencialidade | Integridade e disponibilidade |
| Alguém altera registros financeiros e o sistema segue online | Integridade | Confidencialidade e disponibilidade |
| DDoS derruba o site do banco, mas os dados estão seguros | Disponibilidade | Confidencialidade e integridade |
| Ransomware criptografa arquivos (e, se roubou dados antes, também vazou) | Integridade e disponibilidade (e possivelmente confidencialidade) | Depende do caso |

> **Dica:** pergunte sempre: **vazou? mudou? parou?** Um mesmo incidente pode violar mais de um pilar.

## Perguntas de revisão

1. Um DDoS derruba o site de uma loja, sem vazar nada. Qual pilar foi violado?
2. Por que um ransomware pode violar os três pilares?

<details><summary>Respostas</summary>

1. Disponibilidade.
2. Criptografa e bloqueia arquivos (disponibilidade e integridade) e, se roubou os dados antes, também vazou (confidencialidade).
</details>
