---
title: Pass-Through-Authentifizierung für Ihre Microsoft 365-Testumgebung
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/13/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLG
- Ent_TLGs
ms.assetid: ''
description: 'Zusammenfassung: Konfigurieren von Pass-Through-Authentifizierung für Ihre Microsoft 365-Testumgebung.'
ms.openlocfilehash: 4835b909dbe20f449828b604192d9f3957f54c5c
ms.sourcegitcommit: 2c2248b03f7753d64490f2f7e56ec644a235b65a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2019
ms.locfileid: "38640734"
---
# <a name="pass-through-authentication-for-your-microsoft-365-test-environment"></a>Pass-Through-Authentifizierung für Ihre Microsoft 365-Testumgebung

Organisationen, die ihre lokale Active Directory Domain Services(AD DS)-Infrastruktur direkt für die Authentifizierung bei Cloud-basierten Microsoft-Diensten und -Anwendungen verwenden möchten, können Pass-Through-Authentifizierung verwenden. Dieser Artikel beschreibt, wie Sie Ihre Microsoft 365-Testumgebung für Pass-Through-Authentifizierung konfigurieren, was zu folgender Konfiguration führt:
  
![Das simulierte Unternehmen mit einer Testumgebung mit Pass-Trought-Authentifizierung](media/pass-through-auth-m365-ent-test-environment/Phase2.png)
  
Es gibt zwei Hauptphasen bei der Einrichtung dieser Testumgebung:

1.  Erstellen Sie die simulierte Microsoft 365-Testunternehmensumgebung mit Kennworthashsynchronisierung.
2.  Konfigurieren Sie Azure AD Connect auf APP1 für Pass-Through-Authentifizierung.
    
![Testumgebungsanleitungen für die Microsoft-Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Klicken Sie [hier](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Phase 1: Konfigurieren Sie Kennworthashsynchronisierung für Ihre Microsoft 365-Testumgebung

Befolgen Sie die Anweisungen unter [Kennworthashsynchronisierung für Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Hier ist die resultierende Konfiguration.
  
![Das simulierte Unternehmen mit Kennworthashsynchronisierung für die Testumgebung](media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
Diese Konfiguration besteht aus: 
  
- Testversionen oder kostenpflichtigen Abonnements von Office 365 E5 und EMS E5.
- Einem vereinfachtem Unternehmensintranet mit Internetzugriff, das aus virtuellen DC1-, APP1- und CLIENT1-Computern in einem Subnetz eines virtuellen Azure-Netzwerks besteht. Azure AD Connect wird auf APP1 ausgeführt, um die AD DS-Domäne "TESTLAB" mit dem Azure AD-Mandanten Ihrer Office 365- und EMS E5-Abonnements regelmäßig zu synchronisieren.

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-pass-through-authentication"></a>Phase 2: Konfigurieren Sie Azure AD Connect auf APP1 für Pass-Through-Authentifizierung

In dieser Phase konfigurieren Sie Azure AD Connect auf APP1 für die Verwendung von Pass-Through-Authentifizierung und vergewissern sich dann, dass sie funktioniert.

### <a name="configure-azure-ad-connect-on-app1"></a>Konfigurieren von Azure AD Connect auf APP1

1.  Melden Sie sich über das [Azure-Portal](https://portal.azure.com) mit Ihrem globalen Administratorkonto an, und stellen Sie dann mit dem Konto „TESTLAB\User1“ eine Verbindung zu APP1 her.

2.  Führen Sie Azure AD Connect über den Desktop von APP1 aus.

3.  Klicken Sie auf der Seite **Willkommen** auf **Konfigurieren**.

4.  Klicken Sie auf der Seite „Weitere Aufgaben“ auf **Benutzeranmeldung ändern**, und klicken Sie dann auf **Weiter**.

5.  Geben Sie auf der Seite **Mit Azure AD verbinden** die Anmeldeinformationen für das globale Administratorkonto ein, und klicken Sie dann auf **Weiter**.

6.  Klicken Sie auf der Seite **Benutzeranmeldung** auf **Pass-Through-Authentifizierung**, und klicken Sie dann auf **Weiter**.

7.  Klicken Sie auf der Seite **Bereit zur Konfiguration** auf **Konfigurieren**.

8.  Klicken Sie auf der Seite **Konfiguration abgeschlossen** auf **Beenden**.

9.  Klicken Sie im Azure-Portal im linken Bereich auf **Azure Active Directory > Azure AD Connect**. Überprüfen Sie, ob die Funktion **Pass-Through-Authentifizierung** als **Aktiviert** angezeigt wird.

10. Klicken Sie auf **Pass-Through-Authentifizierung**. Im Bereich **Pass-Through-Authentifizierung** werden die Server aufgeführt, auf denen Ihre Authentifizierungsagenten installiert sind. APP1 sollte in der Liste angezeigt werden. Schließen Sie den Bereich **Pass-Through-Authentifizierung**.

Als Nächstes testen Sie, ob Sie sich mit dem Benutzernamen <strong>user1@testlab.</strong>\<Ihre öffentliche Domäne> des Kontos „Benutzer1“ beim Ihrem Office 365-Abonnement anmelden können.

1. Melden Sie sich auf APP1 von Office 365 ab, und melden Sie sich dann erneut an. Geben Sie dieses Mal ein anderes Konto an.

2. Wenn Sie aufgefordert werden, einen Benutzernamen und ein Kennwort anzugeben, geben Sie <strong>user1@testlab.</strong>\<Ihre öffentliche Domäne> und das Kennwort für Benutzer 1 an. Sie sollten sich erfolgreich als „Benutzer 1“ anmelden können.

Beachten Sie, dass „Benutzer 1" zwar über Administratorberechtigungen für die AD DS-Domäne TESTLAB verfügt, er aber kein globaler Administrator für Office 365 ist. Daher wird das Symbol **Admin** nicht als Option angezeigt.

Nachfolgend sehen Sie die daraus resultierende Konfiguration:

![Das simulierte Unternehmen mit einer Testumgebung mit Pass-Trought-Authentifizierung](media/pass-through-auth-m365-ent-test-environment/Phase2.png)
 
Diese Konfiguration besteht aus: 

- Testversionen oder kostenpflichtige Abonnements von Office 365 E5 und EMS E5 mit der registrierten DNS-Domäne testlab.\<Ihr Domänenname>.
- Einem vereinfachtem Unternehmensintranet mit Internetzugriff, das aus virtuellen DC1-, APP1- und CLIENT1-Computern in einem Subnetz eines virtuellen Azure-Netzwerks besteht. Ein Authentifizierungsagent wird auf APP1 für die Verarbeitung von Pass-Through-Authentifizierungsanfragen vom Azure AD-Mandanten Ihrer Office 365- und EMS E5-Abonnements ausgeführt.

## <a name="next-step"></a>Nächster Schritt

Sehen Sie sich weitere [Identitäts](m365-enterprise-test-lab-guides.md#identity)features und- funktionen in Ihrer Testumgebung an.

## <a name="see-also"></a>Siehe auch

[Testumgebungsanleitungen für Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Bereitstellen von Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Dokumentation zu Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)


