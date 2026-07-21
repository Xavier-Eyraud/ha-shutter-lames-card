# Shutter Lames Card

Carte Home Assistant personnalisée pour piloter un volet roulant (`cover`) par clic-glissé, sous forme de lames.

- Visuel pur : pas d'en-tête, pas d'icône, pas de titre — juste les lames.
- Nombre de lames configurable (`lames`), la position s'accroche automatiquement aux pas de `100 / lames` %.
- Les séparateurs de lames ne sont visibles que dans la partie fermée du volet, jamais dans la partie ouverte.
- Une carte = un volet. Couleur et nombre de lames se règlent indépendamment pour chaque carte.

## Installation

### Via HACS (recommandé)

1. HACS → **Tableau de bord** → ⋮ → **Dépôts personnalisés**.
2. URL : `https://github.com/Xavier-Eyraud/cube_shutter_lames_card`, catégorie **Tableau de bord**.
3. Cherche **Shutter Lames Card**, clique **Télécharger**. La ressource Lovelace est ajoutée automatiquement.
4. Recharge la page.

### Manuellement

1. Copie `cube_shutter_lames_card.js` dans le dossier `config/www/` de ta configuration Home Assistant.
2. Ajoute-le comme ressource Lovelace :
   - **Paramètres → Tableaux de bord → ⋮ → Ressources → Ajouter une ressource**
   - URL : `/local/cube_shutter_lames_card.js`
   - Type : **Module JavaScript**
3. Recharge la page (vide le cache navigateur si besoin).

## Utilisation

### Via l'éditeur visuel

Ajoute la carte depuis le tableau de bord (**Ajouter une carte → Shutter Lames Card**) : un éditeur permet de
choisir l'entité `cover` dans la liste, la couleur des lames et le nombre de lames, sans passer par le YAML.

### Manuellement (YAML)

```yaml
type: custom:shutter-lames-card
entity: cover.volet_chambre
color: "#B784C4"
lames: 10
```

## Options

| Option   | Requis | Défaut                 | Description                                            |
|----------|--------|------------------------|----------------------------------------------------------|
| `entity` | oui    | —                      | Entité `cover.*` à piloter                              |
| `color`  | non    | `var(--primary-color)` | Couleur de remplissage des lames                         |
| `lames`  | non    | `4`                    | Nombre de lames — la position s'accroche à `100/lames` % |
