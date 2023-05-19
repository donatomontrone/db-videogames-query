## SELECT
- Selezionare tutte le software house americane (3)

```sql
SELECT *
FROM software_houses sh 
WHERE country LIKE "united states";
```

- Selezionare tutti i giocatori della città di 'Rogahnland' (2)

```sql
SELECT *
FROM players p 
WHERE city LIKE "Rogahnland";
```

- Selezionare tutti i giocatori il cui nome finisce per "a" (220)

```sql
SELECT *
FROM players p 
WHERE name LIKE "%a";
```

- Selezionare tutte le recensioni scritte dal giocatore con ID = 800 (11)

```sql
SELECT *
FROM reviews r 
WHERE player_id = 800;
```

- Contare quanti tornei ci sono stati nell'anno 2015 (9)

```sql
SELECT COUNT(*) 
FROM tournaments t 
WHERE year = 2015;
```

- Selezionare tutti i premi che contengono nella descrizione la parola 'facere' (2)

```sql
SELECT * 
FROM awards a  
WHERE description LIKE "%facere%";
```
- Selezionare tutti i videogame che hanno la categoria 2 (FPS) o 6 (RPG), mostrandoli una sola volta (del videogioco vogliamo solo l'ID) (287)

```sql
SELECT DISTINCT videogame_id 
FROM category_videogame cv 
WHERE category_id = 2 
	OR category_id = 6; 
```

- Selezionare tutte le recensioni con voto compreso tra 2 e 4 (2947)

```sql
SELECT * 
FROM reviews r 
WHERE rating BETWEEN 2 AND 4;
```

- Selezionare tutti i dati dei videogiochi rilasciati nell'anno 2020 (46)

```sql
SELECT *
FROM videogames v 
WHERE YEAR(release_date) = 2020; 
```

- Selezionare gli id dei videogame che hanno ricevuto almeno una recensione da 5 stelle, mostrandoli una sola volta (443)

```sql
SELECT DISTINCT videogame_id  
FROM reviews r 
WHERE rating >= 5;
```


#### Bonus
- Selezionare il numero e la media delle recensioni per il videogioco con ID = 412 (review number = 12, avg_rating = 3.16 circa)

```sql
SELECT COUNT(*), AVG(rating) 
FROM reviews r
WHERE videogame_id = 412;
```

- Selezionare il numero di videogame che la software house con ID = 1 ha rilasciato nel 2018 (13)

```sql
SELECT COUNT(*)  
FROM videogames v 
WHERE software_house_id = 1
AND YEAR(release_date) = 2018;
```

### GROUP BY
- Contare quante software house ci sono per ogni paese (3)
- Contare quante recensioni ha ricevuto ogni videogioco (del videogioco vogliamo solo l'ID) (500)
- Contare quanti videogiochi hanno ciascuna classificazione PEGI (della classificazione PEGI vogliamo solo l'ID) (13)
- Mostrare il numero di videogiochi rilasciati ogni anno (11)
- Contare quanti videogiochi sono disponbiili per ciascun device (del device vogliamo solo l'ID) (7)
- Ordinare i videogame in base alla media delle recensioni (del videogioco vogliamo solo l'ID) (500)

---

### JOIN

- Selezionare i dati di tutti giocatori che hanno scritto almeno una recensione, mostrandoli una sola volta (996)
- Sezionare tutti i videogame dei tornei tenuti nel 2016, mostrandoli una sola volta (226)
- Mostrare le categorie di ogni videogioco (1718)
- Selezionare i dati di tutte le software house che hanno rilasciato almeno un gioco dopo il 2020, mostrandoli una sola volta (6)
- Selezionare i premi ricevuti da ogni software house per i videogiochi che ha prodotto (55)
- Selezionare categorie e classificazioni PEGI dei videogiochi che hanno ricevuto recensioni da 4 e 5 stelle, mostrandole una sola volta (3363)
- Selezionare quali giochi erano presenti nei tornei nei quali hanno partecipato i giocatori il cui nome inizia per 'S' (474)
- Selezionare le città in cui è stato giocato il gioco dell'anno del 2018 (36)
- Selezionare i giocatori che hanno giocato al gioco più atteso del 2018 in un torneo del 2019 (3306)

#### Bonus
- Selezionare i dati della prima software house che ha rilasciato un gioco, assieme ai dati del gioco stesso (software house id : 5)
- Selezionare i dati del videogame (id, name, release_date, totale recensioni) con più recensioni (videogame id : potrebbe uscire 449 o 398, sono entrambi a 20)
- Selezionare la software house che ha vinto più premi tra il 2015 e il 2016 (software house id : potrebbe uscire 3 o 1, sono entrambi a 3)
- Selezionare le categorie dei videogame i quali hanno una media recensioni inferiore a 1.5 (10)