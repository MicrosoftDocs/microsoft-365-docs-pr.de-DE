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
description: Entdecken Sie die Setupschritte für Microsoft 365 Business Premium, einschließlich hinzufügen einer Domäne und Benutzer, Einrichten von Sicherheitsrichtlinien und mehr.
ms.openlocfilehash: 4d49ba7ccdb65691756aaa505d0856deb115595b
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51052232"
---
# <a name="set-up-microsoft-365-business-premium-in-the-setup-wizard"></a>Einrichten von Microsoft 365 Business Premium im Setup-Assistenten

Sehen Sie sich dieses Video an, um eine Übersicht über das Microsoft 365 Business Premium-Setup zu erhalten.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4jZwg] 

## <a name="add-your-domain-users-and-set-up-policies"></a>Hinzufügen Ihrer Domäne, Benutzer und Einrichten von Richtlinien

Wenn Sie Microsoft 365 Business Premium erwerben, haben Sie die Möglichkeit, eine Domäne zu verwenden, die Sie besitzen, oder eine Domäne während der [Anmeldung zu kaufen.](sign-up.md)

- Wenn Sie bei der Registrierung eine neue Domäne erworben haben, ist Ihre Domäne eingerichtet, und Sie können zu [Benutzer hinzufügen und Lizenzen zuweisen](#add-users-and-assign-licenses) wechseln.

### <a name="add-your-domain-to-personalize-sign-in"></a>Hinzufügen Ihrer Domäne zum Personalisieren der Anmeldung

1. Melden Sie sich mit den Anmeldeinformationen des globalen Administrators bei [Microsoft 365 Admin Center](https://admin.microsoft.com) an. 

2. Wählen Sie **Zu Setup wechseln** aus, um den Assistenten zu starten.

    ![Wählen Sie Zum Setup wechseln aus.](../media/gotosetupinadmincenter.png)

3. Auf der Seite **Office-Anwendungen installieren** können Sie die Apps optional auf Ihrem eigenen Computer installieren.
    
4. Geben Sie im Schritt **Domäne hinzufügen** den gewünschten Domänennamen ein (z. B. contoso.com).

    > [!IMPORTANT]
    > Wenn Sie während der Registrierung eine Domäne erworben haben, wird der Schritt **eine Domäne hinzufügen** nicht angezeigt. Wechseln Sie stattdessen zu [Benutzer hinzufügen](#add-users-and-assign-licenses).

    ![Screenshot der Seite "Anmelden personalisieren".](../media/adddomain.png)

    
4. Führen Sie die Schritte im Assistenten zum Erstellen von DNS-Einträgen bei einem beliebigen DNS-Hostinganbieter für [Microsoft 365](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) aus, der Ihre Domäne überprüft. Wenn Sie Ihren Domänenhost kennen, lesen Sie auch die [hostspezifischen Anweisungen](/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).

    Wenn es sich bei Ihrem Hostinganbieter um GoDaddy oder einen anderen Host handelt, der mit [Domain Connect](/office365/admin/get-help-with-domains/domain-connect) arbeitet, ist der Vorgang einfach, und Sie werden aufgefordert, sich anzumelden, um Microsoft in Ihrem Auftrag authentifizieren zu lassen.

    ![Wählen Sie auf der GoDaddy-Seite „Zugriff bestätigen“ den Befehl Autorisieren aus.](../media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a>Benutzer hinzufügen und Lizenzen zuweisen

Sie können Benutzer entweder hier hinzufügen oder Sie können [Benutzer später im Admin Center hinzufügen](../admin/add-users/add-users.md). Wenn Sie einen lokalen Domänencontroller besitzen, können Sie Benutzer zudem mit [Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-express) hinzufügen.

#### <a name="add-users-in-the-wizard"></a>Hinzufügen von Benutzern im Assistenten

Allen Benutzern, die Sie im Assistenten hinzufügen, wird automatisch eine Microsoft 365 Business Premium-Lizenz zugewiesen.

![Screenshot der Seite Neue Benutzer hinzufügen im Assistenten](../media/addnewuserspage.png)

1. Wenn Ihr Microsoft 365 Business Premium-Abonnement über vorhandene Benutzer verfügt (z. B. wenn Sie Azure AD Connect verwendet haben), erhalten Sie eine Option, um ihnen jetzt Lizenzen zu zuweisen. Setzen Sie den Vorgang fort, und fügen Sie ihnen Lizenzen hinzu.

2. Nachdem Sie die Benutzer hinzugefügrt haben, erhalten Sie außerdem die Möglichkeit, Anmeldeinformationen für die hinzugefügten neuen Benutzer freizugeben. Sie können auswählen, ob diese Informationen ausgedruckt, per E-Mail gesendet oder heruntergeladen werden sollen.

### <a name="connect-your-domain"></a>Ihre Domäne verbinden

> [!NOTE]
> Wenn Sie sich für die Verwendung der .onmicrosoft-Domäne oder die Verwendung von Azure AD Connect zum Einrichten von Benutzern entschieden haben, wird dieser Schritt nicht angezeigt.
  
Zum Einrichten von Diensten müssen Sie einige Einträge bei Ihrem DNS-Host oder Ihrer Domänenregistrierungsstelle aktualisieren.
  
1. In der Regel erkennt der Setup-Assistent Ihre Registrierungsstelle und zeigt einen Link an, über den Sie schrittweise Anleitungen zum Aktualisieren Ihrer NS-Einträge auf der Website der Registrierungsstelle aufrufen können. Wenn dies nicht der Fall ist, ändern Sie [Namenserver, um Microsoft 365 mit einer beliebigen Domänenregistrierungsstelle zu einrichten.](../admin/get-help-with-domains/change-nameservers-at-any-domain-registrar.md) 

    - Wenn Sie über vorhandene DNS-Einträge verfügen, z. B. eine vorhandene Website, aber Ihr DNS-Host für [Domain Connect](/office365/admin/get-help-with-domains/domain-connect) aktiviert ist, wählen Sie **Einträge für mich hinzufügen** aus. Übernehmen Sie auf der Seite **Wählen Sie Ihre Onlinedienste** die Standardeinstellungen, wählen Sie **Weiter** aus, und wählen Sie auf der Seite Ihres DNS-Hosts **autorisieren** aus.
    - Wenn Sie über vorhandene DNS-Einträge für andere DNS-Hosts (die nicht mit Domain Connect arbeiten) verfügen, können Sie Ihre eigenen DNS-Einträge verwalten, um sicherzustellen, dass die vorhandenen Dienste verbunden bleiben. Weitere Informationen finden Sie unter [Domain-Grundlagen](/office365/admin/get-help-with-domains/dns-basics).

        ![Aktiviere die Datensatzseite.](../media/activaterecords.png)

2. Befolgen Sie die Schritte im Assistenten, damit E-Mail und andere Dienste für Sie eingerichtet werden.

### <a name="protect-your-organization"></a>Schützen Ihrer Organisation 

Die richtlinien, die Sie im Assistenten eingerichtet haben, werden automatisch auf eine [Sicherheitsgruppe](/office365/admin/create-groups/compare-groups#security-groups) mit dem Namen *Alle Benutzer angewendet.* Sie können auch zusätzliche Gruppen erstellen, um Richtlinien im Admin Center zuzuordnen.

1. Unter **Erhöhen des Schutzes** vor erweiterten Cyberbedrohungen wird empfohlen, dass Sie die Standardeinstellungen akzeptieren, um [Office 365 Advance Threat Protection](../security/defender-365-security/defender-for-office-365.md) Dateien und Links in Office-Apps überprüfen zu lassen.

    ![Screenshot der Seite Schutz erhöhen.](../media/increasetreatprotection.png)


2. Akzeptieren  Sie auf der Seite Datenlecks von vertraulichen Daten verhindern die Standardeinstellungen zum Aktivieren von Office 365 Data Loss Prevention (DLP), um vertrauliche Daten in Office-Apps nachverfolgt und die versehentliche Freigabe dieser Daten außerhalb Ihrer Organisation zu verhindern.

3. Lassen Sie auf der Seite Daten **in Office für Mobile** schützen die Verwaltung mobiler Apps auf, erweitern Sie die Einstellungen, und überprüfen Sie sie, und wählen Sie dann Verwaltungsrichtlinie für mobile Apps erstellen **aus.**

    ![Screenshot der Seite Daten in Office für Mobile schützen.](../media/protectdatainmobile.png)


## <a name="secure-windows-10-pcs"></a>Sichern von Windows 10-PCs

Wählen Sie im linken Navigationsfenster **Setup** aus, und wählen Sie dann unter **Anmeldung** und Sicherheit die Option **Windows 10-Computer sichern aus.** Wählen **Sie Ansicht** aus, um zu beginnen. Vollständige Anweisungen finden Sie unter [Secure your Windows 10 computers.](secure-win-10-pcs.md)

## <a name="deploy-office-365-client-apps"></a>Bereitstellen von Office 365-Client-Apps

Wenn Sie sich für die automatische Installation von Office-Apps während des Setups entschieden haben, werden die Apps auf den Windows 10-Geräten installiert, sobald sich die Benutzer über ihre Windows-Geräte mit ihren Geschäftsanmeldeinformationen bei Azure AD angemeldet haben.

Informationen zur Installation von Office auf mobilen iOS- oder Android-Geräten finden Sie unter Einrichten mobiler Geräte [für Microsoft 365 Business Premium-Benutzer.](set-up-mobile-devices.md)

Sie können Office auch einzeln installieren. Anweisungen finden Sie unter Installieren von Office auf [einem PC oder Mac.](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658)

## <a name="see-also"></a>Siehe auch

[Microsoft 365 für Unternehmen-Schulungsvideos](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
