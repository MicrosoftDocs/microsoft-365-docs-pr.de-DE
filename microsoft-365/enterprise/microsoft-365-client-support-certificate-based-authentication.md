---
title: Microsoft 365-Client-App-Unterstützung – zertifikatbasierte Authentifizierung
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: Normal
ms.collection:
- Strat_O365_Enterprise
- M365-subscription-management
search.appverid:
- MET150
f1.keywords:
- NOCSH
description: In diesem Artikel finden Sie Details zur Microsoft 365-Client-App-Unterstützung für die zertifikatbasierte Authentifizierung..
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 870e6f39c054752a2a07848c34eecd0996e1816c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690883"
---
# <a name="microsoft-365-client-app-support--certificate-based-authentication"></a>Microsoft 365-Client-App-Unterstützung – zertifikatbasierte Authentifizierung

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Die zertifikatbasierte Authentifizierung ermöglicht die Authentifizierung bei Azure Active Directory mit einem Clientzertifikat auf Windows-, Android-oder IOS-Geräten. Wenn Sie dieses Feature konfigurieren, müssen Sie keine Kombination aus Benutzername und Kennwort in bestimmte e-Mail-und Microsoft Office-Anwendungen auf Ihrem mobilen Gerät eingeben.

Erfahren Sie mehr über die [zertifikatbasierte Authentifizierung](https://docs.microsoft.com/azure/active-directory/authentication/active-directory-certificate-based-authentication-get-started).

## <a name="supported-platforms"></a>Unterstützte Plattformen

 - Windows 10 Desktop<sup>2</sup>
 - Windows 10-moderne apps
 - Webbrowser<sup>3</sup>
 - Android<sup>4</sup>
 - iOS
 - macOS<sup>1</sup> <sup>2</sup>

Weitere Informationen zur Plattformunterstützung in Microsoft 365 finden Sie unter [System Requirements for Microsoft 365](https://products.office.com/office-system-requirements).

## <a name="supported-clients"></a>Unterstützte Clients

Die neuesten Versionen der folgenden Clients unterstützen die zertifikatbasierte Authentifizierung:

| | | | | | |
|:---:|:---:|:---:|:---:|:---:|:---:|
| ![Access-Symbol](../media/o365-access-64x64.png) <br> [Access](https://products.office.com/access) | ![Azure-Symbol](../media/o365-azure-64x64.png) <br> [Azure AD <br> Portal ](https://azure.microsoft.com/features/azure-portal/) | ![Symbol des Unternehmensportals](../media/o365-microsoft-64x64.png) <br> [Unternehmens <br> Portal ](https://docs.microsoft.com/intune-user-help/sign-in-to-the-company-portal) | ![Vertiefen (Symbol)](../media/o365-delve-64x64.png) <br> [Delve](https://products.office.com/business/intelligent-search) | ![Dynamics 365-Symbol](../media/o365-dynamics365-64x64.png) <br> [Dynamics 365](https://dynamics.microsoft.com) 
| ![Edge-Symbol](../media/o365-edge-64x64.png) <br> [Microsoft Edge](https://www.microsoft.com/windows/microsoft-edge) | ![Excel-Symbol](../media/o365-excel-64x64.png) <br> [Excel](https://products.office.com/excel) | ![Symbol "Formulare"](../media/o365-forms-64x64.png) <br> [Formulare](https://flow.microsoft.com/connectors/shared_microsoftforms/microsoft-forms/) | ![Kaizala-Symbol](../media/o365-kaizala-64x64.png) <br> [Kaizala](https://products.office.com/en/business/microsoft-kaizala) | ![Office.com-Symbol](../media/o365-office-64x64.png) <br> [Office.com](https://www.office.com/) 
| ![Office 365 Administrator Symbol](../media/o365-o365admin-64x64.png) <br> [Microsoft 365- <br> Administrator](https://products.office.com/business/manage-office-365-admin-app) | ![Linsen Symbol](../media/o365-lens-64x64.png) <br> [Office Lens](https://www.microsoft.com/p/office-lens/9wzdncrfj3t8?activetab=pivot%3Aoverviewtab) | ![OneDrive für Unternehmen Symbol](../media/o365-OneDrive-64x64.png) <br> [OneDrive<sup>1</sup>](https://products.office.com/onedrive-for-business/online-cloud-storage) |  ![OneNote-Symbol](../media/o365-OneNote-64x64.png) <br> [OneNote](https://products.office.com/onenote) | ![Outlook-Symbol](../media/o365-outlook-64x64.png) <br> [Outlook](https://products.office.com/outlook) 
| ![Planner-Symbol](../media/o365-planner-64x64.png) <br> [Planner](https://products.office.com/business/task-management-software) | ![PowerApps-Symbol](../media/o365-powerapps-64x64.png) <br> [PowerApps<sup>3</sup>](https://powerapps.microsoft.com) | ![Power-Automatisierungs Symbol](../media/o365-flow-64x64.png) <br> [Power- <br> Automatisierung](https://flow.microsoft.com) | ![PowerBI-Symbol](../media/o365-powerbi-64x64.png) <br> [Power BI](https://powerbi.microsoft.com)| ![PowerPoint-Symbol](../media/o365-powerpoint-64x64.png) <br> [PowerPoint](https://products.office.com/powerpoint) 
| ![Project-Symbol](../media/o365-project-64x64.png) <br> [Project](https://products.office.com/project) | ![Publisher-Symbol](../media/o365-publisher-64x64.png) <br> [Publisher](https://products.office.com/publisher) | ![SharePoint-Symbol](../media/o365-sharepoint-64x64.png) <br> [Share](https://products.office.com/sharepoint) | ![Skype for Business-Symbol](../media/o365-skypeforbusiness-64x64.png) <br> [Skype for <br> Business](https://www.skype.com/business/) | ![Symbol für Notizen](../media/o365-stickynotes-64x64.png) <br> [Kurznotizen](https://www.microsoft.com/p/microsoft-sticky-notes/9nblggh4qghw) 
| ![Stream-Symbol](../media/o365-stream-64x64.png) <br> [Stream](https://stream.microsoft.com) | ![Sway-Symbol](../media/o365-sway-64x64.png) <br> [Sway](https://sway.com) | ![Teams-Symbol](../media/o365-teams-64x64.png) <br> [Teams<sup>2</sup>](https://products.office.com/microsoft-teams/group-chat-software) | ![To-do-Symbol](../media/o365-todo-64x64.png) <br> [Aufgabe](https://todo.microsoft.com) | ![Visio-Symbol](../media/o365-visio-64x64.png) <br> [Visio](https://products.office.com/visio/flowchart-software) 
| ![Whiteboard-Symbol](../media/o365-whiteboard-64x64.png) <br> [Whiteboard<sup>3</sup>,<sup>4</sup>](https://whiteboard.microsoft.com/) | ![Word-Symbol](../media/o365-word-64x64.png) <br> [Word](https://products.office.com/word) | ![Yammer-Symbol](../media/o365-yammer-64x64.png) <br> [Jammern<sup>2</sup>](https://products.office.com/yammer/yammer-overview) |

## <a name="supported-powershell-modules"></a>Unterstützte PowerShell-Module

| | | | | | |
|:---:|:---:|:---:|:---:|:---:|:---:|
| ![Azure-Symbol](../media/o365-azure-64x64.png) <br> [Azure AD <br> PowerShell](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) | ![Exchange-Symbol](../media/o365-exchange-64x64.png) <br> [Exchange Online <br> PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps) | ![SharePoint-Symbol](../media/o365-sharepoint-64x64.png) <br> [SharePoint Online <br> PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

> [!NOTE]
> <sup>1</sup> Unterstützung für OneDrive in macOS in Kürze verfügbar. <br>
> <sup>2</sup> Unterstützung für jammern auf Windows-Desktop und macOS in Kürze verfügbar. Die Unterstützung für Microsoft Teams auf dem Windows-Desktop ist in Kürze verfügbar.<br>
> <sup>3</sup> Unterstützung für PowerApps und Whiteboards in Webanwendungen in Kürze verfügbar. <br>
> <sup>4</sup> Unterstützung für Whiteboard auf Android in Kürze verfügbar.

## <a name="see-also"></a>Siehe auch

[Übersicht zu Microsoft 365 Enterprise](microsoft-365-overview.md)
