---
title: Bereitstellen von konfigurierbaren Einstellungen in Microsoft Managed Desktop
description: Bereitstellen und Nachverfolgen von Änderungen an konfigurierbaren Einstellungen in Microsoft Managed Desktop.
keywords: Microsoft Managed Desktop, Microsoft 365, Service, Dokumentation, Deploy, Staging-Bereitstellung, konfigurierbare Einstellungen
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: e6946c138cb6fde15e35374b447038d5c302187e
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42085757"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a>Bereitstellen und Nachverfolgen von konfigurierbaren Einstellungen – Microsoft Managed Desktop

Nachdem Sie Änderungen an den Einstellungskategorien vorgenommen und eine Bereitstellung bereitgestellt haben, können Sie mit der Seite Bereitstellungsstatus die Bereitstellung Ihrer Einstellungen für Gruppen beginnen. Auf dieser Seite wird eine Zusammenfassung der einzelnen konfigurierbaren Einstellungen angezeigt. Wenn Sie eine Einstellungskategorie öffnen, können Sie Einstellungen für Gruppen bereitstellen und den Status dieser Bereitstellungen nachverfolgen.

## <a name="deployment-statuses"></a>Bereitstellungsstatus 

Dies sind die Status, die Sie für jede Bereitstellung sehen.

Status  | Erklärung 
--- | --- 
Bereitstellen | Ihre Änderung wartet auf die Bereitstellung für diese Gruppe.
In Arbeit | Die Änderung wird auf aktive Geräte in dieser Gruppe angewendet. 
Abschließen | Die Änderung, die für alle aktiven Geräte in dieser Gruppe abgeschlossen wurde. 
Failed | Die Änderung konnte auf 10 Prozent der aktiven Geräte in der Gruppe nicht ausgeführt werden, sodass die Bereitstellung angehalten wurde.<br><br> Eine Supportanfrage wird automatisch mit Microsoft Managed Desktop Operations geöffnet, um die Bereitstellung zu beheben. 
Zurückgesetzt | Die Änderung wurde auf die letzte Änderung zurückgesetzt, die für alle Bereitstellungsgruppen erfolgreich bereitgestellt wurde.

## <a name="deploy-changes"></a>Bereitstellen von Änderungen

In diesen Anweisungen wird ein Desktop Hintergrundbild angezeigt. Nachdem Sie eine Bereitstellung bereitgestellt haben, stellen Sie die Änderungen auf der Seite Bereitstellungsstatus bereit. 

**So stellen Sie Änderungen bereit**

1. Anmelden beim [Microsoft Managed Desktop-Verwaltungsportal](https://aka.ms/mwaasportal)
2. Wählen Sie unter **Einstellungen**die Option **konfigurierbar**aus.
3. Wählen Sie im Bereich **Bereitstellungsstatus** die Einstellung aus, die Sie bereitstellen möchten, und wählen Sie dann die bereitgestellte Bereitstellung aus.
4. Wählen Sie **Bereitstellen** aus, um die Änderung an einer der Bereitstellungsgruppen bereitzustellen.

> [!NOTE] 
> Das orangefarbene Warnsymbol zeigt an, dass für die Bereitstellung eine frühere Gruppe zur Verfügung steht, da es empfehlenswert ist, das Rollout in der richtigen Reihenfolge auszuführen. 

![Bereitstellungsstatus Arbeitsbereich. Bereich vertrauenswürdige Websites auf der rechten Seite. Im Abschnitt Bereitstellungsgruppen sind drei Spalten enthalten: Bereitstellungsgruppen, Geräte und Status. In der Spalte Status wird "Deploy" hervorgehoben.](../../media/1deployedit.png)
Wir empfehlen die Bereitstellung in Bereitstellungsgruppen in dieser Reihenfolge: Test, erste, schnelle und dann breit. 

Wenn Änderungen in jeder Gruppe abgeschlossen werden, ändert sich der Status in **abgeschlossen**.

![Bereitstellungsstatus Arbeitsbereich mit Spalten für aktualisiertes Datum, Version, Test, erste, schnelle und Breite. Die Proxy Zeile wird erweitert und zeigt eine datierte Einstellung an, die in jeder der vier Bereitstellungsgruppen als "abgeschlossen" gekennzeichnet ist.](../../media/2completeedit.png)

## <a name="revert-deployment"></a>Wiederherstellen der Bereitstellung

Nachdem Sie eine Änderung bereitgestellt haben, können Sie den **Bereitstellungsstatus**wiederherstellen. Wenn Sie eine gerade **ausgeführte** oder **abgeschlossene**Änderung wiederherstellen, wird die aktuelle Bereitstellung angehalten. Die Einstellung wird auf die letzte Version zurückgesetzt, die für alle Gruppen bereitgestellt wurde. 

Wir zeigen die Schritte zum Rückgängigmachen einer Änderung mithilfe des Desktop Hintergrundbilds als Beispiel. 

**So stellen Sie eine Änderung wieder her**
1. Anmelden beim [Microsoft Managed Desktop-Verwaltungsportal](https://aka.ms/mwaasportal)
2. Wählen Sie unter **Einstellungen**die Option **konfigurierbar**aus.
3. Wählen Sie im Arbeitsbereich **Bereitstellungsstatus** die Einstellung aus, die Sie wiederherstellen möchten, und wählen Sie dann die bereitgestellte Bereitstellung aus, die wiederhergestellt werden soll.
4. Wählen Sie unter **Notwendigkeit, diese Änderung wiederherzustellen?** die Option **Bereitstellung rückgängig**machen aus.

![Bereitstellungsstatus Arbeitsbereich. Browser Startseiten werden ausgewählt, wobei ein Bereich auf der rechten Seite mit Daten über die übermittelte Änderung und deren Status geöffnet wird. Unten sehen Sie den Bereich "diese Änderung muss wiederhergestellt werden", in dem Sie "Bereitstellung wiederherstellen" auswählen können.](../../media/3revert.png) 

## <a name="additional-resources"></a>Zusätzliche Ressourcen
- [Übersicht über konfigurierbare Einstellungen](config-setting-overview.md)
- [Referenz der konfigurierbaren Einstellungen](config-setting-ref.md) 
