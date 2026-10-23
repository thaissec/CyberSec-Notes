# 03 · Logs e serviços no Linux

[← Índice do módulo](README.md)

## Observabilidade básica

```bash
systemctl --type=service --state=running
journalctl -n 30 --no-pager
ss -tuln
```

- `systemctl` mostra serviços em execução em sistemas com systemd.
- `journalctl` consulta registros do sistema.
- `ss -tuln` lista portas TCP/UDP em escuta.

## Investigação defensiva

Em uma VM de laboratório, identifique um serviço ativo, sua porta e mensagens recentes nos logs. Registre horário, comando e observação.

> Alguns comandos podem exigir permissões administrativas ou não existir em sistemas sem systemd.
