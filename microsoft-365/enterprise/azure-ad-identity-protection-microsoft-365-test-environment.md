---
title: Azure AD Identitätsschutz für Ihre Microsoft 365 Enterprise-Testumgebung
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Konfigurieren Sie Azure AD Identitätsschutz, und analysieren Sie die aktuellen Konten in Ihrer Microsoft 365 Enterprise-Testumgebung.
ms.openlocfilehash: bc98ebbdd45e06481e2d95687fb4eb8c986533a3
ms.sourcegitcommit: 9ee873c6a2f738a0c99921e036894b646742e706
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2019
ms.locfileid: "38673241"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-enterprise-test-environment"></a>Azure AD Identitätsschutz für Ihre Microsoft 365 Enterprise-Testumgebung

*Diese Test Umgebungs Anleitung kann nur für Microsoft 365 Enterprise-Testumgebungen verwendet werden.*

Mit Azure AD Identity Protection können Sie potenzielle Sicherheitsrisiken erkennen, die sich auf die Identitäten Ihrer Organisation auswirken, automatisierte Antworten konfigurieren und Vorfälle untersuchen. In diesem Artikel wird beschrieben, wie Sie Azure AD Identitätsschutz aktivieren und die Analyse Ihrer Test Umgebungs Konten anzeigen können.

Es gibt zwei Phasen zum Einrichten Azure AD Identitätsschutzes in Ihrer Microsoft 365 Enterprise-Testumgebung:

1. Erstellen Sie die Microsoft 365 Enterprise-Testumgebung.
2. Aktivieren und verwenden Sie Azure AD Identity Protection.

![Testumgebungsanleitungen für die Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Klicken Sie [hier](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Phase 1: Erstellen Ihrer Microsoft 365 Enterprise-Testumgebung

Wenn Sie Azure AD Identitätsschutz nur auf einfache Weise mit den Mindestanforderungen testen möchten, befolgen Sie die Anweisungen unter [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Wenn Sie Azure AD Identitätsschutz in einem simulierten Unternehmen testen möchten, befolgen Sie die Anweisungen unter [Pass-Through-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Für das Testen Azure AD Identitätsschutzes ist keine simulierte Enterprise-Testumgebung erforderlich, die ein simuliertes, mit dem Internet verbundenes Intranet und eine Verzeichnissynchronisierung für eine Active Directory-Domänendienste (AD DS) Gesamtstruktur umfasst. Sie wird hier als Option bereitgestellt, damit Sie Azure AD Identitätsschutz testen und mit dieser in einer Umgebung experimentieren können, die eine typische Organisation darstellt. 
  
## <a name="phase-2-enable-and-use-azure-ad-identity-protection"></a>Phase 2: Aktivieren und Verwenden von Azure AD Identitätsschutz

1. Öffnen Sie eine private Instanz Ihres Browsers, und melden Sie sich beim Azure- [https://portal.azure.com](https://portal.azure.com) Portal unter mit dem globalen Administratorkonto Ihrer Microsoft 365 Enterprise-Testumgebung an.
2. Klicken Sie im Azure-Portal auf **alle Dienste #a0 Marketplace**.
3. Geben Sie **Azure AD Identitätsschutz** ein, und klicken Sie darauf.
4. Klicken Sie auf dem Blade **Erste Schritte** unter **Einstellungen**auf **Onboard** , klicken Sie auf **an Dashboard anheften**, und klicken Sie dann auf **Erstellen**.
5. Klicken Sie im Azure-Portal im Dashboard auf **Azure AD Identitätsschutz** . 

   Es sollte ein **Azure AD-Blatt mit Identitätsschutz – Übersicht** mit einem Dashboard angezeigt werden. Beachten Sie bei **Sicherheitsanfälligkeiten**, dass die Anzahl der Benutzerkonten ohne mehrstufige Authentifizierungs Registrierung ermittelt wurde. Diese Nummer variiert je nach den zuvor durchgeführten Microsoft 365 Enterprise Test Lab Guides.

6. Klicken Sie durch die Kategorien für **untersuchen** , um zu ermitteln, ob Benutzer oder Ereignisse erkannt wurden.

Weitere Tests und Experimente finden Sie unter [Simulieren von Risikoereignissen](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).

Weitere Informationen und Links zum Bereitstellen Azure AD Identitätsschutzes in der Produktion finden Sie im Schritt zum [Schutz gegen Anmeldeinformationen](identity-secure-user-sign-ins.md#identity-ident-prot) in der Identitäts Phase.

## <a name="next-step"></a>Nächster Schritt

Sehen Sie sich weitere [Identitäts](m365-enterprise-test-lab-guides.md#identity)features und- funktionen in Ihrer Testumgebung an.

## <a name="see-also"></a>Siehe auch

[Phase 2: Identität](identity-infrastructure.md)

[Testumgebungsanleitungen für Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Microsoft 365 Enterprise-Bereitstellungshandbuch](deploy-microsoft-365-enterprise.md)

[Dokumentation zu Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
