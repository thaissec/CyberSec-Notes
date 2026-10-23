# 02 · Permissões, usuários e processos

[← Índice do módulo](README.md)

## Permissões

No Linux, arquivos possuem permissões para **usuário**, **grupo** e **outros**. Cada grupo pode receber leitura (`r`), escrita (`w`) e execução (`x`).

```bash
ls -l notas.txt
chmod 640 notas.txt
stat notas.txt
```

`640` significa: proprietário lê e escreve (6), grupo lê (4), outros não têm acesso (0).

## Usuários e processos

```bash
whoami
id
ps aux | head
top
```

Use `sudo` somente quando necessário. Evite permissões amplas como `chmod 777`.

## Exercício
Em uma VM própria, crie um arquivo e compare as permissões `600` e `644`.
