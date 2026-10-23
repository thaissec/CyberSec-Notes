# Ambiente de laboratório

> **Importante:** endereços e senhas do laboratório da escola **não** devem ser publicados. Aqui eles aparecem como `[ENDEREÇO]` e `[SENHA]`. Mantenha o original em um arquivo local fora do repositório.

## Alvos de prática

| Alvo | O que é | Acesso |
|---|---|---|
| **Kali Linux** (desktop no navegador) | Desktop completo com Nmap, Metasploit, Hydra, Wireshark | `[ENDEREÇO]/kali/` |
| **DVWA** | Aplicação web propositalmente vulnerável | `[ENDEREÇO]/dvwa/` |
| **Juice Shop** | Loja online vulnerável; crie sua própria conta | `[ENDEREÇO]/juiceshop/` |
| **WebGoat** | Aplicação de treino com lições guiadas | `[ENDEREÇO]/webgoat/` |
| **Alvo de sistema** | Metasploitable 2, acessível de dentro do Kali | `[IP]` |

DVWA, Juice Shop e WebGoat têm duas camadas de login: a janela de autenticação do navegador (credenciais fornecidas pela escola) e o login dentro da aplicação.

## Passo obrigatório antes de usar o Kali no navegador

O desktop do Kali usa WebRTC, que exige configuração especial no Chrome quando o lab não tem HTTPS:

1. Abra uma nova aba no Chrome e cole `chrome://flags/#unsafely-treat-insecure-origin-as-secure`.
2. No campo de texto, cole o endereço do laboratório.
3. Troque o menu de "Desativado" para **Enabled**.
4. Clique em **Relaunch**.

Só é preciso fazer isso uma vez por computador, e só funciona no Chrome.

## Praticar em casa

- Máquinas Docker de teste: <https://github.com/cybersantana83/cyberlab-local>
- Alvo público autorizado do Nmap: <http://scanme.nmap.org> (**não exagere** nas varreduras)
- Sem Kali: `whatismyip.com` (IP público), `mxtoolbox.com` (traceroute), `nmap.online` (Nmap contra o scanme).

## Exercício: ficha de rede

Funciona em Kali, WSL2, cmd do Windows ou Mac.

| Parte | O que fazer | Como |
|---|---|---|
| 1 | IP local | `ip addr` ou `ifconfig` |
| 2 | IP público | `whatismyip.com` |
| 3 | Conectividade | `ping 8.8.8.8` |
| 4 | Caminho do pacote | `traceroute google.com` |
| 5 | Varredura autorizada | `nmap -p 80,443,22 scanme.nmap.org` |
| 6 | Análise: onde está o firewall e qual porta é mais arriscada | Interpretação |

Na parte 6: compare IP local e público (a diferença é o NAT), veja onde aparecem asteriscos no traceroute (possível filtro) e justifique a porta mais arriscada.
