---
title: 'Microsoft 365-Client-App-Unterstützung: zertifikatbasierte Authentifizierung'
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
ms.openlocfilehash: fde124fcefdf3b949ec35a3b2ed99b15ee36f85e
ms.sourcegitcommit: 2beefb695cead03cc21d6066f589572d3ae029aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "49349680"
---
# <a name="microsoft-365-client-app-support-certificate-based-authentication"></a>Microsoft 365-Client-App-Unterstützung: zertifikatbasierte Authentifizierung

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Die moderne Authentifizierung ist ein übergeordneter Ausdruck für eine Kombination aus Authentifizierungs-und Autorisierungsmethoden. Zu diesen zählen:

- **Authentifizierungsmethoden**: mehrstufige Authentifizierung; Client zertifikatbasierte Authentifizierung.
- **Autorisierungsmethoden**: Microsoft-Implementierung der Open Authorization (OAuth).

Die moderne Authentifizierung wird mithilfe einer Authentifizierungsbibliothek wie Active Directory Authentication Library (Adal) oder Microsoft Authentication Library (MSAL) aktiviert. Die moderne Authentifizierung verwendet Clients zum Authentifizieren und Autorisieren des Zugriffs auf Microsoft 365-Ressourcen. Die moderne Authentifizierung nutzt OAuth und stellt einen sicheren Mechanismus für Clients bereit, um auf Microsoft 365-Dienste zuzugreifen, ohne Zugriff auf Benutzeranmeldeinformationen zu benötigen. Bei der Anmeldung authentifiziert sich der Benutzer direkt bei Azure Active Directory und erhält ein Zugriffs-/Aktualisierungstoken-Paar als Rückgabewert. Das Zugriffstoken erteilt dem Clientzugriff auf die entsprechenden Ressourcen im Microsoft 365-Mandanten. Ein Aktualisierungstoken wird verwendet, um ein neues Zugriffs-oder Aktualisierungstoken-paar zu erhalten, wenn das aktuelle Zugriffstoken abläuft.

Die moderne Authentifizierung unterstützt unterschiedliche Authentifizierungsmechanismen, wie die zertifikatbasierte Authentifizierung. Clients auf Windows-, Android-oder IOS-Geräten können die zertifikatbasierte Authentifizierung (CBA) zur Authentifizierung bei Azure Active Directory mithilfe eines Clientzertifikats auf dem Gerät verwenden. Anstelle eines typischen Benutzernamens/Kennworts wird das Zertifikat verwendet, um ein Zugriffs/Aktualisierungs-Token-Paar aus Azure-Active Directory zu erhalten.

Erfahren Sie mehr über die [zertifikatbasierte Authentifizierung](https://docs.microsoft.com/azure/active-directory/authentication/active-directory-certificate-based-authentication-get-started).

## <a name="supported-clients--platforms"></a>Unterstützte Clients & Plattformen

Die neuesten Versionen der folgenden Clients und Plattformen unterstützen die zertifikatbasierte Authentifizierung bei der Anmeldung bei Azure Active Directory-Konten innerhalb des Clients (beispielsweise beim Hinzufügen eines Kontos zur APP). Weitere Informationen zur Plattformunterstützung in Microsoft 365 finden Sie unter [System Requirements for Microsoft 365](https://www.microsoft.com/microsoft-365/microsoft-365-and-office-resources).
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
| Rand<sup>1</sup> | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | Nicht zutreffend | Nicht zutreffend | ![Unterstützt](../media/check-mark.png) |
| Excel | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) |
| Exchange Online Administrator | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend | ![Unterstützt](../media/check-mark.png) |
| Formulare | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend |
| Office 365 Admin | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend | ![Unterstützt](../media/check-mark.png) |  |
| Kaizala | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend |
| Office Lens| ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | N/V | ![Unterstützt](../media/check-mark.png) | N/V |
| Office Mobile | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend |
| Office-Portal | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend | ![Unterstützt](../media/check-mark.png) | N/V |
| OneDrive | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | Geplant | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) |
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
| SharePoint Online Administrator | Geplant | Geplant | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend |
| Kurznotizen | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend | ![Unterstützt](../media/check-mark.png) | N/V |
| Stream | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend |
| Sway | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend | ![Unterstützt](../media/check-mark.png) | N/V |
| Teams | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | N/V | Geplant |
| Aufgabe | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | N/V |
| Visio | Nicht zutreffend | ![Unterstützt](../media/check-mark.png) | Nicht zutreffend | Nicht zutreffend | ![Unterstützt](../media/check-mark.png) |
| Whiteboard | Geplant | Geplant | Nicht zutreffend | ![Unterstützt](../media/check-mark.png) | N/V |
| Word | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) |
| Analyse am Arbeitsplatz | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend |
| Yammer | ![Unterstützt](../media/check-mark.png) | ![Unterstützt](../media/check-mark.png) | Geplant | Nicht zutreffend | Geplant |

>[!NOTE]
><sup>1</sup> Edge für IOS und Android unterstützt die zertifikatbasierte Authentifizierung bei Konten-Add-Flows. Edge für IOS und Android unterstützt die zertifikatbasierte Authentifizierung nicht beim Durchführen einer Authentifizierung für Websites, bei denen es sich normalerweise um Intranet-Websites handelt. <br><br>  In diesem Szenario navigiert ein Benutzer zu einer Website (in der Regel im Intranet), für die die Website den Benutzer über ein Zertifikat authentifizieren muss. Dies beinhaltet keine moderne Authentifizierung und nutzt keine Microsoft-Authentifizierungsbibliothek. Dies liegt an einer Beschränkung mit ios: IOS verhindert, dass Drittanbieter-apps auf den System-Schlüsselbund zugreifen, in dem die Zertifikate gespeichert sind (nur Apple-Apps und der [Safari-WebView-Controller](https://developer.apple.com/documentation/safariservices/sfsafariviewcontroller) können auf den System-Schlüsselbund zugreifen). <br><br> Da Edge auf dem [WebKit](https://developer.apple.com/documentation/webkit) -Framework zum Rendern von Websites basiert, kann Edge nicht auf den System-Schlüsselbund zugreifen und dem Benutzer eine Zertifikatauswahl vorlegen. Dies ist leider Design bedingt durch die Architektur von Apple.

## <a name="supported-powershell-modules"></a>Unterstützte PowerShell-Module

- [Azure Active Directory PowerShell](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0)
- [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)
- [SharePoint Online-PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

