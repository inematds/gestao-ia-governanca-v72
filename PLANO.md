# PLANO — G5 · Governar, medir e evoluir (v7.2)

Curso G5 da **Formação Gestão de IA 2027** (área https://eventos.inema.pro/gestao-ia/), o curso de **fechamento**, com o **projeto final no Gestoria**. Contrato: tabela G5 e seção 2 (rubrica de 8 itens) de `~/projetos/ia-2027/estrategia/CURRICULO-GESTAO-IA-2027.md`. Padrão aprovado: piloto G3 `gestao-ia-agentes-v72`; irmãos publicados G2 `gestao-ia-processos-v72` e G4 `gestao-ia-recursos-v72`. Competências da área: **5 Governança** ("o que ele faz sozinho, confirma, ou jamais executa? Permissões, identidade, credenciais, auditoria, logs e rastreabilidade"), **7 Avaliação** ("Está bom? Comparado a quê?") e **8 Evolução** ("O que aprendemos nesta execução?", o LOOP-R). Módulos 8, 9 e 10 da área + projeto final.

**Aluno:** gestor de área, dono de PME, líder de operações, RH. Não programa: governa, mede e melhora a operação.
**Caso condutor:** Horizonte Distribuidora (`https://inematds.github.io/prof2030-lab/`, empresa fictícia de estudo). O aluno é a **Patrícia Lima, gerente comercial**, responsável pela **Hora** (agente de vendas no WhatsApp). Colegas: Juliana (atendimento), Rafael (TI terceirizada), Carlos (dono). Novo neste curso: **Valdir (logística)**, fictício, dono da tabela de rotas (aulas 5 e 6).
**Gancho do curso:** no lab o Carlos quer ampliar a Hora para a cobrança olhando um painel sem linha de base (F11). A Patrícia pede que a decisão espere o pacote do G5: quem responde, o que está permitido e registrado, como se mede, e um ciclo de melhoria com volta. O projeto final é esse pacote. A aprovação pedagógica não autoriza a ampliação: quem decide é o Carlos.
**Falhas do lab como problemas de gestão:** F12 IA na sombra e "responsável: Rafael (TI)" no `agente-config.json` → agente sem dono do negócio (aula 1); F7 registro desligado "para economizar espaço" e F9 "aprovado por WhatsApp: 'pode ligar'" → identidade, concessão e registro (aula 2); F6/F5 → casos críticos do conjunto de avaliação (aula 3); F11 painel sem linha de base → os 5 indicadores do agente (aula 4).
**Prática dupla:** e1 na Horizonte (treino), e2 no processo do próprio aluno (para valer).
**Riscos e LGPD não se repetem:** a aula 2 aponta para `https://inematds.github.io/prof2030-base/aulas/riscos/` e `/aulas/dados-lgpd/` (200 em 19/10/2026); a aula 7 aponta para `/aulas/regras/`.

## Fontes (não alteradas)
- Cadernos `~/projetos/arquiteto-agentes-contabil` ("quem lança não aprova, o agente nunca transmite nem paga"), `-advocacia` ("o agente lê, conta, prepara e resume; o advogado decide, assina e protocola"), `-saude` ("dados de paciente fora do alcance"); área §02 ("O limite é uma decisão de gestão, tomada antes de ligar o agente").
- `~/projetos/curso-gestao-ia/planejamento/PLANO-CURSO.md` mód. 5–6 (credencial no servidor, escopo mínimo, evidência da ação; política não depende só do prompt), 8, 9 (9.1–9.5: conjunto representativo, gabarito, rubrica; correto/aceitável/incorreto/crítico; versões, regressões, treino × teste; acerto, autonomia, intervenção, tempo), 10 (LOOP-R: feedback não altera produção; teste antes da validação; humano autoriza promoção; versão anterior identificada) e projeto final (rubrica 100 pontos, obrigatórios). `METODO.md` (contratos de avaliação e de mudança, indicadores com denominador, LOOP-R, rituais). `TEMPLATES.md` (6 caso de avaliação, 8 experimento LOOP-R, 10 revisão semanal).
- `~/projetos/loop-r`: README, guia, `docs/05-medicao-evals-guardrails.md` (3 tipos de métrica, guarda-corpos, tolerância de evento raro = 2 erros-padrão, amostra mínima, rubrica sim/não, calibração ≥ 80%, força FORTE/MODERADA/FRACA, rollback no 1º ciclo após promoção, cartão de 5 linhas, L0/L1/L2), `docs/04-agentes.md` (9 assistentes), `exemplos/vendas-whatsapp` (4 ciclos: amostra insuficiente, descarte por guarda-corpo, promoção). Vídeos t1–t3.
- `~/projetos/gestoria`: README (roteiro de 8 passos, limites do MVP), guia, `src/domain.ts` (métricas, `promotionCheck`: 100 casos da versão atual, meta, zero crítico, sem pendência; estágios Proposta → Em teste → Validada → Promovida).
- `~/projetos/inemaeventos/gestao-ia/index.html` §02, §04 (competências 5, 7, 8), §05 (LOOP-R e regra 3), §06 (indicadores), §07 (projeto final: os passos do Gestoria).
- `~/projetos/prof2030-lab`: `pecas/agente-whatsapp/agente-config.json`, `pecas/mcp-email/mcp.json`, `pecas/painel/indicadores.json`, `inventario.html`, `gabarito.html`.
- Mercado: `mercado-gestao-ia-2026-10.md` e `mercado-ia-2026-10.md` (só fatos sem [incerto]; Sinch fora; um fato por aula; painel completo na aula 8).

## Política fictícia da Horizonte (reusada do G3; sempre rotulada)
- Tabela: detergente neutro 5 L R$ 38,90; desinfetante lavanda 5 L R$ 42,50. Caixa = 6 galões.
- Desconto: até 5% a Hora concede sozinha a cliente cadastrado; 5% a 10% a Patrícia aprova; acima de 10% a Hora não oferece (Carlos, se a Patrícia levar).
- Pedido acima de R$ 5 mil: aprovação da Patrícia antes de separar. Níveis 0–4 do METODO.
- Nunca pela Hora: marcar como pago, mudar preço, cadastrar cliente novo, apagar conversa. Registro de toda ação.
- Números do G4 que este curso reusa: mês de referência com **3.600 conversas** e **680 pedidos concluídos**; custo do processo R$ 4.542 → **R$ 6,68 por pedido concluído**; horas de gente D+E+F = 9 + 30 + 10,8 = **49,8 h/mês**.

## Versões da Hora neste curso (fictícias; semanas relativas, não datas)
- **v2.0** — a do dossiê do G3.
- **v2.1** — v2.0 + trava na ferramenta: soma dos pedidos do mesmo cliente no mesmo dia acima de R$ 5 mil vai para aprovação (corrige o caso crítico T-27 da aula 3).
- **v2.2** — v2.1 + tabela de rotas e dias de entrega por cidade no pacote de contexto (candidata do ciclo LOOP-R da aula 5; promovida e depois revertida na aula 6).
- **v2.3** — v2.2 com a tabela com dono, validade e aviso de mudança de rota (candidata seguinte; fica proposta).
- Linha do tempo relativa: semanas 1–4 = linha de base da v2.1 (aula 4); semanas 5–6 = piloto A/B v2.1 × v2.2 (aula 5); semana 7 = promoção da v2.2; semana 8 = reversão para a v2.1 (aula 6).

## Números da Horizonte (G5) — conferidos à mão

**Aula 3 · conjunto de avaliação (30 casos, partição de teste reservada):** 12 rotina, 6 fronteira, 4 dados insuficientes, 4 conflito, 4 risco crítico = 30. Rubrica sim/não R1–R7; R3, R4, R5 são invariáveis.
- Hora v2.0: 21 corretos, 4 aceitáveis, 4 incorretos, **1 crítico** = 30. Acerto estrito 21/30 = **70,0%**; aproveitável (21+4)/30 = **83,3%**.
  - Crítico T-27: cliente pede para dividir R$ 5.320 em dois pedidos de R$ 2.660 "para sair hoje"; a Hora dividiu e escapou da aprovação (R3 = não).
  - Incorretos: T-09 prazo para Campinas errado (R2); T-14 caixa × galão (R1); T-19 prometeu entrega numa cidade fora da rota do dia (R2); T-22 cliente sem CNPJ, a Hora usou o CNPJ de um cadastro antigo parecido (R6).
- Hora v2.1: T-27 vira correto → 22 corretos, 4 aceitáveis, 4 incorretos, 0 crítico = 30. Nenhum caso piorou (regressão = 0).
- Calibração: Patrícia e Juliana classificam os mesmos 10 resultados sem combinar: concordam em 9 → **90%** (≥ 80%, regra do LOOP-R).
- Comparação com o G4: os 20 casos de lá eram exploratórios para escolher modelo (A: 16/3/1/0); aqui o conjunto vira permanente, com categorias, partição reservada e rubrica. Os 100 casos com 95% e zero crítico são o limiar didático da ferramenta Gestoria para promover nível, não o tamanho deste conjunto.

**Aula 4 · os 5 indicadores do agente (linha de base = semanas 1–4, Hora v2.1; 3.600 conversas, 680 pedidos concluídos):**

| # | Indicador | Fração | Hoje (observado) | Limite / ação | Dono |
|---|---|---|---|---|---|
| 1 | Qualidade: acerto estrito na amostra | corretas ÷ conversas julgadas (40 sorteadas por semana) | 148 ÷ 160 = **92,5%** · erros críticos **0** (contados à parte) | < 90% numa semana: amostra dobra e causa vai para a revisão semanal · 1 crítico: ação volta ao amarelo na hora + incidente | Patrícia |
| 2 | Tempo de ciclo | mediana e p95 de (pedido confirmado − 1ª mensagem), pedidos concluídos | mediana **18 min**, p95 **4 h 40 min** | p95 > 6 h: olhar a fila de aprovação | Patrícia |
| 3 | Custo por resultado | custo total do processo ÷ pedidos concluídos | 4.542 ÷ 680 = **R$ 6,68** | > R$ 7,50 no mês: revisar (G4: a configuração barata deu R$ 7,51) | Patrícia, com Rafael |
| 4 | Autonomia | pedidos concluídos sem nenhuma intervenção humana ÷ pedidos concluídos | 510 ÷ 680 = **75,0%** | sem meta sozinha: só vale com o 1 e o crítico estáveis | Patrícia |
| 5 | Intervenção humana | minutos de gente (revisão + conversas assumidas + retrabalho) ÷ pedidos concluídos | 49,8 h × 60 = 2.988 min ÷ 680 = **4,4 min** | > 6 min: ver onde as horas foram | Juliana |

O painel do lab (F11) tem 4 colunas: atendimentos (volume, não resultado), pedidos fechados (sem o antes), satisfação média (~6% respondem), tempo de resposta em segundos (velocidade da 1ª resposta, não do pedido). Pedidos ÷ atendimentos caiu de 20,1% (141/702) para 18,6% (168/901): já calculado no G2, citado aqui só como lembrete.

**Aula 5 · ciclo LOOP-R (v2.1 → v2.2):**
- Observar (semanas 1–4): 640 das 3.600 conversas tiveram dúvida de prazo ou rota; a Juliana assumiu 288 → **45,0%**. N = 640 ≥ 90 → evidência FORTE (régua do LOOP-R). Nos 30 casos, 2 dos 4 incorretos são de prazo/rota.
- Criticar: causa provável = a Hora não tem a tabela de rotas por cidade e dia; responde prazo com o texto genérico do pacote.
- Propor: **SE** a tabela de rotas e dias de entrega por cidade (dono: Valdir, logística) entrar no pacote de contexto, **ENTÃO** as conversas de prazo assumidas pela Juliana caem de 45% para 25% ou menos, **PORQUE** a Hora passa a responder rota e dia pela fonte. **Sem piorar:** promessas de prazo não cumpridas (guarda-corpo), erros críticos = 0, custo de IA por conversa até R$ 0,35. Vetada pelo guardião (invariável de preço): "oferecer frete grátis para fechar".
- Amostra mínima (fórmula de duas proporções, 95% de confiança, poder 80%, a do LOOP-R): 45% → 25% pede ≈ **89 conversas de prazo por variante**. Conta: p̄ = 0,35; 1,96·√(2·0,35·0,65) = 1,322; 0,8416·√(0,2475+0,1875) = 0,555; (1,877)² = 3,524; ÷ 0,04 = 88,1 → 89.
- Experimentar: primeiro os 30 casos (v2.2: T-09 e T-19 viram corretos → 24 corretos, 4 aceitáveis, 2 incorretos, 0 crítico; nenhum piorou). Depois piloto de 2 semanas (semanas 5–6), dias alternados (pares v2.1 = A, ímpares v2.2 = B).
- Resultado: conversas de prazo A 330, B 326. Assumidas: A 148/330 = **44,8%**; B 59/326 = **18,1%**. Guarda-corpo: promessas não cumpridas A 4/330 = **1,2%**; B 5/326 = **1,5%**. Tolerância escrita antes = 2 erros-padrão da taxa-base na amostra planejada: 2·√(0,012·0,988/330) = 2·0,0060 = **1,2 ponto** → limite 2,4%; B 1,5% dentro. Críticos 0 e 0. Custo de IA por conversa R$ 0,31 → **R$ 0,33** (contexto maior), dentro do teto.
- Validar: "B ganhou" (métrica melhorou com N acima do mínimo, guarda-corpos dentro, 30 casos sem regressão).
- Promover: proposta da Patrícia (a observação veio da Juliana); aprova o Carlos (quem propõe não aprova). Nível do loop = L1 (pessoa aprova cada mudança).

**Aula 6 · promoção e reversão (v2.2 → v2.1):**
- Semana 7: v2.2 promovida para todas as conversas. Janela de vigia = as duas primeiras semanas depois da promoção.
- Gatilho de reversão escrito na promoção: promessas de prazo não cumpridas acima de **3,4%** numa semana. Conta: taxa do piloto B 1,5% + 2 erros-padrão numa semana de ~160 conversas de prazo: 2·√(0,015·0,985/160) = 2·0,0096 = 1,9 ponto → 3,4%. Ou 1 erro crítico.
- Semana 8: a logística mudou o dia de entrega da rota de Sorocaba e a tabela não foi atualizada. Conversas de prazo 158; promessas não cumpridas **7/158 = 4,4%** (> 3,4%). Assumidas pela Juliana continuaram baixas: 30/158 = 19,0%.
- Reversão: decidida pela Patrícia pelo gatilho escrito (reverter não espera aprovação; promover espera); o Rafael aponta a Hora para a v2.1 em até 2 h; a Juliana é avisada antes; a v2.2 fica guardada. Carlos informado com o número.
- Depois: causa = documento sem validade nem aviso de mudança de rota → v2.3 (dono Valdir, validade semanal, aviso de mudança) volta aos 30 casos e a um piloto novo. Ledger com as 4 linhas (v2.0, v2.1, v2.2 promovida e revertida, v2.3 proposta).
- Contraexemplo do LOOP-R (exemplo vendas-whatsapp, ciclo 0002): 6 × 1 reclamações em 300 por variante com tolerância 0 é ruído (p ≈ 0,12), não piora; por isso a tolerância é calculada antes.

## As 8 aulas

| # | slug | aula | objetivo (≤160) | diagrama | prática ("pronto quando") | extra |
|---|---|---|---|---|---|---|
| 1 | `responsaveis` | Quem responde pelo agente | nomear, ação por ação, quem executa, quem responde, quem é consultado e quem é informado, sem que quem lança aprove | matriz RACI em 5 nós: executa (R) → responde (A) → consultado (C) → informado (I) → substituto | e1 RACI da operação da Horizonte (≥ 10 linhas, 3 agentes, um A por linha, nenhum executor aprovando a própria ação, nenhum agente nem TI como A de resultado); e2 RACI do seu processo | McKinsey: "accountability by design" (moldura de consultoria, 2025–2026) |
| 2 | `permissoes` | Permissões, identidade e registro | garantir que cada ação do agente tenha identidade própria, permissão concedida por escrito e registro que diga quem, quando, o quê e com que versão | fluxo identidade → permissão → registro → revisão (volta mensal) | e1 checklist de 10 itens aplicado à Hora com a evidência de cada um (lab) e a linha de registro do pedido do hotel; e2 checklist do seu agente + revisão de acessos marcada | Okta 2026 (identidade de agente; controles mais fracos); riscos e LGPD → prof2030-base |
| 3 | `evals` | Evals: está bom comparado a quê? | montar um conjunto de 30 casos com gabarito e rubrica que separe correto, aceitável, incorreto e crítico, e rodá-lo a cada mudança | rolagem guiada: casos → gabarito → rubrica → classe → comparar versões | e1 conjunto da Hora (30 casos nas 5 categorias, gabarito e rubrica) e classificar 4 resultados; e2 30 casos do seu processo, rodados na versão atual, com calibração entre 2 pessoas | — |
| 4 | `indicadores` | Os indicadores do agente | acompanhar o agente num painel de 5 indicadores com numerador, denominador, linha de base e limite, corrigindo o painel que só mostra volume | 5 nós: qualidade, tempo, custo, autonomia, intervenção (+ erro crítico à parte) | e1 painel da Hora (5 fichas) + o que cada coluna do painel do lab não mostra; e2 painel do seu agente com 4 semanas de linha de base marcadas | Microsoft WTI 2025: human-agent ratio |
| 5 | `loop-r` | LOOP-R: o processo que aprende | rodar um ciclo LOOP-R completo, de executar a promover, com hipótese, teste comparado à linha de base e decisão de quem não propôs | ciclo de 7 nós (executar … promover) + volta "repetir" | e1 registro do ciclo v2.1 → v2.2 com os 7 passos; e2 1 ciclo completo no seu processo | vídeos `loop-r` t2 (principal), t1 e t3 (para ir além) |
| 6 | `promover-reverter` | Promover e reverter | tratar promoção e reversão como etapas planejadas: promover em fases com gatilho de volta escrito e reverter pelo gatilho, sem caça ao culpado | escada: validada → promovida com vigia → gatilho → mantém ou reverte → causa e nova candidata | e1 registro de 1 promoção e 1 reversão da Horizonte + ledger; e2 promoção com gatilho e reversão ensaiada (tempo medido); e3 simconversa com placar máximo | **simconversa** (o Carlos não quer voltar) |
| 7 | `regras` | Regras que chegam | montar a linha do tempo de conformidade da sua área: o que já vale, o que tem data, o que está em discussão e quem cuida de cada item | 4 nós: já vale → com data → em discussão → chega pelo cliente | e1 linha do tempo da Horizonte (≥ 6 itens, status, fonte com data, dono, revisão; nenhum incerto como fato); e2 a da sua área | EU AI Act: alto risco do Anexo III → 02/12/2027 (Digital Omnibus, 24/07/2026); letramento já vale; PL 2338 só como "noticiado parado, fonte secundária" |
| 8 | `projeto-final` | Projeto final no Gestoria + O que mudou | administrar uma operação de ponta a ponta nos 14 passos do Gestoria e aprovar o relatório final pela rubrica de 8 itens da formação | 6 fases com os 14 passos (entender, redesenhar, dividir, equipar, operar, evoluir) + volta | e1 relatório da Horizonte no Gestoria (JSON exportado + 14 passos + rubrica ≥ 75 com os 7 obrigatórios); e2 relatório do seu processo assinado por outra pessoa; e3 plano datado | "O que mudou" (governança, incidentes, regras, certificações), ponte para o Prof 2030 com o vídeo `consultor-ia-2027` (opcional), seção "Certificação", `mapa` (4 degraus) + `gerador` |

Rodapé da aula 8 (seção `texto` "Certificação"): "Certificação INEMA de qualificação 'Gestor de IA', em breve no cert.inema.pro. Não é certificação profissional regulada."

## Os 14 passos do Gestoria (aula 8)

A área §07 lista os passos separados por "·" e diz "catorze passos"; o texto tem 13 itens. **Decisão:** separar "definir tarefas humanas e tarefas de agentes" em dois (5 = tarefas humanas, 6 = tarefas de agentes), o que casa com G1 (pessoas) e G3 (agentes). A ferramenta não gera relatório: ela guarda processo, cargos, execuções, decisões, avaliações e melhorias e exporta JSON. O **relatório final é um modelo do curso** (bloco `codigo`), preenchido com os 14 passos e com o JSON em anexo.

| # | passo | onde no Gestoria | curso |
|---|---|---|---|
| 1 | compreender o objetivo | Processos: objetivo, responsável, meta | G0/G2 |
| 2 | analisar o processo existente | Processos: etapas, volume, tempo atual | G2 |
| 3 | eliminar etapas | relatório (a ferramenta guarda só a lista final) | G2 |
| 4 | redesenhar o fluxo | Processos: etapas da versão nova | G2 |
| 5 | definir tarefas humanas | relatório | G1 |
| 6 | definir tarefas de agentes | Força de trabalho: missão, recebe, entrega | G3 |
| 7 | escolher ferramentas e modelos | Força de trabalho: modelo planejado, ferramentas, Skills, contexto | G4 |
| 8 | definir permissões | Força de trabalho: pode, não pode, autonomia inicial | G3/G5 |
| 9 | estabelecer custos | Processos: custo por hora, orçamento | G4 |
| 10 | definir métricas | Processos: meta + painel de 5 indicadores | G5 |
| 11 | executar | Visão geral: simular rotina, dados conflitantes, fora da política | G5 |
| 12 | observar | Decisões humanas (aprovar ou devolver com justificativa) + indicadores | G3/G5 |
| 13 | avaliar | Avaliações: esperado, produzido, classificação | G5 |
| 14 | melhorar com o LOOP-R | Melhoria contínua: Proposta → Em teste → Validada → Promovida, com evidência | G5 |

Limites do Gestoria que o curso diz: MVP local, sem modelo real nem integração; cada simulação usa R$ 0,38 e 42 s didáticos; promover um nível do agente exige 100 avaliações da versão atual (o projeto não exige isso); não existe estágio "revertida" na Melhoria contínua: a reversão vai no relatório e o agente pode ser pausado.

## Rubrica final (aula 8) — 8 itens do currículo §2, 100 pontos

| item | origem | pontos | ponto cheio |
|---|---|---|---|
| 1 Processo e resultado | G2 | 15 | nome com começo e fim; dono e substituto; gatilho e conclusão; resultado para a empresa; linha de base marcada (bloco 1 + 5 da rubrica do G2) |
| 2 Etapas cortadas antes de automatizar | G2 | 10 | cada etapa eliminada ou movida com motivo e nova fonte; exigências reais mantidas (bloco 3 do G2) |
| 3 Agentes | G3 | 15 | cargo com missão, entrega verificável, proibidos e responsável; delegação; constituição de uma página; matriz com cor por ação e aprovação com conteúdo e prazo |
| 4 Pessoas | G1 | 10 | o que fica com as pessoas, por tarefa; conversa com a equipe feita ou marcada; formação de quem supervisiona; avaliação de quem trabalha com agentes (critério escrito a partir da tabela G1 do currículo: o G1 ainda não estava publicado) |
| 5 Recursos | G4 | 10 | modelo escolhido por casos com crítico separado; contexto com dono; ferramentas com acesso mínimo; custo por resultado e teto mensal |
| 6 Governança | G5 | 15 | RACI por ação com um A; identidade própria e checklist de 10 itens; registro que responde às 5 perguntas; revisão de acessos e desligamento; linha do tempo de conformidade |
| 7 Medida | G5 | 15 | 30 casos com gabarito, rubrica e 4 classes; 5 indicadores com numerador, denominador, linha de base, limite e dono |
| 8 Um ciclo LOOP-R | G5 | 10 | os 7 passos registrados; hipótese com guarda-corpo e tolerância; comparação com a linha de base; decisão de quem não propôs; promoção ou reversão com critério |

Aprova com **75 ou mais E os 7 obrigatórios** (um faltando reprova): dono do processo e responsável de cada agente com nome; linha de base observada ou marcada como hipótese, com indicador com denominador; nada irreversível no verde e teto em número onde há valor; quem lança não aprova (nenhuma linha com executor = aprovador; relatório assinado por outra pessoa); erros críticos contados à parte; reversão com gatilho em número e versão anterior identificada; dados fictícios ou anonimizados identificados.

## A simconversa da aula 6 — "o Carlos não quer voltar"

Personagem: **Carlos · dono da Horizonte (simulação)**. Estrutura linear; só a opção fraca de cada fala tem atalho para um fim ruim. Melhor caminho = 2 + 2 + 2 + 2 = **8**.

| fala | o Carlos diz | opções (nota → destino) |
|---|---|---|
| `abre` | soube que a Patrícia quer voltar à versão antiga; as conversas de prazo assumidas pela Juliana caíram de 45% para 18% | manter e pedir à logística que avise (0 → `fim-mantem`) · "recebi duas reclamações ontem" (1 → `criterio`) · o gatilho escrito antes de promover disparou: 4,4% (7 de 158) contra limite de 3,4%; a meta melhorou, o guarda-corpo caiu (2 → `criterio`) |
| `criterio` | "7 em 158 é pouco; não é azar?" | esperar mais um mês (0 → `fim-espera`) · "prefiro não arriscar" (1 → `como`) · o limite já considera a variação de uma semana de ~160 conversas; 7 passa dele; para o cliente sem entrega não é azar (2 → `como`) |
| `como` | "voltar não vai bagunçar tudo? a Juliana volta a ficar sobrecarregada" | desligar a Hora hoje até achar a causa (0 → `fim-desliga`) · voltar só nas cidades com reclamação (1 → `causa`) · passo escrito: Rafael aponta para a v2.1 em até 2 h, Juliana avisada antes, v2.2 guardada; a carga da Juliana volta à conhecida (2 → `causa`) |
| `causa` | "e a ideia da tabela de rotas morre aí?" | "morre, foi erro tentar" (0 → `fim-desiste`) · Rafael corrige a tabela e promovemos amanhã (1 → `fim-pressa`) · causa provável = tabela sem dono atualizado (Sorocaba mudou de dia); dono, validade e aviso, 30 casos e piloto de novo, cartão para você (2 → `fim-bom`) |

Somas: `fim-mantem` 0; `fim-espera` ≤ 2; `fim-desliga` ≤ 4; `fim-desiste` ≤ 6; `fim-pressa` ≤ 7; `fim-bom` = 8 (máximo, único caminho). Nenhum desvio soma fala extra.

## Decisões
- **simfila:** não entra. Nenhuma aula ensina fila com interromper e retomar; a decisão de reverter é conversa com critério (simconversa na aula 6).
- **Vídeos:** `loop-r` t2 ("O método") é o principal da aula 5; t1 e t3 entram na mesma aula como opcionais (os três têm ~17 min). `consultor-ia-2027` só na ponte da aula 8, opcional. EN/ES declarados em `idiomas` (MP4 `-en-en`/`-es-es` no loop-r; `-en`/`-es` no consultor). Pôster = quadro extraído do próprio vídeo por idioma.
- **Duas leituras do LOOP-R:** a área usa o ciclo executar → observar → criticar → propor → experimentar → validar → promover → repetir (é o que o curso ensina); o curso e os vídeos do LOOP-R resumem o mesmo ciclo em cinco letras (Localizar, Operar, Observar, Propor, Reforçar) com 9 assistentes. A aula 5 diz isso num parágrafo.
- **Aula 2 não repete G3/G4:** a cor de cada ação é do G3 (aula 4) e o contrato de cada ferramenta é do G4 (aula 4). O G5 confere, como gestor, que identidade, concessão, registro e revisão existem e continuam existindo.
- **Aula 4 não refaz o F11 do G2:** lá, 3 indicadores do processo; aqui, 5 do agente (os nomes casam com os da Visão geral do Gestoria: acerto, erros críticos, trabalho autônomo, custo por caso).
- **Aula 7 com um fato:** a data do alto risco do EU AI Act. "Letramento já vale" sem data (o arquivo de mercado não a dá); o detalhe fica em `prof2030-base/aulas/regras/`. PL 2338: "noticiado como parado na Câmara, fonte secundária; confira a ficha oficial".
- **Datas:** casos e resultados do G5 em semanas relativas, depois dos incidentes do lab (14/10) e dos casos do G2 (15–17/10/2026).
- **Valdir (logística):** personagem novo e fictício, porque a tabela de rotas precisa de um dono que não seja a Patrícia.
- **Capa sem texto** (instrução do brief, como no G3).
- `lado_card` aponta para o G0 (`gestao-ia-base-v72`, ainda não publicado em 19/10/2026: 404 esperado no `validar --links`). O G1 (`gestao-ia-pessoas-v72`) também dá 404 por enquanto.
