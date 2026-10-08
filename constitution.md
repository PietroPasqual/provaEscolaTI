Constituição do Projeto — Zona Azul Digital

1. Objetivo

Desenvolver uma API REST para gerenciamento de bilhetes de estacionamento rotativo.
A implementação deverá contemplar os oito casos de uso (UC1 a UC8), sem desenvolver funcionalidades fora do escopo.

2. Hierarquia das especificações

Os valores da variante do repositório devem ser respeitados.
Exemplos ilustrativos que contradigam o pedido deve ser ignorado.
Nenhuma decisão técnica pode alterar endpoints, códigos HTTP, nomes de campos ou regras de negócio.
Em situações não especificadas, priorizar soluções simples, determinísticas.

3. Parâmetros obrigatórios

A implementação utilizará os seguintes parâmetros da variante:

Parâmetro        |       Valor
TARIFA_HORA_CENTAVOS:     500

FRACAO_MINUTOS:           30

TETO_DIARIO_CENTAVOS:     5000

TOLERANCIA_MINUTOS:       15

PORTA_SERVICO:            8003
