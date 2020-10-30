---
title: 'Microsoft 365-Client-App-Support: bedingter Zugriff'
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_Enterprise
- M365-subscription-management
f1.keywords:
- NOCSH
description: In diesem Artikel erfahren Sie, welche Plattformen, Clients und PowerShell-Module den bedingten Zugriff für Microsoft 365 unterstützen.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: dc187a26cd3aa644888312327b07fc9a116950cc
ms.sourcegitcommit: 04a43a146cb62a10b1a4555ec3bed49eb08fbb99
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2020
ms.locfileid: "48806682"
---
# <a name="microsoft-365-client-app-support-conditional-access"></a>Microsoft 365-Client-App-Support: bedingter Zugriff

Auf dem modernen Arbeitsplatz können Benutzer über verschiedene Geräte und apps von überall auf die Ressourcen Ihrer Organisation zugreifen. Das bedeutet, dass die Fokussierung nur darauf, wer auf eine Ressource zugreifen kann, nicht mehr ausreicht. In Ihrer Organisation muss auch unterstützt werden, wie und wo auf eine Ressource in ihrer Zugriffs Steuerungsinfrastruktur zugegriffen wird.

Mit Azure Active Directory Gerät, Standort und mehrstufigen Authentifizierungs basierten bedingten Zugriff können Sie diese neue Anforderung erfüllen. Bedingter Zugriff ist eine Funktion von Azure Active Directory, mit der Sie Steuerelemente für den Zugriff auf apps in Ihrer Umgebung erzwingen können, die alle auf spezifischen Bedingungen basieren und von einem zentralen Standort aus verwaltet werden.

Erfahren Sie mehr über [Azure Active Directory bedingten Zugriff](https://docs.microsoft.com/azure/active-directory/conditional-access/).

## <a name="supported-clients--platforms"></a>Unterstützte Clients & Plattformen

Die neuesten Versionen der folgenden Clients und Plattformen unterstützen den bedingten Zugriff. Weitere Informationen zur Plattformunterstützung in Microsoft 365 finden Sie unter [System Requirements for Microsoft 365](https://www.microsoft.com/microsoft-365/microsoft-365-and-office-resources).

<br>
<br>

| Clients | Android | iOS | Mac| Windows 10 <br> Moderne apps| Windows 10 <br> Desktop |
|:---|:---:|:---:|:---:|:---:|:---:|
| Azure Active Directory Administrator | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend | ![Unterstützt](../media/check-mark.png) |
| Access | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend | ![Unterstützt](../media/check-mark.png) |
| Azure-Administrator | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend |
| Unternehmensportal | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | N/V |
| Cortana | Geplant | Geplant | Nicht zutreffend | ![Unterstützt](../media/check-mark.png) | N/V |
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
| Power-Apps | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | N/V | Geplant | Nicht zutreffend |
| Power Automate | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend |
| Power BI | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | N/V | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) |
| PowerPoint | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) |
| Project | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend | ![Unterstützt](../media/check-mark.png) |
| Publisher | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend | ![Unterstützt](../media/check-mark.png) |
| Skype for Business | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend ||
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
