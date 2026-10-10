---
description: Exécute la prochaine étape déterministe du parcours Foyer
argument-hint: "[chemin du projet cible — optionnel]"
---

**Lis puis exécute intégralement `pilote/adapters/claude/commands/foyer-next.md`**, tel quel : c'est
lui qui fait autorité. Cette commande n'est qu'une porte d'entrée à la racine du dépôt Foyer —
elle n'ajoute que la localisation du projet cible.

**Projet cible demandé** (peut être vide) : $ARGUMENTS

**Projet cible.** Si le répertoire courant est le dépôt Foyer lui-même, le registre n'est pas
ici : résous le projet cible comme dans `.claude/commands/foyer.md` (§ « Projet cible ≠ dépôt
Foyer » — chemin donné, sinon registre voisin `../*/PROJET.md` / `RETROFIT.md` / `RELEASE.md` ;
s'il y en a plusieurs, demande lequel). Aucun registre trouvé → dis-le et renvoie vers `/foyer`,
ne crée rien. Registre, code et commits vont dans le projet cible
(chemins absolus, `git -C <cible>`), jamais dans le dépôt Foyer.
