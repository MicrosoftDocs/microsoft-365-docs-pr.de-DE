---
title: Azure-Integration in Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- M365-identity-device-management
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: a5efce5d-9c9c-4190-b61b-fd273c1d425f
description: Integrieren Sie Microsoft 365 in Azure AD, wenn Sie eine Kennwortsynchronisierung oder einmaliges Anmelden in Ihre lokale Umgebung wünschen.
ms.openlocfilehash: f977969634401d59d7598136f9323cb0e37f9ece
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905332"
---
# <a name="azure-integration-with-microsoft-365"></a>Azure-Integration in Microsoft 365

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Microsoft 365 verwendet Azure Active Directory (Azure AD) zum Verwalten von Benutzeridentitäten hinter den Kulissen. Ihr Microsoft 365-Abonnement umfasst ein kostenloses Azure AD-Abonnement, damit Sie Ihre lokalen Active Directory Domain Services (AD DS) integrieren können, um Benutzerkonten und Kennwörter zu synchronisieren oder einmaliges Anmelden einrichten zu können. Sie können auch erweiterte Features erwerben, um Ihre Konten besser zu verwalten.
  
Azure AD bietet auch andere Funktionen, z. B. die Verwaltung integrierter Apps, die Sie zum Erweitern und Anpassen Ihrer Microsoft 365-Abonnements verwenden können.
  
Sie können die Azure AD-Bereitstellungsratgeber für eine geführte Einrichtung und Konfiguration im Microsoft 365 Admin Center verwenden (Sie müssen bei Microsoft 365 angemeldet sein):

 - [Azure AD Connect-Ratgeber](https://aka.ms/aadconnectpwsync)
 - [Bereitstellungsratgeber für AD FS](https://aka.ms/adfsguidance)
 - [Azure AD-Einrichtungshandbuch](https://aka.ms/aadpguidance)
  
## <a name="azure-ad-editions-and-microsoft-365-identity-management"></a>Azure AD-Editionen und Microsoft 365-Identitätsverwaltung

Wenn Sie über ein kostenpflichtiges Abonnement für Microsoft 365 verfügen, haben Sie auch ein kostenloses Azure AD-Abonnement. Sie können Azure AD verwenden, um Benutzer- und Gruppenkonten zu erstellen und zu verwalten. Um dieses Abonnement zu aktivieren, müssen Sie eine einmalregistrierung abschließen. Anschließend können Sie über Ihr Microsoft 365 Admin Center auf Azure AD zugreifen. 

Anweisungen zur Registrierung Ihres kostenlosen Azure AD-Abonnements finden Sie [unter Verwenden Ihres kostenlosen Azure AD-Abonnements.](../compliance/use-your-free-azure-ad-subscription-in-office-365.md) Gehen Sie nicht direkt zu azure.microsoft.com, um sich zu registrieren, oder Sie erhalten ein Test- oder kostenpflichtiges Abonnement für Microsoft Azure, das von Ihrem kostenlosen Azure AD-Abonnement mit Microsoft 365 getrennt ist. 
  
Mit dem kostenlosen Abonnement können Sie mit lokalen Verzeichnissen synchronisieren, einmaliges Anmelden einrichten und mit vielen Software als Dienstanwendungen synchronisieren, z. B. Salesforce, DropBox und viele mehr.
  
Wenn Sie erweiterte AD DS-Funktionen, bidirektionale Synchronisierung und andere Verwaltungsfunktionen wünschen, können Sie Ihr kostenloses Abonnement auf ein kostenpflichtiges Premium-Abonnement aktualisieren. Weitere Informationen finden Sie unter [Azure Active Directory Editions](https://azure.microsoft.com/pricing/details/active-directory/).
  
Weitere Informationen zu Microsoft 365 und Azure AD finden Sie unter [Microsoft 365 Identity Models](about-microsoft-365-identity.md).
  
## <a name="extend-the-capabilities-of-your-microsoft-365-tenant"></a>Erweitern der Funktionen Ihres Microsoft 365-Mandanten

|**Feature**|**Beschreibung**|
|:-----|:-----|
|Integrierte Apps  <br/> |Sie können einzelnen Apps Zugriff auf Ihre Microsoft 365-Daten gewähren, z. B. E-Mails, Kalender, Kontakte, Benutzer, Gruppen, Dateien und Ordner. Sie können diese Apps auch auf globaler Administratorebene autorisieren und für Ihr gesamtes Unternehmen verfügbar machen, indem Sie die Apps in Azure AD registrieren. Weitere Informationen finden Sie unter [Integrierte Apps und Azure AD für Microsoft 365-Administratoren.](integrated-apps-and-azure-ads.md)  <br/> Weitere Informationen finden [Sie unter Einmaliges Anmelden](/azure/active-directory/manage-apps/what-is-single-sign-on).  <br/> |
|PowerApps  <br/> | Power apps are focused apps for mobile devices that can connect to your existing data sources like SharePoint lists and other data apps. Weitere Informationen finden Sie unter Erstellen einer [PowerApp für eine Liste in SharePoint Online](https://support.office.com/article/9338b2d2-67ac-4b81-8e67-97da27e5e9ab) und auf der [PowerApps-Seite.](https://powerapps.microsoft.com/)  <br/> |
   
## <a name="see-also"></a>Siehe auch

[Übersicht zu Microsoft 365 Enterprise](microsoft-365-overview.md)