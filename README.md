# Organizație GitHub · .gitignore · .gitattributes · Git LFS · Commit-uri semnate

**Elev:** Popov Serghei — popov.serghei@elev.cihcahul.md · **Grupa:** AAW 2231
**Instituția:** IP Colegiul „Iulia Hasdeu” din Cahul — Catedra TIC · **Profesor:** Turceac Natalia

Rezolvarea fișei de lucru „Organizație GitHub, .gitignore, .gitattributes, Git LFS, semnarea commit-urilor”.
Acest repozitoriu este chiar `proiect-echipa` din fișă: conține istoricul real al exercițiilor 4–6
(fișier mare prin LFS, commit-uri și etichetă semnate GPG, folderul `echipa/`).

| Ce găsiți | Unde |
|---|---|
| Fișa completată, cu răspunsuri, capturi și explicații | [`raport/Fisa_de_lucru_Popov_Serghei_rezolvata.docx`](raport/Fisa_de_lucru_Popov_Serghei_rezolvata.docx) · [PDF](raport/Fisa_de_lucru_Popov_Serghei_rezolvata.pdf) |
| Toate capturile de ecran Git Bash (20) | [`raport/capturi/`](raport/capturi) |
| Proiectul de exercițiu de la Ex. 2–3 (`proiect-ignore`) | [`proiect-ignore/`](proiect-ignore) + `ISTORIC-git-log.txt` |
| Fișier mare stocat cu Git LFS (Ex. 4) | [`date-serghei.bin`](date-serghei.bin) — „Stored with Git LFS” |
| Commit semnat + etichetă semnată (Ex. 5) | `semnatura-serghei.txt`, tag `v1.0-serghei` |
| Contribuția în echipă (Ex. 6) | [`echipa/serghei.txt`](echipa/serghei.txt) |
| Cheia GPG **publică** (ID `87BDA85210AA89C5`) | [`raport/cheie-publica-gpg-Popov-Serghei.asc`](raport/cheie-publica-gpg-Popov-Serghei.asc) |

## Rezumat pe exerciții

1. **Organizația GitHub** — se creează din browser (+ → New organization → Free), se invită colegii, coordonatorul creează `proiect-echipa`. Membrii îl clonează (`git clone`, `git remote -v`).
2. **.gitignore** — reguli `*.log`, `node_modules/`, `.env`, comentarii `#`, excepția `!important.log`, `temp/`; verificare cu `git check-ignore -v`; reguli locale (`.git/info/exclude`) și globale (`core.excludesfile`); oprirea urmăririi cu `git rm --cached`.
3. **.gitattributes** — `*.txt text eol=lf`, `*.sh text eol=lf`, `*.png binary`, `docs/* export-ignore`; `git check-attr`, `git add --renormalize .` (CRLF → LF), `git archive` fără `docs/`.
4. **Git LFS** — `git lfs install`, `git lfs track "*.bin"`, fișier de 5 MB; în depozit rămâne doar pointerul (`oid sha256…`, `size 5242880`); `git lfs untrack`.
5. **Semnare GPG** — cheie RSA 4096 valabilă 30 de zile, `user.signingkey`, `git commit -S`, `git log --show-signature` → *Good signature*, `git tag -s` / `git tag -v`, `commit.gpgSign true`, export cheie publică.
6. **Lucru în echipă** — `echipa/serghei.txt`, `git pull`, `git push`, `git log --pretty="%h %an %G? %s"`, `git lfs pull`.

## Răspunsuri la întrebările de control

| Situația | Comanda / regula |
|---|---|
| Să nu fie urmărit niciun fișier `.log` | `*.log` în `.gitignore` |
| Scot un fișier din urmărire, dar rămâne pe disc | `git rm --cached <fișier>` |
| Marchez `.png` ca binare | `*.png binary` în `.gitattributes` |
| `.zip` gestionate prin LFS | `git lfs track "*.zip"` |
| Semnez un commit | `git commit -S -m "mesaj"` |
| Văd dacă commit-urile sunt semnate | `git log --show-signature` / `git log --pretty="%h %G? %s"` |

> Insigna verde **Verified** apare pe GitHub după ce cheia publică din `raport/` este adăugată în
> *Settings → SSH and GPG keys → New GPG key*, iar e-mailul `popov.serghei@elev.cihcahul.md` este verificat în cont.
