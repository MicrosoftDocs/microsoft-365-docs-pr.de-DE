---
title: Aktivieren oder Deaktivieren der Überwachung
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
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: e893b19a-660c-41f2-9074-d3631c95a014
ms.custom: seo-marvel-apr2020
description: So aktivieren oder deaktivieren Sie das Feature für die Überwachungsprotokollsuche im Microsoft 365 Compliance Center, um die Möglichkeit von Administratoren zum Durchsuchen des Überwachungsprotokolls zu aktivieren oder zu deaktivieren.
ms.openlocfilehash: dd39b883036ce6060aef71c6a927c03f391d827f
ms.sourcegitcommit: 5db5047c24b56f3af90c2bc5c830a7a13eeeccad
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2021
ms.locfileid: "53341496"
---
# <a name="turn-auditing-on-or-off"></a>Aktivieren oder Deaktivieren der Überwachung

Die Überwachungsprotokollierung ist für Microsoft 365- und Office 365 Enterprise-Organisationen standardmäßig aktiviert. Wenn die Überwachung in der Microsoft 365 Compliance Center aktiviert ist, werden die Aktivitäten von Benutzern und Administratoren aus Ihrer Organisation im Überwachungsprotokoll aufgezeichnet und 90 Tage lang und bis zu einem Jahr aufbewahrt, je nach der Den Benutzern zugewiesenen Lizenz. Möglicherweise hat Ihre Organisation jedoch Gründe dafür, dass Überwachungsprotokolldaten nicht aufgezeichnet und aufbewahrt werden sollen. In diesen Fällen kann ein globaler Administrator die Überwachung in Microsoft 365 deaktivieren.

Beim Einrichten einer neuen Microsoft 365 oder Office 365 Organisation können Sie den Überwachungsstatus für Ihre Organisation überprüfen. Anweisungen finden Sie im Abschnitt ["Überprüfen des Überwachungsstatus für Ihre Organisation"](#verify-the-auditing-status-for-your-organization) in diesem Artikel.

> [!IMPORTANT]
> Wenn Sie die Überwachung in Microsoft 365 deaktivieren, können Sie die Office 365-Verwaltungsaktivitäts-API oder Azure Sentinel nicht für den Zugriff auf Überwachungsdaten für Ihre Organisation verwenden. Wenn Sie die Überwachung deaktivieren, indem Sie die Schritte in diesem Artikel ausführen, werden beim Durchsuchen des Überwachungsprotokolls mithilfe des Microsoft 365 Compliance Center oder beim Ausführen des Cmdlets **Search-UnifiedAuditLog** in Exchange Online PowerShell keine Ergebnisse zurückgegeben. Dies bedeutet auch, dass Überwachungsprotokolle nicht über die Office 365-Verwaltungsaktivitäts-API oder Azure Sentinel verfügbar sind.
  
## <a name="before-you-turn-auditing-on-or-off"></a>Vor dem Aktivieren oder Deaktivieren der Überwachung

- Ihnen muss die Rolle "Überwachungsprotokolle" in Exchange Online zugewiesen werden, um die Überwachung in Ihrer Microsoft 365 Organisation zu aktivieren oder zu deaktivieren. Standardmäßig wird diese Rolle den Rollengruppen "Complianceverwaltung" und "Organisationsverwaltung" auf der Seite **"Berechtigungen"** im Exchange Admin Center zugewiesen. Globale Administratoren in Microsoft 365 sind Mitglieder der Rollengruppe "Organisationsverwaltung" in Exchange Online.

    > [!NOTE]
    > Benutzern müssen Berechtigungen in Exchange Online zugewiesen werden, um die Überwachung zu aktivieren oder zu deaktivieren. Wenn Sie Benutzern die Rolle "Überwachungsprotokolle" auf der Seite **"Berechtigungen"** im Microsoft 365 Compliance Center zuweisen, können sie die Überwachung nicht aktivieren oder deaktivieren. Dies liegt daran, dass das zugrunde liegende Cmdlet ein Exchange Online PowerShell-Cmdlet ist.

- Schritt-für-Schritt-Anweisungen zum Durchsuchen des Überwachungsprotokolls finden Sie unter [Durchsuchen des Überwachungsprotokolls.](search-the-audit-log-in-security-and-compliance.md) Weitere Informationen zur Microsoft 365-Verwaltungsaktivitäts-API finden Sie unter [Erste Schritte mit Microsoft 365-Verwaltungs-APIs.](/office/office-365-management-api/get-started-with-office-365-management-apis)

## <a name="verify-the-auditing-status-for-your-organization"></a>Überprüfen des Überwachungsstatus für Ihre Organisation

Um zu überprüfen, ob die Überwachung für Ihre Organisation aktiviert ist, können Sie den folgenden Befehl in [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)ausführen:

```powershell
Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
```

Der Wert `True` für die  _UnifiedAuditLogIngestionEnabled-Eigenschaft_ gibt an, dass die Überwachung aktiviert ist. Ein Wert von `False` gibt an, dass die Überwachung nicht aktiviert ist.

## <a name="turn-on-auditing"></a>Aktivieren der Überwachung

Wenn die Überwachung für Ihre Organisation nicht aktiviert ist, können Sie sie im Microsoft 365 Compliance Center oder mithilfe Exchange Online PowerShell aktivieren. Es kann mehrere Stunden dauern, nachdem Sie die Überwachung aktiviert haben, bevor Sie beim Durchsuchen des Überwachungsprotokolls Ergebnisse zurückgeben können.
  
### <a name="use-the-compliance-center-to-turn-on-auditing"></a>Verwenden des Compliance Centers zum Aktivieren der Überwachung

1. Gehen Sie auf <https://compliance.microsoft.com>, und melden Sie sich an.

2. Klicken Sie im linken Navigationsbereich des Microsoft 365 Compliance Center auf **"Überwachen".**

   Wenn die Überwachung für Ihre Organisation nicht aktiviert ist, wird ein Banner angezeigt, in dem Sie aufgefordert werden, die Benutzer- und Administratoraktivitäten aufzuzeichnen.

   ![Banner auf der Seite "Überwachung"](../media/AuditingBanner.png)

3. Klicken Sie auf das Banner "Aufzeichnung von **Benutzer- und Administratoraktivitäten starten".**

   Es kann bis zu 60 Minuten dauern, bis die Änderung wirksam wird.

### <a name="use-powershell-to-turn-on-auditing"></a>Verwenden von PowerShell zum Aktivieren der Überwachung

1. [Stellen Sie eine Verbindung mit Exchange Online PowerShell her](/powershell/exchange/connect-to-exchange-online-powershell).

2. Führen Sie den folgenden PowerShell-Befehl aus, um die Überwachung zu aktivieren.

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    Es wird eine Meldung angezeigt, die besagt, dass es bis zu 60 Minuten dauern kann, bis die Änderung wirksam wird.
  
## <a name="turn-off-auditing"></a>Deaktivieren der Überwachung

Sie müssen Exchange Online PowerShell verwenden, um die Überwachung zu deaktivieren.
  
1. [Stellen Sie eine Verbindung mit Exchange Online PowerShell her](/powershell/exchange/connect-to-exchange-online-powershell).

2. Führen Sie den folgenden PowerShell-Befehl aus, um die Überwachung zu deaktivieren.

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. Überprüfen Sie nach einer Weile, ob die Überwachung deaktiviert ist. Sie können auf zwei Arten vorgehen:

    - Führen Sie in Exchange Online PowerShell den folgenden Befehl aus:

      ```powershell
      Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
      ```

      Der Wert  `False` der  _UnifiedAuditLogIngestionEnabled-Eigenschaft_ gibt an, dass die Überwachung deaktiviert ist.

    - Wechseln Sie zur **Seite "Überwachung"** im Microsoft 365 Compliance Center.

      Wenn die Überwachung für Ihre Organisation nicht aktiviert ist, wird ein Banner angezeigt, in dem Sie aufgefordert werden, die Benutzer- und Administratoraktivitäten aufzuzeichnen.
