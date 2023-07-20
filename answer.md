1. Récupérer tous les albums
SELECT * FROM albums

2. Récupérer tous les albums dont le titre contient "Great" (indice)
SELECT * FROM albums WHERE Title LIKE '%Great %';

3. Donner le nombre total d'albums contenus dans la base (sans regarder les id bien sûr)
SELECT COUNT(Title) FROM albums;

4. Supprimer tous les albums dont le nom contient "music"
SELECT * FROM albums WHERE Title LIKE '%music %';
DELETE FROM albums WHERE Title='%music %';

5. Récupérer tous les albums écrits par AC/DC
SELECT * FROM albums JOIN artists ON albums.ArtistId = artists.ArtistId WHERE artists.Name = 'AC/DC';

6. Récupérer tous les titres des albums de AC/DC
SELECT * FROM albums a, artists b, tracks c
WHERE a.ArtistID = b.ArtistId AND a.AlbumId = c.AlbumId AND b.Name = 'AC/DC'

7. Récupérer la liste des titres de l'album "Let There Be Rock"
SELECT * FROM albums a, artists b, tracks c
WHERE a.ArtistID = b.ArtistId AND a.AlbumId = c.AlbumId AND a.Title = 'Let There Be Rock'

8. Afficher le prix de cet album ainsi que sa durée totale
SELECT SUM(UnitPrice), SUM(Milliseconds) FROM albums a, artists b, tracks c
WHERE a.ArtistID = b.ArtistId AND a.AlbumId = c.AlbumId AND a.Title = 'Let There Be Rock'

9. Afficher le coût de l'intégralité de la discographie de "Deep Purple"
SELECT SUM(UnitPrice) FROM albums a, artists b, tracks c
WHERE a.ArtistID = b.ArtistId AND a.AlbumId = c.AlbumId AND b.Name = 'Deep Purple'

10. Créer l'album de ton artiste favori en base, en renseignant correctement les trois tables albums, artists et tracks
INSERT INTO artists(Name) VALUES ('Manou');
INSERT INTO tracks(Name) VALUES ('Mayumi');
INSERT INTO albums(Title) VALUES ('Noum');