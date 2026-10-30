# Session Handoff

> Skill OpenCode de transfert entre sessions — mémo d'état réel pour reprendre le travail sans relire tout le dépôt.

**ID** : `session-handoff` · **Portée** : globale (`~/.config/opencode/skills/`) · **Langue** : FR

## Ce que fait le skill

Produit un mémo compact qui remplace la relecture à la reprise :

```markdown
# Handoff — <projet> — <date>
## Objectif        # ce que l'utilisateur veut réellement
## État            # fait vérifié / fait non vérifié / non fait
## Décisions       # choix + pourquoi, alternatives rejetées
## Fichiers touchés # changements + fichiers lus utiles à reprendre
## Repères         # digests : commandes, ports, constantes, pièges
## Prochaines étapes # actions vérifiables, numérotées
## Blocages        # questions ouvertes
```

## Règles

1. **Vérité sur l'état** : strict distinction fait vérifié / non vérifié / non fait
2. **Actions vérifiables** : chaque étape peut être dite vraie ou fausse
3. **Compact** : lecture < 1 minute, les détails vivent dans les fichiers
4. **Digests, pas des copies** : chemins pour retrouver, pas de contenu collé
5. **Aucun fait inventé**

## À la reprise

Lire le mémo (pas le dépôt), vérifier que l'état vieillit bien (`git status`, un test), reprendre à la première étape non faite.

## Structure

```text
session-handoff/
└── SKILL.md              # Format complet, règles, protocole de reprise
```

## Déclenchement

- **Automatique** : fin de session longue, avant pause, « par où on en était »
- **Manuel** : `@session-handoff`

## Skills liés

- `opti-skill` (digests), `anti-dream` (honnêteté sur l'état réel)
