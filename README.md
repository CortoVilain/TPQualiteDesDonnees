# Contexte

  L’objectif de ce TP est de déterminer à partir de deux jeux de données la capitale européenne dont les données de température sont fournis dans le fichier suivant : [Climat_si.csv](https://github.com/CortoVilain/TPQualiteDesDonnees/blob/main/climat_si.csv)

# Outils utilisés

Google Colab : 
Nous avons choisi d’utiliser Google Colab, car c’est un outil collaboratif, il nous a permis de travailler en groupe sur un fichier commun, et permet donc de garantir l’intégrité dans le code pour l’ensemble de l’équipe. 

Numpy :
Cette librairie permet d’effectuer des calculs numériques avec Python. Elle introduit une gestion facilitée des tableaux de nombres.

Panda : 
Pandas est une bibliothèque écrite pour le langage de programmation Python, destiné à être le meilleur outil statistique qui soit aussi bien performant, facile d'utilisation et flexible. Cette librairie à l’avantage de pouvoir récupérer des données depuis n’importe quel support (fichiers CSV, tableaux Excel, des pages web, etc…). Cette librairie peut également grouper, découper, alléger, déplacer, écrire les données.


# Démarche de résolution

CSV de base : [Climat_si.csv](https://github.com/CortoVilain/TPQualiteDesDonnees/blob/main/climat_si.csv)

Dans un premier temps, nous avons récupéré le fichier csv contenant les données à traiter.
Nous avons supprimé les lignes 1,2, 4 qui sont des lignes qui ne comportent aucune donnée à traiter mais des informations parasites. 
De même pour la ligne 42 à la ligne 52, ainsi que pour la colonne A,B et C.

De ce fait, nous avons le jeu de données suivant : 

![](https://www.infolux.fr/wp-content/uploads/2021/02/1.png)


**Traitement pour obtenir des données homogènes**

Dans un second temps, nous avons importé le fichier csv à google colab. Cependant certaines données étaient au format int, d'autres étaient au format float. Nous avons donc converti l’ensemble des données en float pour pouvoir faire des analyses statistiques.



**Calcul de la moyenne par mois**

Pour calculer la moyenne, nous avons utilisé la librairie numpy, et la fonction np.mean().

![](https://www.infolux.fr/wp-content/uploads/2021/02/2.png)

**Calcul de l’écart type par mois** 

Pour calculer la moyenne, nous avons utilisé la librairie numpy, et la fonction np.std().

![](https://www.infolux.fr/wp-content/uploads/2021/02/3.png)

**Calcul du minimum par mois**

Pour calculer la moyenne, nous avons utilisé la librairie numpy, et la fonction np.min().

![](https://www.infolux.fr/wp-content/uploads/2021/02/4.png)

**Calcul du maximum par mois**

Pour calculer la moyenne, nous avons utilisé la librairie numpy, et la fonction np.max().

![](https://www.infolux.fr/wp-content/uploads/2021/02/5.png)

**Calcul du maximum de l’année**

Pour calculer la moyenne, nous avons utilisé la librairie numpy, et la fonction np.nanmax(). Cette fonction permet d’ignorer les valeurs NaN afin d’éviter de fausser les calculs statistiques.

![](https://www.infolux.fr/wp-content/uploads/2021/02/6.png)

**Calcul du minimum de l’année**

Pour calculer la moyenne, nous avons utilisé la librairie numpy, et la fonction np.nanmin(). Cette fonction permet d’ignorer les valeurs NaN afin d’éviter de fausser les calculs statistiques.

![](https://www.infolux.fr/wp-content/uploads/2021/02/7.png)

**Affichage des courbes par mois**

Pour l’affichage des courbes par mois, nous avons utilisé la librairie pyplot de matplotlib.
Elle permet des visualisations statiques, animées et interactives.

![](https://www.infolux.fr/wp-content/uploads/2021/02/8.png)
![](https://www.infolux.fr/wp-content/uploads/2021/02/9.png)
![](https://www.infolux.fr/wp-content/uploads/2021/02/10.png)
![](https://www.infolux.fr/wp-content/uploads/2021/02/11.png)
![](https://www.infolux.fr/wp-content/uploads/2021/02/12.png)
![](https://www.infolux.fr/wp-content/uploads/2021/02/13.png)
![](https://www.infolux.fr/wp-content/uploads/2021/02/14.png)
![](https://www.infolux.fr/wp-content/uploads/2021/02/15.png)
![](https://www.infolux.fr/wp-content/uploads/2021/02/16.png)
![](https://www.infolux.fr/wp-content/uploads/2021/02/17.png)
![](https://www.infolux.fr/wp-content/uploads/2021/02/18.png)
![](https://www.infolux.fr/wp-content/uploads/2021/02/19.png)
![](https://www.infolux.fr/wp-content/uploads/2021/02/20.png)
![](https://www.infolux.fr/wp-content/uploads/2021/02/21.png)


**Affichage de la courbe annuelle**

Pour l’affichage des courbes par mois, nous avons utilisé la librairie pyplot de matplotlib.
Elle permet des visualisations statiques, animées et interactives.

Nous avons créé un tableau regroupant les données ne comportant pas de NaN pour éviter les trous dans la courbe. En effet les mois ne comportant pas 31 jours comportent des valeurs NaN qui fausseraient la représentation de la courbe.

![](https://www.infolux.fr/wp-content/uploads/2021/02/22.png)

**Affichage de la courbe à l’aide du pointeur**

Pour afficher les courbes annuelles à l’aide du pointeur, nous avons utilisé la librairie express de plotly.

![](https://www.infolux.fr/wp-content/uploads/2021/02/23.png)
![](https://www.infolux.fr/wp-content/uploads/2021/02/24.png)

II / Jeu de données avec erreur
CSV avec des erreurs : [si-erreur.csv](https://github.com/CortoVilain/TPQualiteDesDonnees/blob/main/si-erreur.csv)


Un jeu de données avec erreur a été fourni. Le but est, comme pour la première partie, de parcourir les valeurs du CSV pour les convertir dans un même type de données float lorsque cela est possible.
Si cela n’est pas possible, ça veut dire que la donnée est une erreur et qu’il faut déterminer un valeure fictive pour garder une homogénéité dans les données.
Pour ce faire, ces valeurs sont remplacées par une valeur aléatoire calculée grâce à la formule suivante :
“Moyenne* - Écart type* < Valeur décimale aléatoire < Moyenne* + Écart type*”

*La moyenne et l’écart type sont calculés à partir des données à -5 et +5 jours de la valeur à calculer.
