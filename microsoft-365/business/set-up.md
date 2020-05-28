---
title: Microsoft 365 Business Premium einrichten
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
ms.openlocfilehash: 6606e9fd66aacab317e4b0bfd5ce2a090208018e
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44402942"
---
# <a name="set-up-microsoft-365-business-premium-in-the-setup-wizard"></a>Einrichten von Microsoft 365 Business Premium im Setup-Assistenten

In diesem Video sehen Sie eine Übersicht über das Microsoft 365 Business Premium-Setup.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FYSM] 

Wenn Sie dieses Video hilfreich fanden, sehen Sie sich bitte die [komplette Schulungsserie für kleine Unternehmen und jene, die neu bei Microsoft 365 sind](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816), an.

## <a name="add-your-domain-users-and-set-up-policies"></a>Hinzufügen von Richtlinien für Domäne, Benutzer und einrichten

[![Hinweis, der Sie darüber informiert, dass sich das Admin Center ändert und Sie unter "aka.ms/aboutM365preview" weitere Details finden.](../media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)

Wenn Sie Microsoft 365 Business Premium erwerben, haben Sie die Möglichkeit, eine Domäne zu verwenden, die Sie besitzen oder die Sie während der [Anmeldung](sign-up.md)kaufen.

- Wenn Sie bei der Registrierung eine neue Domäne erworben haben, ist Ihre Domäne eingerichtet, und Sie können zum [Hinzufügen von Benutzern und Zuweisen von Lizenzen](#add-users-and-assign-licenses)umsteigen.

### <a name="add-your-domain-to-personalize-sign-in"></a>Hinzufügen Ihrer Domäne zur Personalisierung der Anmeldung

1. Melden Sie sich mit ihren globalen Administratoranmeldeinformationen beim [Microsoft 365 Admin Center](https://admin.microsoft.com) an. 

2. Wählen Sie **Gehe zu Setup** aus, um den Assistenten zu starten.

    ![Wählen Sie Gehe zu Setup aus.](../media/gotosetupinadmincenter.png)

3. Auf der Seite **Office-Apps installieren** können Sie optional die apps auf Ihrem eigenen Computer installieren.
    
4. Geben Sie im Schritt **Domäne hinzufügen** den Domänennamen ein, den Sie verwenden möchten (wie contoso.com).

    > [!IMPORTANT]
    > Wenn Sie während der Registrierung eine Domäne erworben haben, wird hier kein Domänen Schritt **Hinzufügen** angezeigt. Wechseln Sie stattdessen zu [Benutzer hinzufügen](#add-users-and-assign-licenses) .

    ![Screenshot der Personalisierung Ihrer Anmeldeseite.](../media/adddomain.png)

    
4. Befolgen Sie die Schritte im Assistenten zum [Erstellen von DNS-Einträgen bei einem beliebigen DNS-Hostinganbieter für Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) , die ihre eigene Domäne verifizieren. Wenn Sie Ihren Domänenhost kennen, lesen Sie auch die [hostspezifischen Anweisungen](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).

    Wenn Ihr Hosting-Anbieter GoDaddy oder ein anderer Host ist, der mit der [Domäne Connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect)aktiviert ist, ist der Prozess einfach, und Sie werden automatisch aufgefordert, sich anzumelden und Microsoft in Ihrem Namen authentifizieren zu lassen.

    ![Wählen Sie auf der Seite GoDaddy-Zugriff bestätigen die Option autorisieren aus.](../media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a>Hinzufügen von Benutzern und Zuweisen von Lizenzen

Sie können Benutzer im Assistenten hinzufügen, Sie können aber auch später im Admin Center [Hinzufügen](add-users-m365b.md) . Wenn Sie über einen lokalen Domänencontroller verfügen, können Sie außerdem Benutzer mit [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express)hinzufügen.

#### <a name="add-users-in-the-wizard"></a>Hinzufügen von Benutzern im Assistenten

Alle Benutzer, die Sie dem Assistenten hinzufügen, erhalten automatisch eine Microsoft 365 Business Premium-Lizenz zugewiesen.

![Screenshot der Seite "neue Benutzer hinzufügen" im Assistenten](../media/addnewuserspage.png)

1. Wenn Ihr Microsoft 365 Business Premium-Abonnement über vorhandene Benutzer verfügt (beispielsweise wenn Sie Azure AD Connect verwendet haben), erhalten Sie eine Option, um Ihnen jetzt Lizenzen zuzuweisen. Fügen Sie die Lizenzen ebenfalls hinzu.

2. Nachdem Sie die Benutzer hinzugefügt haben, erhalten Sie auch eine Option zum Freigeben von Anmeldeinformationen für die neuen Benutzer, die Sie hinzugefügt haben. Sie können auswählen, ob Sie Sie ausdrucken, per e-Mail versenden oder herunterladen möchten.

### <a name="connect-your-domain"></a>Verbinden Ihrer Domäne

> [!NOTE]
> Wenn Sie sich für die Verwendung der. onmicrosoft-Domäne entschieden oder Azure AD Connect zum Einrichten von Benutzern verwendet haben, wird dieser Schritt nicht angezeigt.
  
Zum Einrichten von Diensten müssen Sie einige Datensätze bei Ihrem DNS-Host oder Ihrer Domänenregistrierungsstelle aktualisieren.
  
1. Der Setup-Assistent erkennt normalerweise Ihre Registrierungsstelle und stellt einen Link zu Schritt-für-Schritt-Anweisungen zum Aktualisieren der NS-Einträge auf der Registrierungsstellen Website bereit. Wenn dies nicht der Fall ist, ändern Sie Namen [Server, um Office 365 bei einer beliebigen Domänenregistrierungsstelle einzurichten](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/change-nameservers-at-any-domain-registrar). 

    - Wenn Sie über vorhandene DNS-Einträge verfügen, beispielsweise eine vorhandene Website, Ihr DNS-Host jedoch für die [Domäne Connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect)aktiviert ist, wählen Sie **für mich Datensätze hinzufügen**aus. Übernehmen Sie auf der Seite **Wählen Sie Ihre Onlinedienste aus** alle Standardeinstellungen, und wählen Sie **weiter**aus, und klicken Sie auf der Seite Ihres DNS-Hosts auf **autorisieren** .
    - Wenn Sie über vorhandene DNS-Einträge mit anderen DNS-Hosts verfügen (nicht für Domäne Connect aktiviert), sollten Sie Ihre eigenen DNS-Einträge verwalten, um sicherzustellen, dass die vorhandenen Dienste verbunden bleiben. Weitere Informationen finden Sie unter [Domain Basics](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) .

        ![Seite Datensätze aktivieren.](../media/activaterecords.png)

2. Führen Sie die Schritte im Assistenten aus, und e-Mail und andere Dienste werden für Sie eingerichtet.

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

Sie können Office auch einzeln installieren. Anweisungen finden Sie unter [Installieren von Office auf einem PC oder Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658) .

## <a name="see-also"></a>Siehe auch

[Microsoft 365 für Unternehmen-Schulungsvideos](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
