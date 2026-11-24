# Pașii finali (se fac din contul tău GitHub / Git Bash)

## 1. Insigna verde „Verified” pe commit-uri
1. Deschide fișierul [`cheie-publica-gpg-Popov-Serghei.asc`](cheie-publica-gpg-Popov-Serghei.asc) → butonul **Raw** → copiază tot textul
   (de la `-----BEGIN PGP PUBLIC KEY BLOCK-----` până la `-----END PGP PUBLIC KEY BLOCK-----`).
2. GitHub → poza de profil → **Settings** → **SSH and GPG keys** → **New GPG key** → lipește → **Add GPG key**.
3. GitHub → **Settings** → **Emails**: adaugă `popov.serghei@elev.cihcahul.md` și confirmă-l din e-mailul primit.
4. Reîmprospătează pagina *Commits*: commit-urile semnate primesc insigna **Verified**.

## 2. Urcarea etichetei semnate `v1.0-serghei`
Eticheta (cu semnătura GPG inclusă) se află în `eticheta-v1.0-serghei.bundle`. În Git Bash:

```bash
git clone https://github.com/Fagura/Lab-gitignore-gitattributes-LFS-GPG-Popov-Serghei.git
cd Lab-gitignore-gitattributes-LFS-GPG-Popov-Serghei
git fetch raport/eticheta-v1.0-serghei.bundle refs/tags/v1.0-serghei:refs/tags/v1.0-serghei
git push origin v1.0-serghei
```

Nu este nevoie de cheia privată: semnătura este deja în etichetă. După import, la tine
`git tag -v v1.0-serghei` arată „Good signature” doar după ce imporți și cheia publică
(`gpg --import raport/cheie-publica-gpg-Popov-Serghei.asc`); pe GitHub eticheta apare **Verified** după pasul 1.
