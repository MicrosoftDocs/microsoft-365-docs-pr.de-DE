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
description: Administratoren erfahren, wie Sie bestimmte Benutzergruppen mit Benutzertags in Microsoft Defender für Office 365 Plan 2 identifizieren. Die Tagfilterung ist in Warnungen, Berichten und Untersuchungen in Microsoft Defender für Office 365 verfügbar, um die markierten Benutzer schnell zu identifizieren.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e9bb6a233f21268df860974549ecffbfd7154045
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50916406"
---
# <a name="user-tags-in-microsoft-defender-for-office-365"></a>Benutzertags in Microsoft Defender für Office 365

> [!NOTE]
> Das Feature für Benutzertags befindet sich in der Vorschau, ist nicht für alle verfügbar und kann geändert werden. Informationen zum Veröffentlichungszeitplan finden Sie in [der Microsoft 365-Roadmap](https://www.microsoft.com/microsoft-365/roadmap).

Benutzertags sind Bezeichner für bestimmte Benutzergruppen in [Microsoft Defender für Office 365](office-365-atp.md). Es gibt zwei Arten von Benutzertags:

- **Systemtags**: Derzeit sind [Prioritätskonten](../../admin/setup/priority-accounts.md) der einzige Systemtagtyp.
- **Benutzerdefinierte Tags:** Sie erstellen diese Benutzertags selbst.

Wenn Ihre Organisation Defender für Office 365 Plan 2 (in Ihrem Abonnement oder als Add-On enthalten) hat, können Sie zusätzlich zum Prioritätskontotag benutzerdefinierte Benutzertags erstellen.

Nachdem Sie Systemtags oder benutzerdefinierte Tags auf Benutzer angewendet haben, können Sie diese Tags als Filter in Warnungen, Berichten und Untersuchungen verwenden:

- [Warnungen im Security & Compliance Center](alerts.md)
- [Bedrohungs-Explorer und Echtzeiterkennungen](threat-explorer.md)
- [Threat Protection-Statusbericht](view-email-security-reports.md#threat-protection-status-report)
- [Kampagnenansichten](campaigns.md)
- Für Prioritätskonten können Sie den Bericht [E-Mail-Probleme für Prioritätskonten](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) im Exchange Admin Center (EAC) verwenden.

In diesem Artikel wird erläutert, wie Sie Benutzertags im Security & Compliance Center konfigurieren. Es gibt keine Cmdlets im Security & Compliance Center zum Verwalten von Benutzertags.

Informationen dazu, wie Benutzertags Teil der Strategie zum Schutz von Benutzerkonten mit hoher Auswirkung sind, finden Sie unter Sicherheitsempfehlungen für Prioritätskonten [in Microsoft 365](security-recommendations-for-priority-accounts.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>. Öffnen Sie , um direkt zur **Seite Benutzertags zu** <https://protection.office.com/userTags> wechseln.

- Bevor Sie die Verfahren in diesem Artikel ausführen können, müssen Ihnen im Security & Compliance Center Berechtigungen zugewiesen werden.
  - Zum Erstellen, Ändern und Löschen von Benutzertags müssen  Sie Mitglied der Rollengruppen Organisationsverwaltung oder **Sicherheitsadministrator** sein.
  - Zum Hinzufügen und Entfernen von Mitgliedern aus vorhandenen Benutzertags müssen Sie Mitglied der Rollengruppen **Organisationsverwaltung,** Sicherheitsadministrator **oder** **Sicherheitsoperator** sein.
  - Für den schreibgeschützten Zugriff auf Benutzertags müssen Sie Mitglied der Rollengruppen **"Globaler Leser"** oder **"Sicherheitsleser"** sein.

  Weitere Informationen finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).

  **Hinweise**:

  - Durch das Hinzufügen von Benutzern zur entsprechenden Azure Active Directory-Rolle im Microsoft 365 Admin Center erhalten Benutzer die erforderlichen Berechtigungen im Security & Compliance Center _und_ Berechtigungen für andere Features in Microsoft 365. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).
  - Die Verwaltung von Benutzertagen wird durch die **Rollen Tag Reader und** Tag **Manager** gesteuert.

- Sie können auch Prioritätskonten im Microsoft 365 Admin Center verwalten und überwachen. Anweisungen finden Sie unter [Verwalten und Überwachen von Prioritätskonten](../../admin/setup/priority-accounts.md).

## <a name="use-the-security--compliance-center-to-create-user-tags"></a>Erstellen von Benutzertags mithilfe & Security & Compliance Center

1. Wechseln Sie im Security & Compliance Center zu **Benutzertags für die Bedrohungsverwaltung.** \> 

2. Klicken Sie **auf der** geöffneten Seite Benutzertags auf **Tag erstellen.**

3. Der **Assistent zum Erstellen** von Tag wird in einem neuen Fly-Out geöffnet. Konfigurieren Sie **auf** der Seite Tag definieren die folgenden Einstellungen:
   - **Name**: Geben Sie einen eindeutigen, beschreibenden Namen für das Tag ein. Dies ist der Wert, den Sie sehen und verwenden werden.
   - **Beschreibung**: Geben Sie eine optionale Beschreibung für das Tag ein.

   Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.

4. Gehen Sie **auf der** Seite Benutzer zuweisen wie folgt vor:

   - Klicken **Sie auf Benutzer hinzufügen.** Gehen Sie in dem angezeigten Fly-Out wie folgt vor, um einzelne Benutzer oder Gruppen hinzuzufügen:
     - Klicken Sie in das Feld, und scrollen Sie durch die Liste, um einen Benutzer oder eine Gruppe auszuwählen.
     - Klicken Sie in das Feld, und beginnen Sie mit der Eingabe, um die Liste zu filtern und einen Benutzer oder eine Gruppe auszuwählen.
     - Klicken Sie auf einen leeren Bereich im Feld, um weitere Werte hinzuzufügen.
     - Klicken Sie zum Entfernen einzelner  Einträge aus dem Feld auf Entfernen (Symbol entfernen) für den Benutzer ![ oder die Gruppe im ](../../media/scc-remove-icon.png) Feld.
     - Wenn Sie vorhandene Einträge aus der Liste unterhalb des Felds entfernen möchten, klicken Sie auf **Entfernen** ![ Symbol für den ](../../media/scc-remove-icon.png) Eintrag.

     Klicken Sie nach Abschluss des Vorgangs auf **Hinzufügen**.

   - Klicken **Sie auf Importieren,** um eine Textdatei auszuwählen, die die E-Mail-Adressen der Benutzer oder Gruppen enthält. Stellen Sie sicher, dass die Textdatei einen Eintrag pro Zeile enthält.

   Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.

5. Überprüfen Sie **auf der** Seite Tag überprüfen Ihre Einstellungen. Sie können **im** jeweiligen Abschnitt auf Bearbeiten klicken, um Änderungen vorzunehmen.

   Klicken Sie nach Abschluss des Abschlusses auf **Absenden**.

## <a name="use-the-security--compliance-center-to-view-user-tags"></a>Verwenden des Security & Compliance Center zum Anzeigen von Benutzertags

1. Wechseln Sie im Security & Compliance Center zu **Benutzertags für die Bedrohungsverwaltung.** \> 

2. Wählen Sie **auf** der geöffneten Seite Benutzertags das Benutzertag aus, das Sie anzeigen möchten (klicken Sie nicht auf das Kontrollkästchen).

3. Überprüfen Sie in den angezeigten schreibgeschützten Details die Einstellungen.

   Klicken Sie nach Abschluss des Vorgangs auf **Schließen**.

## <a name="use-the-security--compliance-center-to-modify-user-tags"></a>Verwenden des Security & Compliance Center zum Ändern von Benutzertags

1. Wechseln Sie im Security & Compliance Center zu **Benutzertags für die Bedrohungsverwaltung.** \> 

2. Wählen Sie **auf der** geöffneten Seite Benutzertags das Benutzertag aus, das Sie anzeigen möchten, und klicken Sie dann auf **Tag bearbeiten**.

3. Der Richtlinien-Assistent wird in einem **Edit-Tag** geöffnet. Klicken **Sie auf Weiter,** um die Einstellungen zu überprüfen und zu ändern.

   Klicken Sie nach Abschluss des Abschlusses auf **Absenden**.

## <a name="use-the-security--compliance-center-to-remove-user-tags"></a>Verwenden des Security & Compliance Center zum Entfernen von Benutzertags

**Hinweis:** Sie können das integrierte Prioritätskontotag **nicht** entfernen.

1. Wechseln Sie im Security & Compliance Center zu **Benutzertags für die Bedrohungsverwaltung.** \> 

2. Wählen Sie **auf** der geöffneten Seite Benutzertags das Benutzertag aus, das Sie entfernen möchten, klicken Sie auf Tag **löschen,** und wählen Sie dann **Ja,** entfernen in der angezeigten Warnung aus.