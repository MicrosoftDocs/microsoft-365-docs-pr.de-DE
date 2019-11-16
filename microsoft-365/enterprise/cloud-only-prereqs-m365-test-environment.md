---
title: Voraussetzungen für Identitäts- und Gerätezugriff für reine Cloudbereitstellung in Ihrer Microsoft 365-Testumgebung
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
description: Erstellen Sie eine Microsoft 365-Umgebung zum Testen des Identitäts- und Gerätezugriffs anhand der Voraussetzungen für die Authentifizierung der reinen Cloudbereitstellung.
ms.openlocfilehash: 6e0796d24f2644907d214c4528eab2051fa3d83c
ms.sourcegitcommit: 9ee873c6a2f738a0c99921e036894b646742e706
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2019
ms.locfileid: "38673231"
---
# <a name="identity-and-device-access-prerequisites-for-cloud-only-in-your-microsoft-365-test-environment"></a>Voraussetzungen für Identitäts- und Gerätezugriff für reine Cloudbereitstellung in Ihrer Microsoft 365-Testumgebung

*Diese Testumgebungsanleitung kann nur für Microsoft 365 Enterprise-Testumgebungen verwendet werden.*

[Identitäts- und Gerätezugriffskonfigurationen](microsoft-365-policies-configurations.md) sind eine Reihe von Konfigurationen und Richtlinien zum Schutz des Zugriffs auf alle in Azure Active Directory (Azure AD) integrierten Dienste, einschließlich Office 365 und Microsoft Intune in Microsoft 365 Enterprise.

In diesem Artikel wird beschrieben, wie eine Microsoft 365 Test-Umgebung konfiguriert wird, die die Anforderungen der [erforderlichen Konfiguration für die reine Cloudbereitstellung](identity-access-prerequisites.md#prerequisites) für den Identitäts- und Gerätezugriff erfüllt.

Es gibt sieben Hauptphasen bei der Einrichtung dieser Testumgebung:

1.  Erstellen einer einfachen Testumgebung
2.  Konfigurieren benannter Orte
3.  Konfigurieren von Kennwortrückschreiben
4.  Konfigurieren von Self-Service-Kennwortzurücksetzungen
5.  Konfigurieren der mehrstufigen Authentifizierung
6.  Aktivieren von Azure AD Identity Protection
7.  Aktivieren der modernen Authentifizierung für Exchange Online und Skype for Business Online

## <a name="phase-1-build-out-your-lightweight-microsoft-365-test-environment"></a>Phase 1: Erstellen einer einfachen Microsoft 365-Testumgebung

Befolgen Sie die Anweisungen unter [Einfache Basiskonfiguration](lightweight-base-configuration-microsoft-365-enterprise.md).
Nachfolgend sehen Sie die daraus resultierende Konfiguration.

![Einfache Microsoft 365 Enterprise-Testumgebung](media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)
 

## <a name="phase-2-configure-named-locations"></a>Phase 2: Konfigurieren benannter Orte

Ermitteln Sie zunächst die öffentlichen IP-Adressen oder Adressbereiche, die von Ihrer Organisation verwendet werden.

Befolgen Sie dann die Anweisungen unter [Konfigurieren benannter Orte in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations), um die Adressen oder Adressbereiche als benannte Orte hinzuzufügen. 

## <a name="phase-3-configure-password-writeback"></a>Phase 3: Konfigurieren von Kennwortrückschreiben

Folgen Sie anschließend den Anweisungen unter [Phase 2 der Kennwortrückschreibung](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain) der Testumgebungsanleitungen.

## <a name="phase-4-configure-self-service-password-reset"></a>Phase 4: Konfigurieren der Self-Service-Kennwortzurücksetzung

Folgen Sie anschließend den Anweisungen unter [Phase 3 der Kennwortzurücksetzung](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset) der Testumgebungsanleitungen. 

Wenn Sie das Zurücksetzen des Kennworts für die Konten in einer bestimmten Azure AD-Gruppe aktivieren, fügen Sie diese Konten der Gruppe **Kennwort zurücksetzen** hinzu:

- Benutzer 2
- Benutzer 3
- Benutzer 4
- Benutzer 5

Testen Sie die Kennwortzurücksetzung für das Konto von Benutzer 2.

## <a name="phase-5-configure-multi-factor-authentication"></a>Phase 5: Konfigurieren der mehrstufigen Authentifizierung

Befolgen Sie die Anweisungen unter [Phase 2 der mehrstufige Authentifizierung](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) der Testumgebungsanleitungen für die folgenden Benutzerkonten:

- Benutzer 2
- Benutzer 3
- Benutzer 4
- Benutzer 5

Testen der mehrstufigen Authentifizierung für das Konto „Benutzer 2“.

## <a name="phase-6-enable-azure-ad-identity-protection"></a>Phase 6: Aktivieren von Azure AD Identity Protection

Befolgen Sie die Anweisungen unter [Phase 2 der Testumgebungsanleitungen für Azure AD Identity Protection](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-enable-and-use-azure-ad-identity-protection). 

## <a name="phase-7-enable-modern-authentication-for-exchange-online-and-skype-for-business-online"></a>Phase 7: Aktivieren der modernen Authentifizierung für Exchange Online und Skype for Business Online

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

Das Ergebnis ist eine Testumgebung, die die Anforderungen der [erforderlichen Konfiguration für reine Cloudbereitstellung](identity-access-prerequisites.md#prerequisites) für den Identitäts- und Gerätezugriff erfüllt. 

## <a name="next-step"></a>Nächster Schritt

Verwenden Sie [Gemeinsame Identitäts- und Gerätezugriffsrichtlinien](identity-access-policies.md), um die Richtlinien zu konfigurieren, die auf den Voraussetzungen aufbauen und Identitäten und Geräte schützen.

## <a name="see-also"></a>Siehe auch

[Testumgebungsanleitungen für zusätzliche Identitäten](m365-enterprise-test-lab-guides.md#identity)

[Phase 2: Identität](identity-infrastructure.md)

[Testumgebungsanleitungen für Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Microsoft 365 Enterprise-Bereitstellungshandbuch](deploy-microsoft-365-enterprise.md)

[Dokumentation zu Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
