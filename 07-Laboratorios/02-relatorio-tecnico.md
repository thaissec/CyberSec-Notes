# Documentação técnica e relatório

## O relatório é o produto

Um exame de sangue com valores alterados, mas sem laudo, é inútil. O relatório é o laudo: transforma dados em decisão.

- O cliente paga pelo relatório, não pelo scan.
- **Achado sem evidência é achado sem valor.**
- **Mitigação vaga** deixa o cliente sem saber o que fazer.

## Estrutura padrão

| # | Seção | Conteúdo |
|---|---|---|
| 1 | Capa | Cliente, escopo, data, classificação de confidencialidade |
| 2 | Sumário executivo | Para não técnicos: o que foi achado e o risco. Máximo 1 página |
| 3 | Escopo e metodologia | O que foi testado, o que ficou fora, como, base legal e ética |
| 4 | Achados | O coração do relatório, com 6 campos |
| 5 | Conclusão e mitigações | Recomendações priorizadas e próximos passos |

## Os 6 campos de um achado

| # | Campo | O que escrever |
|---|---|---|
| 1 | Título | Nome curto e descritivo |
| 2 | Descrição técnica | O que é, como foi encontrado, contexto (ferramenta, comando, alvo) |
| 3 | Evidência | Print, log ou output que comprova |
| 4 | Impacto | Perdas para o negócio: reputação, LGPD, operação, financeiro |
| 5 | Severidade | Baixo, médio, alto ou crítico, pelo impacto real |
| 6 | Mitigação | Ação específica e aplicável |

## Achado fraco versus bem documentado

| Campo | Fraco | Bem documentado |
|---|---|---|
| Título | Problema no domínio | Dados pessoais do responsável expostos no WHOIS |
| Descrição | O domínio expõe informações. | A consulta WHOIS revelou nome, e-mail e telefone do responsável técnico sem proteção de privacidade. |
| Evidência | (vazio) | Trecho do `whois` com os campos destacados |
| Impacto | Pode ser ruim. | Phishing direcionado ou engenharia social |
| Severidade | Alto (sem justificativa) | Médio (risco real, impacto limitado ou condicionado) |
| Mitigação | Corrigir o problema. | Habilitar a privacidade do WHOIS no painel do registrador |

## Severidade

Baseada no **impacto real no negócio**, não só no CVSS.

| Severidade | Critério | Exemplos |
|---|---|---|
| **Crítico** (9.0 a 10.0) | Comprometimento total ou perda de dados sensíveis de terceiros | RCE, exfiltração |
| **Alto** (7.0 a 8.9) | Impacto significativo na operação ou reputação | Acesso não autorizado a sistemas |
| **Médio** (4.0 a 6.9) | Risco real, impacto limitado ou condicionado | Contatos expostos no WHOIS |
| **Baixo** (0.1 a 3.9) | Informação útil ao atacante, sem impacto imediato | Versão do servidor HTTP revelada |

## Checklist antes de entregar

- [ ] Todas as seções preenchidas, sem textos de instrução do template.
- [ ] Cada achado tem evidência legível, com o comando visível.
- [ ] Mínimo de 3 vulnerabilidades, do CVSS mais alto ao mais baixo.
- [ ] Cada técnica MITRE com ID e nome corretos.
- [ ] Recomendações específicas, com prazo.
- [ ] Sumário executivo em 1 página, sem jargão.
- [ ] Nenhuma senha ou dado pessoal real exposto.
