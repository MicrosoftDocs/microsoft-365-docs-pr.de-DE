---
title: Azure-Integration mit Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/09/2019
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
description: Integrieren Sie Microsoft 365 mit Azure AD, wenn Sie die Kennwortsynchronisierung oder das einmalige Anmelden mit Ihrer lokalen Umgebung wünschen.
ms.openlocfilehash: 045760f000abdbf053e09d89b296fbafa4c24786
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690836"
---
# <a name="azure-integration-with-microsoft-365"></a>Azure-Integration mit Microsoft 365

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Microsoft 365 verwendet Azure Active Directory (Azure AD), um Benutzeridentitäten hinter den Kulissen zu verwalten. Ihr Microsoft 365-Abonnement enthält ein kostenloses Abonnement für Azure AD, damit Sie Microsoft 365 mit Azure AD integrieren können, wenn Sie Kennwörter synchronisieren oder einmaliges Anmelden mit Ihrer lokalen Umgebung einrichten möchten. Sie können auch erweiterte Funktionen erwerben, um Ihre Konten besser zu verwalten.
  
Azure bietet auch andere Funktionen wie das Verwalten integrierter apps, mit denen Sie Ihre Microsoft 365-Abonnements erweitern und anpassen können.
  
Sie können die Azure AD-Bereitstellungs Ratgeber für eine gesteuerte Setup-und Konfigurationsumgebung verwenden (Sie müssen bei Microsoft 365 angemeldet sein):

 - [Azure AD Connect-Ratgeber](https://aka.ms/aadconnectpwsync)
 - [Bereitstellungsratgeber für AD FS](https://aka.ms/adfsguidance)
 - [Azure AD-Installationshandbuch](https://aka.ms/aadpguidance)
  
## <a name="azure-ad-editions-and-microsoft-365-identity-management"></a>Azure AD Editionen und Microsoft 365 Identity Management

Wenn Sie ein kostenpflichtiges Abonnement für Microsoft 365 haben, haben Sie auch ein kostenloses Abonnement für Azure AD. Sie können Azure AD verwenden, um Benutzer-und Gruppenkonten zu erstellen und zu verwalten. Um dieses Abonnement zu aktivieren, müssen Sie eine einmalige Registrierung durchführen. Anschließend können Sie über Ihr Microsoft 365 Admin Center auf Azure AD zugreifen. 

Anweisungen finden Sie unter [Verwenden Ihres kostenlosen Azure AD-Abonnements](https://go.microsoft.com/fwlink/p/?LinkId=617127). Befolgen Sie die Anweisungen, um das ﻿kostenlose Azure AD-Abonnement zu registrieren, das mit Ihrem Abonnement für Microsoft 365 geliefert wird. Gehen Sie nicht direkt zu Azure.Microsoft.com, um sich anzumelden, oder Sie erhalten ein Test-oder kostenpflichtiges Abonnement für Microsoft Azure, das von Ihrer kostenlosen Version für Microsoft 365 getrennt ist. 
  
Mit dem kostenlosen Abonnement können Sie mit lokalen Verzeichnissen synchronisieren, einmaliges Anmelden einrichten und mit vielen Software als Dienstanwendungen wie Salesforce, Dropbox und vieles mehr synchronisieren.
  
Wenn Sie erweiterte Active Directory-Domänendienste (AD DS) Funktionalität, bidirektionale Synchronisierung und andere Verwaltungsfunktionen wünschen, können Sie Ihr kostenloses Abonnement auf ein kostenpflichtiges Premium-Abonnement upgraden. Ausführliche Informationen finden Sie unter [Azure Active Directory Editions](https://azure.microsoft.com/pricing/details/active-directory/).
  
Weitere Informationen zu Microsoft 365 und Azure AD finden Sie unter [Understanding Microsoft 365 Identity and Azure Active Directory](about-microsoft-365-identity.md).
  
## <a name="extend-the-capabilities-of-your-microsoft-365-tenant"></a>Erweitern der Funktionen Ihres Microsoft 365-Mandanten

|**Feature**|**Beschreibung**|
|:-----|:-----|
|Integrierte apps  <br/> |Sie können einzelnen apps Zugriff auf Ihre Microsoft 365-Daten wie e-Mail, Kalender, Kontakte, Benutzer, Gruppen, Dateien und Ordner gewähren. Sie können diese apps auch auf globaler Administratorebene autorisieren und Sie für Ihr gesamtes Unternehmen zur Verfügung stellen, indem Sie die apps in Azure AD registrieren. Ausführliche Informationen finden Sie unter [integrierte apps und Azure AD für Microsoft 365-Administratoren](https://support.office.com/article/cb2250e3-451e-416f-bf4e-363549652c2a).  <br/> Siehe auch [einmaliges Anmelden bei Anwendungen](https://go.microsoft.com/fwlink/p/?LinkId=698604).  <br/> |
|PowerApps  <br/> | Power apps sind fokussierte Apps für mobile Geräte, die mit Ihren vorhandenen Datenquellen wie SharePoint-Listen und anderen Daten-apps verbunden werden können. Weitere Informationen finden Sie unter [Erstellen eines PowerApp für eine Liste auf SharePoint Online](https://support.office.com/article/9338b2d2-67ac-4b81-8e67-97da27e5e9ab) -und [PowerApps-Seite](https://powerapps.microsoft.com/) .  <br/> |
   
Weitere Informationen finden Sie unter [integrierte apps und Azure AD für Microsoft 365-Administratoren](integrated-apps-and-azure-ads.md) und [Azure AD Anwendungskatalog und einmaliges Anmelden](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on).

## <a name="see-also"></a>Siehe auch

[Übersicht zu Microsoft 365 Enterprise](microsoft-365-overview.md)
