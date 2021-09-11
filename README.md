# The Gossip Project - Chinook Music db

## Questions

### Niveau facile

- Quel est le nombre total d'objets Album contenus dans la base (sans regarder les id bien sûr) ?

  ```ruby
  $ Album.count
  ```

- Qui est l'auteur de la chanson "White Room" ?

  ```ruby
  $ Track.find_by(title: "White Room").artist
  ```

- Quelle chanson dure exactement 188133 milliseconds ?

  ```ruby
  $ Track.find_by(duration: 188133).title
  ```

- Quel groupe a sorti l'album "Use Your Illusion II" ?
  ```ruby
  $ Album.find_by(title: "Use Your Illusion II").artist
  ```

### Niveau Moyen

- Combien y a t'il d'albums dont le titre contient "Great" ? (indice)

  ```ruby
  Album.where("title like ?", "%great%").count
  ```

- Supprime tous les albums dont le nom contient "music".

  ```ruby
  Album.where("title like ?", "%music%").destroy_all
  ```

- Combien y a t'il d'albums écrits par AC/DC ?

  ```ruby
  Album.where(artist: "AC/DC").count
  ```

- Combien de chanson durent exactement 158589 millisecondes ?
  ```ruby
  Track.where(duration: 158589).count
  ```

### Niveau Difficile

- Pour ces questions, tu vas devoir effectuer des boucles dans la console Rails. C'est peu commun mais c'est faisable, tout comme dans IRB.

  ```ruby

  ```

- puts en console tous les titres de AC/DC.

  ```ruby

  ```

- puts en console tous les titres de l'album "Let There Be Rock".

  ```ruby

  ```

- Calcule le prix total de cet album ainsi que sa durée totale.

  ```ruby

  ```

- Calcule le coût de l'intégralité de la discographie de "Deep Purple".

  ```ruby

  ```

- Modifie (via une boucle) tous les titres de "Eric Clapton" afin qu'ils soient affichés avec "Britney Spears" en artist.

  ```ruby

  ```
