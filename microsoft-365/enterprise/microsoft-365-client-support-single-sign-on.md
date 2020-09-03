---
title: Microsoft 365-Client-App-Unterstützung – einmaliges Anmelden
ms.author: robmazz
author: robmazz
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
description: In diesem Artikel erfahren Sie, welche Plattformen, Clients und PowerShell-Module einmaliges Anmelden für Microsoft 365 unterstützen.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8ab973fcfb0cc61378ee06c115264e308d8ec3ad
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332004"
---
# <a name="microsoft-365-client-app-support--single-sign-on"></a>Microsoft 365-Client-App-Unterstützung – einmaliges Anmelden

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Einmaliges Anmelden (Single Sign-on, SSO) fügt Sicherheit und Bequemlichkeit hinzu, wenn sich Ihre Benutzer bei Anwendungen in Azure Active Directory (Azure AD) anmelden. Bei der einmaligen Anmeldung melden sich Benutzer mit einem Konto einmal an, um auf Domänen verbundene Geräte, Unternehmensressourcen, Software as a Service (SaaS)-Anwendungen und Webanwendungen zuzugreifen.

Weitere Informationen finden Sie [unter Single Sign-on](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on).

## <a name="supported-platforms"></a>Unterstützte Plattformen

 - Windows 10 Desktop<sup>2</sup>
 - Windows 10-moderne apps
 - Webbrowser
 - Android<sup>3</sup>
 - IOS<sup>1</sup>
 - macOS<sup>4</sup>

Weitere Informationen zur Plattformunterstützung in Microsoft 365 finden Sie unter [System Requirements for Microsoft 365](https://products.office.com/office-system-requirements).

## <a name="supported-clients"></a>Unterstützte Clients

Die neuesten Versionen der folgenden Clients unterstützen einmaliges Anmelden:

| | | | | | |
|:---:|:---:|:---:|:---:|:---:|:---:|
| ![Access-Symbol](../media/o365-access-64x64.png) <br> [Access](https://products.office.com/access) | ![Symbol des Unternehmensportals](../media/o365-microsoft-64x64.png) <br> [Unternehmens <br> Portal<sup>3, 4</sup>](https://docs.microsoft.com/intune-user-help/sign-in-to-the-company-portal) | ![Vertiefen (Symbol)](../media/o365-delve-64x64.png) <br> [Delve](https://products.office.com/business/intelligent-search) | ![Edge-Symbol](../media/o365-edge-64x64.png) <br> [Rand<sup>1</sup>](https://www.microsoft.com/windows/microsoft-edge) | ![Excel-Symbol](../media/o365-excel-64x64.png) <br> [Excel](https://products.office.com/excel) 
| ![Kaizala-Symbol](../media/o365-kaizala-64x64.png) <br> [Kaizala<sup>1</sup>](https://products.office.com/en/business/microsoft-kaizala) | ![Office.com-Symbol](../media/o365-office-64x64.png) <br> [Office.com](https://www.office.com/) | ![Linsen Symbol](../media/o365-lens-64x64.png) <br> [Office Lens](https://www.microsoft.com/p/office-lens/9wzdncrfj3t8?activetab=pivot%3Aoverviewtab) | ![OneDrive für Unternehmen Symbol](../media/o365-OneDrive-64x64.png) <br> [OneDrive](https://products.office.com/onedrive-for-business/online-cloud-storage) | ![OneNote-Symbol](../media/o365-OneNote-64x64.png) <br> [OneNote<sup>2</sup>](https://products.office.com/onenote) 
| ![Outlook-Symbol](../media/o365-outlook-64x64.png) <br> [Outlook<sup>4</sup>](https://products.office.com/outlook) | ![Planner-Symbol](../media/o365-planner-64x64.png) <br> [Planner](https://products.office.com/business/task-management-software) | ![Power-Automatisierungs Symbol](../media/o365-flow-64x64.png) <br> [Power- <br> Automatisierung](https://flow.microsoft.com) | ![PowerBI-Symbol](../media/o365-powerbi-64x64.png) <br> [Power BI<sup>2</sup>](https://powerbi.microsoft.com)| ![PowerPoint-Symbol](../media/o365-powerpoint-64x64.png) <br> [PowerPoint](https://products.office.com/powerpoint) 
| ![Project-Symbol](../media/o365-project-64x64.png) <br> [Project](https://products.office.com/project) | ![Publisher-Symbol](../media/o365-publisher-64x64.png) <br> [Publisher](https://products.office.com/publisher) | ![SharePoint-Symbol](../media/o365-sharepoint-64x64.png) <br> [Share](https://products.office.com/sharepoint) | ![Symbol für Notizen](../media/o365-stickynotes-64x64.png) <br> [Kurznotizen](https://www.microsoft.com/p/microsoft-sticky-notes/9nblggh4qghw)  | ![Sway-Symbol](../media/o365-sway-64x64.png) <br> [Sway](https://sway.com) 
| ![Teams-Symbol](../media/o365-teams-64x64.png) <br> [Teams<sup>2, 4</sup>](https://products.office.com/microsoft-teams/group-chat-software) | ![To-do-Symbol](../media/o365-todo-64x64.png) <br> [Aufgabe](https://todo.microsoft.com) | ![Visio-Symbol](../media/o365-visio-64x64.png) <br> [Visio](https://products.office.com/visio/flowchart-software) | ![Whiteboard-Symbol](../media/o365-whiteboard-64x64.png) <br> [Whiteboard<sup>3</sup>](https://whiteboard.microsoft.com/) | ![Word-Symbol](../media/o365-word-64x64.png) <br> [Word](https://products.office.com/word) 
| ![Yammer-Symbol](../media/o365-yammer-64x64.png) <br> [Jammern<sup>2</sup>](https://products.office.com/yammer/yammer-overview) |

## <a name="supported-powershell-modules"></a>Unterstützte PowerShell-Module

| | | | | | |
|:---:|:---:|:---:|:---:|:---:|:---:|
| ![Azure-Symbol](../media/o365-azure-64x64.png) <br> [Azure AD <br> PowerShell](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) | ![Exchange-Symbol](../media/o365-exchange-64x64.png) <br> [Exchange Online <br> PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps) | ![SharePoint-Symbol](../media/o365-sharepoint-64x64.png) <br> [SharePoint Online <br> PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

> [!NOTE]
> <sup>1</sup> Unterstützung für Edge-und Kaizala in ios in Kürze verfügbar. <br>
> <sup>2</sup> Unterstützung für OneNote, PowerBI, Teams und jammern auf Windows 10-Desktop verfügbar in Kürze. <br>
> <sup>3</sup> Unterstützung für Whiteboard auf Android in Kürze verfügbar. <br>
> <sup>4</sup> Unterstützung für Outlook, Teams und Unternehmens Portal auf macOS in Kürze verfügbar. <br>

## <a name="see-also"></a>Siehe auch

[Übersicht zu Microsoft 365 Enterprise](microsoft-365-overview.md)
