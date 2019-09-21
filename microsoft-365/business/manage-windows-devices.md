---
title: Aktivieren von Domänenbeitritt von Windows 10-Geräten, die von Microsoft 365 Business verwaltet werden
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
search.appverid:
- BCS160
- MET150
ms.assetid: 9b4de218-f1ad-41fa-a61b-e9e8ac0cf993
description: In diesem Artikel erfahren Sie, wie Sie Microsoft 365 zum Schutz von lokalen AD-Joints von Windows 10-Geräten aktivieren.
ms.openlocfilehash: 15804a0bd6cf9d013c5138470aa4a4a7acec57e1
ms.sourcegitcommit: 08c334b754bd6d64375b33d91a972a31f2f309cb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/21/2019
ms.locfileid: "37100439"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business"></a>Aktivieren von Domänenbeitritt von Windows 10-Geräten, die von Microsoft 365 Business verwaltet werden

Wenn Ihre Organisation Windows Server Active Directory lokal verwendet, können Sie Microsoft 365 Business zum Schutz Ihrer Windows 10-Geräte einrichten und gleichzeitig den Zugriff auf lokale Ressourcen aufrecht erhalten, die lokale Authentifizierung erfordern.
Um dies festzulegen, können Sie **hybride Azure AD verbundene Geräte**implementieren. Dabei handelt es sich um Geräte, die sowohl zu Ihrer lokalen Active Directory als auch zu Ihrem Azure-Active Directory hinzugefügt werden.

Im folgenden Video werden die Schritte beschrieben, wie Sie diese Einstellung für das gängigste Szenario festlegen können, das auch in den folgenden Schritten detailliert beschrieben wird.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  

## <a name="1-prepare-for-directory-synchronization"></a>1. Vorbereiten der Verzeichnissynchronisierung 

Bevor Sie Ihre Benutzer und Computer aus der lokalen Active Directory Domäne synchronisieren, überprüfen Sie die [Verzeichnissynchronisierung auf Office 365 vorbereiten](https://docs.microsoft.com/office365/enterprise/prepare-for-directory-synchronization). Insbesondere:

   - Stellen Sie sicher, dass in Ihrem Verzeichnis keine Duplikate für die folgenden Attribute vorhanden sind: **Mail**, **proxyAddresses**und **userPrincipalName**. Diese Werte sollten eindeutig sein, und alle Duplikate sollten entfernt werden..
   
   - Es wird empfohlen, das UPN-Attribut ( **userPrincipalName** ) für jedes lokale Benutzerkonto so zu konfigurieren, dass es der primären e-Mail-Adresse entspricht, die dem lizenzierten Microsoft 365-Benutzer entspricht. Beispiel *: Mary. Shelley @<span>contoso.<span> com* statt *Mary @ contoso. local*
   
   - Wenn die Active Directory Domäne in einem nicht routingfähigen Suffix wie *. local* oder *. LAN*endet, müssen Sie anstelle eines routingfähigen Internet-Suffixes wie *. com* oder *. org*das UPN-Suffix der lokalen Benutzerkonten wie in beschrieben anpassen. [Vorbereiten einer nicht routingfähigen Domäne für die Verzeichnissynchronisierung](https://docs.microsoft.com/office365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization). 

## <a name="2-install-and-configure-azure-ad-connect"></a>2. installieren und Konfigurieren von Azure AD Connect

Wenn Sie Ihre Benutzer, Gruppen und Kontakte vom lokalen Active Directory in Azure Active Directory synchronisieren möchten, installieren Sie Azure Active Directory Connect, und richten Sie die Verzeichnissynchronisierung ein. Weitere Informationen finden Sie unter [Einrichten der Verzeichnissynchronisierung für Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846) .

> [!NOTE]
> Die Schritte sind für Microsoft 365 Business genau gleich. 

Wenn Sie Ihre Optionen für Azure AD Connect konfigurieren, empfehlen wir die Aktivierung der **Kennwortsynchronisierung** und des **nahtlosen einmaligen Anmeldens**sowie das Feature zum **Kenn Wort** Rückschreiben, das in Microsoft 365 Business ebenfalls unterstützt wird.

> [!NOTE]
> Es gibt einige zusätzliche Schritte für das Kenn Wort Rückschreiben über das Kontrollkästchen in Azure AD Connect hinaus. Weitere Informationen finden Sie unter [Vorgehensweise: Konfigurieren des Kenn Wort](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback)Rückschreibens. 

## <a name="3-configure-hybrid-azure-ad-join"></a>3. Konfigurieren des Joins für Hybrid Azure AD

Bevor Sie Windows 10-Geräte als Hybrid Azure AD verbunden aktivieren, sollten Sie sicherstellen, dass die folgenden Voraussetzungen erfüllt sind:

   - Sie führen die neueste Version von Azure AD Connect aus.

   - Azure AD Connect hat alle Computerobjekte der Geräte synchronisiert, die Sie als Hybrid Azure AD verbunden haben möchten. Wenn die Computerobjekte bestimmten Organisationseinheiten (Organizational Units, OU) angehören, stellen Sie sicher, dass diese OUs in Azure AD Connect ebenfalls für die Synchronisierung festgelegt sind.

Führen Sie die Schritte im [Lernprogramm: Configure Hybrid Azure Active Directory Join for Managed Domains](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join)aus, um die vorhandenen Domänen verbundenen Windows 10-Geräte als Hybrid Azure AD registriert zu registrieren. Auf diese Weise können Sie Ihre vorhandenen lokalen Active Directory, die Windows 10-Computern beigetreten sind, Hybrid aktivieren und Cloud bereit machen.
    
## <a name="4-enable-automatic-enrollment-for-windows-10"></a>4. Aktivieren der automatischen Registrierung für Windows 10

 Informationen zum automatischen Registrieren von Windows 10-Geräten für die Verwaltung mobiler Geräte in InTune finden Sie unter [Registrieren eines Windows 10-Geräts automatisch mithilfe von Gruppenrichtlinien](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy). Sie können die Gruppenrichtlinie auf lokaler Computerebene festlegen oder für Massenvorgänge diese Gruppenrichtlinieneinstellung auf dem Domänen Controller mithilfe der Gruppenrichtlinien-Verwaltungskonsole und der ADMX-Vorlagen erstellen.

## <a name="5-configure-seamless-single-sign-on"></a>5. Konfigurieren des nahtlosen einmaligen Anmeldens

  Seamless SSO signiert Benutzer automatisch bei der Verwendung von Unternehmenscomputern in Ihren Microsoft 365-Cloud-Ressourcen. Stellen Sie einfach eine der beiden in Azure beschriebenen Gruppenrichtlinienoptionen bereit [Active Directory nahtloses einmaliges Anmelden: Schnellstart](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sso-quick-start#step-2-enable-the-feature). Die **Gruppenrichtlinien** Option lässt nicht zu, dass Benutzer Ihre Einstellungen ändern, während die Option **Gruppenrichtlinieneinstellung** die Werte festlegt, Sie aber auch Benutzer konfigurierbar lässt.

## <a name="6-set-up-windows-hello-for-business"></a>6. Einrichten von Windows Hello for Business

 Windows Hello for Business ersetzt Kennwörter mit starker zweistufiger Authentifizierung (2FA) für die Anmeldung bei einem lokalen Computer. Ein Faktor ist ein asymmetrisches Schlüsselpaar, das andere eine PIN oder andere lokale Geste wie Fingerabdruck oder Gesichtserkennung, wenn Ihr Gerät Sie unterstützt. Wir empfehlen, dass Sie, wenn möglich, Kennwörter durch 2FA und Windows Hello for Business ersetzen.

Überprüfen Sie zum Konfigurieren von Hybrid-Windows Hello for Business die [Voraussetzungen für den Hybrid Schlüssel Trust Windows Hello for Business](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-key-trust-prereqs). Befolgen Sie dann die Anweisungen unter [configure Hybrid Windows Hello for Business Key Trust Settings](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-key-whfb-settings). 
