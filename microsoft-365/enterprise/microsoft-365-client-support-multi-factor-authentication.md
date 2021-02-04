---
title: 'Microsoft 365-Client-App-Unterstützung: Mehrstufige Authentifizierung'
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
description: In diesem Artikel erfahren Sie, welche Plattformen, Clients und PowerShell-Module die mehrstufige Authentifizierung für Microsoft 365 unterstützen.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fdec611fc595cdc15abb0fc1fb7a998f7a615ff7
ms.sourcegitcommit: 8e696c084d097520209c864140af11aa055b979e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2021
ms.locfileid: "50097468"
---
# <a name="microsoft-365-client-app-support-multi-factor-authentication"></a>Microsoft 365-Client-App-Unterstützung: Mehrstufige Authentifizierung

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Um eine zusätzliche Sicherheitsstufe für Anmeldungen zu bieten, können Clients für die Verwendung der mehrstufigen Authentifizierung (Multi-Factor Authentication, MFA) konfiguriert werden, bei der sowohl ein Benutzerkennwort als auch eine zusätzliche Benutzerüberprüfungsmethode verwendet wird, basierend auf:

- Etwas in ihrem Besitz, das nicht einfach dupliziert werden kann, z. B. ein Smartphone.
- Etwas, über das der Benutzer eindeutig und in regelmäßigen Fällen verfügt, z. B. seine Fingerabdrücke, das Gesicht oder ein anderes biometrisches Attribut

Erfahren Sie mehr über [die mehrstufige Authentifizierung.](/azure/active-directory/authentication/multi-factor-authentication)

## <a name="supported-clients--platforms"></a>Unterstützte Clients & Plattformen

Die neuesten Versionen der folgenden Clients und Plattformen unterstützen die mehrstufige Authentifizierung. Weitere Informationen zur Plattformunterstützung in Microsoft 365 finden Sie unter [Systemanforderungen für Microsoft 365](/microsoft-365/microsoft-365-and-office-resources).
<br>
<br>

| Clients | Android | iOS | Mac| Windows 10 <br> Moderne Apps| Windows 10 <br> Desktop |
|:---|:---:|:---:|:---:|:---:|:---:|
| Azure Active Directory Admin | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend | ![Unterstützt](../media/check-mark.png) |
| Zugriff | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend | ![Unterstützt](../media/check-mark.png) |
| Azure Admin | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend |
| Unternehmensportal | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | N/V |
| Cortana | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | N/V | ![Unterstützt](../media/check-mark.png) | N/V |
| Delve | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend |
| Microsoft Edge | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | Nicht zutreffend | Nicht zutreffend | ![Unterstützt](../media/check-mark.png) |
| Excel | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) |
| Exchange Online Admin | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend | ![Unterstützt](../media/check-mark.png) |
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
| Skype for Business Admin | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend | ![Unterstützt](../media/check-mark.png) |
| SharePoint | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend |
| SharePoint Online Admin | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend | ![Unterstützt](../media/check-mark.png) |
| Kurznotizen | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend | ![Unterstützt](../media/check-mark.png) | N/V |
| Stream | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend |
| Sway | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend | ![Unterstützt](../media/check-mark.png) | N/V |
| Teams | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | N/V | ![Unterstützt](../media/check-mark.png) |
| To Do | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | N/V |
| Visio | Nicht zutreffend | ![Unterstützt](../media/check-mark.png) | Nicht zutreffend | Nicht zutreffend | ![Unterstützt](../media/check-mark.png) |
| Whiteboard | Geplant | ![Unterstützt](../media/check-mark.png) | N/V | ![Unterstützt](../media/check-mark.png) | N/V |
| Word | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) |
| Arbeitsplatzanalyse | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend |
| Yammer | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | N/V | ![Unterstützt](../media/check-mark.png) |

## <a name="supported-powershell-modules"></a>Unterstützte PowerShell-Module

- [Azure Active Directory PowerShell](/powershell/azure/active-directory/overview?view=azureadps-2.0)
- [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell)
- [SharePoint Online-PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)