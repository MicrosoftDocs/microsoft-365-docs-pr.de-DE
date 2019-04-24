---
title: Vorbereiten von Apps für Microsoft Managed Desktop
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.collection: M365-modern-desktop
ms.openlocfilehash: be28760fc3facdb21643943ace11deda378d437c
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32289065"
---
# <a name="preparing-apps-for-microsoft-managed-desktop"></a>Vorbereiten von Apps für Microsoft Managed Desktop

<!--This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.-->

<!--Applications: supported/onboard/deployment -->
 
Microsoft und Microsoft Managed Desktop-Kunden haben gleichermaßen kritische, aber unterschiedliche Aufgaben bei Anwendungen, die mit Microsoft Managed Desktop verwendet werden.

## <a name="microsoft-responsibilities"></a>Microsoft-Verantwortlichkeiten
**Office 365-apps** Microsoft stellt den vollständigen Dienst für die Bereitstellung, Aktualisierung und Unterstützung bestimmter Office 365-apps bereit. Alle Benutzer erhalten den Basissatz von Office 365 Click to Run, 64-Bit-Version von Anwendungen, die im Bild des Geräts enthalten sind, damit ein Benutzer schnell produktiv werden kann. Die Project-und Visio-Anwendungen in der Office 365-Suite werden separat lizenziert.  Microsoft Managed Desktop stellt Bereitstellungsgruppen bereit, die es dem IT-Administrator ermöglichen, Lizenzen zu verwalten und diese Anwendungen entsprechend für Ihre Organisation bereitzustellen. Microsoft unterstützt Endbenutzer dieser Anwendungen über die Microsoft Managed Desktop Support-Kanäle.

**Branchenspezifische apps** Microsoft bietet IT-Administratoren Tools für die Verwaltung und Bereitstellung von Branchenanwendungen für Endbenutzer als Teil des InTune-Produkts. Microsoft unterstützt Anwendungs Bereitstellungsprobleme, die in Branchen [Anwendungen](#line-of-business-applications) ausführlich beschrieben werden. 

**Bereitstellen mit InTune** InTune wird während des onboardings von Microsoft Managed Desktop mit dem **Microsoft Store for Business** verknüpft, sodass beschaffte Apps über InTune bereitgestellt werden können. Microsoft stellt die Unternehmens Portal Anwendung auch vom Microsoft Store für Endbenutzer bereit, sodass IT-Administratoren eine Self-Service-Erfahrung für Ihre Endbenutzer bereitstellen können.

**App-Verwaltung** Microsoft kann eingeschränkte Anwendungen identifizieren, die aufgrund ihrer System Auswirkung nicht für den modernen Arbeitsbereich geeignet sind. Wenn eine solche Anwendung identifiziert wird, benachrichtigt Microsoft den Kunden, und die Anwendung muss aus dem Mandanten entfernt werden. 

Weitere Informationen zu eingeschränkten App-Verhaltensweisen und App-Anforderungen finden Sie unter [Microsoft Managed Desktop App Requirements](../service-description/mmd-app-requirements.md)

## <a name="customer-responsibilities"></a>Verantwortlichkeiten des Kunden
Die Office 365-Suite ist Kern des Produktivitäts Angebots von Microsoft und ist in der Microsoft 365-Lizenz für alle Microsoft Managed Desktop-Benutzer enthalten. Während Microsoft Office-Anwendungen auf verwalteten Desktop Geräten von Microsoft bereitstellt, aktualisiert und unterstützt, gibt es noch einige Bereiche, für die der Kunde verantwortlich ist.
- **Lizenzen zuweisen** – Kunden sind für das Zuweisen der entsprechenden Lizenzen zu Endbenutzern für Office 365 verantwortlich. 
- **Hinzufügen von Benutzern zu Sicherheitsgruppen** – für Kunden mit Benutzern, die Project oder Visio benötigen, muss der IT-Administrator diese Benutzer den entsprechenden Bereitstellungsgruppen hinzufügen. IT-Administratoren sind auch für die Verwaltung der Lebensdauer für diese Benutzer verantwortlich. 
- **Deploy office 365 Add ons** -Kunden sind für die Bereitstellung von Plugins für die Office 365-Suite verantwortlich, die als notwendig erachtet werden. 

Da BRANCHENspezifische Apps für jeden Kunden eindeutig sind, sind Kunden für die Verwaltung aller Anwendungen in Ihrer Organisation verantwortlich, die nicht von Microsoft bereitgestellt werden. Dies umfasst Folgendes:
- Entscheiden, welche apps benötigt werden und wer Sie benötigt
- Zuweisen von apps zu diesen Benutzern
- Erstellen und Verwalten von Azure Active Directory (AD)-Gruppen für die Verwaltung von App-Zuweisungen 

Der Kunde muss LOB-apps in InTune hochladen. Sie sind dann für die Bereitstellung, Aktualisierung und Außerbetriebnahme dieser Anwendungen über die jeweiligen Lebenszyklen verantwortlich und verwalten die Unterstützung für diese apps für Ihre Benutzer.

## <a name="office-applications"></a>Office-Anwendungen
Im Rahmen der Microsoft 365 E5-Lizenz wird Office 365 Standard Suite (64-Bit) von Microsoft bereitgestellt. 

Weitere Informationen finden Sie unter [Microsoft Managed Desktop Technologies](../intro/technologies.md) <!--- and the other applications licensed under Office 365 E5 may be deployed by the customer using Intune’s deployment tools.-->

## <a name="line-of-business-applications"></a>Branchenanwendungen
In dieser Tabelle werden die Verantwortlichkeiten für die verschiedenen Phasen von Branchenanwendungen zusammengefasst. 

Anwendungs Arbeitselemente |    Kunde    | Microsoft
--- | --- | ---
**Onboarding-apps** |  |
Identifizieren von Anwendungen, die für bestimmte Benutzergruppen erforderlich sind   | ![ja](images/checkmark.png)  |
Erstellen und Verwalten von Azure AD-Gruppen für die APP-Bereitstellung | ![ja](images/checkmark.png) |   
**App-Verpackungen** |  |
Paket-Apps zur Erfüllung der InTune-Bereitstellungsstandards |  ![ja](images/checkmark.png) |  
Hochladen von apps in InTune | ![ja](images/checkmark.png)     |
Testen von apps in Microsoft Managed Desktop Environment |    ![ja](images/checkmark.png) |  
Testen von apps mit Endbenutzern    | ![ja](images/checkmark.png) |    
**Bereitstellung** | |
Verwalten und Zuweisen von Benutzern zu Anwendungen  | ![ja](images/checkmark.png)  |
InTune-Bereitstellungstools für Remoteclients| |   ![ja](images/checkmark.png)
Identifizieren und Bereitstellen von Anwendungsupdates über InTune | ![ja](images/checkmark.png)    |
Unistall und Entfernen von Anwendungen, wenn Sie zurückgezogen wurden    | ![ja](images/checkmark.png) |    
**Verwaltung** | |
Erwerben und Zuweisen von Lizenzen |   ![ja](images/checkmark.png)     |
Unterstützung von Endbenutzern für Branchen-apps  | ![ja](images/checkmark.png) |
Remoteverwaltung von App-Einstellungen    | ![ja](images/checkmark.png) |

Informationen zu Anforderungen an Branchenanwendungen finden Sie unter [Microsoft Managed Desktop Application Requirements](../service-description/mmd-app-requirements.md)


## <a name="intune-application-deployment"></a>InTune-Anwendungsbereitstellung
Die Anwendungsverwaltung kann über das Microsoft Managed Desktop-Verwaltungsportal oder über das InTune-Portal behandelt werden. Intunes App-Verwaltungsportal zeigt Anwendungen, die für Windows, Android und iOS bereitgestellt werden. Microsoft Managed Desktop Admin Portal schränkt die Ansicht auf Windows 10-Anwendungen ein. Beide sind über das Azure-Portal verfügbar. 
* [InTune-Grundlagen der APP-Verwaltung](https://docs.microsoft.com/intune/app-management)
* [Hinzufügen von apps zu InTune](https://docs.microsoft.com/intune/app-management)
   * [Hinzufügen einer Branchen-App](https://docs.microsoft.com/intune/lob-apps-windows)
   * [Hinzufügen von Win32-apps zu InTune](https://docs.microsoft.com/intune/apps-win32-app-management)
   * [Hinzufügen von Webanwendungen](https://docs.microsoft.com/intune/web-app)
* [Bereitstellen von apps](https://docs.microsoft.com/intune/apps-deploy)
   * [Bereitstellen von apps auf Windows 10](https://docs.microsoft.com/intune/apps-windows-10-app-deploy)
* Unternehmens Portal
   * [Bereitstellen des Unternehmensportals](https://docs.microsoft.com/intune/store-apps-company-portal-app)
   * [Konfigurieren der Unternehmens Portal-App](https://docs.microsoft.com/intune/company-portal-app)
