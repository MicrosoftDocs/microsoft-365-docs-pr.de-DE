---
title: Aktivieren oder Deaktivieren der Office 365-Überwachungsprotokollsuche
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
description: 'Sie können das Feature Überwachungsprotokoll Suche im Security #a0 Compliance Center aktivieren. Wenn Sie Ihre Meinung ändern, können Sie jederzeit deaktivieren. Wenn die Überwachungsprotokoll Suche deaktiviert ist, können Administratoren das Office 365 Überwachungsprotokoll nicht nach Benutzer-und Administratoraktivitäten in Ihrer Organisation durchsuchen.'
ms.openlocfilehash: 4e382c9916a9460d2c837a336607734427416a1a
ms.sourcegitcommit: 1d376287f6c1bf5174873e89ed4bf7bb15bc13f6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2019
ms.locfileid: "38686279"
---
# <a name="turn-office-365-audit-log-search-on-or-off"></a>Aktivieren oder Deaktivieren der Office 365-Überwachungsprotokollsuche

Sie (oder ein anderer Administrator) müssen die Überwachungsprotokollierung aktivieren, bevor Sie mit der Suche im Office 365 Überwachungsprotokoll beginnen können. Wenn die Überwachungsprotokoll Suche im Security #a0 Compliance Center aktiviert ist, werden Benutzer-und Administratoraktivitäten aus Ihrer Organisation im Überwachungsprotokoll aufgezeichnet und für 90 Tage aufbewahrt. Ihre Organisation möchte jedoch möglicherweise keine Überwachungsprotokolldaten aufzeichnen und aufbewahren. Oder Sie verwenden möglicherweise eine Siem-Anwendung (Security Information and Event Management) eines Drittanbieters, um auf Ihre Überwachungsdaten zuzugreifen. In diesen Fällen kann ein globaler Administrator die Überwachungsprotokoll Suche in Office 365 deaktivieren.
  
## <a name="before-you-begin"></a>Bevor Sie beginnen:

- Sie müssen die Rolle Überwachungsprotokolle in Exchange Online zugewiesen haben, um die Überwachungsprotokoll Suche in Ihrer Office 365 Organisation ein-oder auszuschalten. Diese Rolle wird standardmäßig der Rollengruppe Compliance Management und Organisationsverwaltung auf der Seite **Berechtigungen** im Exchange Admin Center zugewiesen. Globale Administratoren in Office 365 sind Mitglieder der Rollengruppe "Organisationsverwaltung" in Exchange Online. 
    
    > [!IMPORTANT]
    > Benutzern müssen Berechtigungen in Exchange Online zugewiesen sein, um die Überwachungsprotokoll Suche ein-oder auszuschalten. Wenn Sie den Benutzern die Rolle "Überwachungsprotokolle" auf der Seite **Berechtigungen** im Security #a0 Compliance Center zuweisen, kann die Überwachungsprotokoll Suche nicht aktiviert oder deaktiviert werden. Dies liegt daran, dass das zugrunde liegende Cmdlet ein Exchange Online-Cmdlet ist. 
  
- Wenn Sie die Überwachungsprotokoll Suche in Office 365 deaktivieren, können Sie die Office 365 Verwaltungs Aktivitäts-API nicht verwenden, um auf Überwachungsdaten für Ihre Organisation zuzugreifen. Wenn Sie die Überwachungsprotokoll Suche deaktivieren, indem Sie die Schritte in diesem Artikel durchführen, werden keine Ergebnisse zurückgegeben, wenn Sie das Überwachungsprotokoll mithilfe des Security #a0 Compliance Center oder durch Ausführen des Cmdlets **Search-UnifiedAuditLog** in Exchange Online PowerShell durchsuchen. Dies bedeutet auch, dass Ihre Überwachungsprotokolle nicht über die Office 365 Verwaltungs Aktivitäts-API verfügbar sind.  
    
- Eine Schritt-für-Schritt-Anleitung zum Durchsuchen des Office 365 Überwachungsprotokolls finden Sie unter [Durchsuchen des Überwachungsprotokolls im Security #a0 Compliance Center](search-the-audit-log-in-security-and-compliance.md).
    
## <a name="turn-on-audit-log-search"></a>Aktivieren der Überwachungsprotokoll Suche

Sie können das Security #a0 Compliance Center oder die PowerShell verwenden, um die Überwachungsprotokoll Suche in Office 365 zu aktivieren. Es kann mehrere Stunden dauern, nachdem Sie die Überwachungsprotokoll Suche aktiviert haben, bevor Sie Ergebnisse zurückgeben können, wenn Sie das Überwachungsprotokoll durchsuchen. Sie müssen der Rolle "Überwachungsprotokolle" in Exchange Online zugewiesen sein, um die Überwachungsprotokoll Suche zu aktivieren.
  
### <a name="use-the-security--compliance-center-to-turn-on-audit-log-search"></a>Aktivieren der Überwachungsprotokoll Suche mithilfe des Security #a0 Compliance Centers

1. Wechseln Sie im Security #a0 Compliance Center zu **Such** \> **Überwachungsprotokoll-Suche**.
    
   Ein Banner wird angezeigt, das besagt, dass die Überwachung aktiviert werden muss, um Benutzer-und Administratoraktivitäten aufzuzeichnen.

2. Klicken Sie auf **Überwachung aktivieren**.
    
    ![Klicken Sie auf Überwachung aktivieren](media/39a9d35f-88d0-4bbe-a962-0be2f838e2bf.png)
  
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
    
    - Wechseln Sie im Security #a0 Compliance Center zu **Such** \> **Überwachungsprotokoll-Suche**.
    
      Ein Banner wird angezeigt, das besagt, dass die Überwachung aktiviert werden muss, um Benutzer-und Administratoraktivitäten aufzuzeichnen.
