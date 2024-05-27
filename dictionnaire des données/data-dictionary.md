# Dictionnaire de Données

### Table : Modules
| Code                        | Information                              | Type            | Exemple                             |
|-----------------------------|------------------------------------------|-----------------|-------------------------------------|
| id_module                   | Identifiant unique du module             | INTEGER         | 1                                   |
| version                     | Numéro de version du module au format sémantique | VARCHAR(10)     | 1.0.0                               |
| intitule                    | Intitulé du module                       | VARCHAR(255)    | Commandes de base Git               |
| objectif_pedagogique        | Objectif pédagogique du module           | TEXT            | Apprendre les commandes de base de Git |
| contenu_texte               | Contenu textuel du module                | TEXT            | Description des commandes Git       |
| contenu_image               | Lien vers l'image du module              | VARCHAR(255)    | https://example.com/image.jpg       |
| contenu_video               | Lien vers la vidéo du module             | VARCHAR(255)    | https://example.com/video.mp4       |
| duree                       | Durée du module en heures                | INTEGER         | 4                                   |
| tags                        | Liste de tags associés au module, séparés par des virgules | VARCHAR(255)    | Git, Commandes                      |
| auteur_id                   | Identifiant du formateur auteur du module | INTEGER         | 123                                 |

### Table : Formations
| Code                        | Information                              | Type            | Exemple                             |
|-----------------------------|------------------------------------------|-----------------|-------------------------------------|
| id_formation                | Identifiant unique de la formation       | INTEGER         | 1                                   |
| intitule                    | Intitulé de la formation                 | VARCHAR(255)    | Frontend Javascript                 |

### Table : Formation_Modules
| Code                        | Information                              | Type            | Exemple                             |
|-----------------------------|------------------------------------------|-----------------|-------------------------------------|
| id_formation_module         | Identifiant unique de l'association formation-module | INTEGER         | 1                                   |
| formation_id                | Identifiant de la formation              | INTEGER         | 1                                   |
| module_id                   | Identifiant du module                    | INTEGER         | 1                                   |

### Table : Apprenants
| Code                        | Information                              | Type            | Exemple                             |
|-----------------------------|------------------------------------------|-----------------|-------------------------------------|
| id_apprenant                | Identifiant unique de l'apprenant        | INTEGER         | 456                                 |
| numero_inscription          | Numéro d'inscription unique de l'apprenant | VARCHAR(50)     | A123456                             |
| nom                         | Nom de l'apprenant                       | VARCHAR(255)    | Tyson                            |
| prenom                      | Prénom de l'apprenant                    | VARCHAR(255)    | Fury                               |
| adresse                     | Adresse de l'apprenant                   | VARCHAR(255)    | 16 Place de la Victoire, 37200 Tours      |
| date_naissance              | Date de naissance de l'apprenant         | DATE            | 2003-03-21                          |

### Table : Apprenant_Formations
| Code                        | Information                              | Type            | Exemple                             |
|-----------------------------|------------------------------------------|-----------------|-------------------------------------|
| id_apprenant_formation      | Identifiant unique de l'inscription apprenant-formation | INTEGER         | 1                                   |
| apprenant_id                | Identifiant de l'apprenant               | INTEGER         | 456                                 |
| formation_id                | Identifiant de la formation              | INTEGER         | 1                                   |

### Table : Apprenant_Modules
| Code                        | Information                              | Type            | Exemple                             |
|-----------------------------|------------------------------------------|-----------------|-------------------------------------|
| id_apprenant_module         | Identifiant unique de l'inscription apprenant-module | INTEGER         | 1                                   |
| apprenant_id                | Identifiant de l'apprenant               | INTEGER         | 456                                 |
| module_id                   | Identifiant du module                    | INTEGER         | 1                                   |
| etat_fin_module             | État de fin du module (true = OK, false = KO) | BOOLEAN         | true                                |

### Table : Formateurs
| Code                        | Information                              | Type            | Exemple                             |
|-----------------------------|------------------------------------------|-----------------|-------------------------------------|
| id_formateur                | Identifiant unique du formateur          | INTEGER         | 123                                 |
| code                        | Code unique du formateur                 | VARCHAR(50)     | F123                                |
| nom                         | Nom du formateur                         | VARCHAR(255)    | Martin                              |
| prenom                      | Prénom du formateur                      | VARCHAR(255)    | Ruy                              |
