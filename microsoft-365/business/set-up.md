---
title: Einrichten von Microsoft 365 Business
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
f1_keywords:
- O365E_M365SetupBanner
- BCS365_M365SetupBanner
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Erfahren Sie, wie Sie Microsoft 365 Business einrichten.
ms.openlocfilehash: e635b828609fc47cd8b92bb179a25bcc43cb0a1a
ms.sourcegitcommit: db1dfb2df2c2f7beced3b57bc772d106c189e88a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2019
ms.locfileid: "33660787"
---
# <a name="set-up-microsoft-365-business"></a>Einrichten von Microsoft 365 Business

Weitere Informationen finden Sie unter [Get Microsoft 365 Business](get-microsoft-365-business.md) for Sign-up Details.

Sehen Sie sich ein [kurzes Video über das Einrichten von Microsoft 365 Business](https://support.office.com/article/38003e30-9d10-44cf-b596-f1b5f662bfa1) mithilfe des Assistenten zum Einrichten und wenn Sie nicht über ein lokales Active Directory verfügen.
  

## <a name="overview"></a>Übersicht

Die meisten der einrichten-Schritte können im Setup-Assistenten ausgeführt werden, die anderen Optionen werden ebenfalls aufgeführt.

1. [Hinzufügen Ihrer Domäne](#add-your-domain-to-personalize-sign-in) (wenn Sie Ihre Domäne während der [Registrierung](sign-up.md)erworben haben, ist dieser Schritt bereits erfolgt.)
2. Fügen Sie Benutzer hinzu. Sie haben die folgenden Möglichkeiten:
    - Im [Setup-Assistenten](#add-users-in-the-wizard).
    - Verwenden Sie die Verzeichnissynchronisierung, um [Benutzer mithilfe von Azure AD Connect hinzuzufügen](#add-users-by-using-azure-ad-connect) , wenn Sie über ein lokales Active Directory verfügen.
    - Sie können auch später im Admin Center [Benutzer hinzufügen](add-users-m365b.md) .
3. Einrichten von Sicherheitsrichtlinien und Konfigurieren von Geräten Sie haben die folgenden Möglichkeiten:
    - Im [Setup-Assistenten](#set-up-policies-in-the-wizard).  
    - Im [Admin Center](#modify-or-add-policies-in-the-admin-center).
    - Im [InTune Admin Center](https://docs.microsoft.com/intune/what-is-device-management).
4. Einrichten und Verwalten von Windows 10-Geräten.

    Wenn Sie einem Windows 10-Gerät zu Azure AD beitreten, werden alle Richtlinien angewendet.
    - Richten Sie Windows 10-Gerätekonfigurationen im [Setup-Assistenten](#set-up-policies-in-the-wizard)ein.
    - Verbinden Sie ein [neues Windows 10-Gerät](set-up-windows-devices.md#for-a-brand-new-or-newly-upgraded-windows-10-pro-device) mit Azure AD.
    - Verbinden Sie ein [vorhandenes Windows 10-Gerät](set-up-windows-devices.md#for-a-device-already-set-up-and-running-windows-10-pro) mit Azure AD.
1. Installieren Sie Office 365 Business.
    - Sie können Office auf den Windows-Geräten mithilfe des Setup- [Assistenten](#set-up-policies-in-the-wizard)automatisch installieren.
    - [Installieren Sie Office](auto-install-or-uninstall-office.md) automatisch über das Admin Center.
    - Benutzer können [Office-Apps](https://docs.microsoft.com/office365/admin/setup/install-applications) für Windows und Geräte installieren.
     
1. Richten Sie zusätzliche Sicherheit ein.
    - Der Setup-Assistent fügt Richtlinien hinzu, um Ihre Geräte zu schützen, aber Sie können auch [zusätzliche Sicherheits](#additional-security-settings) Funktionen nutzen, um Ihre Daten, Konten und e-Mails zu schützen. 

## <a name="add-your-domain-users-and-set-up-policies"></a>Hinzufügen Ihrer Domäne, der Benutzer und Einrichten von Richtlinien

![Banner, das auf https://aka.ms/aboutM365preview.](media/m365admincenterchanging.png)

Wenn Sie Microsoft 365 Business erwerben, haben Sie die Möglichkeit, eine Domäne zu verwenden, die Sie besitzen, oder einen während der [Registrierung](sign-up.md)zu kaufen.

- Wenn Sie bei der Registrierung eine neue Domäne erworben haben, ist Ihre Domäne vollständig eingerichtet, und Sie können zum [Hinzufügen von Benutzern und zum Zuweisen von Lizenzen](#add-users-and-assign-licenses)wechseln.

### <a name="add-your-domain-to-personalize-sign-in"></a>Hinzufügen Ihrer Domäne zur Personalisierung der Anmeldung

1. Melden Sie sich mit ihren globalen Administratoranmeldeinformationen beim [Microsoft 365 Admin Center](https://admin.microsoft.com) an. 

2. Wählen Sie **Domäne hinzufügen** aus, um den Assistenten zu starten.

    ![Wählen Sie Domäne hinzufügen aus.](media/addadomainadmincenter.png)
    
3. Geben Sie im Assistenten den Domänennamen ein, den Sie verwenden möchten (wie contoso.com).


    ![Screenshot der personalisieren Sie Ihre Anmeldeseite.](media/personalizesignin.png)

    
4. Führen Sie die Schritte im Assistenten aus, um [DNS-Einträge bei einem beliebigen DNS-Hostinganbieter für Office 365 zu erstellen](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) , der überprüft, ob Sie die Domäne besitzen. Wenn Sie Ihren Domänenhost kennen, lesen Sie auch die [hostspezifischen Anweisungen](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).

    Wenn Ihr Hostinganbieter GoDaddy ist, ist der Vorgang einfach und Sie werden automatisch aufgefordert, sich anzumelden und Microsoft in Ihrem Namen zu authentifizieren:

    ![Wählen Sie auf GoDaddy Zugriffsseite bestätigen aus.](media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a>Hinzufügen von Benutzern und Zuweisen von Lizenzen

Sie können Benutzer im Assistenten hinzufügen, Sie können aber auch später im Admin Center [Benutzer hinzufügen](add-users-m365b.md) . Darüber hinaus können Sie Benutzer mit [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express)hinzufügen, wenn Sie über einen lokalen Domänencontroller verfügen.

#### <a name="add-users-in-the-wizard"></a>Hinzufügen von Benutzern im Assistenten

Alle Benutzer, die Sie im Assistenten hinzufügen, erhalten automatisch eine Microsoft 365 Business-Lizenz.
Wenn Sie über einen lokalen Domänencontroller verfügen und Active Directory verwenden, erfahren Sie, [wie Sie DDD-Benutzer mithilfe von Azure AD Connect verwenden](#add-users-by-using-azure-ad-connect).

![Screenshot der Seite "neue Benutzer hinzufügen" im Assistenten](media/addnewuserspage.png)

1. Wenn Ihr Microsoft 365 Business-Abonnement über vorhandene Benutzer verfügt (beispielsweise, wenn Sie Azure AD Connect verwendet haben), erhalten Sie jetzt die Option, Ihnen Lizenzen zuzuweisen. Gehen Sie vor, und fügen Sie Lizenzen hinzu.

3. Nachdem Sie die Benutzer hinzugefügt haben, erhalten Sie auch die Möglichkeit, die Anmeldeinformationen für die neuen Benutzer freizugeben, die Sie hinzugefügt haben. Sie können auswählen, ob Sie Sie ausdrucken, per e-Mail versenden oder herunterladen möchten.

4. Überspringen Sie die Migration von e-Mail-Nachrichten, und wählen Sie **weiter** auf Seite **e-Mails migrieren** . 

    Wenn Sie von einem anderen e-Mail-Anbieter wechseln und Ihre Daten später kopieren möchten, können Sie [e-Mails und Kontakte zu Office 365 migrieren](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e).

#### <a name="add-users-by-using-azure-ad-connect"></a>Hinzufügen von Benutzern mithilfe von Azure AD Connect

 Wenn Sie über einen lokalen Domänencontroller mit Active Directory verfügen, synchronisieren Sie Ihre Benutzer mit Microsoft 365 Business mithilfe von [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express). Führen Sie diese Schritte aus, bevor Sie den Setup-Assistenten starten. Sie können es im Admin Center herunterladen:

- Wechseln Sie zu **Users** \> **Active Users**, wählen Sie die Ellipsen oben auf der Seite aus, und wählen Sie dann **Verzeichnissynchronisierung** zum Herunterladen von Azure AD Connect aus.

    ![Wählen Sie auf der Seite aktive Benutzer Auslassungszeichen > Verzeichnis snchronization.](media/setupdirsync.png)

    > [!IMPORTANT]
    > Wenn Sie Benutzer auf diese Weise erstellen, müssen Sie Ihnen im Admin Center weiterhin Lizenzen zuweisen.

##### <a name="continue-to-access-domain-joined-apps-and-devices"></a>Weiterhin Zugriff auf Domänen verbundene apps und Geräte

Wenn Sie weiterhin auf Domänen-Joined-apps und-Geräte zugreifen möchten, lesen Sie die folgenden Artikel, um Folgendes zu ermöglichen:
  
- [Aktivieren von Domänenbeitritt zu Windows 10-Geräten, die von Microsoft 365 Business verwaltet werden](manage-windows-devices.md)
    - Dies ist die empfohlene Methode.

- [Zugreifen auf lokale Ressourcen über ein Azure AD-verbundenes Gerät in Microsoft 365 Business](access-resources.md)

### <a name="connect-your-domain"></a>Verbinden Ihrer Domäne

> [!NOTE]
> Wenn Sie die. onmicrosoft-Domäne verwenden oder Azure AD Connect zum Einrichten von Benutzern verwendet haben, wird dieser Schritt nicht angezeigt.
  
Um Dienste einzurichten, müssen Sie einige Datensätze bei Ihrem DNS-Host oder Ihrer Domänenregistrierungsstelle aktualisieren.
  
1. Der Setup-Assistent erkennt in der Regel Ihre Registrierungsstelle und gibt Ihnen einen Link zu Schritt-für-Schritt-Anweisungen zum Aktualisieren Ihrer NS-Einträge auf der Registrierungsstelle. Wenn dies nicht der Fall ist, [Ändern Sie die Namenserver, um Office 365 für eine beliebige Domänenregistrierungsstelle](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2)einzurichten. 

    - Wenn Sie über vorhandene DNS-Einträge verfügen (beispielsweise eine vorhandene Website), sollten Sie Ihre eigenen DNS-Einträge verwalten, um sicherzustellen, dass die vorhandenen Dienste verbunden bleiben. Weitere Informationen finden Sie unter [Grundlagen der Domäne](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) .

        ![Verbinden Sie Ihre Domänen Seite mit ich werde meine eigenen DNS-Einträge verwalten.](media/connectyourdomainpage.png)

2. Führen Sie die Schritte im Assistenten aus, und e-Mails und andere Dienste werden für Sie eingerichtet.

### <a name="set-up-security-policies-and-device-configurations"></a>Einrichten von Sicherheitsrichtlinien und Gerätekonfigurationen 

Diese Richtlinien gelten für jeden Benutzer, dem Sie eine Lizenz erteilen, oder für eine Gruppe von Benutzern, wenn Sie eine Reihe von Benutzern unterschiedliche Richtlinien zuweisen möchten.

#### <a name="set-up-policies-in-the-wizard"></a>Einrichten von Richtlinien im Assistenten

Die Richtlinien, die Sie im Assistenten einrichten, werden automatisch auf eine [Sicherheitsgruppe](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) namens " *alle Benutzer*" angewendet.

1. Aktivieren Sie auf der Seite **schützen Sie Ihre Arbeitsdateien auf mobilen Geräten** standardmäßig die Option **Arbeitsdateien bei verlorenen oder gestohlenen Geräten schützen** . Sie haben die Möglichkeit, zu **Steuern, wie Benutzer auf Office-Dateien auf mobilen Geräten zugreifen**, und dies wird empfohlen.

    ![Screenshot der Seite zum Schutz von Arbeitsdateien auf mobilen Geräten.](media/protectworkfilesondevices.png)

     - Wenn Sie **Arbeitsdateien schützen erweitern, wenn Geräte verloren gehen oder gestohlen**werden, sind die [Standardwerte](protect-work-files-on-lost-or-stolen-device.md) vorab ausgewählt:

        ![Screenshot der Standardwerte für den Schutz von Dateien auf verlorenen Geräten.](media/protectworkfilesondevicesdefault.png)

    - Wenn Sie verwalten auswählen, **wie Benutzer auf mobilen Geräten auf Office-Dateien zugreifen** und diese erweitern, werden die [Standardwerte](manage-user-access-on-mobile-devices.md) angezeigt. Wir empfehlen, während des Setups die Standardwerte zu übernehmen, um Anwendungsrichtlinien für Android, iOS und Windows 10 zu erstellen, die für alle Benutzer gelten. Nach Abschluss des Setups können Sie weitere Richtlinien erstellen.

        ![Screenshot der Schutzeinstellungen für Office-Dateien auf mobilen Geräten.](media/useraccessonmobile.png)

2. Im letzten Schritt zum Schutz von Daten und Geräten können Sie Richtlinien einrichten, um Windows 10-Geräte zu sichern. Diese Einstellungen werden automatisch angewendet, wenn Windows 10 eines Benutzers eine Verbindung mit Ihrer Organisation herstellt. Sie können **Secure Windows 10-Geräte** erweitern, um die [Standardwerte](secure-windows-10-devices.md)anzuzeigen und zu ändern.
3. Sie können Office auf Windows 10-Geräten auch [automatisch installieren](install-office-on-windows-10-during-setup.md) .

    ![Screenshot der Seite Set Windows 10 Device Configuration.](media/setwin10config.png)

#### <a name="modify-or-add-policies-in-the-admin-center"></a>Ändern oder Hinzufügen von Richtlinien im Admin Center

Weitere Informationen finden Sie unter [Verwalten von Microsoft 365 Business](manage.md) für Links zu Themen zum Anzeigen und Ändern von Geräte-und App-Schutzrichtlinien sowie zum Entfernen von Daten aus oder Zurücksetzen von Benutzergeräten.

## <a name="deploy-and-manage-windows-10"></a>Bereitstellen und Verwalten von Windows 10
Weitere Informationen finden Sie unter [Einrichten von Windows-Geräten für Microsoft 365 Business-Benutzer](set-up-windows-devices.md) zur manuellen Verbindung mit Azure AD, entweder beim Setup für neue Computer oder durch Ändern des Anmelde Profils für vorhandene Computer. 

### <a name="use-autopilot-to-set-up-new-devices"></a>Verwenden von Autopilot zum Einrichten neuer Geräte

Sie können [Windows Autopilot](add-autopilot-devices-and-profile.md) verwenden, um **neue** Windows 10-Geräte für einen Benutzer automatisch vorkonfigurieren, aber es ist möglicherweise einfacher, einen [Partner](https://www.microsoft.com/solution-providers/search) zu erhalten, der dies für Sie tun kann. Sie können auch zu [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598) wechseln und einen Experten für die Cloud-Technologie bitten, neue Geräte einzurichten, die Sie für Sie erwerben.

### <a name="access-on-premises-resources"></a>Zugriff auf lokale Ressourcen

Wenn Ihre Organisation Windows Server Active Directory lokal verwendet, können Sie Microsoft 365 Business einrichten, um Ihre Windows 10-Geräte zu schützen, ohne dabei den Zugriff auf lokale Ressourcen zu gewährleisten, die lokal authentifiziert werden müssen. Führen Sie die Schritte unter [enable Domain-Joined Windows 10 Devices aus, die von Microsoft 365 Business verwaltet werden](manage-windows-devices.md) , um diese einzurichten. Dies ist die bevorzugte Methode, und die Geräte in diesem Zustand werden als hybride Azure AD-verbundene Geräte bezeichnet.

Wenn Ihr Unternehmen über ein lokales Active Directory verfügt, das einige lokale Ressourcen (wie Dateifreigaben und Drucker) enthält, können Sie Ihren Azure AD-verbundenen Geräten Zugriff auf diese Ressourcen gewähren, indem Sie die folgenden Schritte ausführen: [Zugriff auf lokale Ressourcen über eine Azure AD-verbundenes Gerät in Microsoft 365 Business](access-resources.md).

## <a name="deploy-office-365-client-apps"></a>Bereitstellen von Office 365-Client-apps

Wenn Sie während des Einrichtens die automatische Installation von Office-Apps ausgewählt haben, werden die apps auf den Windows 10-Geräten installiert, sobald sich die Benutzer bei Azure AD von Ihren Windows-Geräten mit Ihren Anmeldeinformationen angemeldet haben.
Informationen zum Installieren von Office auf mobilen IOS-oder Android-Geräten finden Sie unter [Einrichten von mobilen Geräten für Microsoft 365 Business-Benutzer](set-up-mobile-devices.md).

Sie können Office auch einzeln installieren. Anweisungen hierzu finden Sie unter [Installieren von Office auf einem PC oder Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc471665) .

## <a name="additional-security-settings"></a>Zusätzliche Sicherheitseinstellungen

Zusätzlich zur Sicherheits-und Konformitäts Einstellung im Setup-Assistenten können Sie auch die folgenden zusätzlichen Einstellungen einrichten:
  
- **Schutz von e-Mail-Schadsoftware**
- **Advanced Threat Protection (ATP) sichere Anlagen**
- **ATP-sichere Links**
- **APT-Phishing**
- **Exchange Online-Archivierung**
- **Verhinderung von Datenverlusten (Data Loss Prevention, DLP)**
- **Azure Information Protection** (Plan 1)
- **InTune-Portal Verfügbarkeit**

Weitere Informationen finden Sie unter [Einrichten von erweiterten Sicherheitsrichtlinien](set-up-advanced-security.md).

Weitere Informationen finden Sie unter [Top 10 Ways to Secure your Microsoft 365 Business](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) for a Roadmap of Best Security Practices.