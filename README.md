# PrintForFishing — mises à jour du peson connecté

Ce dépôt **public** ne distribue **que les binaires** de mise à jour du peson ESP32-C3 PrintForFishing. Le code source du firmware reste dans le dépôt privé `davidkls/Peson_firmware`.

## Firmware v1.0.10 : association Bluetooth securisee

**Installer d'abord l'application GRAVIS Android 1.0.27 ou superieure avant de mettre le peson a jour vers v1.0.10.** La version du firmware active les associations securisees et les anciennes versions Android n'ont pas la procedure d'association correspondante. Au premier appairage ou pour ajouter un telephone, maintenir TARE + SAVE pendant 3 secondes, puis saisir le code affiche sur l'ecran via le dialogue Android. Pour effacer les associations Bluetooth en cas de revente, maintenir TARE + SAVE pendant 8 secondes.

Le retour vers v1.0.9 est possible par mise a jour manuelle si la liaison BLE fonctionne, ou par USB si elle ne fonctionne plus. Le controle physique du peson n'a pas ete valide au moment de la publication du binaire.

Les mises à jour sont publiées dans [**Releases**](https://github.com/davidkls/Peson_firmware_public/releases/latest). L'application PrintForFishing vérifie cette page au démarrage et propose l'installation lorsqu'une version plus récente du firmware est disponible.

Chaque version stable contient :
- `PrintForFishing_ESP32C3_ota.bin` : programme ESP32-C3 à installer par Bluetooth ;
- `PrintForFishing_ESP32C3_ota.sha256` : empreinte SHA-256 du programme pour vérifier son intégrité.

> **Important :** la première version compatible avec les mises à jour (V22) doit être installée **une fois par USB**. Les versions suivantes (V23 et suivantes) peuvent ensuite être installées via l'application. Ne pas éteindre le peson pendant le transfert et utiliser une pile suffisamment chargée.

Une archive ZIP placée dans `releases/vXX/` sert de paquet de publication. Le workflow GitHub vérifie le contenu, le modèle ESP32-C3 et le SHA-256, puis crée une Release avec les deux fichiers.
