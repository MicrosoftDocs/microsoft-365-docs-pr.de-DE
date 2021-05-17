---
title: Informationen zu Windows-Sicherheitsupdates
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: b3b1f43217b3be285f20925065bf9710a38f9606
ms.sourcegitcommit: 36795a6735cd3fc678c7d5db71ddc97fac3f6f8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/06/2020
ms.locfileid: "48941441"
---
# <a name="windows-security-update-insights"></a>Informationen zu Windows-Sicherheitsupdates
Diese Ansicht bietet eine Übersicht über den Status von Sicherheitsupdates für Ihre Microsoft Managed Desktop Geräte. 

Wählen Sie zum Anzeigen von Verwendungsdaten die <strong>Registerkarte Windows Sicherheitsupdates</strong> aus.

![Windows Bereich Sicherheitsupdates: Balkendiagramme des Gerätestatus und der Updateversion in der linken Spalte, Aktualisierung des Bereitstellungsfortschritts im Laufe der Zeit in der Mitte und Prozentsatz der aktiven Geräte nach Bereitstellungsgruppe sowie die Anzahl der Tage, die zum Erreichen des Bereitstellungsziels von 95 % in der rechten Spalte verwendet wurden.](../../media/update-insights.jpg)

## <a name="device-status"></a>Gerätestatus

Damit Geräte mit Windows Update aktualisiert werden können, müssen sie mit dem Internet verbunden sein und nicht mindestens sechs Stunden lang im Ruhezustand sein, von denen zwei kontinuierlich sein müssen. Obwohl es möglich ist, dass ein Gerät aktualisiert wird, das diese Anforderungen nicht erfüllt, haben Geräte, die diese Anforderungen erfüllen, die höchste Wahrscheinlichkeit, aktualisiert zu werden. 

Wir kategorisieren Geräteaktivitäten im Kontext Windows Update mit den folgenden Begriffen:

- <strong>Aktiv:</strong> Geräte, die die Mindestaktivitätskriterien (sechs Stunden, zwei fortlaufende) für die neueste Sicherheitsupdateversion erfüllt haben und mindestens alle fünf Tage mit Microsoft Intune eingecheckt haben
- <strong>Synchronisiert:</strong> Geräte, die in den letzten 28 Tagen mit Intune eingecheckt haben
- <strong>Nicht synchronisiert:</strong> Geräte, die <i>in den</i> letzten 28 Tagen nicht mit Intune eingecheckt haben




## <a name="update-version-status"></a>Versionsstatus aktualisieren

Microsoft veröffentlicht Sicherheitsupdates jeden zweiten Dienstag im Monat. Jede Version fügt wichtige Updates für bekannte Sicherheitsrisiken hinzu. Microsoft Managed Desktop stellt sicher, dass 95 % der verwalteten Geräte jeden Monat mit dem neuesten verfügbaren Sicherheitsupdate aktualisiert werden. Sicherheitsupdates werden manchmal zu anderen Zeiten veröffentlicht, um neue Bedrohungen dringend zu bekämpfen. Microsoft Managed Desktop stellt diese Updates auf ähnliche Weise zur Verfügung.

Wir kategorisieren den Status von Sicherheitsupdateversionen mit den folgenden Bedingungen:

- <strong>Aktuell:</strong> Geräte, auf den das update ausgeführt wird, das im aktuellen Monat veröffentlicht wurde
- <strong>Vorheriger:</strong> Geräte mit dem Update, das im Vorherigen Monat veröffentlicht wurde
- <strong>Älter:</strong> Geräte mit sicherheitsupdates, die vor dem vorherigen Monat veröffentlicht wurden

In der Kategorie "Älter" sollten nur wenige Geräte angezeigt werden. Eine große oder wachsende Population weist wahrscheinlich auf ein systemisches Problem hin, das Sie melden sollten, Microsoft Managed Desktop wir untersuchen können. <strong></strong>


## <a name="deployment-progress"></a>Bereitstellungsfortschritt

Zu Beginn jedes Veröffentlichungszyklus für Sicherheitsupdates erstellt Microsoft Managed Desktop eine Momentaufnahme der Gerätegesamtheit und legt das Bereitstellungsziel auf 95 % dieser Population fest. Der <strong>Bereich Bereitstellungsfortschritt</strong> zeigt einen verlaufshistorischen Trend, der täglich aktualisiert wird und verfolgt, wie genau die Updatebereitstellung dieses Ziel für jede Version erfüllt. In diesem Diagramm werden nur Geräte mit dem Status "Aktiv" angezeigt.

Sie können diese Daten für vorherige Aktualisierungszyklen anzeigen, indem Sie das Dropdownmenü oben rechts verwenden. Der in diesem Menü ausgewählte Zeitraum gilt für alle Informationen auf der gesamten Seite.

Der <strong>Bereich Aktualisierte aktive Geräte</strong> nach Bereitstellungsgruppen bietet eine andere Ansicht, indem der Fortschritt der Updateinstallation für jede der Microsoft Managed Desktop angezeigt wird.

Der <strong>Bereich Tage bis</strong> zum Erreichen des Zielbereichs zeigt an, wie lange 95 % der Gesamtzahl der Geräte mit dem aktuellen Sicherheitsupdate aktualisiert wurden. Während der Bereitstellung wird in diesem Bereich <strong>weiterhin</strong> aktualisiert, bis das Ziel von 95 % für das ausgewählte Update erreicht ist.

## <a name="device-details-area"></a>Bereich "Gerätedetails"

Im unteren Bereich des Dashboards finden Sie eine Tabelle mit detaillierten Informationen für Ihre Geräte, einschließlich des [Gerätestatus](#device-status) und [des Updateversionsstatus.](#update-version-status) Sie können diese Liste durchsuchen oder nach einem beliebigen aufgelisteten Wert filtern.


![Gerätedetailsetabelle mit Spalten für gerätenamen, zugewiesenen Benutzer, Gerätestatus, Updateversion, Betriebssystemversion und das Datum, an dem das Gerät zuletzt synchronisiert wurde.](../../media/security-update-insights-device-table-sterile.png)
