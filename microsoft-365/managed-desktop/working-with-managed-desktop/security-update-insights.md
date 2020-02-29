---
title: Informationen zu Windows-Sicherheitsupdates
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: ef2d5c897709e7f7d2484d032b7471031be77d74
ms.sourcegitcommit: cf07dfccec476ac2526a6171ec6b6365686f759f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/29/2020
ms.locfileid: "42341255"
---
# <a name="windows-security-update-insights"></a>Informationen zu Windows-Sicherheitsupdates
Diese Ansicht bietet eine Übersicht über den Status von Sicherheitsupdates für Ihre von Microsoft verwalteten Desktop Geräte. 

Um Verwendungsdaten anzuzeigen, wählen Sie die Registerkarte <strong>Windows-Sicherheitsupdates</strong> aus.

![Windows-Sicherheitsupdate Bereich: Balkendiagramme des Gerätestatus und der Update Version in der linken Spalte, Aktualisierungs Bereitstellungsfortschritt im Zeitverlauf in der mittleren Spalte und Prozentsatz aktiver Geräte nach Bereitstellungsgruppe sowie die Anzahl der Tage, die für die Bereitstellung der 95% erreicht wurden Target in der rechten Spalte.](../../media/update-insights.jpg)

## <a name="device-status"></a>Gerätestatus

Für Geräte, die von Windows Update aktualisiert werden sollen, müssen Sie mit dem Internet verbunden sein und nicht über einen Ruhezustand für mindestens sechs Stunden verfügen, von denen zwei kontinuierlich sein müssen. Solange ein Gerät angeschlossen ist und kein Ruhezustand ist, wird es als "verwendet" betrachtet. Obwohl es möglich ist, dass ein Gerät, das diese Anforderungen nicht erfüllt, aktualisiert wird, haben Geräte, die diese erfüllen, die höchste Wahrscheinlichkeit, dass Sie aktualisiert werden. 

Die Geräteaktivität wird im Kontext von Windows Update mit den folgenden Begriffen kategorisiert:

- <strong>Aktiv:</strong> Geräte, die die minimalen Verwendungskriterien (sechs Stunden, zwei kontinuierlich) für die neueste Version des Sicherheitsupdates erfüllt haben und mindestens alle fünf Tage mit Microsoft InTune eingecheckt wurden
- <strong>Synchronisiert:</strong> Geräte, die innerhalb der letzten 28 Tage mit InTune eingecheckt haben
- <strong>Nicht synchron:</strong> Geräte, die in den letzten 28 Tagen <i>nicht</i> mit InTune eingecheckt haben




## <a name="update-version-status"></a>Aktualisieren des Versionsstatus

Microsoft veröffentlicht jeden zweiten Dienstag im Monat Sicherheitsupdates. In jeder Version werden wichtige Updates für bekannte Sicherheitsrisiken hinzugefügt. Microsoft Managed Desktop stellt sicher, dass 95% der verwalteten Geräte monatlich mit dem neuesten verfügbaren Sicherheitsupdate aktualisiert werden. Manchmal werden Sicherheitsupdates zu anderen Zeiten veröffentlicht, um neue Bedrohungen dringend zu beheben. Microsoft Managed Desktop stellt diese Updates auf ähnliche Weise bereit.

Der Status von Sicherheitsupdate Versionen wird mit den folgenden Begriffen kategorisiert:

- <strong>Aktuell:</strong> Geräte, die das im aktuellen Monat veröffentlichte Update durchführen
- <strong>Zurück:</strong> Geräte, die das Update durchführen, das im vorherigen Monat veröffentlicht wurde
- <strong>Älter:</strong> Geräte, auf denen ein Sicherheitsupdate vor dem vorherigen Monat veröffentlicht wurde

Es sollten nur wenige Geräte in der <strong>älteren</strong> Kategorie angezeigt werden – eine große oder wachsende Population deutet wahrscheinlich auf ein systemisches Problem hin, das Sie an Microsoft Managed Desktop melden sollten, damit wir dies untersuchen können.


## <a name="deployment-progress"></a>Bereitstellungsfortschritt

Zu Beginn jedes Sicherheitsupdate-Veröffentlichungszyklus nimmt Microsoft Managed Desktop eine Momentaufnahme der Geräte Auffüllung vor und legt sein Bereitstellungsziel auf 95% dieser Auffüllung fest. Im Bereich <strong>Bereitstellungsfortschritt</strong> wird ein historischer Trend angezeigt, der täglich aktualisiert wird und nachverfolgen kann, wie eng die Updatebereitstellung dieses Ziel für jede Version erfüllt. In diesem Diagramm werden nur Geräte mit aktivem Status angezeigt.

Sie können diese Daten für frühere Aktualisierungszyklen anzeigen, indem Sie das Dropdownmenü in der oberen rechten Ecke verwenden. Der Zeitraum, den Sie in diesem Menü auswählen, gilt für alle Informationen auf der gesamten Seite.

Der Bereich " <strong>aktualisierte aktive Geräte nach Bereitstellungsgruppe</strong> " bietet eine andere Ansicht, indem der Fortschritt der Updateinstallation für jede der Microsoft Managed Desktop-Bereitstellungsgruppen angezeigt wird.

Der <strong>Zielbereich "Tage zum erreichen</strong> " zeigt an, wie lange es dauerte, bis 95% der Gesamtzahl der Geräte mit dem aktuellen Sicherheitsupdate aktualisiert wurden. Während der Bereitstellung wird in diesem Bereich <strong>noch aktualisiert</strong> , bis das 95%-Ziel für das ausgewählte Update erreicht wird.

## <a name="device-details-area"></a>Geräte Detailbereich

Im unteren Bereich des Dashboards finden Sie eine Tabelle mit detaillierten Informationen zu Ihren Geräten, einschließlich des [Gerätestatus](#device-status) und des [Status der Update Version](#update-version-status). Sie können diese Liste durchsuchen oder nach einem beliebigen angegebenen Wert filtern.


![Geräte Detailtabelle mit Spalten für Gerätename, zugewiesener Benutzer, Gerätestatus, Update Version, Betriebssystemversion und Datum, an dem das Gerät zuletzt synchronisiert wurde.](../../media/security-update-insights-device-table-sterile.png)
