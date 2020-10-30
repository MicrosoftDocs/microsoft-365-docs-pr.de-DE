---
title: 'Microsoft 365-Client-App-Support: Einzel Sign-On'
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
description: In diesem Artikel erfahren Sie, welche Plattformen, Clients und PowerShell-Module einmaliges Anmelden für Microsoft 365 unterstützen.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b70f0c1ec4a6e94651b987830c8b29993732a3c2
ms.sourcegitcommit: 04a43a146cb62a10b1a4555ec3bed49eb08fbb99
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2020
ms.locfileid: "48806663"
---
# <a name="microsoft-365-client-app-support-single-sign-on"></a>Microsoft 365-Client-App-Support: Einzel Sign-On

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Einmaliges Anmelden (Single Sign-on, SSO) fügt Sicherheit und Bequemlichkeit hinzu, wenn sich Ihre Benutzer bei Anwendungen in Azure Active Directory anmelden. Bei der einmaligen Anmeldung melden sich Benutzer mit einem Konto einmal an, um auf lokale Active Directory-Domänendienste (AD DS) Domänenbeitritt, Software as a Service (SaaS)-Anwendungen und Webanwendungen zuzugreifen.

Weitere Informationen finden Sie [unter Single Sign-on](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on).

## <a name="supported-clients--platforms"></a>Unterstützte Clients & Plattformen

Die neuesten Versionen der folgenden Clients und Plattformen unterstützen einmaliges Anmelden. Weitere Informationen zur Plattformunterstützung in Microsoft 365 finden Sie unter [System Requirements for Microsoft 365](https://products.office.com/office-system-requirements).
<br>
<br>

| Clients | Android | iOS | Mac| Windows 10 <br> Moderne apps| Windows 10 <br> Desktop |
|:---|:---:|:---:|:---:|:---:|:---:|
| Access | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend | ![Unterstützt](../media/check-mark.png) |
| Unternehmensportal | Nicht zutreffend | ![Unterstützt](../media/check-mark.png) | Geplant | ![Unterstützt](../media/check-mark.png) | N/V |
| Cortana | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend | ![Unterstützt](../media/check-mark.png) | N/V |
| Delve | Geplant | ![Unterstützt](../media/check-mark.png) | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend |
| Microsoft Edge | ![Unterstützt](../media/check-mark.png) | Geplant | Nicht zutreffend | Nicht zutreffend | ![Unterstützt](../media/check-mark.png) |
| Excel | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) |
| Kaizala | ![Unterstützt](../media/check-mark.png) | Geplant | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend |
| Office Lens| ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend |
| Office Mobile | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend |
| Office-Portal | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend | ![Unterstützt](../media/check-mark.png) | N/V |
| OneDrive | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | Geplant | ![Unterstützt](../media/check-mark.png) | Geplant |
| OneNote | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | Geplant |
| Outlook | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | Geplant | ![Unterstützt](../media/check-mark.png) |
| Planner | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend |
| Power-Apps | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | N/V | Geplant | Nicht zutreffend |
| Power Automate | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend |
| Power BI | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | N/V | ![Unterstützt](../media/check-mark.png) | Geplant |
| PowerPoint | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) |
| Project | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend | ![Unterstützt](../media/check-mark.png) |
| Publisher | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend | ![Unterstützt](../media/check-mark.png) |
| Skype for Business | Geplant | Geplant | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend |
| SharePoint | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend |
| Kurznotizen | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend | ![Unterstützt](../media/check-mark.png) |
| Stream | Geplant | Geplant | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend |
| Sway | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend | ![Unterstützt](../media/check-mark.png) |
| Teams | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | Geplant | Nicht zutreffend | Geplant |
| Aufgabe | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | N/V | ![Unterstützt](../media/check-mark.png) | N/V |
| Visio | Nicht zutreffend | ![Unterstützt](../media/check-mark.png) | Nicht zutreffend | Nicht zutreffend | ![Unterstützt](../media/check-mark.png) |
| Whiteboard | Nicht zutreffend | ![Unterstützt](../media/check-mark.png) | N/V | ![Unterstützt](../media/check-mark.png) | N/V |
| Word | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) |
| Yammer | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | Nicht zutreffend | Nicht zutreffend | Geplant |

## <a name="supported-powershell-modules"></a>Unterstützte PowerShell-Module

- [Azure Active Directory PowerShell](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0)
- [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)
- [SharePoint Online-PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
