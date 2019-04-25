---
title: 'Schritt 3: Konfigurieren der Hybrididentität'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 02/25/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Informationen zu Identitätsoptionen und zum Konfigurieren von Azure AD Connect, um Ihre lokalen Active Directory Domain Services mit Azure AD zu synchronisieren.
ms.openlocfilehash: 6e582a3e3c68b00968faac17fd60b922eaaf7121
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32289597"
---
# <a name="step-3-configure-hybrid-identity"></a>Schritt 3: Konfigurieren der Hybrididentität

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-sync"></a>
## <a name="synchronize-identities"></a>Synchronisieren von Identitäten

*Dieser Schritt ist erforderlich für Hybridumgebungen und gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*

In diesem Abschnitt synchronisieren Sie Ihre lokalen Active Directory Domain Services (AD DS) mit dem Azure Active Directory (Azure AD)-Mandanten, der von Ihren Office 365- und Enterprise Mobility + Security (EMS)-Abonnements verwendet wird.

Azure AD Connect ist das unterstützte Microsoft-Tool, das Sie durch die Synchronisierung nur der Identitäten führt, die Sie aus AD DS -Umgebungen mit einer oder mehreren Gesamtstrukturen wirklich für Ihren Azure AD-Mandanten benötigen. In der folgenden Abbildung ist der grundlegende Prozess für die Azure AD Connect-Synchronisierung dargestellt.

![Wie Azure AD Connect Ihr lokales Verzeichnis mit Azure AD synchronisiert](./media/identity-azure-ad-connect/azure-ad-connect.png)

1. Azure AD Connect, das auf einem Server ausgeführt wird, fragt AD DS auf Änderungen in Konten, Gruppen und Kontakten ab.
2. Azure AD Connect sendet diese Änderungen an den Azure AD-Mandanten Ihres Microsoft 365-Abonnements.

Die erste Entscheidung in Ihrer Identitätshybridlösung ist Ihre Authentifizierungsanforderung. Die folgenden Optionen sind verfügbar:

- Bei der **verwalteten Authentifizierung** verarbeitet Azure AD den Authentifizierungsprozess für die Benutzeranmeldung. Es gibt zwei Methoden für die verwaltete Authentifizierung: 
    - **Kennworthashsynchronisierung (Password Hash Sync, PHS)** [Empfohlen und für einige Premiumfunktionen erforderlich]. Dies ist die einfachste Methode, um die Authentifizierung für lokale Verzeichnisobjekte in Azure AD zu aktivieren. Azure AD Connect extrahiert das Kennworthash aus AD DS, führt eine zusätzliche Sicherheitsverarbeitung für das Kennwort durch und speichert es in Azure AD. Weitere Informationen finden Sie unter [Implementieren der Kennworthashsynchronisierung mit der Azure AD Connect-Synchronisierung](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization).
    - Die **Pass-Through-Authentifizierung (PTA)** bietet eine einfache Kennwortüberprüfungslösung für auf Azure AD basierende Dienste. PTA verwendet einen Agent, der auf einem oder mehreren lokalen Servern ausgeführt wird, um die Benutzerauthentifizierungen direkt mit Ihren lokalen AD DS zu überprüfen. Weitere Informationen finden Sie unter [Benutzeranmeldung mit der Azure Active Directory-Passthrough-Authentifizierung](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-pass-through-authentication).
- Bei der **Verbundauthentifizierung** wird der Authentifizierungsprozess über einen Identitätsverbundserver wie die Active Directory-Verbunddienste (AD FS) an einen anderen Identitätsanbieter weitergeleitet, wenn der Benutzer sich anmelden möchte. Der Identitätsanbieter kann weitere Authentifizierungsmethoden bereitstellen, z. B. Smartcard-basierte Authentifizierung. Weitere Informationen finden Sie unter [Wählen der richtigen Authentifizierungsmethode für Ihre Azure Active Directory-Hybrididentitätslösung](https://docs.microsoft.com/azure/security/azure-ad-choose-authn).

Nachdem Sie Ihre Identitätshybridlösung ermittelt haben, laden Sie das [IdFix-Tool für die Fehlerbehebung bei der Verzeichnissynchronisierung herunter](https://www.microsoft.com/download/details.aspx?id=36832) und führen es aus, um Ihre AD DS auf Probleme zu analysieren.

Beheben Sie alle vom IdFix-Tool erkannten Probleme, und lesen Sie dann [Implementieren der Kennworthashsynchronisierung](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-hash-synchronization). Dort finden Sie eine Anleitung zur Installation des Azure AD Connect-Tools und zur Konfiguration der Verzeichnissynchronisierung zwischen Ihren lokalen AD DS und dem Azure AD-Mandanten für Ihre Office 365- und EMS-Abonnements. Nach dem Start der Synchronisierung werden die Benutzerkonten und Gruppen im lokalen Identitätsanbieter (z. B. AD DS) beibehalten.

Microsoft stellt eine Reihe von Empfehlungen für [Identität und Gerätezugriff](microsoft-365-policies-configurations.md) bereit, um sicherzustellen, dass die Mitarbeiter sicher und produktiv arbeiten können. 

- Empfohlene Anforderungen für Hybridumgebungen finden Sie in der Spalte **Active Directory mit Kennworthashsynchronisierung** unter [Voraussetzungen](identity-access-prerequisites.md#prerequisites). 

- Empfohlene Anforderungen nur für Cloudumgebungen finden Sie in der Spalte **Nur Cloud** unter [Voraussetzungen](identity-access-prerequisites.md#prerequisites).

Sobald Ihre lokalen Benutzer und Gruppen in Azure AD vorhanden sind, können Sie mit dem Zuweisen von Lizenzen und der Verwendung von Exchange Online beginnen. Informationen zur Einführung von Exchange Online bei Ihren Benutzern und zum Migrieren von lokalen Postfächern finden Sie unter [Bereitstellen von Exchange Online für Microsoft 365 Enterprise](exchangeonline-workload.md).

|||
|:-------|:-----|
|![Testumgebungsanleitungen für die Microsoft-Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Testumgebungsanleitung: Kennworthashsynchronisierung](password-hash-sync-m365-ent-test-environment.md)<br> [Testumgebungsanleitung: Pass-Through-Authentifizierung](pass-through-auth-m365-ent-test-environment.md) |
|||

Als Zwischenprüfung können Sie sich die [Beendigungskriterien](identity-exit-criteria.md#crit-identity-sync) für diesen Abschnitt anschauen.

<a name="identity-sync-health"></a>
## <a name="monitor-synchronization-health"></a>Überwachen des Synchronisierungsstatus

*Dieser Schritt ist optional und gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*

In diesem Abschnitt installieren Sie einen Azure AD Connect Health-Agent auf den einzelnen lokalen Identitätsserver, um die Identitätsinfrastruktur und die von Azure AD Connect bereitgestellten Synchronisierungsdienste zu überwachen. Die Überwachungsinformationen werden in einem Azure AD Connect Health-Portal verfügbar gemacht, wo Sie Warnungen, Leistungsüberwachungsdaten, Nutzungsanalysen und andere Informationen anzeigen können.

![Komponenten von Azure AD Connect Health](./media/identity-azure-ad-connect-health/identity-azure-ad-connect-health.png)

Die wichtigste Entwurfsentscheidung hinsichtlich der Verwendung von Azure AD Connect Health basiert auf der Art und Weise, wie Sie Azure AD Connect verwenden:

- Wenn Sie die **verwaltete Authentifizierung** verwenden, beginnen Sie mit [Verwenden von Azure AD Connect Health mit Synchronisierung](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync), um Informationen zur Funktionsweise und Konfiguration von Azure AD Connect Health zu erhalten.
- Wenn Sie nur die Namen der Konten und Gruppen mithilfe der **Verbundauthentifizierung** mit Active Directory-Verbunddiensten (AD FS) synchronisieren, beginnen Sie mit [Verwenden von Azure AD Connect Health mit AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs), um Informationen zur Funktionsweise und zur Konfiguration von Azure AD Connect Health zu erhalten.

Wenn Sie diesen Abschnitt abgeschlossen haben, verfügen Sie über Folgendes:

- Der Azure AD Connect Health-Agent ist auf jedem Ihrer lokalen Identitätsanbieterserver installiert.
- Das Azure AD Connect Health-Portal zeigt den aktuellen Status Ihrer lokalen Infrastruktur und der Synchronisierungsaktivitäten mit dem Azure AD-Mandanten für Ihre Office 365- und EMS-Abonnements.

Als Zwischenprüfung können Sie die [Beendigungskriterien](identity-exit-criteria.md#crit-identity-sync-health) für diesen Abschnitt betrachten.

## <a name="next-step"></a>Nächster Schritt

|||
|:-------|:-----|
![](./media/stepnumbers/Step4.png)| [Konfigurieren der sicheren Benutzerauthentifizierung](identity-multi-factor-authentication.md)
