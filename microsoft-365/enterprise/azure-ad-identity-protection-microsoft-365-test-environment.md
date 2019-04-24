---
title: Azure AD Identity Protection für Ihre Microsoft 365 Enterprise-Testumgebung
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Konfigurieren Sie Azure AD Identity Protection, und analysieren Sie die aktuellen Konten in Ihrer Microsoft 365 Enterprise-Testumgebung.
ms.openlocfilehash: bdac512f7645bf78c0a9c6bc5f71b35916bc4812
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32279094"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-enterprise-test-environment"></a>Azure AD Identity Protection für Ihre Microsoft 365 Enterprise-Testumgebung

Azure AD Identity Protection ermöglicht es Ihnen, potenzielle Sicherheitsrisiken zu ermitteln, die sich auf die Identitäten Ihrer Organisation auswirken, automatische Antworten zu konfigurieren und Vorfälle zu untersuchen. In diesem Artikel wird beschrieben, wie Sie Azure AD Identity Protection aktivieren und die Analyse der Test Umgebungs Konten anzeigen.

Es gibt zwei Phasen zum Einrichten von Azure AD Identity Protection in Ihrer Microsoft 365 Enterprise-Testumgebung:

1. Erstellen Sie die Microsoft 365 Enterprise-Testumgebung.
2. Aktivieren und Verwenden von Azure AD Identity Protection.

![Testumgebungsanleitungen für die Microsoft-Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Klicken Sie [hier](https://aka.ms/m365etlgstack), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Phase 1: Erstellen Ihrer Microsoft 365 Enterprise-Testumgebung

Wenn Sie Azure AD Identity Protection auf einfache Weise mit den Mindestanforderungen testen möchten, befolgen Sie die Anweisungen unter [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Wenn Sie Azure AD Identity Protection in einem simulierten Unternehmen testen möchten, befolgen Sie die Anweisungen unter [Passthrough-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Das Testen von Azure AD Identity Protection erfordert nicht die simulierte Enterprise-Testumgebung, die ein simuliertes Intranet enthält, das mit dem Internet und der Verzeichnissynchronisierung für eine Active Directory-Domänendienste (AD DS) verbunden ist. Sie wird hier als Option bereitgestellt, damit Sie Azure AD Identity Protection testen und in einer Umgebung experimentieren können, die eine typische Organisation darstellt. 
  
## <a name="phase-2-enable-and-use-azure-ad-identity-protection"></a>Phase 2: Aktivieren und Verwenden von Azure AD Identity Protection

1. Öffnen Sie eine private Instanz Ihres Browsers, und melden Sie sich beim Azure- [https://portal.azure.com](https://portal.azure.com) Portal unter mit dem globalen Administratorkonto ihrer Microsoft 365 Enterprise-Testumgebung an.
2. Klicken Sie im Azure-Portal auf **alle Dienste _GT_ Marketplace**.
3. Geben Sie **Azure AD Identity Protection** ein, und klicken Sie darauf.
4. Klicken Sie auf dem Blade **Erste Schritte** unter **Einstellungen**auf **Onboard** , klicken Sie auf **an Dashboard anheften**, und klicken Sie dann auf **Erstellen**.
5. Klicken Sie im Azure-Portal im Dashboard auf **Azure AD Identity Protection** . 

   Es sollte ein **Azure AD Identity Protection-Blade-Übersicht** mit einem Dashboard angezeigt werden. Beachten Sie bei **Sicherheitsanfälligkeiten**, dass die Anzahl der Benutzerkonten ohne mehrstufige Authentifizierungs Registrierung bestimmt wurde. Diese Anzahl variiert basierend auf früheren Microsoft 365 Enterprise Test Lab Guides, die Sie ausgeführt haben.

6. Klicken Sie auf die Kategorien für **untersuchen** , um festzustellen, ob Benutzer oder Ereignisse erkannt wurden.

Weitere Tests und Experimente finden Sie unter [simulierEn von Risikoereignissen](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).

Informationen und Links zur Bereitstellung von Azure AD Identity Protection in der Produktion finden Sie unter schützen Sie sich [gegen Anmeldeinformationen Kompromiss](identity-multi-factor-authentication.md#identity-ident-prot) Schritt in der Identitäts Phase.

## <a name="next-step"></a>Nächster Schritt

Sehen Sie sich weitere [Identitäts](m365-enterprise-test-lab-guides.md#identity)features und- funktionen in Ihrer Testumgebung an.

## <a name="see-also"></a>Siehe auch

[Phase 2: Identität](identity-infrastructure.md)

[Testumgebungsanleitungen für Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Microsoft 365 Enterprise-Bereitstellung](deploy-microsoft-365-enterprise.md)

[Dokumentation zu Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
