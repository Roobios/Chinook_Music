# Exercice Ruby on Rails - Chinook Music
[![forthebadge](./.README_files/the-hacking-project.svg)](https://forthebadge.com)


## 1. Enoncé
L'exercice conciste à :
1. Créer une application Rails
1. Créer un model "Album" contenant :
    - **title** qui porte le titre de l'album et est de type string.
    - **artist** qui porte nom de l'artiste et est de type string.
1. Créer un model "Track" contenant :
    - **title** qui porte le titre de la chanson et est de type string.
    - **album** qui porte le titre de l'album et est de type string.
    - **artist** qui porte le nom de l'artiste et est de type string.
    - **duration** qui porte la durée de la chanson (en millisecondes) et est de type integer.
    - **size** qui porte la taille (en octets) de la chanson et est de type integer.
    - **price** qui porte le prix de la chanson et est de type float.
1. Effectuer les migrations
1. Effectuer le seed de la base de données 
1. Répondre aux questions

## 2. Questions
### a. Niveau facile
Quel est le nombre total d'objets Album contenus dans la base (sans regarder les id bien sûr) ?\
`Album.all.length`

Qui est l'auteur de la chanson "White Room" ?\
`Track.find_by(title: "White Room").artist`
    
Quelle chanson dure exactement 188133 milliseconds ?\
`Track.find_by(duration: 188133).title`

Quel groupe a sorti l'album "Use Your Illusion II" ?\
`Album.find_by(title: "Use Your Illusion II").artist`

### b. Niveau Moyen

Combien y a t'il d'albums dont le titre contient "Great" ?\
`Album.where("title like ?", "%Great%").length`

Supprime tous les albums dont le nom contient "music".\
`Album.where("title like ?", "%music%").destroy`

Combien y a t'il d'albums écrits par AC/DC ?\
`̀Album.where("artist like ?", "AC/DC").count`

Combien de chanson durent exactement 158589 millisecondes ?\
`Track.where(duration: 158589).count`

### c. Niveau Difficile

Pour ces questions, tu vas devoir effectuer des boucles dans la console Rails. C'est peu commun mais c'est faisable, tout comme dans IRB.

puts en console tous les titres de AC/DC.\
`Track.where(artist: "AC/DC").each { |i| puts i.title }`

puts en console tous les titres de l'album "Let There Be Rock".\
̀̀`Track.where(album: "Let There Be Rock").each{|i| puts i.title}`

Calcule le prix total de cet album ainsi que sa durée totale.\
`Track.where(album: "Let There Be Rock").sum(:price)`
`Track.where(album: "Let There Be Rock").sum(:duration)`
    
Calcule le coût de l'intégralité de la discographie de "Deep Purple".\
`Track.where(artist: "Deep Purple").sum(:price)`

Modifie (via une boucle) tous les titres de "Eric Clapton" afin qu'ils soient affichés avec "Britney Spears" en artist.\
`Track.where(artist: "Eric Clapton").each { |i| i.update(artist: "Britney Spears") }`

## 3. Crédits

Un pair-programme [Roobios](https://github.com/Roobios), [joffrey7486](https://github.com/joffrey7486) et [fleopaulD](https://github.com/fleopaulD) :smiley:

