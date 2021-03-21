---
title: Anzeigen von Microsoft 365-Lizenzen und -Diensten mit PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Ent_Office_Other
- O365ITProTrain
- LIL_Placement
- PowerShell
ms.assetid: bb5260a9-a6a3-4f34-b19a-06c6699f6723
description: Erläutert die Verwendung von PowerShell zum Anzeigen von Informationen zu Den Lizenzierungsplänen, Diensten und Lizenzen, die in Ihrer Microsoft 365-Organisation verfügbar sind.
ms.openlocfilehash: 08f48301001ee6a40318428f3310eab8b0d0a351
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924636"
---
# <a name="view-microsoft-365-licenses-and-services-with-powershell"></a>Anzeigen von Microsoft 365-Lizenzen und -Diensten mit PowerShell

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Jedes Microsoft 365-Abonnement besteht aus den folgenden Elementen:

- **Lizenzierungspläne** Diese werden auch als Lizenzpläne oder Microsoft 365-Pläne bezeichnet. Lizenzierungspläne definieren die Microsoft 365-Dienste, die Benutzern zur Verfügung stehen. Ihr Microsoft 365-Abonnement kann mehrere Lizenzierungspläne enthalten. Ein Beispiel für einen Lizenzierungsplan wäre Microsoft 365 E3.
    
- **Dienste** Diese werden auch als Dienstpläne bezeichnet. Dienste sind die Microsoft 365-Produkte, -Features und -Funktionen, die in jedem Lizenzierungsplan verfügbar sind, z. B. Exchange Online und Microsoft 365 Apps for Enterprise (zuvor Office 365 ProPlus genannt). Benutzern können mehrere verschiedene Lizenzen aus unterschiedlichen Lizenzierungsplänen zugewiesen sein, über die sie Zugriff auf unterschiedliche Dienste haben.
    
- **Lizenzen** Jeder Lizenzierungsplan enthält die Anzahl der lizenzen, die Sie erworben haben. Sie weisen Benutzern Lizenzen zu, damit sie die microsoft 365-Dienste verwenden können, die im Lizenzierungsplan definiert sind. Jedes Benutzerkonto benötigt mindestens eine Lizenz aus einem Lizenzierungsplan, damit sie sich bei Microsoft 365 anmelden und die Dienste nutzen können.
    
Sie können PowerShell für Microsoft 365 verwenden, um Details zu den verfügbaren Lizenzierungsplänen, Lizenzen und Diensten in Ihrer Microsoft 365-Organisation anzuzeigen. Weitere Informationen zu den Produkten, Features und Diensten, die in verschiedenen Office 365-Abonnements verfügbar sind, finden Sie unter [Office 365 Plan Options](/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options).


## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Verwenden der Azure Active Directory PowerShell für Graph-Module

Stellen Sie [zunächst eine Verbindung mit Ihrem Microsoft 365-Mandanten herzustellen.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
  
Führen Sie den folgenden Befehl aus, um Zusammenfassungsinformationen zu Ihren aktuellen Lizenzierungsplänen und den verfügbaren Lizenzen für jeden Plan anzeigen zu können:
  
```powershell
Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
```

Die Ergebnisse enthalten:
  
- **SkuPartNumber:** Zeigt die verfügbaren Lizenzierungspläne für Ihre Organisation an. `ENTERPRISEPACK` ist z. B. der Name des Lizenzplans für Office 365 Enterprise E3.
    
- **Enabled:**: Gibt die Anzahl der Lizenzen an, die Sie im Rahmen eines spezifischen Lizenzierungsplans erworben haben.
    
- **ConsumedUnits**: Gibt die Anzahl der Lizenzen an, die Sie Benutzern aus einem bestimmten Lizenzierungsplan zugewiesen haben.
    
Um Details zu den Microsoft 365-Diensten anzuzeigen, die in allen Lizenzplänen verfügbar sind, zeigen Sie zunächst eine Liste Ihrer Lizenzpläne an.

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

Speichern Sie dann die Informationen zu den Lizenzplänen in einer Variablen.

```powershell
$licenses = Get-AzureADSubscribedSku
```

Zeigen Sie die Dienste in einem spezifischen Lizenzplan an.

```powershell
$licenses[<index>].ServicePlans
```

\<index> ist eine ganze Zahl, die die Zeilennummer des Lizenzplans aus der Anzeige des Befehls `Get-AzureADSubscribedSku | Select SkuPartNumber` minus 1 angibt.

Wenn die Anzeige des `Get-AzureADSubscribedSku | Select SkuPartNumber`-Befehls z.B. folgendermaßen lautet:

```powershell
SkuPartNumber
-------------
WIN10_VDA_E5
EMSPREMIUM
ENTERPRISEPREMIUM
FLOW_FREE
```

Lautet der Befehl zum Anzeigen der Dienste für den Plan ENTERPRISEPREMIUM folgendermaßen:

```powershell
$licenses[2].ServicePlans
```

ENTERPRISEPREMIUM ist die dritte Zeile. Aus diesem Grund wird der Indexwert mit (3 - 1) oder 2 angegeben.

Eine vollständige Liste von Lizenzplänen (auch bezeichnet als Produktnamen), deren enthaltenen Serviceplänen und die entsprechenden Anzeigenamen finden Sie unter [Produktnamen und Serviceplanbezeichner für die Lizenzierung](/azure/active-directory/users-groups-roles/licensing-service-plan-reference).

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Verwenden des Microsoft Azure Active Directory-Moduls für Windows PowerShell

Stellen Sie [zunächst eine Verbindung mit Ihrem Microsoft 365-Mandanten herzustellen.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

>[!Note]
>Ein PowerShell-Skript steht zur Verfügung, das die in diesem Thema erläuterten Verfahren automatisiert. Insbesondere können Sie mit dem Skript Dienste in Ihrer Microsoft 365-Organisation, einschließlich Sway, anzeigen und deaktivieren. Weitere Informationen finden Sie unter [Disable access to Sway with PowerShell](disable-access-to-sway-with-microsoft-365-powershell.md).
>
    
Führen Sie den folgenden Befehl aus, um eine Übersicht über Ihre aktuellen Lizenzierungspläne und die in den einzelnen Plänen verfügbaren Lizenzen anzuzeigen:
  
```powershell
Get-MsolAccountSku
```

>[!Note]
>PowerShell Core unterstützt nicht das Microsoft Azure Active Directory-Modul für Windows PowerShell und Cmdlets mit **Msol** im Namen. Um diese Cmdlets weiterhin verwenden zu können, müssen Sie sie über Windows PowerShell ausführen.
>

Die Ergebnisse enthalten die folgenden Informationen:
  
- **AccountSkuId:** Zeigen Sie die verfügbaren Lizenzierungspläne für Ihre Organisation mithilfe der Syntax `<CompanyName>:<LicensingPlan>` an.  _\<CompanyName>_ ist der Wert, den Sie bei der Registrierung bei Microsoft 365 angegeben haben und für Ihre Organisation eindeutig sind. Der _\<LicensingPlan>_ Wert ist für alle gleich. Im Wert ist beispielsweise der Firmenname , und der Name des Lizenzierungsplans , der der `litwareinc:ENTERPRISEPACK`  `litwareinc`  `ENTERPRISEPACK` Systemname für Office 365 Enterprise E3 ist.
    
- **ActiveUnits**: Gibt die Anzahl der Lizenzen an, die Sie im Rahmen eines spezifischen Lizenzierungsplans erworben haben.
    
- **WarningUnits**: Gibt die Anzahl der Lizenzen in einem Lizenzierungsplan an, die Sie nicht verlängert haben und die nach der 30-tägigen Toleranzperiode ablaufen werden.
    
- **ConsumedUnits**: Gibt die Anzahl der Lizenzen an, die Sie Benutzern aus einem bestimmten Lizenzierungsplan zugewiesen haben.
    
Führen Sie den folgenden Befehl aus, um Details zu den Microsoft 365-Diensten anzuzeigen, die in allen Lizenzplänen verfügbar sind:
  
```powershell
Get-MsolAccountSku | Select -ExpandProperty ServiceStatus
```

In der folgenden Tabelle sind die Microsoft 365-Dienstpläne und deren Anzeigenamen für die gängigsten Dienste aufgeführt. Ihre individuelle Serviceplanliste sieht möglicherweise anders aus. 
  
|**Dienstplan**|**Beschreibung**|
|:-----|:-----|
| `SWAY` <br/> |Sway  <br/> |
| `TEAMS1` <br/> |Microsoft Teams  <br/> |
| `YAMMER_ENTERPRISE` <br/> |Yammer  <br/> |
| `RMS_S_ENTERPRISE` <br/> |Azure-Rechteverwaltung (Rights Management, RMS)  <br/> |
| `OFFICESUBSCRIPTION` <br/> |Microsoft 365 Apps for Enterprise *(zuvor Office 365 ProPlus genannt)*  <br/> |
| `MCOSTANDARD` <br/> |Skype for Business Online  <br/> |
| `SHAREPOINTWAC` <br/> |Office  <br/> |
| `SHAREPOINTENTERPRISE` <br/> |SharePoint Online  <br/> |
| `EXCHANGE_S_ENTERPRISE` <br/> |Exchange Online Plan 2  <br/> |
   
Eine vollständige Liste von Lizenzplänen (auch bezeichnet als Produktnamen), deren enthaltenen Serviceplänen und die entsprechenden Anzeigenamen finden Sie unter [Produktnamen und Serviceplanbezeichner für die Lizenzierung](/azure/active-directory/users-groups-roles/licensing-service-plan-reference).

Verwenden Sie die folgende Syntax, um Details zu den Microsoft 365-Diensten anzuzeigen, die in einem bestimmten Lizenzierungsplan verfügbar sind.
  
```powershell
(Get-MsolAccountSku | where {$_.AccountSkuId -eq "<AccountSkuId>"}).ServiceStatus
```

In diesem Beispiel werden die Dienste gezeigt, die im Lizenzplan litwareinc:ENTERPRISEPACK (Office 365 Enterprise E3) verfügbar sind.
  
```powershell
(Get-MsolAccountSku | where {$_.AccountSkuId -eq "litwareinc:ENTERPRISEPACK"}).ServiceStatus
```

## <a name="see-also"></a>Siehe auch

[Verwalten von Microsoft 365-Benutzerkonten, -Lizenzen und -Gruppen mit PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Verwalten von Microsoft 365 mit PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Erste Schritte mit PowerShell für Microsoft 365](getting-started-with-microsoft-365-powershell.md)