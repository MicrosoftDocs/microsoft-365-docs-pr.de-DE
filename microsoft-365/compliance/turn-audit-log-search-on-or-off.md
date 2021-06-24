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
ms.openlocfilehash: 7c55443eda9a99ff4ef153d8564fd9ac43fcc549
ms.sourcegitcommit: ccbdf2638fc6646bfb89450169953f4c3ce4b9b0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2021
ms.locfileid: "53105308"
---
# <a name="turn-auditing-on-or-off"></a>Aktivieren oder Deaktivieren der Überwachung

Die Überwachungsprotokollierung ist für Microsoft 365- und Office 365 Enterprise-Organisationen standardmäßig aktiviert. Das schließt Organisationen mit E3/G3- oder E5/G5-Abonnements ein. Wenn die Überwachung im Compliance Center aktiviert ist, werden die Aktivitäten von Benutzern und Administratoren aus Ihrer Organisation im Überwachungsprotokoll aufgezeichnet und 90 Tage und bis zu einem Jahr aufbewahrt, je nachdem, welche Lizenz den Benutzern zugewiesen wurde. Möglicherweise hat Ihre Organisation jedoch Gründe dafür, dass Überwachungsprotokolldaten nicht aufgezeichnet und aufbewahrt werden sollen. In diesen Fällen kann ein globaler Administrator die Überwachung in Microsoft 365 deaktivieren.

> [!IMPORTANT]
> Wenn Sie die Überwachung in Microsoft 365 deaktivieren, können Sie die Office 365-Verwaltungsaktivitäts-API oder Azure Sentinel nicht für den Zugriff auf Überwachungsdaten für Ihre Organisation verwenden. Wenn Sie die Überwachung deaktivieren, indem Sie die Schritte in diesem Artikel ausführen, werden keine Ergebnisse zurückgegeben, wenn Sie das Überwachungsprotokoll mithilfe des Security & Compliance Centers durchsuchen oder wenn Sie das Cmdlet **Search-UnifiedAuditLog** in Exchange Online PowerShell ausführen. Dies bedeutet auch, dass Überwachungsprotokolle nicht über die Office 365-Verwaltungsaktivitäts-API oder Azure Sentinel verfügbar sind.
  
## <a name="before-you-turn-auditing-on-or-off"></a>Vor dem Aktivieren oder Deaktivieren der Überwachung

- Ihnen muss die Rolle "Überwachungsprotokolle" in Exchange Online zugewiesen werden, um die Überwachung in Ihrer Microsoft 365 Organisation zu aktivieren oder zu deaktivieren. Standardmäßig wird diese Rolle den Rollengruppen "Complianceverwaltung" und "Organisationsverwaltung" auf der Seite **"Berechtigungen"** im Exchange Admin Center zugewiesen. Globale Administratoren in Microsoft 365 sind Mitglieder der Rollengruppe "Organisationsverwaltung" in Exchange Online. 

    > [!NOTE]
    > Benutzern müssen Berechtigungen in Exchange Online zugewiesen werden, um die Überwachung zu aktivieren oder zu deaktivieren. Wenn Sie Benutzern die Rolle "Überwachungsprotokolle" auf der Seite **"Berechtigungen"** im Security & Compliance Center zuweisen, können sie die Überwachung nicht aktivieren oder deaktivieren. Dies liegt daran, dass das zugrunde liegende Cmdlet ein Exchange Online PowerShell-Cmdlet ist.

- Schritt-für-Schritt-Anleitungen zum Durchsuchen des Überwachungsprotokolls finden Sie unter [Durchsuchen des Überwachungsprotokolls im Security & Compliance Center.](search-the-audit-log-in-security-and-compliance.md) Weitere Informationen zur Microsoft 365-Verwaltungsaktivitäts-API finden Sie unter [Erste Schritte mit Microsoft 365-Verwaltungs-APIs.](/office/office-365-management-api/get-started-with-office-365-management-apis)

- Um zu überprüfen, ob die Überwachung aktiviert ist, können Sie den folgenden Befehl in Exchange Online PowerShell ausführen:

    ```powershell
    Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
    ```

    Der Wert  `True` der  _UnifiedAuditLogIngestionEnabled-Eigenschaft_ gibt an, dass die Überwachung aktiviert ist. 

## <a name="turn-on-auditing"></a>Aktivieren der Überwachung

Wenn die Überwachung für Ihre Organisation nicht aktiviert ist, können Sie sie im Compliance Center oder mithilfe von Exchange Online PowerShell aktivieren. Es kann mehrere Stunden dauern, nachdem Sie die Überwachung aktiviert haben, bevor Sie beim Durchsuchen des Überwachungsprotokolls Ergebnisse zurückgeben können.
  
### <a name="use-the-compliance-center-to-turn-on-auditing"></a>Verwenden des Compliance Centers zum Aktivieren der Überwachung

1. Gehen Sie auf <https://compliance.microsoft.com>, und melden Sie sich an.

2. Klicken Sie im linken Navigationsbereich des Microsoft 365 Compliance Center auf **"Alle anzeigen"** und dann auf **"Überwachen".**

   Wenn die Überwachung für Ihre Organisation nicht aktiviert ist, wird ein Banner angezeigt, in dem Sie aufgefordert werden, die Benutzer- und Administratoraktivitäten aufzuzeichnen.

   ![Banner auf der Seite "Überwachung"](../media/AuditingBanner.png)

3. Klicken Sie auf das Banner "Aufzeichnung von **Benutzer- und Administratoraktivitäten starten".**

   Es kann bis zu 60 Minuten dauern, bis die Änderung wirksam wird.

### <a name="use-powershell-to-turn-on-auditing"></a>Verwenden von PowerShell zum Aktivieren der Überwachung

1. [Herstellen einer Verbindung mit Exchange Online mithilfe der Remote-PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Führen Sie den folgenden PowerShell-Befehl aus, um die Überwachung in Office 365 zu aktivieren.

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    Es wird eine Meldung angezeigt, die besagt, dass es bis zu 60 Minuten dauern kann, bis die Änderung wirksam wird.
  
## <a name="turn-off-auditing"></a>Deaktivieren der Überwachung

Sie müssen Exchange Online PowerShell verwenden, um die Überwachung zu deaktivieren.
  
1. [Herstellen einer Verbindung mit Exchange Online mithilfe der Remote-PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

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
