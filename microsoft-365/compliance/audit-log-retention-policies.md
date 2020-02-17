---
title: Verwalten von Aufbewahrungsrichtlinien für Überwachungsprotokolle
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Aufbewahrungsrichtlinien für Überwachungsprotokolle sind Bestandteil der neuen erweiterten Überwachungsfunktionen in Microsoft 365. Mit einer Aufbewahrungsrichtlinie für Überwachungsprotokolle können Sie festlegen, wie lange Überwachungsprotokolle in Ihrer Organisation aufbewahrt werden sollen.
ms.openlocfilehash: 5e2a1e328888a6aadf5c3057bbe7882ac0f72fbe
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42079210"
---
# <a name="manage-audit-log-retention-policies"></a>Verwalten von Aufbewahrungsrichtlinien für Überwachungsprotokolle

Sie können Aufbewahrungsrichtlinien für Überwachungsprotokolle im Security & Compliance Center erstellen und verwalten. Aufbewahrungsrichtlinien für Überwachungsprotokolle sind Bestandteil der neuen erweiterten Überwachungsfunktionen in Microsoft 365. Mit einer Aufbewahrungsrichtlinie für Überwachungsprotokolle können Sie festlegen, wie lange Überwachungsprotokolle in Ihrer Organisation aufbewahrt werden sollen. Überwachungsprotokolle können bis zu einem Jahr aufbewahrt werden. Sie können Richtlinien nach folgenden Kriterien erstellen:

- Alle Aktivitäten in einem oder mehreren Microsoft 365-Diensten

- Bestimmte Aktivitäten (in einem bestimmten Dienst), die von allen Benutzern oder von bestimmten Benutzern ausgeführt werden

- Eine Prioritätsstufe, die angibt, welche Richtlinie Vorrang hat, wenn es in Ihrer Organisation mehrere Richtlinien gibt

## <a name="default-audit-log-retention-policy"></a>Standardmäßige Aufbewahrungsrichtlinie für Überwachungsprotokolle

Die erweiterte Überwachung in Microsoft 365 stellt eine Standardaufbewahrungsrichtlinie für Überwachungsprotokolle für alle Organisationen bereit. Diese Richtlinie bewahrt alle Exchange-, SharePoint- und Azure Active Directory-Überwachungsdatensätze für ein Jahr auf. Diese Standardrichtlinie bewahrt Überwachungsdatensätze auf, die den Wert **AzureActiveDirectory**, **Exchange**oder **SharePoint** für die **Workload**-Eigenschaft (der Dienst, in dem die Aktivität aufgetreten ist) enthalten. Die Standardrichtlinie kann nicht geändert werden. Im Abschnitt [Weitere Informationen](#more-information) in diesem Artikel finden Sie eine Liste der Datensatztypen für die einzelnen Workloads, die in der Standardrichtlinie enthalten sind.

> [!NOTE]
> Die standardmäßige Aufbewahrungsrichtlinie für Überwachungsprotokolle gilt nur für Überwachungseinträge für Aktivitäten, die von Benutzern ausgeführt werden, denen eine Office 365- oder Microsoft 365 E5-Lizenz zugewiesen wurde, oder die über eine Microsoft 365 E5 Compliance-Add-on-Lizenz verfügen. Wenn es in Ihrer Organisation nicht-E5-Benutzer gibt, werden die entsprechenden Überwachungsdatensätze für 90 Tage aufbewahrt.

## <a name="before-you-begin"></a>Vorabinformationen

- Ihnen muss die Rolle "Organisationskonfiguration" im Security & Compliance Center zugewiesen sein, um eine Aufbewahrungsrichtlinie für Überwachungsprotokolle erstellen oder ändern zu können.

- In Ihrer Organisation kann es maximal 50 Aufbewahrungsrichtlinien für Überwachungsprotokolle geben.

- Wenn Sie ein Überwachungsprotokoll länger als 90 Tage aufbewahren möchten, muss der Benutzer, der das Überwachungsprotokoll generiert hat, über eine Lizenz für Office 365, für Microsoft 365 E5 oder über eine Microsoft 365 E5 Compliance-Add-on-Lizenz verfügen.

- Alle benutzerdefinierten (von Ihrer Organisation erstellen) Aufbewahrungsrichtlinien für Überwachungsprotokolle haben Vorrang vor der Standardaufbewahrungsrichtlinie. Wenn Sie beispielsweise eine Aufbewahrungsrichtlinie für Überwachungsprotokolle für Exchange-Postfachaktivitäten erstellen, die einen Aufbewahrungszeitraum von weniger als einem Jahr vorsieht, werden die Überwachungsdatensätze für Exchange-Postfachaktivitäten für die in der benutzerdefinierten Richtlinie festgelegte kürzere Dauer aufbewahrt.

## <a name="create-an-audit-log-retention-policy-in-the-security--compliance-center"></a>Erstellen einer Aufbewahrungsrichtlinie für Überwachungsprotokolle im Security & Compliance Center

1. Wechseln Sie zu [https://protection.office.com](https://protection.office.com), und melden Sie sich mit dem Benutzerkonto an, dem die Rolle "Organisationskonfiguration"im Security & Compliance Center zugewiesen ist. 

2. Klicken Sie im Security & Compliance Center im linken Bereich auf **Suchen**  > **Überwachungsprotokollsuche**.

    Die Seite **Überwachungsprotokollsuche** wird angezeigt.

    ![Die Seite "Überwachungsprotokollsuche"](../media/AuditLogRetentionPolicy1.png)

3. Klicken Sie auf **Neue Aufbewahrungsrichtlinie**, und führen Sie dann auf der Flayoutseite die folgenden Felder aus:

    ![Flyoutseite "Aufbewahrungsrichtlinien für Überwachungsprotokolle"](../media/AuditLogRetentionPolicy2.png)

   a. **Name:** Der Name der Aufbewahrungsrichtlinie für Überwachungsprotokolle. Dieser Name muss in Ihrer Organisation eindeutig sein.
   
   b. **Beschreibung:** Optional, aber hilfreich, um Informationen zur Richtlinie bereitzustellen, z. B. den Datensatztyp oder den Workload, die in der Richtlinie angegebenen Benutzer sowie die Dauer.

   c. **Datensatztypen:** Der Überwachungsdatensatztyp, für den die Richtlinie gilt. Wenn Sie mehr als einen Datensatztyp auswählen, können Sie keine Aktivitäten auswählen, da die Richtlinie für alle Aktivitäten der ausgewählten Datensatztypen gilt. Wenn Sie diese Eigenschaft leer lassen, müssen Sie außerdem einen Benutzer im Feld **Benutzer** auswählen.

   d. **Aktivitäten:** In diesem Feld können Sie Aktivitäten aus dem ausgewählten Datensatztyp auswählen. Sie können bestimmte Aktivitäten auswählen, auf die die Richtlinie angewendet werden soll. Wenn Sie keine bestimmten Aktivitäten auswählen, gilt die Richtlinie für alle Aktivitäten des ausgewählten Datensatztyps.

   e. **Benutzer:** Wählen Sie einen oder mehrere Benutzer aus, auf die die Richtlinie angewendet werden soll. Wenn Sie dieses Feld leer lassen, gilt die Richtlinie für alle Benutzer. Wenn Sie das Feld **Datensatztypen** leer lassen, müssen Sie einen Benutzer auswählen.

   f. **Dauer:** Wie lange die Überwachungsprotokolle aufbewahrt werden, die den Kriterien der Richtlinie entsprechen.

   g. **Priorität:** Dieser Wert bestimmt die Reihenfolge, in der Aufbewahrungsrichtlinien für Überwachungsprotokolle in Ihrer Organisation angewandt werden. Ein höherer Wert weist auf eine höhere Priorität hin.  So würde beispielsweise eine Richtlinie mit einem Prioritätswert von **5** Vorrang vor einer Richtlinie mit einem Prioritätswert von **0**haben. Wie zuvor erläutert, hat jede benutzerdefinierte Aufbewahrungsrichtlinie für Überwachungsprotokolle Vorrang vor der Standardrichtlinie für Ihre Organisation.

6. Klicken Sie auf **Speichern**, um die neue Aufbewahrungsrichtlinie für Überwachungsprotokolle zu erstellen. 

Zurzeit gibt es keine Bestätigung, dass die Aufbewahrungsrichtlinie erfolgreich erstellt wurde. Im nächsten Abschnitt erfahren Sie, wie Sie die Eigenschaften von Aufbewahrungsrichtlinien für Überwachungsprotokolle einsehen können.

## <a name="create-an-audit-log-retention-policy-in-powershell"></a>Erstellen einer Aufbewahrungsrichtlinie für Überwachungsprotokolle in PowerShell

Aufbewahrungsrichtlinien für Überwachungsprotokolle können auch mithilfe von Office 365 Security & Compliance Center PowerShell erstellt werden. 

1. [Stellen Sie eine Verbindung mit Security & Compliance Center PowerShell her](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).

2. Führen Sie zum Erstellen einer neuen Aufbewahrungsrichtlinie den folgenden Befehl aus: 

   ```powershell
   New-UnifiedAuditLogRetentionPolicy -Name "Microsoft Teams Audit Policy" -Description "One year retention policy for all Microsoft Teams activities" -RecordTypes MicrosoftTeams -RetentionDuration TwelveMonths -Priority 100
   ```
    
    In diesem Beispiel wird eine Aufbewahrungsrichtlinie für Überwachungsprotokolle namens "Microsoft Teams Audit Policy" mit diesen Einstellungen erstellt:

   - Eine Beschreibung der Richtlinie.

   - Bewahrt alle Microsoft Teams-Aktivitäten auf (gemäß der Definition durch den *RecordType*-Parameter).

   - Bewahrt Microsoft Teams-Überwachungsprotokolle ein Jahr lang auf.

   - Eine Priorität von 100.

Hier ist ein weiteres Beispiel für das Erstellen einer Aufbewahrungsrichtlinie für Überwachungsprotokolle. Diese Richtlinie bewahrt Überwachungsprotokolle für die Aktivität "Benutzer angemeldet" für den Benutzer admin@contoso.onmicrosoft.com für sechs Monate auf.

```powershell
New-UnifiedAuditLogRetentionPolicy -Name "SixMonth retention for admin logons" -RecordTypes AzureActiveDirectoryStsLogon -Operations UserLoggedIn -UserIds admin@contoso.onmicrosoft.com -RetentionDuration SixMonths -Priority 25
```

Weitere Informationen finden Sie unter [New-UnifiedAuditLogRetentionPolicy-](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/new-unifiedauditlogretentionpolicy).

## <a name="view-audit-log-retention-policies"></a>Anzeigen von Aufbewahrungsrichtlinien für Überwachungsprotokolle

Zurzeit können benutzerdefinierte Aufbewahrungsrichtlinien für Überwachungsprotokolle nur mithilfe des Cmdlets **Get-UnifiedAuditRetentionPolicy** in Security & Compliance Center PowerShell angezeigt werden. Hier ist ein Beispielbefehl zum Anzeigen der Einstellungen (die Sie im vorherigen Schritt konfiguriert haben) für die Aufbewahrungsrichtlinien für Überwachungsprotokolle in Ihrer Organisation. Mit diesem Befehl werden die Richtlinien von der höchsten bis zur niedrigsten Priorität sortiert.

```powershell
Get-UnifiedAuditLogRetentionPolicy | Sort-Object -Property Priority -Descending | FL Priority,Name,Description,RecordTypes,Operations,UserIds,RetentionDuration
```

> [!NOTE]
> Zurzeit gibt das Cmdlet **Get-UnifiedAuditLogRetentionPolicy** nicht die Standardrichtlinie für Überwachungsprotokolle für Ihre Organisation zurück.

Weitere Informationen finden Sie unter [Get-UnifiedAuditLogRetentionPolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/get-unifiedauditlogretentionpolicy).

## <a name="more-information"></a>Weitere Informationen

- Verwenden Sie das Cmdlet **Set-UnifiedAuditLogRetentionPolicy** in Security & Compliance Center PowerShell, um eine bestehende Aufbewahrungsrichtlinie für Überwachungsprotokolle zu ändern. Weitere Informationen finden Sie unter [Set-UnifiedAuditLogRetentionPolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/set-unifiedauditlogretentionpolicy).

- Verwenden Sie das Cmdlet **Remove-UnifiedAuditLogRetentionPolicy** in Security & Compliance Center PowerShell, um eine Aufbewahrungsrichtlinie für Überwachungsprotokolle zu löschen. Es kann bis zu 30 Minuten dauern, bis die Richtlinie vollständig entfernt wurde. Weitere Informationen finden Sie unter [Remove-UnifiedAuditLogRetentionPolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/remove-unifiedauditlogretentionpolicy).

- Wie bereits erwähnt, werden Überwachungseinträge für Vorgänge in Azure Active Directory, Exchange und SharePoint für ein Jahr aufbewahrt. In der folgenden Tabelle sind alle Datensatztypen (für jeden dieser Dienste) aufgelistet, die in der standardmäßigen Aufbewahrungsrichtlinie für Überwachungsprotokolle enthalten sind. Dies bedeutet, dass Überwachungsprotokolle für jeden Vorgang mit diesem Datensatztyp für ein Jahr aufbewahrt werden, es sei denn, eine benutzerdefinierte Aufbewahrungsrichtlinie für Überwachungsprotokolle hat Vorrang in Hinblick auf einen bestimmten Datensatztyp, Vorgang oder Benutzer. Der Enumerationswert (der als Wert für die RecordType-Eigenschaft in einem Überwachungsdatensatz angezeigt wird) ist in Klammern angezeigt.

   |AzureActiveDirectory |Exchange  |SharePoint|
   |:---------|:---------|:---------|
   |AzureActiveDirectory (8)|ExchangeAdmin (1)|ComplianceDLPSharePoint (11)|
   |AzureActiveDirectoryAccountLogon (9)|ExchangeItem (2)|ComplianceDLPSharePointClassification (33)|
   |AzureActiveDirectoryStsLogon (15)|Campaign (62)|Project (35)|
   ||ComplianceDLPExchange (13)|SharePoint (4)|
   ||ComplianceSupervisionExchange (68)|SharePointCommentOperation (37)|
   ||CustomerKeyServiceEncryption (69)|SharePointContentTypeOperation (55)|
   ||ExchangeAggregatedOperation (19)|SharePointFieldOperation (56)|
   ||ExchangeItemAggregated (50)|SharePointFileOperation (6)|
   ||ExchangeItemGroup (3)|SharePointListOperation (36)|
   ||InformationBarrierPolicyApplication (53)|SharePointSharingOperation (14)|
   ||||
