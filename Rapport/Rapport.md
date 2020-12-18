# Smartphone To Virtuality
## Auteurs
Clément Malléjac
Charles Cogoluègnes
Maël Le Gal
Samuel Le Berre
## Introduction
Le projet Smartphone To Virtuality a pour but de représenter un téléphone dans un environement virtuel, que ce soit par un hololens ou un casque de réalité virtuelle, pour qu'il soit affichable en jeu.
On cherche donc a trouver le téléphone dans le monde réel et donc a reconnaitre son positionnement, afin de pouvoir déterminer sa position nous utiliserons 3 camera webcam logitech.
Elle seront disposé à 3 mètres de distance les une des autres, formant un triangle équilatérale comme visible sur la figure 1, permettant la capture d'une zone de 9 m².  
![alt text](/Rapport/assets/images/position_camera.png "Figure 1 : Position des caméras dans la pièces")

## Reconnaissance
### Positionnement du téléphone
La première approche de la reconnaisance du smartphone dans le monde réel à été d'utiliser darknet, cependant darknet requiere l'utilisation de Cuda et de OpenCV. Hors l'installation de Cuda nous aura posé de nombreux problème bloquant l'utilisation de darknet pendant 3 semaines.
N'ayant toujours pas réussiit à installer correctement Cuda, nous avons décidé d'abandonner l'utilisation de darknet et de nous concentrer sur la reconnaissance grâce à 
### Reconstruction du positonement en 3D
**Partie a voir avec Mael**
## Serveur
Nous avons mis en place un serveur UDP afin de recupéré les données des capteurs. L'utilisation d'un serveur UDP nous a parus la plus pertinente car les données doivent transitter rapidement.
## Capteur
Afin de représenté correctement le téléphone dans l'environnement virtuel, il est nécessaire d'utilisé les capteurs dont dispose le téléphone.
Pour permettre à notre application de se servire des capteurs nous avons créer une application mobile. 
Cette application va mettre en place un service qui va tourner en fond et qui permettra l'envoie des données des capteurs au serveur. Le fait d'utiliser un service permet à l'utilisateur de pouvoir vérouiller son téléphone et de toujours transmettre les données au serveur.
Dans le but d'utiliser au mieux les différentes données sans pour autant surchargé l'envoie de ces dernières. 
Nous avons décidé de nous concentrés sur la récupération de 3 capteurs que nous avons jugés élémentaires.

### Accélération Linéaire
Les deux premiers capteurs servent à déterminé si le téléphone est en mouvement ainsi que son sens d'orientation.
### Rotation

### Proximité
Le capteur de proximité quant à lui va nous aider à savoir si le téléphone est par exemple dans une poche ou si il est caché par un objet posé dessus, ou encore contre l'oreille de l'utilisateur. Ces cas nous permettent déjà de savoir dans qu'elle circonstance une reconnaissance du téléphone peut échouer.
Cependant un autre cas de figure impliquerait que le téléphone est posé, par exemple sur une table, mais l'écran contre la surface trompant le capteur qui afficherait que le telphone est proche d'un objet nommé plus haut.
Lors de la réalisaation de l'application, nous avons pu observé que tous les téléphones mobiles non pas les même valeurs affectés au capteur de proximité.  
Par exemple, un Samsung Galaxy s9 va avoir 2 valeurs :
* 0 :  quand le capteur detecte un objet proche 
* 8 :  lorsque rien n'est détecté  

Tandis qu'un Motorola Moto G5 va avoir 3 valeurs possibles : 
* 1 : un élément très proche est détecté
* 3 : un élément moyennement proche est détecté
* 8 : rien n'est détecté 

Pour supprimer ce problème de valeurs qui sont définies par les constructeur et non par le système d'exploitation et en prenant en compte les valeurs que nous avons pu observer. Nous aons déterminer que plus la valeur est petite et plus un objet est proche du capteur.
Nous avons donc utiliser une normalisation des valeurs en prenant toute les valeurs observer lors de l'exécution de l'application et en normalisant les nouvelles valeurs perçut.

 
## Application

## Résultat

## Conclusion
