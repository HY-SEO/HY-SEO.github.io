# Phonetisaurus 
### 3 modèles de phonétisation du français


## Général 
#### Dictionnaires brut (Zaion Grand, Lexique4Linguistes, FrWikitionnaire) 👉 Correction/Modification des dictionnaires 👉 Préparation des jeux de données Train (DICT1, DICT2, DICT3)/Test :point_right: Entraînement de trois modèles 👉 Test et Evaluation 
- Les dictionnaires utilisés ici sont issu des versions corrigées. Les symboles phonétiques ont été modifiés pour que les trois dictionnaires puissent avoir les même symboles afin de les comparer. Le désaccord au niveau d'ouverture des voyelles, c'est-à-dire la différence entre o ouvert et o fermé, e ouvert et e fermé, n'a pas été corrigé, car ceci varie en fonction des facteurs d'un locuteur à l'autre : région, âge, sexe, pays....


### Jeux de données
Les 3 dictionnaires de phonétisation utilisé ici ont des sources différentes. Voici le tableau récapitulatif.
||ZAION|Lexique4Linguistes|FrWikitionnaire|
|---|---|---|---|
|Format original|.dict|.xml|.json||Format final|
|Format final|.dict|.dict|.dict|
|Codage original|ZAION*|Lexique4**|API***|
|Codage final|ZAION-bis****|ZAION-bis|ZAION-bis|
|NBphonétisation final|523920|162399|565172|

- *ZAION utilise le codage issu de Lexique4Linguiste mais modifié.

- **Lexique4Linguiste utilise leur codage spécifique http://www.lexique.org/?page_id=286 qui ressemble à SAMPA.

- ***API : Alphabet Phonétique International (IPA en anglais)

- ****ZAION-bis : Il s'agit d'un codage version de Zaion corrigé concernant au son nasale palatale [gn](/ɲ/ en API).
---
Voir la liste de codage complète : https://zaionai.sharepoint.com/:x:/s/Labellisation/EUff57DXioFHorkFjy6WoOoB17gBZaOCqWb-0zTdLY6ljw?e=eBH6O7&wdLOR=cB946B4A4-1527-4275-9003-3A3083451BD9 

### ZAION
Le dictionnaire de phonétisation de Zaion (Grand) est la prédiction du modèle entraîné avec le dictionnaire de Zaion (Petit). Comme ceci est le résultat de prédiction, il existe des phonétisations erronées. Certaines fautes ont été corrigées. Le petit dictionnaire de ZAION est basé sur le corpus Lexique3.83 qui est un dictionnaire de prototype de Lexique4Linguistes. Par conséquent, le dictionnaire ZAION et le dictionnaire Lexique4Linguistes sont plutôt en accord au niveau phonétisation par défaut.
### Lexique4Linguistes
Le dictionnaire de Lexique4Linguistes est une base de données lexicale française au format xml en droit libre. https://www.ortolang.fr/market/lexicons/lexique4linguists Plusieurs informations sont liés à un mot : Genre, nombre, mode, temps, personnes, fréquence, prononciation.  Ce dictionnaire au format xml utilise un codage spécial qui n'est pas API, ni SAMPA 👉 http://www.lexique.org/?page_id=286 
### FrWikitionnaire
Ce dictionnaire contient le plus d'entrée parmis les trois.  
### 
## Entraînement
### DICT 1 (dict1.dict) => MODEL1 (dict1.fst)
Le dict1 est l'ensemble des mots et des phonétisations lorsque le dictionnaire de ZAION, Lexique4 et Frwiki sont complètement en accord au niveau de phonétisation. On peut considérer que ce dictionnaire 1 est le plus propre 
### DICT 2 (dict2.dict) => MODEL2 (dict2.fst)
Le DICT2 est le résultat de concaténation de DICT1 et les intersections de chaque 2 dictionnaires de phonétisation. C'est-à-dire que
### DICT 3 (dict3.dict) => MODEL3 (dict3.fst)
Le DICT3 est l'ensemble de tous les trois dictionnaires ZAION, Lexique4 et FrWikitionnaire. 

## Utilisation des modèles 
```
$ phonetisaurus-apply --model nom_model.fst --word_list mots.wlist
```
Pour appliquer le model, il faut une liste de mots sans phonétisation. Cette liste de mot doit être composé un mot par ligne, divisé avec retour chariot. Le format du ce fichier sera ```.wlist```.


- Exemple du fichier wlist 👇
``` 
étudiant
ordinateur
france
```
- Exemple de résultat d'application du modèle 👇
```
étudiant  e t y d j @
ordinateur o R d i n a t neuf R
france f R @ s
```
Le délimiteur de mot et phonétisation sera une tabulation.
