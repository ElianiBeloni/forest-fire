# Forest Fire

Simulação de incêndios florestais baseada em agentes, com a biblioteca [Mesa](https://mesa.readthedocs.io/). Parte do exemplo [forest_fire](https://github.com/projectmesa/mesa-examples/tree/main/examples/forest_fire) do Mesa e o estende com biomas brasileiros, vento, chuva, bombeiros e obstáculos naturais.

## O que o modelo simula

- **Biomas.** Amazônia, Mata Atlântica, Cerrado, Caatinga e Pantanal, além de um bioma padrão. Cada um tem densidade de árvores, umidade, temperatura, tamanho das árvores e fator de emissão de CO2 próprios.
- **Vento.** Direção e intensidade alteram a propagação do fogo e o deslocamento das nuvens.
- **Estação chuvosa.** Nuvens surgem em intervalos configuráveis, com quantidade e tamanho ajustáveis.
- **Bombeiros.** Agentes que apagam o fogo na célula em que estão e se deslocam para árvores vizinhas em chamas.
- **Terreno.** Lagos, corredores e obstáculos, cada um com densidade configurável.
- **Regeneração.** As árvores se reproduzem a uma velocidade ajustável.
- **Foco inicial.** Aleatório, ou em uma borda ou no centro da grade.

A cada passo o modelo registra o número de árvores saudáveis, em chamas e queimadas, a quantidade de nuvens e o CO2 emitido, em kg.

## Como executar

```bash
python -m venv .venv
```

```bash
pip install -r requirements.txt
```

```bash
python run.py
```

O servidor do Mesa abre a visualização no navegador, com os controles de bioma, vento, chuva e terreno.

## Estrutura

```
run.py                 inicia o servidor
forest_fire/
  model.py             o modelo: grade, inicialização e coleta de dados
  tree.py              árvores e solo
  biome.py             parâmetros de cada bioma
  cloud.py             nuvens e chuva
  fireman.py           bombeiros
  obstacles.py         lagos, corredores e obstáculos
  server.py            interface e controles
  batch.py             execuções em lote
  static/images/       imagens das árvores e do solo, por bioma
dados/data.csv         resultados das execuções em lote
```

## Equipe

Trabalho em grupo de alunos do IMPA Tech, feito em novembro de 2024. Contribuíram com código:
[tainaimpa](https://github.com/tainaimpa), [bianca-zavadisk](https://github.com/bianca-zavadisk), [ElianiBeloni](https://github.com/ElianiBeloni), [kaio-costa](https://github.com/kaio-costa), [Suelen-Luiz](https://github.com/Suelen-Luiz), [yas-monteiro](https://github.com/yas-monteiro), [tomazcavalcantee](https://github.com/tomazcavalcantee), [adririffel](https://github.com/adririffel) e [isabelli-cristhini](https://github.com/isabelli-cristhini).
