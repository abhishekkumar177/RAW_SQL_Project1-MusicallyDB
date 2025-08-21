# Music_System

# 1 DESIGN THE ALBUM SCHEMA

SQL> CREATE TABLE ALBUM(
       ALBUM_ID NUMBER(4) PRIMARY KEY,
       TITLE VARCHAR(15),
       ARTIST_ID NUMBER(4)
       );

Table created.

# 2 DESIGN THE ARTIST SCHEMA

SQL> CREATE TABLE ARTIST(
       ARTIST_ID NUMBER(4) PRIMARY KEY,
       NAME VARCHAR(10)
       );

Table created.

# 3 DESIGN THE PLAYLIST SCHEMA

SQL> CREATE TABLE PLAYLIST(
       PLAYLIST_ID NUMBER(4) PRIMARY KEY,
       NAME VARCHAR(12)
       );

Table created.

# 4 DESIGN THE PLAYLIST TRACK SCHEMA

SQL> CREATE TABLE PLAYLIST_TRACK(
       PLAYLIST_ID NUMBER(4),
       TRACK_ID NUMBER(4) PRIMARY KEY
       );

Table created.

# 5 DESIGN THE TRACK SCHEMA

SQL> CREATE TABLE TRACK(
      TRACK_ID NUMBER(4) PRIMARY KEY,
      NAME VARCHAR(10),
      ALBUM_ID NUMBER(4),
      MEDIA_TYPE_ID NUMBER(2),
      GENRE_ID NUMBER(2),
      COMPOSER VARCHAR(12),
      DURATION_IN_SECS NUMBER(5),
      BYTES NUMBER(10),
      UNIT_PRICE NUMBER(5)
      );

Table created.

# 6 DESIGN THE INVOICE LINE SCHEMA

SQL> CREATE TABLE INVOICE_LINE(
       INVOICE_LINE_ID NUMBER(4) PRIMARY KEY,
       INVOICE_ID NUMBER(4),
       TRACK_ID NUMBER(4),
       UNIT_PRICE NUMBER(5),
       QUANTITY NUMBER(4)
       );

Table created.

# 7 DESIGN THE GENRE SCHEMA

SQL> CREATE TABLE GENRE(
       GENRE_ID NUMBER(4) PRIMARY KEY,
       NAME VARCHAR(12)
       );

Table created.

# 8 DESIGN THE MEDIA TYPE SCHEMA

SQL> CREATE TABLE MEDIA_TYPE(
  2     MEDIA_TYPE_ID NUMBER(2) PRIMARY KEY,
  3     NAME VARCHAR(10)
  4     );

Table created.

# 9 DESIGN THE TABLE CUSTOMER SCHEMA

SQL> CREATE TABLE CUSTOMER (
       CUSTOMER_ID NUMBER(4) PRIMARY KEY,
       LASTNAME VARCHAR2(10),
       FIRSTNAME VARCHAR2(10),
       COMPANY VARCHAR2(20),
       ADDRESS VARCHAR2(100),
       CITY VARCHAR2(10),
       STATE VARCHAR2(10),
       COUNTRY VARCHAR2(10),
       POSTAL_CODE VARCHAR2(10),
       PHONE VARCHAR2(15),
       FAX VARCHAR2(15),
       EMAIL VARCHAR2(30),
       SUPPORT_REP_ID VARCHAR(10)
   );

Table created.


# 10 DESIGN THE EMPLOYEE SCHEMA

SQL> CREATE TABLE EMPLOYEE (
       EMPLOYEE_ID NUMBER(4) PRIMARY KEY,
       LASTNAME VARCHAR2(10),
       FIRSTNAME VARCHAR2(10),
       TITLE VARCHAR2(10),
       REPORTS_TO NUMBER(4),
       BIRTH_DATE DATE,
       HIRE_DATE DATE,
       ADDRESS VARCHAR2(100),
       CITY VARCHAR2(10),
       STATE VARCHAR2(10),
       COUNTRY VARCHAR2(10),
       POSTAL_CODE VARCHAR2(10),
       PHONE VARCHAR2(15),
       FAX VARCHAR2(15),
       EMAIL VARCHAR2(30)
       );

Table created.

# 11 DESIGN THE INVOICE SCHEMA

SQL> CREATE TABLE INVOICE (
       INVOICE_ID NUMBER(10) NOT NULL,
       CUSTOMER_ID NUMBER(10),
       INVOICE_DATE DATE,
       BILLING_ADDRESS VARCHAR2(100),
       BILLING_CITY VARCHAR2(10),
       BILLING_STATE VARCHAR2(10),
       BILLING_COUNTRY VARCHAR2(10),
       BILLING_POSTAL_CODE VARCHAR2(10),
       TOTAL NUMBER(10,2)
       );

Table created.


# 12 POPULATING THE ARTIST DB

INSERT ALL
    INTO ARTIST (ARTIST_ID, NAME) VALUES (1, 'Queen')
    INTO ARTIST (ARTIST_ID, NAME) VALUES (2, 'Beatles')
    INTO ARTIST (ARTIST_ID, NAME) VALUES (3, 'M. Jackson')
    INTO ARTIST (ARTIST_ID, NAME) VALUES (4, 'Madonna')
    INTO ARTIST (ARTIST_ID, NAME) VALUES (5, 'Elton John')
    INTO ARTIST (ARTIST_ID, NAME) VALUES (6, 'E. Presley')
    INTO ARTIST (ARTIST_ID, NAME) VALUES (7, 'T. Swift')
    INTO ARTIST (ARTIST_ID, NAME) VALUES (8, 'E. Sheeran')
    INTO ARTIST (ARTIST_ID, NAME) VALUES (9, 'Coldplay')
    INTO ARTIST (ARTIST_ID, NAME) VALUES (10, 'Adele')
    INTO ARTIST (ARTIST_ID, NAME) VALUES (11, 'Eminem')
    INTO ARTIST (ARTIST_ID, NAME) VALUES (12, 'B. Mars')
    INTO ARTIST (ARTIST_ID, NAME) VALUES (13, 'Rihanna')
    INTO ARTIST (ARTIST_ID, NAME) VALUES (14, 'Beyoncé')
    INTO ARTIST (ARTIST_ID, NAME) VALUES (15, 'Zepellin')
    INTO ARTIST (ARTIST_ID, NAME) VALUES (16, 'P. Floyd')
    INTO ARTIST (ARTIST_ID, NAME) VALUES (17, 'U2')
    INTO ARTIST (ARTIST_ID, NAME) VALUES (18, 'Nirvana')
    INTO ARTIST (ARTIST_ID, NAME) VALUES (19, 'AC/DC')
    INTO ARTIST (ARTIST_ID, NAME) VALUES (20, 'Guns N''R')
SELECT 1 FROM dual;

20 rows created.

# 13 POPULATING THE ALBUM DB

INSERT ALL
    INTO ALBUM (ALBUM_ID, TITLE, ARTIST_ID) VALUES (1, 'Night at Opa', 1)
    INTO ALBUM (ALBUM_ID, TITLE, ARTIST_ID) VALUES (2, 'News of Worl', 1)
    INTO ALBUM (ALBUM_ID, TITLE, ARTIST_ID) VALUES (3, 'Abbey Road', 2)
    INTO ALBUM (ALBUM_ID, TITLE, ARTIST_ID) VALUES (4, 'Thriller', 3)
    INTO ALBUM (ALBUM_ID, TITLE, ARTIST_ID) VALUES (5, 'Like a Virgi', 4)
    INTO ALBUM (ALBUM_ID, TITLE, ARTIST_ID) VALUES (6, 'Rocket Man', 5)
    INTO ALBUM (ALBUM_ID, TITLE, ARTIST_ID) VALUES (7, 'Blue Hawaii', 6)
    INTO ALBUM (ALBUM_ID, TITLE, ARTIST_ID) VALUES (8, 'Folklore', 7)
    INTO ALBUM (ALBUM_ID, TITLE, ARTIST_ID) VALUES (9, 'X', 8)
    INTO ALBUM (ALBUM_ID, TITLE, ARTIST_ID) VALUES (10, 'Parachutes', 9)
    INTO ALBUM (ALBUM_ID, TITLE, ARTIST_ID) VALUES (11, '21', 10)
    INTO ALBUM (ALBUM_ID, TITLE, ARTIST_ID) VALUES (12, 'Slim Shady', 11)
    INTO ALBUM (ALBUM_ID, TITLE, ARTIST_ID) VALUES (13, 'Doo-Wops', 12)
    INTO ALBUM (ALBUM_ID, TITLE, ARTIST_ID) VALUES (14, 'Anti', 13)
    INTO ALBUM (ALBUM_ID, TITLE, ARTIST_ID) VALUES (15, 'Lemonade', 14)
    INTO ALBUM (ALBUM_ID, TITLE, ARTIST_ID) VALUES (16, 'IV', 15)
    INTO ALBUM (ALBUM_ID, TITLE, ARTIST_ID) VALUES (17, 'Dark Side', 16)
    INTO ALBUM (ALBUM_ID, TITLE, ARTIST_ID) VALUES (18, 'Achtung Ba', 17)
    INTO ALBUM (ALBUM_ID, TITLE, ARTIST_ID) VALUES (19, 'Nevermind', 18)
    INTO ALBUM (ALBUM_ID, TITLE, ARTIST_ID) VALUES (20, 'Unassigned', NULL)
    INTO ALBUM (ALBUM_ID, TITLE, ARTIST_ID) VALUES (21, 'Untitled', NULL)
SELECT 1 FROM dual;

21 rows selected.

# 14 JOINING THE ARTIST AND ALBUM FOR OPERATIONS

SQL> SELECT A.TITLE, B.NAME
    FROM ALBUM A
    JOIN ARTIST B ON A.ARTIST_ID = B.ARTIST_ID;

TITLE           NAME
--------------- ----------
Night at Opa    Queen
News of Worl    Queen
Abbey Road      Beatles
Thriller        M. Jackson
Like a Virgi    Madonna
Rocket Man      Elton John
Blue Hawaii     E. Presley
Folklore        T. Swift
X               E. Sheeran
Parachutes      Coldplay
21              Adele
Slim Shady      Eminem
Doo-Wops        B. Mars
Anti            Rihanna
Lemonade        Beyoncé
IV              Zepellin
Dark Side       P. Floyd
Achtung Ba      U2
Nevermind       Nirvana

19 rows selected.

# 15 POPULATING THE TRACK SCHEMA

SQL>INSERT ALL
    INTO TRACK (TRACK_ID, NAME, ALBUM_ID, MEDIA_TYPE_ID, GENRE_ID, COMPOSER, DURATION_IN_SECS, BYTES, UNIT_PRICE)
        VALUES (1, 'Bohemian', 1, 1, 1, 'Mercury', 355, 8875000, 20)
    INTO TRACK (TRACK_ID, NAME, ALBUM_ID, MEDIA_TYPE_ID, GENRE_ID, COMPOSER, DURATION_IN_SECS, BYTES, UNIT_PRICE)
        VALUES (2, 'LoveLife', 1, 2, 1, 'Mercury', 215, 5375000, 18)
    INTO TRACK (TRACK_ID, NAME, ALBUM_ID, MEDIA_TYPE_ID, GENRE_ID, COMPOSER, DURATION_IN_SECS, BYTES, UNIT_PRICE)
        VALUES (3, 'RockYou', 2, 3, 1, 'May', 122, 3050000, 15)
    INTO TRACK (TRACK_ID, NAME, ALBUM_ID, MEDIA_TYPE_ID, GENRE_ID, COMPOSER, DURATION_IN_SECS, BYTES, UNIT_PRICE)
        VALUES (4, 'Champion', 2, 1, 1, 'Mercury', 179, 4475000, 18)
    INTO TRACK (TRACK_ID, NAME, ALBUM_ID, MEDIA_TYPE_ID, GENRE_ID, COMPOSER, DURATION_IN_SECS, BYTES, UNIT_PRICE)
        VALUES (5, 'Together', 3, 2, 1, 'Lennon', 259, 6475000, 20)
    INTO TRACK (TRACK_ID, NAME, ALBUM_ID, MEDIA_TYPE_ID, GENRE_ID, COMPOSER, DURATION_IN_SECS, BYTES, UNIT_PRICE)
        VALUES (6, 'Something', 3, 3, 1, 'Harrison', 182, 4550000, 18)
    INTO TRACK (TRACK_ID, NAME, ALBUM_ID, MEDIA_TYPE_ID, GENRE_ID, COMPOSER, DURATION_IN_SECS, BYTES, UNIT_PRICE)
        VALUES (7, 'Sunshine', 3, 1, 1, 'Harrison', 185, 4625000, 19)
    INTO TRACK (TRACK_ID, NAME, ALBUM_ID, MEDIA_TYPE_ID, GENRE_ID, COMPOSER, DURATION_IN_SECS, BYTES, UNIT_PRICE)
        VALUES (8, 'BillieJn', 4, 2, 2, 'Jackson', 294, 7350000, 22)
    INTO TRACK (TRACK_ID, NAME, ALBUM_ID, MEDIA_TYPE_ID, GENRE_ID, COMPOSER, DURATION_IN_SECS, BYTES, UNIT_PRICE)
        VALUES (9, 'Thriller', 4, 3, 2, 'RodT', 358, 8950000, 25)
    INTO TRACK (TRACK_ID, NAME, ALBUM_ID, MEDIA_TYPE_ID, GENRE_ID, COMPOSER, DURATION_IN_SECS, BYTES, UNIT_PRICE)
        VALUES (10, 'BeatIt', 4, 1, 2, 'Jackson', 258, 6450000, 20)
    INTO TRACK (TRACK_ID, NAME, ALBUM_ID, MEDIA_TYPE_ID, GENRE_ID, COMPOSER, DURATION_IN_SECS, BYTES, UNIT_PRICE)
        VALUES (11, 'Virgin', 5, 2, 2, 'Steinberg', 230, 5750000, 20)
    INTO TRACK (TRACK_ID, NAME, ALBUM_ID, MEDIA_TYPE_ID, GENRE_ID, COMPOSER, DURATION_IN_SECS, BYTES, UNIT_PRICE)
        VALUES (12, 'Material', 5, 3, 2, 'Brown', 245, 6125000, 18)
    INTO TRACK (TRACK_ID, NAME, ALBUM_ID, MEDIA_TYPE_ID, GENRE_ID, COMPOSER, DURATION_IN_SECS, BYTES, UNIT_PRICE)
        VALUES (13, 'RocketMn', 6, 1, 1, 'EltonJohn', 280, 7000000, 22)
    INTO TRACK (TRACK_ID, NAME, ALBUM_ID, MEDIA_TYPE_ID, GENRE_ID, COMPOSER, DURATION_IN_SECS, BYTES, UNIT_PRICE)
        VALUES (14, 'TinyDanc', 6, 2, 1, 'EltonJohn', 360, 9000000, 24)
    INTO TRACK (TRACK_ID, NAME, ALBUM_ID, MEDIA_TYPE_ID, GENRE_ID, COMPOSER, DURATION_IN_SECS, BYTES, UNIT_PRICE)
        VALUES (15, 'BlueHaw', 7, 3, 2, 'Presley', 150, 3750000, 15)
    INTO TRACK (TRACK_ID, NAME, ALBUM_ID, MEDIA_TYPE_ID, GENRE_ID, COMPOSER, DURATION_IN_SECS, BYTES, UNIT_PRICE)
        VALUES (16, 'CantHelp', 7, 1, 2, 'Presley', 180, 4500000, 18)
    INTO TRACK (TRACK_ID, NAME, ALBUM_ID, MEDIA_TYPE_ID, GENRE_ID, COMPOSER, DURATION_IN_SECS, BYTES, UNIT_PRICE)
        VALUES (17, 'Cardigan', 8, 2, 5, 'Swift', 239, 5975000, 20)
    INTO TRACK (TRACK_ID, NAME, ALBUM_ID, MEDIA_TYPE_ID, GENRE_ID, COMPOSER, DURATION_IN_SECS, BYTES, UNIT_PRICE)
        VALUES (18, 'Exile', 8, 3, 5, 'Swift', 275, 6875000, 22)
    INTO TRACK (TRACK_ID, NAME, ALBUM_ID, MEDIA_TYPE_ID, GENRE_ID, COMPOSER, DURATION_IN_SECS, BYTES, UNIT_PRICE)
        VALUES (19, 'August', 8, 1, 5, 'Swift', 261, 6525000, 21)
    INTO TRACK (TRACK_ID, NAME, ALBUM_ID, MEDIA_TYPE_ID, GENRE_ID, COMPOSER, DURATION_IN_SECS, BYTES, UNIT_PRICE)
        VALUES (20, 'Sing', 9, 2, 5, 'Sheeran', 230, 5750000, 18)
    INTO TRACK (TRACK_ID, NAME, ALBUM_ID, MEDIA_TYPE_ID, GENRE_ID, COMPOSER, DURATION_IN_SECS, BYTES, UNIT_PRICE)
        VALUES (21, 'ThinkLoud', 9, 3, 5, 'Sheeran', 281, 7025000, 22)
    INTO TRACK (TRACK_ID, NAME, ALBUM_ID, MEDIA_TYPE_ID, GENRE_ID, COMPOSER, DURATION_IN_SECS, BYTES, UNIT_PRICE)
        VALUES (22, 'Yellow', 10, 1, 5, 'Coldplay', 270, 6750000, 20)
    INTO TRACK (TRACK_ID, NAME, ALBUM_ID, MEDIA_TYPE_ID, GENRE_ID, COMPOSER, DURATION_IN_SECS, BYTES, UNIT_PRICE)
        VALUES (23, 'Trouble', 10, 2, 5, 'Coldplay', 270, 6750000, 20)
    INTO TRACK (TRACK_ID, NAME, ALBUM_ID, MEDIA_TYPE_ID, GENRE_ID, COMPOSER, DURATION_IN_SECS, BYTES, UNIT_PRICE)
        VALUES (24, 'Sparks', 10, 3, 5, 'Coldplay', 240, 6000000, 18)
    INTO TRACK (TRACK_ID, NAME, ALBUM_ID, MEDIA_TYPE_ID, GENRE_ID, COMPOSER, DURATION_IN_SECS, BYTES, UNIT_PRICE)
        VALUES (25, 'Rolling', 11, 1, 2, 'Adele', 228, 5700000, 20)
    INTO TRACK (TRACK_ID, NAME, ALBUM_ID, MEDIA_TYPE_ID, GENRE_ID, COMPOSER, DURATION_IN_SECS, BYTES, UNIT_PRICE)
        VALUES (26, 'Someone', 11, 2, 2, 'Adele', 285, 7125000, 22)
    INTO TRACK (TRACK_ID, NAME, ALBUM_ID, MEDIA_TYPE_ID, GENRE_ID, COMPOSER, DURATION_IN_SECS, BYTES, UNIT_PRICE)
        VALUES (27, 'SetFire', 11, 3, 2, 'Adele', 242, 6050000, 19)
    INTO TRACK (TRACK_ID, NAME, ALBUM_ID, MEDIA_TYPE_ID, GENRE_ID, COMPOSER, DURATION_IN_SECS, BYTES, UNIT_PRICE)
        VALUES (28, 'Intro', 12, 1, 3, 'Eminem', 97, 2425000, 15)
    INTO TRACK (TRACK_ID, NAME, ALBUM_ID, MEDIA_TYPE_ID, GENRE_ID, COMPOSER, DURATION_IN_SECS, BYTES, UNIT_PRICE)
        VALUES (29, 'MyNameIs', 12, 2, 3, 'Eminem', 268, 6700000, 20)
    INTO TRACK (TRACK_ID, NAME, ALBUM_ID, MEDIA_TYPE_ID, GENRE_ID, COMPOSER, DURATION_IN_SECS, BYTES, UNIT_PRICE)
        VALUES (30, 'Guilty', 12, 3, 3, 'Eminem', 218, 5450000, 18)
    INTO TRACK (TRACK_ID, NAME, ALBUM_ID, MEDIA_TYPE_ID, GENRE_ID, COMPOSER, DURATION_IN_SECS, BYTES, UNIT_PRICE)
        VALUES (31, 'Grenade', 13, 1, 2, 'BrunoMars', 223, 5575000, 20)
    INTO TRACK (TRACK_ID, NAME, ALBUM_ID, MEDIA_TYPE_ID, GENRE_ID, COMPOSER, DURATION_IN_SECS, BYTES, UNIT_PRICE)
        VALUES (32, 'JustWay', 13, 2, 2, 'BrunoMars', 220, 5500000, 18)
    INTO TRACK (TRACK_ID, NAME, ALBUM_ID, MEDIA_TYPE_ID, GENRE_ID, COMPOSER, DURATION_IN_SECS, BYTES, UNIT_PRICE)
        VALUES (33, 'MarryYou', 13, 3, 2, 'BrunoMars', 232, 5800000, 19)
    INTO TRACK (TRACK_ID, NAME, ALBUM_ID, MEDIA_TYPE_ID, GENRE_ID, COMPOSER, DURATION_IN_SECS, BYTES, UNIT_PRICE)
        VALUES (34, 'Work', 14, 1, 4, 'Rihanna', 219, 5475000, 20)
    INTO TRACK (TRACK_ID, NAME, ALBUM_ID, MEDIA_TYPE_ID, GENRE_ID, COMPOSER, DURATION_IN_SECS, BYTES, UNIT_PRICE)
        VALUES (35, 'KissItBt', 14, 2, 4, 'Rihanna', 265, 6625000, 21)
    INTO TRACK (TRACK_ID, NAME, ALBUM_ID, MEDIA_TYPE_ID, GENRE_ID, COMPOSER, DURATION_IN_SECS, BYTES, UNIT_PRICE)
        VALUES (36, 'NeededMe', 14, 3, 4, 'Rihanna', 193, 4825000, 18)
    INTO TRACK (TRACK_ID, NAME, ALBUM_ID, MEDIA_TYPE_ID, GENRE_ID, COMPOSER, DURATION_IN_SECS, BYTES, UNIT_PRICE)
        VALUES (37, 'Formation', 15, 1, 4, 'Beyonce', 233, 5825000, 22)
    INTO TRACK (TRACK_ID, NAME, ALBUM_ID, MEDIA_TYPE_ID, GENRE_ID, COMPOSER, DURATION_IN_SECS, BYTES, UNIT_PRICE)
        VALUES (38, 'Sorry', 15, 2, 4, 'Beyonce', 220, 5500000, 20)
    INTO TRACK (TRACK_ID, NAME, ALBUM_ID, MEDIA_TYPE_ID, GENRE_ID, COMPOSER, DURATION_IN_SECS, BYTES, UNIT_PRICE)
        VALUES (39, 'Freedom', 15, 3, 4, 'Beyonce', 271, 6775000, 23)
    INTO TRACK (TRACK_ID, NAME, ALBUM_ID, MEDIA_TYPE_ID, GENRE_ID, COMPOSER, DURATION_IN_SECS, BYTES, UNIT_PRICE)
        VALUES (40, 'DNA', 16, 1, 3, 'Kendrick', 185, 4625000, 20)
    INTO TRACK (TRACK_ID, NAME, ALBUM_ID, MEDIA_TYPE_ID, GENRE_ID, COMPOSER, DURATION_IN_SECS, BYTES, UNIT_PRICE)
        VALUES (41, 'Humble', 16, 2, 3, 'Kendrick', 177, 4425000, 20)
    INTO TRACK (TRACK_ID, NAME, ALBUM_ID, MEDIA_TYPE_ID, GENRE_ID, COMPOSER, DURATION_IN_SECS, BYTES, UNIT_PRICE)
        VALUES (42, 'Loyalty', 16, 3, 3, 'Kendrick', 215, 5375000, 19)
    INTO TRACK (TRACK_ID, NAME, ALBUM_ID, MEDIA_TYPE_ID, GENRE_ID, COMPOSER, DURATION_IN_SECS, BYTES, UNIT_PRICE)
        VALUES (43, 'Money', 17, 1, 1, 'PinkFloyd', 382, 9550000, 22)
    INTO TRACK (TRACK_ID, NAME, ALBUM_ID, MEDIA_TYPE_ID, GENRE_ID, COMPOSER, DURATION_IN_SECS, BYTES, UNIT_PRICE)
        VALUES (44, 'Time', 17, 2, 1, 'PinkFloyd', 414, 10350000, 24)
    INTO TRACK (TRACK_ID, NAME, ALBUM_ID, MEDIA_TYPE_ID, GENRE_ID, COMPOSER, DURATION_IN_SECS, BYTES, UNIT_PRICE)
        VALUES (45, 'Breathe', 17, 3, 1, 'PinkFloyd', 169, 4225000, 18)
    INTO TRACK (TRACK_ID, NAME, ALBUM_ID, MEDIA_TYPE_ID, GENRE_ID, COMPOSER, DURATION_IN_SECS, BYTES, UNIT_PRICE)
        VALUES (46, 'One', 18, 1, 1, 'U2', 272, 6800000, 20)
    INTO TRACK (TRACK_ID, NAME, ALBUM_ID, MEDIA_TYPE_ID, GENRE_ID, COMPOSER, DURATION_IN_SECS, BYTES, UNIT_PRICE)
        VALUES (47, 'Mysterious', 18, 2, 1, 'U2', 245, 6125000, 19)
    INTO TRACK (TRACK_ID, NAME, ALBUM_ID, MEDIA_TYPE_ID, GENRE_ID, COMPOSER, DURATION_IN_SECS, BYTES, UNIT_PRICE)
        VALUES (48, 'UntilEnd', 18, 3, 1, 'U2', 260, 6500000, 20)
    INTO TRACK (TRACK_ID, NAME, ALBUM_ID, MEDIA_TYPE_ID, GENRE_ID, COMPOSER, DURATION_IN_SECS, BYTES, UNIT_PRICE)
        VALUES (49, 'Smells', 19, 1, 5, 'Nirvana', 301, 7525000, 22)
    INTO TRACK (TRACK_ID, NAME, ALBUM_ID, MEDIA_TYPE_ID, GENRE_ID, COMPOSER, DURATION_IN_SECS, BYTES, UNIT_PRICE)
        VALUES (50, 'ComeAsYou', 19, 2, 5, 'Nirvana', 219, 5475000, 19)
SELECT 1 FROM dual;

50 rows created.

# 16 POPULATING THE PLAYLIST SCHEMA

SQL> INSERT ALL
  2      INTO PLAYLIST (PLAYLIST_ID, NAME) VALUES (1, 'RockClass')
  3      INTO PLAYLIST (PLAYLIST_ID, NAME) VALUES (2, 'PopHits')
  4      INTO PLAYLIST (PLAYLIST_ID, NAME) VALUES (3, 'Mix90s')
  5      INTO PLAYLIST (PLAYLIST_ID, NAME) VALUES (4, 'Workout')
  6      INTO PLAYLIST (PLAYLIST_ID, NAME) VALUES (5, 'ChillVibes')
  7      INTO PLAYLIST (PLAYLIST_ID, NAME) VALUES (6, 'PartyTime')
  8      INTO PLAYLIST (PLAYLIST_ID, NAME) VALUES (7, 'LoveSongs')
  9      INTO PLAYLIST (PLAYLIST_ID, NAME) VALUES (8, 'RoadTrip')
 10      INTO PLAYLIST (PLAYLIST_ID, NAME) VALUES (9, 'Top50')
 11      INTO PLAYLIST (PLAYLIST_ID, NAME) VALUES (10, 'Acoustic')
 12      INTO PLAYLIST (PLAYLIST_ID, NAME) VALUES (11, 'HipHop')
 13      INTO PLAYLIST (PLAYLIST_ID, NAME) VALUES (12, 'JazzNight')
 14      INTO PLAYLIST (PLAYLIST_ID, NAME) VALUES (13, 'IndieMix')
 15      INTO PLAYLIST (PLAYLIST_ID, NAME) VALUES (14, 'FocusMode')
 16      INTO PLAYLIST (PLAYLIST_ID, NAME) VALUES (15, 'DanceBeat')
 17      INTO PLAYLIST (PLAYLIST_ID, NAME) VALUES (16, 'RelaxMode')
 18      INTO PLAYLIST (PLAYLIST_ID, NAME) VALUES (17, 'Throwback')
 19      INTO PLAYLIST (PLAYLIST_ID, NAME) VALUES (18, 'SoftRock')
 20      INTO PLAYLIST (PLAYLIST_ID, NAME) VALUES (19, 'Instrumental')
 21      INTO PLAYLIST (PLAYLIST_ID, NAME) VALUES (20, 'GlobalMix')
 22  SELECT 1 FROM dual;

20 rows created.

# 17 POPULATING THE PLAYLIST _TRACK SCHEMA

INSERT ALL
    INTO PLAYLIST_TRACK (PLAYLIST_ID, TRACK_ID) VALUES (1, 1)
    INTO PLAYLIST_TRACK (PLAYLIST_ID, TRACK_ID) VALUES (1, 2)
    INTO PLAYLIST_TRACK (PLAYLIST_ID, TRACK_ID) VALUES (1, 3)
    INTO PLAYLIST_TRACK (PLAYLIST_ID, TRACK_ID) VALUES (2, 4)
    INTO PLAYLIST_TRACK (PLAYLIST_ID, TRACK_ID) VALUES (2, 5)
    INTO PLAYLIST_TRACK (PLAYLIST_ID, TRACK_ID) VALUES (2, 6)
    INTO PLAYLIST_TRACK (PLAYLIST_ID, TRACK_ID) VALUES (3, 7)
    INTO PLAYLIST_TRACK (PLAYLIST_ID, TRACK_ID) VALUES (3, 8)
    INTO PLAYLIST_TRACK (PLAYLIST_ID, TRACK_ID) VALUES (3, 9)
    INTO PLAYLIST_TRACK (PLAYLIST_ID, TRACK_ID) VALUES (4, 10)
    INTO PLAYLIST_TRACK (PLAYLIST_ID, TRACK_ID) VALUES (4, 11)
    INTO PLAYLIST_TRACK (PLAYLIST_ID, TRACK_ID) VALUES (4, 12)
    INTO PLAYLIST_TRACK (PLAYLIST_ID, TRACK_ID) VALUES (5, 13)
    INTO PLAYLIST_TRACK (PLAYLIST_ID, TRACK_ID) VALUES (5, 14)
    INTO PLAYLIST_TRACK (PLAYLIST_ID, TRACK_ID) VALUES (5, 15)
    INTO PLAYLIST_TRACK (PLAYLIST_ID, TRACK_ID) VALUES (6, 16)
    INTO PLAYLIST_TRACK (PLAYLIST_ID, TRACK_ID) VALUES (6, 17)
    INTO PLAYLIST_TRACK (PLAYLIST_ID, TRACK_ID) VALUES (6, 18)
    INTO PLAYLIST_TRACK (PLAYLIST_ID, TRACK_ID) VALUES (7, 19)
    INTO PLAYLIST_TRACK (PLAYLIST_ID, TRACK_ID) VALUES (7, 20)
    INTO PLAYLIST_TRACK (PLAYLIST_ID, TRACK_ID) VALUES (7, 21)
    INTO PLAYLIST_TRACK (PLAYLIST_ID, TRACK_ID) VALUES (8, 22)
    INTO PLAYLIST_TRACK (PLAYLIST_ID, TRACK_ID) VALUES (8, 23)
    INTO PLAYLIST_TRACK (PLAYLIST_ID, TRACK_ID) VALUES (8, 24)
    INTO PLAYLIST_TRACK (PLAYLIST_ID, TRACK_ID) VALUES (9, 25)
    INTO PLAYLIST_TRACK (PLAYLIST_ID, TRACK_ID) VALUES (9, 26)
    INTO PLAYLIST_TRACK (PLAYLIST_ID, TRACK_ID) VALUES (9, 27)
    INTO PLAYLIST_TRACK (PLAYLIST_ID, TRACK_ID) VALUES (10, 28)
    INTO PLAYLIST_TRACK (PLAYLIST_ID, TRACK_ID) VALUES (10, 29)
    INTO PLAYLIST_TRACK (PLAYLIST_ID, TRACK_ID) VALUES (10, 30)
SELECT 1 FROM dual;

# 17 JOINING PLAYLIST AND PLAYLIST_TRACK SCHEMA

SELECT 
    p.PLAYLIST_ID,
    p.NAME AS PLAYLIST_NAME,
    t.TRACK_ID,
    t.NAME AS TRACK_NAME
FROM PLAYLIST p
JOIN PLAYLIST_TRACK pt
    ON p.PLAYLIST_ID = pt.PLAYLIST_ID
JOIN TRACK t
    ON pt.TRACK_ID = t.TRACK_ID
ORDER BY p.PLAYLIST_ID, t.TRACK_ID;

PLAYLIST_ID PLAYLIST_NAM   TRACK_ID TRACK_NAME
----------- ------------ ---------- ----------
          1 RockClass             1 Bohemian
          1 RockClass             2 LoveLife
          1 RockClass             3 RockYou
          2 PopHits               4 Champion
          2 PopHits               5 Together
          2 PopHits               6 Something
          3 Mix90s                7 Sunshine
          3 Mix90s                8 BillieJn
          3 Mix90s                9 Thriller
          4 Workout              10 BeatIt
          4 Workout              11 Virgin
          4 Workout              12 Material
          5 ChillVibes           13 RocketMn
          5 ChillVibes           14 TinyDanc
          5 ChillVibes           15 BlueHaw
          6 PartyTime            16 CantHelp
          6 PartyTime            17 Cardigan
          6 PartyTime            18 Exile
          7 LoveSongs            19 August
          7 LoveSongs            20 Sing
          7 LoveSongs            21 ThinkLoud
          8 RoadTrip             22 Yellow
          8 RoadTrip             23 Trouble
          8 RoadTrip             24 Sparks
          9 Top50                25 Rolling
          9 Top50                26 Someone
          9 Top50                27 SetFire
         10 Acoustic             28 Intro
         10 Acoustic             29 MyNameIs
         10 Acoustic             30 Guilty

30 rows selected.

# 18 MULTI-JOIN IN DATABASE :: PLAYLIST,PLAYLIST_TRACK,TRACK,ALBUM,ARTIST 

SELECT 
    pl.PLAYLIST_ID,
    pl.NAME       AS PLAYLIST_NAME,
    t.TRACK_ID,
    t.NAME        AS TRACK_NAME,
    a.TITLE       AS ALBUM_TITLE,
    ar.NAME       AS ARTIST_NAME
FROM PLAYLIST pl
JOIN PLAYLIST_TRACK pt 
    ON pl.PLAYLIST_ID = pt.PLAYLIST_ID
JOIN TRACK t 
    ON pt.TRACK_ID = t.TRACK_ID
JOIN ALBUM a 
    ON t.ALBUM_ID = a.ALBUM_ID
JOIN ARTIST ar 
    ON a.ARTIST_ID = ar.ARTIST_ID
ORDER BY pl.PLAYLIST_ID, t.TRACK_ID;

PLAYLIST_ID PLAYLIST_NAM   TRACK_ID TRACK_NAME ALBUM_TITLE     ARTIST_NAM
----------- ------------ ---------- ---------- --------------- ----------
          1 RockClass             1 Bohemian   Night at Opa    Queen
          1 RockClass             2 LoveLife   Night at Opa    Queen
          1 RockClass             3 RockYou    News of Worl    Queen
          2 PopHits               4 Champion   News of Worl    Queen
          2 PopHits               5 Together   Abbey Road      Beatles
          2 PopHits               6 Something  Abbey Road      Beatles
          3 Mix90s                7 Sunshine   Abbey Road      Beatles
          3 Mix90s                8 BillieJn   Thriller        M. Jackson
          3 Mix90s                9 Thriller   Thriller        M. Jackson
          4 Workout              10 BeatIt     Thriller        M. Jackson
          4 Workout              11 Virgin     Like a Virgi    Madonna
          4 Workout              12 Material   Like a Virgi    Madonna
          5 ChillVibes           13 RocketMn   Rocket Man      Elton John
          5 ChillVibes           14 TinyDanc   Rocket Man      Elton John
          5 ChillVibes           15 BlueHaw    Blue Hawaii     E. Presley
          6 PartyTime            16 CantHelp   Blue Hawaii     E. Presley
          6 PartyTime            17 Cardigan   Folklore        T. Swift
          6 PartyTime            18 Exile      Folklore        T. Swift
          7 LoveSongs            19 August     Folklore        T. Swift
          7 LoveSongs            20 Sing       X               E. Sheeran
          7 LoveSongs            21 ThinkLoud  X               E. Sheeran
          8 RoadTrip             22 Yellow     Parachutes      Coldplay
          8 RoadTrip             23 Trouble    Parachutes      Coldplay
          8 RoadTrip             24 Sparks     Parachutes      Coldplay
          9 Top50                25 Rolling    21              Adele
          9 Top50                26 Someone    21              Adele
          9 Top50                27 SetFire    21              Adele
         10 Acoustic             28 Intro      Slim Shady      Eminem
         10 Acoustic             29 MyNameIs   Slim Shady      Eminem
         10 Acoustic             30 Guilty     Slim Shady      Eminem

30 rows selected.

# 19 POPULATING MEDITYPE SCHEMA

INSERT ALL
    INTO MEDIA_TYPE (MEDIA_TYPE_ID, NAME) VALUES (1, 'MP3')
    INTO MEDIA_TYPE (MEDIA_TYPE_ID, NAME) VALUES (2, 'WAV')
    INTO MEDIA_TYPE (MEDIA_TYPE_ID, NAME) VALUES (3, 'FLAC')
    INTO MEDIA_TYPE (MEDIA_TYPE_ID, NAME) VALUES (4, 'AAC')
    INTO MEDIA_TYPE (MEDIA_TYPE_ID, NAME) VALUES (5, 'OGG')
    INTO MEDIA_TYPE (MEDIA_TYPE_ID, NAME) VALUES (6, 'ALAC')
    INTO MEDIA_TYPE (MEDIA_TYPE_ID, NAME) VALUES (7, 'AIFF')
SELECT 1 FROM dual;

7 rows created.

# 20 POPULATING GENRE SCHEMA

INSERT ALL
    INTO GENRE (GENRE_ID, NAME) VALUES (1, 'Rock')
    INTO GENRE (GENRE_ID, NAME) VALUES (2, 'Pop')
    INTO GENRE (GENRE_ID, NAME) VALUES (3, 'HipHop')
    INTO GENRE (GENRE_ID, NAME) VALUES (4, 'Jazz')
    INTO GENRE (GENRE_ID, NAME) VALUES (5, 'Classical')
    INTO GENRE (GENRE_ID, NAME) VALUES (6, 'Metal')
    INTO GENRE (GENRE_ID, NAME) VALUES (7, 'Country')
    INTO GENRE (GENRE_ID, NAME) VALUES (8, 'R&B')
    INTO GENRE (GENRE_ID, NAME) VALUES (9, 'Indie')
    INTO GENRE (GENRE_ID, NAME) VALUES (10, 'Reggae')
    INTO GENRE (GENRE_ID, NAME) VALUES (11, 'EDM')
    INTO GENRE (GENRE_ID, NAME) VALUES (12, 'Folk')
SELECT 1 FROM dual;

# 20 MULTI-JOIN IN DATABASE :: PLAYLIST,PLAYLIST_TRACK,TRACK,ALBUM,ARTIST,MEDIA_TYPE,GENRE

SELECT 
    pl.PLAYLIST_ID,
    pl.NAME              AS PLAYLIST_NAME,
    t.TRACK_ID,
    t.NAME               AS TRACK_NAME,
    a.TITLE              AS ALBUM_TITLE,
    ar.NAME              AS ARTIST_NAME,
    mt.NAME              AS MEDIA_TYPE,
    g.NAME               AS GENRE
FROM PLAYLIST pl
JOIN PLAYLIST_TRACK pt 
    ON pl.PLAYLIST_ID = pt.PLAYLIST_ID
JOIN TRACK t 
    ON pt.TRACK_ID = t.TRACK_ID
JOIN ALBUM a 
    ON t.ALBUM_ID = a.ALBUM_ID
JOIN ARTIST ar 
    ON a.ARTIST_ID = ar.ARTIST_ID
JOIN MEDIA_TYPE mt
    ON t.MEDIA_TYPE_ID = mt.MEDIA_TYPE_ID
JOIN GENRE g
    ON t.GENRE_ID = g.GENRE_ID
ORDER BY pl.PLAYLIST_ID, t.TRACK_ID;

PLAYLIST_ID PLAYLIST_NAM   TRACK_ID TRACK_NAME ALBUM_TITLE     ARTIST_NAM MEDIA_TYPE GENRE
----------- ------------ ---------- ---------- --------------- ---------- ---------- ------------
          1 RockClass             1 Bohemian   Night at Opa    Queen      MP3        Rock
          1 RockClass             2 LoveLife   Night at Opa    Queen      WAV        Rock
          1 RockClass             3 RockYou    News of Worl    Queen      FLAC       Rock
          2 PopHits               4 Champion   News of Worl    Queen      MP3        Rock
          2 PopHits               5 Together   Abbey Road      Beatles    WAV        Rock
          2 PopHits               6 Something  Abbey Road      Beatles    FLAC       Rock
          3 Mix90s                7 Sunshine   Abbey Road      Beatles    MP3        Rock
          3 Mix90s                8 BillieJn   Thriller        M. Jackson WAV        Pop
          3 Mix90s                9 Thriller   Thriller        M. Jackson FLAC       Pop
          4 Workout              10 BeatIt     Thriller        M. Jackson MP3        Pop
          4 Workout              11 Virgin     Like a Virgi    Madonna    WAV        Pop
          4 Workout              12 Material   Like a Virgi    Madonna    FLAC       Pop
          5 ChillVibes           13 RocketMn   Rocket Man      Elton John MP3        Rock
          5 ChillVibes           14 TinyDanc   Rocket Man      Elton John WAV        Rock
          5 ChillVibes           15 BlueHaw    Blue Hawaii     E. Presley FLAC       Pop
          6 PartyTime            16 CantHelp   Blue Hawaii     E. Presley MP3        Pop
          6 PartyTime            17 Cardigan   Folklore        T. Swift   WAV        Classical
          6 PartyTime            18 Exile      Folklore        T. Swift   FLAC       Classical
          7 LoveSongs            19 August     Folklore        T. Swift   MP3        Classical
          7 LoveSongs            20 Sing       X               E. Sheeran WAV        Classical
          7 LoveSongs            21 ThinkLoud  X               E. Sheeran FLAC       Classical
          8 RoadTrip             22 Yellow     Parachutes      Coldplay   MP3        Classical
          8 RoadTrip             23 Trouble    Parachutes      Coldplay   WAV        Classical
          8 RoadTrip             24 Sparks     Parachutes      Coldplay   FLAC       Classical
          9 Top50                25 Rolling    21              Adele      MP3        Pop
          9 Top50                26 Someone    21              Adele      WAV        Pop
          9 Top50                27 SetFire    21              Adele      FLAC       Pop
         10 Acoustic             28 Intro      Slim Shady      Eminem     MP3        HipHop
         10 Acoustic             29 MyNameIs   Slim Shady      Eminem     WAV        HipHop
         10 Acoustic             30 Guilty     Slim Shady      Eminem     FLAC       HipHop

30 rows selected.

# 21 POPULATING INVOICE SCHEMA

INSERT ALL
    INTO INVOICE (INVOICE_ID, CUSTOMER_ID, INVOICE_DATE, BILLING_ADDRESS, BILLING_CITY, BILLING_STATE, BILLING_COUNTRY, BILLING_POSTAL_CODE, TOTAL) 
    VALUES (1, 101, DATE '2025-01-05', '123 Queen St', 'London', 'LN', 'UK', 'SW1A1AA', 19.99)
    INTO INVOICE VALUES (2, 102, DATE '2025-01-07', '55 Abbey Rd', 'London', 'LN', 'UK', 'NW87JL', 29.99)
    INTO INVOICE VALUES (3, 103, DATE '2025-01-09', '9 King St', 'New York', 'NY', 'USA', '10001', 15.99)
    INTO INVOICE VALUES (4, 104, DATE '2025-01-10', '77 Sunset Blvd', 'LosAng', 'CA', 'USA', '90001', 25.00)
    INTO INVOICE VALUES (5, 105, DATE '2025-01-12', '12 Marine Dr', 'Mumbai', 'MH', 'India', '400001', 10.00)
    INTO INVOICE VALUES (6, 106, DATE '2025-01-14', '88 Broadway', 'New York', 'NY', 'USA', '10002', 30.00)
    INTO INVOICE VALUES (7, 107, DATE '2025-01-16', '221B Baker St', 'London', 'LN', 'UK', 'NW16XE', 12.00)
    INTO INVOICE VALUES (8, 108, DATE '2025-01-18', '5 Champs Ely', 'Paris', 'PR', 'France', '75001', 20.50)
    INTO INVOICE VALUES (9, 109, DATE '2025-01-20', 'Karlstr 11', 'Berlin', 'BE', 'Germany', '10115', 18.00)
    INTO INVOICE VALUES (10, 110, DATE '2025-01-22', '2 Shibuya', 'Tokyo', 'TK', 'Japan', '1500002', 15.50)
    INTO INVOICE VALUES (11, 111, DATE '2025-01-23', '44 Orchard Rd', 'Singapore', 'SG', 'Singapore', '238880', 16.99)
    INTO INVOICE VALUES (12, 112, DATE '2025-01-25', '1 George St', 'Sydney', 'NSW', 'Australia', '2000', 19.99)
    INTO INVOICE VALUES (13, 113, DATE '2025-01-26', '88 Collins St', 'Melbourne', 'VIC', 'Australia', '3000', 21.99)
    INTO INVOICE VALUES (14, 114, DATE '2025-01-27', '3 Times Sq', 'New York', 'NY', 'USA', '10036', 22.50)
    INTO INVOICE VALUES (15, 115, DATE '2025-01-28', '14 Park Ave', 'New Delhi', 'DL', 'India', '110001', 14.99)
    INTO INVOICE VALUES (16, 116, DATE '2025-01-29', '10 Marina Bay', 'Singapore', 'SG', 'Singapore', '018956', 25.00)
    INTO INVOICE VALUES (17, 117, DATE '2025-01-30', '6 Gran Via', 'Madrid', 'MD', 'Spain', '28013', 17.50)
    INTO INVOICE VALUES (18, 118, DATE '2025-02-01', '15 Piazza Nav', 'Rome', 'RM', 'Italy', '00186', 23.99)
    INTO INVOICE VALUES (19, 119, DATE '2025-02-02', '22 Nevsky Pr', 'Moscow', 'MS', 'Russia', '190000', 27.99)
    INTO INVOICE VALUES (20, 120, DATE '2025-02-03', '8 Oxford St', 'London', 'LN', 'UK', 'W1D1AA', 19.00)
    INTO INVOICE VALUES (21, 121, DATE '2025-02-04', '32 Fifth Ave', 'New York', 'NY', 'USA', '10011', 12.99)
    INTO INVOICE VALUES (22, 122, DATE '2025-02-05', '16 Orchard', 'Toronto', 'ON', 'Canada', 'M5H2N2', 15.50)
    INTO INVOICE VALUES (23, 123, DATE '2025-02-06', '20 Bund', 'Shanghai', 'SH', 'China', '200002', 29.99)
    INTO INVOICE VALUES (24, 124, DATE '2025-02-07', '5 Seoul St', 'Seoul', 'SL', 'Korea', '04524', 16.99)
    INTO INVOICE VALUES (25, 125, DATE '2025-02-08', '66 Sheikh Rd', 'Dubai', 'DB', 'UAE', '00000', 33.00)
    INTO INVOICE VALUES (26, 126, DATE '2025-02-09', '45 Orchard', 'Singapore', 'SG', 'Singapore', '238885', 27.49)
    INTO INVOICE VALUES (27, 127, DATE '2025-02-10', '23 Marina Dr', 'Mumbai', 'MH', 'India', '400002', 19.99)
    INTO INVOICE VALUES (28, 128, DATE '2025-02-11', '9 Ginza Rd', 'Tokyo', 'TK', 'Japan', '1040061', 22.99)
    INTO INVOICE VALUES (29, 129, DATE '2025-02-12', '3 Champs Ely', 'Paris', 'PR', 'France', '75002', 18.49)
    INTO INVOICE VALUES (30, 130, DATE '2025-02-13', '11 Baker St', 'London', 'LN', 'UK', 'NW17XE', 20.99)
SELECT 1 FROM dual;

# 22 POPULATING INVOICE_LINE SCHEMA

INSERT ALL
    INTO INVOICE_LINE (INVOICE_LINE_ID, INVOICE_ID, TRACK_ID, UNIT_PRICE, QUANTITY) VALUES (1, 1, 1, 9.99, 1)
    INTO INVOICE_LINE VALUES (2, 2, 2, 14.99, 2)
    INTO INVOICE_LINE VALUES (3, 3, 3, 7.99, 1)
    INTO INVOICE_LINE VALUES (4, 4, 4, 12.50, 2)
    INTO INVOICE_LINE VALUES (5, 5, 5, 10.00, 1)
    INTO INVOICE_LINE VALUES (6, 6, 6, 15.00, 2)
    INTO INVOICE_LINE VALUES (7, 7, 7, 12.00, 1)
    INTO INVOICE_LINE VALUES (8, 8, 8, 10.25, 2)
    INTO INVOICE_LINE VALUES (9, 9, 9, 9.00, 1)
    INTO INVOICE_LINE VALUES (10, 10, 10, 8.50, 2)
    INTO INVOICE_LINE VALUES (11, 11, 11, 8.99, 1)
    INTO INVOICE_LINE VALUES (12, 12, 12, 10.50, 1)
    INTO INVOICE_LINE VALUES (13, 13, 13, 11.99, 2)
    INTO INVOICE_LINE VALUES (14, 14, 14, 13.50, 1)
    INTO INVOICE_LINE VALUES (15, 15, 15, 9.99, 1)
    INTO INVOICE_LINE VALUES (16, 16, 16, 12.00, 2)
    INTO INVOICE_LINE VALUES (17, 17, 17, 10.75, 1)
    INTO INVOICE_LINE VALUES (18, 18, 18, 14.25, 2)
    INTO INVOICE_LINE VALUES (19, 19, 19, 13.00, 1)
    INTO INVOICE_LINE VALUES (20, 20, 20, 9.50, 1)
    INTO INVOICE_LINE VALUES (21, 21, 21, 8.99, 2)
    INTO INVOICE_LINE VALUES (22, 22, 22, 10.25, 1)
    INTO INVOICE_LINE VALUES (23, 23, 23, 12.75, 2)
    INTO INVOICE_LINE VALUES (24, 24, 24, 11.50, 1)
    INTO INVOICE_LINE VALUES (25, 25, 25, 16.50, 2)
    INTO INVOICE_LINE VALUES (26, 26, 26, 13.99, 1)
    INTO INVOICE_LINE VALUES (27, 27, 27, 12.25, 2)
    INTO INVOICE_LINE VALUES (28, 28, 28, 14.50, 1)
    INTO INVOICE_LINE VALUES (29, 29, 29, 15.99, 1)
    INTO INVOICE_LINE VALUES (30, 30, 30, 11.25, 2)
SELECT 1 FROM dual;


# 23 POPULATING THE EMPLOYEE SCHEMA

INSERT ALL
    INTO EMPLOYEE (EMPLOYEE_ID, LASTNAME, FIRSTNAME, TITLE, REPORTS_TO, BIRTH_DATE, HIRE_DATE, ADDRESS, CITY, STATE, COUNTRY, POSTAL_CODE, PHONE, FAX, EMAIL) 
    VALUES (1, 'Adams', 'Andrew', 'Manager', NULL, DATE '1980-05-12', DATE '2010-01-15', '123 Queen St', 'London', 'LN', 'UK', 'SW1A1AA', '+44-20-111111', '+44-20-111112', 'andrew.adams@musicdb.com')
    INTO EMPLOYEE VALUES (2, 'Baker', 'Susan', 'Sales', 1, DATE '1985-09-20', DATE '2012-03-10', '88 Broadway', 'New York', 'NY', 'USA', '10001', '+1-212-222222', '+1-212-222223', 'susan.baker@musicdb.com')
    INTO EMPLOYEE VALUES (3, 'Clark', 'James', 'Sales', 1, DATE '1983-07-15', DATE '2013-05-01', '55 Abbey Rd', 'London', 'LN', 'UK', 'NW87JL', '+44-20-333333', '+44-20-333334', 'james.clark@musicdb.com')
    INTO EMPLOYEE VALUES (4, 'Diaz', 'Maria', 'IT', 1, DATE '1990-01-10', DATE '2015-07-18', '77 Sunset Blvd', 'LosAng', 'CA', 'USA', '90001', '+1-310-444444', '+1-310-444445', 'maria.diaz@musicdb.com')
    INTO EMPLOYEE VALUES (5, 'Evans', 'David', 'Sales', 2, DATE '1988-03-22', DATE '2016-09-12', '12 Marine Dr', 'Mumbai', 'MH', 'India', '400001', '+91-22-555555', '+91-22-555556', 'david.evans@musicdb.com')
    INTO EMPLOYEE VALUES (6, 'Foster', 'Emma', 'Support', 2, DATE '1992-12-05', DATE '2017-11-21', '221B Baker St', 'London', 'LN', 'UK', 'NW16XE', '+44-20-666666', '+44-20-666667', 'emma.foster@musicdb.com')
    INTO EMPLOYEE VALUES (7, 'Green', 'Robert', 'Support', 3, DATE '1989-06-11', DATE '2018-02-05', '5 Champs Ely', 'Paris', 'PR', 'France', '75001', '+33-1-777777', '+33-1-777778', 'robert.green@musicdb.com')
    INTO EMPLOYEE VALUES (8, 'Hall', 'Olivia', 'Sales', 3, DATE '1993-08-30', DATE '2019-04-14', 'Karlstr 11', 'Berlin', 'BE', 'Germany', '10115', '+49-30-888888', '+49-30-888889', 'olivia.hall@musicdb.com')
    INTO EMPLOYEE VALUES (9, 'Ivy', 'Sophia', 'IT', 4, DATE '1991-11-25', DATE '2020-06-20', '2 Shibuya', 'Tokyo', 'TK', 'Japan', '1500002', '+81-3-999999', '+81-3-999990', 'sophia.ivy@musicdb.com')
    INTO EMPLOYEE VALUES (10, 'Jones', 'Michael', 'Support', 4, DATE '1987-04-03', DATE '2021-08-15', '44 Orchard Rd', 'Singapore', 'SG', 'Singapore', '238880', '+65-10-123456', '+65-10-123457', 'michael.jones@musicdb.com')
SELECT 1 FROM dual;

# 24 POPULATING THE CUSTOMER SCHEMA 

INSERT ALL
    INTO CUSTOMER VALUES (1, 'Smith', 'John', 'Acme Corp', '123 King St', 'London', 'LN', 'UK', 'SW1A2AA', '+44-20-100000', '+44-20-100001', 'jsmith@acme.com', '6')
    INTO CUSTOMER VALUES (2, 'Johnson', 'Mary', 'Tech Ltd', '55 Wall St', 'New York', 'NY', 'USA', '10005', '+1-212-100002', '+1-212-100003', 'maryj@tech.com', '7')
    INTO CUSTOMER VALUES (3, 'Williams', 'Robert', 'Global Inc', '9 Queen Rd', 'Toronto', 'ON', 'Canada', 'M5H2N2', '+1-416-100004', '+1-416-100005', 'rwilliams@global.com', '8')
    INTO CUSTOMER VALUES (4, 'Brown', 'Linda', 'Music Co', '88 Champs Ely', 'Paris', 'PR', 'France', '75008', '+33-1-100006', '+33-1-100007', 'lbrown@musicco.com', '6')
    INTO CUSTOMER VALUES (5, 'Jones', 'Michael', 'Media Ltd', '7 Marine Dr', 'Mumbai', 'MH', 'India', '400002', '+91-22-100008', '+91-22-100009', 'mjones@media.com', '9')
    INTO CUSTOMER VALUES (6, 'Garcia', 'Maria', 'AudioWorks', '11 Karlstr', 'Berlin', 'BE', 'Germany', '10116', '+49-30-100010', '+49-30-100011', 'mgarcia@audiowrk.com', '10')
    INTO CUSTOMER VALUES (7, 'Miller', 'James', 'Sound Inc', '3 Orchard Rd', 'Singapore', 'SG', 'Singapore', '238881', '+65-10-100012', '+65-10-100013', 'jmiller@sound.com', '8')
    INTO CUSTOMER VALUES (8, 'Davis', 'Patricia', 'Melody LLC', '99 Broadway', 'New York', 'NY', 'USA', '10002', '+1-212-100014', '+1-212-100015', 'pdavis@melody.com', '7')
    INTO CUSTOMER VALUES (9, 'Rodriguez', 'David', 'Harmony Ltd', '22 Ginza Rd', 'Tokyo', 'TK', 'Japan', '1040061', '+81-3-100016', '+81-3-100017', 'drod@harmony.com', '9')
    INTO CUSTOMER VALUES (10, 'Martinez', 'Jennifer', 'Tune Corp', '12 Piazza Nav', 'Rome', 'RM', 'Italy', '00186', '+39-6-100018', '+39-6-100019', 'jmartinez@tune.com', '10')
    INTO CUSTOMER VALUES (11, 'Hernandez', 'Charles', 'NoteWorks', '4 Nevsky Pr', 'Moscow', 'MS', 'Russia', '190000', '+7-495-100020', '+7-495-100021', 'chernandez@note.com', '6')
    INTO CUSTOMER VALUES (12, 'Lopez', 'Jessica', 'Beat Co', '15 Oxford St', 'London', 'LN', 'UK', 'W1D1AA', '+44-20-100022', '+44-20-100023', 'jlopez@beatco.com', '7')
    INTO CUSTOMER VALUES (13, 'Gonzalez', 'Daniel', 'Rhythm Ltd', '2 Fifth Ave', 'New York', 'NY', 'USA', '10011', '+1-212-100024', '+1-212-100025', 'dgonzalez@rhythm.com', '8')
    INTO CUSTOMER VALUES (14, 'Wilson', 'Sarah', 'Symphony Inc', '1 Gran Via', 'Madrid', 'MD', 'Spain', '28013', '+34-91-100026', '+34-91-100027', 'swilson@symphony.com', '10')
    INTO CUSTOMER VALUES (15, 'Anderson', 'Paul', 'ChordWorks', '20 George St', 'Sydney', 'NSW', 'Australia', '2000', '+61-2-100028', '+61-2-100029', 'panders@chord.com', '9')
    INTO CUSTOMER VALUES (16, 'Thomas', 'Laura', 'Echo Corp', '5 King St', 'London', 'LN', 'UK', 'SW1A1AA', '+44-20-100030', '+44-20-100031', 'lthomas@echo.com', '7')
    INTO CUSTOMER VALUES (17, 'Taylor', 'Mark', 'Pulse Ltd', '7 Main St', 'Chicago', 'IL', 'USA', '60601', '+1-312-100032', '+1-312-100033', 'mtaylor@pulse.com', '8')
    INTO CUSTOMER VALUES (18, 'Moore', 'Nancy', 'ToneWorks', '45 Queen St', 'Toronto', 'ON', 'Canada', 'M5H1P9', '+1-416-100034', '+1-416-100035', 'nmoore@tone.com', '9')
    INTO CUSTOMER VALUES (19, 'Jackson', 'Brian', 'Vibe Inc', '8 Sunset Blvd', 'LosAngels', 'CA', 'USA', '90028', '+1-213-100036', '+1-213-100037', 'bjackson@vibe.com', '6')
    INTO CUSTOMER VALUES (20, 'White', 'Karen', 'Lyric Ltd', '66 High St', 'Dublin', 'DB', 'Ireland', 'D02Y006', '+353-1-100038', '+353-1-100039', 'kwhite@lyric.com', '10')
    INTO CUSTOMER VALUES (21, 'Harris', 'Steven', 'Chord Inc', '17 Elm St', 'Boston', 'MA', 'USA', '02108', '+1-617-100040', '+1-617-100041', 'sharris@chord.com', '7')
    INTO CUSTOMER VALUES (22, 'Clark', 'Emily', 'Octave LLC', '2 Rue Rivoli', 'Paris', 'PR', 'France', '75004', '+33-1-100042', '+33-1-100043', 'eclark@octave.com', '8')
    INTO CUSTOMER VALUES (23, 'Lewis', 'George', 'Harmony Co', '31 King Rd', 'Toronto', 'ON', 'Canada', 'M4Y2A6', '+1-416-100044', '+1-416-100045', 'glewis@harmny.com', '9')
    INTO CUSTOMER VALUES (24, 'Robinson', 'Anna', 'Riff Ltd', '6 Marina Bay', 'Singapore', 'SG', 'Singapore', '018900', '+65-10-100046', '+65-10-100047', 'arobinson@riff.com', '6')
    INTO CUSTOMER VALUES (25, 'Walker', 'Kevin', 'ScaleWorks', '88 Market St', 'SanJose', 'CA', 'USA', '95113', '+1-408-100048', '+1-408-100049', 'kwalker@scale.com', '7')
    INTO CUSTOMER VALUES (26, 'Hall', 'Olivia', 'Melody Inc', '15 Collins St', 'Melbourne', 'VIC', 'Australia', '3000', '+61-3-100050', '+61-3-100051', 'ohall@melody.com', '8')
    INTO CUSTOMER VALUES (27, 'Allen', 'Patrick', 'Tune Ltd', '19 Oxford Rd', 'Manchester', 'MN', 'UK', 'M11DA', '+44-161-100052', '+44-161-100053', 'pallen@tune.com', '9')
    INTO CUSTOMER VALUES (28, 'Young', 'Sophia', 'Tempo Corp', '5 Karlstr', 'Berlin', 'BE', 'Germany', '10117', '+49-30-100054', '+49-30-100055', 'syoung@tempo.com', '10')
    INTO CUSTOMER VALUES (29, 'King', 'Edward', 'BeatWorks', '17 Nevsky', 'Moscow', 'MS', 'Russia', '190008', '+7-495-100056', '+7-495-100057', 'eking@beatwrk.com', '6')
    INTO CUSTOMER VALUES (30, 'Scott', 'Grace', 'Note Ltd', '3 Orchard', 'Singapore', 'SG', 'Singapore', '238882', '+65-10-100058', '+65-10-100059', 'gscott@note.com', '7')
SELECT 1 FROM dual;


# MASTER JOIN WITH NO BOTTLE NECK 

SELECT 
    C.CUSTOMER_ID,
    C.FIRSTNAME        AS CUSTOMER_FIRSTNAME,
    C.LASTNAME         AS CUSTOMER_LASTNAME,
    C.EMAIL            AS CUSTOMER_EMAIL,
    E.EMPLOYEE_ID,
    E.FIRSTNAME        AS EMP_FIRSTNAME,
    E.LASTNAME         AS EMP_LASTNAME,
    I.INVOICE_ID,
    I.INVOICE_DATE,
    I.BILLING_ADDRESS,
    I.BILLING_CITY,
    I.BILLING_STATE,
    I.BILLING_COUNTRY,
    I.TOTAL            AS INVOICE_TOTAL,
    IL.INVOICE_LINE_ID,
    IL.QUANTITY,
    IL.UNIT_PRICE      AS LINE_UNIT_PRICE,
    T.TRACK_ID,
    T.NAME             AS TRACK_NAME,
    T.DURATION_IN_SECS,
    T.UNIT_PRICE       AS TRACK_PRICE,
    MT.NAME            AS MEDIA_TYPE,
    G.NAME             AS GENRE,
    A.ALBUM_ID,
    A.TITLE            AS ALBUM_TITLE,
    AR.ARTIST_ID,
    AR.NAME            AS ARTIST_NAME
FROM CUSTOMER C
LEFT JOIN EMPLOYEE E 
    ON C.SUPPORT_REP_ID = E.EMPLOYEE_ID
JOIN INVOICE I 
    ON C.CUSTOMER_ID = I.CUSTOMER_ID
JOIN INVOICE_LINE IL 
    ON I.INVOICE_ID = IL.INVOICE_ID
JOIN TRACK T 
    ON IL.TRACK_ID = T.TRACK_ID
JOIN MEDIA_TYPE MT 
    ON T.MEDIA_TYPE_ID = MT.MEDIA_TYPE_ID
JOIN GENRE G 
    ON T.GENRE_ID = G.GENRE_ID
JOIN ALBUM A 
    ON T.ALBUM_ID = A.ALBUM_ID
JOIN ARTIST AR 
    ON A.ARTIST_ID = AR.ARTIST_ID
ORDER BY C.CUSTOMER_ID, I.INVOICE_ID, IL.INVOICE_LINE_ID;

no rows selected.

# BOTTLING NECK 

-- 1. EMPLOYEE (Support Rep) -- pick new ID
INSERT INTO EMPLOYEE (EMPLOYEE_ID, LASTNAME, FIRSTNAME, TITLE, HIRE_DATE, EMAIL)
VALUES (101, 'Smith', 'John', 'Sales', SYSDATE, 'john.smith@msic.com');

-- 2. CUSTOMER (linked to Employee)
INSERT INTO CUSTOMER (CUSTOMER_ID, LASTNAME, FIRSTNAME, EMAIL, SUPPORT_REP_ID)
VALUES (201, 'Doe', 'Jane', 'jane.doe@client.com', 101);

-- 3. ARTIST (shortened to <= 10 chars)
INSERT INTO ARTIST (ARTIST_ID, NAME)
VALUES (301, 'Beatles');

-- 4. ALBUM (new ID + linked to Artist)
INSERT INTO ALBUM (ALBUM_ID, TITLE, ARTIST_ID)
VALUES (401, 'Abbey Rd', 301);

-- 5. MEDIA_TYPE (new ID)
INSERT INTO MEDIA_TYPE (MEDIA_TYPE_ID, NAME)
VALUES (11, 'MP3');

-- 6. GENRE (new ID, <= 12 chars)
INSERT INTO GENRE (GENRE_ID, NAME)
VALUES (12, 'Rock');

-- 7. TRACK (shortened name <= 10 chars)
INSERT INTO TRACK (TRACK_ID, NAME, ALBUM_ID, MEDIA_TYPE_ID, GENRE_ID, DURATION_IN_SECS, UNIT_PRICE)
VALUES (21, 'ComeToget', 401, 11, 12, 259, 1);

-- 8. INVOICE (linked to Customer)
INSERT INTO INVOICE (INVOICE_ID, CUSTOMER_ID, INVOICE_DATE, BILLING_ADDRESS, BILLING_CITY, BILLING_COUNTRY, TOTAL)
VALUES (801, 201, SYSDATE, '123 Main St', 'NYC', 'USA', 10.99);

-- 9. INVOICE_LINE (linked to Invoice + Track)
INSERT INTO INVOICE_LINE (INVOICE_LINE_ID, INVOICE_ID, TRACK_ID, UNIT_PRICE, QUANTITY)
VALUES (901, 801, 701, 1, 2);

# MASTER JOIN IN END 

SELECT 
    C.CUSTOMER_ID,
    C.FIRSTNAME        AS CUSTOMER_FIRSTNAME,
    C.LASTNAME         AS CUSTOMER_LASTNAME,
    C.EMAIL            AS CUSTOMER_EMAIL,
    E.EMPLOYEE_ID,
    E.FIRSTNAME        AS EMP_FIRSTNAME,
    E.LASTNAME         AS EMP_LASTNAME,
    E.TITLE            AS EMP_TITLE,
    I.INVOICE_ID,
    I.INVOICE_DATE,
    I.BILLING_ADDRESS,
    I.BILLING_CITY,
    I.BILLING_STATE,
    I.BILLING_COUNTRY,
    I.TOTAL            AS INVOICE_TOTAL,
    IL.INVOICE_LINE_ID,
    IL.QUANTITY,
    IL.UNIT_PRICE      AS LINE_PRICE,
    T.TRACK_ID,
    T.NAME             AS TRACK_NAME,
    T.DURATION_IN_SECS,
    T.UNIT_PRICE       AS TRACK_PRICE,
    MT.MEDIA_TYPE_ID,
    MT.NAME            AS MEDIA_TYPE,
    G.GENRE_ID,
    G.NAME             AS GENRE_NAME,
    A.ALBUM_ID,
    A.TITLE            AS ALBUM_TITLE,
    AR.ARTIST_ID,
    AR.NAME            AS ARTIST_NAME
FROM CUSTOMER C
JOIN INVOICE I 
    ON C.CUSTOMER_ID = I.CUSTOMER_ID
JOIN INVOICE_LINE IL 
    ON I.INVOICE_ID = IL.INVOICE_ID
JOIN TRACK T 
    ON IL.TRACK_ID = T.TRACK_ID
JOIN ALBUM A 
    ON T.ALBUM_ID = A.ALBUM_ID
JOIN ARTIST AR 
    ON A.ARTIST_ID = AR.ARTIST_ID
JOIN MEDIA_TYPE MT 
    ON T.MEDIA_TYPE_ID = MT.MEDIA_TYPE_ID
JOIN GENRE G 
    ON T.GENRE_ID = G.GENRE_ID
LEFT JOIN EMPLOYEE E 
    ON C.SUPPORT_REP_ID = E.EMPLOYEE_ID
ORDER BY C.CUSTOMER_ID, I.INVOICE_ID, IL.INVOICE_LINE_ID;

# Basic Level (to get comfortable with tables)

 ## List all customers with their assigned support rep’s first and last name.

## Show all invoices with customer first name, last name, and invoice total.

## Display all tracks with their album title and artist name.

## Retrieve all tracks along with their genre and media type.

## Show all employees and the number of customers they support.

# Intermediate Level (joins & aggregations)

## Find the top 5 invoices with the highest total amount.

## List customers who have purchased tracks from the genre "Rock".

## Show each customer and the total number of invoices they have.

## Find the average invoice total per country.

## For each album, list the number of tracks and total duration (in seconds).

## Show employees along with the total sales generated by the customers they manage.

## Retrieve all invoices that include tracks by "The Beatles".

# Advanced Level (nested queries, grouping, analytics)

## Find the most popular track (highest total quantity sold).

## Show the customer who has spent the most money overall.

## Find the top 3 genres by total sales.

## Retrieve albums where every track has been purchased at least once.

## List employees who manage customers that bought tracks from more than 5 different genres.

## Show customers who have purchased tracks from multiple media types.

## For each artist, show the total revenue generated from their tracks.

## Use a window function (if Oracle version supports it):

## Rank customers by their total spending within each country.
