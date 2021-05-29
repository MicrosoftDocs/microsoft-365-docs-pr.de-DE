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
description: Aktivieren oder Deaktivieren des Überwachungsprotokollsuchfeatures im Microsoft 365 Compliance Center, um die Möglichkeit von Administratoren zum Durchsuchen des Überwachungsprotokolls zu aktivieren oder zu deaktivieren.
ms.openlocfilehash: 457f453b001f71a095bc60932c8e0cebf46aa7b1
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706664"
---
# <a name="turn-auditing-on-or-off"></a>Aktivieren oder Deaktivieren der Überwachung

Die Überwachungsprotokollierung ist für Microsoft 365- und Office 365 Enterprise-Organisationen standardmäßig aktiviert. Das schließt Organisationen mit E3/G3- oder E5/G5-Abonnements ein. Wenn die Überwachung im Compliance Center aktiviert ist, werden Benutzer- und Administratoraktivitäten aus Ihrer Organisation im Überwachungsprotokoll aufgezeichnet und für 90 Tage und je nach der den Benutzern zugewiesenen Lizenz bis zu einem Jahr aufbewahrt. Ihre Organisation hat jedoch möglicherweise Gründe, die Überwachungsprotokolldaten nicht aufzeichnen und beibehalten zu möchten. In diesen Fällen kann ein globaler Administrator die Überwachung in einem Microsoft 365.

> [!IMPORTANT]
> Wenn Sie die Überwachung in Microsoft 365 deaktivieren, können Sie die Office 365 Management Activity API oder Azure Sentinel nicht verwenden, um auf Überwachungsdaten für Ihre Organisation zu zugreifen. Wenn Sie die Überwachung deaktivieren, indem Sie die Schritte in diesem Artikel ausführen, werden keine Ergebnisse zurückgegeben, wenn Sie das Überwachungsprotokoll mithilfe des Security & Compliance Center durchsuchen oder das **Cmdlet Search-UnifiedAuditLog** in Exchange Online PowerShell ausführen. Dies bedeutet auch, dass Überwachungsprotokolle nicht über die Office 365 Management Activity API oder Azure Sentinel verfügbar sind.
  
## <a name="before-you-turn-auditing-on-or-off"></a>Vor dem Aktivieren oder Deaktivieren der Überwachung

- Ihnen muss die Rolle Überwachungsprotokolle in Exchange Online zugewiesen werden, um die Überwachung in Ihrer Organisation Microsoft 365 aktivieren oder deaktivieren. Diese Rolle wird standardmäßig den Rollengruppen Complianceverwaltung und  Organisationsverwaltung auf der Seite Berechtigungen im Exchange zugewiesen. Globale Administratoren in Microsoft 365 mitglieder der Rollengruppe Organisationsverwaltung in Exchange Online. 

    > [!NOTE]
    > Benutzern müssen berechtigungen in den Exchange Online, um die Überwachung ein- oder auszuschalten. Wenn Sie Benutzern die Rolle  Überwachungsprotokolle auf der Seite Berechtigungen im Security & Compliance Center zuweisen, können sie die Überwachung nicht aktivieren oder deaktivieren. Dies liegt daran, dass das zugrunde liegende Cmdlet ein Exchange Online PowerShell-Cmdlet ist. 

- Schrittweise Anweisungen zum Durchsuchen des Überwachungsprotokolls finden Sie unter Durchsuchen des Überwachungsprotokolls im [Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md). Weitere Informationen zur Microsoft 365 Management Activity API finden Sie unter [Get started with Microsoft 365 Management APIs](/office/office-365-management-api/get-started-with-office-365-management-apis).

- Um zu überprüfen, ob die Überwachung aktiviert ist, können Sie den folgenden Befehl in Exchange Online PowerShell ausführen:

    ```powershell
    Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
    ```

    Der Wert  `True` der  _UnifiedAuditLogIngestionEnabled-Eigenschaft_ gibt an, dass die Überwachung aktiviert ist. 

## <a name="turn-on-auditing"></a>Aktivieren der Überwachung

Wenn die Überwachung für Ihre Organisation nicht aktiviert ist, können Sie sie im Compliance Center oder mithilfe Exchange Online PowerShell aktivieren. Es kann mehrere Stunden dauern, bis Sie die Überwachung aktiviert haben, bevor Sie ergebnisse zurückgeben können, wenn Sie das Überwachungsprotokoll durchsuchen.
  
### <a name="use-the-compliance-center-to-turn-on-auditing"></a>Aktivieren der Überwachung mithilfe des Compliance Centers

1. Gehen Sie auf <https://compliance.microsoft.com>, und melden Sie sich an.

2. Klicken Sie im linken Navigationsbereich Microsoft 365 Compliance Center auf **Alle** anzeigen, und klicken Sie dann auf **Überwachung**.

   Wenn die Überwachung für Ihre Organisation nicht aktiviert ist, wird ein Banner mit der Aufforderung angezeigt, Benutzer- und Administratoraktivitäten zu erfassen.

   ![Banner auf der Seite "Überwachung"](../media/AuditingBanner.png)

3. Klicken Sie **auf das Banner Start recording user and admin activity.**

   Es kann bis zu 60 Minuten dauern, bis die Änderung wirksam wird.

### <a name="use-powershell-to-turn-on-auditing"></a>Aktivieren der Überwachung mithilfe von PowerShell

1. [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)

2. Führen Sie den folgenden PowerShell-Befehl aus, um die Überwachung in Office 365.

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    Es wird eine Meldung angezeigt, dass es bis zu 60 Minuten dauern kann, bis die Änderung wirksam wird.
  
## <a name="turn-off-auditing"></a>Deaktivieren der Überwachung

Sie müssen die Exchange Online PowerShell verwenden, um die Überwachung zu deaktivieren.
  
1. [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)

2. Führen Sie den folgenden PowerShell-Befehl aus, um die Überwachung zu deaktivieren.

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. Überprüfen Sie nach einer Weile, ob die Überwachung deaktiviert (deaktiviert) ist. Sie können auf zwei Arten vorgehen:

    - Führen Exchange Online in powerShell den folgenden Befehl aus:

      ```powershell
      Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
      ```

      Der Wert  `False` der  _UnifiedAuditLogIngestionEnabled-Eigenschaft_ gibt an, dass die Überwachung deaktiviert ist.

    - Wechseln Sie zur **Seite Überwachung** im Microsoft 365 Compliance Center.

      Wenn die Überwachung für Ihre Organisation nicht aktiviert ist, wird ein Banner mit der Aufforderung angezeigt, Benutzer- und Administratoraktivitäten zu erfassen.
