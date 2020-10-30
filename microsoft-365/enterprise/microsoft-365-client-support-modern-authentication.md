---
title: 'Microsoft 365-Client-App-Support: moderne Authentifizierung'
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Strat_O365_Enterprise
- M365-subscription-management
search.appverid:
- MET150
f1.keywords:
- NOCSH
description: In diesem Artikel erfahren Sie, welche Plattformen, Clients und PowerShell-Module die moderne Authentifizierung für Microsoft 365 unterstützen.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 290a151e127b05e984b9d262c3b429b561201545
ms.sourcegitcommit: 04a43a146cb62a10b1a4555ec3bed49eb08fbb99
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2020
ms.locfileid: "48806664"
---
# <a name="microsoft-365-client-app-support-modern-authentication"></a>Microsoft 365-Client-App-Support: moderne Authentifizierung

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Die moderne Authentifizierung ermöglicht die Active Directory Authentifizierungsbibliothek (Adal)-basierte Anmeldung für Office-Client-apps auf verschiedenen Plattformen. Dadurch werden Anmeldefeatures wie mehrstufige Authentifizierung (MFA), Smartcards und zertifikatbasierte Authentifizierung aktiviert.

Erfahren Sie mehr über [mehrstufige Authentifizierung](https://docs.microsoft.com/azure/active-directory/authentication/multi-factor-authentication) und [zertifikatbasierte Authentifizierung](https://docs.microsoft.com/azure/active-directory/active-directory-certificate-based-authentication-get-started).

## <a name="supported-clients--platforms"></a>Unterstützte Clients & Plattformen

Die neuesten Versionen der folgenden Clients und Plattformen unterstützen die moderne Authentifizierung. Weitere Informationen zur Plattformunterstützung in Microsoft 365 finden Sie unter [System Requirements for Microsoft 365](https://www.microsoft.com/microsoft-365/microsoft-365-and-office-resources).
<br>
<br>

| Clients | Android | iOS | Mac| Windows 10 <br> Moderne apps| Windows 10 <br> Desktop |
|:---|:---:|:---:|:---:|:---:|:---:|
| Azure Active Directory Administrator | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend | ![Unterstützt](../media/check-mark.png) |
| Access | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend | ![Unterstützt](../media/check-mark.png) |
| Azure-Administrator | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend |
| Unternehmensportal | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | N/V |
| Cortana | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | N/V | ![Unterstützt](../media/check-mark.png) | N/V |
| Delve | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend |
| Microsoft Edge | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | Nicht zutreffend | Nicht zutreffend | ![Unterstützt](../media/check-mark.png) |
| Excel | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) |
| Exchange Online Administrator | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend | ![Unterstützt](../media/check-mark.png) |
| Formulare | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend |
| Office 365 Admin | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend | ![Unterstützt](../media/check-mark.png) |  |
| Kaizala | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend |
| Office Lens| ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | N/V | ![Unterstützt](../media/check-mark.png) | N/V |
| Office Mobile | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend |
| Office-Portal | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend | ![Unterstützt](../media/check-mark.png) | N/V |
| OneDrive | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) |
| OneNote | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) |
| Outlook | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) |
| Planner | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend |
| Power-Apps | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | N/V | ![Unterstützt](../media/check-mark.png) | N/V |
| Power Automate | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend |
| Power BI | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | N/V | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) |
| PowerPoint | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) |
| Project | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend | ![Unterstützt](../media/check-mark.png) |
| Publisher | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend | ![Unterstützt](../media/check-mark.png) |
| Skype for Business | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | N/V | ![Unterstützt](../media/check-mark.png) |
| Skype for Business Administrator | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend | ![Unterstützt](../media/check-mark.png) |
| SharePoint | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend |
| SharePoint Online Administrator | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend | ![Unterstützt](../media/check-mark.png) |
| Kurznotizen | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend | ![Unterstützt](../media/check-mark.png) | N/V |
| Stream | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend |
| Sway | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend | ![Unterstützt](../media/check-mark.png) | N/V |
| Teams | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | N/V | ![Unterstützt](../media/check-mark.png) |
| Aufgabe | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | N/V |
| Visio | Nicht zutreffend | ![Unterstützt](../media/check-mark.png) | Nicht zutreffend | Nicht zutreffend | ![Unterstützt](../media/check-mark.png) |
| Whiteboard | Geplant | ![Unterstützt](../media/check-mark.png) | N/V | ![Unterstützt](../media/check-mark.png) | N/V |
| Word | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) |
| Analyse am Arbeitsplatz | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend |
| Yammer | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | N/V | ![Unterstützt](../media/check-mark.png) |

## <a name="supported-powershell-modules"></a>Unterstützte PowerShell-Module

- [Azure Active Directory PowerShell](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0)
- [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)
- [SharePoint Online-PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)