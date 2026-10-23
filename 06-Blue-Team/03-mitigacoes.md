# Mitigações e defesa

## Contra ARP spoofing em uma empresa

- **Monitoramento de ARP** e alertas para mudança de MAC de IPs críticos (como o gateway).
- **IDS/IPS** para detectar o padrão.
- **Segmentação de rede** (VLANs) para limitar quem alcança quem.
- **Dynamic ARP Inspection** e tabelas ARP estáticas para equipamentos críticos.
- **Criptografia ponta a ponta** (HTTPS, VPN) para reduzir o dano mesmo com interceptação.

## Onde a defesa age na cadeia de ataque

| Fase | Controles |
|---|---|
| Reconhecimento | Privacidade do WHOIS, revisão do que está indexado, DMARC |
| Entrega | Treinamento contra phishing, filtro de anexos, sandbox de e-mail |
| Exploração | Atualização de sistemas, desabilitar macros por GPO |
| Persistência | Restringir escrita no registro, EDR, MFA, expiração de senhas |
| Exfiltração | Monitorar tráfego de saída (DLP), alertas de anomalia |

## Boas práticas apontadas pelo curso

- MFA e políticas de senha forte, com bloqueio de conta após tentativas.
- Manter sistemas atualizados e reduzir a exposição à internet.
- Backups isolados e protegidos.
- Alertas para acessos fora do horário normal.
- Trocar credenciais padrão (por exemplo, a community `public` do SNMP) e usar SNMPv3.
- Bloquear consultas anônimas ao LDAP e usar TLS.

## Detecção segundo o MITRE ATT&CK

Cada técnica no site tem uma aba **Detecção** com o que monitorar. Para estudar: escolha uma técnica (por exemplo, T1078 Valid Accounts) e anote quais logs e comportamentos denunciariam o uso.
