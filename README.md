# 🔭 LSST_Tools

Bem-vindo ao **LSST_Tools**! Este repositório é uma coletânea de scripts em Python e Jupyter Notebooks voltados para pesquisadores, cientistas de dados e estudantes que trabalham (ou pretendem trabalhar) com os dados do **Observatório Vera C. Rubin (LSST)**.

O objetivo principal deste repositório é fornecer soluções limpas, reprodutíveis e independentes para tarefas cotidianas da astronomia no LSST. Em vez de focar em uma pesquisa específica, estas ferramentas são projetadas para serem de uso geral, resolvendo gargalos comuns e contornando dependências desatualizadas na Rubin Science Platform (RSP).

## 🚀 Ferramentas Disponíveis

### 1. Robust LSST Footprint Cross-Matcher (`lsst_footprint_crossmatch.ipynb`)
Uma ferramenta definitiva para cruzar catálogos astronômicos (Quasares, AGNs, Galáxias, etc.) com a área oficial de cobertura do LSST.
* **Fisicamente Preciso:** Gera o *Wide-Fast-Deep (WFD)* baseando-se em limites reais de extinção de poeira da Via Láctea (SFD Dust Maps, E(B-V) < 0.2), em vez de cortes geométricos arbitrários ou APIs defasadas.
* **Deep Drilling Fields (DDFs):** Identifica, classifica e plota dinamicamente objetos que caem dentro dos campos profundos do LSST (COSMOS, XMM-LSS, ECDFS, ELAIS-S1, EDFS).
* **100% Reprodutível na RSP:** Inclui um bloco de setup automático que garante que o ambiente (mapas de poeira) seja configurado silenciosamente para qualquer usuário rodando o script na Rubin Science Platform, sem erros de diretório.
* **Exportação Limpa:** Separa os resultados automaticamente em arquivos `.txt` prontos para ingestão no Pandas ou outras análises.

## 💻 Como Usar

A maioria dos scripts foi otimizada para rodar nativamente na **Rubin Science Platform (RSP)** utilizando o kernel padrão do LSST, não exigindo a instalação de pacotes complexos de terceiros.

Bibliotecas base utilizadas:
* `numpy`, `pandas`, `matplotlib`
* `astropy` (para manipulação de coordenadas e cosmologia)
* `healpy` (para projeções e mapas no formato HEALPix)
* `rubin_sim` (Nativa da RSP)

Para usar a ferramenta de Footprint:
1. Clone este repositório ou baixe o notebook desejado.
2. Faça o upload do seu catálogo de objetos (em `.csv` contendo colunas de `RA` e `DEC`).
3. Rode o bloco de Setup Inicial (para baixar os mapas de poeira, se necessário).
4. Execute o script para gerar os gráficos e arquivos `.txt` com os *cross-matches*.

## 🤝 Contribuições
Este é um repositório em crescimento. Sinta-se à vontade para abrir *Issues* relatando problemas ou enviar *Pull Requests* com novas ferramentas, scripts de visualização de curvas de luz ou métodos de consulta de banco de dados (TAP/ADQL) que possam ser úteis para a comunidade do LSST.

---
**Autor:** Vítor Güez
**Licença:** MIT (Livre para uso, modificação e distribuição acadêmica)
