---
title: Aktivieren von Domänenbeitritt von Windows 10-Geräten, die von Microsoft 365 for Business verwaltet werden
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
search.appverid:
- BCS160
- MET150
ms.assetid: 9b4de218-f1ad-41fa-a61b-e9e8ac0cf993
description: In diesem Artikel erfahren Sie, wie Sie Microsoft 365 in wenigen Schritten zum Schutz von lokalen Active Directory-verbundenen Windows 10-Geräten aktivieren.
ms.openlocfilehash: 431c1be74723e156befb13ffe1ed98b48b9a23cb
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43633281"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-for-business"></a>Aktivieren von Domänenbeitritt von Windows 10-Geräten, die von Microsoft 365 for Business verwaltet werden

Wenn Ihre Organisation Windows Server Active Directory lokal verwendet, können Sie Microsoft 365 for Business zum Schutz Ihrer Windows 10-Geräte einrichten und gleichzeitig den Zugriff auf lokale Ressourcen aufrecht erhalten, die eine lokale Authentifizierung erfordern.
Um diesen Schutz einzurichten, können Sie **hybride Azure AD verbundene Geräte**implementieren. Diese Geräte sind sowohl mit Ihrem lokalen Active Directory als auch mit Ihrem Azure-Active Directory verbunden.

In diesem Video werden die Schritte beschrieben, wie Sie dies für das am häufigsten verwendete Szenario einrichten, das auch in den folgenden Schritten detailliert erläutert wird.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  

## <a name="1-prepare-for-directory-synchronization"></a>1. Vorbereiten der Verzeichnissynchronisierung 

Bevor Sie Ihre Benutzer und Computer aus der lokalen Active Directory Domäne synchronisieren, überprüfen Sie die [Verzeichnissynchronisierung auf Office 365 vorbereiten](https://docs.microsoft.com/office365/enterprise/prepare-for-directory-synchronization). Insbesondere:

   - Stellen Sie sicher, dass in Ihrem Verzeichnis keine Duplikate für die folgenden Attribute vorhanden sind: **Mail**, **proxyAddresses**und **userPrincipalName**. Diese Werte müssen eindeutig sein, und alle Duplikate müssen entfernt werden.
   
   - Es wird empfohlen, das UPN-Attribut ( **userPrincipalName** ) für jedes lokale Benutzerkonto so zu konfigurieren, dass es mit der primären e-Mail-Adresse übereinstimmt, die dem lizenzierten Microsoft 365-Benutzer entspricht. Beispiel: *Mary.Shelley@contoso.com* statt *Mary@contoso. local*
   
   - Wenn die Active Directory Domäne in einem nicht routingfähigen Suffix wie *. local* oder *. LAN*endet, müssen Sie anstelle eines über das Internet routingfähigen Suffixes wie *. com* oder *. org*das UPN-Suffix der lokalen Benutzerkonten anpassen, wie unter [Vorbereiten einer nicht routingfähigen Domäne für die Verzeichnissynchronisierung](https://docs.microsoft.com/office365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization)beschrieben. 

## <a name="2-install-and-configure-azure-ad-connect"></a>2. installieren und Konfigurieren von Azure AD Connect

Wenn Sie Ihre Benutzer, Gruppen und Kontakte vom lokalen Active Directory in Azure Active Directory synchronisieren möchten, installieren Sie Azure Active Directory Connect, und richten Sie die Verzeichnissynchronisierung ein. Weitere Informationen finden Sie unter [Einrichten der Verzeichnissynchronisierung für Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846) .

> [!NOTE]
> Die Schritte sind für Microsoft 365 for Business genau gleich. 

Wenn Sie Ihre Optionen für Azure AD Connect konfigurieren, wird empfohlen, dass Sie die **Kennwortsynchronisierung**, das **nahtlose einmalige Anmelden**und das **Kenn Wort Rückschreibe** Feature aktivieren, das auch in Microsoft 365 for Business unterstützt wird.

> [!NOTE]
> Es gibt einige zusätzliche Schritte für das Kenn Wort Rückschreiben über das Kontrollkästchen in Azure AD Connect hinaus. Weitere Informationen finden Sie unter [Vorgehensweise: Konfigurieren des Kenn Wort](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback)Rückschreibens. 

## <a name="3-configure-hybrid-azure-ad-join"></a>3. Konfigurieren des Joins für Hybrid Azure AD

Stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind, bevor Sie Windows 10-Geräte so aktivieren, dass Sie Hybrid Azure AD verbunden sind:

   - Sie führen die neueste Version von Azure AD Connect aus.

   - Azure AD Connect hat alle Computerobjekte der Geräte synchronisiert, die Sie als Hybrid Azure AD verbunden haben möchten. Wenn die Computerobjekte bestimmten Organisationseinheiten (Organizational Units, OU) angehören, stellen Sie sicher, dass diese OUs in Azure AD Connect ebenfalls für die Synchronisierung festgelegt sind.

Führen Sie die Schritte im [Lernprogramm: Configure Hybrid Azure Active Directory Join for Managed Domains](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join)aus, um die vorhandenen Domänen verbundenen Windows 10-Geräte als Hybrid Azure AD registriert zu registrieren. Dieser Hybrid aktiviert ihre vorhandenen lokalen Active Directory den Windows 10-Computern beigetreten sind und Sie zur Cloud bereit machen.
    
## <a name="4-enable-automatic-enrollment-for-windows-10"></a>4. Aktivieren der automatischen Registrierung für Windows 10

 Informationen zum automatischen Registrieren von Windows 10-Geräten für die Verwaltung mobiler Geräte in InTune finden Sie unter [Registrieren eines Windows 10-Geräts automatisch mithilfe von Gruppenrichtlinien](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy). Sie können die Gruppenrichtlinie auf lokaler Computerebene oder für Massenvorgänge festlegen, indem Sie die Gruppenrichtlinien-Verwaltungskonsole und ADMX-Vorlagen verwenden, um diese Gruppenrichtlinieneinstellung auf dem Domänen Controller zu erstellen.

## <a name="5-configure-seamless-single-sign-on"></a>5. Konfigurieren des nahtlosen einmaligen Anmeldens

  Seamless SSO signiert Benutzer automatisch bei Verwendung von Unternehmenscomputern in Ihre Microsoft 365 Cloud-Ressourcen. Stellen Sie einfach eine der beiden in Azure beschriebenen Gruppenrichtlinienoptionen bereit [Active Directory nahtloses einmaliges Anmelden: Schnellstart](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sso-quick-start#step-2-enable-the-feature). Mit der **Gruppenrichtlinien** Option können Benutzer Ihre Einstellungen nicht ändern, während die Option **Gruppenrichtlinieneinstellung** die Werte festlegt, Sie aber auch Benutzer konfigurierbar lässt.

## <a name="6-set-up-windows-hello-for-business"></a>6. Einrichten von Windows Hello for Business

 Windows Hello for Business ersetzt Kennwörter mit starker zweistufiger Authentifizierung (2FA) für die Anmeldung bei einem lokalen Computer. Ein Faktor ist ein asymmetrisches Schlüsselpaar, das andere eine PIN oder andere lokale Geste wie Fingerabdruck oder Gesichtserkennung, wenn Ihr Gerät Sie unterstützt. Es wird empfohlen, nach Möglichkeit Kennwörter durch 2FA und Windows Hello for Business zu ersetzen.

Überprüfen Sie zum Konfigurieren von Hybrid-Windows Hello for Business die [Voraussetzungen für den Hybrid Schlüssel Trust Windows Hello for Business](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-key-trust-prereqs). Befolgen Sie dann die Anweisungen unter [configure Hybrid Windows Hello for Business Key Trust Settings](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-key-whfb-settings). 
