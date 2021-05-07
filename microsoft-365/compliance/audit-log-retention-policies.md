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
ms.openlocfilehash: 2ac95d9bb9c13b6bf0c0e31d17b4fb46c30c492a
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51687358"
---
# <a name="manage-audit-log-retention-policies"></a>Verwalten von Aufbewahrungsrichtlinien für Überwachungsprotokolle

Sie können Aufbewahrungsrichtlinien für Überwachungsprotokolle im Security & Compliance Center erstellen und verwalten. Aufbewahrungsrichtlinien für Überwachungsprotokolle sind Bestandteil der neuen erweiterten Überwachungsfunktionen in Microsoft 365. Mit einer Aufbewahrungsrichtlinie für Überwachungsprotokolle können Sie festlegen, wie lange Überwachungsprotokolle in Ihrer Organisation aufbewahrt werden sollen. Sie können Überwachungsprotokolle bis zu 10 Jahre lang aufbewahren. Sie können Richtlinien nach folgenden Kriterien erstellen:

- Alle Aktivitäten in einem oder mehreren Microsoft 365-Diensten

- Bestimmte Aktivitäten (in einem Microsoft 365-Dienst), die von allen Benutzern oder von bestimmten Benutzern ausgeführt werden

- Eine Prioritätsstufe, die angibt, welche Richtlinie Vorrang hat, wenn es in Ihrer Organisation mehrere Richtlinien gibt

## <a name="default-audit-log-retention-policy"></a>Standardmäßige Aufbewahrungsrichtlinie für Überwachungsprotokolle

Die erweiterte Überwachung in Microsoft 365 stellt eine Standardaufbewahrungsrichtlinie für Überwachungsprotokolle für alle Organisationen bereit. Diese Richtlinie bewahrt alle Exchange Online-, SharePoint Online-, OneDrive for Business- und Azure Active Directory-Überwachungsdatensätze für ein Jahr auf. Diese Standardrichtlinie bewahrt Überwachungsdatensätze auf, die den Wert **Exchange**, **SharePoint**, **OneDrive** oder **AzureActiveDirectory** für die Eigenschaft **Workload** (der Dienst, in dem die Aktivität aufgetreten ist) enthalten. Die Standardrichtlinie kann nicht geändert werden. Im Abschnitt [Weitere Informationen](#more-information) in diesem Artikel finden Sie eine Liste der Datensatztypen für die einzelnen Workloads, die in der Standardrichtlinie enthalten sind.

> [!NOTE]
> Die Standardrichtlinie zur Aufbewahrung von Überwachungsprotokollen gilt nur für Überwachungsdatensätze für Aktivitäten, die von Benutzern durchgeführt werden, denen eine Office 365- oder Microsoft 365 E5-Lizenz zugewiesen ist, oder die über eine Microsoft 365 E5 Compliance- oder E5 eDiscovery- und Überwachungs-Add-on-Lizenz verfügen. Wenn Sie Nicht-E5-Benutzer oder Gastbenutzer in Ihrer Organisation haben, werden die entsprechenden Audit-Aufzeichnungen 90 Tage lang aufbewahrt.

## <a name="before-you-create-an-audit-log-retention-policy"></a>Vor dem Erstellen einer Aufbewahrungsrichtlinie für Überwachungsprotokolle

- Ihnen muss die Rolle "Organisationskonfiguration" im Security & Compliance Center zugewiesen sein, um eine Aufbewahrungsrichtlinie für Überwachungsprotokolle erstellen oder ändern zu können.

- In Ihrer Organisation kann es maximal 50 Aufbewahrungsrichtlinien für Überwachungsprotokolle geben.

- Um ein Überwachungsprotokoll länger als 90 Tage (und bis zu 1 Jahr) aufzubewahren, muss dem Benutzer, der das Überwachungsprotokoll erstellt (durch Ausführen einer geprüften Aktivität), eine Office 365 E5- oder Microsoft 365 E5-Lizenz zugewiesen werden oder er muss über eine Microsoft 365 E5 Compliance- oder E5 eDiscovery und Audit-Add-On-Lizenz verfügen. Um Überwachungsprotokolle 10 Jahre lang aufzubewahren, muss dem Benutzer, der das Überwachungsprotokoll erstellt, zusätzlich zu einer E5-Lizenz eine 10-Jahres-Zusatzlizenz zur Aufbewahrung von Überwachungsprotokollen zugewiesen werden.

- Alle benutzerdefinierten (von Ihrer Organisation erstellten) Aufbewahrungsrichtlinien für Überwachungsprotokolle haben Vorrang vor der Standardaufbewahrungsrichtlinie. Wenn Sie beispielsweise eine Aufbewahrungsrichtlinie für Überwachungsprotokolle für Exchange-Postfachaktivitäten erstellen, die einen Aufbewahrungszeitraum von weniger als einem Jahr vorsieht, werden die Überwachungsdatensätze für Exchange-Postfachaktivitäten für die in der benutzerdefinierten Richtlinie festgelegte kürzere Dauer aufbewahrt.

## <a name="create-an-audit-log-retention-policy"></a>Erstellen einer Aufbewahrungsrichtlinie für Überwachungsprotokolle

1. Wechseln Sie zu [https://compliance.microsoft.com](https://compliance.microsoft.com), und melden Sie sich mit dem Benutzerkonto an, dem auf der Berechtigungsseite im Security & Compliance Center die Rolle "Organisationskonfiguration" zugewiesen ist.

2. Klicken Sie im linken Bereich des Microsoft 365 Compliance Center auf **Alle anzeigen** und dann auf **Überwachung**.

3. Klicken Sie auf die Registerkarte **Aufbewahrungsrichtlinien für die Überwachung**.

4. Klicken Sie auf **Aufbewahrungsrichtlinie für die Überwachung erstellen**, und füllen Sie dann auf der Flyoutseite die folgenden Felder aus:

    ![Flyoutseite "Neue Aufbewahrungsrichtlinie für die Überwachung"](../media/CreateAuditLogRetentionPolicy.png)

   1. **Richtlinienname:** Der Name der Aufbewahrungsrichtlinie für Überwachungsprotokolle. Dieser Name muss in Ihrer Organisation eindeutig sein und kann nach dem Erstellen der Richtlinie nicht mehr geändert werden.

   2. **Beschreibung:** Optional, aber hilfreich, um Informationen zur Richtlinie bereitzustellen, z. B. den Datensatztyp oder den Workload, die in der Richtlinie angegebenen Benutzer sowie die Dauer.

   3. **Benutzer:** Wählen Sie einen oder mehrere Benutzer aus, auf die die Richtlinie angewendet werden soll. Wenn Sie dieses Feld leer lassen, gilt die Richtlinie für alle Benutzer. Wenn Sie die **Datensatzart** leer lassen, müssen Sie einen Benutzer auswählen.

   4. **Datensatzart:** die Art des Überwachungsdatensatzes, auf den sich die Richtlinie bezieht Wenn Sie diese Eigenschaft leer lassen, müssen Sie im Feld **Benutzer** einen Benutzer auswählen. Sie können einen einzelnen oder mehrere Datensatztypen auswählen:

   - Wenn Sie einen einzelnen Datensatztyp auswählen, wird das Feld **Aktivitäten** dynamisch angezeigt. Mithilfe der Drop-down-Liste können Sie Aktivitäten des ausgewählten Datensatztyps auswählen, auf die die Richtlinie angewendet werden soll. Wenn Sie keine bestimmten Aktivitäten auswählen, gilt die Richtlinie für alle Aktivitäten des ausgewählten Datensatztyps.

   - Wenn Sie mehrere Datensatztypen auswählen, können Sie keine Aktivitäten auswählen. Die Richtlinie wird auf alle Aktivitäten des ausgewählten Datensatztyps angewendet.

   5. **Dauer:** die Zeitdauer, wie lange die Überwachungsprotokolle aufbewahrt werden, die den Kriterien der Richtlinie entsprechen

   6. **Priorität:** Dieser Wert bestimmt die Reihenfolge, in der Aufbewahrungsrichtlinien für Überwachungsprotokolle in Ihrer Organisation angewandt werden. Ein höherer Wert weist auf eine höhere Priorität hin.  So würde beispielsweise eine Richtlinie mit einem Prioritätswert von **5** Vorrang vor einer Richtlinie mit einem Prioritätswert von **0** haben. Wie zuvor erläutert, hat jede benutzerdefinierte Aufbewahrungsrichtlinie für Überwachungsprotokolle Vorrang vor der Standardrichtlinie für Ihre Organisation.

5. Klicken Sie auf **Speichern**, um die neue Aufbewahrungsrichtlinie für Überwachungsprotokolle zu erstellen.

   Die neue Richtlinie wird in der Liste auf der Registerkarte **Aufbewahrungsrichtlinien für die Überwachung** angezeigt.

## <a name="manage-audit-log-retention-policies"></a>Verwalten von Aufbewahrungsrichtlinien für Überwachungsprotokolle

Aufbewahrungsrichtlinien für Überwachungsprotokolle werden auf der Registerkarte **Aufbewahrungsrichtlinien für die Überwachung** (auch als *Dashboard* bezeichnet) angezeigt. Über das Dashboard können Sie Aufbewahrungsrichtlinien anzeigen, bearbeiten und löschen.

### <a name="view-policies-in-the-dashboard"></a>Anzeigen von Richtlinien im Dashboard

Aufbewahrungsrichtlinien für Überwachungsprotokolle werden im Dashboard aufgelistet. Ein Vorteil des Anzeigens von Richtlinien im Dashboard besteht darin, dass Sie auf die Spalte **Priorität** klicken können, damit die Richtlinien nach der Priorität aufgelistet werden, mit der sie angewendet werden. Wie zuvor erläutert, steht ein höherer Wert für eine höhere Priorität.

![Spalte "Priorität" im Dashboard für "Aufbewahrungsrichtlinien für die Überwachung"](../media/AuditLogRetentionDashboardPriority.png)

Sie können außerdem eine Richtlinie auswählen, damit deren Einstellungen auf der Flyoutseite angezeigt werden.

> [!NOTE]
> Die standardmäßige Aufbewahrungsrichtlinie für Überwachungsprotokolle für Ihre Organisation wird nicht im Dashboard angezeigt.

### <a name="edit-policies-in-the-dashboard"></a>Bearbeiten von Richtlinien im Dashboard

Wenn Sie eine Richtlinie bearbeiten möchten, klicken Sie darauf, um die Flyoutseite anzuzeigen. Sie können eine oder mehrere Einstellungen ändern und die Änderungen dann speichern.


> [!IMPORTANT]
> Wenn Sie das Cmdlet **New-UnifiedAuditLogRetentionPolicy** verwenden, können Sie eine Aufbewahrungsrichtlinie für Überwachungsprotokolle für Datensatztypen oder Aktivitäten erstellen, die im Tool zum **Erstellen von Aufbewahrungsrichtlinien für die Überwachung** im Dashboard nicht verfügbar sind. In diesem Fall werden Sie nicht in der Lage sein, die Richtlinie über das Dashboard für **Aufbewahrungsrichtlinien für die Überwachung** zu bearbeiten (beispielsweise die Aufbewahrungsdauer ändern oder Aktivitäten hinzufügen oder entfernen).  Sie können die Richtlinie im Compliance Center nur anzeigen oder löschen. Um die Richtlinie zu ändern, müssen Sie das Cmdlet [Set-UnifiedAuditLogRetentionPolicy](/powershell/module/exchange/set-unifiedauditlogretentionpolicy) im PowerShell des Security & Compliance Centers verwenden.<br/><br/>**Tipp:** Oben auf der Flyoutseite wird eine Nachricht zu Richtlinien angezeigt, die mittels PowerShell bearbeitet werden müssen.

### <a name="delete-policies-in-the-dashboard"></a>Löschen von Richtlinien im Dashboard

Klicken Sie zum Löschen einer Richtlinie auf das **Löschsymbol**![Löschsymbol ](../media/92a9f8e0-d469-48da-addb-69365e7ffb6f.jpg), und bestätigen Sie dann, dass Sie die Richtlinie tatsächlich löschen möchten. Die Richtlinie wird aus dem Dashboard entfernt, es kann jedoch bis zu 30 Minuten dauern, bis die Richtlinie aus Ihrer Organisation entfernt wurde.

## <a name="create-and-manage-audit-log-retention-policies-in-powershell"></a>Erstellen und Verwalten von Aufbewahrungsrichtlinien für Überwachungsprotokolle in PowerShell

Aufbewahrungsrichtlinien für Überwachungsprotokolle können auch mithilfe von Security & Compliance Center PowerShell erstellt und verwaltet werden. Ein Grund für die Verwendung von PowerShell ist das Erstellen einer Richtlinie für einen Datensatztyp oder eine Aktivität, der bzw. die auf der Benutzeroberfläche nicht verfügbar ist.

### <a name="create-an-audit-log-retention-policy-in-powershell"></a>Erstellen einer Aufbewahrungsrichtlinie für Überwachungsprotokolle in PowerShell

Gehen Sie folgendermaßen vor, um eine Aufbewahrungsrichtlinie für Überwachungsprotokolle in PowerShell zu erstellen:

1. [Stellen Sie eine Verbindung mit der Security & Compliance Center PowerShell her](/powershell/exchange/connect-to-scc-powershell).

2. Führen Sie zum Erstellen einer neuen Aufbewahrungsrichtlinie den folgenden Befehl aus:

   ```powershell
   New-UnifiedAuditLogRetentionPolicy -Name "Microsoft Teams Audit Policy" -Description "One year retention policy for all Microsoft Teams activities" -RecordTypes MicrosoftTeams -RetentionDuration TenYears -Priority 100
   ```

    In diesem Beispiel wird eine Aufbewahrungsrichtlinie für Überwachungsprotokolle namens "Microsoft Teams Audit Policy" mit diesen Einstellungen erstellt:

   - Eine Beschreibung der Richtlinie.

   - Bewahrt alle Microsoft Teams-Aktivitäten auf (gemäß der Definition durch den *RecordType*-Parameter).

   - Bewahrt Microsoft Teams-Überwachungsprotokolle 10 Jahre lang auf.

   - Eine Priorität von 100.

Hier ist ein weiteres Beispiel für das Erstellen einer Aufbewahrungsrichtlinie für Überwachungsprotokolle. Diese Richtlinie bewahrt Überwachungsprotokolle für die Aktivität "Benutzer angemeldet" für den Benutzer admin@contoso.onmicrosoft.com für sechs Monate auf.

```powershell
New-UnifiedAuditLogRetentionPolicy -Name "SixMonth retention for admin logons" -RecordTypes AzureActiveDirectoryStsLogon -Operations UserLoggedIn -UserIds admin@contoso.onmicrosoft.com -RetentionDuration SixMonths -Priority 25
```

Weitere Informationen finden Sie unter [New-UnifiedAuditLogRetentionPolicy-](/powershell/module/exchange/new-unifiedauditlogretentionpolicy).

### <a name="view-policies-in-powershell"></a>Anzeigen von Richtlinien in PowerShell

Verwenden Sie das Cmdlet [Get-UnifiedAuditLogRetentionPolicy](/powershell/module/exchange/get-unifiedauditlogretentionpolicy) in Security & Compliance Center PowerShell, um Aufbewahrungsrichtlinien für Überwachungsprotokolle anzuzeigen.

Hier ist ein Beispielbefehl zum Anzeigen der Einstellungen für alle Aufbewahrungsrichtlinien für Überwachungsprotokolle in Ihrer Organisation. Mit diesem Befehl werden die Richtlinien von der höchsten bis zur niedrigsten Priorität sortiert.

```powershell
Get-UnifiedAuditLogRetentionPolicy | Sort-Object -Property Priority -Descending | FL Priority,Name,Description,RecordTypes,Operations,UserIds,RetentionDuration
```

> [!NOTE]
> Das Cmdlet **Get-UnifiedAuditLogRetentionPolicy** gibt nicht die standardmäßige Aufbewahrungsrichtlinie für Überwachungsprotokolle für Ihre Organisation zurück.

### <a name="edit-policies-in-powershell"></a>Bearbeiten von Richtlinien in PowerShell

Verwenden Sie das Cmdlet [Set-UnifiedAuditLogRetentionPolicy](/powershell/module/exchange/set-unifiedauditlogretentionpolicy) in Security & Compliance Center PowerShell, um eine bestehende Aufbewahrungsrichtlinie für Überwachungsprotokolle zu bearbeiten.

### <a name="delete-policies-in-powershell"></a>Löschen von Richtlinien in PowerShell

Verwenden Sie das Cmdlet [Remove-UnifiedAuditLogRetentionPolicy](/powershell/module/exchange/remove-unifiedauditlogretentionpolicy) in Security & Compliance Center PowerShell, um eine Aufbewahrungsrichtlinie für Überwachungsprotokolle zu löschen. Es kann bis zu 30 Minuten dauern, bis die Richtlinie aus Ihrer Organisation entfernt wurde.

## <a name="more-information"></a>Weitere Informationen

Wie bereits erwähnt, werden Überwachungsdatensätze für Vorgänge in Azure Active Directory, Exchange Online, SharePoint Online und OneDrive for Business standardmäßig für ein Jahr aufbewahrt. In der folgenden Tabelle sind alle Datensatztypen (für jeden dieser Dienste) aufgelistet, die in der standardmäßigen Aufbewahrungsrichtlinie für Überwachungsprotokolle enthalten sind. Dies bedeutet, dass Überwachungsprotokolle für jeden Vorgang mit diesem Datensatztyp für ein Jahr aufbewahrt werden, es sei denn, eine benutzerdefinierte Aufbewahrungsrichtlinie für Überwachungsprotokolle hat Vorrang in Hinblick auf einen bestimmten Datensatztyp, Vorgang oder Benutzer. Der Enumerationswert (der als Wert für die RecordType-Eigenschaft in einem Überwachungsdatensatz angezeigt wird) ist in Klammern angezeigt.

|AzureActiveDirectory |Exchange  |SharePoint oder OneDrive|
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
