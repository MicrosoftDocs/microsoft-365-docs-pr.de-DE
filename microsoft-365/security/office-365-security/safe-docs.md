---
title: Sichere Dokumente in Office 365 ATP
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: kshi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Erfahren Sie mehr über sichere Dokumente in Office 365 ATP.
ms.openlocfilehash: 11c2736edee3dd1fcbc2560d5fa574def05a8f6e
ms.sourcegitcommit: 8e655c6cbb91bfb97efda9a99c39fac33eaa974a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "44213116"
---
# <a name="safe-documents-in-office-365-advanced-threat-protection"></a>Sichere Dokumente in Office 365 Advanced Threat Protection

Safe Documents ist ein Feature in Office 365 Advanced Threat Protection (Office 365 ATP), das [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) zum Überprüfen von Dokumenten und Dateien verwendet, die in der [geschützten Ansicht](https://support.office.com/article/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653)geöffnet werden.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Dieses Feature steht nur Benutzern mit der Sicherheitslizenz Microsoft 365 E5 oder Microsoft 365 E5 zur Verfügung.

- Sichere Dokumente stehen derzeit für die öffentliche Vorschau zur Verfügung, die für Benutzer verfügbar sind, die Teil des [Office-Insider Programms](https://insider.office.com/en-us/join) auf dem "monatlichen Kanal (Targeted)" mit der Office-Version 2002 (12527,20092) oder höher sind. Dieses Feature ist standardmäßig deaktiviert und muss vom Sicherheits Administrator aktiviert werden.

- Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell). Informationen zum Herstellen einer Verbindung mit einer eigenständigen EoP PowerShell finden Sie unter [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).

- Sie müssen Berechtigungen zugewiesen haben, bevor Sie die Verfahren in diesem Thema ausführen können. Um sichere Dokumente zu aktivieren und zu konfigurieren, müssen Sie Mitglied der Rollengruppen " **Organisationsverwaltung** " oder " **Sicherheits Administrator** " sein. Weitere Informationen zu Rollengruppen im Security & Compliance Center finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).

## <a name="how-does-microsoft-handle-your-data"></a>Wie verarbeitet Microsoft Ihre Daten?

Damit Sie geschützt bleiben, sendet Safe Documents Dateien zur Analyse an die [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) -Cloud.

- Details dazu, wie der erweiterte Thread Schutz von Microsoft Defender Ihre Daten verarbeitet, finden Sie [hier](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy) .
- Zusätzlich zu den oben aufgeführten Richtlinien werden Dateien, die von sicheren Dokumenten gesendet werden, nicht in Defender aufbewahrt, was in der Regel weniger als 24 Stunden dauert, die für die Analyse benötigt werden.

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a>Konfigurieren sicherer Dokumente mithilfe des Security & Compliance Center

1. Öffnen Sie das Security & Compliance Center unter <https://protection.office.com> .

2. Wechseln Sie zu **Threat Management** \> **Policy** \> **ATP Safe Attachments**.

3. Konfigurieren Sie im Abschnitt **Hilfe für Personen, die beim Vertrauen auf eine Datei beim Öffnen außerhalb geschützter Ansicht in Office-Anwendungen sicher bleiben eine** der folgenden Einstellungen:

   - **Aktivieren sicherer Dokumente für Office-Clients (Dateien werden auch an Microsoft Cloud für tiefe Analysen gesendet)**

   - **Personen können durch die geschützte Ansicht klicken, selbst wenn sichere Dokumente die Datei als bösartig Kenn**zeichnen: Es wird empfohlen, diese Option nicht zu aktivieren.

4. Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.

![Seite "ATP-sichere Anlagen"](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-documents"></a>Verwenden Exchange Online PowerShell oder eigenständiger EoP PowerShell zum Konfigurieren sicherer Dokumente

Verwenden Sie die folgende Syntax:

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true|$false> -AllowSafeDocsOpen <$true|$false>
```

- Der Parameter _EnableSafeDocs_ aktiviert oder deaktiviert sichere Dokumente für die gesamte Organisation.

- Der Parameter _AllowSafeDocsOpen_ ermöglicht oder verhindert, dass Benutzer die geschützte Ansicht (also das Öffnen des Dokuments) verlassen, wenn das Dokument als bösartig gekennzeichnet wurde.

In diesem Beispiel werden sichere Dokumente für die gesamte Organisation aktiviert, und es wird verhindert, dass Benutzer Dokumente öffnen, die als "bösartig" aus geschützter Ansicht identifiziert wurden.

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Sets-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-atppolicyforo365).

### <a name="how-do-i-know-this-worked"></a>Woher weiß ich, dass der Vorgang erfolgreich war?

Führen Sie einen der folgenden Schritte aus, um zu überprüfen, ob Sie sichere Dokumente aktiviert und konfiguriert haben:

- Im Security & Compliance Center gehen Sie zu **Threat Management** \> **Policy** \> **ATP Safe Attachments**, und überprüfen Sie die Auswahl im Abschnitt **Hilfe Personen bleiben sicher, wenn Sie einer Datei vertrauen, dass Sie außerhalb geschützter Ansicht in Office-Anwendungen geöffnet** wird.

- Führen Sie den folgenden Befehl in Exchange Online PowerShell aus, und überprüfen Sie die Eigenschaftswerte:

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```
