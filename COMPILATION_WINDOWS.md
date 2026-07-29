# Compilation Windows automatique

Ce dépôt contient un workflow GitHub Actions :

`.github/workflows/build-windows.yml`

## Utilisation

1. Créez un nouveau dépôt GitHub vide.
2. Décompressez cette archive puis envoyez tous les fichiers dans le dépôt.
3. Ouvrez l'onglet **Actions**.
4. Sélectionnez **Build psiconv for Windows**.
5. Cliquez sur **Run workflow**.
6. À la fin, téléchargez l'artefact **psiconv-windows-x64**.

Le workflow utilise un véritable environnement Windows avec MSYS2/UCRT64 et MinGW-w64. Il tente de générer un `psiconv.exe` 64 bits statique, sans ImageMagick.

## État vérifié ici

La compilation Linux du même code a réussi avec :

```sh
./configure --with-imagemagick=no
make
```

Le binaire Linux obtenu répond correctement à `--help`. La compilation Windows doit néanmoins être validée par le workflow, car l'ancien code peut révéler des incompatibilités spécifiques à MinGW.
