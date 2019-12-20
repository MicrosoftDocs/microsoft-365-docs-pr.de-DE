---
title: Aktivieren von Office 365 ATP für SharePoint, OneDrive und Microsoft Teams
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 02/06/2019
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 07e76024-0c80-40dc-8c48-1dd0d0f863cb
ms.collection:
- M365-security-compliance
- SPO_Content
description: Hier erfahren Sie, wie Sie ATP für SharePoint, OneDrive und Microsoft Teams aktivieren, einschließlich der Vorgehensweise zum Festlegen von Benachrichtigungen für erkannte Dateien.
ms.openlocfilehash: 49e29f838fa8fbcd4b0b6eea36e9bbe2d5547a7f
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2019
ms.locfileid: "40806738"
---
# <a name="turn-on-office-365-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>Aktivieren von Office 365 ATP für SharePoint, OneDrive und Microsoft Teams

> [!IMPORTANT]
> Dieser Artikel richtet sich an Geschäftskunden, die über [Office 365 Advanced Threat Protection](office-365-atp.md) verfügen. Wenn Sie ein Privatbenutzer sind, der nach Informationen zu sicheren Links in Outlook sucht, lesen Sie [Erweiterte Outlook.com-Sicherheit](https://support.office.com/article/882d2243-eab9-4545-a58a-b36fee4a46e2).

[Office 365 ATP für SharePoint, OneDrive und Microsoft Teams](atp-for-spo-odb-and-teams.md) schützt Ihre Organisation vor versehentlicher Freigabe schädlicher Dateien. Wenn eine bösartige Datei erkannt wird, wird diese Datei blockiert, sodass niemand Sie öffnen, kopieren, weiterleiten oder freigeben kann, bis weitere Aktionen vom Sicherheitsteam der Organisation ausgeführt werden. Lesen Sie diesen Artikel, um ATP für SharePoint, OneDrive und Teams zu aktivieren, Warnungen einzurichten, um über erkannte Dateien benachrichtigt zu werden, und führen Sie die nächsten Schritte aus.

Um ATP-Richtlinien zu definieren oder zu bearbeiten, muss Ihnen eine entsprechende Rolle zugewiesen sein. In der folgenden Tabelle werden einige Beispiele beschrieben:

|Rolle|Wo/wie zugewiesen|
|---------|---------|
|Globaler Office 365-Administrator|Die Person, die sich zum Kauf Office 365 registriert, ist standardmäßig ein globaler Administrator. (Weitere Informationen finden Sie unter [Informationen zu Office 365 Administratorrollen](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) .)|
|Sicherheitsadministrator|Azure Active Directory Admin Center ([https://aad.portal.azure.com](https://aad.portal.azure.com))|
|Exchange Online-Organisationsverwaltung|Exchange Admin Center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) <br>oder <br>  PowerShell-Cmdlets (siehe [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell))|

## <a name="turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>Aktivieren von ATP für SharePoint, OneDrive und Microsoft Teams

**Bevor Sie mit diesem Verfahren beginnen, müssen Sie sicherstellen, dass die Überwachungsprotokollierung bereits für Ihre Office 365 Umgebung aktiviert ist**. Dies erfolgt in der Regel durch eine Person, der die Rolle "Überwachungsprotokolle" in Exchange Online zugewiesen ist. Weitere Informationen finden Sie unter [Aktivieren oder Deaktivieren von Office 365 Überwachungsprotokoll Suche](../../compliance/turn-audit-log-search-on-or-off.md).

1. Wechseln Sie [https://protection.office.com](https://protection.office.com)zu, und melden Sie sich mit ihrem geschäftlichen oder Schulkonto an.

2. Wählen Sie im Office 365 Security #a0 Compliance Center im linken Navigationsbereich unter **Bedrohungs Verwaltung**die Option **Richtlinien** \> für **sichere Anlagen**aus.

   ![Wählen Sie im Security #a0 Compliance Center die Option Threat \> Management Policy aus.](../media/08849c91-f043-4cd1-a55e-d440c86442f2.png)

3. Wählen Sie **ATP für SharePoint, OneDrive und Microsoft Teams aktivieren**aus.

   ![Aktivieren von Advanced Threat Protection für SharePoint Online, OneDrive für Unternehmen und Microsoft Teams](../media/48cfaace-59cc-4e60-bf86-05ff6b99bdbf.png)

4. Klicken Sie auf **Speichern**.

5. Überprüfen Sie (und bearbeiten Sie gegebenenfalls die Richtlinien für [sichere Anlagen](set-up-atp-safe-attachments-policies.md) Ihrer Organisation und [Richtlinien für sichere Links](set-up-atp-safe-links-policies.md)).

6. Empfohlen Führen Sie als globaler Administrator oder SharePoint Online Administrator das Cmdlet " **[SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** " aus, wobei der Parameter " _DisallowInfectedFileDownload_ " auf " *true*" festgelegt ist.

   - Durch Festlegen des Parameters auf *true* werden alle Aktionen (außer DELETE) für erkannte Dateien blockiert. Personen können erkannte Dateien nicht öffnen, kopieren oder freigeben.

   - Durch Festlegen des Parameters auf *false* werden alle Aktionen außer DELETE und Download blockiert. Personen können wählen, das Risiko zu akzeptieren und eine erkannte Datei herunterzuladen.

7. Lassen Sie bis zu 30 Minuten zu, bis Ihre Änderungen auf alle Office 365-Rechenzentren verteilt sind.

8. Empfohlen Fahren Sie mit Einrichten von Benachrichtigungen für erkannte Dateien fort.

Weitere Informationen zur Verwendung von PowerShell mit Office 365 finden Sie unter [Manage Office 365 with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell).

Weitere Informationen zur Benutzerfreundlichkeit, wenn eine Datei als bösartig erkannt wurde, finden Sie unter [Vorgehensweise, wenn eine schädliche Datei in SharePoint Online, OneDrive oder Microsoft Teams gefunden wird](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2).

## <a name="set-up-alerts-for-detected-files"></a>Einrichten von Benachrichtigungen für erkannte Dateien

Um eine Benachrichtigung zu erhalten, wenn eine Datei in SharePoint Online, OneDrive für Unternehmen oder Microsoft Teams als bösartig identifiziert wurde, können Sie eine Warnung einrichten.

1. Wählen Sie im [Office 365 Security #a0 Compliance Center](https://protection.office.com) **Alerts** \> **Manage Alerts**aus.

2. Wählen Sie **neue Warnungs Richtlinie**aus.

3. Geben Sie einen Namen für die Warnung an. Sie können beispielsweise böswillige Dateien in Bibliotheken eingeben.

4. Geben Sie eine Beschreibung für die Warnung ein. Sie können beispielsweise benachrichtigte Administratoren eingeben, wenn schädliche Dateien in SharePoint Online, OneDrive oder Microsoft Teams erkannt werden.

5. Führen Sie im Abschnitt **Diese Warnung senden, wenn...** folgende Schritte aus:

   a. Wählen Sie in der Liste **Aktivitäten** die Option **erkannte Schadsoftware in Datei aus**.

   b. Lassen Sie das Feld **Benutzer** leer.

6. Wählen Sie im Abschnitt **diese Benachrichtigung an... senden** einen oder mehrere globale Administratoren, Sicherheitsadministratoren oder Sicherheits Leser aus, die eine Benachrichtigung erhalten sollen, wenn eine Schadsoftware erkannt wird.

7. Klicken Sie auf **Speichern**.

Weitere Informationen zu Warnungen finden Sie unter [Erstellen von Aktivitäts Warnungen im Office 365 Security #a0 Compliance Center](../../compliance/create-activity-alerts.md).

## <a name="next-steps"></a>Nächste Schritte

1. [Anzeigen von Informationen zu bösartigen Dateien, die in SharePoint, OneDrive oder Microsoft Teams erkannt wurden](malicious-files-detected-in-spo-odb-or-teams.md)

2. [Verwalten von isolierten Nachrichten und Dateien als Administrator in Office 365](manage-quarantined-messages-and-files.md)
