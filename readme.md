# DB structure
Modellare la struttura di un database per memorizzare tutti i dati riguardanti una università:
- sono presenti diversi Dipartimenti (es.: Lettere e Filosofia, Matematica, Ingegneria ecc.);
- ogni Dipartimento offre più Corsi di Laurea (es.: Civiltà e Letterature Classiche, Informatica, Ingegneria Elettronica ecc..)
- ogni Corso di Laurea prevede diversi Corsi (es.: Letteratura Latina, Sistemi Operativi 1, Analisi Matematica 2 ecc.);
- ogni Corso può essere tenuto da diversi Insegnanti;
- ogni Corso prevede più appelli d'Esame;
- ogni Studente è iscritto ad un solo Corso di Laurea;
- ogni Studente può iscriversi a più appelli di Esame;
- per ogni appello d'Esame a cui lo Studente ha partecipato, è necessario memorizzare il voto ottenuto, anche se non sufficiente. Pensiamo a quali entità (tabelle) creare per il nostro database e cerchiamo poi di stabilirne le relazioni. Infine, andiamo a definire le colonne e i tipi di dato di ogni tabella.

## Table name
- dipartimenti
- corsi_di_laurea
- corsi
- insegnanti
- insegnamenti (tabella ponte)
- esami
- studenti
- iscrizioni_esami

## Dipartimenti
- id | BIGINT - PK - AI
- nome | VARCHAR(255) - NOT NULL

## Corsi di laurea
- id | BIGINT - PK - AI
- nome | VARCHAR(255) - NOT NULL
- dipartimento_id | FK - BIGINT 

## Corsi 
- id | BIGINT - PK - AI
- nome | VARCHAR(255) - NOT NULL
- corso_di_laurea_id | FK - BIGINT 

## Insegnanti
- id | BIGINT - PK - AI
- nome | VARCHAR(30) - NOT NULL
- cognome | VARCHAR(30) - NOT NULL

## Insegnamenti
- id | BIGINT - PK - AI
- insegnante_id | FK - BIGINT 
- corso_id | BIGINT - BIGINT 

## esami 
- id | BIGINT - PK - AI
- date | DATE - NOT NULL
- corso_id | FK - BIGINT 

## Studenti 
- id | BIGINT - PK - AI
- nome | VARCHAR(30) - NOT NULL
- cognome | VARCHAR(30) - NOT NULL
- matricola | VARCHAR(15) - UNIQUE
- corso_di_laurea_id | FK - BIGINT 

## Iscrizioni esami
- id | BIGINT - PK - AI
- studente_id | FK - BIGINT
- esame_id | FK - BIGINT
- superato | TINYINT - DEFAULT(0)
- voto | INT - NULL
- data_esame | DATE - NOT NULL