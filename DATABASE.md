# Gestion BDD

## Création table

```sql
-- table Etudiants definition
CREATE TABLE Etudiants (
	id INTEGER NOT NULL,
	nom TEXT(50),
	prenom TEXT,
	naissance TEXT(10),
	email TEXT(100), age INTEGER, ville VARCHAR(50),
	CONSTRAINT Etudiants_PK PRIMARY KEY (id)
);
```
## Selection de lignes
```sql
-- Afficher toutes les lignes de la table Etudiants
SELECT * FROM Etudiants;

-- Afficher les étudiants de + de 18 ans
SELECT nom,prenom,age 
FROM Etudiants
WHERE age>18
ORDER BY nom;

-- Afficher les étudiants entre 20 et 25 ans
SELECT nom,prenom,age 
FROM Etudiants
WHERE age BETWEEN 20 AND 25
ORDER BY nom;

-- lignes ou naissance est non vide
SELECT * 
FROM Etudiants
WHERE naissance IS NOT NULL;
```

## Ajout de ligne 
```sql
-- Insertion d'une ligne dans la table
INSERT INTO Etudiants (id,nom, prenom, naissance, email)
VALUES(16, 'name', 'surname', '2000-01-15', 'kjqsbdkqsbd@free.fr');
```

## Mise à jour de lignes
```sql
-- MaJ de l'email de l'étudiant dont l'id = 20
UPDATE Etudiants
SET email='pierre.xxx@free.fr'
WHERE id=20
```

## Suppression de lignes
```sql
-- suppression des lignes ou naissance est non vide
DELETE
FROM Etudiants
WHERE naissance IS NOT NULL;
```