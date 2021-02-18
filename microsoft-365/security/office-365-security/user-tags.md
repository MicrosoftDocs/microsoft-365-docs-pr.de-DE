---
title: Benutzertags in Microsoft Defender für Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Administratoren können erfahren, wie Sie bestimmte Benutzergruppen mit Benutzertags in Microsoft Defender für Office 365 Plan 2 identifizieren. Die Tagfilterung ist in Warnungen, Berichten und Untersuchungen in Microsoft Defender für Office 365 verfügbar, um die markierten Benutzer schnell zu identifizieren.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 62d858fe5962b94f536d4ccbd712e21bdd5caa57
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290129"
---
# <a name="user-tags-in-microsoft-defender-for-office-365"></a>Benutzertags in Microsoft Defender für Office 365

> [!NOTE]
> Das Feature für Benutzertags befindet sich in der Vorschau, ist nicht für alle verfügbar und kann geändert werden. Informationen zum Veröffentlichungszeitplan finden Sie in der [Microsoft 365-Roadmap.](https://www.microsoft.com/microsoft-365/roadmap)

Benutzertags sind Bezeichner für bestimmte Benutzergruppen in [Microsoft Defender für Office 365.](office-365-atp.md) Es gibt zwei Arten von Benutzertags:

- **Systemtags:** Derzeit sind [Prioritätskonten](../../admin/setup/priority-accounts.md) der einzige Systemtagtyp.
- **Benutzerdefinierte Tags:** Sie erstellen diese Benutzertags selbst.

Wenn Ihre Organisation über Defender für Office 365 Plan 2 verfügt (in Ihrem Abonnement oder als Add-On enthalten), können Sie benutzerdefinierte Benutzertags zusätzlich zur Verwendung des Prioritätskontotags erstellen.

Nachdem Sie Systemtags oder benutzerdefinierte Tags auf Benutzer angewendet haben, können Sie diese Tags als Filter in Warnungen, Berichten und Untersuchungen verwenden:

- [Warnungen im Security & Compliance Center](alerts.md)
- [Bedrohungs-Explorer und Echtzeiterkennungen](threat-explorer.md)
- [Threat Protection-Statusbericht](view-email-security-reports.md#threat-protection-status-report)
- [Kampagnenansichten](campaigns.md)
- Für Prioritätskonten können Sie den Bericht "E-Mail-Probleme [für](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) Prioritätskonten" im Exchange Admin Center (EAC) verwenden.

In diesem Artikel wird erläutert, wie Sie Benutzertags im Security & Compliance Center konfigurieren. Es gibt keine Cmdlets im Security & Compliance Center zum Verwalten von Benutzertags.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>. Öffnen Sie die Seite **"Benutzertags",** um direkt zur Seite "Benutzertags" zu <https://protection.office.com/userTags> wechseln.

- Bevor Sie die Verfahren in diesem Artikel ausführen können, müssen Ihnen im Security & Compliance Center Berechtigungen zugewiesen werden.
  - Zum Erstellen, Ändern und Löschen von Benutzertags müssen Sie Mitglied der Rollengruppe **"Organisationsverwaltung"** oder **"Sicherheitsadministrator"** sein.
  - Zum Hinzufügen und Entfernen von Mitgliedern aus vorhandenen Benutzertags müssen Sie Mitglied der Rollengruppen **"Organisationsverwaltung",** **"Sicherheitsadministrator"** oder "Sicherheitsoperator" sein. 
  - Für den schreibgeschützten Zugriff auf Benutzertags müssen  Sie Mitglied der Rollengruppe "Globaler Leser" oder **"Sicherheitsleser"** sein.

  Weitere Informationen finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).

  **Hinweise**:

  - Durch das Hinzufügen von Benutzern zur entsprechenden Azure Active Directory-Rolle im Microsoft 365 Admin Center erhalten Benutzer die erforderlichen Berechtigungen im Security & Compliance Center _und_ Berechtigungen für andere Features in Microsoft 365. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).
  - Die Verwaltung von Benutzertags wird durch die **Rollen "Tag Reader",** **"Tag Contributor"** und **"Tag Manager"** gesteuert.

- Sie können auch Prioritätskonten im Microsoft 365 Admin Center verwalten und überwachen. Anweisungen finden Sie unter [Verwalten und Überwachen von Prioritätskonten.](../../admin/setup/priority-accounts.md)

## <a name="use-the-security-center-to-create-user-tags"></a>Verwenden des Sicherheitscenters zum Erstellen von Benutzertags

1. Wechseln Sie im Security Center zu Benutzertags für **die** \> **Bedrohungsverwaltung.**

2. Klicken Sie **auf der Seite "Benutzertags",** die geöffnet wird, auf **"Tag erstellen".**

3. Der **Assistent zum Erstellen** von Tags wird in einem neuen Flyout geöffnet. Konfigurieren Sie **auf der Seite "Tag** definieren" die folgenden Einstellungen:
   - **Name**: Geben Sie einen eindeutigen, beschreibenden Namen für das Tag ein. Dies ist der Wert, den Sie sehen und verwenden werden.
   - **Beschreibung**: Geben Sie eine optionale Beschreibung für das Tag ein.

   Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.

4. Gehen Sie **auf der** Seite "Benutzer zuweisen" wie folgt vor:

   - Klicken Sie **auf "Benutzer hinzufügen".** In dem angezeigten Flyout müssen Sie einen der folgenden Schritte ausführen, um einzelne Benutzer oder Gruppen hinzuzufügen:
     - Klicken Sie in das Feld, und scrollen Sie durch die Liste, um einen Benutzer oder eine Gruppe auszuwählen.
     - Klicken Sie in das Feld, und beginnen Sie mit der Eingabe, um die Liste zu filtern und einen Benutzer oder eine Gruppe auszuwählen.
     - Wenn Sie weitere Werte hinzufügen möchten, klicken Sie in einen leeren Bereich des Felds.
     - Um einzelne Einträge aus dem  Feld zu entfernen, klicken Sie auf das Symbol "Entfernen" für den Benutzer oder die ![ Gruppe im ](../../media/scc-remove-icon.png) Feld.
     - Um vorhandene Einträge aus der Liste  unterhalb des Felds zu entfernen, klicken Sie auf ![ "Entfernen", um den ](../../media/scc-remove-icon.png) Eintrag zu entfernen.

     Klicken Sie nach Abschluss des Vorgangs auf **Hinzufügen**.

   - Klicken **Sie auf "Importieren",** um eine Textdatei auszuwählen, die die E-Mail-Adressen der Benutzer oder Gruppen enthält. Stellen Sie sicher, dass die Textdatei einen Eintrag pro Zeile enthält.

   Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.

5. Überprüfen Sie **auf der Seite "Überprüfungstag"** Ihre Einstellungen. Sie können im jeweiligen Abschnitt **auf** "Bearbeiten" klicken, um Änderungen vorzunehmen.

   Klicken Sie nach Abschluss des Abschlusses auf **"Absenden".**

## <a name="use-the-security-center-to-view-user-tags"></a>Verwenden des Sicherheitscenters zum Anzeigen von Benutzertags

1. Wechseln Sie im Security Center zu Benutzertags für **die** \> **Bedrohungsverwaltung.**

2. Wählen Sie **auf der Seite** mit den Benutzertags, die geöffnet wird, das Benutzertag aus, das Sie anzeigen möchten (klicken Sie nicht auf das Kontrollkästchen).

3. Überprüfen Sie in den angezeigten schreibgeschützten Details die Einstellungen.

   Klicken Sie nach Abschluss des Vorgangs auf **Schließen**.

## <a name="use-the-security-center-to-modify-user-tags"></a>Verwenden des Sicherheitscenters zum Ändern von Benutzertags

1. Wechseln Sie im Security Center zu Benutzertags für **die** \> **Bedrohungsverwaltung.**

2. Wählen Sie **auf der Seite** mit den Benutzertags, die geöffnet wird, das Benutzertag aus, das Sie anzeigen möchten, und klicken Sie dann auf **"Tag bearbeiten".**

3. Der Richtlinienassistent wird im Flyout **"Tag** bearbeiten" geöffnet. Klicken **Sie auf "Weiter",** um die Einstellungen zu überprüfen und zu ändern.

   Klicken Sie nach Abschluss des Abschlusses auf **"Absenden".**

## <a name="use-the-security-center-to-remove-user-tags"></a>Entfernen von Benutzertags mithilfe des Sicherheitscenters

**Hinweis:** Sie können das integrierte Prioritätskontotag **nicht** entfernen.

1. Wechseln Sie im Security Center zu Benutzertags für **die** \> **Bedrohungsverwaltung.**

2. Wählen Sie **auf** der Seite mit den Benutzertags, die geöffnet wird, das Benutzertag aus, das Sie entfernen möchten, klicken Sie auf "Tag löschen" **und** dann in der angezeigten Warnung auf "Ja", "Entfernen". 
