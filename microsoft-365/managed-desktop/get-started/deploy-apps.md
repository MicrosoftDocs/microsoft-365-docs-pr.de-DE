---
title: Bereitstellen von apps für Microsoft verwalteter Desktop-Geräte
description: Informationen zum Hinzufügen und Bereitstellen von apps für Microsoft verwalteter Desktop-Geräte.
keywords: Microsoft verwalteter Desktop, Microsoft 365, Dienst, Dokumentation, apps, Line-of-Business-apps, LOB-apps
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 01/17/2019
ms.openlocfilehash: 65d45be5ddb21d8f2cac876a1c8f93b2bbddf7b8
ms.sourcegitcommit: 0fc00286d7dc8cafddf9d17a98a375503b9551e6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/18/2019
ms.locfileid: "29341606"
---
# <a name="deploy-apps-to-microsoft-managed-desktop-devices"></a>Bereitstellen von apps in Microsoft verwalteter Desktop-Geräte
Teil Onboarding auf Microsoft Managed Desktop umfasst hinzufügen und Bereitstellen von apps für Geräte des Benutzers. Nachdem Sie das Microsoft verwalteter Desktop-Portal verwenden, können Sie hinzufügen und Bereitstellen Ihrer apps. 

Der Gesamtprozess sieht folgendermaßen aus:
1. [Hinzufügen von apps verwalteter Microsoft-Desktop-Portal](#1) – dies apps Line-of-Business (LOB) oder apps aus Microsoft Store für Unternehmen, die Sie synchronisiert haben mit Intune vorhanden sein. 
2. [Erstellen von Azure Active Directory (AD) Gruppen für die Zuweisung von app](#2) - verwenden Sie diese Gruppen zum Verwalten von app-Zuordnung.
3. [Zuweisen von apps für Ihre Benutzer](#3)

<span id="1" />

## <a name="step-1-add-apps-to-microsoft-managed-desktop-portal"></a>Schritt 1: Hinzufügen von apps verwalteter Microsoft-Desktop-Portal
Sie können Microsoft verwalteter Desktop [Win32 Windows MSI-basierte apps](#lob-apps)oder [Microsoft Store für Business apps](#msfb-apps) hinzugefügt werden und klicken Sie dann auf Microsoft verwalteter Desktop Geräte bereitstellen.

<span id="lob-apps">

###  <a name="win32-or-windows-msi-based-apps-to-microsoft-managed-desktop"></a>Win32- oder Windows MSI-basierte apps an Microsoft verwalteten Desktops

Sie können Ihre apps Line-of-Business (LOB) Microsoft verwalteter Desktop-Portal hinzufügen. Informationen zu Anforderungen für apps, die auf Microsoft verwalteter Desktop Geräten installiert finden Sie unter [Microsoft verwalteter Desktop-app-Anforderungen](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements).

In diesem Verfahren wählen Sie die Art der app aus, den, die Sie hinzufügen möchten, und klicken Sie dann konfigurieren und Hochladen der app-Quelle möchten. 

**So fügen Sie Ihre LOB-app oder Windows-app verwalteter Microsoft-Desktop-Portal hinzu**

Melden Sie sich bei Microsoft verwalteter Desktop-Portal oder Intune melden Sie sich, und suchen Sie dann nach Microsoft verwalteter Desktop. Anmelden bei Microsoft verwalteter Desktop Portal erfahren. 

1.  Melden Sie sich bei [verwalteten Desktops Verwaltungsportal von Microsoft](http://aka.ms/mmdportal). 
2.  Wählen Sie unter **Inventar** **Apps**.
3.  Wählen Sie in der Arbeitslast Apps **Hinzufügen**aus.
4.  Wählen Sie in **app hinzufügen** **Branchen app** oder **Windows-Anwendung (Win32) - Vorschau anzuzeigen**.
    - Wenn Sie **LOB app**ausgewählt haben, finden Sie unter [Hinzufügen einer Windows LOB app zu Microsoft Intune](https://docs.microsoft.com/intune/lob-apps-windows) Anweisung zum Hinzufügen und Konfigurieren von Line-of-Business-apps.
    - Wenn Sie **Windows-Anwendung (Win32) - Vorschau anzeigen**ausgewählt haben, finden Sie unter [Win32-app-Verwaltung](https://docs.microsoft.com/intune/apps-win32-app-management) erhalten Sie Anleitungen hinzufügen und Konfigurieren von apps für Windows.

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a>Microsoft-Speichers für die Business-apps
Wenn Sie nicht mit Microsoft Store for Business angemeldet haben, können Sie sich anmelden, wenn Sie für apps kaufen. Nachdem Sie Ihre apps haben, können Sie diese mit Microsoft verwalteter Desktop synchronisieren. 

**Zum Erwerben von apps aus dem Microsoft Store for Business**

1. Melden Sie sich an [Microsoft Store for Business](https://businessstore.microsoft.com) mit Ihrem Microsoft Store für Business Administratorkonto.
2. Wählen Sie **Meine Gruppe kaufen**.
3. Anhand der Suche, die die app zu suchen, und wählen Sie die app.
4. Wählen Sie auf Produktdetails **rufen Sie die App**. Microsoft Store hinzugefügt **Produkte & Dienstleistungen** für Ihre Organisation die app.

**So erzwingen Sie eine Synchronisierung zwischen Intune und Microsoft Store for Business**
1. Melden Sie sich [Azure-Portal](https://portal.azure.com/) als Intune Admin oder globaler Administrator für Ihre Mandanten
2. Wählen Sie **alle Dienste > Intune**aus. Intune befindet sich in der Überwachung + Management Abschnitt.
3. Klicken Sie im Bereich Intune wählen Sie **Client-Apps**, und wählen Sie dann **Microsoft Store for Business**aus.
4. Wählen Sie Ihre Microsoft Store für Business-apps mit Intune synchronisieren **Aktivieren** .
    - Wenn Sie noch nicht geschehen ist, Sign up und Zuordnen Ihrer Microsoft Speichern Business-Kontos mit Intune
    - Wählen Sie die Sprache, in der apps aus dem Microsoft Store for Business in Ihre Konsole Intune angezeigt wird
    - Wählen Sie **Synchronisierung** Ihrer Microsoft Store für Business-apps mit Intune synchronisieren.
    - Stellen Sie sicher, dass die Synchronisierung zwischen Microsoft Store for Business und Intune aktiv ist (Nächster Schritt). 

**Um sicherzustellen, dass eine Synchronisierung zwischen Intune und Microsoft Store for Business aktiv ist.**
1. Melden Sie sich an [Microsoft Store for Business](https://businessstore.microsoft.com) mit Ihrem Microsoft Store für Business Administratorkonto.
2. Wählen Sie **Verwalten**aus.
3. Wählen Sie **Einstellungen** , und wählen Sie dann **verteilen**.
4. Klicken Sie unter **Verwaltungstools**sicherstellen Sie, dass Intune aufgeführt wird und der Status **aktiv**ist.  

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a>Schritt 2: Erstellen von Azure AD-Gruppen

Erstellen Sie drei Azure Active Directory-Gruppen für die jeweilige app. Die folgende Tabelle beschreibt die Gruppen, die Sie benötigen (verfügbar, die erforderlich sind, und deinstallieren). 

Typ der App-Zuordnung |   Gruppe verwenden   | Azure AD-Beispielname
--- | --- | ---
Verfügbar |  Die app aus Unternehmensportal app oder Website zur Verfügung. | MMD – *app-Name* – verfügbar
Erforderlich |  Die app ist auf Geräten in den ausgewählten Gruppen installiert. | MMD – *app-Name* – erforderlich
„Deinstallieren“ |  TThe app wird von Geräten in den ausgewählten Gruppen deinstalliert. | MMD – *app-Name* – deinstallieren

Diese Gruppen, damit der app verfügbar machen, die app installieren oder Entfernen der app auf ihrem Gerät Microsoft verwalteter Desktop fügen Sie Ihrer Benutzer hinzu. 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a>Schritt 3: Zuweisen von apps für Ihre Benutzer

**Ihre Benutzer die app zuweisen**

1. Melden Sie sich bei [verwalteten Desktops Verwaltungsportal von Microsoft](http://aka.ms/mmdportal).
2. Wählen Sie im Bereich verwalteter Desktop **Apps**ein.
3. Wählen Sie in der Arbeitslast Apps die app, den, die Sie Benutzern zuweisen, und wählen Sie **Benutzer und Gruppen zuweisen**möchten.
4. Wählen Sie für die bestimmte app eine Zuordnung (verfügbar, erforderlich, deinstallieren), und weisen Sie die entsprechende Gruppe.
5. Klicken Sie im Bereich weisen Sie Apps wählen Sie **OK**aus.

<!--# Preparing apps for Microsoft Managed Desktop

This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.

Applications: supported/onboard/deployment
 
Microsoft and Microsoft Managed Desktop customers have equally critical, yet different responsibilities around applications used with Microsoft Managed Desktop.

## Microsoft responsibilities
**Office 365 apps**
Microsoft will provide full service for the deployment, update, and support of specific Office 365 apps. All users will receive the base set of Office 365 click to run, 64 bit version of applications included in the device’s image so that a user can quickly become productive. The Project and Visio applications in of the Office 365 suite are licensed separately.  Microsoft Managed Desktop will provide deployment groups allowing the IT Administrator to manage licenses and deploy these applications appropriately for their organization. Microsoft will support end users of these applications through the Microsoft Managed Desktop Support channels.

**Line-of-business apps**
Microsoft provides tooling for IT Administrators to manage and deploy their line-of-business (LOB) applications to end users as a part of the Intune product. Microsoft will support application deployment issues as detailed in [Line-of-business applications](#line-of-business-applications) 

**Deploy with Intune**
Intune will be linked to the **Microsoft Store for Business** during Microsoft Managed Desktop onboarding allowing procured apps to be deployed through Intune. Microsoft will also deploy the web-based version of the Company Portal to end users so that IT Administrators can provide a self-service experience for end users.

**App management**
Microsoft may identify restricted applications which are not suitable for the modern workplace because of their system impact. When such an application is identified Microsoft will notify the customer and that application will need to be removed from the tenant. 

For more information on restricted app behaviors and app requirements, see [Microsoft Managed Desktop app requirements](../service-description/mmd-app-requirements.md)

## Customer responsibilities
The Office 365 Suite is core to Microsoft’s productivity offerings and is included in the Microsoft 365 License for all Microsoft Managed Desktop users. While Microsoft deploys, updates, and supports Office Applications to Microsoft Managed Desktop Devices there are still some areas for which the customer is responsible.
- **Assign licenses** - Customers are responsible for assigning the appropriate licenses to end users for Office 365. 
- **Add users to security groups** - For customers with users who need Project or Visio, the IT administrator must add those users to the appropriate deployment groups. IT administrators are also responsible for managing end of life for those users. 
- **Deploy Office 365 Add Ons** - Customers are responsible for deploying any plugins to the Office 365 suite which are deemed necessary. 

Since line-of-business (LOB) apps are unique for each customer, customers are responsible for managing all applications within their organization not deployed by Microsoft. This includes:
- Deciding which apps are needed and who needs them
- Assigning apps to those users
- Create and maintain Azure Active Directory (AD) groups for managing app assignments 

The customer must upload LOB apps to Intune. They are then responsible for deploying, updating, and decommissioning those applications over their respective lifecycles, as well as managing support for these apps for their users.

## Office applications
As part of the Microsoft 365 E5 license, Office 365 Standard Suite (64 Bit) is deployed by Microsoft. 

For details, see [Microsoft Managed Desktop technologies](../intro/technologies.md) <!--- and the other applications licensed under Office 365 E5 may be deployed by the customer using Intune’s deployment tools.

## Line-of-business applications
This table summarizes responsibilities across the different phases for line-of-business (LOB) applications. 

Application work items |    Customer    | Microsoft
--- | --- | ---
**Onboarding apps** |  |
Identify applications needed for targeted user groups   | ![yes](images/checkmark.png)  |
Create and manage Azure AD groups for app deployment | ![yes](images/checkmark.png) |   
**App Packaging** |  |
Package apps to meet Intune deployment standards |  ![yes](images/checkmark.png) |  
Upload apps to Intune | ![yes](images/checkmark.png)     |
Test apps in Microsoft Managed Desktop environment |    ![yes](images/checkmark.png) |  
Test apps with end users    | ![yes](images/checkmark.png) |    
**Deployment** | |
Manage and assign users to applications  | ![yes](images/checkmark.png)  |
Intune deployment tools delivers application to remote clients| |   ![yes](images/checkmark.png)
Identify and deploy application updates through Intune | ![yes](images/checkmark.png)    |
Unistall and remove applications when they have been retired    | ![yes](images/checkmark.png) |    
**Management** | |
Procure and assign licenses |   ![yes](images/checkmark.png)     |
Provide end-user support for line-of-business apps  | ![yes](images/checkmark.png) |
Manage app settings remotely    | ![yes](images/checkmark.png) |

For information on LOB application requirements, see [Microsoft Managed Desktop application requirements](../service-description/mmd-app-requirements.md)


## Intune application deployment
Application management can be handled through the Microsoft Managed Desktop Admin portal, or through the Intune portal. Intune’s app management portal shows applications deployed for Windows, Android, and iOS. Microsoft Managed Desktop Admin portal limits the view to Windows 10 applications. Both are available through the Azure Portal. 
* [Intune app management basics](https://docs.microsoft.com/intune/app-management)
* [Add apps to Intune](https://docs.microsoft.com/intune/app-management)
   * [Add a line-of-business App](https://docs.microsoft.com/intune/lob-apps-windows)
   * [Add Win32 apps to Intune](https://docs.microsoft.com/intune/apps-win32-app-management)
   * [Add web applications](https://docs.microsoft.com/intune/web-app)
* [Deploy apps](https://docs.microsoft.com/intune/apps-deploy)
   * [Deploy apps to Windows 10](https://docs.microsoft.com/intune/apps-windows-10-app-deploy)
* Company Portal
   * [Deploy the Company Portal](https://docs.microsoft.com/intune/store-apps-company-portal-app)
   * [Configure the Company Portal app](https://docs.microsoft.com/intune/company-portal-app)-->