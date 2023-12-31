# Script d'upload de données dans un bucket Minio

Ce petit dépôt a pour objectif de donner les éléments aux producteurs de données devant publier les données via notre cluster Minio.

## Installation

```
pip install -r requirements.txt
```

Copy du fichier config_example.py

```
cp config_example.py config.py
```

Vous devez ensuite remplir les config que nous vous avons fournis par ailleurs

Pour les variables liées à data.gouv.fr, vous devez configurer les variables `DATAGOUV_URL` (`https://demo.data.gouv.fr` pour l'espace démo ou `https://www.data.gouv.fr` pour l'espace de production), le token `DATAGOUV_TOKEN` que vous pouvez trouver sur votre espace administration `https://www.data.gouv.fr/fr/admin/me/` (vous devez le générer une première fois si c'est la première fois que vous utilisez l'api), `DATASET_ID` qui est l'identifiant du dataset, disponible dans l'onglet "Informations" de la page Jeu de données (ex: https://www.data.gouv.fr/fr/datasets/liste-des-api-disponibles-sur-le-catalogue-api-gouv-fr/#/information), `RESOURCE_ID` qui est l'identifiant de la ressource, que vous pouvez trouver dans les métadonnées d'une ressource (URL Stable, ne prendre que l'identifiant final, par exemple `73b55ca6-58f4-4930-91dd-983567ae83ab` pour https://www.data.gouv.fr/fr/datasets/r/73b55ca6-58f4-4930-91dd-983567ae83ab)

## Utilisation

```
python upload_and_publish_file.py
```

Le fichier test.csv du dépôt est alors stocké sur le bucket spécifié et référencés sur data.gouv.fr.