---
title: Erstellen von Benachrichtigungen für genaue Datenübereinstimmungsaktivitäten
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
ms.openlocfilehash: 263dc319d7e7d3ee5f12ebe374e8f5bd44c4cc8c
ms.sourcegitcommit: 5db5047c24b56f3af90c2bc5c830a7a13eeeccad
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2021
ms.locfileid: "53341676"
---
# <a name="create-notifications-for-exact-data-match-activities"></a>Erstellen von Benachrichtigungen für genaue Datenübereinstimmungsaktivitäten

Wenn Sie [benutzerdefinierte vertrauliche Informationstypen mit exakter Datenübereinstimmung (EDM)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md) erstellen, werden im [Überwachungsprotokoll](search-the-audit-log-in-security-and-compliance.md#before-you-search-the-audit-log) eine Reihe von Aktivitäten erstellt. Mit dem PowerShell-Cmdlet [New-ProtectionAlert](/powershell/module/exchange/new-protectionalert) können Sie Benachrichtigungen erstellen, die Sie über folgende Aktivitäten informieren:

- CreateSchema
- EditSchema
- RemoveSchema
- UploadDataFailed
- UploadDataCompleted

## <a name="pre-requisites"></a>Voraussetzungen

Das von Ihnen verwendete Konto muss eines der folgenden sein:

- ein globaler Administrator
- Compliance-Administrator
- Exchange Online-Administrator

Weitere Informationen über DLP-Berechtigungen finden Sie unter [Berechtigungen](data-loss-prevention-policies.md#permissions).

Die EDM-basierte Klassifizierung ist in diesen Abonnements enthalten:

- Office 365 E5
- Microsoft 365 E5
- Microsoft 365 E5 Compliance
- Microsoft E5/ A5 Information Protection und Governance

Weitere Informationen zur DLP-Lizenzierung finden Sie in den [Microsoft 365-Lizenzierungsrichtlinien für Security & Compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection).

## <a name="configure-notifications-for-edm-activities"></a>Konfigurieren von Benachrichtigungen für EDM-Aktivitäten

1. Stellen Sie eine Verbindung mit der [Security & Compliance Center-PowerShell](/powershell/exchange/connect-to-scc-powershell) her.

2. Führen Sie das `New-ProtectionAlert`-Cmdlet mit der Aktivität aus, für die Sie die Benachrichtigung erstellen möchten.  Wenn Sie beispielsweise benachrichtigt werden möchten, wenn die Aktion **UploadDataCompleted** ausgeführt wurde, führen Sie Folgendes aus:

    ```powershell
    New-ProtectionAlert -Name "EdmUploadCompleteAlertPolicy" -Category Others -NotifyUser <address to send notification to> -ThreatType Activity -Operation UploadDataCompleted -Description "Custom alert policy to track when EDM upload Completed" -AggregationType None
    ```
    
    für die Aktion **UploadDataFailed** können Sie Folgendes ausführen:
    
    ```powershell
    New-ProtectionAlert -Name "EdmUploadFailAlertPolicy" -Category Others -NotifyUser <SMTP address to send notification to> -ThreatType Activity -Operation UploadDataFailed -Description "Custom alert policy to track when EDM upload Failed" -AggregationType None -Severity High
    ```

## <a name="related-articles"></a>Verwandte Artikel

- [Erstellen benutzerdefinierter Typen vertraulicher Informationen mit genauer Datenübereinstimmung (EDM)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
- [New-ProtectionAlert](/powershell/module/exchange/new-protectionalert)