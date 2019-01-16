---
title: Vorbereiten von apps für Microsoft verwalteten Desktops
description: ''
keywords: Dokumentation Microsoft verwalteter Desktop, Microsoft-365-Dienst
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: b46e3de4a4cfe2140574ab9fc589e3a738bd2e17
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2019
ms.locfileid: "26867762"
---
# <a name="preparing-apps-for-microsoft-managed-desktop"></a>Vorbereiten von apps für Microsoft verwalteten Desktops

<!--This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.-->

<!--Applications: supported/onboard/deployment -->
 
Kunden von Microsoft und Microsoft verwalteter Desktop haben gleichmäßig kritische, noch andere Aufgaben um Anwendungen, die mit Microsoft verwalteter Desktop verwendet.

## <a name="microsoft-responsibilities"></a>Zuständigkeiten von Microsoft
**Apps für Office 365** Microsoft stellt die gesamten Diensts für die Bereitstellung, Update und Unterstützung für bestimmte apps für Office 365 bereit. Alle Benutzer erhält den Basis Satz von Office 365 klicken Sie auf Ausführen, 64-Bit-Version von Anwendungen in das Gerät Bild eingeschlossen werden, sodass ein Benutzer schneller produktiv werden kann. Die Project und Visio-Anwendungen in der Office 365-Suite werden separat lizenziert.  Microsoft verwalteter Desktop wird Bereitstellungsgruppen ermöglicht es dem IT-Administrator zum Verwalten von Lizenzen und Bereitstellen dieser Anwendungen entsprechend für ihre Organisation bereitstellen. Microsoft unterstützt Endbenutzer dieser Anwendungen die Kanäle Microsoft Managed Desktop zu unterstützen.

**Line-of-Business-apps** Microsoft bietet Tools für IT-Administratoren zum Verwalten und Bereitstellen von ihnen Line-of-Business (LOB) Anwendungen für Endbenutzer als Bestandteil des Produkts Intune. Microsoft unterstützt Anwendung Bereitstellungsprobleme wie in [LOB Anwendungen](#line-of-business-applications) 

**Bereitstellen mit Intune** Intune wird an den **Microsoft Store for Business** während Microsoft verwalteter Desktop Onboarding beschaffte apps durch Intune bereitgestellt werden, sodass verknüpft werden. Microsoft wird auch die Web-basierten Version des Unternehmens Portals Endbenutzer bereitstellen, damit IT-Administratoren eine Benutzeroberfläche Self-service für Endbenutzer bereitstellen können.

**App-Verwaltung** Microsoft kann eingeschränkte Applications identifizieren, die aufgrund von deren Einfluss System nicht für die moderne Jahrestag geeignet sind. Wenn eine solche Anwendung identifiziert wird Microsoft benachrichtigt den Kunden und dieser Anwendung müssen aus den Mandanten entfernt werden soll. 

Weitere Informationen zu eingeschränkten app Verhaltensweisen und app-Anforderungen finden Sie unter [Microsoft verwalteter Desktop-app-Anforderungen](../service-description/mmd-app-requirements.md)

## <a name="customer-responsibilities"></a>Kundenverantwortlichkeiten
Die Office 365-Suite ist der Kern Microsofts Produktivität angeboten und ist in der Microsoft-365-Lizenz für alle Benutzer von Microsoft verwalteten Desktops enthalten. Während Microsoft bereitstellt, aktualisiert und unterstützt die Office-Programme auf Microsoft verwaltete Desktops Geräte immer noch einige Bereiche für die der Kunde zuständig ist.
- **Zuweisen von Lizenzen** - Kunden sind verantwortlich für die Endbenutzer auf Office 365 die entsprechenden Lizenzen zuweisen. 
- **Hinzufügen von Benutzern zu Sicherheitsgruppen** - muss Kunden mit Benutzern, Project oder Visio, benötigen, der IT-Administrator diese Benutzer die entsprechenden Bereitstellungsgruppen hinzufügen. IT-Administratoren sind auch für das Ende der Lebensdauer für diese Benutzer verwalten verantwortlich. 
- **Bereitstellen von Office 365 Add-Ons** - Kunden sind verantwortlich für die Bereitstellung-Plug-Ins in der Office 365-Suite, die als notwendig erachtet werden. 

Da Line-of-Business (LOB) apps für jeden Kunden spezifisch sind, sind die Kunden verantwortlich für die Verwaltung von allen Anwendungen innerhalb ihrer Organisation, die nicht von Microsoft bereitgestellt. Dazu gehören:
- Entscheiden, welche apps erforderlich sind, und wer benötigt werden
- Zuweisen von apps auf die Benutzer
- Erstellen und Verwalten von Azure Active Directory (AD) Gruppen für die Verwaltung von app-Zuordnungen 

Der Kunde muss LOB-apps in Intune hoch. Sie sind verantwortlich für die Bereitstellung von, aktualisieren, und Außerbetriebnahme Anwendungsbereiche über ihre jeweiligen Lebenszyklen als auch Unterstützung für diese apps für ihre Benutzer verwalten.

## <a name="office-applications"></a>Office-Anwendungen
Als Teil der Microsoft 365 E5-Lizenz wird von Microsoft Office 365-Standard Suite (64 Bit) bereitgestellt. 

Weitere Informationen hierzu finden Sie unter [Microsoft verwalteter Desktop Technologien](../intro/technologies.md)<!--- and the other applications licensed under Office 365 E5 may be deployed by the customer using Intune’s deployment tools.-->

## <a name="line-of-business-applications"></a>Line-of-Business applications
In dieser Tabelle werden Aufgaben über die verschiedenen Phasen für Applikationen Line-of-Business (LOB) zusammengefasst. 

Anwendung Arbeitsaufgaben |    Kunde    | Microsoft
--- | --- | ---
**Onboarding-apps** |  |
Identifizieren der Anwendungen für Zielgruppen erforderlich ist   | ![ja](images/checkmark.png)  |
Erstellen und Verwalten von Azure Active Directory-Gruppen für die app-Bereitstellung | ![ja](images/checkmark.png) |   
**Verpacken der App** |  |
Paket apps Intune Bereitstellungsstandards erfüllt |  ![ja](images/checkmark.png) |  
Laden Sie apps in Intune | ![ja](images/checkmark.png)     |
Testen von apps in Microsoft verwalteter Desktop-Umgebung |    ![ja](images/checkmark.png) |  
Testen von apps mit den Endbenutzern    | ![ja](images/checkmark.png) |    
**Bereitstellung** | |
Verwalten und Zuweisen von Benutzern für Clientanwendungen  | ![ja](images/checkmark.png)  |
Bereitstellungstools Intune bietet Anwendung Remoteclients| |   ![ja](images/checkmark.png)
Identifizieren und Bereitstellen von Anwendungsupdates durch Intune | ![ja](images/checkmark.png)    |
Deinstallieren und Remove-Anwendungen beim eingestellt wurden    | ![ja](images/checkmark.png) |    
**Verwaltung** | |
Beschaffen und Zuweisen von Lizenzen |   ![ja](images/checkmark.png)     |
Unterstützen Sie die Endbenutzer Line-of-Business-apps  | ![ja](images/checkmark.png) |
Verwalten von app-Einstellungen Remote    | ![ja](images/checkmark.png) |

Informationen zu Anforderungen für LOB-Anwendung finden Sie unter [Anforderungen an Microsoft verwalteten Desktops](../service-description/mmd-app-requirements.md)


## <a name="intune-application-deployment"></a>Bereitstellung einer Anwendung Intune
Verwaltung von kann über das Microsoft verwalteten Desktops Admin-Portal oder über das Portal Intune behandelt werden. Intune des app-Verwaltungsportal werden für Windows, iOS und Android bereitgestellt. Verwaltete Desktops Verwaltungsportal von Microsoft beschränkt die Ansicht für Windows-10-Clientanwendungen. Beide sind über das Portal Azure verfügbar. 
* [Grundlagen der Intune app-Verwaltung](https://docs.microsoft.com/intune/app-management)
* [Hinzufügen von apps zum Intune](https://docs.microsoft.com/intune/app-management)
   * [Hinzufügen einer Line-of-Business-App](https://docs.microsoft.com/intune/lob-apps-windows)
   * [Hinzufügen von Win32-apps auf Intune](https://docs.microsoft.com/intune/apps-win32-app-management)
   * [Hinzufügen von Webanwendungen](https://docs.microsoft.com/intune/web-app)
* [Bereitstellen von apps](https://docs.microsoft.com/intune/apps-deploy)
   * [Bereitstellen von apps für Windows 10](https://docs.microsoft.com/intune/apps-windows-10-app-deploy)
* Unternehmensportal
   * [Bereitstellen der Unternehmensportal](https://docs.microsoft.com/intune/store-apps-company-portal-app)
   * [Konfigurieren der Unternehmen Portal-app](https://docs.microsoft.com/intune/company-portal-app)
