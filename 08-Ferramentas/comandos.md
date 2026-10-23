# Cola de comandos

| Objetivo | Comando |
|---|---|
| Ver IP local | `ip addr` ou `ifconfig` (Windows: `ipconfig`) |
| Testar conectividade | `ping 8.8.8.8` |
| Caminho até um destino | `traceroute google.com` (Windows: `tracert`) |
| WHOIS | `whois dominio.com` |
| Todos os registros DNS | `dig dominio.com ANY` |
| Consulta DNS simples | `nslookup dominio.com` |
| Varredura padrão | `nmap [IP]` |
| Portas específicas | `nmap -p 80,443,22 [IP]` |
| Todas as portas | `nmap -p- -T4 [IP]` |
| Connect / SYN / UDP | `nmap -sT [IP]`, `sudo nmap -sS [IP]`, `sudo nmap -sU [IP]` |
| Versões | `nmap -sV [IP]` |
| Sistema operacional | `sudo nmap -O [IP]` |
| Versão, scripts e SO | `sudo nmap -sV -sC -O [IP]` |
| SMB: SO e domínio | `nmap -p445 --script smb-os-discovery [IP]` |
| SMB: EternalBlue | `nmap -p445 --script smb-vuln-ms17-010 [IP]` |
| SNMP: info básica | `nmap -sU -p161 --script snmp-info [IP]` |
| Scripts de vulnerabilidade | `nmap --script vuln [IP]` |
| Enumeração SMB | `enum4linux -a [IP]` |
| Listar shares sem senha | `smbclient -L //[IP] -N` |
| Enumeração SNMP | `snmpwalk -v2c -c public [IP]` |
| Um único OID | `snmpget -v2c -c public [IP] sysName.0` |
| Enumeração LDAP | `ldapsearch -x -H ldap://[IP] -b 'dc=exemplo,dc=lab'` |
| Base do LDAP | `ldapsearch -x -H ldap://[IP] -s base namingContexts` |
| E-mails e subdomínios | `theHarvester -d [dominio] -b google,bing,linkedin` |
| Instalar SNMP e LDAP | `sudo apt install snmp ldap-utils -y` |
| Instalar MIBs | `sudo apt install snmp-mibs-downloader -y` |
| Instalar OpenVAS/GVM | `sudo apt install gvm -y` |
| Configurar e iniciar GVM | `sudo gvm-setup`, `sudo gvm-check-setup`, `sudo gvm-start` |
| Filtros Wireshark | `http`, `dns`, `arp`, `icmp`, `tcp`, `ip.addr == X`, `tcp.port == 443` |
