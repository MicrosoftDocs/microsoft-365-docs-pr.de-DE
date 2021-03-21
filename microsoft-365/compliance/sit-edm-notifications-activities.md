---
title: Erstellen von Benachrichtigungen für exakte Datenübereinstimmungsaktivitäten (Vorschau)
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: ''
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Erfahren Sie, wie Sie Benachrichtigungen für genaue Datenübereinstimmungsaktivitäten erstellen.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2e2f67ef0f276211483519bd5e246e4e041b2b15
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919361"
---
# <a name="create-notifications-for-exact-data-match-activities-preview"></a>Erstellen von Benachrichtigungen für exakte Datenübereinstimmungsaktivitäten (Vorschau)

Wenn Sie [benutzerdefinierte vertrauliche Informationstypen mit exakter Datenübereinstimmung (EDM)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md) erstellen, werden im [Überwachungsprotokoll](search-the-audit-log-in-security-and-compliance.md#requirements-to-search-the-audit-log) eine Reihe von Aktivitäten erstellt. Mit dem PowerShell-Cmdlet [New-ProtectionAlert](/powershell/module/exchange/new-protectionalert?view=exchange-ps) können Sie Benachrichtigungen erstellen, die Sie über folgende Aktivitäten informieren:

- CreateSchema
- EditSchema
- RemoveSchema
- UploadDataFailed
- UploadDataCompleted

> [!NOTE]
> Die Möglichkeit, Benachrichtigungen für EDM-Aktivitäten zu erstellen, ist nur für die World Wide- und GCC-Clouds verfügbar.

## <a name="pre-requisites"></a>Voraussetzungen

Das von Ihnen verwendete Konto muss eines der folgenden sein:

- ein globaler Administrator
- Compliance-Administrator
- Exchange Online-Administrator

Weitere Informationen über DLP-Berechtigungen finden Sie unter [Berechtigungen](data-loss-prevention-policies.md#permissions).

Die EDM-basierte Klassifizierung ist in diesen Abonnements enthalten.

- Office 365 E5
- Microsoft 365 E5
- Microsoft 365 E5 Compliance
- Microsoft E5/ A5 Information Protection und Governance

Weitere Informationen zur DLP-Lizenzierung finden Sie in den [Microsoft 365-Lizenzierungsrichtlinien für Security & Compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)

## <a name="configure-notifications-for-edm-activities"></a>Konfigurieren von Benachrichtigungen für EDM-Aktivitäten

1. Stellen Sie eine Verbindung mit der [Security & Compliance Center PowerShell her](/powershell/exchange/connect-to-scc-powershell?view=exchange-ps). 

2. Führen Sie das `New-ProtectionAlert` -Cmdlet mit der Aktivität aus, für die Sie die Benachrichtigung erstellen möchten.  Wenn Sie beispielsweise benachrichtigt werden möchten, wenn die Aktion **UploadDataCompleted-Aktion** ausgeführt wurde, führen Sie das Folgende aus

```powershell
New-ProtectionAlert -Name "EdmUploadCompleteAlertPolicy" -Category Others -NotifyUser <***address to send  notification to***> -ThreatType Activity -Operation UploadDataCompleted -Description "Custom alert policy to track when EDM upload Completed" -AggregationType None
```

für den **UploadDataFailed** können Sie das Folgende ausführen

```powershell
New-ProtectionAlert -Name "EdmUploadFailAlertPolicy" -Category Others -NotifyUser <***SMTP address to send notification to***> -ThreatType Activity -Operation UploadDataFailed -Description "Custom alert policy to track when EDM upload Failed" -AggregationType None -Severity High
```

## <a name="related-articles"></a>Verwandte Artikel

- [Erstellen benutzerdefinierter Typen vertraulicher Informationen mit genauer Datenübereinstimmung (EDM)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
- [New-ProtectionAlert](/powershell/module/exchange/new-protectionalert?view=exchange-ps)