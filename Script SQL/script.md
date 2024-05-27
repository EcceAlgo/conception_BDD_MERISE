CREATE TABLE Apprenant(
   Id_Apprenant COUNTER,
   UUID VARCHAR(50),
   Nom VARCHAR(50),
   Adresse VARCHAR(50) NOT NULL,
   Prenom VARCHAR(50),
   PRIMARY KEY(Id_Apprenant, UUID)
);

CREATE TABLE Module_(
   Id_Module COUNTER,
   Version VARCHAR(50) NOT NULL,
   Objectif VARCHAR(50) NOT NULL,
   Titre VARCHAR(50) NOT NULL,
   Duree INT NOT NULL,
   Tags VARCHAR(50) NOT NULL,
   PRIMARY KEY(Id_Module)
);

CREATE TABLE Formation(
   Id_Formation COUNTER,
   Titre VARCHAR(50),
   PRIMARY KEY(Id_Formation)
);

CREATE TABLE Contenu(
   Id_Contenu COUNTER,
   Texte VARCHAR(50),
   Image VARCHAR(50),
   Video VARCHAR(50),
   PRIMARY KEY(Id_Contenu),
   UNIQUE(Texte),
   UNIQUE(Image),
   UNIQUE(Video)
);

CREATE TABLE Formateur(
   UUID VARCHAR(50),
   Id_Formateur COUNTER,
   Code VARCHAR(50),
   Nom VARCHAR(50) NOT NULL,
   Prenom VARCHAR(50) NOT NULL,
   PRIMARY KEY(UUID, Id_Formateur, Code)
);

CREATE TABLE Valider(
   Id_Apprenant INT,
   UUID VARCHAR(50),
   Id_Module INT,
   Validation LOGICAL NOT NULL,
   PRIMARY KEY(Id_Apprenant, UUID, Id_Module),
   FOREIGN KEY(Id_Apprenant, UUID) REFERENCES Apprenant(Id_Apprenant, UUID),
   FOREIGN KEY(Id_Module) REFERENCES Module_(Id_Module)
);

CREATE TABLE Contenir(
   Id_Module INT,
   Id_Formation INT,
   PRIMARY KEY(Id_Module, Id_Formation),
   FOREIGN KEY(Id_Module) REFERENCES Module_(Id_Module),
   FOREIGN KEY(Id_Formation) REFERENCES Formation(Id_Formation)
);

CREATE TABLE Composer(
   Id_Module INT,
   Id_Contenu INT,
   PRIMARY KEY(Id_Module, Id_Contenu),
   FOREIGN KEY(Id_Module) REFERENCES Module_(Id_Module),
   FOREIGN KEY(Id_Contenu) REFERENCES Contenu(Id_Contenu)
);

CREATE TABLE Rediger(
   Id_Module INT,
   UUID VARCHAR(50),
   Id_Formateur INT,
   Code VARCHAR(50),
   PRIMARY KEY(Id_Module, UUID, Id_Formateur, Code),
   FOREIGN KEY(Id_Module) REFERENCES Module_(Id_Module),
   FOREIGN KEY(UUID, Id_Formateur, Code) REFERENCES Formateur(UUID, Id_Formateur, Code)
);
