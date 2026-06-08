# Mission Control IA — Módulo de Energia Sustentável

Sistema de monitoramento energético para uma missão espacial experimental, com foco em geração solar simulada, consumo dos módulos, saldo energético, autonomia da bateria e tomada de decisão operacional.

---

## Informações da entrega

**Nome da missão:** Artemis Deep Scan  

**Vídeo não listado no YouTube:** 

---

## Integrantes

- Caio César Portela França — RM: 573127
- Gustavo Curis de Francisco — RM: 569704
- Tiago Pimentel Muniz — RM: 574148

---

## Visão geral

O **Mission Control IA** é uma central de monitoramento de missão espacial experimental.

O sistema acompanha dados simulados da missão, interpreta condições operacionais, gera alertas e apresenta recomendações de tomada de decisão.

Nesta entrega, o foco principal está no módulo **Energia Sustentável**, responsável por analisar geração solar, consumo energético, autonomia da bateria e priorização de cargas operacionais.

---

## Objetivo

Monitorar o sistema energético de uma missão espacial experimental, analisando:

- geração solar simulada;
- consumo total dos módulos;
- consumo por carga operacional;
- saldo energético;
- autonomia estimada da bateria;
- modo energético da missão;
- priorização de cargas essenciais e não essenciais;
- alertas em situações de atenção ou emergência.

A proposta é apoiar decisões operacionais durante a missão, indicando quando a energia disponível é suficiente e quando é necessário reduzir cargas para preservar sistemas críticos.

---

## Problema abordado

Missões espaciais dependem de energia limitada e precisam equilibrar geração, armazenamento e consumo.

Quando o consumo dos módulos ultrapassa a geração disponível, a missão pode perder autonomia e comprometer sistemas essenciais, como:

- suporte de oxigênio;
- comunicação com a base;
- estabilidade operacional;
- controle térmico.

O módulo de Energia Sustentável identifica esses riscos e recomenda ações básicas de conservação energética.

---

## Solução desenvolvida

A solução analisa dados simulados da missão e calcula indicadores energéticos a cada atualização.

O sistema possui duas formas de visualização:

1. **Sistema integrado com interface gráfica**  
   Demonstra o monitoramento completo da missão, com destaque para a aba **Energia Sustentável**.

2. **Módulo individual em terminal**  
   Executa a lógica energética em formato textual, permitindo validar o módulo separadamente.

---

## Principais funcionalidades

- Monitoramento da bateria da missão.
- Cálculo de geração solar simulada.
- Cálculo do consumo total dos módulos.
- Cálculo de saldo energético.
- Estimativa de autonomia da bateria.
- Classificação do estado energético.
- Definição automática do modo energético.
- Priorização de cargas essenciais.
- Recomendação de redução de cargas secundárias.
- Alertas em cenários de atenção ou emergência.
- Visualização dos dados em cards, gráficos, tabelas e relatório.

---

## Conceitos aplicados

O módulo aplica conceitos relacionados a:

- energia armazenada em bateria;
- potência elétrica em watts;
- geração solar simulada;
- consumo energético por módulo;
- saldo energético;
- autonomia operacional;
- eficiência energética;
- sustentabilidade em sistemas espaciais;
- tomada de decisão baseada em dados.

---

## Indicadores monitorados

| Indicador | Descrição |
|---|---|
| Bateria atual | Percentual de energia armazenada na missão |
| Geração solar | Energia gerada por fonte renovável simulada |
| Consumo total | Soma do consumo dos módulos operacionais |
| Saldo energético | Diferença entre geração solar e consumo |
| Autonomia | Tempo estimado de operação com a bateria disponível |
| Modo energético | Estado operacional definido pelo sistema |
| Painel de cargas | Indicação de quais cargas manter ou reduzir |

---

## Regras de decisão energética

O sistema classifica o estado energético com base na bateria e no saldo energético.

### Estado Normal

Condição geral:

- bateria em nível seguro;
- saldo energético positivo ou estável.

Ação recomendada:

- manter operação nominal;
- armazenar excedente solar;
- continuar monitoramento preventivo.

### Estado de Atenção

Condição geral:

- bateria abaixo do ideal; ou
- consumo maior que geração.

Ação recomendada:

- reduzir consumo secundário;
- monitorar autonomia;
- evitar expansão de cargas experimentais.

### Estado Crítico

Condição geral:

- bateria em nível crítico;
- saldo energético negativo.

Ação recomendada:

- reduzir cargas não essenciais;
- preservar suporte de oxigênio, comunicação e estabilidade;
- direcionar energia disponível para recuperação da bateria.

---

## Priorização de cargas

O sistema separa as cargas da missão em essenciais e não essenciais.

| Carga | Prioridade | Decisão esperada |
|---|---|---|
| Suporte de oxigênio | Essencial | Manter ativa |
| Comunicação com a base | Essencial | Manter ativa |
| Estabilidade operacional | Essencial | Manter ativa ou reduzir parcialmente em caso crítico |
| Controle térmico | Essencial | Manter ativa |
| Pesquisa / carga experimental | Não essencial | Reduzir em atenção ou emergência |

Essa lógica permite preservar os sistemas mais importantes antes de manter cargas secundárias.

---

## Uso de Inteligência Artificial

O sistema utiliza IA como camada de apoio à interpretação operacional da missão.

O modelo configurado é:

```text
llama3.2:1b
```

Executado localmente via:

```text
Ollama
```

A IA pode ser usada para:

- interpretar o estado atual da missão;
- analisar contexto de telemetria;
- apoiar recomendações operacionais;
- complementar o relatório final;
- explicar riscos e prioridades em linguagem natural.

A IA não substitui os cálculos determinísticos do sistema. Os cálculos de risco, energia, saldo, autonomia e alertas continuam sendo feitos pelo Python.

---

## Configuração da IA com Ollama

O sistema também funciona sem IA, usando regras internas.  
Para utilizar a geração/análise com IA local, é necessário instalar o **Ollama** e baixar o modelo usado no projeto.

### 1. Instalar o Ollama

Instale o Ollama conforme o sistema operacional utilizado.

Após instalar, verifique no terminal:

```bash
ollama --version
```

Se o terminal retornar a versão instalada, o Ollama está pronto para uso.

### 2. Baixar o modelo

O modelo usado pelo projeto é:

```text
llama3.2:1b
```

Baixe o modelo com:

```bash
ollama pull llama3.2:1b
```

Também é possível baixar e testar diretamente com:

```bash
ollama run llama3.2:1b
```

### 3. Iniciar o servidor local do Ollama

Antes de executar o sistema integrado com IA, abra um terminal separado e rode:

```bash
ollama serve
```

Mantenha esse terminal aberto durante o uso do sistema.

Se aparecer uma mensagem informando que a porta já está em uso, provavelmente o Ollama já está rodando em segundo plano.

### 4. Testar o modelo

Em outro terminal, execute:

```bash
ollama run llama3.2:1b
```

Digite uma mensagem simples, por exemplo:

```text
Responda apenas: modelo funcionando
```

Se o modelo responder, a IA está pronta para ser usada no Mission Control IA.

### 5. Aquecer o modelo antes da apresentação

Para reduzir o atraso na primeira resposta, é recomendado executar:

```bash
ollama run llama3.2:1b "Responda apenas: pronto"
```

Depois disso, mantenha o Ollama ativo e execute o sistema.

### 6. Fallback

Se o Ollama não estiver rodando ou o modelo não responder, o sistema continua funcionando com regras internas e fallback determinístico.

---

## Como executar o sistema integrado

Na raiz do projeto, execute:

```bash
python main.py
```

Depois:

1. Configure a missão na tela inicial.
2. Clique em **Iniciar missão**.
3. Acesse a aba **Energia Sustentável**.
4. Acompanhe geração solar, consumo, saldo energético, autonomia e decisão energética.

---

## Como executar o módulo individual em terminal

Execute:

```bash
python entregas_materias/energias_sustentaveis/energy_monitor.py
```

Esse arquivo apresenta no terminal:

- análise energética por ciclo;
- geração solar;
- consumo total;
- saldo energético;
- autonomia;
- painel de cargas;
- recomendações;
- relatório energético consolidado.

---

## Módulo de energia no sistema integrado

No sistema integrado, o motor energético é responsável por calcular:

- consumo total;
- saldo energético;
- autonomia;
- status energético;
- modo energético;
- recomendações;
- painel de cargas.

A interface gráfica exibe esses dados na aba **Energia Sustentável**, permitindo acompanhar a evolução da missão por meio de cards, gráficos e tabelas.

---

## Visualização dos dados

A interface gráfica apresenta:

- cards com indicadores principais;
- gráficos de geração solar;
- gráfico de consumo total;
- gráfico de autonomia;
- tabela de cargas;
- painel de decisão energética;
- alertas e recomendações.

Essa visualização facilita a leitura rápida do estado energético da missão.

---

## Relação com sustentabilidade

A solução utiliza geração solar simulada como fonte renovável principal da missão.

O sistema busca preservar energia e aumentar a eficiência operacional por meio de:

- monitoramento do saldo energético;
- redução de cargas não essenciais;
- priorização de sistemas críticos;
- uso estratégico da energia solar disponível;
- recomendações de conservação energética.

---

## Tecnologias utilizadas

- Python
- Tkinter
- Ollama
- Llama 3.2 1B
- Estruturas condicionais
- Listas e dicionários
- Funções modulares
- Simulação de dados operacionais
- Lógica de tomada de decisão

---

## Dados simulados

Os dados utilizados são simulados e representam uma missão espacial experimental.

Eles foram criados para demonstrar cenários como:

- operação nominal;
- redução de geração solar;
- aumento de consumo;
- déficit energético;
- queda de autonomia;
- necessidade de conservação de energia.

---

## Observação

O Mission Control IA é uma solução de simulação e demonstração. Os dados não representam uma missão real, mas foram estruturados para ilustrar como um sistema computacional pode apoiar o monitoramento energético de uma operação espacial experimental.
