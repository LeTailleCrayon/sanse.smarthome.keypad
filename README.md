# Le Taille Crayon Projects - sanse.smarthome.keypad
Utilisez un clavier numérique pour contrôler votre installation connectée ! (Fonctionne avec HomeAssistant, Domoticz et autres...) / Use a keypad to control your smart home functionnalities ! (Works with Sanse.SmartHome, Home-Assistant, Domoticz and others)

Multi-languages documentations available !
- English (en)
- Français (fr)

# Prerequis (en) / Prérequis (fr)

- 1 numeric keypad (en) / 1 Clavier Numérique (fr)
- 1 buzzer (en) / 1 buzzer (pour le son) (fr)
- 1 led (en) / 1 DEL (fr)
- 1 RPi Zero WH at least (en) / 1 RPi Zero WH au minimum (fr)
- 1 Smart Home Hub (eg. Home Assistant or Domoticz) / 1 Concentrateur Domotique (ex: Home Assistant ou Domoticz)

# Compatibilities (en) / Compatibilité (fr)

- Hardware (en) / Matériel (fr) :
 For the moment, our project is only available with the Raspberry Pi computers. The RPi needs to have a wifi connection and some GPIO Ports. If you want, you can try to make it run on some other devices that can run Python scripts! (en) / Pour le moment, notre projet ne fonctionne qu'avec les machines Raspberry Pi. Le micro-ordinateur doit disposer d'une connexion Wifi et de plusieurs ports GPIO. Si vous el souhaitez, vous pouvez essayer de l'adapter pour le faire fonctionner sur tout appareil pouvant éxecuter des scripts Python !   (fr)

This table is updated monthly and list all of the devices that can run sanse.smarthome.keypad (en) / Ce tableau est actualisé tous les mois et liste les appareils pouvant supporter sanse.smarthome.keypad (fr)

 | Matériel  | Compatibilité |
 | ------------- | ------------- |
 | Raspberry Pi Zero WH  | OK  |
 | Raspberry Pi Zero W  | Ok. With GPIOs  |
 | Raspberry Pi 3+/4+ | OK |

For the keyboard, we advise you to use a keyboard that have one more column with the "ABCD#" buttons. (en) / Pour le clavier nous vous recommandons d'utiliser un clavier avec une rangée suppplémentaire contenant les touches "ABCD#" (fr)

![keypad](https://protosupplies.com/wp-content/uploads/2017/11/Membrane-Keypad-4-x-4.jpg)

- Software (en) / Logiciels (fr)
 Now, our projects can ineract with Home-Assistant and Domoticz but you can make it run with any webhook-based system (en) / Actuellement, notre projet intéragit nativement avec Home-Assistant et Domoticz, mais vous pouvez le faire fonctionner en Webhook avec n'importe quel système.

 | Software  | Compatibilité |
 | ------------- | ------------- |
 | Sanse.SmartHome| OK |
 | Home Assistant  | OK  |
 | Domoticz  | Ok |
 | IFTTT Webhooks | OK (Better with IFTTT Pro) |
 
 # Installation
 
 First, install the keyboard, the led and the buzzer (en) / Premièrement, intsallons le clavier, la DEL et le buzzer :
 
 Here is the connections diagram (en) / Voici le schéma de connexion :
 
  | Matériel | GPIO (BCM) |
 | ------------- | ------------- |
 | LED/DEL  | 16  |
 | Buzzer  | 4 |
 | Keypad/Clavier | Lignes/Rows [17,27,22,5] |
 | Keypad/Clavier | Colonnes/Columns [6,13,19,26] |
 
 Find the rows and the columns with this diagram made by AzDelivery (en) / Trouvez les cables correspondants aux lignes et colonnes avec ce schéma de AZDelivery (fr) :
 
 ![Diagram](https://images-na.ssl-images-amazon.com/images/I/61ih6z9E3NL._SL1500_.jpg)
 
 | Output | GPIO (BCM) |
 | ------------- | ------------- |
 | C1  | 6  |
 | C2  | 13 |
 | C3 | 19 |
 | C4 | 26 |
 | R1 | 17 |
 | R2 | 27 |
 | R3 | 22 |
 | R4 | 5 |
 
 - Download and install the newest version of Raspberry Pi OS Lite (https://downloads.raspberrypi.org/raspios_lite_armhf/images/raspios_lite_armhf-2021-05-28/2021-05-07-raspios-buster-armhf-lite.zip) / Téléchargez la dernière versions de Raspberry Pi OS Lite (fr)
 - On start, update all the packages and make sure to enable SSH/SFTP / Au démarrage, mettez à jour le système et activez SSH/SFTP (fr)
 - Download the "sanse-smarthome-keypad-package.zip" file, extract it and move the folder on your RPi main path (via FileZilla) (en) / Téléchargez la dernière version du fichier "sanse-smarthome-keypad-package.zip", décompressez le et déplacez-le vers le répertoire principal /root de votre RPi (via Filezille) (fr)


# Configuration - First Setup (en) / Premier démarrage (fr)
Run the file called "setup-configuration-en.py" with your RPi Shell in SSH, by typing this (en) / Executez le fichier "demarrage-configuration-fr.py" dans le terminal du RPi en saisissant :

 `cd keypad-smart-home-package` 
 
 According to your language / Selon votre langue : 
`sudo python3 sanse-kp-configuration-en.py ` (en)

`sudo python3 sanse-kp-configuration-fr.py` (fr)

And follow the differents steps (en) / Et suivez les étapes (fr)

> Manual Configuration Mode (en only) : You can configure keypad-smart-home using a json file, for that, download the last version of the file called "manual-configuration.json", and complete it with your differents informations. Move it into the folder called "manual configuration > json" and run in Python the file called "json-configuration.py", it will detects your file and apply all modifications automatically.

# Connect it to your smart-home integrations ! (en) / Connectez le à vos intégrations de Maison Intelligente ! (fr)
You can connect it to a lot of smart home platforms, the principals are : Sanse.SmartHome (Sanse.SH DIY Bridge required), HomeAssistant, Domoticz, IFTT Webhooks.

<details>
  <summary>Sanse.SmartHome (Bêta 0.1) :</summary>
  ## What is that ? / C'est quoi ?

  Sanse.SH is a smart home platform project that is 100% running in Python, so it can run on a lot of devices without using big performances. (en) / Sanse.SH est un projet de de   plateforme domotique qui fonctionne à 100% en Python, il peut être utilisé sur une majorité d'appareils sans utiliser beaucoup de performances. (fr)
  
  ## Prerequis
  
  1. A Sanse.SmartHome DIY Bridge (en) / Un concentrateur domotique DIY Sanse.SmartHome (fr)
  2. An operational Sanse.SH system (en) / Un système opérationnel Sanse.SH (fr)
  > !!UPCOMING!! - For the moment, Sanse.SH is on beta deployement and only some users can have access to it. We are working to improve the project and deploy it to all the         users that are interested by this project. (en) / Pour le moment, Sanse.SH est en phase de développement bêta et est en accès limité. Nous travaillons à développer ce projet     et à le rendre disponible à tous ceux interressés par ce projet ! (fr)
</details>
