CREATE TABLE Person(
   uuid INT AUTO_INCREMENT,
   nom VARCHAR(50) NOT NULL,
   prenom VARCHAR(50) NOT NULL,
   date_naissance DATE NOT NULL,
   adresse VARCHAR(100) NOT NULL,
   PRIMARY KEY(uuid)
);

CREATE TABLE Apprenant(
   id_apprenant INT AUTO_INCREMENT,
   uuid INT NOT NULL,
   PRIMARY KEY(id_apprenant),
   UNIQUE(uuid),
   FOREIGN KEY(uuid) REFERENCES Person(uuid)
);

CREATE TABLE Formateur(
   id_formateur INT AUTO_INCREMENT,
   code VARCHAR(50) NOT NULL,
   uuid INT NOT NULL,
   PRIMARY KEY(id_formateur),
   UNIQUE(uuid),
   UNIQUE(code),
   FOREIGN KEY(uuid) REFERENCES Person(uuid)
);

CREATE TABLE Module_(
   id_module INT AUTO_INCREMENT,
   intitule VARCHAR(100) NOT NULL,
   objectif_pedagogique VARCHAR(255) NOT NULL,
   version VARCHAR(20),
   date_creation DATETIME NOT NULL,
   duree TIME NOT NULL,
   tags VARCHAR(255) NOT NULL,
   PRIMARY KEY(id_module)
);

CREATE TABLE Formation(
   id_formation INT AUTO_INCREMENT,
   titre VARCHAR(100) NOT NULL,
   PRIMARY KEY(id_formation),
   UNIQUE(titre)
);

CREATE TABLE Contenu(
   id_contenu INT AUTO_INCREMENT,
   image VARCHAR(255),
   video VARCHAR(255),
   texte TEXT,
   PRIMARY KEY(id_contenu)
);

CREATE TABLE Suivre(
   id_apprenant INT,
   id_formation INT,
   PRIMARY KEY(id_apprenant, id_formation),
   FOREIGN KEY(id_apprenant) REFERENCES Apprenant(id_apprenant),
   FOREIGN KEY(id_formation) REFERENCES Formation(id_formation)
);

CREATE TABLE Composer(
   id_module INT,
   id_formation INT,
   PRIMARY KEY(id_module, id_formation),
   FOREIGN KEY(id_module) REFERENCES Module_(id_module),
   FOREIGN KEY(id_formation) REFERENCES Formation(id_formation)
);

CREATE TABLE Valider(
   id_apprenant INT,
   id_module INT,
   evaluation BOOLEAN NOT NULL,
   PRIMARY KEY(id_apprenant, id_module),
   FOREIGN KEY(id_apprenant) REFERENCES Apprenant(id_apprenant),
   FOREIGN KEY(id_module) REFERENCES Module_(id_module)
);

CREATE TABLE Gerer(
   id_formateur INT,
   id_module INT,
   date_modification DATETIME,
   PRIMARY KEY(id_formateur, id_module),
   FOREIGN KEY(id_formateur) REFERENCES Formateur(id_formateur),
   FOREIGN KEY(id_module) REFERENCES Module_(id_module)
);

CREATE TABLE Constituer(
   id_module INT,
   id_contenu INT,
   PRIMARY KEY(id_module, id_contenu),
   FOREIGN KEY(id_module) REFERENCES Module_(id_module),
   FOREIGN KEY(id_contenu) REFERENCES Contenu(id_contenu)
);
