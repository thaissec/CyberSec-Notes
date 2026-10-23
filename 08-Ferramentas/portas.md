# Portas de interesse

| Porta | Serviço | Observação de segurança |
|---|---|---|
| 21 | FTP | Credenciais em texto puro; verificar login anônimo |
| 22 | SSH | Preferir chaves; limitar tentativas |
| 23 | Telnet | Sem criptografia; substituir por SSH |
| 25 | SMTP | Verificar relay aberto |
| 53 | DNS | Cuidado com transferência de zona |
| 80 | HTTP | Redirecionar para HTTPS |
| 110 / 143 | POP3 / IMAP | Usar versões com TLS |
| 139 / 445 | NetBIOS / SMB | Desabilitar SMBv1; restringir acesso |
| 161 (UDP) | SNMP | Trocar community; usar SNMPv3 |
| 389 / 636 | LDAP / LDAPS | Bloquear consulta anônima; usar TLS |
| 443 | HTTPS | Manter certificados e TLS atualizados |
| 1433 | MS SQL Server | Não expor à internet |
| 3306 | MySQL | Não expor à internet |
| 3389 | RDP | Proteger com VPN e MFA |
| 5432 | PostgreSQL | Não expor à internet |
| 5900 | VNC | Senha forte e túnel seguro |
