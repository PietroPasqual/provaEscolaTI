Especificação — Zona Azul Digital

1. Objetivo

Definir as funcionalidades da API, seguindo as regras do constitution.md.

2. Funcionalidades

UC1 — Abrir bilhete

POST /bilhetes
Receber placa válida e entrada opcional.
Retornar 201 com id, placa, entrada e status aberto.
Dados inválidos retornam 422 (placa_invalida ou entrada_invalida).

UC2 —  Encerrar bilhete

Cobra-se por fração de FRACAO_MINUTOS minutos, arredondando para cima (fração exata cobra 1 fração; 1 minuto a mais já cobra a fração seguinte);
hora cheia = TARIFA_HORA_CENTAVOS; valor da fração = tarifa ÷ (60 ÷ FRACAO_MINUTOS);
aplica-se o teto diário: valor_centavos nunca supera TETO_DIARIO_CENTAVOS;
valor sempre em centavos 

UC3 — Listar ativos

GET /bilhetes/ativos 
com array dos bilhetes abertos, mais recentes primeiro.

UC4 — Relatório diário

GET /relatorios/diario?data=AAAA-MM-DD 

tempo_medio_minutos considera apenas bilhetes encerrados no dia, arredondando 0,5 para cima.

UC5 — Cancelar bilhete

POST /bilhetes/{id}/cancelamento
com status: "cancelado". Só bilhetes abertos podem ser cancelados

UC6 — Histórico por placa

GET /bilhetes?placa=ABC1D23
com array de todos os bilhetes da placa (qualquer status), mais recentes primeiro.
Placa que nunca estacionou = array vazio.

UC7 — Tolerância gratuita

Os primeiros TOLERANCIA_MINUTOS de um bilhete são grátis.
Passou da tolerância (mesmo por 1 minuto) = cobra integral desde o primeiro minuto




UC8 — Uma vaga por placa
POST /bilhetes 
para placa que já tem bilhete aberto → 409 {"erro": "bilhete_em_aberto"}. Após encerrar ou cancelar, a placa volta a poder abrir.



