# Publicar CyberSec-Notes no GitHub

Este ZIP contém a pasta `CyberSec-Notes/` com o README e os oito módulos.

## Opção recomendada: pelo navegador

1. Extraia o ZIP no computador.
2. Abra seu repositório GitHub e entre na aba **Code**.
3. Clique em **Add file → Upload files**.
4. Abra a pasta `CyberSec-Notes` extraída, selecione **todos os arquivos e pastas dentro dela** (não a pasta externa) e arraste para a página de upload.
5. Confira se os caminhos aparecem corretamente e confirme em **Commit changes**.
6. Se o navegador não aceitar a estrutura de pastas ou houver conflitos, use a opção Git abaixo.

## Opção mais confiável: Git no computador

1. Instale o Git e abra o terminal na pasta onde deseja trabalhar.
2. Execute:

```bash
git clone https://github.com/thaissec/CyberSec-Notes.git
```

3. Copie **o conteúdo** da pasta `CyberSec-Notes` extraída para dentro da pasta clonada, substituindo o `README.md` e o banner quando solicitado.
4. No terminal, dentro da pasta clonada:

```bash
git add -A
git commit -m "docs: apply Orbital Cyber and expand modules"
git push origin main
```

**Importante:** o repositório atual já possui `01-Fundamentos`. Este pacote usa esse padrão de nomes para todos os módulos. Se houver pastas antigas com nomes em minúsculas, remova as duplicatas somente após conferir os arquivos.

## Verificação

- O banner aparece no topo do README.
- Os oito links da tabela abrem as pastas.
- Os links internos de cada módulo abrem os capítulos.
- As seis imagens originais permanecem em `assets/`.
