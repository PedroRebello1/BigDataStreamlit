# Dashboard de Vendas – Olist (Tema 5: Visualização e Exploração)

Visualização interativa em Streamlit para explorar vendas da Olist, com KPIs, comparação por métodos de pagamento, séries temporais de faturamento e satisfação, e proporção de status dos pedidos.

## Sumário
- [Arquitetura](#arquitetura)
- [Principais recursos](#principais-recursos)
- [Requisitos](#requisitos)
- [Instalação](#instalação)
- [Dados](#dados)
- [Execução](#execução)
- [Uso do dashboard](#uso-do-dashboard)
- [Slides e navegação](#slides-e-navegação)

## Arquitetura
- **Camada de app:** Streamlit (frontend) + Plotly (visualização) + Pandas (manipulação).
- **Dados:** CSV pré-processado em `data_processed/dataset_final_simple.csv`.
- **Execução:** Local, sem Docker.

## Principais recursos
- **KPIs:** Faturamento total, total de pedidos, nota média.
- **Pagamento:** Gráfico combinado (barras: quantidade; linha: receita) por `payment_types`.
- **Séries temporais:** Faturamento mensal e evolução da nota média.
- **Status:** Barra horizontal com top 3 status + “Outros”.
- **Filtros na sidebar:** Período, status do pedido, métodos de pagamento.

## Requisitos
- Python 3.10+ (recomendado)
- pip

## Instalação
```bash
python -m venv .venv
# Ativar o ambiente
.venv\Scripts\Activate.ps1

pip install -r requirements.txt
```

## Dados
- Coloque o CSV pré-processado em: `data_processed/dataset_final_simple.csv`.
- Se o arquivo não estiver presente, o app exibirá uma mensagem de erro.
- Colunas usadas: `order_purchase_timestamp`, `payment_value_total`, `order_id`, `review_score`, `order_status`, `payment_types` (valores ausentes são tratados como "not_defined").

## Execução
```bash
streamlit run .\\dashboard\\app.py
# Acesse: http://localhost:8501
```

## Uso do dashboard
1. Ajuste os filtros na sidebar:
   - Período (intervalo de datas).
   - Status do pedido (multiselect).
   - Métodos de pagamento (multiselect).
2. Observe:
   - KPIs no topo.
   - Gráfico combinado de quantidade vs receita por método de pagamento.
   - Séries temporais de faturamento e nota média.
   - Distribuição de status (top 3 + Outros).

## Slides e navegação
- Os slides foram salvos como `slide1.html` … `slide14.html`.
- O arquivo `index.html` faz a navegação.


## Estrutura
```
.
├─ dashboard/
│  └─ app.py
├─ data_processed/
│  └─ dataset_final_simple.csv
├─ data_raw/ (Não utilizado para a exibição, e ocupa bastante espaço)
├─ Slides/
├─ README.md
├─ .gitignore
├─ requirements.txt
└─ index.html
```

## Integrantes
- Pedro Rebello
- Mariana Almeida
- Gabriel Francisco
- Guilherme Mendes