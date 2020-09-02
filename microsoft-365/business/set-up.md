---
title: Einrichten von Microsoft 365 Business Premium
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
f1_keywords:
- O365E_M365SetupBanner
- BCS365_M365SetupBanner
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- TRN_SMB
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
- OKR_SMB_M365
- TRN_M365B
- OKR_SMB_Videos
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Ermitteln Sie die Installationsschritte für Microsoft 365 Business Premium, einschließlich Hinzufügen einer Domäne und Benutzer, Einrichten von Sicherheitsrichtlinien und vieles mehr.
ms.openlocfilehash: cc20637d7a78bd34ecb61a4ed46eb06d564d63df
ms.sourcegitcommit: 25afc0c34edc7f8a5eb389d8c701175256c58ec8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2020
ms.locfileid: "47324494"
---
# <a name="set-up-microsoft-365-business-premium-in-the-setup-wizard"></a>Einrichten von Microsoft 365 Business Premium im Setup-Assistenten

In diesem Video sehen Sie eine Übersicht über das Microsoft 365 Business Premium-Setup.<br><br>

## <a name="add-your-domain-users-and-set-up-policies"></a>Hinzufügen von Richtlinien für Domäne, Benutzer und einrichten

Wenn Sie Microsoft 365 Business Premium erwerben, haben Sie die Möglichkeit, eine Domäne zu verwenden, die Sie besitzen oder die Sie während der [Anmeldung](sign-up.md)kaufen.

- Wenn Sie bei der Registrierung eine neue Domäne erworben haben, ist Ihre Domäne eingerichtet, und Sie können zu [Benutzer hinzufügen und Lizenzen zuweisen](#add-users-and-assign-licenses) wechseln.

### <a name="add-your-domain-to-personalize-sign-in"></a>Hinzufügen Ihrer Domäne zum Personalisieren der Anmeldung

1. Melden Sie sich mit den Anmeldeinformationen des globalen Administrators bei [Microsoft 365 Admin Center](https://admin.microsoft.com) an. 

2. Wählen Sie **Zu Setup wechseln** aus, um den Assistenten zu starten.

    ![Wählen Sie Gehe zu Setup aus.](../media/gotosetupinadmincenter.png)

3. Auf der Seite **Office-Anwendungen installieren** können Sie die Apps optional auf Ihrem eigenen Computer installieren.
    
4. Geben Sie im Schritt **Domäne hinzufügen** den gewünschten Domänennamen ein (z. B. contoso.com).

    > [!IMPORTANT]
    > Wenn Sie während der Registrierung eine Domäne erworben haben, wird der Schritt **eine Domäne hinzufügen** nicht angezeigt. Wechseln Sie stattdessen zu [Benutzer hinzufügen](#add-users-and-assign-licenses).

    ![Screenshot der Personalisierung Ihrer Anmeldeseite.](../media/adddomain.png)

    
4. Befolgen Sie die Schritte im Assistenten zum [Erstellen von DNS-Einträgen bei einem beliebigen DNS-Hostinganbieter für Microsoft 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) , der überprüft, ob Sie die Domäne besitzen. Wenn Sie Ihren Domänenhost kennen, lesen Sie auch die [hostspezifischen Anweisungen](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).

    Wenn es sich bei Ihrem Hostinganbieter um GoDaddy oder einen anderen Host handelt, der mit [Domain Connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect) arbeitet, ist der Vorgang einfach, und Sie werden aufgefordert, sich anzumelden, um Microsoft in Ihrem Auftrag authentifizieren zu lassen.

    ![Wählen Sie auf der GoDaddy-Seite „Zugriff bestätigen“ den Befehl Autorisieren aus.](../media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a>Benutzer hinzufügen und Lizenzen zuweisen

Sie können Benutzer entweder hier hinzufügen oder Sie können [Benutzer später im Admin Center hinzufügen](add-users-m365b.md). Wenn Sie einen lokalen Domänencontroller besitzen, können Sie Benutzer zudem mit [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express) hinzufügen.

#### <a name="add-users-in-the-wizard"></a>Hinzufügen von Benutzern im Assistenten

Alle Benutzer, die Sie dem Assistenten hinzufügen, erhalten automatisch eine Microsoft 365 Business Premium-Lizenz zugewiesen.

![Screenshot der Seite "neue Benutzer hinzufügen" im Assistenten](../media/addnewuserspage.png)

1. Wenn Ihr Microsoft 365 Business Premium-Abonnement über vorhandene Benutzer verfügt (beispielsweise wenn Sie Azure AD Connect verwendet haben), erhalten Sie eine Option, um Ihnen jetzt Lizenzen zuzuweisen. Setzen Sie den Vorgang fort, und fügen Sie ihnen Lizenzen hinzu.

2. Nachdem Sie die Benutzer hinzugefügrt haben, erhalten Sie außerdem die Möglichkeit, Anmeldeinformationen für die hinzugefügten neuen Benutzer freizugeben. Sie können auswählen, ob diese Informationen ausgedruckt, per E-Mail gesendet oder heruntergeladen werden sollen.

### <a name="connect-your-domain"></a>Ihre Domäne verbinden

> [!NOTE]
> Wenn Sie sich für die Verwendung der .onmicrosoft-Domäne oder die Verwendung von Azure AD Connect zum Einrichten von Benutzern entschieden haben, wird dieser Schritt nicht angezeigt.
  
Zum Einrichten von Diensten müssen Sie einige Einträge bei Ihrem DNS-Host oder Ihrer Domänenregistrierungsstelle aktualisieren.
  
1. In der Regel erkennt der Setup-Assistent Ihre Registrierungsstelle und zeigt einen Link an, über den Sie schrittweise Anleitungen zum Aktualisieren Ihrer NS-Einträge auf der Website der Registrierungsstelle aufrufen können. Wenn dies nicht der Fall ist, ändern Sie Namen [Server, um Microsoft 365 bei einer beliebigen Domänenregistrierungsstelle einzurichten](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/change-nameservers-at-any-domain-registrar). 

    - Wenn Sie über vorhandene DNS-Einträge verfügen, z. B. eine vorhandene Website, aber Ihr DNS-Host für [Domain Connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect) aktiviert ist, wählen Sie **Einträge für mich hinzufügen** aus. Übernehmen Sie auf der Seite **Wählen Sie Ihre Onlinedienste** die Standardeinstellungen, wählen Sie **Weiter** aus, und wählen Sie auf der Seite Ihres DNS-Hosts **autorisieren** aus.
    - Wenn Sie über vorhandene DNS-Einträge für andere DNS-Hosts (die nicht mit Domain Connect arbeiten) verfügen, können Sie Ihre eigenen DNS-Einträge verwalten, um sicherzustellen, dass die vorhandenen Dienste verbunden bleiben. Weitere Informationen finden Sie unter [Domain-Grundlagen](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics).

        ![Seite Datensätze aktivieren.](../media/activaterecords.png)

2. Befolgen Sie die Schritte im Assistenten, damit E-Mail und andere Dienste für Sie eingerichtet werden.

### <a name="protect-your-organization"></a>Schützen Ihrer Organisation 

Die Richtlinien, die Sie im Assistenten eingerichtet haben, werden automatisch auf eine [Sicherheitsgruppe](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) mit dem Namen " *alle Benutzer*" angewendet. Sie können auch weitere Gruppen zum Zuweisen von Richtlinien im Admin Center erstellen.

1. Um den **Schutz vor fortgeschrittenen Cyber-Bedrohungen zu verbessern**, wird empfohlen, dass Sie die Standardeinstellungen akzeptieren, damit [Office 365 Advance Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) Scandateien und Links in Office-Apps.

    ![Screenshot der Seite zur Verstärkung des Schutzes.](../media/increasetreatprotection.png)


2. Übernehmen Sie auf der Seite " **Lecks von vertraulichen Daten verhindern** " die Standardeinstellungen, um die Office 365 Verhinderung von Datenverlust (Data Loss Prevention, DLP) zum Nachverfolgen vertraulicher Daten in Office-Apps zu aktivieren und die unbeabsichtigte Freigabe dieser außerhalb Ihrer Organisation zu verhindern.

3. Lassen Sie Mobile App Verwaltung auf der Seite **Daten in Office für Mobile schützen** auf, erweitern Sie die Einstellungen, und überprüfen Sie Sie, und wählen Sie dann **Mobile App Verwaltungsrichtlinie erstellen**aus.

    ![Screenshot von Daten in Office für Mobile Seite schützen.](../media/protectdatainmobile.png)


## <a name="secure-windows-10-pcs"></a>Sichere Windows 10-PCs

Wählen Sie im linken Navigationsbereich die Option **Setup** aus, und wählen Sie dann unter **Anmeldung und Sicherheit** **die Option Sichern Ihrer Windows 10-Computer**aus. Wählen Sie **Ansicht** für erste Schritte aus. Ausführliche Anweisungen finden Sie unter [Sichern Ihrer Windows 10-Computer](secure-win-10-pcs.md) .

## <a name="deploy-office-365-client-apps"></a>Bereitstellen von Office 365-Client-apps

Wenn Sie während des Setups die automatische Installation von Office-Apps ausgewählt haben, werden die apps auf den Windows 10-Geräten installiert, sobald sich die Benutzer bei Azure AD von Ihren Windows-Geräten unter Verwendung ihrer Arbeits Anmeldeinformationen angemeldet haben.

Informationen zum Installieren von Office auf mobilen IOS-oder Android-Geräten finden Sie unter [Einrichten von mobilen Geräten für Microsoft 365 Business Premium-Benutzer](set-up-mobile-devices.md).

Sie können Office auch einzeln installieren. Anweisungen finden Sie unter [Installieren von Office auf einem PC oder Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) .

## <a name="see-also"></a>Siehe auch

[Microsoft 365 für Unternehmen-Schulungsvideos](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
