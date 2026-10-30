
## 1. Vision (le pitch)

Un site qui ressemble à un **jeu vidéo rétro dont il est le héros** : chaque page est un « niveau », chaque projet un « boss à débloquer », un compteur de XP monte à chaque visite. Pas un portfolio ennuyeux — une **aventure interactive** découverte en jouant.

> Tagline : *« Appuie sur START pour me découvrir. »*

## 2. Comment ça va vraiment se construire

**Workflow Google AI Studio, en 4 temps :**

| Étape | Action | Résultat |
|-------|--------|----------|
| 1️⃣ Prompt initial | Coller le « prompt fondateur » (fourni en §11) dans AI Studio | Un fichier `index.html` complet, fonctionnel |
| 2️⃣ Tests | Ouvrir le fichier dans le navigateur, cliquer partout | Liste de ce qui marche / coince |
| 3️⃣ Affinage | Retour dans AI Studio : *« Garde tout, mais change X »* | Itération rapide, sans jamais repartir de zéro |
| 4️⃣ Copilote | Lui propose ses propres modifs (*« rends le bleu plus flashy »*) | Il apprend en réformulant, pas en codant |

**Règle d'or du vibe coding :** jamais deux changements dans le même prompt. Un prompt = une amélioration = un test. C'est ça, la boucle d'affinage.

## 3. Public cible

- **Principal** : copains/copines de 10–14 ans (attention courte, fun, interactivité)
- **Secondaire** : famille, profs — qui découvrent le sérieux sous le fun

## 4. Objectifs

| # | Objectif | Critère de succès |
|---|----------|-------------------|
| 1 | Obtenir un site jouable en 1 soirée | `index.html` fonctionnel dès le 1er prompt |
| 2 | Apprendre la boucle « prompt → test → affinage » | 10+ itérations documentées dans le devlog (§8) |
| 3 | Personnaliser un site qui lui ressemble | Zéro texte générique laissé dans la version finale |
| 4 | Impressionner | Un visiteur reste ≥ 2 min et trouve au moins 1 easter egg |

## 5. Concept créatif — les mécaniques

### 🕹️ Écran d'accueil façon borne d'arcade
- Logo pixellisé animé (néon clignotant)
- Bouton **« INSERT COIN / START »** clignotable
- Son 8-bit au clic (avec bouton 🔇 — la politesse web !)

### 🗺️ La « carte du monde » = le menu
Un avatar pixel-art marche sur une map, 4 zones cliquables :
1. **🌋 Qui suis-je ?** — cartes animées : hobbies, sports, 5 faits fun (dont 1 absurde)
2. **🏰 Mes projets** — chaque projet se débloque après une mini-interaction
3. **👾 Mes high scores** — badges et records de la vraie vie gamifiés
4. **📬 Boss final : contact** — formulaire simple + trésor caché à trouver

### ✨ Effets « waouh » (un par prompt d'affinage)
- Curseur custom (épée ou fusée 🚀)
- Konami code → mode rainbow 10 s
- 5 clics sur l'avatar → danse pixel
- Confettis à chaque niveau débloqué
- Mode jour/nuit = « jour/nuit dans le jeu »

### 📈 Système de XP
- Compteur en `localStorage` : +10 XP par niveau visité, badge « Explorateur » si tout est débloqué
- Barre « Level X — Héros en herbe »

## 6. Contenus à préparer AVANT le premier prompt (checklist)

- [ ] Un pseudo (pas son vrai nom complet — voir §9)
- [ ] Un avatar pixel-art (5 min sur [Piskel](https://www.piskelapp.com), export PNG)
- [ ] 5 faits fun sur lui (dont 1 totalement absurde)
- [ ] 3 projets + 1 photo/description chacun
- [ ] Son meilleur « high score » (sport, jeu, note…)
- [ ] Une couleur dominante préférée

## 7. Stack — imposée par le vibe coding

| Besoin | Choix | Pourquoi |
|--------|-------|----------|
| **Tout** | **Un seul fichier `index.html`** | C'est le format naturel de sortie d'AI Studio : copier-coller, double-clic, ça marche. Zéro installation. |
| Style | CSS dans `<style>` | Modifié par prompts successifs |
| Interactivité | JavaScript dans `<script>` | Sons, XP, easter eggs |
| Hébergement | GitHub Pages ou Netlify (drag & drop du fichier) | Gratuit, en 2 min, fierté maximale |
| Images | PNG pixel-art légers ou emojis 🎨 | Pas de bibliothèque d'images lourde |

> ⚠️ **Décision clé : un seul fichier.** Multiplier les fichiers = multiplier les erreurs de copier-coller pour un débutant. Tout tient dans `index.html` jusqu'à la V2.

## 8. Le devlog — son cahier de bord de vibe codeur

Tableau simple (carnet ou doc) avec 3 colonnes :

| Prompt envoyé | Ce que ça a donné | Prochaine idée |
|---------------|-------------------|----------------|
| « Crée un site arcade rétro… » | Écran START super mais bouton ne marche pas | Demander de réparer le bouton |
| « Répare le bouton START » | ✅ Ça marche ! | Ajouter la carte monde |
| … | … | … |

**Objectif pédagogique :** à la fin, il peut relire ses 10–20 itérations et *comprendre comment il a construit son site* — sans avoir écrit une ligne de code à la main. C'est la vraie compétence du vibe coding.

## 9. Contraintes

- **Sécurité/privacy** : pseudo uniquement, pas de nom complet, d'adresse, de photo identifiable ou d'école sans accord parental
- **Accessibilité** : son coupé par défaut, contrastes lisibles, boutons grands
- **Taille** : le fichier reste léger (< 500 Ko) pour tourner partout, y compris le téléphone de mamie
- **Parental** : accord pour l'hébergement et tout contenu publié en ligne
- **Règle d'or des prompts** : après chaque modif, re-télécharger le **fichier entier** plutôt que patcher à la main — sinon la version diverge

## 10. MVP vs V2

**MVP (soirée 1)** — tout via AI Studio :
- Prompt fondateur → site complet de base
- 5 à 8 itérations d'affinage (boutons, couleurs, textes, 1 easter egg)
- Hébergement sur GitHub Pages

**V2 (sessions suivantes)** — toujours 100 % prompts :
- Système XP + badges complets
- Mode jour/nuit
- Un vrai mini-jeu jouable (snake ou dodge) intégré
- Multi-pages (`projets.html`…) si le fichier devient trop chargé

## 11. Le Prompt Fondateur 🚀 (à copier-coller tel quel dans AI Studio)

```
Crée un site web complet pour un garçon de 12 ans, en un seul fichier HTML 
autonome (HTML + CSS + JS inline). Thème : borne d'arcade rétro pixel-art, 
écran d'accueil avec un logo "PIXELQUEST" en néon clignotant et un bouton 
"INSERT COIN / START" qui lance un son 8-bit et affiche une carte-monde. 
Sur cette carte, un avatar pixel-art (utilise un emoji 🧑‍🚀 en attendant) 
peut aller dans 4 zones : "Qui suis-je ?" (cartes animées de présentation), 
"Mes projets" (3 projets à débloquer par un clic), "Mes high scores" 
(badges), et "Contact" (formulaire simple). Ajoute : un compteur d'XP en 
localStorage (+10 par zone visitée), un bouton pour couper le son, un 
mode jour/nuit, et au moins 1 easter egg (le code Konami ↑↑↓↓←→←→BA 
active un mode rainbow). Style : pixels, néons, palette bleu nuit + 
violet + cyan, animations CSS uniquement. Mets des textes temporaires 
fun et faciles à remplacer. Tout doit fonctionner en double-cliquant 
sur le fichier, sans serveur ni dépendance externe.
```

**Ensuite, la boucle :** tester → noter → *« Garde tout et change seulement… »* → retester.

## 12. Définition du succès

Le site est réussi si : **il est fier de le montrer à sa classe le lendemain, et s'il peut expliquer comment il l'a obtenu — prompt après prompt.** 🏆

[[PRD - Site Web Pixel Art - 15 Prompts]]