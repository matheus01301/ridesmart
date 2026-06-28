# RideSmart — Modelagem e Análise de Rotas Urbanas com Grafos

**Projeto Final** — Estrutura de Dados II (DCA3702, Unidade 3)

**Aluno:** Matheus Rodrigues Marinho

---

## Problema

Dado um ponto de origem **A** (UFRN), um destino **B** (Midway Mall) e uma distância máxima de caminhada **X = 500m**, encontrar o melhor ponto de embarque **P** tal que P esteja a no máximo X metros de caminhada de A.

```
A → P  (caminhada)
P → B  (carro)
```

## Cenários Comparados

1. Menor rota em **distância**
2. Rota mais rápida **sem trânsito**
3. Rota mais rápida **com trânsito sintético**
4. Caso **sem caminhada** (embarcar direto em A)
5. **Ganho** obtido ao caminhar até outro ponto de embarque

## Algoritmos Implementados

| Algoritmo | Complexidade | Descrição |
|-----------|-------------|-----------|
| Dijkstra Simples | O(V²) | Busca linear pelo mínimo (baseline) |
| Dijkstra com Heap | O((V+E) log V) | Fila de prioridade com heap binário |
| A* | O((V+E) log V) | Heurística haversine (distância geodésica) |
| Dijkstra Bidirecional | O((V+E) log V) | Busca simultânea dos dois lados |

## Estrutura do Projeto

```
ridesmart-lagoa-nova/
├── README.md
├── requirements.txt
├── notebook/
│   └── projeto_final_ridesmart.ipynb   # Notebook principal (executável)
├── imagens/                             # Visualizações geradas
│   ├── 01_rede_completa.png
│   ├── 02_nos_expandidos.png
│   ├── 03_tempo_execucao.png
│   ├── 04_rotas_comparadas.png
│   └── 05_ganho_caminhada.png
└── docs/
    └── relatorio.pdf                    # Relatório IEEE (até 4 páginas)
```

## Como Executar

```bash
# Clonar o repositório
git clone https://github.com/seu-usuario/ridesmart-lagoa-nova.git
cd ridesmart-lagoa-nova

# Criar ambiente virtual e instalar dependências
python -m venv .venv
.venv\Scripts\activate        # Windows
pip install -r requirements.txt

# Executar o notebook
jupyter notebook notebook/projeto_final_ridesmart.ipynb
```

## Tecnologias

- **Python 3.11+**
- **OSMnx** — download e manipulação de redes viárias do OpenStreetMap
- **NetworkX** — estrutura de grafos
- **Folium** — mapas interativos
- **Matplotlib** — gráficos e visualizações
- **Pandas / NumPy** — análise de dados

## Área de Estudo

Lagoa Nova e arredores — Natal/RN, cobrindo o trecho entre a **UFRN (Campus Central)** e o **Midway Mall**.
