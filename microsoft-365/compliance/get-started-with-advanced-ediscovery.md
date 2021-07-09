---
title: Einrichten Advanced eDiscovery in Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-aed
- m365initiative-compliance
- m365solution-scenario
search.appverid:
- MOE150
- MET150
description: In diesem Artikel wird beschrieben, wie Sie Advanced eDiscovery einrichten, damit Sie mit dem Erstellen und Verwalten von Fällen beginnen können. Außerdem werden die erforderlichen Microsoft-Abonnements und -Lizenzen beschrieben. Nachdem Sie einige schnelle Schritte ausgeführt haben, kann das tool Advanced eDiscovery verwendet werden.
ms.openlocfilehash: be5e5aea03950d28889590004bd796455a71c5be
ms.sourcegitcommit: 5db5047c24b56f3af90c2bc5c830a7a13eeeccad
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2021
ms.locfileid: "53341448"
---
# <a name="set-up-microsoft-365-advanced-ediscovery"></a>Einrichten Microsoft 365 Advanced eDiscovery

Advanced eDiscovery in Microsoft 365 bietet einen End-to-End-Workflow zum Aufbewahren, Sammeln, Überprüfen, Analysieren und Exportieren von Daten, die für interne und externe Untersuchungen Ihrer Organisation relevant sind. Es ist nichts erforderlich, um Advanced eDiscovery bereitzustellen, aber es gibt einige erforderliche Aufgaben, die ein IT-Administrator und eDiscovery-Manager ausführen müssen, bevor Ihre Organisation mit der Erstellung und Verwendung von Advanced eDiscovery Fällen zur Verwaltung Ihrer Untersuchungen beginnen kann.

In diesem Artikel werden die folgenden Schritte erläutert, die zum Einrichten Advanced eDiscovery erforderlich sind.

![Schritte zum Einrichten Advanced eDiscovery](../media/set-up-advanced-ediscovery.png)

Dazu gehört die Sicherstellung der ordnungsgemäßen Lizenzierung, die für den Zugriff auf Advanced eDiscovery und das Hinzufügen von Verwahrern zu Fällen erforderlich ist, und das Zuweisen von Berechtigungen zu Ihrem Rechts- und Untersuchungsteam, damit sie auf Fälle zugreifen und diese verwalten können.

## <a name="step-1-verify-and-assign-appropriate-licenses"></a>Schritt 1: Überprüfen und Zuweisen der entsprechenden Lizenzen

Die Lizenzierung für Advanced eDiscovery erfordert das entsprechende Organisationsabonnement und eine Lizenzierung pro Benutzer. Eine Liste der Lizenzierungsanforderungen für Advanced eDiscovery finden Sie unter [Abonnements und Lizenzierung.](overview-ediscovery-20.md#subscriptions-and-licensing)

## <a name="step-2-assign-ediscovery-permissions"></a>Schritt 2: Zuweisen von eDiscovery-Berechtigungen

Um auf Advanced eDiscovery zugreifen oder als Mitglied eines Advanced eDiscovery Falls hinzugefügt werden zu können, müssen einem Benutzer die entsprechenden Berechtigungen zugewiesen werden. Insbesondere muss ein Benutzer als Mitglied der Rollengruppe "eDiscovery-Manager" im Security & Compliance Center hinzugefügt werden. Mitglieder dieser Rollengruppe können Advanced eDiscovery Fälle erstellen und verwalten. Sie können Mitglieder hinzufügen und entfernen, Verwahrer und Inhaltsspeicherorte in den Haltebereich setzen, Benachrichtigungen zur Aufbewahrung für juristische Zwecke verwalten, Suchvorgänge erstellen und bearbeiten, die in einem Fall zugeordnet sind, Suchergebnisse zu einem Prüfdateisatz hinzufügen, Daten in einem Prüfdateisatz analysieren und aus einem Advanced eDiscovery Fall exportieren und herunterladen.

Führen Sie die folgenden Schritte aus, um der Rollengruppe "eDiscovery-Manager" Benutzer hinzuzufügen:

1. Rufen Sie <https://compliance.microsoft.com/permissions> die Anmeldeinformationen für ein Administratorkonto in Ihrer Microsoft 365 Organisation auf, und melden Sie sich an.

2. Wählen Sie auf der Seite **"Berechtigungen"** die **Rollengruppe "eDiscovery-Manager"** aus.

3. Klicken Sie auf der Flyoutseite des eDiscovery-Managers neben dem **Abschnitt "eDiscovery-Manager"** auf **"Bearbeiten".**

4. Klicken Sie auf der Seite **"eDiscovery-Manager auswählen"** im Assistenten zum Bearbeiten von Rollengruppen auf **"eDiscovery-Manager auswählen".**

5. Klicken Sie auf **"Hinzufügen",** und aktivieren Sie dann das Kontrollkästchen für alle Benutzer, die Sie der Rollengruppe hinzufügen möchten.

6. Klicken Sie auf **"Hinzufügen",** um die ausgewählten Benutzer hinzuzufügen, und klicken Sie dann auf **"Fertig".**

7. Klicken Sie auf **"Speichern",** um die Benutzer zur Rollengruppe hinzuzufügen, und klicken Sie dann auf **"Schließen",** um den Schritt abzuschließen.

### <a name="more-information-about-the-ediscovery-manager-role-group"></a>Weitere Informationen zur Rollengruppe "eDiscovery-Manager"

Es gibt zwei Untergruppen in der Rollengruppe "eDiscovery-Manager". Der Unterschied zwischen diesen Untergruppen basiert auf dem Bereich.

- **eDiscovery-Manager:** Kann die Advanced eDiscovery Fälle anzeigen und verwalten, in denen sie erstellt wurden oder mitglied sind. Wenn ein anderer eDiscovery-Manager einen Fall erstellt, aber keinen zweiten eDiscovery-Manager als Mitglied dieses Falls hinzufüge, kann der zweite eDiscovery-Manager den Fall nicht auf der Advanced eDiscovery Seite im Compliance Center anzeigen oder öffnen. Im Allgemeinen können die meisten Personen in Ihrer Organisation der Untergruppe "eDiscovery-Manager" hinzugefügt werden.

- **eDiscovery-Administrator:** Kann alle Fallverwaltungsaufgaben ausführen, die ein eDiscovery-Manager ausführen kann. Außerdem kann ein eDiscovery-Administrator Folgendes:

  - Anzeigen aller Fälle, die auf der Seite „ Advanced eDiscovery“ aufgeführt sind.
  
  - Verwalten aller Fälle in der Organisation, nachdem er sich selbst als Fallmitglied hinzugefügt hat.

  - Zugreifen auf und Exportieren von Falldaten für jeden Fall in der Organisation.

  Aufgrund des breit gefächerten Zugriffs sollte eine Organisation nur über wenige Administratoren verfügen, die Mitglieder der Untergruppe der eDiscovery-Administratoren sind.

Weitere Informationen zu eDiscovery-Berechtigungen und eine Beschreibung der einzelnen Rollen, die der Rollengruppe "eDiscovery-Manager" zugewiesen sind, finden Sie unter ["Zuweisen von eDiscovery-Berechtigungen".](assign-ediscovery-permissions.md)

## <a name="step-3-configure-global-settings-for-advanced-ediscovery"></a>Schritt 3: Konfigurieren globaler Einstellungen für Advanced eDiscovery

Der letzte Schritt, der abgeschlossen werden muss, bevor Personen in Ihrer Organisation mit dem Erstellen und Verwenden von Fällen beginnen, besteht darin, globale Einstellungen zu konfigurieren, die für alle Fälle in Ihrer Organisation gelten. Zu diesem Zeitpunkt ist die einzige globale Einstellung die Erkennung von *Anwaltsgeheimnissen* (weitere globale Einstellungen werden in Zukunft verfügbar sein). Mit dieser Einstellung kann das Anwaltsgeheimnisse-Modell ausgeführt werden, wenn Sie Daten in einem Prüfdateisatz analysieren. Das Modell verwendet maschinelles Lernen, um die Wahrscheinlichkeit zu bestimmen, dass ein Dokument Inhalte enthält, die rechtlicher Natur sind. Außerdem werden die Teilnehmer von Dokumenten mit einer Anwaltsliste verglichen (die Sie beim Einrichten des Modells übermitteln), um festzustellen, ob ein Dokument mindestens einen Teilnehmer hat, der ein Anwalt ist.

Weitere Informationen zum Einrichten und Verwenden des Erkennungsmodells für Anwaltsgeheimnisse finden Sie unter Einrichten der Erkennung von [Anwaltsgeheimnissen in Advanced eDiscovery](attorney-privilege-detection.md).

> [!NOTE]
> Dies ist ein optionaler Schritt, den Sie jederzeit ausführen können. Das Nicht implementieren des Modells zur Erkennung von Anwaltsgeheimnissen hindert Sie nicht daran, Advanced eDiscovery Fälle zu erstellen und zu verwenden.

## <a name="next-steps"></a>Nächste Schritte

Nachdem Sie Advanced eDiscovery eingerichtet haben, können Sie [einen Fall erstellen.](create-and-manage-advanced-ediscoveryv2-case.md)