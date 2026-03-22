---
description: "Audit qualité d'un skill — checklist 13 critères + plan d'amélioration"
---

```xml
<context>
Je crée des skills (system prompts réutilisables) au format XML avec 5 blocs :
role, context, instructions, format_sortie, contraintes.
J'ai besoin d'auditer un skill existant pour identifier ses faiblesses
et l'améliorer. Le résultat est pour moi-même, pour augmenter l'efficacité
de mes skills.
</context>

<donnees>
$ARGUMENTS
</donnees>

<instructions>
1. Évalue le skill avec cette checklist de 13 critères répartis en 4 catégories :

   **Structure (5 points)** :
   - Le rôle est défini et spécifique (pas "tu es un expert")
   - Le contexte explique le POURQUOI et le POUR QUI
   - Les instructions sont numérotées et actionnables
   - Le format de sortie est un template concret
   - Les contraintes corrigent des défauts réels observés

   **Précision (3 points)** :
   - Chaque instruction = 1 seule action
   - Les nombres sont précis ("5 idées", pas "quelques idées")
   - Les termes ambigus sont définis ("court" = combien de mots ?)

   **Robustesse (3 points)** :
   - Le skill gère les cas limites (input vide, input ambigu)
   - Une instruction de repli existe ("si tu n'es pas sûr, dis-le")
   - Le skill fonctionne avec des inputs variés (testé sur 3+ cas)

   **Concision (2 points)** :
   - Le skill tient en moins de 30 lignes de contenu XML
   - Pas de répétitions entre les sections

2. Pour chaque critère, coche [x] ou [ ] avec une justification courte.
3. Identifie les forces principales (max 3).
4. Identifie les faiblesses avec actions correctives.
5. Propose un plan d'amélioration priorisé et implémentable.
6. Implémente toutes les améliorations et génère le skill corrigé complet.
7. Affiche le skill amélioré dans un bloc markdown prêt à copier.
8. Si tu n'es pas sûr d'un point, signale-le plutôt que deviner.
</instructions>

<format_sortie>
## Audit skill : [nom du skill]
### Score : X/13

### Structure (X/5)
- [x/  ] Critère — justification
### Précision (X/3)
- [x/  ] Critère — justification
### Robustesse (X/3)
- [x/  ] Critère — justification
### Concision (X/2)
- [x/  ] Critère — justification

### Forces
- [force 1]

### Faiblesses et actions
| # | Problème | Impact | Action corrective |
|---|----------|--------|-------------------|

### Plan d'amélioration
| Priorité | Action | Effort (S/M/L) | Résultat attendu |
|----------|--------|-----------------|------------------|
| 1 | ... | ... | ... |

### Skill amélioré
```markdown
[Skill complet corrigé, prêt à copier-coller]
```
</format_sortie>
```
