---
title: Azure AD-Schutz für Ihr Unternehmen der Microsoft 365 test Environment.
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- TLG
- Ent_TLGs
description: Konfigurieren von Azure AD-Schutz und analysieren Sie die aktuellen Konten in Ihrer testumgebung Microsoft 365 Enterprise.
ms.openlocfilehash: 165667ad2122839336ef0790ab5661cff53ca32b
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2019
ms.locfileid: "26867643"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-enterprise-test-environment"></a>Azure AD-Schutz für Ihr Unternehmen der Microsoft 365 test Environment.

Azure AD-Schutz können Sie Identitäten Ihrer Organisation beeinflussen potenzielle Sicherheitsrisiken zu erkennen, konfigurieren Automatische Antworten und untersuchen Vorfälle. In diesem Artikel wird beschrieben, wie zum Aktivieren von Azure AD-Schutz und die Analyse von Ihrer Umgebung Testkonten anzeigen.

Es gibt zwei Phasen Azure AD-Schutz in Ihrer Microsoft 365 Enterprise-testumgebung einrichten:

1. Erstellen der testumgebung Microsoft 365 Enterprise.
2. Aktivieren und Azure Active Directory-Identität Protection verwenden.

![Testumgebungsanleitungen für die Microsoft-Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Klicken Sie [hier](https://aka.ms/m365etlgstack), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Phase 1: Erstellen Sie Ihre Umgebung für Microsoft 365 Enterprise

Wenn Sie Azure AD-Schutz auf einfache Weise mit den Mindestanforderungen testen möchten, befolgen Sie die Anweisungen in der [Lightweight Basiskonfiguration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Wenn Sie in einer simulierten Enterprise Azure AD-Schutz testen möchten, befolgen Sie die Anweisungen in [Pass-Through-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Testen von Azure AD-Schutz erfordert keinen der simulierten Enterprise-testumgebung, einschließlich einer simulierten Intranet mit dem Internet verbunden und Directory-Synchronisierung für eine Windows Server Active Directory-Gesamtstruktur. Erfolgt hier als eine Option, damit können Sie Azure AD-Schutz testen und probieren Sie es in einer Umgebung, die eine typische Organisation darstellt. 
  
## <a name="phase-2-enable-and-use-azure-ad-identity-protection"></a>Phase 2: Aktivieren und Verwenden von Azure AD-Schutz

1. Öffnen Sie eine private Instanz des Browsers, und melden Sie sich bei der Azure-Portal unter [https://portal.azure.com](https://portal.azure.com) mit dem globalen Administratorkonto der Umgebung testen Microsoft 365 Enterprise.
2. Klicken Sie in der Azure-Portal auf **alle Dienste > Marketplace**.
3. Geben Sie **Azure AD-Schutz** , und klicken Sie dann auf.
4. Klicken Sie in die **Erste Schritte** Blade unter **Einstellungen**auf **Onboard** , klicken Sie auf **Pin Dashboard**und klicken Sie dann auf **Erstellen**.
5. Klicken Sie im Azure-Portal **Azure AD-Schutz** auf das Dashboard. 

   Ein **Azure AD Identity Protection-Overview** Blade mit einem Dashboard sollte angezeigt werden. Beachten Sie unter **Sicherheitsrisiken**bestimmt die Anzahl der Benutzerkonten ohne Multi-Factor Authentication-Registrierung. Diese Zahl variiert je nach auf vorherigen Microsoft 365 Enterprise Test Lab Guides, die Sie getan haben.

6. Klicken Sie auf die Kategorien für **untersuchen** , um festzustellen, ob Benutzer oder Ereignisse, die gefunden wurden vorhanden sind.

Weitere Tests und experimentieren finden Sie unter [Simulating Risikoereignisse](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).

Finden Sie unter der [Schutz vor Anmeldeinformationen gefährden](identity-azure-ad-identity-protection.md) Schritt in der Phase Identität Informationen und Links zu Azure AD-Schutz in der Produktion bereitstellen.

## <a name="next-step"></a>Nächster Schritt

Sehen Sie sich weitere [Identitäts](m365-enterprise-test-lab-guides.md#identity)features und- funktionen in Ihrer Testumgebung an.

## <a name="see-also"></a>Siehe auch

[Phase 2: Identität](identity-infrastructure.md)

[Testumgebungsanleitungen für Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Bereitstellung von Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Dokumentation zu Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
