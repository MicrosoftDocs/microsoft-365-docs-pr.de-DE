---
title: Microsoft 365-Client-App-Unterstützung – bedingter Zugriff
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
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
ms.openlocfilehash: 2245b8fe9b235013bccc9ea2b80d6b6c86448a89
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332016"
---
# <a name="microsoft-365-client-app-support--conditional-access"></a>Microsoft 365-Client-App-Unterstützung – bedingter Zugriff

Auf dem modernen Arbeitsplatz können Benutzer über verschiedene Geräte und apps von überall auf die Ressourcen Ihrer Organisation zugreifen. Das bedeutet, dass die Fokussierung nur darauf, wer auf eine Ressource zugreifen kann, nicht mehr ausreicht. In Ihrer Organisation muss auch unterstützt werden, wie und wo auf eine Ressource in ihrer Zugriffs Steuerungsinfrastruktur zugegriffen wird.

Mit Azure Active Directory (Azure AD)-Gerät, Standort und mehrstufigen Authentifizierungs basierten bedingten Zugriff können Sie diese neue Anforderung erfüllen. Der bedingte Zugriff ist eine Funktion von Azure AD, die es Ihnen ermöglicht, eine Steuerung des Zugriffs auf Apps in Ihrer Umgebung zu erzwingen – basierend auf spezifischen Bedingungen und verwaltet von einem zentralen Ort aus.

Erfahren Sie mehr über den [bedingten Zugriff mit Azure AD](https://docs.microsoft.com/azure/active-directory/conditional-access/).

## <a name="supported-platforms"></a>Unterstützte Plattformen

 - Windows 10-Desktop
 - Windows 10-moderne apps
 - Webbrowser
 - Android
 - iOS
 - macOS<sup>1</sup>

Weitere Informationen zur Plattformunterstützung in Microsoft 365 finden Sie unter [System Requirements for Microsoft 365](https://products.office.com/office-system-requirements).

## <a name="supported-clients"></a>Unterstützte Clients

Die neuesten Versionen der folgenden Clients unterstützen bedingten Zugriff:

| | | | | | |
|:---:|:---:|:---:|:---:|:---:|:---:|
| ![Azure-Symbol](../media/o365-azure-64x64.png) <br> [Azure AD <br> Portal ](https://azure.microsoft.com/features/azure-portal/) | ![Access-Symbol](../media/o365-access-64x64.png) <br> [Access](https://products.office.com/access) | ![Symbol des Unternehmensportals](../media/o365-microsoft-64x64.png) <br> [Unternehmens <br> Portal ](https://docs.microsoft.com/intune-user-help/sign-in-to-the-company-portal)  | ![Cortana-Symbol](../media/o365-cortana-64x64.png) <br> [Cortana](https://www.microsoft.com/cortana) | ![Vertiefen (Symbol)](../media/o365-delve-64x64.png) <br> [Delve](https://products.office.com/business/intelligent-search) 
| ![Dynamics 365-Symbol](../media/o365-dynamics365-64x64.png) <br> [Dynamics 365](https://dynamics.microsoft.com) | ![Edge-Symbol](../media/o365-edge-64x64.png) <br> [Edge](https://www.microsoft.com/windows/microsoft-edge) | ![Exchange-Symbol](../media/o365-exchange-64x64.png) <br> [Exchange](https://products.office.com/exchange/exchange-online) | ![Excel-Symbol](../media/o365-excel-64x64.png) <br> [Excel](https://products.office.com/excel) | ![Symbol "Formulare"](../media/o365-forms-64x64.png) <br> [Formulare](https://flow.microsoft.com/connectors/shared_microsoftforms/microsoft-forms/) 
| ![Kaizala-Symbol](../media/o365-kaizala-64x64.png) <br> [Kaizala](https://products.office.com/en/business/microsoft-kaizala) | ![Office.com-Symbol](../media/o365-office-64x64.png) <br> [Office.com](https://www.office.com/) | ![Linsen Symbol](../media/o365-lens-64x64.png) <br> [Office Lens](https://www.microsoft.com/p/office-lens/9wzdncrfj3t8?activetab=pivot%3Aoverviewtab) | ![Office 365 Administrator Symbol](../media/o365-o365admin-64x64.png) <br> [Microsoft 365- <br> Administrator](https://products.office.com/business/manage-office-365-admin-app) | ![OneDrive für Unternehmen Symbol](../media/o365-OneDrive-64x64.png) <br> [OneDrive<sup>1</sup>](https://products.office.com/onedrive-for-business/online-cloud-storage) 
| ![OneNote-Symbol](../media/o365-OneNote-64x64.png) <br> [OneNote](https://products.office.com/onenote) | ![Outlook-Symbol](../media/o365-outlook-64x64.png) <br> [Outlook](https://products.office.com/outlook) | ![Planner-Symbol](../media/o365-planner-64x64.png) <br> [Planner](https://products.office.com/business/task-management-software) | ![PowerApps-Symbol](../media/o365-powerapps-64x64.png) <br> [PowerApps](https://powerapps.microsoft.com) | ![Power-Automatisierungs Symbol](../media/o365-flow-64x64.png) <br> [Power- <br> Automatisierung](https://flow.microsoft.com)
| ![PowerBI-Symbol](../media/o365-powerbi-64x64.png) <br> [Power BI](https://powerbi.microsoft.com) | ![PowerPoint-Symbol](../media/o365-powerpoint-64x64.png) <br> [PowerPoint](https://products.office.com/powerpoint) | ![Project-Symbol](../media/o365-project-64x64.png) <br> [Project](https://products.office.com/project) | ![Publisher-Symbol](../media/o365-publisher-64x64.png) <br> [Publisher](https://products.office.com/publisher) | ![SharePoint-Symbol](../media/o365-sharepoint-64x64.png) <br> [Share](https://products.office.com/sharepoint) 
| ![Skype for Business-Symbol](../media/o365-skypeforbusiness-64x64.png) <br> [Skype for <br> Business](https://www.skype.com/business/) | ![Symbol für Notizen](../media/o365-stickynotes-64x64.png) <br> [Kurznotizen](https://www.microsoft.com/p/microsoft-sticky-notes/9nblggh4qghw) | ![Stream-Symbol](../media/o365-stream-64x64.png) <br> [Stream](https://stream.microsoft.com) | ![Sway-Symbol](../media/o365-sway-64x64.png) <br> [Sway](https://sway.com) | ![Teams-Symbol](../media/o365-teams-64x64.png) <br> [Teams](https://products.office.com/microsoft-teams/group-chat-software) 
| ![To-do-Symbol](../media/o365-todo-64x64.png) <br> [Aufgabe](https://todo.microsoft.com) | ![Visio-Symbol](../media/o365-visio-64x64.png) <br> [Visio](https://products.office.com/visio/flowchart-software) | ![Word-Symbol](../media/o365-word-64x64.png) <br> [Word](https://products.office.com/word) | ![Yammer-Symbol](../media/o365-yammer-64x64.png) <br> [Yammer](https://products.office.com/yammer/yammer-overview)

## <a name="supported-powershell-modules"></a>Unterstützte PowerShell-Module

| | | | | | |
|:---:|:---:|:---:|:---:|:---:|:---:|
| ![Azure-Symbol](../media/o365-azure-64x64.png) <br> [Azure AD <br> PowerShell](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) | ![Exchange-Symbol](../media/o365-exchange-64x64.png) <br> [Exchange Online <br> PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps) | ![SharePoint-Symbol](../media/o365-sharepoint-64x64.png) <br> [SharePoint Online <br> PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

> [!NOTE]
> <sup>1</sup> Unterstützung für OneDrive in macOS in Kürze verfügbar.

## <a name="see-also"></a>Siehe auch

[Übersicht zu Microsoft 365 Enterprise](microsoft-365-overview.md)
