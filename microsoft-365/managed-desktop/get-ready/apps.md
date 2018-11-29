---
title: Vorbereiten von apps für Microsoft verwalteten Desktops
description: ''
keywords: Dokumentation Microsoft verwalteter Desktop, Microsoft-365-Dienst
ms.service: m365-md
author: jdeckerms
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: ebeb54bd5d1f50cbb6f78b1c8ad4a624c449b8c2
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2018
ms.locfileid: "26867762"
---
# <a name="preparing-apps-for-microsoft-managed-desktop"></a>Vorbereiten von apps für Microsoft verwalteten Desktops

<!--This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.-->

<!--Applications: supported/onboard/deployment -->
 
Kunden von Microsoft und Microsoft verwalteter Desktop haben gleichmäßig kritische, noch andere Aufgaben um Anwendungen, die mit Microsoft verwalteter Desktop verwendet.

## <a name="microsoft-responsibilites"></a>Microsoft responsibilites
**Apps für Office 365** Microsoft stellt die gesamten Diensts für die Bereitstellung, Update und Unterstützung für bestimmte apps für Office 365 bereit. Alle Benutzer erhält den Basis Satz von Office 365 klicken Sie auf Ausführen, 64-Bit-Version von Anwendungen in das Gerät Bild eingeschlossen werden, sodass ein Benutzer schneller produktiv werden kann. Die Project und Visio-Anwendungen in der Office 365-Suite werden separat lizenziert.  Microsoft verwalteter Desktop wird Bereitstellungsgruppen ermöglicht es dem IT-Administrator zum Verwalten von Lizenzen und Bereitstellen dieser Anwendungen entsprechend für ihre Organisation bereitstellen. Microsoft unterstützt Endbenutzer dieser Anwendungen die Kanäle Microsoft Managed Desktop zu unterstützen.

**Line-of-Business-apps** Microsoft bietet Tools für IT-Administratoren zum Verwalten und ihre Line of Business Applications für Endbenutzer als Bestandteil des Produkts Intune bereitstellen. Microsoft unterstützt Anwendung Bereitstellungsprobleme wie in [LOB Anwendungen](#line-of-business-applications) 

**Bereitstellen mit Intune** Intune wird an den **Microsoft Store for Business** während Microsoft verwalteter Desktop Onboarding beschaffte apps durch Intune bereitgestellt werden, sodass verknüpft werden. Microsoft wird auch die Web-basierten Version des Unternehmens Portals Endbenutzer bereitstellen, damit IT-Administratoren eine Benutzeroberfläche Self-service für Endbenutzer bereitstellen können.

**App-Verwaltung** Microsoft kann eingeschränkte Applications identifizieren, die aufgrund von deren Einfluss System nicht für die moderne Jahrestag geeignet sind. Wenn eine solche Anwendung identifiziert wird Microsoft benachrichtigt den Kunden und dieser Anwendung müssen aus den Mandanten entfernt werden soll. 

## <a name="customer-responsibilities"></a>Kundenverantwortlichkeiten
Die Office 365-Suite ist der Kern Microsofts Produktivität angeboten und ist in der Microsoft-365-Lizenz für alle Benutzer von Microsoft verwalteten Desktops enthalten. Während Microsoft bereitstellt, aktualisiert und unterstützt die Office-Programme auf Microsoft verwaltete Desktops Geräte immer noch einige Bereiche für die der Kunde zuständig ist.
- **Zuweisen von Lizenzen** - Kunden sind verantwortlich für die Endbenutzer auf Office 365 die entsprechenden Lizenzen zuweisen. 
- **Hinzufügen von Benutzern zu Sicherheitsgruppen** - muss Kunden mit Benutzern, Project oder Visio, benötigen, der IT-Administrator diese Benutzer die entsprechenden Bereitstellungsgruppen hinzufügen. IT-Administratoren sind auch für das Ende der Lebensdauer für diese Benutzer verwalten verantwortlich. 
- **Bereitstellen von Office 365 Add-Ons** - Kunden sind verantwortlich für die Bereitstellung-Plug-Ins in der Office 365-Suite, die als notwendig erachtet werden. 

Da Line-of-Business (LOB) apps für jeden Kunden spezifisch sind, sind die Kunden verantwortlich für die Verwaltung von allen Anwendungen innerhalb ihrer Organisation, die nicht von Microsoft bereitgestellt. Dazu gehören:
- Entscheiden, welche apps erforderlich sind, und wer benötigt werden
- Zuweisen von apps auf die Benutzer
- Erstellen und Verwalten von Azure Active Directory (AD) Gruppen für die Verwaltung von app-Zuordnungen 

Nachdem die Kerngruppe von LOB-apps identifiziert wurde wird der Kunde beschaffen, lizenzieren, Packen und testen diese Anwendung in der Umgebung Microsoft verwalteten Desktops. Der Kunde muss hochladen und Bereitstellen von Anwendungen für den Intune bereitstellen, aktualisieren und außer Betrieb nehmen ihre LOB-Anwendungen. Kunden sind verantwortlich für die Verwaltung von LOB-apps-Unterstützung für die Benutzer.
 

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

## <a name="resources"></a>Ressourcen
Viele Dienste außerhalb des Gültigkeitsbereichs für Microsoft verwalteter Desktop Vorgänge sind werden Dienste, welche Microsoft bietet die der Kunde Ihnen möglicherweise weiterhelfen ihre Anwendungen zu verwalten.

### <a name="windows-upgrade-readiness"></a>Windows-Upgradebereitschaft
Ein wichtiger Teil der Einrichtung der neuen Microsoft verwalteten Geräten ist Verständnis dafür, welche apps Gerätebenutzer benötigt werden. Windows-Upgrade-Bereitschaft ist ein Microsoft-Tool, mit dem kann Unternehmen die Anwendung im Querformat innerhalb ihres Unternehmens zu verstehen, und Registrierungsschlüsseldaten zu diesen Anwendungen wie überprüfen:

- **Anwendungsverwendung** - Telemetriedaten wird verwendet, um die Anwendungsverwendung von zu überwachen.
- **Anwendungskompatibilität** - Upgrade-Bereitschaft befasst sich mit jeder Anwendung und sieht wie weit verbreitet es auf die neueste Version von Windows 10 bereitgestellt wurde und wie identifiziert ist "Bereit für Windows" bewertet. Diese Daten können Testen auf Anwendungen, die bereits verbreitet sind nicht den Fokus.

### <a name="intune-application-deployment"></a>Bereitstellung einer Anwendung Intune
Verwaltung von kann über das Microsoft verwalteten Desktops Admin-Portal oder über das Portal Intune behandelt werden. Intune des app-Verwaltungsportal werden für Windows, iOS und Android bereitgestellt. Verwaltete Desktops Verwaltungsportal von Microsoft beschränkt die Ansicht für Windows-10-Clientanwendungen. Beide sind über das Portal Azure verfügbar. 
- [Grundlagen der Intune app-Verwaltung](https://docs.microsoft.com/intune/app-management)
- [Hinzufügen einer Anwendung Windows 32](https://docs.microsoft.com/intune/lob-apps-windows)
- [Hinzufügen von Webanwendungen](https://docs.microsoft.com/intune/web-app)
- [Zuweisen und Bereitstellen von apps für Benutzergruppen](https://docs.microsoft.com/intune/apps-deploy)

### <a name="application-packaging-standards"></a>Anwendung Packen Standards (engl.)
Verpackt, um Windows 32 Applikationen über Intune bereitstellen, müssen sie entweder als Single-Wert. MSI, ein .appx oder. MSIX. Der am häufigsten verwendete Pakettyp für Intune ist aktuell. MSI-DATEI.
