---
title: Integrierte apps und Azure AD für Microsoft 365 Administratoren
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.collection: M365-subscription-management
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: cb2250e3-451e-416f-bf4e-363549652c2a
description: Hier erfahren Sie, wie Sie Office 365 integrierte apps in Azure AD registrieren und verwalten können, sodass App-Autorisierungen auf globaler Administratorebene möglich sind.
ms.openlocfilehash: 1e84b5e6f82848bf1d100004bcd2711ad2e9ed39
ms.sourcegitcommit: 11d1044c6600b1f568b6dc8a53db9b07f2f0ad1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/08/2020
ms.locfileid: "48384899"
---
# <a name="integrated-apps-and-azure-ad-for-microsoft-365-administrators"></a>Integrierte apps und Azure AD für Microsoft 365 Administratoren

Es gibt mehr zur Verwaltung integrierter apps, als nur die [Benutzer Zustimmung zu apps zu verwalten](https://docs.microsoft.com/microsoft-365/admin/misc/integrated-apps). Mit dem Aufkommen der Microsoft 365-Rest-APIs können Benutzer apps Zugriff auf Ihre Microsoft 365-Daten gewähren, beispielsweise e-Mails, Kalender, Kontakte, Benutzer, Gruppen, Dateien und Ordner. Standardmäßig müssen Benutzer jeder App Berechtigungen einzeln erteilen. 

Dies ist jedoch nicht gut skalierbar, wenn Sie eine APP einmal auf globaler Administratorebene autorisieren und über das App-Startfeld auf Ihre gesamte Organisation Ausrollen möchten. Hierzu müssen Sie die app in Azure Active Directory (Azure AD) registrieren. Es gibt einige Schritte, die Sie ausführen müssen, bevor Sie eine app in Azure AD registrieren können, sowie einige Hintergrundinformationen, die Sie kennen sollten, die Ihnen bei der Verwaltung von apps in Ihrer Microsoft 365-Organisation helfen können.
  
## <a name="azure-ad-resources-for-microsoft-365-admins"></a>Azure AD Ressourcen für Microsoft 365-Administratoren

Sie müssen diese beiden Aufgaben durchführen, bevor Sie Ihre Microsoft 365-apps in Azure AD verwalten können.
  
|Voraussetzungen|Kommentare|
|:-----|:-----|
|[Verwenden Ihres kostenlosen Azure AD-Abonnements](https://docs.microsoft.com/microsoft-365/compliance/use-your-free-azure-ad-subscription-in-office-365) <br/> |Jedes kostenpflichtige Abonnement für Microsoft 365 wird mit einem kostenlosen Abonnement für Azure AD ausgeliefert. Sie können Azure AD verwenden, um Ihre apps zu verwalten und Benutzer-und Gruppenkonten zu erstellen und zu verwalten. Um Azure AD zu verwenden, wechseln Sie einfach zum Azure-Portal unter, [https://portal.azure.com](https://portal.azure.com) und melden Sie sich mit Ihrem Microsoft 365-Konto an.  <br/> |
|[Benutzergenehmigung für apps verwalten](https://docs.microsoft.com/microsoft-365/admin/misc/integrated-apps) <br/> |Sie müssen die Benutzer Zustimmung zu apps verwalten, damit Drittanbieter-apps auf Benutzerinformationen von Microsoft 365 zugreifen können, und Sie können apps in Azure AD registrieren. Wenn beispielsweise jemand eine App eines Drittanbieters verwendet, könnte diese App Berechtigungen für den Zugriff auf den Kalender des Benutzers anfordern sowie zum Bearbeiten von Dateien, die sich in einem OneDrive-Ordner befinden.  <br/> |
   
Für die Verwaltung von Microsoft 365-apps müssen Sie über Kenntnisse von apps in Azure AD verfügen. Verwenden Sie diese Artikel, um Ihnen den benötigten Hintergrund zu geben.
  
|Artikel|Kommentare|
|:-----|:-----|
|[Treffen des Microsoft 365-App-Startprogramms](https://support.microsoft.com/office/meet-the-microsoft-365-app-launcher-79f12104-6fed-442f-96a0-eb089a3f476a) <br/> |Wenn Sie neu im App-Startfeld sind, Fragen Sie sich vielleicht, was es ist und wie Sie es verwenden. Das App-Startfeld ist so konzipiert, dass Sie von überall in Microsoft 365 auf Ihre apps zugreifen können.  <br/> |
|[Übersicht über die Office 365-Verwaltungs-APIs](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview) <br/> |Mit den Microsoft 365-Verwaltungs-APIs können Sie Zugriff auf Ihre Microsoft 365-Daten bereitstellen, einschließlich der Dinge, die Ihnen am meisten wichtig sind: e-Mails, Kalender, Kontakte, Benutzer und Gruppen, Dateien und Ordner. <br/> |
|[Integrieren von Anwendungen in Azure AD](https://docs.microsoft.com/azure/active-directory/develop/quickstart-v1-add-azure-ad-app) <br/> | Erfahren Sie mehr über Anwendungen, die in Azure AD integriert sind, und wie Sie Ihre Anwendung registrieren, Konzepte hinter einer registrierten Anwendung verstehen und Informationen zu Branding-Richtlinien für mehrmandantenfähige Anwendungen erhalten.  <br/> |
|[Hinzufügen von benutzerdefinierten Kacheln zum App-Startfeld](https://docs.microsoft.com/office365/admin/manage/customize-the-app-launcher)  <br/> |Das App-Startfeld in Microsoft 365 erleichtert Benutzern die Suche und den Zugriff auf Ihre apps. In diesem Artikel werden die Möglichkeiten beschrieben, wie Sie als Entwickler ihre apps in den App-Startprogrammen von Benutzern anzeigen und Ihnen außerdem eine einmalige Anmeldung (SSO) mit Ihren Microsoft 365-Anmeldeinformationen ermöglichen können.  <br/> |
|[Azure AD Integrations-Lernprogramme](https://docs.microsoft.com/azure/active-directory/saas-apps/tutorial-list) <br/> |Das Ziel dieser Lernprogramme ist es, Ihnen zu zeigen, wie Sie Azure AD SSO für SaaS-Anwendungen von Drittanbietern konfigurieren.  <br/> |
|[Authentifizierungsszenarien für Azure AD](https://go.microsoft.com/fwlink/?LinkId=617145) <br/> |Azure AD vereinfacht die Authentifizierung für Entwickler durch die Bereitstellung von Identität als Dienst, mit Unterstützung für Branchenstandard Protokolle wie OAuth 2,0 und OpenID Connect sowie Open Source-Bibliotheken für verschiedene Plattformen, mit denen Sie schnell mit der Codierung beginnen können. Dieses Dokument hilft Ihnen, die verschiedenen Szenarien zu verstehen Azure Ad unterstützt und zeigt Ihnen, wie Sie beginnen.  <br/> |
|[Anwendungszugriff](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-access-management) <br/> |Azure AD ermöglicht eine einfache Integration in viele der heute gängigen Software as a Service (SaaS)-Anwendungen. Es bietet Identitäts-und Zugriffsverwaltung und bietet eine Zugriffsgruppe für Benutzer, in der Sie ermitteln können, welche Anwendungs Zugriffe Sie haben und wo Sie SSO verwenden können, um auf Ihre Anwendungen zuzugreifen. In diesem Artikel finden Sie Links zu den zugehörigen Ressourcen, in denen Sie weitere Informationen zu den Anwendungszugriffs Verbesserungen für Azure AD und dazu beitragen können.  <br/> |
|[Personalisieren Ihrer Office 365 Erfahrung](https://support.microsoft.com/office/personalize-your-office-365-experience-eb34a21b-52fa-4fbf-a8d5-146132242985) <br/> |Sie können schnellen Zugriff auf die apps erhalten, die Sie täglich verwenden, indem Sie apps im Microsoft 365 App Launcher hinzufügen oder entfernen.  <br/> |

