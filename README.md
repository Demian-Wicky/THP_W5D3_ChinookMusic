# The Gossip Project - Chinook Music db

## Questions

### Niveau facile

- Quel est le nombre total d'objets Album contenus dans la base (sans regarder les id bien sûr) ?

  ```ruby
  Album.count
  ```

- Qui est l'auteur de la chanson "White Room" ?

  ```ruby
  Track.find_by(title: "White Room").artist
  ```

- Quelle chanson dure exactement 188133 milliseconds ?

  ```ruby
  Track.find_by(duration: 188133).title
  ```

- Quel groupe a sorti l'album "Use Your Illusion II" ?
  ```ruby
  Album.find_by(title: "Use Your Illusion II").artist
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

- puts en console tous les titres de AC/DC.

  ```ruby
  Track.where(artist: "AC/DC").each do |track|
    puts track.title
  end
  ```

- puts en console tous les titres de l'album "Let There Be Rock".

  ```ruby
  Track.where(album: "Let There Be Rock").each do |track|
    puts track.title
  end
  ```

- Calcule le prix total de cet album ainsi que sa durée totale.

  ```ruby
  price = Track.where(album: "Let There Be Rock").sum(:price).round(2)
  duration = Track.where(album: "Let There Be Rock").sum(:duration)
  puts "#{price}, #{duration}"
  ```

- Calcule le coût de l'intégralité de la discographie de "Deep Purple".

  ```ruby
  Track.where(artist: "Deep Purple").sum(:price).round(2)
  ```

- Modifie (via une boucle) tous les titres de "Eric Clapton" afin qu'ils soient affichés avec "Britney Spears" en artist.

  ```ruby
  Track.where(artist: "Eric Clapton").each do |track|
    track.update(artist: 'Britney Spears')
  end
  ```
