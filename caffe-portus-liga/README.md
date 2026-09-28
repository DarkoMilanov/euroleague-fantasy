# Caffe Portus Liga

Tabela EuroLeague Fantasy lige Caffe Portus: runde od 5 kola, pobjednik runde, uplate i nagradni fond.

## Fajlovi

- `index.html` je stranica.
- `podaci.json` sadrži sve podatke: učesnike, bodove po kolu, uplate i izbačene.
- `.nojekyll` govori GitHub Pages-u da objavi fajlove onakve kakvi jesu.

## Postavljanje (jednom)

1. Na GitHub-u klikni **New repository**. Naziv: `caffe-portus-liga`. Označi **Public** (GitHub Pages je besplatan samo za javne repozitorije).
2. U repozitoriju klikni **Add file → Upload files** i prevuci sva tri fajla (`index.html`, `podaci.json`, `.nojekyll`). Klikni **Commit changes**.
   - Na Mac-u je `.nojekyll` sakriven. U prozoru za izbor fajlova pritisni `Cmd + Shift + .` da ga vidiš.
3. Otvori **Settings → Pages**. Pod **Source** izaberi **Deploy from a branch**, branch `main`, folder `/ (root)`, pa klikni **Save**.
4. Za 1–2 minute stranica je na adresi `https://TVOJE-KORISNIČKO-IME.github.io/caffe-portus-liga/`. Taj link pošalji ekipi. Za gledanje ne treba nikakav nalog.

## Admin: upis bodova i uplata direktno sa stranice

Da bi stranica mogla sama da sačuva promjene na GitHub, treba joj token.

1. Na GitHub-u: slika profila → **Settings → Developer settings → Personal access tokens → Fine-grained tokens → Generate new token**.
2. **Repository access:** *Only select repositories* → `caffe-portus-liga`.
3. **Permissions → Repository permissions → Contents:** *Read and write*.
4. Izaberi rok trajanja (npr. do kraja sezone), klikni **Generate token** i kopiraj ga.
5. Na stranici lige klikni **Admin** (dno stranice), pa u **Podešavanja** zalijepi token. Repozitorij se popuni sam kad je stranica na github.io. Klikni **Sačuvaj podešavanja**.

Token ostaje samo u pregledaču na tvom uređaju. Nikome ga ne šalji i ne upisuj ga u fajlove u repozitoriju.

Poslije svakog kola:

1. **Upiši bodove kola** → izaberi kolo → upiši bodove → **Primijeni**.
2. Označi uplate u tabu **Uplate**, izbaci ili dodaj učesnike preko **⋯** ako treba.
3. Klikni **Sačuvaj na GitHub** na dnu. Ekipa vidi promjene za 1–2 minute.

**Bez tokena:** uradi iste izmjene, klikni **Preuzmi podaci.json**, pa u repozitoriju **Add file → Upload files** i ubaci novi `podaci.json` (zamijeni stari).

## Format podataka

```json
{
 "ukupnoKola": 38,
 "kolaPoRundi": 5,
 "igraci": [
  { "id": "p01", "team": "Bušač", "manager": "Nemanja Prodanovic",
    "joinedFrom": 1, "outFrom": null,
    "pts": { "1": 189.2 }, "paid": { "1": true } }
 ]
}
```

- `pts`: bodovi po kolu (`"kolo": bodovi`).
- `paid`: uplata po rundi (`"runda": true`).
- `outFrom`: prvo kolo od kog je učesnik izbačen, ili `null`.
- `joinedFrom`: kolo od kog učesnik igra.
