---
name: Session Handoff
description: Produire un mémo de transfert entre sessions — état réel du travail, décisions, fichiers touchés, prochaines étapes, blocages — pour reprendre sans relire tout le dépôt. À utiliser en fin de session longue, avant une pause, ou quand on demande « par où on en était ».
---

# Session Handoff

Objectif : une reprise en contexte frais coûte un minimum de tokens et
ne perd aucun fait. Le mémo remplace la relecture (lien `opti-skill`)
et dit la vérité sur ce qui est fait ou non (lien `anti-dream`).

## Quand produire le mémo

- Fin d'une session longue ou avant une pause
- Avant de changer de sujet majeur
- Quand l'utilisateur demande « résume », « par où on en était »,
  « on reprend demain »
- Quand un changement important de direction a eu lieu

## Format du mémo

```markdown
# Handoff — <projet> — <date>

## Objectif
<1–2 lignes : ce que l'utilisateur veut réellement obtenir>

## État
- **Fait et vérifié** : … (preuve : test passé, exécuté, observé)
- **Fait non vérifié** : … (quoi manque : tests, non exécuté…)
- **Non fait** : … (ce qui reste de la demande initiale)

## Décisions
- <choix fait + pourquoi> — alternatives rejetées : …

## Fichiers touchés
- `chemin` — ce qui a changé et pourquoi
- Fichiers **lus mais non modifiés** utiles à reprendre : …

## Repères
- Digests utiles : commandes qui marchent, ports, URLs, constantes
  (pas besoin de relire les fichiers pour les retrouver)
- Pièges rencontrés : ce qui ne marche pas et pourquoi

## Prochaines étapes
1. <action concrète, vérifiable>
2. …

## Blocages / questions ouvertes
- <bloquant pour qui, quoi décider>
```

## Règles

1. **Vérité sur l'état** : distinguer strictement *fait vérifié* /
   *fait non vérifié* / *non fait*. Jamais présenter un travail non
   testé comme terminé.
2. **Actions vérifiables** : chaque « prochaine étape » doit pouvoir
   être dite vraie ou fausse (« lancer `npm test` et obtenir 0 échec »
   plutôt que « continuer le dev »).
3. **Compact** : viser une lecture de moins d'une minute. Les détails
   vivent dans les fichiers, le mémo donne les **chemins** pour les
   retrouver sans les relire.
4. **Digests, pas des copies** : ne pas coller le contenu des fichiers —
   donner l'essentiel + l'endroit où le relire si besoin.
5. **Aucun fait inventé** : si un truc n'a pas été vérifié dans la
   session, il figure dans *non vérifié*, pas dans *fait*.

## À la reprise

1. Lire le mémo, pas tout le dépôt.
2. Vérifier rapidement que l'état décrit correspond au réel
   (`git status`, un test rapide) — un mémo peut vieillir.
3. Reprendre à la première étape non faite, pas à la dernière faite.
