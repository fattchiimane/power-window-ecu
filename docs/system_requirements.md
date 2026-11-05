Exigences système - Power Window ECU



Plateforme : STM32 Nucleo-L476RG (ECU 1), CAN 500 kbit/s via SN65HVD230.

Les valeurs (seuils, délais) sont des hypothèses de projet.



&#x20;ID  Exigence  Origine  Test 



&#x20;REQ-01 : Le système doit monter la vitre tant que le bouton « monter » est maintenu. CUST-01 : Test manuel 

&#x20;REQ-02 : Le système doit descendre la vitre tant que le bouton « descendre » est maintenu.  CUST-01 : Test manuel 

&#x20;REQ-03 : Le système doit arrêter le moteur à une fin de course (haute ou basse).  CUST-01 : Simulation 

&#x20;REQ-04 : Le système doit lancer une montée/descente automatique sur appui bref (< 300 ms).  CUST-01 : Test manuel 

&#x20;REQ-05 : Le système doit détecter un pincement quand le courant moteur dépasse le seuil configuré (ex. 8 A). CUST-02 : Injection de faute 

&#x20;REQ-06 : Le système doit arrêter puis inverser le mouvement en moins de 100 ms après détection d'un pincement. CUST-02 :Mesure du temps 

&#x20;REQ-07 :Le système doit passer en état sûr (moteur coupé) si WIN\_CMD est absent pendant plus de 200 ms.  CUST-04  Message CAN manquant 

&#x20;REQ-08 :Le conducteur doit pouvoir commander la vitre passager par le message CAN WIN\_CMD (ID 0x100), et l'ECU doit envoyer WIN\_STATUS (ID 0x200) toutes les 50 ms ± 5 ms.  CUST-03 : Analyse des logs 

&#x20;REQ-09 :Chaque message doit contenir un rolling counter et un CRC ; l'ECU doit rejeter tout message invalide. CUST-04 :Injection de faute 

&#x20;REQ-10 :L'ECU doit répondre au service UDS 0x22 pour lire la version logicielle et la position de la vitre.  CUST-05 :udsoncan 

&#x20;REQ-11 : L'ECU doit enregistrer le DTC 0xC10001 en cas de surintensité et le rendre lisible via 0x19. CUST-05  udsoncan 

&#x20;REQ-12 :L'ECU doit effacer les DTC via le service 0x14.  CUST-05  udsoncan 

&#x20;REQ-13 : Le code C doit respecter MISRA C, avec analyse cppcheck et écarts documentés.  CUST-06 : cppcheck 

