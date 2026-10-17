# Modpack Vexilium

Dépôt public lu par le launcher Vexilium. Il contient :

- `manifest.json` : la version du modpack, de Minecraft et de Forge, l'adresse du serveur, les actualités affichées dans le launcher, et la liste des mods avec leur empreinte SHA-1 ;
- dans ses **releases** : les fichiers des mods (`modpack-<version>`) et l'installeur du launcher (`v<version>`).

Les mods dont la licence interdit le rehébergement ne sont pas ici : le manifeste pointe vers leur fichier officiel sur Modrinth.

Ne pas modifier `manifest.json` à la main : il est généré depuis le dépôt du launcher.

## Publier une version du modpack

Depuis le dossier du launcher (`D:\Vexilium\vexilium-launcher`), ce dépôt étant cloné dans `D:\Vexilium\vexilium-modpack` :

1. `powershell -ExecutionPolicy Bypass -File scripts\prepare-modpack.ps1` : remplit `D:\Vexilium\modpack\mods`.
2. `npm run manifest -- D:\Vexilium\modpack\mods <version>` : écrit `manifest.json` ici et affiche la commande `gh release create` qui publie les mods.
3. Lancer cette commande, puis commiter et pousser `manifest.json` sur `main`.

Les launchers installés récupèrent la nouvelle version au prochain clic sur **Jouer**.
