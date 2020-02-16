---
title: Azure AD Identitätsschutz für Ihre Microsoft 365 Enterprise-Testumgebung
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Konfigurieren Sie Azure AD Identitätsschutz, und analysieren Sie die aktuellen Konten in Ihrer Microsoft 365 Enterprise-Testumgebung.
ms.openlocfilehash: 3f3740e42c7ec909f44a3c761dfc743359b3f030
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42068492"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-enterprise-test-environment"></a>Azure AD Identitätsschutz für Ihre Microsoft 365 Enterprise-Testumgebung

*Diese Testumgebungsanleitung kann nur für Microsoft 365 Enterprise-Testumgebungen verwendet werden.*

Azure Active Directory (Azure AD) Identity Protection ermöglicht Ihnen das Erkennen potenzieller Sicherheitsanfälligkeiten, die sich auf die Identitäten Ihrer Organisation auswirken, automatische Antworten konfigurieren und Vorfälle untersuchen. In diesem Artikel wird beschrieben, wie Sie Azure AD Identitätsschutz verwenden, um die Analyse Ihrer Test Umgebungs Konten anzuzeigen.

Es gibt zwei Phasen zum Einrichten Azure AD Identitätsschutzes in Ihrer Microsoft 365 Enterprise-Testumgebung:

1. Erstellen Sie die Microsoft 365 Enterprise-Testumgebung.
2. Verwenden Sie Azure AD Identitätsschutz.

![Testumgebungsanleitungen für die Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Klicken Sie [hier](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Phase 1: Erstellen Ihrer Microsoft 365 Enterprise-Testumgebung

Wenn Sie Azure AD Identitätsschutz nur auf einfache Weise mit den Mindestanforderungen testen möchten, befolgen Sie die Anweisungen unter [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Wenn Sie Azure AD Identitätsschutz in einem simulierten Unternehmen testen möchten, befolgen Sie die Anweisungen unter [Pass-Through-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Für das Testen Azure AD Identitätsschutzes ist keine simulierte Enterprise-Testumgebung erforderlich, die ein simuliertes, mit dem Internet verbundenes Intranet und eine Verzeichnissynchronisierung für eine Active Directory-Domänendienste (AD DS) Gesamtstruktur umfasst. Sie wird hier als Option bereitgestellt, damit Sie Azure AD Identitätsschutz testen und mit dieser in einer Umgebung experimentieren können, die eine typische Organisation darstellt. 
  
## <a name="phase-2-use-azure-ad-identity-protection"></a>Phase 2: Verwenden von Azure AD Identitätsschutz

1. Öffnen Sie eine private Instanz Ihres Browsers, und melden Sie sich beim Azure- [https://portal.azure.com](https://portal.azure.com) Portal unter mit dem globalen Administratorkonto Ihrer Microsoft 365 Enterprise-Testumgebung an.
2. Geben Sie im Azure-Portal **Identity Protection** in das Suchfeld ein, und klicken Sie dann auf **Azure AD Identitätsschutz**.
3. Klicken Sie im Blatt **Identitätsschutz – Übersicht** auf die einzelnen Berichte, um zu sehen, was Sie berichten.
4. Klicken Sie unter **Benachrichtigen**auf **Benutzer bei Risiko erkannte Warnungen**.
5. Wählen Sie im Bereich **Benutzer bei Risiko erkannte Warnungen** die Option **Mittel**aus.
6. Wenn **e-Mails an die folgenden Benutzer gesendet werden**, klicken Sie auf **einschließen** , und vergewissern Sie sich, dass sich ihr globales Administratorkonto in der Liste der ausgewählten Mitglieder befindet.
7. Klicken Sie auf **Speichern**.

Klicken Sie auf die verschiedenen Richtlinien unter **Protect** , um zu erfahren, wie Sie konfiguriert werden. Wenn Sie eine Richtlinie erstellen und aktivieren, müssen Sie sicherstellen, dass der Zugriff für einen zu weiten Bereich von Bedingungen nicht blockiert wird, oder Sie können sich nicht selbst als globaler Administrator anmelden.

Weitere Tests und Experimente finden Sie unter [Simulieren von Risikoereignissen](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).

Weitere Informationen und Links zum Bereitstellen Azure AD Identitätsschutzes in der Produktion finden Sie im Schritt zum [Schutz gegen Anmeldeinformationen](identity-secure-user-sign-ins.md#identity-ident-prot) in der Identitäts Phase.

## <a name="next-step"></a>Nächster Schritt

Sehen Sie sich weitere [Identitäts](m365-enterprise-test-lab-guides.md#identity)features und- funktionen in Ihrer Testumgebung an.

## <a name="see-also"></a>Siehe auch

[Phase 2: Identität](identity-infrastructure.md)

[Testumgebungsanleitungen für Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Microsoft 365 Enterprise-Bereitstellungshandbuch](deploy-microsoft-365-enterprise.md)

[Dokumentation zu Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
