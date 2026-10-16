# Règles du projet — Réveil / Jarvis (iPad)

Après CHAQUE modification de `reveil/index.html` (ou de `reveil/data.json`), sans que l'utilisateur ait à le demander :
1. Changer la valeur de `<meta name="reveil-version">` (ex. 2026-10-16-b) pour que les appareils se rechargent seuls.
2. Vérifier la syntaxe (`node --check` sur le script) et que tout tient sur l'écran de l'iPad Air 2.
3. `git add -A && git commit && git pull --rebase origin main && git push origin main` (GitHub Pages = iPad).
4. Republier l'Artifact https://claude.ai/artifact/EfsNihzPH8bnb5MHLjzw9w avec le même fichier (`reveil/index.html`) pour que la version dans Claude soit identique.
5. Vérifier que `git status` est propre et que la version en ligne (https://westphal03.github.io/jarvis-ai/reveil/) affiche le nouveau numéro de version.

Données: `reveil/data.json` est la source commune (notes, routine, calendrier). L'iPad la lit sans clé; avec une clé GitHub (touche le texte au-dessus du bloc-notes) il y écrit aussi. Ne jamais écraser les notes de l'utilisateur: fusionner, ne pas remplacer.
Ne jamais supprimer `reveil/sounds/`. Le workflow `.github/workflows/fetch-sounds.yml` télécharge les sons CC0 (BigSoundBank).
