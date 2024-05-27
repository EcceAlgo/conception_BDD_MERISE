## Contexte

Nous avons pour objectif de fournir un systeme de gestion de formations organisés en modules. Cette dernière a pour but d'elaborer correctement le suivi et la validation des formations dispensés par les formateurs aux apprenants.

# Règle de Gestion : Organisation des Formations en Modules

## Caractéristiques des Modules

- **Numéro de Module** : Sous forme de Semantic Versioning (ex : 1.0.0).
- **Intitulé** : Titre du module.
- **Objectif Pédagogique** : Description de l'objectif du module.
- **Contenu** : Peut inclure des textes, images et vidéos.
- **Durée** : En heures.
- **Tags** : Un ou plusieurs tags pour catégoriser le module.
- **Auteur** : Le formateur qui a créé le module.

## Associations des Modules

- Un module peut faire partie d'une ou plusieurs formations. 
  - Exemple : Le module "Commandes de base Git" peut faire partie des formations "Frontend Javascript" et "DevOps", entre autres.

## Contenu des Modules

- Un module peut contenir :
  - Un texte.
  - Une image.
  - Une vidéo.

## Inscription et Suivi des Apprenants

- **Inscription** : Les apprenants peuvent s'inscrire à une ou plusieurs formations.
- **Choix des Modules** : Les apprenants peuvent choisir de ne pas suivre certains modules s'ils possèdent déjà les compétences correspondantes. Ils peuvent valider les modules de leur choix en un clic.
- **Évaluation** :
  - Chaque apprenant est évalué pour chaque module.
  - État de fin de module : OK / KO.

## Achèvement d'une Formation

- Une formation est considérée comme terminée lorsque tous les modules ont été validés.

## Caractéristiques des Apprenants

- **Numéro d'inscription** : Unique pour chaque apprenant.
- **Nom** : Nom de l'apprenant.
- **Prénom** : Prénom de l'apprenant.
- **Adresse** : Adresse de l'apprenant.
- **Date de Naissance** : Date de naissance de l'apprenant.

## Caractéristiques des Formateurs

- **Code** : Identifiant unique du formateur.
- **Nom** : Nom du formateur.
- **Prénom** : Prénom du formateur.
- **Auteur** : Le formateur est auteur d'un module pour une formation donnée.