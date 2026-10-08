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

Parâmetro               |  Valor
TARIFA_HORA_CENTAVOS:   |  500
FRACAO_MINUTOS:         |  30
TETO_DIARIO_CENTAVOS:   |  5000
TOLERANCIA_MINUTOS:     |  15
PORTA_SERVICO:          |  8003

Os parâmetros não poderão ser substituídos por valores ilustrativos ou padrões arbitrários.

4. Regras fundamentais

Todos os valores monetários devem ser representados em centavos inteiros.
A cobrança deve respeitar as frações de 30 minutos, a tolerância de 15 minutos e o teto de 5000 centavos.
Após ultrapassar a tolerância, a cobrança deve considerar o tempo integral.
Cada placa poderá possuir apenas um bilhete aberto por vez.
Somente bilhetes abertos poderão ser encerrados ou cancelados.
A API deverá funcionar na porta 8003.
