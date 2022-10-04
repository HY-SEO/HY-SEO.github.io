# Phonetisaurus

## Général 
- Les dictionnaires utilisés ici sont des versions corrigées. Les symboles phonétiques ont été modifiés pour que les trois dictionnaires puissent avoir les même symboles. Le désaccord entre les dictionnaires au niveau d'ouverture des voyelles, c'est-à-dire la différence entre o ouvert et o fermé, e ouvert et e fermé, n'a pas été corrigé, car ceci varie selon différent facteurs : région, âge, sexe, pays....
## Jeux de données
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

- ****ZAION-bis : Il s'agit d'un codage version corrigé du son nasale palatale [gn](/ɲ/ en API).
---
Voir la liste de codage complète : https://zaionai.sharepoint.com/:x:/s/Labellisation/EUff57DXioFHorkFjy6WoOoB17gBZaOCqWb-0zTdLY6ljw?e=eBH6O7&wdLOR=cB946B4A4-1527-4275-9003-3A3083451BD9 

### ZAION
Le dictionnaire de phonétisation de Zaion (Grand) est issu du modèle entraîné avec le dictionnaire de Zaion (Petit). Comme ceci est le résultat de prédiction, il existe des phonétisations erronées. Certaines fautes sont corrigées.
### Lexique4Linguiste
Le dictionnaire de Lexique4Linguistes est une base de données lexicale française au format xml en droit libre. https://www.ortolang.fr/market/lexicons/lexique4linguists Plusieurs informations sont liés à un mot : Genre, nombre, mode, temps, personnes, fréquence, prononciation. Ce dictionnaire au format xml utilise un codage spécial qui est ni API, ni SAMPA. 
### FrWikitionnaire
### 
## Entraînement
### Dictionnaire 1 (DICT1)
Lorsque les trois dictionnaires (ZAION, Lexique4, FrWikitionnaire) sont en accord au niveau de phonétisation d'un mot, on peut considérer que 
### Dictionnaire 2 (DICT2)
Le DICT2 est le résultat de concaténation de DICT1 et les intersections de chaque 2 dictionnaires de phonétisation. C'est-à-dire que
### Dictionnaire 3 (DICT3)
Le DICT3 est l'ensemble de tous les trois dictionnaires ZAION, Lexique4 et FrWikitionnaire. 
## Résultat & Performance
