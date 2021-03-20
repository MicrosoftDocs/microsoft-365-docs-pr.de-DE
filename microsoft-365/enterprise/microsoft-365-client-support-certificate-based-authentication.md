---
title: 'Microsoft 365 Client App Support: Zertifikatbasierte Authentifizierung'
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
description: In diesem Artikel finden Sie Details zur Microsoft 365-Client-App-Unterstützung für die zertifikatbasierte Authentifizierung.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d5ebef7c10aa61ba28c8fb841468be244f6e8542
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904987"
---
# <a name="microsoft-365-client-app-support-certificate-based-authentication"></a>Microsoft 365 Client App Support: Zertifikatbasierte Authentifizierung

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Moderne Authentifizierung ist ein Oberbegriff für eine Kombination aus Authentifizierungs- und Autorisierungsmethoden. Beispiele:

- **Authentifizierungsmethoden**: Mehrstufige Authentifizierung; Clientzertifikatbasierte Authentifizierung.
- **Autorisierungsmethoden**: Microsofts Implementierung von Open Authorization (OAuth).

Die moderne Authentifizierung wird mithilfe einer Authentifizierungsbibliothek wie active Directory Authentication Library (ADAL) oder Microsoft Authentication Library (MSAL) aktiviert. Die moderne Authentifizierung wird von Clients zum Authentifizieren und Autorisieren des Zugriffs auf Microsoft 365-Ressourcen verwendet. Die moderne Authentifizierung verwendet OAuth und stellt einen sicheren Mechanismus für Clients für den Zugriff auf Microsoft 365-Dienste ohne Zugriff auf Benutzeranmeldeinformationen zur Verfügung. Bei der Anmeldung authentifiziert sich der Benutzer direkt bei Azure Active Directory und erhält im Gegenzug ein Zugriffs-/Aktualisierungstokenpaar. Das Zugriffstoken gewährt dem Client Zugriff auf die entsprechenden Ressourcen im Microsoft 365-Mandanten. Ein Aktualisierungstoken wird verwendet, um ein neues Zugriffs- oder Aktualisierungstokenpaar abzurufen, wenn das aktuelle Zugriffstoken abläuft.

Die moderne Authentifizierung unterstützt verschiedene Authentifizierungsmechanismen, z. B. die zertifikatbasierte Authentifizierung. Clients auf Windows-, Android- oder iOS-Geräten können die zertifikatbasierte Authentifizierung (CBA) verwenden, um sich mit einem Clientzertifikat auf dem Gerät bei Azure Active Directory zu authentifizieren. Anstelle eines typischen Benutzernamens/Kennworts wird das Zertifikat verwendet, um ein Zugriffs-/Aktualisierungstokenpaar von Azure Active Directory abzurufen.

Erfahren Sie mehr [über die zertifikatbasierte Authentifizierung](/azure/active-directory/authentication/active-directory-certificate-based-authentication-get-started).

## <a name="supported-clients--platforms"></a>Unterstützte Clients & Plattformen

Die neuesten Versionen der folgenden Clients und Plattformen unterstützen die zertifikatbasierte Authentifizierung beim Anmelden bei Azure Active Directory-Konten innerhalb des Clients (z. B. beim Hinzufügen eines Kontos zur App). Weitere Informationen zur Plattformunterstützung in Microsoft 365 finden Sie unter [System requirements for Microsoft 365](/microsoft-365/microsoft-365-and-office-resources).
<br>
<br>

[!INCLUDE [Certificate-based authentication services support table](../includes/microsoft-365-client-support-certificate-based-authentication-include.md)]

>[!NOTE]
>Edge für iOS und Android unterstützt die zertifikatbasierte Authentifizierung während kontobasierter Add-Flows. Edge für iOS und Android unterstützt keine zertifikatbasierte Authentifizierung bei der Authentifizierung für Websites, bei denen es sich in der Regel um Intranetwebsites handelt. <br><br>  In diesem Szenario navigiert ein Benutzer zu einer Website (in der Regel im Intranet), auf der sich der Benutzer über ein Zertifikat authentifizieren muss. Dies erfordert keine moderne Authentifizierung und nutzt keine Microsoft-Authentifizierungsbibliothek. Dies liegt an einer Einschränkung bei iOS: iOS verhindert, dass Apps von Drittanbietern auf die Systemschlüsselkette zugreifen, in der die Zertifikate gespeichert sind (nur Apple-Apps und der [Safari-Webview-Controller](https://developer.apple.com/documentation/safariservices/sfsafariviewcontroller) können auf die Systemschlüsselkette zugreifen). <br><br> Da Edge das [WebKit-Framework](https://developer.apple.com/documentation/webkit) zum Rendern von Websites verwendet, kann Edge nicht auf die Systemschlüsselkette zugreifen und dem Benutzer eine Zertifikatauswahl präsentieren. Dies liegt leider an der Architektur von Apple.

## <a name="supported-powershell-modules"></a>Unterstützte PowerShell-Module

- [Azure Active Directory PowerShell](/powershell/azure/active-directory/overview?view=azureadps-2.0)
- [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell)
- [SharePoint Online-PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

