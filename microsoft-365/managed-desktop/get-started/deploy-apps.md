---
title: Bereitstellen von Apps für Microsoft Managed Desktop-Geräte
description: Informationen zum Hinzufügen und Bereitstellen von apps auf Microsoft Managed Desktop-Geräten.
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation, apps, Branchenanwendungen, Lob-apps
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 5eac2e8c3023015bd034c51ad7e16a669a484772
ms.sourcegitcommit: 427c6459614d58f6ef7c74354ae1816423e22323
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/28/2019
ms.locfileid: "35390422"
---
# <a name="deploy-apps-to-microsoft-managed-desktop-devices"></a>Bereitstellen von apps auf Microsoft Managed Desktop-Geräten
Ein Teil des onboardings für Microsoft Managed Desktop umfasst das Hinzufügen und Bereitstellen von apps auf den Geräten Ihrer Benutzer. Nachdem Sie das Microsoft Managed Desktop Portal verwendet haben, können Sie Ihre apps hinzufügen und bereitstellen. 

Der Gesamtprozess sieht wie folgt aus:
1. [Hinzufügen von apps zu Microsoft Managed Desktop Portal](#1) -Dies kann vorhandene Branchen-Apps oder Apps aus dem Microsoft Store for Business sein, die Sie mit InTune synchronisiert haben. 
2. [Erstellen von Azure Active Directory (AD)-Gruppen für die APP-Zuweisung](#2) -Sie verwenden diese Gruppen zum Verwalten der APP-Zuweisung.
3. [Zuweisen von apps zu Benutzern](#3)

<span id="1" />

## <a name="step-1-add-apps-to-microsoft-managed-desktop-portal"></a>Schritt 1: Hinzufügen von apps zu Microsoft Managed Desktop Portal
Sie können [Win32-oder Windows MSI-basierte apps](#lob-apps)oder [Microsoft Store for Business-Apps](#msfb-apps) zu Microsoft Managed Desktop hinzufügen und diese dann auf Microsoft Managed Desktop-Geräten bereitstellen.

<span id="lob-apps">

###  <a name="win32-or-windows-msi-based-apps-to-microsoft-managed-desktop"></a>Win32-oder Windows MSI-basierte apps auf Microsoft Managed Desktop

Sie können Ihre Branchen-apps zu Microsoft Managed Desktop Portal hinzufügen. Informationen zu den Anforderungen für apps, die auf Microsoft Managed Desktop-Geräten installiert sind, finden Sie unter [Microsoft Managed Desktop App Requirements](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements).

In diesem Verfahren wählen Sie aus, welche App-Art Sie hinzufügen möchten, und konfigurieren und laden dann die APP-Quelle. 

**So fügen Sie Ihre Branchen-APP oder Windows-APP zu einem Microsoft Managed Desktop-Portal hinzu**

Sie können sich bei Microsoft Managed Desktop Portal anmelden oder sich bei InTune anmelden und dann nach Microsoft Managed Desktop suchen. Wir zeigen, dass Sie sich bei Microsoft Managed Desktop Portal anmelden. 

1.  Melden Sie sich beim [Microsoft Managed Desktop-Verwaltungsportal](http://aka.ms/mmdportal)an. 
2.  Wählen Sie unter **Inventar**die Option **apps**aus.
3.  Wählen Sie in der Arbeitsauslastung von apps die Option **Hinzufügen**aus.
4.  Wählen Sie unter **app hinzufügen**die Option **Branchen-App** oder **Windows-app (Win32) – Vorschau**aus.
    - Wenn Sie die Branchen **-App**ausgewählt haben, finden Sie unter [Hinzufügen einer Windows-Branchen-APP zu Microsoft InTune](https://docs.microsoft.com/intune/lob-apps-windows) Anweisungen zum Hinzufügen und Konfigurieren von Branchen-apps.
    - Wenn Sie **Windows-app (Win32)-Preview**ausgewählt haben, finden Sie unter [Win32 App Management](https://docs.microsoft.com/intune/apps-win32-app-management) Anweisungen zum Hinzufügen und Konfigurieren von Windows-apps.

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a>Microsoft Store for Business-Apps
Wenn Sie sich nicht bei Microsoft Store for Business angemeldet haben, können Sie sich anmelden, wenn Sie apps kaufen. Nachdem Sie Ihre apps haben, können Sie Sie mit dem Microsoft Managed Desktop synchronisieren. 

**So kaufen Sie Apps aus dem Microsoft Store for Business**

1. Melden Sie sich mit Ihrem Microsoft Store for Business-Administratorkonto bei [Microsoft Store for Business](https://businessstore.microsoft.com) an.
2. Wählen Sie **für meine Gruppe Shop**aus.
3. Verwenden Sie die Suche, um die gewünschte APP zu finden, und wählen Sie die APP aus.
4. Wählen Sie auf den Produkt Details **die Option App abrufen**aus. Microsoft Store fügt die APP den **Produkten #a0 Diensten** für Ihre Organisation hinzu.

**So erzwingen Sie eine Synchronisierung zwischen InTune und Microsoft Store for Business**
1. Melden Sie sich beim [Azure-Portal](https://portal.azure.com/) als InTune-Administrator oder globaler Administrator für Ihren Mandanten an.
2. Wählen Sie **alle Dienste #a0 InTune**aus. InTune befindet sich im Abschnitt Überwachung + Verwaltung.
3. Wählen Sie im Bereich InTune die Option **Client apps**aus, und wählen Sie dann **Microsoft Store for Business**aus.
4. Wählen Sie **aktivieren** aus, um Ihren Microsoft Store for Business-Apps mit InTune zu synchronisieren.
    - Wenn Sie noch nicht angemeldet sind, registrieren und Ihr Microsoft Store for Business-Konto mit InTune verknüpfen
    - Wählen Sie die Sprache aus, in der Apps aus dem Microsoft Store for Business in ihrer InTune-Konsole angezeigt werden.
    - Wählen Sie **Sync** aus, um Ihren Microsoft Store for Business-Apps mit InTune zu synchronisieren.
    - Stellen Sie sicher, dass die Synchronisierung zwischen Microsoft Store for Business und InTune aktiv ist (nächster Schritt). 

**So stellen Sie sicher, dass eine Synchronisierung zwischen InTune und Microsoft Store for Business aktiv ist**
1. Melden Sie sich mit Ihrem Microsoft Store for Business-Administratorkonto bei [Microsoft Store for Business](https://businessstore.microsoft.com) an.
2. Wählen Sie **Manage**aus.
3. Wählen Sie **Einstellungen** aus, und wählen Sie dann **verteilen**aus.
4. Überprüfen Sie unter **Verwaltungstools**, ob InTune aufgeführt ist und ob der Status **aktiv**ist.  

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a>Schritt 2: Erstellen von Azure Ad Gruppen

Erstellen Sie für jede APP drei Azure Ad Gruppen. In dieser Tabelle werden die Gruppen beschrieben, die Sie benötigen (verfügbar, erforderlich und Uninstall). 

Zuordnungstyp "App" |   Gruppenverwendung   | Beispiel Azure Ad Name
--- | --- | ---
Available |  Die APP wird über die APP oder Website des Unternehmensportals verfügbar sein. | MMD – *App-Name* – verfügbar
Erforderlich |  Die APP wird auf Geräten in den ausgewählten Gruppen installiert. | MMD – *App-Name* – erforderlich
Uninstall |  Die APP wird auf den Geräten in den ausgewählten Gruppen deinstalliert. | MMD – *App-Name* – deinstallieren

Fügen Sie Ihre Benutzer zu diesen Gruppen hinzu, um entweder die app verfügbar zu machen, die APP zu installieren oder die APP von Ihrem von Microsoft verwalteten Desktop Gerät zu entfernen. 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a>Schritt 3: Zuweisen von apps zu Benutzern

**So weisen Sie die APP Ihren Benutzern zu**

1. Melden Sie sich beim [Microsoft Managed Desktop-Verwaltungsportal](http://aka.ms/mmdportal)an.
2. Wählen Sie im Bereich verwalteter Desktop die Option **apps**aus.
3. Wählen Sie in der Arbeitsauslastung Apps die APP aus, der Sie Benutzer zuweisen möchten, und wählen Sie **Benutzergruppen zuweisen**aus.
4. Wählen Sie für die jeweilige APP einen Zuordnungstyp (verfügbar, erforderlich, deinstallieren) aus, und weisen Sie die entsprechende Gruppe zu.
5. Wählen Sie im Bereich apps zuweisen die Option **OK**aus.

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
