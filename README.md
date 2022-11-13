# Données du système Ford GoBike:201902-fordgobike-tripdata
 
## par MBOCK MBOCK Georges Christian


## Description du Jeu de données


201902-fordgobike-tripdata est un jeu de données du Sytème Ford GoBike [cliquer ici](https://github.com/BetaNYC/Bike-Share-Data-Best-Practices/wiki/Bike-Share-Data-Systems.).
Cet ensemble de données comprend des informations sur cent quatre-vingt-trois mille quatre cent douze(183412) trajets individuels effectués dans un système de partage de vélos couvrant la grande région de la baie de San Francisco.
Ainsi, ces informations sont organisées dans seize(16) colonnes entre autres:

'duration_sec': durée du trajet (en seconde)

'start_time', ('end_time'): date du début, (de fin) du trajet (AA-MM-JJ h:m:s.t)

'start_station_id', ('end_station_id'): numero d'identification du lieu du commencement, (de fin) du trajet

'start_station_name', ('end_station_name'): nom du lieu de commencement, (de fin)du trajet

'start_station_latitude','start_station_longitude', 'end_station_latitude', 'end_station_longitude': coordonnées des lieux de commencement et fin du trajet

'bike_id': immatriculation du vélo

'user_type': type d'utilisateur(Abonné ou Client)

'member_birth_year', ('member_gender'): année de naissance de l'utilisateur, (sexe de l'utilisateur)

'bike_share_for_all_trip': type de vélo(Vélo tout terrain ou non)

## Résumé des conclusions


**Dans l'évaluation des données**
j'ai constaté plusieurs problèmes entre autres:
* Les problèmes de l'ordre que j'ai résolu en éclatant la variable 'start_time' en 'jour' et 'heure'puis en supprimant d'autres variables comme 'start_station_name' et 'end_station_name' qui ne nous semblant pas pertinentes. Cependant, j'ai ajouté la variable 'start_Week' que j'ai jugé pertinent de savoir à quel moment du mois en terme de semaine les trajets ont le plus débutés.

* Les problèmes de qualité comme : - Le mauvais formatage des types de certaines variables que j'ai retransformé en véritable type par exemple la variable 'member_birth_year' qui a été tranformée de simple float en variable catégorielle.
- Les données manquantes :j'ai juste supprimé les lignes dont les valeurs manquaient pour la variable 'start_station_name' et j'ai séparé du jeu de données principal les lignes dont les valeurs manquaient pour la variable 'member_gender' dont j'ai exploré par la suite.

**Dans l'exploration**:
* j'ai remanqué des valeurs exceptionnelles de durée de trajet, ce qui m'a motivé organiser la variable 'duration_sec' en différent type de trajet selon leur durée. Entre autre type, nous avons: Pour les utilisateurs dont la valeur la 'member_gender' est connue  
type_1 --->Au plus 20minutes;
type_2 --->De 21 à 40minutes;
type_3 --->De 41 à 1heure;
type_4 --->De 1heure à 2.5heures;
type_5 --->De 2.5heures à 7heures;
type_6 ---> Plus de 7heures

Et pour les utilisateurs dont la valeur 'member_gender' n'est pas connue nous avons les différents trajets suivants:
type_1 ---> au plus 20minutes;
type_2 --->De 21 à 40minutes;
type_3 --->De 41 à 1heure;
type_4 --->De 1heure à 2.5heures;
type_5 --->De 2.5heures à 5.5heures;
type_6 ---> Plus de 5.5heures

* Pour les utilisateurs dont le sexe est connu, j'ai remarqué le fait qu'un utilisateur soit un Abonné ou Client n'est pas directement influencé ni son sexe, ni par le moment du mois en terme de semaine ou le moment de la journée en terme heures aucours duquel il effectue son trajet. Néammoins, j'ai remarqué une faible influence du type de trajet sur le fait qu'un utilisateur soit un Abonné ou Client. De plus, cette influence semble davantage créer une influence du sexe sur le fait qu'un utilisateur soit un Abonné ou Client lorsqu'on sait que l'utiisateur effectue le trajet du type_5. J'ai aussi remarqué que aucun utilisateur de type Client n'utilise les vélos du type tout déplacement.

* Pour les utilisateurs dont le sexe est inconnu, j'ai remarqué que le fait d'Abonné ou Client semble être directement influencé par le type du trajet. 


## Principales idées pour la présentation

Pour cette présentation, je commence par donner la répartition en fréquence absolue de type d'utilisateurs, puis je me concentre différentes relations éventuellement entre ma variable d'intérêt 'user_type' et d'autres variables comme : 'duration_sec' Vs 'type_trip', 'member_gender' Vs 'user_type', 'type_trip' Vs 'user_type' et 'bike_share_for_all_trip' Vs 'user_type' puis des relations multivariées comme : Type_trajet' ='Type5'|'user_type' Vs 'menber_gender', et enfin 'member_gender'=('Female' or 'Male' or 'Other')|'user_type' Vs 'bike_share_for_all_trip' et pour terminer je présente l'influence du type de trajet sur le type d'utilisateur de sexe non connu 'user_type' Vs 'type_trip'.








