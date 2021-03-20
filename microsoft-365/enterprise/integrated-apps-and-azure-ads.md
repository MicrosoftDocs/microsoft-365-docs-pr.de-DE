---
title: Integrierte Apps und Azure AD für Microsoft 365-Administratoren
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
description: Erfahren Sie, wie Sie integrierte Office 365-Apps in Azure AD registrieren und verwalten, sodass App-Autorisierungen auf globaler Administratorebene zulässig sind.
ms.openlocfilehash: 0b7392984b77b01abb0992fea5db62b80ed9fb6c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909774"
---
# <a name="integrated-apps-and-azure-ad-for-microsoft-365-administrators"></a>Integrierte Apps und Azure AD für Microsoft 365-Administratoren

Es gibt mehr zum Verwalten integrierter Apps als nur zum Verwalten der Zustimmung des Benutzers [zu Apps.](../admin/misc/user-consent.md) Mit dem Aufkommen der Microsoft 365-REST-APIs können Benutzer Apps Zugriff auf ihre Microsoft 365-Daten gewähren, z. B. E-Mails, Kalender, Kontakte, Benutzer, Gruppen, Dateien und Ordner. Standardmäßig müssen Benutzer jeder App einzeln Berechtigungen erteilen. 

Dies kann jedoch nicht gut skaliert werden, wenn Sie eine App einmal auf globaler Administratorebene autorisieren und sie über das App-Startfeld für Ihre gesamte Organisation ausführen möchten. Dazu müssen Sie die App in Azure Active Directory (Azure AD) registrieren. Es gibt einige Schritte, die Sie ausführen müssen, bevor Sie eine App in Azure AD registrieren können, und einige Hintergrundinformationen, die Ihnen bei der Verwaltung von Apps in Ihrer Microsoft 365-Organisation helfen sollten.
  
## <a name="azure-ad-resources-for-microsoft-365-admins"></a>Azure AD-Ressourcen für Microsoft 365-Administratoren

Sie müssen diese beiden Aufgaben ausführen, bevor Sie Ihre Microsoft 365-Apps in Azure AD verwalten können.
  
|Voraussetzungen|Kommentare|
|:-----|:-----|
|[Verwenden Ihres kostenlosen Azure AD-Abonnements](../compliance/use-your-free-azure-ad-subscription-in-office-365.md) <br/> |Jedes kostenpflichtige Abonnement von Microsoft 365 verfügt über ein kostenloses Abonnement für Azure AD. Sie können Azure AD verwenden, um Ihre Apps zu verwalten und Benutzer- und Gruppenkonten zu erstellen und zu verwalten. Um Azure AD zu verwenden, wechseln Sie einfach zum Azure-Portal unter, und melden Sie [https://portal.azure.com](https://portal.azure.com) sich mit Ihrem Microsoft 365-Konto an.  <br/> |
|[Verwalten der Zustimmung des Benutzers zu Apps](../admin/misc/user-consent.md) <br/> |Sie müssen die Zustimmung des Benutzers zu Apps verwalten, damit Apps von Drittanbietern auf Microsoft 365-Benutzerinformationen zugreifen und Apps in Azure AD registrieren können. Wenn beispielsweise jemand eine App eines Drittanbieters verwendet, könnte diese App Berechtigungen für den Zugriff auf den Kalender des Benutzers anfordern sowie zum Bearbeiten von Dateien, die sich in einem OneDrive-Ordner befinden.  <br/> |
   
Für die Verwaltung von Microsoft 365-Apps benötigen Sie Kenntnisse über Apps in Azure AD. Verwenden Sie diese Artikel, um Ihnen den hintergrund zu geben, den Sie benötigen.
  
|Artikel|Kommentare|
|:-----|:-----|
|[Treffen des Microsoft 365-App-Startfelds](https://support.microsoft.com/office/meet-the-microsoft-365-app-launcher-79f12104-6fed-442f-96a0-eb089a3f476a) <br/> |Wenn Sie neu im App-Startfeld sind, fragen Sie sich möglicherweise, was es ist und wie Sie es verwenden. Das App-Startfeld ist so konzipiert, dass Sie von überall in Microsoft 365 zu Ihren Apps wechseln können.  <br/> |
|[Übersicht über Office 365-Verwaltungs-APIs](/office/office-365-management-api/office-365-management-apis-overview) <br/> |Mit den Microsoft 365-Verwaltungs-APIs können Sie Zugriff auf Ihre Microsoft 365-Daten bereitstellen, einschließlich der Dinge, die ihnen am wichtigsten sind– E-Mails, Kalender, Kontakte, Benutzer und Gruppen, Dateien und Ordner. <br/> |
|[Integrieren von Anwendungen in Azure AD](/azure/active-directory/develop/quickstart-v1-add-azure-ad-app) <br/> | Erfahren Sie mehr über anwendungen, die in Azure AD integriert sind, und erfahren Sie, wie Sie Ihre Anwendung registrieren, Konzepte hinter einer registrierten Anwendung verstehen und mehr über Brandingrichtlinien für Mehr-Mandanten-Anwendungen erfahren.  <br/> |
|[Hinzufügen benutzerdefinierter Kacheln zum App-Startfeld](/office365/admin/manage/customize-the-app-launcher)  <br/> |Das App-Startfeld in Microsoft 365 erleichtert Benutzern das Suchen und Zugreifen auf ihre Apps. In diesem Artikel wird beschrieben, wie Sie als Entwickler Ihre Apps in den App-Start starters der Benutzer angezeigt bekommen und ihnen auch eine einmalige Anmeldung (Single Sign-On, SSO) mithilfe ihrer Microsoft 365-Anmeldeinformationen ermöglichen können.  <br/> |
|[Lernprogramme zur Azure AD-Integration](/azure/active-directory/saas-apps/tutorial-list) <br/> |Das Ziel dieser Lernprogramme besteht darin, Ihnen zu zeigen, wie Sie Azure AD SSO für Drittanbieter-SaaS-Anwendungen konfigurieren.  <br/> |
|[Authentifizierungsszenarien für Azure AD](/azure/active-directory/develop/authentication-vs-authorization) <br/> |Azure AD vereinfacht die Authentifizierung für Entwickler, indem identität als Dienst bereitgestellt wird, mit Unterstützung für Branchenstandardprotokolle wie OAuth 2.0 und OpenID Connect sowie Open Source-Bibliotheken für verschiedene Plattformen, die Ihnen helfen, schnell mit der Codierung zu beginnen. Dieses Dokument hilft Ihnen, die verschiedenen Von Azure AD unterstützten Szenarien zu verstehen und zeigt Ihnen, wie Sie beginnen können.  <br/> |
|[Anwendungszugriff](/azure/active-directory/manage-apps/what-is-access-management) <br/> |Azure AD ermöglicht eine einfache Integration in viele der gängigen Software as a Service (SaaS)-Anwendungen von heute. Es bietet Identitäts- und Zugriffsverwaltung und stellt eine Zugriffssteuerung für Benutzer zur Verfügung, in der sie ermitteln können, welchen Anwendungszugriff sie haben und wo sie SSO für den Zugriff auf ihre Anwendungen verwenden können. Dieser Artikel enthält Links zu den zugehörigen Ressourcen, mit denen Sie mehr über die Anwendungszugriffsverbesserungen für Azure AD und deren Beiträge erfahren können.  <br/> |
|[Personalisieren Ihrer Office 365-Erfahrung](https://support.microsoft.com/office/personalize-your-office-365-experience-eb34a21b-52fa-4fbf-a8d5-146132242985) <br/> |Sie können schnell auf die Apps zugreifen, die Sie täglich verwenden, indem Sie Apps im Microsoft 365-App-Startfeld hinzufügen oder entfernen.  <br/> |