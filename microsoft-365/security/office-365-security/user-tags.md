---
title: Benutzer Tags
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Administratoren können erfahren, wie bestimmte Benutzergruppen mit Benutzer Tags in Oiffce 365 ATP Plan 2 identifiziert werden. Die Tag-Filterung ist für Warnungen, Berichte und Untersuchungen in Office 365 ATP verfügbar, um die getaggten Benutzer schnell zu identifizieren.
ms.openlocfilehash: d47c5c00e3cf0362c44aebc18d11db4bba68a149
ms.sourcegitcommit: e5ac81132cc5fd248350627a3cc7b3c640f53b6e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48210026"
---
# <a name="user-tags-in-the-microsoft-security-center"></a>Benutzer Tags im Microsoft-Sicherheits Center

Benutzer Tags sind Bezeichner für bestimmte Benutzergruppen in [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md). [Priority Accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) sind ein Typ von User-Tag. Wenn Ihre Organisation Office 365 ATP-Plan 2 (in Ihrem Abonnement oder als Add-on enthalten) hat, können Sie benutzerdefinierte Benutzer Tags zusätzlich zur Verwendung des Tags Priority Accounts erstellen.

Nachdem Sie Tags auf bestimmte Benutzer angewendet haben, können Sie diese Tags als Filter in Warnungen, Berichten und Untersuchungen verwenden:

- [Warnungen im Security & Compliance Center](alerts.md)
- [Threat Explorer und Echtzeiterkennung](threat-explorer.md)
- [Threat Protection-Statusbericht](view-email-security-reports.md#threat-protection-status-report)
- [Kampagnenansichten](campaigns.md)

In diesem Artikel wird erläutert, wie Benutzer Tags im Sicherheits Center konfiguriert werden.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sie öffnen das Sicherheits Center unter <https://security.microsoft.com/> . Wenn Sie direkt zur Seite **Benutzer Tags** wechseln möchten, öffnen Sie <https://security.microsoft.com/securitysettings/userTags> .

- Um Benutzer Tags zu erstellen, zu ändern oder zu entfernen, müssen Sie Mitglied der Rollengruppen " **Organisationsverwaltung** " oder " **Sicherheits Administrator** " im Security & Compliance Center sein. Weitere Informationen finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).

- Sie können auch Prioritäts Konten im Microsoft 365 Admin Center verwalten und überwachen. Anweisungen finden Sie unter [Verwalten und Überwachen von Prioritäts Konten](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).

## <a name="use-the-security-center-to-create-user-tags"></a>Erstellen von Benutzer Tags mithilfe des Sicherheitscenters

1. Wechseln Sie im Sicherheits Center zu **Einstellungen** \> **e-Mail-& Collaboration-** \> **Benutzer Tags**.

2. Klicken Sie auf der Seite **Benutzer Tags** , die geöffnet wird, auf **Tag erstellen**.

3. Der Assistent zum **Erstellen von Tags** wird in einem neuen Fly Out geöffnet. Konfigurieren Sie auf der Seite **Tag definieren** die folgenden Einstellungen:

   - **Name**: Geben Sie einen eindeutigen, beschreibenden Namen für das Tag ein. Dies ist der Wert, den Sie sehen und verwenden.

   - **Beschreibung**: Geben Sie eine optionale Beschreibung für das Tag ein.

   Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.

4. Führen Sie auf der Seite **Postfächer zuweisen** einen der folgenden Schritte aus:

   - Klicken Sie auf **Postfächer hinzufügen**. Führen Sie im angezeigten Fenster einen der folgenden Schritte aus, um einzelne Benutzer oder Gruppen hinzuzufügen:

     - Klicken Sie in das Feld, und führen Sie einen Bildlauf durch die Liste aus, um einen Benutzer oder eine Gruppe auszuwählen.
     - Klicken Sie in das Feld, und beginnen Sie mit der Eingabe, um die Liste zu filtern und einen Benutzer oder eine Gruppe auszuwählen.
     - Klicken Sie zum Hinzufügen weiterer Werte in einen leeren Bereich des Felds.
     - Wenn Sie einzelne Einträge aus dem Feld entfernen möchten **, klicken Sie** ![ im Feld auf entfernen-Symbol Entfernen ](../../media/scc-remove-icon.png) für den Benutzer oder die Gruppe.
     - Wenn Sie vorhandene Einträge aus der Liste unter dem Feld entfernen möchten **Remove** , klicken Sie auf Remove ![ Icon ](../../media/scc-remove-icon.png) the entry entfernen.

     Wenn Sie fertig sind, klicken Sie auf **Hinzufügen**.

   - Klicken Sie auf **importieren** , um eine Textdatei auszuwählen, die die e-Mail-Adressen der Benutzer oder Gruppen enthält. Stellen Sie sicher, dass die Textdatei einen Eintrag pro Zeile enthält.

   Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.

5. Überprüfen Sie auf der Seite **Tag überprüfen** Ihre Einstellungen. Sie können auf **Bearbeiten** im bestimmten Abschnitt klicken, um Änderungen vorzunehmen.

   Wenn Sie fertig sind, klicken Sie auf über **Mitteln**.

## <a name="use-the-security-center-to-view-user-tags"></a>Verwenden des Sicherheitscenters zum Anzeigen von Benutzer Tags

1. Wechseln Sie im Sicherheits Center zu **Einstellungen** \> **e-Mail-& Collaboration-** \> **Benutzer Tags**.

2. Wählen Sie auf der Seite **Benutzer Tags** , die geöffnet wird, das Benutzertag aus, das Sie anzeigen möchten (Klicken Sie nicht auf das Kontrollkästchen).

3. Überprüfen Sie die Einstellungen in den angezeigten Details im Bereich Schreibschutz.

   Klicken Sie nach Abschluss des Vorgangs auf **Schließen**.

## <a name="use-the-security-center-to-modify-user-tags"></a>Verwenden des Sicherheitscenters zum Ändern von Benutzer Tags

1. Wechseln Sie im Sicherheits Center zu **Einstellungen** \> **e-Mail-& Collaboration-** \> **Benutzer Tags**.

2. Wählen Sie auf der Seite **Benutzer Tags** , die geöffnet wird, das Benutzertag aus, das Sie anzeigen möchten, und klicken Sie dann auf **Tag bearbeiten**.

3. Der Richtlinien-Assistent wird in einem **Edit-Tag** geöffnet, um zu fliegen. Klicken Sie auf **weiter** , um die Einstellungen zu überprüfen und zu ändern.

   Wenn Sie fertig sind, klicken Sie auf über **Mitteln**.

## <a name="use-the-security-center-to-remove-user-tags"></a>Entfernen von Benutzer Tags mithilfe des Sicherheitscenters

**Hinweis**: Sie können das integrierte **Priority-Konto** -Tag nicht entfernen.

1. Wechseln Sie im Sicherheits Center zu **Einstellungen** \> **e-Mail-& Collaboration-** \> **Benutzer Tags**.

2. Wählen Sie auf der Seite **Benutzer Tags** , die geöffnet wird, das Benutzertag aus, das Sie entfernen möchten, klicken Sie auf **Tag löschen**, und wählen Sie dann **Ja, entfernen** in der angezeigten Warnung aus.
