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
description: Aktivieren oder Deaktivieren des Überwachungsprotokollsuchfeatures im Security & Compliance Center zum Aktivieren oder Deaktivieren der Fähigkeit von Administratoren, das Überwachungsprotokoll zu durchsuchen.
ms.openlocfilehash: 1f3da9671b9e5287d715a438a11b0a0eef164584
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/25/2021
ms.locfileid: "49976328"
---
# <a name="turn-audit-log-search-on-or-off"></a>Aktivieren oder Deaktivieren der Überwachungsprotokollsuche

Die Überwachungsprotokollierung ist für Microsoft 365- und Office 365-Unternehmensorganisationen standardmäßig aktiviert. Dazu gehören Organisationen mit E3/G3- oder E5/G5-Abonnements. Wenn die Überwachungsprotokollsuche im Compliance Center aktiviert ist, werden Benutzer- und Administratoraktivitäten aus Ihrer Organisation im Überwachungsprotokoll aufgezeichnet und für 90 Tage und bis zu ein Jahr in Abhängigkeit von der den Benutzern zugewiesenen Lizenz aufbewahrt. Möglicherweise hat Ihre Organisation jedoch Gründe, die Überwachungsprotokolldaten nicht aufzeichnen und beibehalten zu wollen. In diesen Fällen kann ein globaler Administrator die Überwachung in Microsoft 365 deaktivieren.

> [!IMPORTANT]
> Wenn Sie die Überwachungsprotokollsuche in Microsoft 365 deaktivieren, können Sie nicht die Office 365-Verwaltungsaktivitäts-API oder Azure Sentinel verwenden, um auf Überwachungsdaten für Ihre Organisation zu zugreifen. Wenn Sie die Überwachungsprotokollsuche deaktivieren, indem Sie die Schritte in diesem Artikel ausführen, werden keine Ergebnisse zurückgegeben, wenn Sie das Überwachungsprotokoll mit dem Security & Compliance Center durchsuchen oder das **Cmdlet Search-UnifiedAuditLog** in Exchange Online PowerShell ausführen. Dies bedeutet auch, dass Überwachungsprotokolle nicht über die Office 365-Verwaltungsaktivitäts-API oder Azure Sentinel verfügbar sind.
  
## <a name="before-you-turn-audit-log-search-on-or-off"></a>Vor dem Aktivieren oder Deaktivieren der Überwachungsprotokollsuche

- Ihnen muss die Rolle "Überwachungsprotokolle" in Exchange Online zugewiesen sein, um die Überwachungsprotokollsuche in Ihrer Microsoft 365-Organisation zu aktivieren oder zu deaktivieren. Diese Rolle wird standardmäßig den Rollengruppen "Verwaltung der  Richtlinieneinzugsverwaltung" und "Organisationsverwaltung" auf der Seite "Berechtigungen" im Exchange Admin Center zugewiesen. Globale Administratoren in Microsoft 365 sind Mitglieder der Rollengruppe "Organisationsverwaltung" in Exchange Online. 
    
    > [!NOTE]
    > Benutzern müssen in Exchange Online Berechtigungen zugewiesen werden, um die Überwachungsprotokollsuche zu aktivieren oder zu deaktivieren. Wenn Sie Benutzern die Rolle  "Überwachungsprotokolle" auf der Seite "Berechtigungen" im Security & Compliance Center zuweisen, können sie die Überwachungsprotokollsuche nicht aktivieren oder deaktivieren. Der Grund dafür ist, dass das zugrunde liegende Cmdlet ein Exchange Online -PowerShell-Cmdlet ist. 
    
- Schrittweise Anweisungen zum Durchsuchen des Überwachungsprotokolls finden Sie unter Durchsuchen des Überwachungsprotokolls im [Security & Compliance Center.](search-the-audit-log-in-security-and-compliance.md) Weitere Informationen zur Microsoft 365-Verwaltungsaktivitäts-API finden Sie unter ["Erste Schritte mit Microsoft 365-Verwaltungs-APIs".](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)

- Um zu überprüfen, ob die Überwachungsprotokollsuche aktiviert ist, können Sie den folgenden Befehl in Exchange Online PowerShell ausführen:

    ```powershell
    Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
    ```

    Der Wert der  `True`  _Eigenschaft "UnifiedAuditLogIngestionEnabled"_ gibt an, dass die Überwachungsprotokollsuche aktiviert ist. 
    
## <a name="turn-on-audit-log-search"></a>Aktivieren der Überwachungsprotokollsuche

Wenn die Überwachungsprotokollsuche für Ihre Organisation nicht aktiviert ist, können Sie sie im Compliance Center oder mithilfe von Exchange Online PowerShell aktivieren. Es kann mehrere Stunden dauern, bis Sie die Überwachungsprotokollsuche aktivieren, bevor Sie Ergebnisse zurückgeben können, wenn Sie das Überwachungsprotokoll durchsuchen.
  
### <a name="use-the-compliance-center-to-turn-on-audit-log-search"></a>Aktivieren der Überwachungsprotokollsuche mithilfe des Compliance Centers

1. [Wechseln Sie zum Compliance Center,](https://protection.office.com) und melden Sie sich an.

2. Wechseln Sie im Compliance Center zur Suche  >  **nach Überwachungsprotokollen.**

   Wenn die Überwachungsprotokollsuche für Ihre Organisation nicht aktiviert ist, wird ein Banner mit der Meldung angezeigt, dass die Überwachung aktiviert werden muss, um Benutzer- und Administratoraktivitäten zu protokollieren.

3. Klicken **Sie auf "Überwachung aktivieren".**

    ![Klicken Sie auf "Überwachung aktivieren".](../media/39a9d35f-88d0-4bbe-a962-0be2f838e2bf.png)
  
    Das Banner wird aktualisiert, um zu sagen, dass das Überwachungsprotokoll vorbereitet wird und Sie nach Benutzer- und Administratoraktivitäten in ein paar Stunden suchen können.

### <a name="use-powershell-to-turn-on-audit-log-search"></a>Aktivieren der Überwachungsprotokollsuche mithilfe von PowerShell

1. [Herstellen einer Verbindung mit Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkID=396554)

2. Führen Sie den folgenden PowerShell-Befehl aus, um die Überwachungsprotokollsuche in Office 365 zu aktivieren.

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    Es wird eine Meldung angezeigt, dass es bis zu 60 Minuten dauern kann, bis die Änderung wirksam wird.
  
## <a name="turn-off-audit-log-search"></a>Deaktivieren der Überwachungsprotokollsuche

Sie müssen Exchange Online PowerShell verwenden, um die Überwachungsprotokollsuche zu deaktivieren.
  
1. [Herstellen einer Verbindung mit Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkID=396554)

2. Führen Sie den folgenden PowerShell-Befehl aus, um die Überwachungsprotokollsuche zu deaktivieren.

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. Stellen Sie nach einer Weile sicher, dass die Überwachungsprotokollsuche deaktiviert ist. Sie können auf zwei Arten vorgehen:

    - Führen Sie in Exchange Online PowerShell den folgenden Befehl aus:

      ```powershell
      Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
      ```

      Der Wert der  `False`  _Eigenschaft "UnifiedAuditLogIngestionEnabled"_ gibt an, dass die Überwachungsprotokollsuche deaktiviert ist. 

    - Wechseln Sie [im Compliance Center](https://protection.office.com)zur Suche **nach** \> **Überwachungsprotokollen.**

      Es wird ein Banner mit der Meldung angezeigt, dass die Überwachung aktiviert werden muss, um Benutzer- und Administratoraktivitäten aufzeichnen zu können.
