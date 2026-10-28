# simulation-portafolio
# Simulatore di portafoglio con rischio sistematico

Progetto in Python (numpy) che simula 50 asset su 250 giorni di borsa per studiare diversificazione, rischio di mercato e variabilità dei risultati (Monte Carlo).

## Domanda
Quanto rischio si elimina diversificando, e quanto resta anche con moltissimi asset?

## Metodo
- Ogni asset = fattore di mercato comune (media 0,05%, deviazione 0,7% al giorno) + rumore proprio (deviazione 0,7%).
- Rischio del portafoglio a pesi uguali misurato sui rendimenti simulati e confrontato con la formula teorica √(σm² + σi²/n).
- Crescita del capitale con prodotto cumulato dei fattori di crescita (1 + r).
- Monte Carlo: 500 simulazioni di un anno, capitale iniziale 10.000.

## Risultati
| n asset | Rischio misurato | Rischio teorico |
|---|---|---|
| 1 | 0,97% | 0,99% |
| 5 | 0,72% | 0,77% |
| 20 | 0,66% | 0,72% |
| 100 | 0,66% | 0,70% |
| 500 | 0,66% | 0,70% |

- Correlazione media tra asset: 0,47.
- Il rischio scende da circa 1% a circa 0,7% e si ferma: quella parte è il rischio di mercato e non si elimina diversificando.
- Un anno simulato: capitale da 10.000 a 10.135 (+1,35%).
- Monte Carlo: capitale finale medio circa 11.400, deviazione circa 1.350, circa 14,6% delle simulazioni in perdita.

## Limiti
Dati simulati e non reali, un solo fattore comune, pesi uguali, giorni indipendenti tra loro.

## Come eseguirlo
`pip install -r requirements.txt`, poi eseguire il notebook dall'alto (seed fissati: i risultati sono riproducibili).
