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
description: Administratoren können erfahren, wie sie bestimmte Benutzergruppen mit Benutzertags in Microsoft Defender für Office 365 Plan 2 identifizieren. Die Tagfilterung ist für Warnungen, Berichte und Untersuchungen in Microsoft Defender verfügbar, damit Office 365 die markierten Benutzer schnell identifizieren können.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1fb948d63f7bc42839d6fae8a2138d4ad48d81f6
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879168"
---
# <a name="user-tags-in-microsoft-defender-for-office-365"></a>Benutzertags in Microsoft Defender für Office 365

> [!NOTE]
> Das Feature "Benutzertags" befindet sich in der Vorschau, ist nicht für alle verfügbar und kann geändert werden. Informationen zum Veröffentlichungszeitplan finden Sie in der [Roadmap Microsoft 365.](https://www.microsoft.com/microsoft-365/roadmap)

Benutzertags sind Bezeichner für bestimmte Benutzergruppen in [Microsoft Defender für Office 365.](defender-for-office-365.md) Es gibt zwei Arten von Benutzertags:

- **Systemtags:** Derzeit sind [Prioritätskonten](../../admin/setup/priority-accounts.md) der einzige Typ von Systemtag.
- **Benutzerdefinierte Tags:** Sie erstellen diese Benutzertags selbst.

Wenn Ihre Organisation über Defender for Office 365 Plan 2 verfügt (in Ihrem Abonnement oder als Add-On enthalten), können Sie zusätzlich zur Verwendung des Prioritätskontentags benutzerdefinierte Benutzertags erstellen.

> [!NOTE]
> Derzeit können Sie Benutzertags nur auf Postfachbenutzer anwenden.

Nachdem Sie Systemtags oder benutzerdefinierte Tags auf Benutzer angewendet haben, können Sie diese Tags als Filter in Warnungen, Berichten und Untersuchungen verwenden:

- [Benachrichtigungen](alerts.md)
- [Bedrohungs-Explorer und Echtzeiterkennungen](threat-explorer.md)
- [Threat Protection-Statusbericht](view-email-security-reports.md#threat-protection-status-report)
- [Kampagnenansichten](campaigns.md)
- Für Prioritätskonten können Sie den [Bericht "E-Mail-Probleme bei Prioritätskonten"](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) im Exchange Admin Center (EAC) verwenden.

In diesem Artikel wird erläutert, wie Sie Benutzertags im Microsoft 365 Defender-Portal konfigurieren. Es gibt keine Cmdlets in Microsoft 365 Defender-Portal zum Verwalten von Benutzertags.

Informationen dazu, wie Benutzertags Teil der Strategie zum Schutz von Benutzerkonten mit hoher Auswirkung sind, finden Sie in den [Sicherheitsempfehlungen für Prioritätskonten in Microsoft 365.](security-recommendations-for-priority-accounts.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sie öffnen das Microsoft 365 Defender-Portal unter <https://security.microsoft.com/> . Um direkt zur Seite **"Benutzertags"** zu wechseln, öffnen Sie <https://security.microsoft.com/securitysettings/userTags> .

- Bevor Sie die Verfahren in diesem Artikel ausführen können, müssen Ihnen im Microsoft 365 Defender-Portal Berechtigungen zugewiesen werden:
  - Um Benutzertags zu erstellen, zu ändern und zu löschen, müssen Sie Mitglied der Rollengruppen **"Organisationsverwaltung"** oder **"Sicherheitsadministrator"** sein.
  - Um Mitglieder zu vorhandenen Benutzertags hinzuzufügen und daraus zu entfernen, müssen Sie Mitglied der Rollengruppen **"Organisationsverwaltung",** **"Sicherheitsadministrator"** oder **"Sicherheitsoperator"** sein.
  - Für den schreibgeschützten Zugriff auf Benutzertags müssen Sie Mitglied der Rollengruppe **"Globaler Leser"** oder **"Sicherheitsleseberechtigter"** sein.

  Weitere Informationen finden Sie unter [Berechtigungen im Microsoft 365 Defender-Portal.](permissions-in-the-security-and-compliance-center.md)

  > [!NOTE]
  >
  > - Wenn Sie Benutzer zur entsprechenden Azure Active Directory Rolle im Microsoft 365 Admin Center hinzufügen, erhalten Benutzer die erforderlichen Berechtigungen im Microsoft 365 Defender-Portal _und_ Berechtigungen für andere Features in Microsoft 365. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).
  >
  > - Die Verwaltung von Benutzertags wird durch die Rollen **"Tag-Reader"** und **"Tag-Manager"** gesteuert.

- Sie können Prioritätskonten auch im Microsoft 365 Admin Center verwalten und überwachen. Anweisungen finden Sie unter [Verwalten und Überwachen von Prioritätskonten.](../../admin/setup/priority-accounts.md)

- Informationen zum Schützen _privilegierter Konten_ (Administratorkonten) finden Sie in [diesem Thema.](/azure/architecture/framework/security/critical-impact-accounts)

## <a name="use-the-microsoft-365-defender-portal-to-create-user-tags"></a>Verwenden des Microsoft 365 Defender-Portals zum Erstellen von Benutzertags

1. Wechseln Sie im Microsoft 365 Defender-Portal zu **Einstellungen** \> **E-Mail-&** \> **Benutzertags** für die Zusammenarbeit.

2. Klicken Sie auf der Seite **"Benutzertags"** auf das ![ Symbol "Tag ](../../media/m365-cc-sc-create-icon.png) **erstellen"**.

3. Der Assistent **zum Erstellen von Tags** wird in einem neuen Flyout geöffnet. Konfigurieren Sie auf der Seite **"Tag definieren"** die folgenden Einstellungen:
   - **Name:** Geben Sie einen eindeutigen, beschreibenden Namen für das Tag ein. Dies ist der Wert, den Sie sehen und verwenden werden. Beachten Sie, dass Sie ein Tag nach der Erstellung nicht umbenennen können.
   - **Beschreibung:** Geben Sie eine optionale Beschreibung für das Tag ein.

   Wenn Sie fertig sind, klicken Sie auf **Weiter**.

4. Führen Sie auf der Seite **"Mitglieder zuweisen"** einen der folgenden Schritte aus:
   - Klicken Sie auf ![ "Mitglieder hinzufügen" auf symbol ](../../media/m365-cc-sc-create-icon.png) **"Mitglieder hinzufügen".** Führen Sie im angezeigten Flyout einen der folgenden Schritte aus, um einzelne Benutzer oder Gruppen hinzuzufügen:
     - Klicken Sie in das Feld, und scrollen Sie durch die Liste, um einen Benutzer oder eine Gruppe auszuwählen.
     - Klicken Sie in das Feld, und beginnen Sie mit der Eingabe, um die Liste zu filtern und einen Benutzer oder eine Gruppe auszuwählen.
     - Klicken Sie auf einen leeren Bereich im Feld, um weitere Werte hinzuzufügen.
     - Um einzelne Einträge zu entfernen, klicken Sie auf ![Eintragssymbol entfernen](../../media/m365-cc-sc-remove-selection-icon.png) neben dem Eintrag im Feld.
     - Um alle Einträge zu entfernen, klicken Sie ![ auf das Symbol "Eintrag entfernen" ](../../media/m365-cc-sc-remove-selection-icon.png) im Element **"Ausgewählte nn Benutzer" und "nn Gruppen"** unterhalb des Felds.

     Klicken Sie nach Abschluss des Vorgangs auf **Hinzufügen**.

     Zurück auf der Seite **"Mitglieder zuweisen"** können Sie einträge auch entfernen, indem Sie neben dem Eintrag auf ![ das Symbol "Löschen" ](../../media/m365-cc-sc-delete-icon.png) klicken.

   - Klicken Sie auf **"Importieren",** um eine Textdatei auszuwählen, die die E-Mail-Adressen der Benutzer oder Gruppen enthält. Stellen Sie sicher, dass die Textdatei einen Eintrag pro Zeile enthält.

   Wenn Sie fertig sind, klicken Sie auf **Weiter**.

5. Überprüfen Sie auf der daraufhin angezeigten Seite des **Überprüfungstags** Ihre Einstellungen. Sie können in jedem Abschnitt **Bearbeiten** auswählen, um die Einstellungen in diesem Abschnitt zu ändern. Alternativ können Sie auf **Zurück** klicken oder die entsprechende Seite im Assistenten auswählen.

   Wenn Sie fertig sind, klicken Sie auf **"Absenden"** und dann auf **"Fertig".**

## <a name="use-the-microsoft-365-defender-portal-to-view-user-tags"></a>Verwenden des Microsoft 365 Defender-Portals zum Anzeigen von Benutzertags

1. Wechseln Sie im Microsoft 365 Defender-Portal zu **Einstellungen** \> **E-Mail-&** \> **Benutzertags** für die Zusammenarbeit.

2. Auf der Seite **"Benutzertags"** werden die folgenden Eigenschaften in der Liste der Benutzertags angezeigt:

   - **Tag:** Der Name des Benutzertags. Beachten Sie, dass dies das integrierte **Prioritätskonto-Systemtag** enthält.
   - **Angewendet auf**: Die Anzahl der Mitglieder
   - **Zuletzt geändert**
   - **Erstellt am**

3. Wenn Sie ein Benutzertag auswählen, indem Sie auf den Namen klicken, werden die Details in einem Flyout angezeigt.

## <a name="use-the-microsoft-365-defender-portal-to-modify-user-tags"></a>Verwenden des Microsoft 365 Defender-Portals zum Ändern von Benutzertags

1. Wechseln Sie im Microsoft 365 Defender-Portal zu **Einstellungen** \> **E-Mail-&** \> **Benutzertags** für die Zusammenarbeit.

2. Wählen Sie auf der Seite **"Benutzertags"** das Benutzertag aus der Liste aus, und klicken Sie dann auf ![ "Tag bearbeiten" auf ](../../media/m365-cc-sc-edit-icon.png) **"Tag bearbeiten".**

3. Im angezeigten Detail-Flyout sind derselbe Assistent und dieselben Einstellungen verfügbar, wie im Abschnitt ["Verwenden des Microsoft 365 Defender-Portals zum Erstellen von Benutzertags"](#use-the-microsoft-365-defender-portal-to-create-user-tags) weiter oben in diesem Artikel beschrieben.

   **Hinweise**:

   - Die Seite **"Tag definieren"** ist für das integrierte Systemtag des **Prioritätskontos** nicht verfügbar, daher können Sie dieses Tag nicht umbenennen oder die Beschreibung nicht ändern.
   - Sie können ein benutzerdefiniertes Tag nicht umbenennen, aber Sie können die Beschreibung ändern.

## <a name="use-the-microsoft-365-defender-portal-to-remove-user-tags"></a>Verwenden des Microsoft 365 Defender-Portals zum Entfernen von Benutzertags

> [!NOTE]
> Sie können das integrierte **Prioritätskonto-Systemtag** nicht entfernen.

1. Wechseln Sie im Microsoft 365 Defender-Portal zu **Einstellungen** \> **E-Mail-&** \> **Benutzertags** für die Zusammenarbeit.

2. Wählen Sie auf der Seite **"Benutzertags"** das Benutzertag aus der Liste aus, und klicken Sie dann auf ![ "Tag löschen" auf ](../../media/m365-cc-sc-delete-icon.png) **"Tag löschen".**

3. Lesen Sie die Warnung im daraufhin angezeigten Bestätigungsdialogfeld, und klicken Sie dann auf **"Ja", entfernen Sie**.
