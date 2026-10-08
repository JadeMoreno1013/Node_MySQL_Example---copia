Instalar librerías = npm.cmd install;

Ejecutar = node server.js;

Explicación MySQL + Node = https://youtu.be/GxW6b_tlqJM?si=W_15Ni8zlUIPnUxE



Consultas en SQL = https://youtu.be/TFQzm8DIJ_w?si=SUkDzvMsBc8RLYjy




EJEMPLO CONSULTAS SPOTIFY
-- Busquedas con respecto a columnas
SELECT FROM song;
SELECT name, artist FROM song;
SELECT name AS Nombre, artist AS Canción FROM song;
SELECT artist FROM song;

SELECT DISTINCT(artist) FROM song;

-- Contar el numero de registros
SELECT COUNT(*) AS Canciones FROM song;
SELECT COUNT(*) AS Reproducciones FROM activity;
-- AVG -> Count.
SELECT FROM song WHERE artist "Feid";
SELECT FROM activity WHERE id > 20 AND id < 30;
SELECT FROM song WHERE artist "Feid" OR artist "Miranda!";
SELECT FROM song WHERE artist "Feid";
SELECT FROM song WHERE artist IN ("Feid", "Diomedes Diaz", "Miranda!");
SELECT FROM activity WHERE id BETWEEN 20 AND 30;

-- Contar cuantas canciones diferentes hay por artista
SELECT artist, COUNT(*)
FROM song
WHERE name != "Algo"
GROUP BY artist
HAVING COUNT(*) > 20
ORDER BY COUNT(*) DESC
LIMIT 15;


--WHERE
-- % -> Wildcard *
SELECT DISTINCT (artist) FROM song
WHERE artist LIKE "a%"; -- empieza por a
WHERE artist LIKE "%oro%"; -- contiene oro en algun lado

--JOIN Juntar la informacion de 2 tablas
SELECT id_song, name FRON song WHERE artist LIKE "Binomio%"
-- Buscar cuantas veces escuche la cancion Distintos Destinos
-- 3k1DMS815WdQMDB2akhbha -> Distintos Destinos
SELECT * FROM activity WHERE id_song = "3k1DMS815WdQHD82aAhbha"

SELECT activity.listen_date, song.name
FROM activity
INNER JOIN song ON song.id_song = activity.id_song;

-- INNER JOIN -> Retorna todos los registros que estan en las 2 tablas
SELECT COUNT(*) AS Reproducciones, song.artist
FROM activity
INNER JOIN song ON activity.id_song = song.id_song
WHERE song.name LIKE "%mor%"
GROUP BY song.artist
HAVING song.artist LIKE "a%"
ORDER BY Reproducciones DESC
LIMIT 50:

