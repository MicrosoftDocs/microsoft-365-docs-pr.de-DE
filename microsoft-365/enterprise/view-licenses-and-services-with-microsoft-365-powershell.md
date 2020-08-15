---
title: Anzeigen von Microsoft 365-Lizenzen und-Diensten mit PowerShell
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
description: Erläutert die Verwendung von PowerShell zum Anzeigen von Informationen zu den Lizenzierungs Plänen, Diensten und Lizenzen, die in Ihrer Microsoft 365-Organisation zur Verfügung stehen.
ms.openlocfilehash: 3275a513de3c114076e792ab6c5ef86b1413571c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690526"
---
# <a name="view-microsoft-365-licenses-and-services-with-powershell"></a>Anzeigen von Microsoft 365-Lizenzen und-Diensten mit PowerShell

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Jedes Microsoft 365-Abonnement besteht aus den folgenden Elementen:

- **Lizenzierungs Pläne** Diese werden auch als Lizenz Pläne oder Microsoft 365-Pläne bezeichnet. Lizenzierungs Pläne definieren die Microsoft 365-Dienste, die Benutzern zur Verfügung stehen. Ihr Microsoft 365-Abonnement enthält möglicherweise mehrere Lizenzierungs Pläne. Ein Beispiel für einen Lizenzierungs Plan wäre Microsoft 365 E3.
    
- **Dienste** Diese werden auch als Dienstpläne bezeichnet. Dienste sind die Microsoft 365-Produkte,-Features und-Funktionen, die in den einzelnen Lizenzierungs Plänen zur Verfügung stehen, beispielsweise Exchange Online und Microsoft 365 apps for Enterprise (zuvor mit dem Namen Office 365 ProPlus). Benutzern können mehrere verschiedene Lizenzen aus unterschiedlichen Lizenzierungsplänen zugewiesen sein, über die sie Zugriff auf unterschiedliche Dienste haben.
    
- **Lizenzen** Jeder Lizenzierungs Plan enthält die Anzahl der Lizenzen, die Sie erworben haben. Sie weisen Benutzern Lizenzen zu, damit diese die Microsoft 365-Dienste verwenden können, die im Lizenzierungs Plan definiert sind. Für jedes Benutzerkonto ist mindestens eine Lizenz aus einem Lizenzierungs Plan erforderlich, damit Sie sich bei Microsoft 365 anmelden und die Dienste nutzen können.
    
Sie können PowerShell für Microsoft 365 verwenden, um Details über die verfügbaren Lizenzierungs Pläne, Lizenzen und Dienste in Ihrer Microsoft 365-Organisation anzuzeigen. Weitere Informationen zu den Produkten, Features und Diensten, die in verschiedenen Office 365-Abonnements zur Verfügung stehen, finden Sie unter [Office 365 Plan Options](https://go.microsoft.com/fwlink/p/?LinkId=691147).


## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Verwenden der Azure Active Directory PowerShell für Graph-Module

Stellen Sie zunächst [eine Verbindung mit Ihrem Microsoft 365-Mandanten her](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).
  
Führen Sie den folgenden Befehl aus, um zusammenfassende Informationen zu Ihren aktuellen Lizenzierungs Plänen und den verfügbaren Lizenzen für jeden Plan anzuzeigen:
  
```powershell
Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
```

Die Ergebnisse enthalten:
  
- **SkuPartNumber:** Zeigt die verfügbaren Lizenzierungspläne für Ihre Organisation an. `ENTERPRISEPACK` ist z. B. der Name des Lizenzplans für Office 365 Enterprise E3.
    
- **Enabled:**: Gibt die Anzahl der Lizenzen an, die Sie im Rahmen eines spezifischen Lizenzierungsplans erworben haben.
    
- **ConsumedUnits**: Gibt die Anzahl der Lizenzen an, die Sie Benutzern aus einem bestimmten Lizenzierungsplan zugewiesen haben.
    
Um Details zu den Microsoft 365-Diensten anzuzeigen, die in allen ihren Lizenz Plänen zur Verfügung stehen, zeigen Sie zunächst eine Liste Ihrer Lizenz Pläne an.

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

\<index> ist eine ganze Zahl, die die Zeilennummer des Lizenz Plans von der Anzeige des `Get-AzureADSubscribedSku | Select SkuPartNumber` Befehls abzüglich 1 angibt.

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

Eine vollständige Liste von Lizenzplänen (auch bezeichnet als Produktnamen), deren enthaltenen Serviceplänen und die entsprechenden Anzeigenamen finden Sie unter [Produktnamen und Serviceplanbezeichner für die Lizenzierung](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference).

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Verwenden des Microsoft Azure Active Directory-Moduls für Windows PowerShell

Stellen Sie zunächst [eine Verbindung mit Ihrem Microsoft 365-Mandanten her](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).

>[!Note]
>Ein PowerShell-Skript steht zur Verfügung, das die in diesem Thema erläuterten Verfahren automatisiert. Insbesondere können Sie mit dem Skriptdienste in Ihrer Microsoft 365-Organisation anzeigen und deaktivieren, einschließlich Sway. Weitere Informationen finden Sie unter [Deaktivieren des Zugriffs auf Sway mit PowerShell](disable-access-to-sway-with-microsoft-365-powershell.md).
>
    
Führen Sie den folgenden Befehl aus, um eine Übersicht über Ihre aktuellen Lizenzierungspläne und die in den einzelnen Plänen verfügbaren Lizenzen anzuzeigen:
  
```powershell
Get-MsolAccountSku
```

>[!Note]
>PowerShell Core unterstützt nicht das Microsoft Azure Active Directory-Modul für Windows PowerShell und Cmdlets mit **Msol** im Namen. Um diese Cmdlets weiterhin verwenden zu können, müssen Sie sie über Windows PowerShell ausführen.
>

Die Ergebnisse enthalten die folgenden Informationen:
  
- **AccountSkuId:** Zeigen Sie die verfügbaren Lizenzierungs Pläne für Ihre Organisation mithilfe der Syntax an `<CompanyName>:<LicensingPlan>` .  _\<CompanyName>_ ist der Wert, den Sie bei der Registrierung in Microsoft 365 angegeben haben und der für Ihre Organisation eindeutig ist. Der _\<LicensingPlan>_ Wert ist für alle Benutzer gleich. Beispielsweise ist in dem Wert `litwareinc:ENTERPRISEPACK` der Name des Unternehmens  `litwareinc` und der Name des Lizenzierungs Plans, bei dem  `ENTERPRISEPACK` es sich um den Systemnamen für Office 365 Enterprise E3 handelt.
    
- **ActiveUnits**: Gibt die Anzahl der Lizenzen an, die Sie im Rahmen eines spezifischen Lizenzierungsplans erworben haben.
    
- **WarningUnits**: Gibt die Anzahl der Lizenzen in einem Lizenzierungsplan an, die Sie nicht verlängert haben und die nach der 30-tägigen Toleranzperiode ablaufen werden.
    
- **ConsumedUnits**: Gibt die Anzahl der Lizenzen an, die Sie Benutzern aus einem bestimmten Lizenzierungsplan zugewiesen haben.
    
Um Details zu den Microsoft 365-Diensten anzuzeigen, die in allen ihren Lizenz Plänen verfügbar sind, führen Sie den folgenden Befehl aus:
  
```powershell
Get-MsolAccountSku | Select -ExpandProperty ServiceStatus
```

In der folgenden Tabelle sind die Microsoft 365-Dienstpläne und ihre Anzeigenamen für die am häufigsten verwendeten Dienste aufgeführt. Ihre individuelle Serviceplanliste sieht möglicherweise anders aus. 
  
|**Dienstplan**|**Beschreibung**|
|:-----|:-----|
| `SWAY` <br/> |Sway  <br/> |
| `TEAMS1` <br/> |Microsoft Teams  <br/> |
| `YAMMER_ENTERPRISE` <br/> |Yammer  <br/> |
| `RMS_S_ENTERPRISE` <br/> |Azure-Rechteverwaltung (Rights Management, RMS)  <br/> |
| `OFFICESUBSCRIPTION` <br/> |Microsoft 365-Apps für Unternehmen *(zuvor mit dem Namen Office 365 ProPlus)*  <br/> |
| `MCOSTANDARD` <br/> |Skype for Business Online  <br/> |
| `SHAREPOINTWAC` <br/> |Office  <br/> |
| `SHAREPOINTENTERPRISE` <br/> |SharePoint Online  <br/> |
| `EXCHANGE_S_ENTERPRISE` <br/> |Exchange Online Plan 2  <br/> |
   
Eine vollständige Liste von Lizenzplänen (auch bezeichnet als Produktnamen), deren enthaltenen Serviceplänen und die entsprechenden Anzeigenamen finden Sie unter [Produktnamen und Serviceplanbezeichner für die Lizenzierung](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference).

Verwenden Sie die folgende Syntax, um Details zu den Microsoft 365-Diensten anzuzeigen, die in einem bestimmten Lizenzierungs Plan verfügbar sind.
  
```powershell
(Get-MsolAccountSku | where {$_.AccountSkuId -eq "<AccountSkuId>"}).ServiceStatus
```

Dieses Beispiel zeigt die Dienste, die im Lizenzierungs Plan litwareinc: ENTERPRISEPACK (Office 365 Enterprise E3) verfügbar sind.
  
```powershell
(Get-MsolAccountSku | where {$_.AccountSkuId -eq "litwareinc:ENTERPRISEPACK"}).ServiceStatus
```

## <a name="see-also"></a>Siehe auch

[Verwalten von Microsoft 365-Benutzerkonten, -Lizenzen und -Gruppen mit PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Verwalten von Microsoft 365 mit PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Erste Schritte mit PowerShell für Microsoft 365](getting-started-with-microsoft-365-powershell.md)
