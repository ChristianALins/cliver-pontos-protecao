# DOCUMENTACAO DO SISTEMA - CLIVER PONTOS PROTECAO v3.0

## 1. VISAO GERAL
O **Programa de Pontos de Proteção** é um sistema completo de fidelização para clientes da CLIVER Corretora de Seguros. A versão 3.0 traz uma interface administrativa renovada, sistema de backup robusto e portal do cliente integrado via LocalStorage.

**Paridade:** 10 Pontos = R$ 1,00 de desconto.

## 2. ARQUIVOS DO SISTEMA
| Arquivo | Função |
|---|---|
| `index.html` | Sistema administrativo v3 (Gestão, Acúmulo, Resgate e Relatórios) |
| `portal_cliente.html` | Portal do Cliente v3 (Consulta de saldo e extrato por CPF) |
| `docs/DOCUMENTACAO.md` | Documentação técnica e funcional do sistema |

## 3. CHAVE DE ARMAZENAMENTO (CRÍTICO)
A chave mestre usada no LocalStorage é: `programaPontosProtecao_v1`
*Ambos os arquivos devem utilizar esta mesma chave para que os dados apareçam no portal.*

## 4. REGRAS DE PONTUACAO (ACÚMULO)
| Ação | Pontos | Equivalente R$ | Descrição |
|---|---|---|---|
| Renovação Antecipada | 500 | R$ 50,00 | 5 dias antes do vencimento |
| 2º Produto Contratado | 1.000 | R$ 100,00 | Venda adicional (Vida, Res, etc) |
| Indicação Efetivada | 1.500 | R$ 150,00 | Cliente novo indicado fechado |
| Aluno de Aula Habilitado | 200 | R$ 20,00 | Incentivo educacional |
| Valor Customizado | Variável | Variável | Campanhas especiais |

## 5. OPCOES DE RESGATE
- **Opção A (Ouro):** Desconto na renovação do seguro (redução de comissão).
- **Opção B (Serviço):** Voucher de aula ou consultoria (custo financeiro zero).
- **Opção C (Parceiros):** Voucher em estabelecimentos locais (Lava-rápido, oficinas).

## 6. NOVIDADES DA VERSÃO 3.0
- **Dashboard Estatístico:** Visualização em tempo real de pontos em circulação e taxa de resgate.
- **Relatórios Avançados:** Listagem de Top 10 clientes e pontos por tipo de ação.
- **Gestão de Dados:** Botões dedicados para Backup JSON e Exportação CSV (Excel).
- **Importação de Dados:** Possibilidade de restaurar o sistema a partir de um arquivo JSON.

## 7. CONFIGURACAO E USO
1. **Administração:** Use `index.html` para cadastrar clientes e lançar pontos.
2. **Persistência:** Os dados são salvos automaticamente no navegador ao confirmar ações.
3. **Portal:** O `portal_cliente.html` deve ser usado no mesmo navegador para localizar o saldo via CPF.

## 8. MANUTENÇÃO E BACKUP
- **Importante:** Como os dados são locais, se você limpar o cache do navegador, os dados serão perdidos.
- **Rotina:** Faça o "Backup JSON" toda sexta-feira e guarde no seu Google Drive.

---
*Documentação Versão 3.0 - Atualizada em 20 de Fevereiro de 2026*
*Para: CLIVER Corretora de Seguros*

