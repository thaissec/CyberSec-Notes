# Portas e protocolos

O IP identifica o prédio. A **porta** identifica o apartamento (o serviço).

| Porta | Protocolo | Uso |
|---|---|---|
| 22 | SSH | Acesso remoto Linux |
| 53 | DNS | Resolução de nomes |
| 80 | HTTP | Web sem criptografia |
| 443 | HTTPS | Web com criptografia |
| 445 | SMB | Compartilhamento de arquivos Windows |
| 3306 | MySQL | Banco de dados |
| 3389 | RDP | Acesso remoto Windows |

Mais portas em [08-Ferramentas/portas.md](../08-Ferramentas/portas.md).

## Faixas

| Faixa | Nome | Uso |
|---|---|---|
| 0 a 1023 | Bem conhecidas | Serviços padrão |
| 1024 a 49151 | Registradas | Aplicações específicas |
| 49152 a 65535 | Dinâmicas | Porta de origem temporária do cliente |

## TCP versus UDP

| | TCP | UDP |
|---|---|---|
| Ideia | Confiável | Rápido ("dispara e esquece") |
| Conexão | Three-way handshake | Sem conexão |
| Garantias | Entrega e ordem | Nenhuma |
| Usado em | HTTP/HTTPS, SSH, e-mail | Streaming, DNS, jogos, VoIP |
| Analogia | Ligar e confirmar que o amigo atendeu | Gritar "fogo!" sem esperar resposta |

> **Pense:** por que o MySQL fica na 3306 e não na 80? Porque portas separam serviços; na 80 haveria conflito com o servidor web.
