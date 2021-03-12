---
title: Einrichten von Advanced eDiscovery in Microsoft 365
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
- m365solution-ediscovery
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: In diesem Artikel wird beschrieben, wie Sie Advanced eDiscovery einrichten, damit Sie mit dem Erstellen und Verwalten von Fällen beginnen können. Außerdem werden die erforderlichen Microsoft-Abonnements und -Lizenzierung beschrieben. Nachdem Sie einige schnelle Schritte abgeschlossen haben, ist das Advanced eDiscovery-Tool einsatzbereit.
ms.openlocfilehash: 29a220f36a55a04d1c1a24add03b2e013a5c60ba
ms.sourcegitcommit: 3d48e198e706f22ac903b346cadda06b2368dd1e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2021
ms.locfileid: "50727410"
---
# <a name="set-up-microsoft-365-advanced-ediscovery"></a>Einrichten von Microsoft 365 Advanced eDiscovery

Advanced eDiscovery in Microsoft 365 bietet einen [End-to-End-Workflow](overview-ediscovery-20.md#advanced-ediscovery-workflow) zum Beibehalten, Sammeln, Überprüfen, Analysieren und Exportieren von Daten, die auf interne und externe Untersuchungen Ihrer Organisation reagieren. Für die Bereitstellung von Advanced eDiscovery ist nichts erforderlich, aber es gibt einige erforderliche Aufgaben, die ein IT-Administrator und eDiscovery-Manager ausführen müssen, bevor Ihre Organisation mit der Erstellung und Verwendung von Advanced eDiscovery-Fällen beginnen kann, um Ihre Untersuchungen zu verwalten.

In diesem Artikel werden die schritte erläutert, die zum Einrichten von Advanced eDiscovery erforderlich sind. Dies umfasst die Sicherstellung der ordnungsgemäßen Lizenzierung, die für den Zugriff auf Advanced eDiscovery und das Hinzufügen von Verwahrern zu Fällen erforderlich ist, und das Zuweisen von Berechtigungen zu Ihrem Rechts- und Untersuchungsteam, damit diese auf Fälle zugreifen und diese verwalten können.

## <a name="step-1-verify-and-assign-appropriate-licenses"></a>Schritt 1: Überprüfen und Zuweisen entsprechender Lizenzen

Die Lizenzierung für Advanced eDiscovery erfordert das entsprechende Organisationsabonnement und die Benutzerlizenzierung.

- **Organisationsabonnement:** Für den Zugriff auf Advanced eDiscovery im Microsoft 365 Compliance Center oder im Security & Compliance Center muss Ihre Organisation über eine der folgenden Funktionen verfügen:

  - Microsoft 365 E5- oder Office 365 E5-Abonnement
  
  - Microsoft 365 E3-Abonnement mit E5-Compliance-Add-On

  - Microsoft 365 E3-Abonnement mit E5 eDiscovery und Audit-Add-On

  Wenn Sie keinen vorhandenen Microsoft 365 E5-Plan haben und Advanced eDiscovery ausprobieren möchten, können [](https://www.microsoft.com/microsoft-365/enterprise) Sie [Microsoft 365](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365) zu Ihrem vorhandenen Abonnement hinzufügen oder sich für eine Testversion von Microsoft 365 E5 registrieren.

- **Benutzerlizenzierung:** Um einen Benutzer in einem Advance eDiscovery-Fall als Verwahrer hinzuzufügen, muss diesem Benutzer eine der folgenden Lizenzen zugewiesen werden, abhängig von Ihrem Organisationsabonnement:

  - Microsoft 365: Benutzern muss eine Microsoft 365 E5-Lizenz, eine E5 Compliance-Add-On-Lizenz oder eine E5 eDiscovery- und Audit-Add-On-Lizenz zugewiesen werden.

  - Office 365: Benutzern muss eine Office 365 E5-Lizenz zugewiesen sein.

   Informationen zum Zuweisen von Lizenzen finden Sie unter [Zuweisen von Lizenzen zu Benutzern](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).

> [!NOTE]
> Benutzer benötigen nur eine E5-Lizenz (oder die entsprechende Add-On-Lizenz), um einem Advanced eDiscovery-Fall als Verwahrer hinzugefügt zu werden. IT-Administratoren, eDiscovery-Manager, Anwälte, Paralegale oder Ermittler, die Advanced eDiscovery verwenden, um Fälle zu verwalten und Falldaten zu überprüfen, benötigen keine E5- oder Add-On-Lizenz.

## <a name="step-2-assign-ediscovery-permissions"></a>Schritt 2: Zuweisen von eDiscovery-Berechtigungen

Um auf Advanced eDiscovery zu zugreifen oder als Mitglied eines Advanced eDiscovery-Falls hinzugefügt zu werden, müssen einem Benutzer die entsprechenden Berechtigungen zugewiesen werden. Insbesondere muss ein Benutzer als Mitglied der Rollengruppe eDiscovery Manager im Security & Compliance Center hinzugefügt werden. Mitglieder dieser Rollengruppe können Erweiterte eDiscovery-Fälle erstellen und verwalten. Sie können Mitglieder hinzufügen und entfernen, Verwahrer und Inhaltsspeicherorte in den Haltemodus setzen, Benachrichtigungen über rechtliches Halterecht verwalten, in einem Fall zugeordnete Suchen erstellen und bearbeiten, Suchergebnisse zu einem Überprüfungssatz hinzufügen, Daten in einem Überprüfungssatz analysieren und aus einem Advanced eDiscovery-Fall exportieren und herunterladen.

Führen Sie die folgenden Schritte aus, um der Rollengruppe eDiscovery Manager Benutzer hinzuzufügen:

1. Wechseln Sie zu und melden Sie sich mit den Anmeldeinformationen für ein [https://protection.office.com/permissions](https://protection.office.com/permissions) Administratorkonto in Ihrer Microsoft 365-Organisation an.

2. Wählen Sie **auf der** Seite Berechtigungen die **Rollengruppe eDiscovery-Manager** aus.

3. Klicken Sie auf der Flyoutseite  des eDiscovery-Managers neben dem **eDiscovery-Manager** auf Bearbeiten.

4. Klicken Sie auf der Seite **eDiscovery-Manager** auswählen im Assistenten zum Bearbeiten von Rollengruppen auf **eDiscovery-Manager auswählen.**

5. Klicken **Sie auf** Hinzufügen, und aktivieren Sie dann das Kontrollkästchen für alle Benutzer, die Sie der Rollengruppe hinzufügen möchten.

6. Klicken **Sie auf** Hinzufügen, um die ausgewählten Benutzer hinzuzufügen, und klicken Sie dann auf **Fertig**.

7. Klicken **Sie auf Speichern,** um die Benutzer zur Rollengruppe hinzuzufügen, und klicken Sie dann auf **Schließen,** um den Schritt zu vervollständigen.

### <a name="more-information-about-the-ediscovery-manager-role-group"></a>Weitere Informationen zur Rollengruppe eDiscovery-Manager

Die Rollengruppe eDiscovery Manager besteht aus zwei Untergruppen. Der Unterschied zwischen diesen Untergruppen basiert auf dem Bereich.

- **eDiscovery-Manager:** Kann die erweiterten eDiscovery-Fälle anzeigen und verwalten, bei denen sie erstellt wurden oder Mitglied sind. Wenn ein anderer eDiscovery-Manager einen Fall erstellt, aber keinen zweiten eDiscovery-Manager als Mitglied dieses Falls hinzu fügt, kann der zweite eDiscovery-Manager den Fall nicht auf der Seite Advanced eDiscovery im Compliance Center anzeigen oder öffnen. Im Allgemeinen können die meisten Personen in Ihrer Organisation der Untergruppe eDiscovery Manager hinzugefügt werden.

- **eDiscovery-Administrator:** Kann alle Fallverwaltungsaufgaben ausführen, die ein eDiscovery-Manager ausführen kann. Außerdem kann ein eDiscovery-Administrator Folgendes:

  - Anzeigen aller Fälle, die auf der Seite „ Advanced eDiscovery“ aufgeführt sind.
  
  - Verwalten aller Fälle in der Organisation, nachdem er sich selbst als Fallmitglied hinzugefügt hat.

  - Zugreifen auf und Exportieren von Falldaten für jeden Fall in der Organisation.

  Aufgrund des breit gefächerten Zugriffs sollte eine Organisation nur über wenige Administratoren verfügen, die Mitglieder der Untergruppe der eDiscovery-Administratoren sind.

Weitere Informationen zu eDiscovery-Berechtigungen und eine Beschreibung jeder Rolle, die der Rollengruppe eDiscovery-Manager zugewiesen ist, finden Sie unter [Assign eDiscovery permissions](assign-ediscovery-permissions.md).

## <a name="step-3-configure-global-settings-for-advanced-ediscovery"></a>Schritt 3: Konfigurieren globaler Einstellungen für Advanced eDiscovery

Der letzte Schritt, der abgeschlossen werden muss, bevor Personen in Ihrer Organisation mit dem Erstellen und Verwenden von Fällen beginnen, besteht in der Konfiguration globaler Einstellungen, die für alle Fälle in Ihrer Organisation gelten. Derzeit ist die einzige globale Einstellung die Erkennung von *Anwalts-Client-Rechten* (in Zukunft sind weitere globale Einstellungen verfügbar). Diese Einstellung ermöglicht die Ausführung des Anwalts-Client-Berechtigungsmodells, wenn Sie Daten in einem Überprüfungssatz analysieren. Das Modell verwendet maschinelles Lernen, um die Wahrscheinlichkeit zu bestimmen, dass ein Dokument Inhalte enthält, die rechtlicher Natur sind. Außerdem werden die Teilnehmer von Dokumenten mit einer Anwaltsliste verglichen (die Sie beim Einrichten des Modells übermitteln), um festzustellen, ob ein Dokument über mindestens einen Teilnehmer verfügt, der Anwalt ist.

Weitere Informationen zum Einrichten und Verwenden des Erkennungsmodells für Anwalts-Client-Rechte finden Sie unter [Set up attorney-client privilege detection in Advanced eDiscovery](attorney-privilege-detection.md).

> [!NOTE]
> Dies ist ein optionaler Schritt, den Sie jederzeit ausführen können. Wenn Sie das Erkennungsmodell für Anwalts-Client-Rechte nicht implementieren, können Sie advanced eDiscovery-Fälle nicht erstellen und verwenden.

## <a name="next-steps"></a>Nächste Schritte

Nachdem Sie Advanced eDiscovery eingerichtet haben, können Sie [einen Fall erstellen.](create-and-manage-advanced-ediscoveryv2-case.md)
