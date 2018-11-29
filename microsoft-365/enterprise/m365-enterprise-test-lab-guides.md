---
title: Testumgebungsanleitungen für Microsoft 365 Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2018
ms.audience: ITPro
ms.topic: hub-page
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
ms.assetid: 706d5449-45e5-4b0c-a012-ab60501899ad
description: Verwenden Sie die folgenden Testumgebungsanleitungen, um Demos, Machbarkeitsstudien oder Entwicklungs-/Testumgebungen für Microsoft 365 Enterprise einzurichten.
ms.openlocfilehash: df723647748532936e40bbdb4e34ff698b9fa650
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868059"
---
# <a name="microsoft-365-enterprise-test-lab-guides"></a>Testumgebungsanleitungen für Microsoft 365 Enterprise

Mithilfe von Testumgebungsanleitungen können Sie schnell mehr zu Microsoft-Produkten erfahren. Sie enthalten Anweisungen zum Konfigurieren vereinfachter, aber repräsentativer Testumgebungen. Sie können diese Umgebungen für Demos, Anpassungen oder das Erstellen komplexer Machbarkeitsstudien für die Dauer eines Test- oder bezahlten Abonnements verwenden. 

Testumgebungsanleitungen sind modular aufgebaut. Sie bauen aufeinander auf, sodass mehrere Konfigurationen entstehen, die Ihren Lern- oder Testkonfigurationsanforderungen besser entsprechen. Diese praktische Erfahrung erweitert Ihre Kenntnisse der Bereitstellungsanforderungen neuer Produkte oder Szenarien, sodass Sie besser planen können, wie diese in der Produktionsumgebung gehostet werden sollen.

Testumgebungsanleitungen ermöglichen die Erstellung repräsentativer Umgebungen zum Entwickeln und Testen von Anwendungen, auch als Entwicklungs-/Testumgebungen bezeichnet.
  
![Testumgebungsanleitungen für die Microsoft-Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Klicken Sie [hier](https://aka.ms/m365etlgstack), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.
  
## <a name="base-configuration"></a>Standardkonfiguration

Zuerst erstellen Sie eine Testumgebung für [Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/), die Office 365 E5, Enterprise Mobility + Security (EMS) E5 und Windows 10 Enterprise umfasst. Es stehen zwei unterschiedliche Typen von Standardkonfiguration zur Auswahl:

- Verwenden Sie die [einfache Standardkonfiguration](lightweight-base-configuration-microsoft-365-enterprise.md), wenn Sie die Features und Funktionen von Microsoft 365 Enterprise in einer reinen Cloudumgebung konfigurieren und demonstrieren möchten, die keine lokalen Komponenten umfasst.

- Verwenden Sie die [simulierte Unternehmensstandardkonfiguration](simulated-ent-base-configuration-microsoft-365-enterprise.md), wenn Sie die Features und Funktionen von Microsoft 365 Enterprise in einer hybriden Cloudumgebung konfigurieren und demonstrieren möchten, die lokale Komponenten wie eine Windows Server Active Directory (AD)-Domäne verwendet.
    
## <a name="identity"></a>Identität

Wie Sie identitätsbezogene Features und Funktionen demonstrieren können, erfahren Sie hier:

- [Kennworthashsynchronisierung](password-hash-sync-m365-ent-test-environment.md)
  
   Aktivieren und testen Sie die hashbasierte Verzeichnissynchronisierung von einem Windows Server AD-Domänencontroller.

- [Pass-Through-Authentifizierung](pass-through-auth-m365-ent-test-environment.md)
  
   Aktivieren und testen Sie die Pass-Through-Authentifizierung an einen Windows Server AD-Domänencontroller.

- [Nahtloses einmaliges Anmelden in Azure AD](single-sign-on-m365-ent-test-environment.md)
  
   Aktivieren und testen Sie das nahtlose einmalige Anmelden in Azure AD mit einem Windows Server AD-Domänencontroller.

- [Mehrstufige Authentifizierung](multi-factor-authentication-microsoft-365-test-environment.md)
  
   Aktivieren und testen Sie die Smartphone-basierte mehrstufige Authentifizierung für ein bestimmtes Benutzerkonto.

- [Schützen von globalen Administratorkonten](protect-global-administrator-accounts-microsoft-365-test-environment.md)
 
   Sperren Sie Ihre globalen Administratorkonten mit Office 365 Cloud App Security und Richtlinien für bedingten Zugriff.

- [Kennwortzurücksetzung](password-reset-m365-ent-test-environment.md)

   Verwenden Sie die Self-Service-Kennwortzurücksetzung, um Ihr Kennwort zurückzusetzen.

- [Automatische Lizenzierung und Gruppenmitgliedschaft](automate-licenses-group-membership-microsoft-365-test-environment.md)

   Machen Sie die Verwaltung neuer Konten durch automatische Lizenzierung und dynamische Gruppenmitgliedschaft einfacher als je zuvor.

- [Azure AD Identity Protection](azure-ad-identity-protection-microsoft-365-test-environment.md)

   Überprüfen Sie Ihre aktuellen Benutzerkonten auf Sicherheitsrisiken.

## <a name="mobile-device-management"></a>Verwaltung mobiler Geräte

Eine Veranschaulichung von Features und Funktionen im Zusammenhang mit der Verwaltung mobiler Geräte finden Sie unter:

- [MAM-Richtlinien](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
    
   Erstellen Sie Richtlinien für Benutzergruppen und die mobile Anwendung (MAM) für iOS- und Android-Geräte.
    
- [Registrieren von iOS- und Android-Geräten](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
   
   Registrieren Sie iOS- oder Android-Geräte, und verwalten Sie sie remote.


## <a name="information-protection"></a>Schutz von Daten

Eine Veranschaulichung der schutzbezogenen Features und Funktionen finden Sie unter:

- [Erhöhte Office 365-Sicherheit](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md)
    
   Konfigurieren der Einstellungen für höhere Sicherheit von Office 365 und Prüfen der integrierten Sicherheitstools.
  
- [Datenklassifikation](data-classification-microsoft-365-enterprise-dev-test-environment.md)
    
   Konfigurieren und Anwenden von Office 365-Bezeichnungen auf ein Dokument in einer SharePoint Online-Teamwebsite.
    
- [Privileged Access Management für die Microsoft 365 Enterprise-Testumgebung](privileged-access-microsoft-365-enterprise-dev-test-environment.md)
    
   Konfigurieren von Privileged Access Management für Just-in-Time-Zugriff auf privilegierte Aufgaben mit erhöhten Rechten in Ihrer Office 365-Organisation.

## <a name="see-also"></a>Siehe auch

[Testumgebungsanleitungen zur Cloudakzeptanz](https://mva.microsoft.com/training-courses/experience-the-microsoft-cloud-with-cloud-adoption-test-lab-guides-17960?l=LXNRdhSLE_1000115881)
    
[Die One Microsoft Cloud-Testumgebungsanleitung](http://aka.ms/catlgstack)
