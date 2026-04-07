# Algorithme de Transposition pour Guitare : Contourner les Accords Barrés

L'apprentissage de la guitare se heurte souvent à un obstacle biomécanique majeur : les accords barrés. Ce dépôt présente une solution algorithmique basée sur l'arithmétique modulaire pour simplifier n'importe quelle grille d'accords ou tablature.

▶️ **Testez l'algorithme en direct sur notre outil interactif : [Le Transposeur Magique d'Accords](https://transposeur.guitaretoday.com/)**

▶️ **Passez à la vitesse supérieure avec la méthode visuelle : [Adieu les barrés à la guitare (La méthode numérique)](https://store.guitaretoday.com/downloads/adieu-les-barres-a-la-guitare-la-methode-visuelle-guide-numerique-video/)**

---

## 📄 Le Document PDF (Livre Blanc)

Ce dépôt héberge le document de référence détaillant cette logique d'optimisation. Il s'adresse aux musiciens souhaitant comprendre l'architecture de leur manche, ainsi qu'aux développeurs voulant implémenter des fonctions de transposition musicales.

👉 **[Consulter ou télécharger le PDF complet ici : Algorithme-Transposition-accords-Guitare.pdf](./Algorithme-Transposition-accords-Guitare.pdf)**

---

## 🎯 Le Concept : Musique et Ergonomie

En guitare acoustique ou électrique, un accord "barré" (comme le Fa majeur ou le Si mineur) exige une force de pince importante qui génère des douleurs, de la fatigue et un blocage rythmique chez les débutants. Plutôt que de forcer sur les articulations, nous utilisons la théorie musicale et les mathématiques pour modifier la tonalité matérielle de l'instrument grâce à un **capodastre**.

## 🧮 La Logique de Transposition (Modulo 12)

La musique occidentale divise l'octave en 12 demi-tons équidistants. Nous modélisons l'espace musical sous forme d'un tableau indexé (Array) de base 12 :
`["C", "C#", "D", "D#", "E", "F", "F#", "G", "G#", "A", "A#", "B"]`

Lorsqu'un guitariste place un capodastre sur la case `n` de son manche, il augmente la fréquence de toutes les cordes. Pour conserver la tonalité originale d'une chanson et pouvoir chanter par-dessus, il faut décaler chaque accord de la partition initiale de `-n` demi-tons.

La transposition se résout via une équation d'arithmétique modulaire simple pour éviter les index négatifs ou hors limites lors du calcul :

`index_nouveau = (index_original - capo + 12) % 12`

### L'Algorithme d'Optimisation du Capodastre

Le but du script n'est pas seulement de transposer, mais de déterminer la position **ergonomique optimale**. L'algorithme attribue un système de scoring à chaque position possible sur le manche (généralement de la frette 0 à la frette 7) :

* **Points positifs :** L'accord généré est une fondamentale "ouverte" facile à jouer (C, D, E, G, A) ou un accord de base récurrent (Am, Em).
* **Points négatifs :** Le décalage mathématique génère un nouvel accord barré complexe, annulant le bénéfice du capodastre.

La boucle évalue les combinaisons et retourne la variable `bestCapo` ayant le score cumulé le plus élevé.

## 🛠 Intégration Web (Open Source Mindset)

Si vous administrez un site de tablatures, un éditeur de paroles ou un blog musical, épargnez le calcul mental complexe à vos utilisateurs. 

Voici un snippet HTML pur, prêt à l'emploi, à intégrer dans vos pages web pour proposer un lien vers la transposition automatique à vos visiteurs :

```html
<div style="text-align: center; margin: 20px 0;">
  <a href="[https://transposeur.guitaretoday.com/](https://transposeur.guitaretoday.com/)" target="_blank" style="background-color: #2c3e50; color: white; padding: 12px 24px; text-decoration: none; border-radius: 5px; font-weight: bold; font-family: sans-serif; display: inline-block; box-shadow: 0 4px 6px rgba(0,0,0,0.1);">
    🎸 Simplifier ces accords (Calculateur Capodastre)
  </a>
</div>
# Algorithme-transpisition-accords-guitare
Algorithme de transposition d'accords guitare
