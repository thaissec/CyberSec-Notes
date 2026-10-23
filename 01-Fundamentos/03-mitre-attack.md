# MITRE ATT&CK

Base de conhecimento pública, montada a partir de ataques reais documentados. Site: <https://attack.mitre.org>.

| Conceito | Significado | Exemplo |
|---|---|---|
| **Tática** | O **objetivo** do adversário em uma etapa (coluna da matriz) | Initial Access |
| **Técnica** | O **método** usado (linha) | T1566 Phishing |
| **Sub-técnica** | Detalhe específico. Nem toda técnica tem | T1566.001 Phishing com anexo |

O ATT&CK Enterprise tem **14 táticas**.

## Como ler uma técnica no site

- **Descrição:** o que é, como funciona e por que é eficaz.
- **Exemplos de grupos:** quais grupos APT já usaram.
- **Detecção:** o que monitorar (foco do Blue Team/SOC).
- **Mitigação:** como reduzir a superfície de ataque.

## Técnicas frequentes

| ID | Nome | Tática |
|---|---|---|
| T1566.001 / .002 | Phishing: anexo / link | Initial Access |
| T1190 | Exploit Public-Facing Application | Initial Access |
| T1078 | Valid Accounts | Initial Access, Persistence, Defense Evasion |
| T1204.002 | User Execution: Malicious File | Execution |
| T1547.001 | Registry Run Keys / Startup Folder | Persistence |
| T1041 | Exfiltration Over C2 Channel | Exfiltration |
| T1485 | Data Destruction | Impact |

## Passo a passo para mapear um incidente

1. Leia a narrativa e separe em fases.
2. Para cada fase, pergunte: **qual era o objetivo do atacante?** A resposta é a tática.
3. Procure a técnica dentro da tática em `attack.mitre.org` e anote o ID.
4. Confira se existe sub-técnica mais específica.
5. Abra a aba **Mitigações** e escolha uma medida concreta.
6. Feche com uma frase: o que foi comprometido e o que teria impedido.

> **Exploração livre:** escolha um grupo APT no site e veja quais técnicas ele mais usa.
