---
title: Anforderungen für Microsoft 365 Lighthouse
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: Rufen Sie für verwaltete Dienstanbieter (Managed Service Providers, MSPs) eine Liste der Anforderungen für die Verwendung von Microsoft 365 Lighthouse ab.
ms.openlocfilehash: 9c87744053ffe3bace90534287cd2b81697f3554
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "53395188"
---
# <a name="requirements-for-microsoft-365-lighthouse"></a>Anforderungen für Microsoft 365 Lighthouse

> [!NOTE]
> Die in diesem Artikel beschriebenen Features befinden sich in der Vorschau, können geändert werden und sind nur für Partner verfügbar, die die in diesem Artikel aufgeführten Anforderungen erfüllen. Wenn Ihre Organisation nicht über Microsoft 365 Lighthouse verfügt, lesen Sie ["Registrieren für Microsoft 365 Lighthouse".](m365-lighthouse-sign-up.md)

Microsoft 365 Lighthouse ist ein Verwaltungsportal, das Managed Service Providers (MSPs) dabei unterstützt, Geräte, Daten und Benutzer für SMB-Kunden (Small- und Medium-Business) im großen Maßstab zu sichern und zu verwalten.  

MSPs müssen für das programm Cloud Solution Provider (CSP) als indirekter Händler oder Partner für direkte Rechnungen registriert sein, um Microsoft 365 Lighthouse verwenden zu können.  

Darüber hinaus muss sich jeder MSP-Kundenmandant für Microsoft 365 Lighthouse qualifizieren, indem er die folgenden Anforderungen erfüllt: 
 
- Delegierte Administratorrechte (Delegated Admin Privileges, DAP) für den MSP 
- Mindestens eine Microsoft 365 Business Premium-Lizenz 
- Weniger als 500 lizenzierte Benutzer  

## <a name="requirements-for-enablingdevice-management"></a>Anforderungen für die Aktivierung der Geräteverwaltung   

Um Kundenmandantengeräte auf den Geräteverwaltungsseiten anzuzeigen, muss ein MSP Folgendes tun:    

- Registrieren Sie alle Kundengeräte in Microsoft Endpoint Manager (MEM).Weitere Informationen finden Sie unter [Registrieren von Geräten in Microsoft Intune.](/mem/intune/enrollment/)
- Weisen Sie allen Kundengeräten Compliancerichtlinien zu.Weitere Informationen finden Sie unter [Erstellen einer Compliancerichtlinie in Microsoft Intune.](/mem/intune/protect/create-compliance-policy) 

## <a name="requirements-for-enabling-usermanagement"></a>Anforderungen für die Aktivierung der Benutzerverwaltung 

Damit Kundendaten in Berichten auf Benutzerverwaltungsseiten angezeigt werden können, einschließlich riskanter Benutzer, mehrstufiger Authentifizierung und Kennwortzurücksetzung, müssen Kundenmandanten Über Lizenzen für Azure Active Directory Premium P1 oder höher verfügen. Azure AD Premium P1 ist in Microsoft 365 Business Premium enthalten.   

## <a name="requirements-for-enablingthreat-management"></a>Anforderungen für die Aktivierung des Bedrohungsmanagements 

Um Kundenmandantengeräte und Bedrohungen auf den Seiten für das Bedrohungsmanagement anzuzeigen, müssen Sie alle Kundenmandantengeräte in Microsoft Endpoint Manager (MEM) registrieren und diese schützen, indem Sie Microsoft Defender Antivirus ausführen.  

Weitere Informationen finden Sie unter [Registrieren von Geräten in Microsoft Intune.](/mem/intune/enrollment/)  

Microsoft Defender Antivirus ist Teil des Windows Betriebssystems und auf Geräten mit Windows 10 standardmäßig aktiviert.  

> [!NOTE] 
> Wenn Sie eine Antivirenlösung verwenden, die nicht von Microsoft stammt und nicht Microsoft Defender Antivirus, wird Microsoft Defender Antivirus automatisch deaktiviert. Wenn Sie die Antivirenlösung deinstallieren, die nicht von Microsoft stammt, wird Microsoft Defender Antivirus automatisch aktiviert, um Ihre Windows Geräte vor Bedrohungen zu schützen.    

## <a name="related-content"></a>Verwandte Inhalte   

[Konfigurieren Microsoft 365 Lighthouse Portalsicherheit](m365-lighthouse-configure-portal-security.md) (Artikel)\
[Übersicht über Microsoft 365 Lighthouse Gerätekompatibilität](m365-lighthouse-device-compliance-page-overview.md) (Artikel)\
[Übersicht über die Seite "Microsoft 365 Lighthouse Benutzer"](m365-lighthouse-users-page-overview.md) (Artikel)\
[Übersicht über Microsoft 365 Lighthouse Seite "Bedrohungsmanagement"](m365-lighthouse-threat-management-page-overview.md) (Artikel)\
[häufig gestellte Fragen](m365-lighthouse-faq.yml)   zu Microsoft 365 Lighthouse (Artikel)

