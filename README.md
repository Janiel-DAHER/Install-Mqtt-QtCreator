# Install-Mqtt-QtCreator
This repo explain how to install the module Mqtt in Qt Creator 


//Pré-requis 

- Installer QT Creator sur votre machine Windows 
- Laisser le répertoire d'installation réglé par QT 
- Vérifier l'installation de Qt en créant un projet et le tester 
- Vérifier la version de Qt Creator Qt Creator 5.0.2 dans "Aide" "About Qt Creator" pour ma part j'ai : 
	
	Basé sur Qt 5.15.2 (MSVC 2019, 64 bit)
	Built on Sep 30 2021 01:26:25
	From revision 67c0104b8e

//Insatllation du Module 


+ 1 Copier et coller sur votre bureau le module Mqtt contenu au chemin Janiel-DAHER/Install-Mqtt-QtCreator/Module_Mqtt_QtCreator
+ 2 Lorsque vous avez copié le projet du module dans un dossier sur votre bureau, Ouvrir explorateur de fichier 
+ 3 (Fermer toutes vos applications en cours) et aller dans le répertoire d'installation qt (Normalement si laissé par défaut -> C:\Qt\)


+ 4 Créer un nouveau dossier dans C:\Qt\6.2.0\mingw81_64\lib nommé qtmqtt -> Vous devez ensuite avoir ce type de chemin C:\Qt\6.2.0\mingw81_64\lib\qtmqtt
+ 5 Créer un autre dossier dans C:\Qt\6.2.0\mingw81_64\lib nommé qtmqtt_Build -> Vous devez ensuite avoir ce type de chemin C:\Qt\6.2.0\mingw81_64\lib\qtmqtt_Build 
+ 6 Créer un nouveau répertoire dans C:\Qt\6.2.0\mingw81_64\include nommé QtMqtt ->  Vous devez ensuite avoir ce type de chemin C:\Qt\6.2.0\mingw81_64\include\QtMqtt


+ 7 Copier le projet module Mqtt de votre dossier bureau dans C:\Qt\6.2.0\mingw81_64\lib\qtmqtt 
+ 8 Copier uniquement les headers (.h) du répertoire C:\Qt\6.2.0\mingw81_64\lib\qtmqtt\src\mqtt dans le répertoire C:\Qt\6.2.0\mingw81_64\include\QtMqtt


+ 9 Revenir dans le répertoire C:\Qt\6.2.0\mingw81_64\lib\qtmqtt (Celui ou vous avez copié le projet au point n°7)
+ 10 Ouvrir le projet avec Qt creator (Ouvrir le .pro) 

+ 10 Une fois le projet ouvert, selectionner Projet -> Paramètres de Compilation -> Profile debug 
+ 11 Verifier que la case shadow build soit bien active
+ 12 Changer le répertoire de build (Compilation) -> Vous devez régler le répertoire de build sur -> C:\Qt\6.2.0\mingw81_64\lib\qtmqtt_Build (Créé au point n°5)


+ 13 Avant de compiler le projet, il faut régler le compilateur pour ajouter une étape make "-install" pour installer le module QT 
+ 14 Pour ajouter l'étape install, sélectionner  Projet -> Paramètres de Compilation -> Ajouter une étape de Build -> Ajouter une étape Make -> Ajouter dans le champ "-install"
+ 14 Vérifier tout avant de compiler 

+ 15 Lancer la compilation en mode "debug" normalement elle dure 2-3 minutes
+ 16 Une fois finie sans erreur :) , fermer le projet -> Le module Mqtt est installé 

+ 17 Pour inclure le module Mqtt dans vos projet -> Selectionner le .pro -> Ajouter la ligne -> QT += mqtt 
+ 18 Ajouter dans votre projet <QtMqtt\qtmqttclient.h>  

+ 19 Ne pas oublier d'ajouter la dll Mqtt au projet dans lequel vous utilisez le module QT += mqtt !!
+ 20 La dll se trouve au chemin dll du repo git