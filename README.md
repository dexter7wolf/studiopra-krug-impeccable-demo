# Studio PRA – sito statico (versioning)

Questo repository contiene il sito statico HTML di Studio PRA.

## Obiettivo
Mantenere **due versioni** in parallelo su GitHub:
1. **Versione attuale online** (quella già presente ora su GitHub / produzione).
2. **Versione aggiornata** (con footer sedi aggiornato + testo box "Avvocati International" tradotto).

## Modifiche introdotte nella versione aggiornata
- Footer aggiornato in:
  - `index.html`
  - `Impressum.html`
  - `privacy-policy.html`
- Testo box `Avvocati International` aggiornato in `index.html`.

## Come mantenere entrambe le versioni su GitHub

### Strategia consigliata (branch + tag)

- `main` → versione stabile/pubblicata (attuale in produzione).
- `release/footer-update-it` (o branch dedicato) → versione aggiornata.

Passi pratici:

```bash
# 1) Assicurati di avere tutti gli aggiornamenti
git fetch origin

# 2) Tagga la versione attuale (backup storico)
git checkout main
git pull origin main
git tag -a v1-current-prod -m "Versione attuale in produzione"
git push origin v1-current-prod

# 3) Pubblica la nuova versione su branch dedicato
git checkout -b release/footer-update-it
# (se il branch esiste già: git checkout release/footer-update-it)
git push -u origin release/footer-update-it

# 4) Apri una Pull Request verso main quando vuoi sostituire la produzione
# (su GitHub UI)
```

In questo modo:
- la versione vecchia resta recuperabile dal tag `v1-current-prod`;
- la nuova resta sul branch dedicato finché non decidi di fare merge su `main`.

## Variante alternativa (cartella duplicata)
Se vuoi tenere entrambe le versioni nello **stesso branch** contemporaneamente, puoi usare due cartelle (es. `/v1` e `/v2`), ma per un sito statico è spesso meno pulito della strategia con branch/tag.

## Note operative
- Se usi GitHub Pages da branch `main`, il sito live non cambia finché non fai merge della PR.
- Se vuoi provare la nuova versione prima del merge, pubblica da un branch secondario o anteprima.
