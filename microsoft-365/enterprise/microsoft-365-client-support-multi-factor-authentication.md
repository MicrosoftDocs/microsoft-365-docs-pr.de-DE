---
title: 'Microsoft 365 Client App Support: Mehrstufige Authentifizierung'
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
ms.openlocfilehash: 80ee370526d17d472cd048cd4d89b862e158b631
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927561"
---
# <a name="microsoft-365-client-app-support-multi-factor-authentication"></a>Microsoft 365 Client App Support: Mehrstufige Authentifizierung

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Um ein zusätzliches Maß an Sicherheit für Anmeldungen zu bieten, können Clients für die Verwendung der mehrstufigen Authentifizierung (Multi-Factor Authentication, MFA) konfiguriert werden, die sowohl ein Benutzerkennwort als auch eine andere Benutzerüberprüfungsmethode verwendet, basierend auf:

- Etwas, das sich in ihrem Besitz befindet, das nicht einfach dupliziert werden kann, z. B. ein Smartphone.
- Etwas, das der Benutzer eindeutig und biometrisch besitzt, z. B. fingerabdrücke, Gesichtsdaten oder andere biometrische Attribute

Erfahren Sie mehr [über die mehrstufige Authentifizierung](/azure/active-directory/authentication/multi-factor-authentication).

## <a name="supported-clients--platforms"></a>Unterstützte Clients & Plattformen

Die neuesten Versionen der folgenden Clients und Plattformen unterstützen die mehrstufige Authentifizierung. Weitere Informationen zur Plattformunterstützung in Microsoft 365 finden Sie unter [System requirements for Microsoft 365](/microsoft-365/microsoft-365-and-office-resources).
<br>
<br>

[!INCLUDE [Multi-factor authentication services support table](../includes/microsoft-365-client-support-modern-authentication-include.md)]

## <a name="supported-powershell-modules"></a>Unterstützte PowerShell-Module

- [Azure Active Directory PowerShell](/powershell/azure/active-directory/overview?view=azureadps-2.0)
- [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell)
- [SharePoint Online-PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)