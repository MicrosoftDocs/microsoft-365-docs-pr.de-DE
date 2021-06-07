---
title: Benutzertags in Microsoft Defender für Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 04/21/2021
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Administratoren können erfahren, wie sie bestimmte Benutzergruppen mit Benutzertags in Microsoft Defender für Office 365 Plan 2 identifizieren. Tagfilterung ist für Warnungen, Berichte und Untersuchungen in Microsoft Defender verfügbar, um Office 365, um die markierten Benutzer schnell zu identifizieren.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 44b925840700c00c6b2d28c445ac26abd6624d1c
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782861"
---
# <a name="user-tags-in-microsoft-defender-for-office-365"></a>Benutzertags in Microsoft Defender für Office 365

> [!NOTE]
> Das Feature "Benutzertags" befindet sich in der Vorschau, ist nicht für alle verfügbar und kann geändert werden. Informationen zum Veröffentlichungszeitplan finden Sie in der [Microsoft 365 Roadmap.](https://www.microsoft.com/microsoft-365/roadmap)

Benutzertags sind Bezeichner für bestimmte Benutzergruppen in [Microsoft Defender für Office 365](defender-for-office-365.md). Es gibt zwei Arten von Benutzertags:

- **Systemtags:** Derzeit sind [Prioritätskonten](../../admin/setup/priority-accounts.md) der einzige Typ von Systemtag.
- **Benutzerdefinierte Tags:** Sie erstellen diese Benutzertags selbst.

Wenn Ihre Organisation über Defender for Office 365 Plan 2 verfügt (in Ihrem Abonnement oder als Add-On enthalten), können Sie zusätzlich zur Verwendung des Prioritätskontentags benutzerdefinierte Benutzertags erstellen.

> [!NOTE]
> Derzeit können Sie Benutzertags nur auf Postfachbenutzer anwenden.

Nachdem Sie Systemtags oder benutzerdefinierte Tags auf Benutzer angewendet haben, können Sie diese Tags als Filter in Warnungen, Berichten und Untersuchungen verwenden:

- [Warnungen im Security & Compliance Center](alerts.md)
- [Bedrohungs-Explorer und Echtzeiterkennungen](threat-explorer.md)
- [Threat Protection-Statusbericht](view-email-security-reports.md#threat-protection-status-report)
- [Kampagnenansichten](campaigns.md)
- Für Prioritätskonten können Sie den [Bericht "E-Mail-Probleme bei Prioritätskonten"](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) im Exchange Admin Center (EAC) verwenden.

In diesem Artikel wird erläutert, wie Sie Benutzertags im Security & Compliance Center konfigurieren. Es gibt keine Cmdlets im Security & Compliance Center zum Verwalten von Benutzertags.

Informationen dazu, wie Benutzertags Teil der Strategie zum Schutz von Benutzerkonten mit hoher Auswirkung sind, finden Sie in den [Sicherheitsempfehlungen für Prioritätskonten in Microsoft 365.](security-recommendations-for-priority-accounts.md)

> [!NOTE]
> Wenn Sie das einheitliche Microsoft 365 Security Center verwenden, können Sie tags hier festlegen: https://security.microsoft.com/securitysettings/userTags .

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>. Um direkt zur Seite **"Benutzertags"** zu wechseln, öffnen Sie <https://protection.office.com/userTags> .

- Bevor Sie die Verfahren in diesem Artikel ausführen können, müssen Ihnen im Security & Compliance Center Berechtigungen zugewiesen werden.
  - Um Benutzertags zu erstellen, zu ändern und zu löschen, müssen Sie Mitglied der Rollengruppen **"Organisationsverwaltung"** oder **"Sicherheitsadministrator"** sein.
  - Um Mitglieder zu vorhandenen Benutzertags hinzuzufügen und daraus zu entfernen, müssen Sie Mitglied der Rollengruppen **"Organisationsverwaltung",** **"Sicherheitsadministrator"** oder **"Sicherheitsoperator"** sein.
  - Für den schreibgeschützten Zugriff auf Benutzertags müssen Sie Mitglied der Rollengruppe **"Globaler Leser"** oder **"Sicherheitsleseberechtigter"** sein.

  Weitere Informationen finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).

  > [!NOTE]
  >
  > - Durch das Hinzufügen von Benutzern zur entsprechenden Azure Active Directory-Rolle im Microsoft 365 Admin Center erhalten Benutzer die erforderlichen Berechtigungen im Security & Compliance Center _und_ Berechtigungen für andere Features in Microsoft 365. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).
  >
  > - Die Verwaltung von Benutzertags wird durch die Rollen **"Tag-Reader"** und **"Tag-Manager"** gesteuert.

- Sie können Prioritätskonten auch im Microsoft 365 Admin Center verwalten und überwachen. Anweisungen finden Sie unter [Verwalten und Überwachen von Prioritätskonten.](../../admin/setup/priority-accounts.md)

- Informationen zum Schützen _privilegierter Konten_ (Administratorkonten) finden Sie in [diesem Thema.](/azure/architecture/framework/security/critical-impact-accounts)

## <a name="use-the-security--compliance-center-to-create-user-tags"></a>Verwenden des Security & Compliance Centers zum Erstellen von Benutzertags

1. Wechseln Sie im Security & Compliance Center zu Benutzertags für die **Bedrohungsverwaltung.** \> 

2. Klicken Sie auf der seite **"Benutzertags",** die geöffnet wird, auf **"Tag erstellen".**

3. Der Assistent **zum Erstellen von Tags** wird in einem neuen Flyout geöffnet. Konfigurieren Sie auf der Seite **"Tag definieren"** die folgenden Einstellungen:
   - **Name:** Geben Sie einen eindeutigen, beschreibenden Namen für das Tag ein. Dies ist der Wert, den Sie sehen und verwenden werden.
   - **Beschreibung:** Geben Sie eine optionale Beschreibung für das Tag ein.

   Wenn Sie fertig sind, klicken Sie auf **Weiter**.

4. Führen Sie auf der Seite **"Benutzer zuweisen"** einen der folgenden Schritte aus:

   - Klicken Sie auf **"Benutzer hinzufügen".** Führen Sie im angezeigten Flyout einen der folgenden Schritte aus, um einzelne Benutzer oder Gruppen hinzuzufügen:
     - Klicken Sie in das Feld, und scrollen Sie durch die Liste, um einen Benutzer oder eine Gruppe auszuwählen.
     - Klicken Sie in das Feld, und beginnen Sie mit der Eingabe, um die Liste zu filtern und einen Benutzer oder eine Gruppe auszuwählen.
     - Klicken Sie auf einen leeren Bereich im Feld, um weitere Werte hinzuzufügen.
     - Um einzelne Einträge aus dem Feld zu entfernen, klicken Sie im Feld auf das Symbol **"Entfernen"** ![ für den Benutzer oder die ](../../media/scc-remove-icon.png) Gruppe.
     - Wenn Sie vorhandene Einträge aus der Liste unterhalb des Felds entfernen möchten, klicken Sie auf das Symbol **"Entfernen"** ![ des ](../../media/scc-remove-icon.png) Eintrags.

     Klicken Sie nach Abschluss des Vorgangs auf **Hinzufügen**.

   - Klicken Sie auf **"Importieren",** um eine Textdatei auszuwählen, die die E-Mail-Adressen der Benutzer oder Gruppen enthält. Stellen Sie sicher, dass die Textdatei einen Eintrag pro Zeile enthält.

   Wenn Sie fertig sind, klicken Sie auf **Weiter**.

5. Überprüfen Sie auf der Seite **"Tag überprüfen"** Ihre Einstellungen. Sie können im spezifischen Abschnitt auf **"Bearbeiten"** klicken, um Änderungen vorzunehmen.

   Wenn Sie fertig sind, klicken Sie auf **"Absenden".**

## <a name="use-the-security--compliance-center-to-view-user-tags"></a>Verwenden des Security & Compliance Centers zum Anzeigen von Benutzertags

1. Wechseln Sie im Security & Compliance Center zu Benutzertags für die **Bedrohungsverwaltung.** \> 

2. Wählen Sie auf der sich öffnenden Seite **"Benutzertags"** das Benutzertag aus, das Sie anzeigen möchten (klicken Sie nicht auf das Kontrollkästchen).

3. Überprüfen Sie im angezeigten Flyout mit schreibgeschützten Details die Einstellungen.

   Klicken Sie nach Abschluss des Vorgangs auf **Schließen**.

## <a name="use-the-security--compliance-center-to-modify-user-tags"></a>Verwenden des Security & Compliance Centers zum Ändern von Benutzertags

1. Wechseln Sie im Security & Compliance Center zu Benutzertags für die **Bedrohungsverwaltung.** \> 

2. Wählen Sie auf der daraufhin geöffneten Seite **"Benutzertags"** das Benutzertag aus, das Sie anzeigen möchten, und klicken Sie dann auf **"Tag bearbeiten".**

3. Der Richtlinien-Assistent wird in einem **Flyout zum Bearbeiten-Tag** geöffnet. Klicken Sie auf **"Weiter",** um die Einstellungen zu überprüfen und zu ändern.

   Wenn Sie fertig sind, klicken Sie auf **"Absenden".**

## <a name="use-the-security--compliance-center-to-remove-user-tags"></a>Verwenden des Security & Compliance Centers zum Entfernen von Benutzertags

> [!NOTE]
> Sie können das integrierte **Prioritätskontotag** nicht entfernen.

1. Wechseln Sie im Security & Compliance Center zu Benutzertags für die **Bedrohungsverwaltung.** \> 

2. Wählen Sie auf der daraufhin geöffneten Seite **"Benutzertags"** das Benutzertag aus, das Sie entfernen möchten, klicken Sie auf **"Tag löschen",** und wählen Sie dann **"Ja" aus, und entfernen** Sie es in der angezeigten Warnung.
