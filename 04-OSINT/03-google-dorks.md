# Google Dorks

Buscas com operadores avançados. O buscador já indexou o conteúdo; você encontra o que a empresa talvez nem soubesse que estava público.

| Operador | Função | Exemplo |
|---|---|---|
| `site:` | Limita a um domínio | `site:exemplo.com` |
| `filetype:` | Tipo de arquivo | `site:exemplo.com filetype:pdf` |
| `inurl:` | Termo na URL | `site:exemplo.com inurl:admin` |
| `intitle:` | Termo no título | `site:exemplo.com intitle:"index of"` |
| `intext:` | Termo no texto | `site:exemplo.com intext:senha` |

| Dork | O que pode encontrar | Impacto |
|---|---|---|
| `site:[alvo] filetype:pdf` | Documentos públicos | Metadados e informações internas |
| `site:[alvo] inurl:admin` | Painéis administrativos | Onde tentar acesso |
| `site:[alvo] intitle:"index of"` | Diretórios listáveis | Arquivos que deveriam estar protegidos |

**Defesa:** revisar o que está indexado, proteger painéis com autenticação e restrição de IP, remover documentos e metadados sensíveis. O `robots.txt` não é proteção.
