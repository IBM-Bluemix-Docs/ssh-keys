---



copyright:

  years: 2016
lastupdated: "2016-01-19"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}

# Bare-Metal-Server verwalten
{: #managing}


Sie können Server stoppen, starten, neu starten und abbrechen.
{:shortdesc}

## Eine Serverinstanz replizieren
Sie können eine Bare-Metal-Server-Instanz kopieren oder klonen, um die Serverkonfiguration zu replizieren und einen neuen Server schnell betriebsbereit zu machen.
{:shortdesc}

Vorgehensweise zum Klonen der Instanz:
 1. Gehen Sie zum Menü und wählen Sie **Configure Replica** aus. Alle Konfigurationen werden kopiert. Daten oder Inhalte werden nicht kopiert.
 2. Geben Sie einen eindeutigen Servernamen ein.
 3. Geben Sie den Domänennamen an.

## Das Betriebssystem neu laden
Sie haben die Möglichkeit, von Zeit zu Zeit das Betriebssystem auf Ihrem Server neu zu laden.
{:shortdesc}

Vorgehensweise zum erneuten Laden des Betriebssystems:
 1. Sichern Sie vor dem Start alle Daten. Wenn dieser Schritt übersprungen wird, können alle Daten verloren und nicht mehr abgerufen werden.
 2. Gehen Sie zum Menü und wählen Sie **Erneutes Laden des Betriebssystems** aus. Sie können auswählen:
  * Ändern Sie das Betriebssystem zu einem anderen Betriebssystem und nehmen Sie neue Konfigurationen vor. 
  * Behalten Sie das vorhandene Betriebssystem mit den aktuellen Konfigurationen bei, löschen Sie jedoch den Server, um von vorn zu beginnen. 

Während das Betriebssystem neu geladen wird, ist der Server offline und für die Verwendung nicht verfügbar. Die Dauer des erneuten Ladens variiert je nach Betriebssystem und Kapazität des Servers. Wenn Sie ein Bereitstellungsskript definiert haben, werden alle Konfigurationen nach dem Neuladen wiederhergestellt. Wenn Ihre Daten vor dem Neuladen des Betriebssystems gesichert wurden, können Sie sie auf den Server hochladen, wenn dieser verfügbar ist.

## Die Serverinstanz löschen
Sie können die Bare-Metal-Server-Server-Instanz jederzeit löschen, wenn Sie die Instanz nicht mehr benötigen und keine Kosten generieren möchten.
{:shortdesc}

Um die Instanz zu löschen, gehen Sie zum Menü und wählen Sie **Server abbrechen** aus.

## Einen Server ausschalten
Sie können einen Server im Voraus erstellen, um ihn für die Verwendung vorzubereiten, und dann ausschalten, um sicherzustellen, dass nichts geändert wird und niemand darauf zugreifen kann. Wenn Sie bereit sind, können Sie den Server einschalten, der in wenigen Minuten betriebsbereit ist.
{:shortdesc}

Um den Server auszuschalten, gehen Sie zum Menü und wählen Sie **Ein-/Ausschalten** aus. Während der Server ausgeschaltet ist, erhalten Sie jedoch weiterhin eine Rechnung.

**Hinweis:** Wenn der Server ausgeschaltet ist, bleibt er im ausgeschalteten Zustand und muss manuell wieder eingeschaltet werden.
