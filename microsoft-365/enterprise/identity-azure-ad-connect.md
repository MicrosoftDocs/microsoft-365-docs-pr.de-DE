---
title: 'Schritt 7: Synchronisieren von Identitäten'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/09/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Informationen zu Identitätsoptionen und zum Konfigurieren von Azure AD Connect, um Ihr lokales Windows Server Active Directory mit Azure AD zu synchronisieren.
ms.openlocfilehash: 2391ee11a1706bbbfdeb248c5967822d3ea68f72
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2018
ms.locfileid: "26867633"
---
# <a name="step-7-synchronize-identities"></a>Schritt 7: Synchronisieren von Identitäten

*Dieser Schritt ist erforderlich für Hybridumgebungen und gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

In diesem Schritt synchronisieren Sie Ihr lokales Windows Server Azure Active Directory (AD) mit dem Azure Active Directory (AD)-Mandanten, der von Ihren Office 365- und Enterprise Mobility + Security (EMS)-Abonnements verwendet wird.

Azure AD Connect ist das unterstützte Microsoft-Tool, das Sie durch die Synchronisierung nur der Identitäten führt, die Sie aus Windows Server AD-Umgebungen mit einer oder mehreren Gesamtstrukturen wirklich für Ihren Azure AD-Mandanten benötigen.

![Wie Azure AD Connect Ihr lokales Verzeichnis mit Azure AD synchronisiert](./media/identity-azure-ad-connect/azure-ad-connect.png)

*Wie Azure AD Connect Ihr lokales Verzeichnis mit Azure AD synchronisiert*

Die erste Entscheidung in Ihrer Identitätshybridlösung ist Ihre Authentifizierungsanforderung. Die folgenden Optionen sind verfügbar:

- Bei der **verwalteten Authentifizierung** verarbeitet Azure AD den Authentifizierungsprozess für die Benutzeranmeldung. Es gibt zwei Methoden für die verwaltete Authentifizierung: 
    - **Kennworthashsynchronisierung (PHS)** [Für einige Premiumfunktionen empfohlen und erforderlich]. Dies ist die einfachste Methode zum Aktivieren der Authentifizierung für lokale Verzeichnisobjekte in Azure AD. Azure AD Connect extrahiert das Kennwort mit Hash aus Windows Server AD, führt eine zusätzliche Sicherheitsverarbeitung für das Kennwort aus und speichert es in Azure AD. Weitere Informationen finden Sie unter [Implementieren der Kennworthashsynchronisierung mit der Azure AD Connect-Synchronisierung](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization).
    - Die **Passthrough-Authentifizierung (PTA)** stellt eine einfache Lösung zur Kennwortüberprüfung für Azure AD-basierte Dienste bereit. PTA verwendet einen Agent, der auf einem oder mehreren lokalen Servern ausgeführt wird, um die Benutzerauthentifizierungsmethode direkt mit dem lokalen Windows Server Active Directory zu überprüfen. Weitere Informationen finden Sie unter [Benutzeranmeldung mit der Azure Active Directory-Passthrough-Authentifizierung](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-pass-through-authentication).
- Bei der **Verbundauthentifizierung** wird der Authentifizierungsprozess über einen Identitätsverbundserver wie die Active Directory-Verbunddienste (AD FS) an einen anderen Identitätsanbieter weitergeleitet, wenn der Benutzer sich anmelden möchte. Der Identitätsanbieter kann weitere Authentifizierungsmethoden bereitstellen, z. B. Smartcard-basierte Authentifizierung. Weitere Informationen finden Sie unter [Wählen der richtigen Authentifizierungsmethode für Ihre Azure Active Directory-Hybrididentitätslösung](https://docs.microsoft.com/azure/security/azure-ad-choose-authn).

Nachdem Sie Ihre Identitätshybridlösung ermittelt haben, laden Sie das [IdFix-Tool für die Fehlerbehebung bei der Verzeichnissynchronisierung herunter](https://www.microsoft.com/download/details.aspx?id=36832) und führen es aus, um Ihr Windows Server AD auf Probleme zu analysieren.

Beheben Sie alle vom IdFix-Tool erkannten Probleme, und lesen Sie dann [Implementieren der Kennworthashsynchronisierung](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-hash-synchronization). Dort finden Sie eine Anleitung zur Installation des Azure AD Connect-Tools und zur Konfiguration der Verzeichnissynchronisierung zwischen Ihrem lokalen Windows Server AD und dem Azure AD-Mandanten für Ihre Office 365- und EMS-Abonnements. Nach dem Start der Synchronisierung werden die Benutzerkonten und Gruppen im lokalen Identitätsanbieter (z. B. Windows Server AD) beibehalten.

Microsoft stellt eine Reihe von Empfehlungen für [Identität und Gerätezugriff](microsoft-365-policies-configurations.md) bereit, um sicherzustellen, dass die Mitarbeiter sicher und produktiv arbeiten können. 
- Empfohlene Anforderungen für Hybridumgebungen finden Sie in der Spalte **Active Directory mit Kennworthashsynchronisierung** unter [Voraussetzungen](identity-access-prerequisites.md#prerequisites). 

- Empfohlene Anforderungen nur für Cloudumgebungen finden Sie in der Spalte **Nur Cloud** unter [Voraussetzungen](identity-access-prerequisites.md#prerequisites).

|||
|:-------|:-----|
|![Testumgebungsanleitungen für die Microsoft-Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Testumgebungsanleitung: Kennworthashsynchronisierung](password-hash-sync-m365-ent-test-environment.md)<br> [Testumgebungsanleitung: Pass-Through-Authentifizierung](pass-through-auth-m365-ent-test-environment.md) |
|||

Als Zwischenprüfung können Sie sich die [Beendigungskriterien](identity-exit-criteria.md#crit-identity-sync) für diesen Schritt anschauen.

## <a name="next-step"></a>Nächster Schritt

|||
|:-------|:-----|
|![](./media/stepnumbers/Step8.png)| [Überwachen des Synchronisierungsstatus](identity-azure-ad-connect-health.md) |

