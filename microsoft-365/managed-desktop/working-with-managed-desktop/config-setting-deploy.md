---
title: Bereitstellen konfigurierbarer Einstellungen in Microsoft Managed Desktop
description: Bereitstellen und Nachverfolgen konfigurierbarer Einstellungsänderungen in Microsoft Managed Desktop.
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation, bereitstellen, mehrstufige Bereitstellung, konfigurierbare Einstellungen
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: aad4995f9c329b0fd8fcbcc8b1d13379453c2a76
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287795"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a>Bereitstellen und Nachverfolgen konfigurierbarer Einstellungen – Microsoft Managed Desktop

Nachdem Sie Änderungen an den Einstellungskategorien vorgenommen und eine Bereitstellung bereitgestellt haben, können Sie auf der Seite "Bereitstellungsstatus" mit der Bereitstellung Ihrer Einstellungen für Gruppen beginnen. Auf dieser Seite wird eine Zusammenfassung der einzelnen konfigurierbaren Einstellungen angezeigt. Durch Öffnen einer Einstellungskategorie können Sie Einstellungen für Gruppen bereitstellen und den Fortschritt dieser Bereitstellungen nachverfolgen.

## <a name="deployment-statuses"></a>Bereitstellungsstatus

Dies sind die Status, die Für jede Bereitstellung angezeigt werden.

Status | Erklärung
--- | ---
Bereitstellen | Ihre Änderung wartet darauf, für diese Gruppe bereitgestellt zu werden.
In Arbeit | Die Änderung wird auf aktive Geräte in dieser Gruppe angewendet.
Abschließen | Die Änderung wurde auf allen aktiven Geräten in dieser Gruppe abgeschlossen.
Fehlgeschlagen | Die Änderung ist auf 10 Prozent der aktiven Geräte in der Gruppe fehlgeschlagen, sodass die Bereitstellung beendet wurde.<br><br> Eine Supportanfrage wird automatisch mit Microsoft Managed Desktop-Vorgängen geöffnet, um die Bereitstellung zu beheben.
Wiederhergestellt | Die Änderung wurde auf die letzte Änderung zurückgesetzt, die erfolgreich für alle Bereitstellungsgruppen bereitgestellt wurde.

## <a name="deploy-changes"></a>Bereitstellen von Änderungen

In diesen Anweisungen wird das Hintergrundbild des Desktops angezeigt. Nachdem Sie eine Bereitstellung bereitgestellt haben, stellen Sie Änderungen über die Seite "Bereitstellungsstatus" bereit.

**So stellen Sie Änderungen bereit**

1. Melden Sie sich bei [Microsoft Endpoint Manager an,](https://endpoint.microsoft.com/) und navigieren Sie zum Menü **"Geräte".**
2. Suchen Sie nach dem Abschnitt Microsoft Managed Desktop, wählen Sie **Einstellungen** aus.
3. Wählen Sie im Arbeitsbereich **"Bereitstellungsstatus"** die Einstellung aus, die Sie bereitstellen möchten, und wählen Sie dann die bereitstellungsbezogene Bereitstellung aus.
4. Wählen Sie **"Bereitstellen"** aus, um die Änderung in einer der Bereitstellungsgruppen bereitzustellen.

> [!NOTE]
> Das orangefarbene Warnsymbol zeigt an, dass eine vorherige Gruppe für die Bereitstellung verfügbar ist, da es empfohlen wird, das Rollout in der angegebenen Reihenfolge durchzuführen.

<!-- Needs picture updated to show MEM ![Deployment status workspace. Trusted sites pane on the right. In the Deployment groups section are three columns: deployment groups, devices, and status. In the status column, "deploy" is highlighted.](../../media/1deployedit.png) -->

Es wird empfohlen, die Bereitstellung für Bereitstellungsgruppen in der folgenden Reihenfolge durchzuführen: "Test", "First", "Fast" und "Broad". 

Wenn die Änderungen in jeder Gruppe abgeschlossen sind, wird der Status in **"Abgeschlossen"** geändert.

<!-- Needs picture updated to show MEM ![Deployment status workspace with columns for date updated, version, test, first, fast, and broad. The Proxy row is expanded, showing a dated setting flagged as "complete" in each of the four deployment groups.](../../media/2completeedit.png) -->

## <a name="revert-deployment"></a>Bereitstellung kehren zurück

Nachdem Sie eine Änderung bereitgestellt haben, können Sie den **Bereitstellungsstatus** kehren. Wenn Sie eine Änderung kehren, die **in Bearbeitung** oder **abgeschlossen** ist, wird die aktuelle Bereitstellung beendet. Die Einstellung wird auf die letzte Version zurückgesetzt, die für alle Gruppen bereitgestellt wurde.

Wir zeigen die Schritte zum Rückgängig machen einer Änderung mithilfe des Desktop-Hintergrundbilds als Beispiel. 

**So kehren Sie eine Änderung zurück**

1. Melden Sie sich bei [Microsoft Endpoint Manager an,](https://endpoint.microsoft.com/) und navigieren Sie zum Menü **"Geräte".**
2. Suchen Sie nach dem Abschnitt Microsoft Managed Desktop, wählen Sie **Einstellungen** aus.
3. Wählen Sie im Arbeitsbereich **"Bereitstellungsstatus"** die Einstellung aus, die Sie zurücksetzen möchten, und wählen Sie dann die mehrstufige Bereitstellung aus, die wiederhergestellt werden soll.
4. Wählen Sie unter **"Notwendigkeit, diese Änderung rückgängig zu machen?"** die Option **"Bereitstellung kehren"** aus.

<!-- Needs picture updated to show MEM ![Deployment status workspace. Browser start pages is selected, opening a pane on the right side with data about the submitted change and its status. At the bottom is the "need to revert this change" area where you can select "Revert deployment."](../../media/3revert.png) -->

## <a name="additional-resources"></a>Weitere Ressourcen

- [Übersicht über konfigurierbare Einstellungen](config-setting-overview.md)
- [Referenz der konfigurierbaren Einstellungen](config-setting-ref.md) 
