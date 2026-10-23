# Análise de tráfego com Wireshark

Analisador de pacotes: é como colocar um fone de ouvido na rede.

| Uso | Objetivo |
|---|---|
| Defesa | Detectar comportamento anômalo e ataques |
| Ataque | Capturar credenciais em redes sem criptografia (testes autorizados) |
| Forense | Investigar incidentes e reconstruir o que aconteceu |

> Capturar tráfego de outras pessoas sem autorização é ilegal. Use na sua rede, em laboratório ou em `.pcap` de treino.

## Os três painéis

| Painel | O que mostra |
|---|---|
| Lista de pacotes (em cima) | Número, tempo, origem, destino, protocolo, informação |
| Detalhes (meio) | Cabeçalhos por camada: Ethernet, IP, TCP, HTTP |
| Bytes (embaixo) | Hexadecimal e ASCII; tráfego sem criptografia é legível |

Colunas: **No.** (sequência), **Time**, **Source/Destination**, **Protocol**, **Length**, **Info**.

## Capturar ao vivo

1. Escolha a interface (`eth0` cabo, `wlan0` Wi-Fi). A que tem gráfico de atividade costuma ser a correta.
2. Clique na barbatana azul para iniciar.
3. Gere tráfego (site, `ping`, `nslookup`).
4. Quadrado vermelho para parar.
5. Filtre e analise; **File > Save As** para guardar o `.pcap`.

## Filtros de exibição

| Filtro | O que exibe | Quando usar |
|---|---|---|
| `http` | Tráfego HTTP (sem criptografia) | Dados legíveis, formulários, URLs |
| `dns` | Consultas e respostas DNS | Domínios que uma máquina consultou |
| `tcp` | Todo o TCP | Conexões e handshakes |
| `arp` | Resolução de MAC | Anomalias na rede local |
| `icmp` | Ping e respostas | Conectividade e varreduras |
| `ip.addr == 8.8.8.8` | Tráfego de/para um IP | Isolar uma máquina |
| `tcp.port == 443` | Porta 443, qualquer protocolo | Isolar HTTPS |

Combine com `&&` (E) e `||` (OU): `tcp.port == 443 && ip.addr == 8.8.8.8`. A comparação usa **dois** sinais de igual. A barra fica verde se a sintaxe é válida e vermelha se há erro.

| | Filtro de captura | Filtro de exibição |
|---|---|---|
| Quando age | Antes: só grava o que combina | Depois: apenas esconde |
| Sintaxe | BPF (`port 80`) | Wireshark (`http`) |
| Vantagem | Arquivos menores | Muda à vontade sem perder dados |

## Ferramentas úteis

| Onde | Para quê |
|---|---|
| Statistics > Protocol Hierarchy | % de cada protocolo; volume inesperado (ex.: ARP) chama atenção |
| Statistics > Conversations | Pares de máquinas, pacotes e bytes; aba Ethernet mostra MACs |
| Follow TCP Stream (botão direito) | Reconstrói a conversa completa |
| Analyze > Expert Information | Alertas automáticos, como IP duplicado (sinal clássico de ARP spoofing) |

## Encontrando o handshake

Filtro `tcp` e as três primeiras linhas de uma conexão: **SYN**, **SYN-ACK**, **ACK**. A quarta já é de dados (por exemplo, um `GET`), confirmando que dados só trafegam após o handshake.

## HTTP versus HTTPS

No **HTTP** o conteúdo trafega em texto puro: URLs, formulários e até senhas podem ser lidos. No **HTTPS** o conteúdo é criptografado: vê-se só metadados (IPs, portas, tamanho, às vezes o nome do servidor).
