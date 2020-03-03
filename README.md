Welcome to DEV_area_2019 👋

> l'Area est un service web permettant d'interconnecté différentes API

## Trigger Spotify

- Detect a new album from an artist (NAA)
    - route: https://api.spotify.com/v1/artists/"id"/albums
    - params: [ id de l'artiste ] ← recherche avec POST /user/spotify/searchArtist ("keywords" : "mots-clés")
    - variables: nom de l'album (%albumName), nom de l'artiste (%albumArtist)

## Action Spotify

- add album to playlist (ATP)
    - route: https://api.spotify.com/v1/playlists/"id"/tracks
    - params: [ id de la playlist ] ← recherche avec GET /user/spotify/myPlaylists
    - query: "recherche de l'album"
    
## Trigger Deezer

- Detect a new album from an artist (NAA)
    - route: https://api.deezer.com/artist/"id"/albums
    - params: [ id de l'artiste ] ← recherche avec POST /user/deezer/searchArtist ("keywords" : "mots-clés")
    - variables: nom de l'album (%albumName), nom de l'artiste (%albumArtist)
- Then add album to playlist (ATP)
    - route: https://api.deezer.com/playlist/"id"/tracks
    - params: [ id de la playlist ] ← recherche avec GET /user/deezer/myPlaylists
    - query: "recherche de l'album"

- Then add album to favorites (ATF)
    - route: https://api.deezer.com/user/me/albums
    - params: nothing
    - query: "recherche de l'album"

## Trigger Github

- Detect new pull request (NPR)
    - route: https://api.github.com/repos/"user"/"repo"/pulls
    - params: [ propriétaire du repo, nom du repo ]
    - variables: titre de la pull request (%pullrequestTitle), auteur de la pull request (%pullrequestAuthor)
- Detect new commit (NC)
    - route: https://api.github.com/repos/"user"/"repo"/commits
    - params: [ propriétaire du repo, nom du repo ]
    - variables: titre du commit (%commitTitle), auteur du commit (%commitAuthor)
- Detect new branch (NB)
    - route: https://api.github.com/repos/"user"/"repo"/branches
    - params: [ propriétaire du repo, nom du repo ]
    - variables: nom de la branche (%branchName), créateur de la branche (%branchCreator)

## Trigger Youtube

- Detect a new activity (NA)
    - route: https://www.googleapis.com/youtube/v3/activities
    - params : [ id de la chaîne ] ← recherche avec POST /user/youtube/searchChannel ("keywords : "mots-clés")
    - variables : titre de la vidéo (%videoTitle), description (%videoDescription)

## Action Youtube

- Comment a video (CV)
    - route: https://www.googleapis.com/youtube/v3/commentThreads
    - params : [ id de la vidéo ] ← recherche avec POST /user/youtube/searchVideo ("keywords : "mot-clés")
    - query : "contenu du commentaire"
- Like / dislike a vidéo (LDV)
    - route: https://www.googleapis.com/youtube/v3/videos/rate
    - params : [ boolean ] ← true = like & false = dislike
    - query : "recherche de la vidéo"
- Subscribe to a channel (STC)
    - route: https://www.googleapis.com/youtube/v3/subscriptions
    - params: none
    - query: "recherche de la chaîne"
    
## Trigger Gmail

- Detect new e-mail (NE)
    - route: https://www.googleapis.com/gmail/v1/users/"email"/messages
    - mparamms : none
    - variables : e-mail de l'émetteur (%senderEmail), objet du mail (%emailObject), contenu du mail              (%emailContent)

## Action Gmail

- Send e-mail (SE)
    - route: https://www.googleapis.com/gmail/v1/users/me/drafts/send
    - params : [ e-mail du destinataire ]
    - query : "contenu du mail"
- Create a draft (CD)
    - route: https://www.googleapis.com/gmail/v1/users/me/drafts
    - params: none
    - query : "contenu du brouillon"

## Author

👤 **Les boi's**

***
_This README was generated with ❤️ by [readme-md-generator](https://github.com/kefranabg/readme-md-generator)_
