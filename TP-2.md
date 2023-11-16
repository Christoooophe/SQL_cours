## 10 Listez pour chaque ticket la quantité totale d’articles vendus. (Classer par quantité décroissante)

```mysql
SELECT NUMERO_TICKET, SUM(QUANTITE) FROM ventes GROUP BY NUMERO_TICKET;
```

## 11 Listez chaque ticket pour lequel la quantité totale d’articles vendus est supérieure à 500. (Classer par quantité décroissante)

```mysql
SELECT NUMERO_TICKET, SUM(QUANTITE) FROM ventes GROUP BY NUMERO_TICKET HAVING SUM(QUANTITE) > 500 ORDER BY SUM(QUANTITE) DESC;
```

## 12 Listez chaque ticket pour lequel la quantité totale d’articles vendus est supérieure à 500. On exclura du total, les ventes ayant une quantité supérieure à 50 (classer par quantité décroissante)

```mysql
SELECT NUMERO_TICKET, SUM(QUANTITE) FROM ventes WHERE QUANTITE < 50 GROUP BY NUMERO_TICKET HAVING SUM(QUANTITE) > 500 ORDER BY SUM(QUANTITE) DESC;
```

## 13 Listez les bières de type ‘Trappiste’. (id, nom de la bière, volume et titrage)

```mysql
SELECT NOM_ARTICLE, ID_ARTICLE, VOLUME, TITRAGE FROM `type` t JOIN article a ON t.ID_TYPE = a.ID_TYPE WHERE t.ID_TYPE = 13;
```

## 14 Listez les marques de bières du continent ‘Afrique’

```mysql

```

## 15 Lister les bières du continent ‘Afrique’

```mysql
```

## 16. Lister les tickets (année, numéro de ticket, montant total payé). En sachant que le prix de vente est égal au prix d’achat augmenté de 15%.

```mysql

```

## 17  Donner le C.A. par année.

```mysql
```

## 18. Lister les quantités vendues de chaque article pour l’année 2016.

```mysql

```

## 19. Lister les quantités vendues de chaque article pour les années 2014, 2015, 2016.

```mysql

```

