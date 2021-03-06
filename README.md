# 33188 Capteur de pression differentielle GROVE

CAPTEUR DE PRESSION DIFFÉRENTIELLE AU FORMAT GROVE [33188](https://www.pierron.fr/capteur-de-pression-dans-un-liquide.html)

Caractéristiques techniques :
- Alimentation : 3,3 à 5 V
- Plage de mesure : 0 à 50 kPa

![33188](/img/L-33188.png)

# Installation dans IDE Arduino:
Créer un nouveau répertoire nommé "Pierron_33188" dans le dossier "libraries" de votre dossier Arduino.
Y placer tous les fichiers.
ou
Télécharger le dépôt en ZIP et dans l'IDE Arduino : Croquis / inclure bibliothèque / ajouter la bibliothèque ZIP.

# Usage :
Pour utiliser la librairie dans votre propre projet, importez-la avec  *Sketch > Import Library*.

# RESSOURCES À TÉLÉCHARGER :

Ressource utilisation : [MPX2202](https://github.com/pierron-asco-celda/Pierron_33188/blob/master/src/Pierron-33188-Datasheet.pdf)

# Schémas :

![SCH-33188](/img/SCH-33188.png)

![BRD-33188](/img/BRD-33188.png)

# Exemple :
### Arduino / C++
```cpp
/*
    ** Mesure pression differentielle module Grove **
       Moniteur série -> Baud rate 9600.*
*/
#include "Pierron_33188.h"

Pierron_33188 capteur = new Pierron_33188();

void setup(){
  Serial.begin(9600);
  Serial.println("Calibration du capteur.\nAppuyer sur une touche pour continuer.");
  while (Serial.available() == 0) {
    // Wait for User to Input Data
  }
  capteur.calibre();
}

void loop(){
  float p = capteur.read();
  Serial.print("Pression : ");
  Serial.print(p);
  Serial.println(" hPa");
  delay(1000);
}
```
## À propos :
<div style="text-align: justify">*Le débit en bauds est un taux de transfert de données en unités de bits par seconde (bps). Si le débit en bauds est de 9600, cela signifie que la possibilité d’envoyer des données est de 9600 bits en une seconde. 1 caractère est identique à 1 octet.</div>
<br>
PIERRON ASCO-CELDA (https://www.pierron.fr/).
