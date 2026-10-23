# 01 · Terminal e sistema de arquivos

[← Índice do módulo](README.md)

## Objetivo
Navegar pelo sistema Linux e manipular arquivos em um ambiente próprio de estudo.

## Comandos essenciais

| Comando | Função |
|---|---|
| `pwd` | Exibe o diretório atual |
| `ls -la` | Lista arquivos, incluindo ocultos |
| `cd ~/Documentos` | Entra em um diretório |
| `mkdir -p estudos/linux` | Cria diretórios |
| `touch notas.txt` | Cria arquivo vazio |
| `cp notas.txt copia.txt` | Copia arquivo |
| `mv copia.txt backup.txt` | Renomeia arquivo |
| `cat notas.txt` | Exibe conteúdo |
| `grep -n "rede" notas.txt` | Procura texto com número da linha |

> Cuidado com `rm`: a remoção normalmente não passa pela lixeira.

## Laboratório seguro

```bash
mkdir -p ~/cybersec-lab/linux
cd ~/cybersec-lab/linux
printf 'redes\nlinux\nseguranca\n' > notas.txt
cat notas.txt
grep -n linux notas.txt
```

## Exercício
Explique a diferença entre `>` e `>>` e teste os dois em um arquivo descartável.
