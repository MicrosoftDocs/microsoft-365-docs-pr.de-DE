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
ms.sourcegitcommit: cebbdd393dcfd93ff43a1ab66ad70115853f83e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/03/2021
ms.locfileid: "52739797"
---
# <a name="windows-security-update-insights"></a>Informationen zu Windows-Sicherheitsupdates
Diese Ansicht bietet eine Übersicht über den Status von Sicherheitsupdates für Ihre Microsoft Managed Desktop Geräte. 

Um Nutzungsdaten anzuzeigen, wählen Sie die Registerkarte <strong>Windows Sicherheitsupdates</strong> aus.

![Windows Bereich für Sicherheitsupdates: Balkendiagramme des Gerätestatus und der Updateversion in der linken Spalte, Aktualisierung des Bereitstellungsfortschritts im Zeitverlauf in der mittleren Spalte und Prozentsatz der aktiven Geräte nach Bereitstellungsgruppe sowie die Anzahl der Tage, die benötigt werden, um das Bereitstellungsziel von 95 % in der rechten Spalte zu erreichen.](../../media/update-insights.jpg)

## <a name="device-status"></a>Gerätestatus

Damit Geräte durch Windows Update aktualisiert werden können, müssen sie mit dem Internet verbunden sein und nicht mindestens sechs Stunden in den Ruhezustand bleiben, von denen zwei fortlaufend sein müssen. Obwohl es möglich ist, dass ein Gerät, das diese Anforderungen nicht erfüllt, aktualisiert wird, haben Geräte, die diese Anforderungen erfüllen, die höchste Wahrscheinlichkeit, aktualisiert zu werden. 

Wir kategorisieren Geräteaktivitäten im Kontext von Windows Update mit den folgenden Begriffen:

- <strong>Aktiv:</strong> Geräte, die die Mindestaktivitätskriterien (sechs Stunden, zwei fortlaufend) für die letzte Sicherheitsupdateversion erfüllt haben und mindestens alle fünf Tage mit Microsoft Intune eingecheckt wurden
- <strong>Synchronisiert:</strong> Geräte, die innerhalb der letzten 28 Tage bei Intune eingecheckt haben
- <strong>Nicht mehr synchron:</strong> Geräte, die in den letzten 28 Tagen <i>nicht</i> bei Intune eingecheckt wurden




## <a name="update-version-status"></a>Aktualisieren des Versionsstatus

Microsoft veröffentlicht sicherheitsrelevante Updates jeden zweiten Dienstag des Monats. Jede Version fügt wichtige Updates für bekannte Sicherheitsrisiken hinzu. Microsoft Managed Desktop stellt sicher, dass 95 % der verwalteten Geräte jeden Monat mit dem neuesten verfügbaren Sicherheitsupdate aktualisiert werden. Sicherheitsupdates werden manchmal zu anderen Zeiten veröffentlicht, um neue Bedrohungen dringend zu beheben. Microsoft Managed Desktop stellt diese Updates auf ähnliche Weise bereit.

Wir kategorisieren den Status von Sicherheitsupdateversionen mit den folgenden Begriffen:

- <strong>Aktuell:</strong> Geräte, auf denen das im aktuellen Monat veröffentlichte Update ausgeführt wird
- <strong>Zurück:</strong> Geräte, auf denen das Update ausgeführt wird, das im vorherigen Monat veröffentlicht wurde
- <strong>Älter:</strong> Geräte, auf denen ein Sicherheitsupdate ausgeführt wird, das vor dem vorherigen Monat veröffentlicht wurde

Sie sollten einige Geräte in der <strong>älteren</strong> Kategorie sehen – eine große oder wachsende Population deutet wahrscheinlich auf ein erhebliches Problem hin, das Sie an Microsoft Managed Desktop melden sollten, damit wir untersuchen können.


## <a name="deployment-progress"></a>Bereitstellungsfortschritt

Zu Beginn jedes Sicherheitsupdate-Veröffentlichungszyklus erstellt Microsoft Managed Desktop eine Momentaufnahme der Geräteanzahl und legt das Bereitstellungsziel auf 95 % dieser Population fest. Der <strong>Bereich "Bereitstellungsfortschritt"</strong> zeigt einen historischen Trend, der täglich aktualisiert wird, und verfolgt, wie eng die Updatebereitstellung dieses Ziel für jede Version erreicht. Dieses Diagramm zeigt nur Geräte mit dem Status "Aktiv".

Sie können diese Daten für vorherige Updatezyklen anzeigen, indem Sie das Dropdownmenü oben rechts verwenden. Der in diesem Menü ausgewählte Zeitraum gilt für alle Informationen auf der gesamten Seite.

Der Bereich <strong>"Aktualisierte aktive Geräte nach Bereitstellungsgruppen"</strong> bietet eine andere Ansicht, indem der Fortschritt der Updateinstallation für jede der Microsoft Managed Desktop Bereitstellungsgruppen angezeigt wird.

In den <strong>Tagen bis zum Erreichen</strong> des Zielbereichs wird angezeigt, wie lange es gedauert hat, bis 95 % der Gesamtzahl der Geräte mit dem aktuellen Sicherheitsupdate aktualisiert wurden. Während der Bereitstellung wird in diesem Bereich weiterhin <strong>aktualisiert,</strong> bis das Ziel von 95 % für das ausgewählte Update erreicht ist.

## <a name="device-details-area"></a>Gerätedetails

Am unteren Rand des Dashboards finden Sie eine Tabelle mit detaillierten Informationen zu Ihren Geräten, einschließlich des [Gerätestatus](#device-status) und des [Updateversionsstatus.](#update-version-status) Sie können diese Liste durchsuchen oder nach einem beliebigen aufgelisteten Wert filtern.


![Tabelle mit Gerätedetails mit Spalten für Gerätename, zugewiesener Benutzer, Gerätestatus, Updateversion, Betriebssystemversion und datum der letzten Synchronisierung des Geräts.](../../media/security-update-insights-device-table-sterile.png)
