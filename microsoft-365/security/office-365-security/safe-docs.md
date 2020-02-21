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
ms.openlocfilehash: 3980746eb2f48e77c22f5139827bead5640dad61
ms.sourcegitcommit: 1c445d68e54ca4249024ca4bb72460dd6fac0a2d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/20/2020
ms.locfileid: "42170475"
---
# <a name="safe-documents-in-office-365-advanced-threat-protection"></a>Sichere Dokumente in Office 365 Advanced Threat Protection

Safe Documents ist ein Feature in Office 365 Advanced Threat Protection (ATP), das [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) zum Überprüfen von Dokumenten und Dateien verwendet, die in der [geschützten Ansicht](https://support.office.com/article/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653)geöffnet werden.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Dieses Feature steht nur Benutzern mit der Sicherheitslizenz Microsoft 365 E5 oder Microsoft 365 E5 zur Verfügung.

- Sichere Dokumente stehen derzeit für die öffentliche Vorschau zur Verfügung, die für Benutzer verfügbar sind, die Teil des [Office-Insider Programms](https://insider.office.com/en-us/join) auf dem "monatlichen Kanal (Targeted)" mit der Office-Version 2002 (12527,20092) oder höher sind. Dieses Feature ist standardmäßig deaktiviert und muss vom Sicherheits Administrator aktiviert werden.

- Derzeit wird nur die US-Region für die kompatible Dateiverarbeitung unterstützt (alle Dateien werden zur Überprüfung in die US-Region Reisen). Die Unterstützung für die Region Großbritannien/EU ist in einem zukünftigen Update geplant.

- Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell). Informationen zum Herstellen einer Verbindung mit Exchange Online Protection PowerShell finden Sie unter [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).

- Sie müssen Berechtigungen zugewiesen haben, bevor Sie die Verfahren in diesem Thema ausführen können. Um sichere Dokumente zu aktivieren und zu konfigurieren, müssen Sie Mitglied der Rollengruppen " **Organisationsverwaltung** " oder " **Sicherheits Administrator** " sein. Weitere Informationen zu Rollengruppen im Security & Compliance Center finden Sie unter [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).

## <a name="use-the-office-365-security--compliance-center-to-configure-safe-documents"></a>Konfigurieren sicherer Dokumente mithilfe des Office 365 Security & Compliance Center

1. Öffnen Sie das Office 365 Security & Compliance Center <https://protection.office.com>unter.

2. Wechseln Sie zu **Threat Management** \> **Policy** \> **ATP Safe Attachments**.

3. Konfigurieren Sie im Abschnitt **Hilfe für Personen, die beim Vertrauen auf eine Datei beim Öffnen außerhalb geschützter Ansicht in Office-Anwendungen sicher bleiben eine** der folgenden Einstellungen:

   - **Aktivieren sicherer Dokumente für Office-Clients (Dateien werden auch an Microsoft Cloud für tiefe Analysen gesendet)**

   - **Personen können durch die geschützte Ansicht klicken, selbst wenn sichere Dokumente die Datei als bösartig Kenn**zeichnen: Es wird empfohlen, diese Option nicht zu aktivieren.

4. Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.

![Seite "ATP-sichere Anlagen"](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-or-exchange-online-protection-powershell-to-configure-safe-documents"></a>Konfigurieren sicherer Dokumente mithilfe von Exchange Online PowerShell oder Exchange Online Protection PowerShell

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
