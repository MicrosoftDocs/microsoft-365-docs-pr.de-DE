---
title: Azure AD Identitätsschutz für Ihre Microsoft 365 for Enterprise-Testumgebung
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
description: Konfigurieren Sie Azure AD Identitätsschutz, und analysieren Sie die aktuellen Konten in Ihrer Microsoft 365 for Enterprise-Testumgebung.
ms.openlocfilehash: 162a6504fb7541874798f5e795bd2ecd590b5035
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487708"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-for-enterprise-test-environment"></a>Azure AD Identitätsschutz für Ihre Microsoft 365 for Enterprise-Testumgebung

*Diese Test Umgebungs Anleitung kann nur für Microsoft 365 für Enterprise-Testumgebungen verwendet werden.*

Sie können Azure Active Directory (Azure AD) Identity Protection verwenden, um potenzielle Sicherheitsrisiken zu erkennen, die sich auf die Identitäten Ihrer Organisation auswirken, automatisierte Antworten konfigurieren und Vorfälle untersuchen. In diesem Artikel wird beschrieben, wie Sie Azure AD Identitätsschutz verwenden, um die Analyse Ihrer Test Umgebungs Konten anzuzeigen.

Das Einrichten Azure AD Identitätsschutzes in Ihrer Microsoft 365 for Enterprise-Testumgebung umfasst zwei Phasen:

- [Phase 1: Erstellen der Testumgebung für Microsoft 365 für Unternehmen](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Phase 2: Verwenden von Azure AD Identitätsschutz](#phase-2-use-azure-ad-identity-protection)

![Testumgebungsanleitungen für die Microsoft-Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Eine visuelle Zuordnung zu allen Artikeln im Microsoft 365 for Enterprise Test Lab Guide Stack finden Sie unter [Microsoft 365 for Enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Phase 1: Erstellen der Testumgebung für Microsoft 365 für Unternehmen

Wenn Sie Azure AD Identitätsschutz nur auf einfache Weise mit den Mindestanforderungen testen möchten, befolgen Sie die Anweisungen unter [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Wenn Sie Azure AD Identitätsschutz in einem simulierten Unternehmen testen möchten, befolgen Sie die Anweisungen unter [Pass-Through-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Für das Testen Azure AD Identitätsschutzes ist keine simulierte Enterprise-Testumgebung erforderlich, die ein simuliertes, mit dem Internet verbundenes Intranet und eine Verzeichnissynchronisierung für eine Active Directory-Domänendienste (AD DS) Gesamtstruktur umfasst. Sie wird hier als Option bereitgestellt, damit Sie Azure AD Identitätsschutz testen und mit dieser in einer Umgebung experimentieren können, die eine typische Organisation darstellt.
  
## <a name="phase-2-use-azure-ad-identity-protection"></a>Phase 2: Verwenden von Azure AD Identitätsschutz

1. Öffnen Sie eine private Instanz Ihres Browsers, und melden Sie sich beim Azure-Portal unter [https://portal.azure.com](https://portal.azure.com) mit dem globalen Administratorkonto Ihrer Microsoft 365 für Enterprise-Testumgebung an.
2. Geben Sie im Azure-Portal **Identity Protection** in das Suchfeld ein, und wählen Sie dann **Azure AD Identitätsschutz**aus.
3. Wählen Sie im Blatt **Identitätsschutz – Übersicht** die einzelnen Berichte aus, um die Berichterstellung anzuzeigen.
4. Wählen Sie unter **Benachrichtigen**die Option **Benutzer bei Risiko erkannte Warnungen**aus.
5. Wählen Sie im Bereich **Benutzer bei Risiko erkannte Warnungen** die Option **Mittel**aus.
6. Wenn **e-Mails an die folgenden Benutzer gesendet werden**, wählen Sie **einschließen** aus, und stellen Sie sicher, dass sich ihr globales Administratorkonto in der Liste der ausgewählten Mitglieder befindet.
7. Klicken Sie auf **Speichern**.

Wählen Sie unter **Protect**verschiedene Policies aus, um zu sehen, wie Sie konfiguriert werden. Wenn Sie eine Richtlinie erstellen und aktivieren, müssen Sie sicherstellen, dass der Zugriff nicht für alle Benutzer blockiert wird, oder Sie können sich möglicherweise nicht anmelden. Um dies zu verhindern, schließen Sie bestimmte Benutzerkonten wie globale Administratoren aus.

Weitere Tests und Experimente finden Sie unter [Simulieren von Risikoereignissen](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).

## <a name="next-step"></a>Nächster Schritt

Sehen Sie sich weitere [Identitäts](m365-enterprise-test-lab-guides.md#identity)features und- funktionen in Ihrer Testumgebung an.

## <a name="see-also"></a>Siehe auch

[Identity-Roadmap](identity-roadmap-microsoft-365.md)

[Testumgebungsanleitungen für Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Übersicht über Microsoft 365 Enterprise](microsoft-365-overview.md)

[Dokumentation zu Microsoft 365 für Unternehmen](https://docs.microsoft.com/microsoft-365-enterprise/)
