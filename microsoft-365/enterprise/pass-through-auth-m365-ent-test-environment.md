---
title: Pass-Through-Authentifizierung für Ihre Microsoft 365-Testumgebung
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/21/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLG
- Ent_TLGs
ms.assetid: ''
description: 'Zusammenfassung: Konfigurieren von Pass-Through-Authentifizierung für Ihre Microsoft 365-Testumgebung.'
ms.openlocfilehash: d83de4ece4d1eaeddac882cf46a4fe85b8ba7cd4
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487446"
---
# <a name="pass-through-authentication-for-your-microsoft-365-test-environment"></a>Pass-Through-Authentifizierung für Ihre Microsoft 365-Testumgebung

*Diese Test Umgebungs Anleitung kann sowohl für Microsoft 365 für Unternehmen als auch für Office 365 Enterprise Testumgebungen verwendet werden.*

Organisationen, die ihre lokale Active Directory Domain Services(AD DS)-Infrastruktur direkt für die Authentifizierung bei Cloud-basierten Microsoft-Diensten und -Anwendungen verwenden möchten, können Pass-Through-Authentifizierung verwenden. Dieser Artikel beschreibt, wie Sie Ihre Microsoft 365-Testumgebung für Pass-Through-Authentifizierung konfigurieren, was zu folgender Konfiguration führt:
  
![Das simulierte Unternehmen mit einer Testumgebung mit Pass-Trought-Authentifizierung](../media/pass-through-auth-m365-ent-test-environment/Phase2.png)
  
Es gibt zwei Hauptphasen bei der Einrichtung dieser Testumgebung:

1.    Erstellen Sie die simulierte Microsoft 365-Testunternehmensumgebung mit Kennworthashsynchronisierung.
2.    Konfigurieren Sie Azure AD Connect auf APP1 für Pass-Through-Authentifizierung.
    
![Testumgebungsanleitungen für die Microsoft-Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Klicken Sie [hier](../downloads/Microsoft365EnterpriseTLGStack.pdf), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Phase 1: Konfigurieren Sie Kennworthashsynchronisierung für Ihre Microsoft 365-Testumgebung

Befolgen Sie die Anweisungen unter [Kennworthashsynchronisierung für Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Hier ist die resultierende Konfiguration.
  
![Das simulierte Unternehmen mit Kennworthashsynchronisierung für die Testumgebung](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
Diese Konfiguration besteht aus:  
  
- Microsoft 365 E5-Testversion oder ein kostenpflichtiges Abonnement.
- Einem vereinfachtem Unternehmensintranet mit Internetzugriff, das aus virtuellen DC1-, APP1- und CLIENT1-Computern in einem Subnetz eines virtuellen Azure-Netzwerks besteht. Azure AD Connect wird auf APP1 ausgeführt, um die AD DS-Domäne "TESTLAB" mit dem Azure AD-Mandanten Ihres Microsoft 365-Abonnements regelmäßig zu synchronisieren.

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-pass-through-authentication"></a>Phase 2: Konfigurieren Sie Azure AD Connect auf APP1 für Pass-Through-Authentifizierung

In dieser Phase konfigurieren Sie Azure AD Connect auf APP1 für die Verwendung von Pass-Through-Authentifizierung und vergewissern sich dann, dass sie funktioniert.

### <a name="configure-azure-ad-connect-on-app1"></a>Konfigurieren von Azure AD Connect auf APP1

1.    Melden Sie sich über das [Azure-Portal](https://portal.azure.com) mit Ihrem globalen Administratorkonto an, und stellen Sie dann mit dem Konto „TESTLAB\User1“ eine Verbindung zu APP1 her.

2.    Führen Sie Azure AD Connect über den Desktop von APP1 aus.

3.    Klicken Sie auf der Seite **Willkommen** auf **Konfigurieren**.

4.    Klicken Sie auf der Seite „Weitere Aufgaben“ auf **Benutzeranmeldung ändern**, und klicken Sie dann auf **Weiter**.

5.    Geben Sie auf der Seite **Mit Azure AD verbinden** die Anmeldeinformationen für das globale Administratorkonto ein, und klicken Sie dann auf **Weiter**.

6.    Klicken Sie auf der Seite **Benutzeranmeldung** auf **Pass-Through-Authentifizierung**, und klicken Sie dann auf **Weiter**.

7.    Klicken Sie auf der Seite **Bereit zur Konfiguration** auf **Konfigurieren**.

8.    Klicken Sie auf der Seite **Konfiguration abgeschlossen** auf **Beenden**.

9.    Klicken Sie im Azure-Portal im linken Bereich auf **Azure Active Directory > Azure AD Connect**. Überprüfen Sie, ob die Funktion **Pass-Through-Authentifizierung** als **Aktiviert** angezeigt wird.

10.    Klicken Sie auf **Pass-Through-Authentifizierung**. Im Bereich **Pass-Through-Authentifizierung** werden die Server aufgeführt, auf denen Ihre Authentifizierungsagenten installiert sind. APP1 sollte in der Liste angezeigt werden. Schließen Sie den Bereich **Pass-Through-Authentifizierung**.

Testen Sie als nächstes die Möglichkeit, sich mit dem user1@testlab bei Ihrem Abonnement anzumelden <strong>.</strong>\<your public domain> Benutzername des User1-Kontos.

1. Melden Sie sich über APP1 ab, und melden Sie sich dann erneut an. Geben Sie dieses Mal ein anderes Konto an.

2. Wenn Sie zur Eingabe eines Benutzernamens und Kennworts aufgefordert werden, geben Sie <strong>user1@testlab.</strong>\<your public domain> ein und das Kennwort für User1. Sie sollten sich erfolgreich als „Benutzer 1“ anmelden können.

Beachten Sie, dass "User1" zwar über Administratorberechtigungen für die AD DS-Domäne TESTLAB verfügt, er aber kein globaler Administrator ist. Daher wird das Symbol **Admin** nicht als Option angezeigt.

Nachfolgend sehen Sie die daraus resultierende Konfiguration:

![Das simulierte Unternehmen mit einer Testumgebung mit Pass-Trought-Authentifizierung](../media/pass-through-auth-m365-ent-test-environment/Phase2.png)
 
Diese Konfiguration besteht aus: 

- Eine Microsoft 365 E5-Testversion oder kostenpflichtige Abonnements mit der DNS-Domäne testlab.\<your domain name> registriert.
- Einem vereinfachtem Unternehmensintranet mit Internetzugriff, das aus virtuellen DC1-, APP1- und CLIENT1-Computern in einem Subnetz eines virtuellen Azure-Netzwerks besteht. Ein Authentifizierungsagent wird auf APP1 für die Verarbeitung von Pass-Through-Authentifizierungsanfragen vom Azure AD-Mandanten Ihres Microsoft 365-Abonnements ausgeführt.

## <a name="next-step"></a>Nächster Schritt

Sehen Sie sich weitere [Identitäts](m365-enterprise-test-lab-guides.md#identity)features und- funktionen in Ihrer Testumgebung an.

## <a name="see-also"></a>Siehe auch

[Testumgebungsanleitungen für Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Übersicht über Microsoft 365 Enterprise](microsoft-365-overview.md)

[Dokumentation zu Microsoft 365 für Unternehmen](https://docs.microsoft.com/microsoft-365-enterprise/)
