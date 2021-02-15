---
title: Voraussetzungen für Identitäts- und Gerätezugriff für reine Cloudbereitstellung in Ihrer Microsoft 365-Testumgebung
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Erstellen Sie eine Microsoft 365-Umgebung zum Testen des Identitäts- und Gerätezugriffs anhand der Voraussetzungen für die Authentifizierung der reinen Cloudbereitstellung.
ms.openlocfilehash: 1e659304eee330960937b641c9a39b03920f52e7
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233130"
---
# <a name="identity-and-device-access-prerequisites-for-cloud-only-in-your-microsoft-365-test-environment"></a>Voraussetzungen für Identitäts- und Gerätezugriff für reine Cloudbereitstellung in Ihrer Microsoft 365-Testumgebung

*Diese Testumgebungsanleitung kann nur für Microsoft 365 Enterprise-Testumgebungen verwendet werden.*

[Identitäts- und Gerätezugriffskonfigurationen](../security/office-365-security/microsoft-365-policies-configurations.md) sind eine Reihe empfohlener Konfigurationen und Richtlinien für bedingten Zugriff zum Schutz des Zugriffs auf alle Dienste, die in Azure Active Directory (Azure AD) integriert sind.

In diesem Artikel wird beschrieben, wie eine Microsoft 365 Test-Umgebung konfiguriert wird, die die Anforderungen der [erforderlichen Konfiguration für die reine Cloudbereitstellung](../security/office-365-security/identity-access-prerequisites.md#prerequisites) für den Identitäts- und Gerätezugriff erfüllt.

Es gibt acht Hauptphasen bei der Einrichtung dieser Testumgebung:

1. Erstellen einer einfachen Testumgebung
2. Konfigurieren benannter Orte
3. Konfigurieren der Self-Service-Kennwortzurücksetzung
4. Konfigurieren der mehrstufigen Authentifizierung
5. Aktivieren der automatischen Geräteregistrierung für in die Domäne beigetretene Windows-Computer
6. Konfigurieren des Azure AD-Kennwortschutzes 
7. Aktivieren von Azure AD Identity Protection
8. Aktivieren der modernen Authentifizierung für Exchange Online und Skype for Business Online

## <a name="phase-1-build-out-your-lightweight-microsoft-365-test-environment"></a>Phase 1: Erstellen einer einfachen Microsoft 365-Testumgebung

Befolgen Sie die Anweisungen unter [Einfache Basiskonfiguration](lightweight-base-configuration-microsoft-365-enterprise.md).
Nachfolgend sehen Sie die daraus resultierende Konfiguration.

![Einfache Microsoft 365 Enterprise-Testumgebung](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)
 
## <a name="phase-2-configure-named-locations"></a>Phase 2: Konfigurieren benannter Orte

Ermitteln Sie zunächst die öffentlichen IP-Adressen oder Adressbereiche, die von Ihrer Organisation verwendet werden.

Befolgen Sie dann die Anweisungen unter [Konfigurieren benannter Orte in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations), um die Adressen oder Adressbereiche als benannte Orte hinzuzufügen. 

## <a name="phase-3-configure-self-service-password-reset"></a>Phase 3: Konfigurieren der Self-Service-Kennwortzurücksetzung

Folgen Sie anschließend den Anweisungen unter [Phase 3 der Kennwortzurücksetzung](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset) der Testumgebungsanleitungen. 

Wenn Sie das Zurücksetzen des Kennworts für die Konten in einer bestimmten Azure AD-Gruppe aktivieren, fügen Sie diese Konten der Gruppe **Kennwort zurücksetzen** hinzu:

- Benutzer 2
- Benutzer 3
- Benutzer 4
- Benutzer 5

Testen Sie die Kennwortzurücksetzung für das Konto von Benutzer 2.

## <a name="phase-4-configure-multi-factor-authentication"></a>Phase 4: Konfigurieren der mehrstufigen Authentifizierung

Befolgen Sie die Anweisungen unter [Phase 2 der mehrstufige Authentifizierung](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) der Testumgebungsanleitungen für die folgenden Benutzerkonten:

- Benutzer 2
- Benutzer 3
- Benutzer 4
- Benutzer 5

Testen der mehrstufigen Authentifizierung für das Konto „Benutzer 2“.

## <a name="phase-5-enable-automatic-device-registration-of-domain-joined-windows-computers"></a>Phase 5: Aktivieren der automatischen Geräteregistrierung für in die Domäne beigetretene Windows-Computer 

Führen [Sie die folgenden Anweisungen](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-plan) aus, um die automatische Geräteregistrierung für in die Domäne beigetretene Windows-Computer zu aktivieren.

## <a name="phase-6-configure-azure-ad-password-protection"></a>Phase 6: Konfigurieren des Azure AD-Kennwortschutzes 

Befolgen [Sie diese Anweisungen,](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) um bekannte schwache Kennwörter und deren Varianten zu blockieren.

## <a name="phase-7-enable-azure-ad-identity-protection"></a>Phase 7: Aktivieren von Azure AD Identity Protection

Befolgen Sie die Anweisungen unter [Phase 2 der Testumgebungsanleitungen für Azure AD Identity Protection](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection). 

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

Das Ergebnis ist eine Testumgebung, die die Anforderungen der nur für die [Cloud](../security/office-365-security/identity-access-prerequisites.md#prerequisites) erforderlichen Konfiguration für den Identitäts- und Gerätezugriff erfüllt. 

## <a name="next-step"></a>Nächster Schritt

Verwenden Sie [Gemeinsame Identitäts- und Gerätezugriffsrichtlinien](identity-access-policies.md), um die Richtlinien zu konfigurieren, die auf den Voraussetzungen aufbauen und Identitäten und Geräte schützen.

## <a name="see-also"></a>Siehe auch

[Testumgebungsanleitungen für zusätzliche Identitäten](m365-enterprise-test-lab-guides.md#identity)

[Identitätsplan](identity-roadmap-microsoft-365.md)

[Testumgebungsanleitungen für Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Übersicht über Microsoft 365 Enterprise](microsoft-365-overview.md)

[Dokumentation zu Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
