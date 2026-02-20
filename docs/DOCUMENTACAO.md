# DOCUMENTACAO DO SISTEMA - CLIVER PONTOS PROTECAO v2.1

## 1. VISAO GERAL

O **Programa de Pontos de Proteção** e um sistema de fidelizacao para clientes da CLIVER Corretora de Seguros. Permite acumular e resgatar pontos por renovacoes, indicacoes e outros comportamentos desejados.

**Paridade:** 10 Pontos = R$ 1,00 de desconto.

## 2. ARQUIVOS DO SISTEMA

| Arquivo | Funcao |
|---|---|
| `index.html` | Sistema administrativo (uso do corretor) |
| `portal_cliente.html` | Consulta de saldo por CPF (uso do cliente) |
| `docs/DOCUMENTACAO.md` | Esta documentacao |

## 3. CHAVE DE ARMAZENAMENTO

A chave usada no LocalStorage e: `programaPontosProtecao_v1`

Ambos os arquivos (index.html e portal_cliente.html) devem usar exatamente esta chave.

## 4. REGRAS DE PONTUACAO

| Acao | Pontos | Equivalente R$ |
|---|---|---|
| Renovacao Antecipada (5 dias antes) | 500 | R$ 50,00 |
| 2 Produto Contratado | 1.000 | R$ 100,00 |
| Indicacao Efetivada | 1.500 | R$ 150,00 |
| Aluno de Aula Habilitado | 200 | R$ 20,00 |
| Valor Customizado | Variavel | - |

## 5. OPCOES DE RESGATE

- **Opcao A (Ouro):** Desconto na renovacao do seguro.
- **Opcao B (Servico):** Voucher de aula ou consultoria (custo zero para o corretor).
- **Opcao C (Parceiros):** Voucher em estabelecimentos locais parceiros.

## 6. MODELO DE DADOS (LocalStorage)

```json
{
  "clientes": [
    {
      "nome": "Joao Silva",
      "cpf": "12345678901",
      "seguro": "Automovel"
    }
  ],
  "movimentacoes": [
    {
      "cpf": "12345678901",
      "tipo": "renovacao",
      "pontos": 500,
      "data": "20/02/2026, 15:30:00"
    }
  ]
}
```

## 7. CONFIGURACAO INICIAL

1. Abra `index.html` no navegador Chrome/Edge/Firefox.
2. Cadastre os primeiros clientes na aba de cadastro.
3. Lance as movimentacoes de pontos conforme as acoes dos clientes.
4. Para o portal do cliente, abra `portal_cliente.html` no **mesmo navegador** (para acessar o mesmo LocalStorage).
5. O cliente digita o CPF e ve o saldo.

## 8. BACKUP E EXPORTACAO

- **Backup JSON:** Clique no botao 'Fazer Backup JSON' no sistema administrativo. Salve o arquivo em local seguro e suba no Google Drive periodicamente.
- **Exportacao CSV:** Clique em 'Exportar CSV' para abrir no Google Planilhas.

## 9. TROUBLESHOOTING

### Portal retorna 'Nenhum dado encontrado'
- Confirme que o index.html e o portal_cliente.html estao sendo abertos no **mesmo navegador**.
- Confirme que a chave no codigo e identica: `programaPontosProtecao_v1`.
- No DevTools (F12 > Application > LocalStorage), verifique se a chave existe.

### CPF nao encontrado no portal
- Confirme que o CPF foi cadastrado no sistema administrativo (index.html).
- CPF deve ser inserido apenas com numeros, sem pontos ou tracos.

## 10. FAQ

**Os dados sao salvos na nuvem?**
Nao. Os dados ficam no LocalStorage do navegador. Use a funcao de backup regularmente.

**Posso usar em varios computadores?**
Nao diretamente. Exporte o JSON e importe no outro computador. Uma futura versao podera integrar com Google Sheets ou AWS.

**O portal do cliente pode ser acessado publicamente?**
O portal usa o LocalStorage, que e local de cada navegador. Para acesso publico, sera necessario uma versao com backend (AWS/Google Sheets API).

---
*Documentacao versao 2.1 - Fevereiro 2026*
*CLIVER Corretora de Seguros*