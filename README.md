# RideSmart: Modelagem e Análise de Rotas Urbanas com Grafos

Projeto Final de Estrutura de Dados II (DCA3702, Unidade 3).

Aluno: Matheus Rodrigues Marinho

## Problema

Dado um ponto de origem A (UFRN), um destino B (Midway Mall) e uma distância máxima de caminhada X = 500 m, encontrar o melhor ponto de embarque P, tal que P esteja a no máximo X metros de caminhada de A.

```
A → P  (caminhada)
P → B  (carro)
```

## Cenários Comparados

1. Menor rota em distância
2. Rota mais rápida sem trânsito
3. Rota mais rápida com trânsito sintético
4. Caso sem caminhada (embarcar direto em A)
5. Ganho obtido ao caminhar até outro ponto de embarque

## Algoritmos Implementados

| Algoritmo | Complexidade | Descrição |
|-----------|-------------|-----------|
| Dijkstra Simples | O(V²) | Busca linear pelo mínimo (baseline) |
| Dijkstra com Heap | O((V+E) log V) | Fila de prioridade com heap binário |
| A* | O((V+E) log V) | Heurística haversine (distância geodésica) |
| Dijkstra Bidirecional | O((V+E) log V) | Busca simultânea dos dois lados |

## Modelo de Trânsito

O congestionamento segue um "dia típico" assumido, combinando dois eixos:

- Onde: hierarquia viária mais os corredores arteriais reais (pelo nome no OpenStreetMap), com destaque para a Av. Senador Salgado Filho.
- Quando: um perfil de intensidade por hora (basta mudar a variável `HORA` no notebook para simular outro horário).

O notebook inclui ainda um mapa de calor do congestionamento e uma comparação visual entre horários.

## Estrutura do Projeto

```
ridesmart/
├── README.md
├── requirements.txt
├── PROJETO_FINAL.ipynb                     # Enunciado base do professor
├── notebook/
│   ├── projeto_final_ridesmart.ipynb       # Notebook principal (executável)
│   └── projeto_final_ridesmart.html        # Versão renderizada (abre no navegador)
├── imagens/                                # Figuras geradas (01 a 07)
└── docs/
    └── relatorio.tex                       # Relatório IEEE em LaTeX
```

## Como Executar

```bash
# Clonar o repositório
git clone https://github.com/matheus01301/ridesmart.git
cd ridesmart

# Criar ambiente virtual e instalar dependências
python -m venv .venv
.venv\Scripts\activate        # Windows
pip install -r requirements.txt
```

Depois, abra `notebook/projeto_final_ridesmart.ipynb` no VS Code (com a extensão Jupyter), selecione o kernel Python 3.12 e use "Run All".

Para ver apenas os resultados sem rodar nada, abra `notebook/projeto_final_ridesmart.html` no navegador.

## Tecnologias

- Python 3.12
- OSMnx: download e manipulação de redes viárias do OpenStreetMap
- NetworkX: estrutura de grafos
- Folium: mapas interativos
- Matplotlib: gráficos e visualizações
- Pandas e NumPy: análise de dados
- scikit-learn: dependência do OSMnx para busca de nós

## Área de Estudo

Lagoa Nova e arredores, em Natal/RN, cobrindo o trecho entre a UFRN (Campus Central) e o Midway Mall.
