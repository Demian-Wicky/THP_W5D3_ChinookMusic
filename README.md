# The Gossip Project - Chinook Music db (100% finished)

A Ruby on rails project containing a music database (an Album model and a Track model)
The data comes from `db>seeds.rb`

## Table of contents

- [General info](#general-info)
- [Technologies](#technologies)
- [Setup](#setup)

## General info

Made during [The Hacking Project](https://www.thehackingproject.org) course on Week5 Day3.

## Technologies

Project is created with

- Ruby on Rails 5.2.3

## Setup

First, go to the RoR project folder and type:

```
  bundle install
```

then

```
  rails c
```

## Questions

Copy/paste the corresponding commands for each question to display the result in the console.

### Niveau facile

- What is the total number of Album objects contained in the database ?

  ```ruby
  Album.count
  ```

- Who is the author of the song "White Room"?

  ```ruby
  Track.find_by(title: "White Room").artist
  ```

- Which song lasts exactly 188133 milliseconds?

  ```ruby
  Track.find_by(duration: 188133).title
  ```

- Which band released the album "Use Your Illusion II" ?
  ```ruby
  Album.find_by(title: "Use Your Illusion II").artist
  ```

### Niveau Moyen

- How many albums have "Great" in their title?

  ```ruby
  Album.where("title like ?", "%great%").count
  ```

- eletes all the albums whose name contains "music".

  ```ruby
  Album.where("title like ?", "%music%").destroy_all
  ```

- How many albums are there written by AC/DC ?

  ```ruby
  Album.where(artist: "AC/DC").count
  ```

- How many songs last exactly 158589 milliseconds?
  ```ruby
  Track.where(duration: 158589).count
  ```

### Niveau Difficile

- puts in console all the titles of AC/DC.

  ```ruby
  Track.where(artist: "AC/DC").each do |track|
    puts track.title
  end
  ```

- puts in console all the titles of the album "Let There Be Rock".

  ```ruby
  Track.where(album: "Let There Be Rock").each do |track|
    puts track.title
  end
  ```

- Calculate the total price of this album and its total duration.

  ```ruby
  price = Track.where(album: "Let There Be Rock").sum(:price).round(2)
  duration = Track.where(album: "Let There Be Rock").sum(:duration)
  puts "#{price}, #{duration}"
  ```

- Calculate the cost of the entire "Deep Purple" discography.

  ```ruby
  Track.where(artist: "Deep Purple").sum(:price).round(2)
  ```

- Modifies (via a loop) all the titles of "Eric Clapton" so that they are displayed with "Britney Spears" in artist.

  ```ruby
  Track.where(artist: "Eric Clapton").each do |track|
    track.update(artist: 'Britney Spears')
  end
  ```
