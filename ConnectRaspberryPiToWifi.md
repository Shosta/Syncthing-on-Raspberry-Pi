Tout d’abord, nous allons éditer le fichier _wpa_supplicant.conf_

`sudo nano /etc/wpa_supplicant/wpa_supplicant.conf`

Rendez-vous à la fin du fichier et ajoutez la définition de votre box en suivant ce template :
>network={
    ssid="Your box name"
    psk="The security key of your box"
    key_mgmt=WPA-PSK
}

Remplacez `"Your box name"` par le SSID de votre box internet et `"The security key of your box"` par le mot de passe de votre box.
>Si votre box utilise une clé de type WEP plutôt que du WPA/WPA2, insérez la valeur `NONE` dans `key_mgmt`, pour obtenir quelque chose de la forme `key_mgmt=NONE`.

Votre Raspberry Pi 3 est maintenant configuré pour se connecter à internet via sa puce Wi-Fi.
 Il ne vous reste plus qu’à démarrer le Wi-Fi de la Raspberry Pi avec cette commande :
`ifconfig wlan0`

######Change the Raspberry Pi hostname :
Type the following command in a Terminal:
`sudo raspi-config`
to change the Raspberry Pi hostname on your network.

So you can access it on your network even if it has a dynamic IP address.

