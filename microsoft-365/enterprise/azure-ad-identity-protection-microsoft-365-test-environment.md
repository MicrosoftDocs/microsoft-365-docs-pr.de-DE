---
title: Azure AD Identity Protection für Ihre Microsoft 365 for Enterprise-Testumgebung
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
description: Konfigurieren Sie Azure AD Identity Protection, und analysieren Sie die aktuellen Konten in Ihrer Microsoft 365 for Enterprise-Testumgebung.
ms.openlocfilehash: 0cb0acf3faee13676573b04178bd6b4d3d36da4d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905344"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-for-enterprise-test-environment"></a>Azure AD Identity Protection für Ihre Microsoft 365 for Enterprise-Testumgebung

*Diese Testumgebungsanleitung kann nur für Microsoft 365 für Unternehmenstestumgebungen verwendet werden.*

Sie können Azure Active Directory (Azure AD) Identity Protection verwenden, um potenzielle Sicherheitsrisiken zu erkennen, die sich auf die Identität Ihrer Organisation auswirken, automatisierte Antworten zu konfigurieren und Vorfälle zu untersuchen. In diesem Artikel wird beschrieben, wie Sie Azure AD Identity Protection zum Anzeigen der Analyse Ihrer Testumgebungskonten verwenden.

Das Einrichten von Azure AD Identity Protection in Ihrer Microsoft 365 for Enterprise-Testumgebung umfasst zwei Phasen:

- [Phase 1: Erstellen Ihrer Microsoft 365 for Enterprise-Testumgebung](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Phase 2: Verwenden von Azure AD Identity Protection](#phase-2-use-azure-ad-identity-protection)

![Testumgebungsanleitungen für die Microsoft-Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Eine visuelle Karte zu allen Artikeln im Microsoft 365 for Enterprise Test Lab Guide-Stapel finden Sie unter [Microsoft 365 for Enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Phase 1: Erstellen Ihrer Microsoft 365 for Enterprise-Testumgebung

Wenn Sie Azure AD Identity Protection nur auf einfache Weise mit den Mindestanforderungen testen möchten, befolgen Sie die Anweisungen unter [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Wenn Sie Azure AD Identity Protection in einem simulierten Unternehmen testen möchten, befolgen Sie die Anweisungen unter [Pass-Through-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Für das Testen von Azure AD Identity Protection ist keine simulierte Unternehmenstestumgebung erforderlich, die ein simuliertes Intranet umfasst, das mit dem Internet verbunden ist, und die Verzeichnissynchronisierung für eine ACTIVE Directory Domain Services (AD DS)-Gesamtstruktur. Es wird hier als Option bereitgestellt, damit Sie Azure AD Identity Protection testen und damit in einer Umgebung experimentieren können, die eine typische Organisation darstellt.
  
## <a name="phase-2-use-azure-ad-identity-protection"></a>Phase 2: Verwenden von Azure AD Identity Protection

1. Öffnen Sie eine private Instanz Ihres Browsers, und melden Sie sich beim Azure-Portal unter mit dem globalen Administratorkonto Ihrer [https://portal.azure.com](https://portal.azure.com) Microsoft 365 for Enterprise-Testumgebung an.
2. Geben Sie im Azure-Portal **identitätsschutz** in das Suchfeld ein, und wählen Sie **dann Azure AD Identity Protection aus.**
3. Wählen Sie **auf dem Blatt Identity Protection – Overview** jeden Bericht aus, um zu sehen, was berichtet wird.
4. Wählen **Sie unter Benachrichtigen** die Option Erkannte **Warnungen für Benutzer mit Risiko aus.**
5. Wählen Sie **im Bereich Erkannte Warnungen für** Benutzer mit Risiko die Option Mittel **aus.**
6. Wenn **E-Mails an die folgenden Benutzer** gesendet werden, wählen Sie **Eingeschlossen** aus, und stellen Sie sicher, dass Ihr globales Administratorkonto in der Liste der ausgewählten Mitglieder enthalten ist.
7. Wählen Sie **Speichern** aus.

Wählen **Sie unter Schützen** verschiedene Polizeien aus, um zu sehen, wie sie konfiguriert werden. Wenn Sie eine Richtlinie erstellen und aktivieren, stellen Sie sicher, dass sie nicht den Zugriff für alle Benutzer blockiert, oder Sie können sich möglicherweise nicht anmelden. Um dies zu verhindern, schließen Sie bestimmte Benutzerkonten aus, z. B. globale Administratoren.

Weitere Tests und Experimente finden Sie unter [Simulieren von Risikoereignissen](/azure/active-directory/active-directory-identityprotection-playbook).

## <a name="next-step"></a>Nächster Schritt

Sehen Sie sich weitere [Identitäts](m365-enterprise-test-lab-guides.md#identity)features und- funktionen in Ihrer Testumgebung an.

## <a name="see-also"></a>Siehe auch

[Identitätsplan](identity-roadmap-microsoft-365.md)

[Testumgebungsanleitungen für Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Übersicht über Microsoft 365 Enterprise](microsoft-365-overview.md)

[Dokumentation zu Microsoft 365 Enterprise](/microsoft-365-enterprise/)