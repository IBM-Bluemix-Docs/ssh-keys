---
copyright:
  years: 1994, 2017
lastupdated: "2017-12-12"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Verbindung zu einem RedHat-Server mit SSH herstellen

Für dieses Verfahren benötigen Sie einen SSH-Client, z. B. PuTTY, auf Ihrem Heimcomputer. PuTTY ist ein weit verbreiteter, kostenloser SSH-Client.
In den meisten Fällen können Sie die Standardoptionen in PuTTY verwenden, um die erstmalige Verbindung zu Ihrem RedHat-Server erfolgreich herzustellen.

1. Öffnen Sie PuTTY, geben Sie die Haupt-IP-Adresse Ihres Servers in das Feld `'Hostname (oder IP-Adresse)'` ein und klicken Sie auf "Öffnen".
  Anmerkung: Der Standardport für SSH ist 22, Sie können ihn aber auf dem Server ändern, nachdem Sie Ihre erste Verbindung erfolgreich hergestellt haben.
2. Der RedHat-Server fordert Sie zur Eingabe eines Benutzernamens und Kennworts auf. Geben Sie Ihre Rootbenutzer-/Übergabeinformationen für den Server ein.
3. Speichern Sie die Verbindungsdetails (IP-Adresse und Port) in den Sitzungen, indem Sie die IP-Adresse und den Port eingeben. Erstellen Sie einen Titel für diese Verbindungseigenschaften, z. B. "Mein Server", und klicken Sie auf "Speichern".
  Wenn Sie eine Verbindung zu Ihrem Server herstellen, müssen Sie nur die gespeicherte Sitzung markieren und auf "Öffnen" klicken.

Sie können eine Verbindung zu Ihrem Server über das öffentliche Netz herstellen.
Sie können aber auch das private Netz für die Verbindung nutzen. Befolgen Sie dazu die Anweisungen im {{site.data.keyword.slportal_full}} zur Herstellung von Verbindungen zum VPN und verwenden Sie anschließend SSH, um eine Verbindung zu Ihrer privaten IP-Adresse herzustellen.