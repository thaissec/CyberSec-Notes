# Análise de incidentes

## Estrutura de uma análise

1. **Identificação:** título do incidente e fonte da notícia.
2. **CIA:** para cada pilar, sim/não/parcialmente, com justificativa.
3. **Cadeia de ataque:** por quais fases passou e o que teria interrompido cada uma.
4. **MITRE:** pelo menos uma técnica com ID, nome, tática e mitigação.
5. **Conclusão em uma frase.**

> Exemplo de conclusão: "A confidencialidade foi comprometida via phishing (T1566). Um treinamento de conscientização teria reduzido o risco."

## Exemplo resolvido: caso do hospital (didático)

| Momento | O que aconteceu | Tática | Técnica |
|---|---|---|---|
| 1 | Funcionário recebe e-mail com link de "resultado de exame" e digita credenciais numa página falsa | Initial Access | T1566.002 |
| 2 | Credenciais usadas às 2h para entrar no sistema de prontuários | Persistence / Defense Evasion | T1078 |
| 3 | Dados de 80.000 pacientes compactados e enviados a servidor externo | Exfiltration | T1041 |

- **CIA:** confidencialidade comprometida. Integridade e disponibilidade intactas.
- **Onde a defesa podia agir:** treinamento contra phishing, MFA e alerta para acessos fora de horário.

## Exemplo resolvido: empresa fictícia de logística (LogBR)

Cenário: e-mail com "NF-48291.pdf" → macro executa e instala agente remoto → agente passa 3 dias mapeando a rede e coletando credenciais → atacante exfiltra 45 GB por HTTPS.

| Comportamento | ID | Técnica | Mitigação |
|---|---|---|---|
| E-mail com anexo malicioso | T1566.001 | Phishing: Spearphishing Attachment | Treinamento + filtro de anexos |
| Macro executa código | T1204.002 | User Execution: Malicious File | Desabilitar macros por GPO |
| Agente persiste no boot | T1547.001 | Registry Run Keys | Restringir escrita no registro + EDR |
| Dados saem por HTTPS | T1041 | Exfiltration Over C2 Channel | Monitorar tráfego de saída (DLP) |

**Ponto de falha:** a **Entrega**. Desabilitar macros e filtrar anexos com sandbox de e-mail teriam parado o ataque cedo.

## Seus próprios casos

Crie arquivos nesta pasta com o formato acima para cada incidente que analisar (por exemplo, `caso-nome-do-incidente.md`).
