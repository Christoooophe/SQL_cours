## 10 Listez pour chaque ticket la quantité totale d’articles vendus. (Classer par quantité décroissante)

```mysql
SELECT NUMERO_TICKET, SUM(QUANTITE) AS SOMME
FROM ventes 
GROUP BY NUMERO_TICKET
ORDER BY SOMME DESC;
```

## 11 Listez chaque ticket pour lequel la quantité totale d’articles vendus est supérieure à 500. (Classer par quantité décroissante)

```mysql
SELECT NUMERO_TICKET, SUM(QUANTITE) AS SOMME
FROM ventes 
GROUP BY NUMERO_TICKET 
HAVING SOMME > 500 
ORDER BY SOMME DESC;
```

## 12 Listez chaque ticket pour lequel la quantité totale d’articles vendus est supérieure à 500. On exclura du total, les ventes ayant une quantité supérieure à 50 (classer par quantité décroissante)

```mysql
SELECT NUMERO_TICKET, SUM(QUANTITE) AS SOMME
FROM ventes 
WHERE QUANTITE <= 50
GROUP BY NUMERO_TICKET 
HAVING SOMME > 500 
ORDER BY SOMME DESC;
```

## 13 Listez les bières de type ‘Trappiste’. (id, nom de la bière, volume et titrage)

```mysql
SELECT NOM_ARTICLE, ID_ARTICLE, VOLUME, TITRAGE 
FROM `type` t 
JOIN article a ON t.ID_TYPE = a.ID_TYPE 
WHERE t.ID_TYPE = 13;
```

## 14 Listez les marques de bières du continent ‘Afrique’

```mysql
SELECT NOM_MARQUE, NOM_CONTINENT, p.ID_PAYS 
FROM marque m 
JOIN pays p ON m.ID_PAYS = p.ID_PAYS 
JOIN continent c ON c.ID_CONTINENT = p.ID_CONTINENT 
WHERE p.ID_CONTINENT = 1;
```

## 15 Lister les bières du continent ‘Afrique’

```mysql
SELECT NOM_ARTICLE, NOM_PAYS, ID_ARTICLE 
FROM article a 
JOIN marque m ON a.ID_MARQUE = m.ID_MARQUE 
JOIN pays p ON m.ID_PAYS = p.ID_PAYS 
JOIN continent c ON c.ID_CONTINENT = p.ID_CONTINENT 
WHERE p.ID_CONTINENT = 1;
```

## 16. Lister les tickets (année, numéro de ticket, montant total payé). En sachant que le prix de vente est égal au prix d’achat augmenté de 15%.

```mysql
SELECT t.ANNEE, t.NUMERO_TICKET, t.DATE_VENTE, SUM(v.QUANTITE * a.PRIX_ACHAT) * 1.15 AS TOTAL 
FROM ticket t 
JOIN ventes v ON t.NUMERO_TICKET = v.NUMERO_TICKET 
JOIN article a ON v.ID_ARTICLE = a.ID_ARTICLE 
GROUP BY t.ANNEE, t.NUMERO_TICKET
ORDER BY TOTAL DESC;
```

## 17  Donner le C.A. par année.

```mysql
SELECT v.ANNEE, SUM(a.PRIX_ACHAT * v.QUANTITE) * 1.15 AS CHIFFRE_AFFAIRE
FROM ventes v
JOIN article a ON v.ID_ARTICLE = a.ID_ARTICLE
GROUP BY v.ANNEE
```

## 18. Lister les quantités vendues de chaque article pour l’année 2016.

```mysql

```

## 19. Lister les quantités vendues de chaque article pour les années 2014, 2015, 2016.

```mysql

```

