---
title: Identitäts- und Gerätezugriffsvoraussetzungen für die Pass-Through-Authentifizierung in Ihrer Microsoft 365-Umgebung
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 04/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Erstellen Sie eine Microsoft 365-Umgebung zum Testen des Identitäts- und Gerätezugriffs anhand der Voraussetzungen für die Pass-Through-Authentifizierung.
ms.openlocfilehash: 7bef08ba10413f95fb23707ce2ecc4ac248c4bc2
ms.sourcegitcommit: 9ee873c6a2f738a0c99921e036894b646742e706
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2019
ms.locfileid: "38673321"
---
# <a name="identity-and-device-access-prerequisites-for-pass-through-authentication-in-your-microsoft-365-test-environment"></a>Identitäts- und Gerätezugriffsvoraussetzungen für die Pass-Through-Authentifizierung in Ihrer Microsoft 365-Umgebung

*Diese Testumgebungsanleitung kann nur für Microsoft 365 Enterprise-Testumgebungen verwendet werden.*

[Identitäts- und Gerätezugriffskonfigurationen](microsoft-365-policies-configurations.md) sind eine Reihe von Konfigurationen und Richtlinien zum Schutz des Zugriffs auf alle in Azure Active Directory (Azure AD) integrierten Dienste, einschließlich Office 365 und Enterprise Mobility + Security (EMS) in Microsoft 365 Enterprise.

In diesem Artikel wird beschrieben, wie eine Microsoft 365 Test-Umgebung konfiguriert wird, die die Anforderungen der [erforderlichen Konfiguration für die Pass-Through-Authentifizierung](identity-access-prerequisites.md#prerequisites) für den Identitäts- und Gerätezugriff erfüllt.

Es gibt acht Hauptphasen bei der Einrichtung dieser Testumgebung:

1.  Erstellen eines simulierten Unternehmens mit Pass-Through-Authentifizierung für die Microsoft 365-Testumgebung
2.  Konfigurieren des nahtlosen einmaligen Anmeldens in Azure AD
3.  Konfigurieren benannter Orte
4.  Konfigurieren von Kennwortrückschreiben
5.  Konfigurieren der Self-Service-Kennwortzurücksetzung
6.  Konfigurieren der mehrstufigen Authentifizierung
7.  Aktivieren von Azure AD Identity Protection
8.  Aktivieren der modernen Authentifizierung für Exchange Online und Skype for Business Online

## <a name="phase-1-build-out-your-simulated-enterprise-with-pass-through-authentication-microsoft-365-test-environment"></a>Phase 1: Erstellen eines simulierten Unternehmens mit Pass-Through-Authentifizierung für die Microsoft 365-Testumgebung

Befolgen Sie die Anweisungen unter [Passthrough-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).

Nachfolgend sehen Sie die daraus resultierende Konfiguration.

![Das simulierte Unternehmen mit einer Testumgebung mit Pass-Trought-Authentifizierung](media/pass-through-auth-m365-ent-test-environment/Phase2.png)
 
## <a name="phase-2-configure-azure-ad-seamless-single-sign-on"></a>Phase 2: Konfigurieren des nahtlosen einmaligen Anmeldens in Azure AD

Befolgen Sie die Anweisungen unter [Phase 2: Konfigurieren des nahtlosen einmaligen Anmeldens in Azure AD](single-sign-on-m365-ent-test-environment.md#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso) der Testumgebungsanleitungen.

## <a name="phase-3-configure-named-locations"></a>Phase 3: Konfigurieren benannter Orte

Ermitteln Sie zunächst die öffentlichen IP-Adressen oder Adressbereiche, die von Ihrer Organisation verwendet werden.

Befolgen Sie dann die Anweisungen unter [Konfigurieren benannter Orte in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations), um die Adressen oder Adressbereiche als benannte Orte hinzuzufügen. 

## <a name="phase-4-configure-password-writeback"></a>Phase 4: Konfigurieren von Kennwortrückschreiben

Folgen Sie anschließend den Anweisungen unter [Phase 2 der Kennwortrückschreibung](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain) der Testumgebungsanleitungen.

## <a name="phase-5-configure-self-service-password-reset"></a>Phase 5: Konfigurieren der Self-Service-Kennwortzurücksetzung

Folgen Sie anschließend den Anweisungen unter [Phase 3 der Kennwortzurücksetzung](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset) der Testumgebungsanleitungen. 

Wenn Sie das Zurücksetzen des Kennworts für die Konten in einer bestimmten Azure AD-Gruppe aktivieren, fügen Sie diese Konten der Gruppe **Kennwort zurücksetzen** hinzu:

- Benutzer 2
- Benutzer 3
- Benutzer 4
- Benutzer 5

Testen Sie die Kennwortzurücksetzung für das Konto von Benutzer 2.

## <a name="phase-6-configure-multi-factor-authentication"></a>Phase 6: Konfigurieren der mehrstufigen Authentifizierung

Befolgen Sie die Anweisungen unter [Phase 2 der mehrstufige Authentifizierung](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) der Testumgebungsanleitungen für die folgenden Benutzerkonten:

- Benutzer 2
- Benutzer 3
- Benutzer 4
- Benutzer 5

Testen der mehrstufigen Authentifizierung für das Konto „Benutzer 2“.

## <a name="phase-7-enable-azure-ad-identity-protection"></a>Phase 7: Aktivieren von Azure AD Identity Protection

Befolgen Sie die Anweisungen unter [Phase 2 der Testumgebungsanleitungen für Azure AD Identity Protection](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-enable-and-use-azure-ad-identity-protection). 

## <a name="phase-8-enable-modern-authentication-for-exchange-online-and-skype-for-business-online"></a>Phase 8: Aktivieren der modernen Authentifizierung für Exchange Online und Skype for Business Online

Befolgen Sie die [folgenden Anweisungen](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later) für Exchange Online. 

Für Skype for Business Online:

1. Stellen Sie eine Verbindung zu [Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) her.

2. Führen Sie den folgenden Befehl aus.

  ```powershell
  Set-CsOAuthConfiguration -ClientAdalAuthOverride Allowed
  ```

3. Führen Sie den folgenden Befehl aus, um sich zu vergewissern, dass die Änderung erfolgreich war.

  ```powershell
  Get-CsOAuthConfiguration
  ```

Das Ergebnis ist eine Test-Umgebung, die die Anforderungen der [erforderlichen Konfiguration für die Pass-Through-Authentifizierung](identity-access-prerequisites.md#prerequisites) für den Identitäts- und Gerätezugriff erfüllt. 

## <a name="next-step"></a>Nächster Schritt

Verwenden Sie [Gemeinsame Identitäts- und Gerätezugriffsrichtlinien](identity-access-policies.md), um die Richtlinien zu konfigurieren, die auf den Voraussetzungen aufbauen und Identitäten und Geräte schützen.

## <a name="see-also"></a>Siehe auch

[Testumgebungsanleitungen für zusätzliche Identitäten](m365-enterprise-test-lab-guides.md#identity)

[Phase 2: Identität](identity-infrastructure.md)

[Testumgebungsanleitungen für Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Microsoft 365 Enterprise-Bereitstellungshandbuch](deploy-microsoft-365-enterprise.md)

[Dokumentation zu Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)

