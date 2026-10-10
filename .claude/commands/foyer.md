---
description: Lance le pilote Foyer depuis la racine du dépôt (équivaut à donner pilote/BOOTSTRAP.md à l'agent)
argument-hint: "[description de l'app | chemin du projet cible — optionnel]"
---

Tu es le **pilote Foyer**. **Lis puis exécute intégralement `pilote/BOOTSTRAP.md`**, tel quel :
c'est lui qui fait autorité (cœur à charger, Q0, registre, parcours, invariants). Cette commande
n'est qu'une porte d'entrée — elle n'ajoute qu'une précision : **où vit le projet cible**.

**Demande de l'utilisateur** (peut être vide) : $ARGUMENTS

Si c'est une description d'app, sers-t'en pour amorcer le contexte (étape 2 du bootstrap) et ne
la redemande pas.

## Projet cible ≠ dépôt Foyer

Ce dépôt est le cadre méthodologique : on n'y crée **jamais** de registre (`PROJET.md` /
`RETROFIT.md` / `RELEASE.md`) ni de code applicatif. Si le répertoire courant est le dépôt Foyer
lui-même (présence de `Manifeste-Foyer.md` et de `pilote/`), détermine la cible **avant Q0** :

1. **Chemin donné** — si la demande est un répertoire existant, c'est le projet cible.
2. **Reprise** — sinon, cherche un registre dans les dossiers voisins (`../*/PROJET.md`,
   `../*/RETROFIT.md`, `../*/RELEASE.md`). S'il y en a, propose de **reprendre** ce projet
   (une question, en langage clair) plutôt que d'en créer un second ; s'il reprend, ne repose
   pas Q0 et repars de l'étape courante du registre.
3. **Nouveau** — sinon, la cible est `../<nom-du-projet>` (créé et `git init` si absent), ou le
   chemin du legacy pour un rétrofit / une release. **Annonce ce chemin en une phrase** avant
   d'y écrire ; l'utilisateur peut en donner un autre.

Le cœur (`pilote/`, `skills/`, `bmad/`, `kit-*`) se lit depuis ce dépôt ; registre, code et
commits vont dans le projet cible — chemins absolus, `git -C <cible>` pour committer, et lis
l'`AGENTS.md` de la cible s'il existe (il porte les commandes de gates).

Si le répertoire courant n'est pas le dépôt Foyer (commande installée dans un projet
consommateur), le projet cible est le répertoire courant.
