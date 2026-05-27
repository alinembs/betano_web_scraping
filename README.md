# Betano (Odds) — Coleta via Selenium e BeautifulSoup

Este projeto automatiza um navegador para inspecionar uma página de **live** da Betano e montar um dataset com odds e placares/textos relacionados.

## O que foi feito

O script `coletar_odd_betano.py` faz:

1. Configura Selenium com Chrome em modo **headless**.
2. Acessa a URL:
   - `https://br.betano.com/live/`
3. Aguarda 5 segundos (`time.sleep(5)`).
4. Encontra um elemento no DOM via XPath (variável `inspect`) e extrai o HTML interno (`outerHTML`).
5. Usa **BeautifulSoup** para parsear o HTML retornado.
6. Monta listas para:
   - `liga` (header)
   - `time1`, `time2` (participantes)
   - `placartime1`, `palcartime2` (scores)
   - `odd1`, `odd2`, `odd3` (três odds por ocorrência)
7. Gera um `DataFrame` com as colunas:
   - `liga`
   - `time1`
   - `time2`
   - `placartime1`
   - `palcartime2`
   - `odd1_vencedor_1`
   - `odd2_vencedor_2`
   - `odd3_vencedor_3`
8. Imprime o `DataFrame` no console (`print(df)`).

## Arquivo

- `coletar_odd_betano.py`
  - Código principal da automação (Selenium + BeautifulSoup) e montagem do `DataFrame`.

## Fonte dos dados

- Betano (Live)
  - `https://br.betano.com/live/`

## Como executar

No diretório `WebScraping-Python/URL_BETANO`, execute:

```bash
python coletar_odd_betano.py
```
