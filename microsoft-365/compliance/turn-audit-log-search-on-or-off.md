---
title: Aktivieren oder Deaktivieren der Überwachungsprotokollsuche
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
description: Vorgehensweise aktivieren oder Deaktivieren der Überwachungsprotokoll-Suchfunktion im Security & Compliance Center, um die Fähigkeit von Administratoren zum Durchsuchen des Überwachungsprotokolls zu aktivieren oder zu deaktivieren.
ms.openlocfilehash: 4571c90c4fa680acd8925e83e32ffcf07de7d626
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819135"
---
# <a name="turn-audit-log-search-on-or-off"></a>Aktivieren oder Deaktivieren der Überwachungsprotokollsuche

Sie (oder ein anderer Administrator) müssen die Überwachungsprotokollierung aktivieren, bevor Sie mit der Durchsuchung des Überwachungsprotokolls beginnen können. Wenn die Überwachungsprotokoll Suche im Security & Compliance Center aktiviert ist, werden Benutzer-und Administratoraktivitäten aus Ihrer Organisation im Überwachungsprotokoll aufgezeichnet und für 90 Tage und bis zu einem Jahr in Abhängigkeit von der Benutzerlizenz gespeichert. Ihre Organisation hat jedoch möglicherweise Gründe dafür, dass Überwachungsprotokolldaten nicht aufgezeichnet und aufbewahrt werden sollen. In diesen Fällen kann ein globaler Administrator beschließen, die Überwachung in Microsoft 365 zu deaktivieren.

> [!IMPORTANT]
> Wenn Sie die Überwachungsprotokoll Suche in Microsoft 365 deaktivieren, können Sie die Office 365-Verwaltungs Aktivitäts-API oder Azure Sentinel nicht verwenden, um auf Überwachungsdaten für Ihre Organisation zuzugreifen. Wenn Sie die Überwachungsprotokoll Suche deaktivieren, indem Sie die Schritte in diesem Artikel durchführen, werden keine Ergebnisse zurückgegeben, wenn Sie das Überwachungsprotokoll mithilfe des Security & Compliance Center oder durch Ausführen des Cmdlets **Search-UnifiedAuditLog** in Exchange Online PowerShell durchsuchen. Dies bedeutet auch, dass Überwachungsprotokolle nicht über die Office 365-Verwaltungs Aktivitäts-API oder Azure Sentinel verfügbar sind.
  
## <a name="before-you-turn-audit-log-search-on-or-off"></a>Vor dem Aktivieren oder Deaktivieren der Überwachungsprotokoll Suche

- Sie müssen in Exchange Online der Rolle "Überwachungsprotokolle" zugewiesen sein, um die Überwachungsprotokoll Suche in Ihrer Microsoft 365-Organisation ein-oder auszuschalten. Diese Rolle wird standardmäßig der Rollengruppe Compliance Management und Organisationsverwaltung auf der Seite **Berechtigungen** im Exchange Admin Center zugewiesen. Globale Administratoren in Microsoft 365 sind Mitglieder der Rollengruppe "Organisationsverwaltung" in Exchange Online. 
    
    > [!NOTE]
    > Benutzern müssen Berechtigungen in Exchange Online zugewiesen sein, um die Überwachungsprotokoll Suche ein-oder auszuschalten. Wenn Sie den Benutzern die Rolle "Überwachungsprotokolle" auf der Seite **Berechtigungen** im Security & Compliance Center zuweisen, kann die Überwachungsprotokoll Suche nicht aktiviert oder deaktiviert werden. Dies liegt daran, dass das zugrunde liegende Cmdlet ein Exchange Online-Cmdlet ist. 
    
- Eine Schritt-für-Schritt-Anleitung zum Durchsuchen des Überwachungsprotokolls finden Sie unter [Durchsuchen des Überwachungsprotokolls im Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md). Weitere Informationen zur Verwaltungs Aktivitäts-API von Microsoft 365 finden Sie unter [Erste Schritte mit Microsoft 365-Verwaltungs-APIs](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).
    
## <a name="turn-on-audit-log-search"></a>Aktivieren der Überwachungsprotokoll Suche

Sie können das Security & Compliance Center oder PowerShell verwenden, um die Überwachungsprotokoll Suche in Microsoft 365 zu aktivieren. Es kann mehrere Stunden dauern, nachdem Sie die Überwachungsprotokoll Suche aktiviert haben, bevor Sie Ergebnisse zurückgeben können, wenn Sie das Überwachungsprotokoll durchsuchen. Sie müssen der Rolle "Überwachungsprotokolle" in Exchange Online zugewiesen sein, um die Überwachungsprotokoll Suche zu aktivieren.
  
### <a name="use-the-security--compliance-center-to-turn-on-audit-log-search"></a>Aktivieren der Überwachungsprotokoll Suche mithilfe des Security & Compliance Centers

1. [Wechseln Sie zum Security & Compliance Center](https://protection.office.com) , und melden Sie sich an.

2. Wechseln Sie im Security & Compliance Center zu **Such** \> **Überwachungsprotokoll-Suche**.

   Ein Banner wird angezeigt, das besagt, dass die Überwachung aktiviert werden muss, um Benutzer-und Administratoraktivitäten aufzuzeichnen.

3. Klicken Sie auf **Überwachung aktivieren**.

    ![Klicken Sie auf Überwachung aktivieren](../media/39a9d35f-88d0-4bbe-a962-0be2f838e2bf.png)
  
    Das Banner wird aktualisiert, um zu sagen, dass das Überwachungsprotokoll vorbereitet wird und dass Sie in wenigen Stunden nach Benutzer-und Administratoraktivitäten suchen können.

### <a name="use-powershell-to-turn-on-audit-log-search"></a>Aktivieren der Überwachungsprotokoll Suche mithilfe von PowerShell

1. [Herstellen einer Verbindung mit Exchange Online mithilfe der Remote-PowerShell](https://go.microsoft.com/fwlink/p/?LinkID=396554).

2. Führen Sie den folgenden PowerShell-Befehl aus, um die Überwachungsprotokoll Suche in Office 365 zu aktivieren.

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    Es wird eine Meldung angezeigt, die besagt, dass es bis zu 60 Minuten dauern kann, bis die Änderung wirksam wird.
  
## <a name="turn-off-audit-log-search"></a>Deaktivieren der Überwachungsprotokoll Suche

Sie müssen Remote-PowerShell verwenden, die mit Ihrer Exchange Online Organisation verbunden ist, um die Überwachungsprotokoll Suche zu deaktivieren. Ähnlich wie beim Aktivieren der Überwachungsprotokoll Suche müssen Sie der Rolle "Überwachungsprotokolle" in Exchange Online zugewiesen sein, um die Überwachungsprotokoll Suche zu deaktivieren.
  
1. [Herstellen einer Verbindung mit Exchange Online mithilfe der Remote-PowerShell](https://go.microsoft.com/fwlink/p/?LinkID=396554).

2. Führen Sie den folgenden PowerShell-Befehl aus, um die Überwachungsprotokoll Suche in Office 365 zu deaktivieren.

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. Überprüfen Sie nach einer Weile, ob die Überwachungsprotokoll Suche deaktiviert (disabled) ist. Sie können auf zwei Arten vorgehen:

    - Führen Sie in PowerShell den folgenden Befehl aus:

    ```powershell
    Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
    ```

      Der Wert von `False` für die _UnifiedAuditLogIngestionEnabled_ -Eigenschaft gibt an, dass die Überwachungsprotokoll Suche deaktiviert ist. 

    - Wechseln Sie im [Security & Compliance Center](https://protection.office.com)zu **Such** \> **Überwachungsprotokoll-Suche**.

      Ein Banner wird angezeigt, das besagt, dass die Überwachung aktiviert werden muss, um Benutzer-und Administratoraktivitäten aufzuzeichnen.