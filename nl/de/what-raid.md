---
copyright:
  years: 1994, 2017
lastupdated: "2017-12-13"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Informationen zu RAID

RAID (Redundant Array of Independent Disks) erstellt eine einzelne verwendbare Datenplatte, auf der mehrere physische Festplatten für eine höhere Geschwindigkeit und Fehlertoleranz zu einem Array kombiniert werden. In RAID gibt es drei zentrale Konzepte:
* Mirroring: Kopieren von Daten zu mehr als einer Platte
* Striping: Daten über auf mehreren Platten verteilen
* Fehlerkorrektur (Fehlertoleranz): Redundante Daten werden gespeichert, um Probleme zu erkennen und zu beheben 

Obwohl es viele verschiedene RAID-Stufen gibt, unterstützt IBM diese häufigen Raid-Typen: 0, 1, 5 und 10. Die verschiedenen RAID-Stufen nutzen eine oder mehrere Verfahren, je nach Systemanforderungen. Der Hauptzweck der Verwendung von RAID besteht darin, die Zuverlässigkeit zu verbessern, indem entweder 3Ware 9550SX Raid SATA- oder Adaptec SA-SCSI RAID-Controller für alle bereitgestellten RAID-Lösungen verwendet werden.

RAID ist keine Backuplösung. RAID erstellt eine einzelne verwendbare Datenplatte, auf der mehrere physische Festplatten für eine höhere Geschwindigkeit und/oder Fehlertoleranz zu einem Array kombiniert werden. 


**RAID 0** (Stripe-Set ohne Parität/nicht redundantes Array) Implementiert ein Datenstriping, bei dem Dateiblöcke auf mehrere Laufwerke in Fragmenten geschrieben und mindestens zwei Laufwerke benötigt werden. Der Vorteil von RAID 0 ist die erheblich geringere Lese-/Schreibgeschwindigkeit. Je mehr Laufwerke im Array vorhanden sind, desto höher die Bandbreite. Der Nachteil von RAID 0 ist die fehlende Fehlertoleranz. Wenn nur ein Laufwerk ausfällt, ist das ganze Array nicht mehr wiederherstellbar. RAID 0 implementiert auch keine Fehlerprüfung. Das heißt, Fehler sind nicht behebbar. Eine allgemein übliche Lösung für die Fehlertoleranz ist ein Laufwerk außerhalb des Arrays, das im Fall eines Hardwarefehlers als Sicherungsspeicher verwendet wird.

**RAID 1** (Spiegelung ohne Parität) Implementiert eine Datenspiegelung. Die Daten werden auf 2 oder 4 Laufwerken über einen RAID-Hardware-Controller dupliziert und bieten eine gewisse Fehlertoleranz. Das Array kann wiederhergestellt werden, wenn mindestens ein Laufwerk noch funktionstüchtig ist. Es bietet eine schnellere Leseleistung als ein einzelnes Laufwerk und bietet Laufwerksredundanz, wenn ein Laufwerk ausfällt. Die Schreibgeschwindigkeit wird minimal reduziert.

**RAID 5** (Stripe-Set mit dualer verteilter Parität) Implementiert Datenstriping auf Blockebene und verteilt die Parität zwischen den Laufwerken. Die Paritätsinformationen ermöglichen die Wiederherstellung, wenn ein einzelnes Laufwerk ausfällt, da alle folgenden Lesevorgänge anhand der verteilten Parität berechnet werden können. RAID 5 ermöglicht auch eine höhere Lese-/Schreibgeschwindigkeit und die effiziente Nutzung des Plattenspeichers. RAID 5 benötigt mindestens drei Platten.

**RAID 10** (RAID 1 + 0) Erstellt mehrere Spiegelserver, in denen Daten als Stripes (Streifen) über mehrere Platten hinweg organisiert und die Stripe-Set-Datenträgergruppen gespiegelt werden. RAID 10 bietet die gleiche Fehlertoleranz wie RAID 1 mit höherer Lese-/Schreibgeschwindigkeit über einen einzelnen RAID 1-Datenträger oder -Laufwerk hinweg. Für die RAID-Stufe 10 müssen mindestens vier Laufwerke implementiert werden.

