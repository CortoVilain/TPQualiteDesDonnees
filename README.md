# Contexte

  L’objectif de ce TP est de déterminer à partir de deux jeux de données la capitale européenne dont les données de température sont fournis dans le fichier suivant : [Climat_si.csv](https://github.com/CortoVilain/TPQualiteDesDonnees/blob/main/climat_si.csv)

# Outils utilisés

CSV de base : (https://github.com/CortoVilain/TPQualiteDesDonnees/blob/main/climat_si.csv)

Dans un premier temps, nous avons récupéré le fichier csv contenant les données à traiter.
Nous avons supprimé les lignes 1,2, 4 qui sont des lignes qui ne comportent aucune donnée à traiter mais des informations parasites. 
De même pour la ligne 42 à la ligne 52, ainsi que pour la colonne A,B et C.

De ce fait, nous avons le jeu de données suivant : 




Traitement pour obtenir des données homogènes 

Dans un second temps, nous avons importé le fichier csv à google colab. Cependant certaines données étaient au format int, d'autres étaient au format float. Nous avons donc converti l’ensemble des données en float pour pouvoir faire des analyses statistiques.



Calcul de la moyenne par mois 

Pour calculer la moyenne, nous avons utilisé la librairie numpy, et la fonction np.mean().




# Démarche de résolution

