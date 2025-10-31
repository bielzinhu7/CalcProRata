# Calculadora de Pró-Rata — Alteração de Vencimento

Aplicação desenvolvida em HTML, CSS e JavaScript para calcular o valor de Pró-Rata em alterações de data de vencimento de planos.  
O sistema foi criado para auxiliar consultoras e equipes administrativas de academias e outros serviços recorrentes.

---

## Funcionalidades

- Cálculo automático de Pró-Rata proporcional conforme as regras internas.
- Alterações com diferença igual ou superior a seis dias geram cobrança proporcional.
- Adiantamentos dentro do mesmo ciclo não geram cobrança.
- Exibe o status da operação (permitido ou bloqueado).
- Mostra os dias considerados, valor de Pró-Rata e total ilustrativo.
- Formata automaticamente os valores em reais (R$).
- Mostra a data da próxima cobrança conforme o tipo de alteração.
- Interface responsiva com paleta roxa e amarela.

---

## Demonstração

![Tela da calculadora de pró-rata](https://i.imgur.com/Ma3PzvO.png)

O valor da Pró-Rata é cobrado junto à próxima mensalidade.

---

## Lógica de Negócio

| Situação | Regra Aplicada | Exemplo | Cobrança |
|-----------|----------------|----------|-----------|
| Postergar (novo vencimento maior) | Se a diferença for maior ou igual a 6 dias, cobra Pró-Rata | 10 → 22 | Sim |
| Adiantar (novo vencimento menor) | Próxima ocorrência (mês seguinte imediato) não cobra | 25 → 10 (10/11) | Não |
| Adiantar com pulo de ciclo | Aplicar apenas no mês subsequente, cobra Pró-Rata | 25 → 10 (10/12) | Sim |
| Parcelas em aberto | Alteração bloqueada | — | Não |

