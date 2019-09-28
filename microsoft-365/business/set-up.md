---
title: Einrichten von Microsoft 365 Business
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
ms.custom: OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Hier erfahren Sie, wie Sie Microsoft 365 Business einrichten.
ms.openlocfilehash: d33839693001f36fbb56541775015f739300b043
ms.sourcegitcommit: 6003d6da0a85c97357eb3dba3918eb145f381fe1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/27/2019
ms.locfileid: "37288493"
---
# <a name="set-up-microsoft-365-business-in-the-setup-wizard"></a>Einrichten von Microsoft 365 Business im Setup-Assistenten

## <a name="add-your-domain-users-and-set-up-policies"></a>Hinzufügen von Richtlinien für Domäne, Benutzer und einrichten

[![Bezeichnungsfeld, damit Sie wissen, dass sich das Admin Center ändert, und weitere Informationen finden Sie unter aka.ms/aboutM365preview.](media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)

Wenn Sie Microsoft 365 Business erwerben, haben Sie die Möglichkeit, eine Domäne zu verwenden, die Sie besitzen, oder einen Kauf während der [Anmeldung](sign-up.md).

- Wenn Sie bei der Registrierung eine neue Domäne erworben haben, ist Ihre Domäne eingerichtet, und Sie können zum [Hinzufügen von Benutzern und Zuweisen von Lizenzen](#add-users-and-assign-licenses)umsteigen.

### <a name="add-your-domain-to-personalize-sign-in"></a>Hinzufügen Ihrer Domäne zur Personalisierung der Anmeldung

1. Melden Sie sich mit ihren globalen Administratoranmeldeinformationen beim [Microsoft 365 Admin Center](https://admin.microsoft.com) an. 

2. Wählen Sie **Hinzufügen einer Domäne** oder **Hinzufügen von Benutzern** aus, um den Assistenten zu starten.
    > [!IMPORTANT]
    > Wenn Sie während der Registrierung eine Domäne erworben haben, wird hier kein Domänen Schritt **Hinzufügen** angezeigt. Wechseln Sie stattdessen zu [Benutzer hinzufügen](#add-users-and-assign-licenses) .

    ![Wählen Sie Domäne hinzufügen aus.](media/addadomainadmincenter.png)
    
3. Geben Sie im Assistenten den Domänennamen ein, den Sie verwenden möchten (wie contoso.com).


    ![Screenshot der Personalisierung Ihrer Anmeldeseite.](media/personalizesignin.png)

    
4. Befolgen Sie die Schritte im Assistenten zum [Erstellen von DNS-Einträgen bei einem beliebigen DNS-Hostinganbieter für Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) , die ihre eigene Domäne verifizieren. Wenn Sie Ihren Domänenhost kennen, lesen Sie auch die [hostspezifischen Anweisungen](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).

    Wenn es sich bei Ihrem Hostinganbieter um einen GoDaddy oder einen anderen Host handelt, der mit der [Domäne Connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect)aktiviert ist, ist der Prozess einfach, und Sie werden automatisch aufgefordert, sich anzumelden und die Authentifizierung von Microsoft in Ihrem Namen zu ermöglichen:

    ![Wählen Sie auf der Seite GoDaddy-Zugriff bestätigen die Option autorisieren aus.](media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a>Hinzufügen von Benutzern und Zuweisen von Lizenzen

Sie können Benutzer im Assistenten hinzufügen, Sie können aber auch später im Admin Center [Hinzufügen](add-users-m365b.md) . Wenn Sie über einen lokalen Domänencontroller verfügen, können Sie außerdem Benutzer mit [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express)hinzufügen.

#### <a name="add-users-in-the-wizard"></a>Hinzufügen von Benutzern im Assistenten

Alle Benutzer, die Sie dem Assistenten hinzufügen, erhalten automatisch eine Microsoft 365 Business-Lizenz zugewiesen.

![Screenshot der Seite "neue Benutzer hinzufügen" im Assistenten](media/addnewuserspage.png)

1. Wenn Ihr Microsoft 365 Business-Abonnement über vorhandene Benutzer verfügt (beispielsweise, wenn Sie Azure AD Connect verwendet haben), erhalten Sie eine Option, um Ihnen jetzt Lizenzen zuzuweisen. Fügen Sie die Lizenzen ebenfalls hinzu.

3. Nachdem Sie die Benutzer hinzugefügt haben, erhalten Sie auch eine Option zum Freigeben von Anmeldeinformationen für die neuen Benutzer, die Sie hinzugefügt haben. Sie können auswählen, ob Sie Sie ausdrucken, per e-Mail versenden oder herunterladen möchten.

4. Überspringen Sie die Migration von e-Mail-Nachrichten, und wählen Sie **weiter** auf Seite **e-Mails migrieren** . 

    Wenn Sie von einem anderen e-Mail-Anbieter wechseln und Ihre Daten später kopieren möchten, können Sie [e-Mails und Kontakte in Office 365 migrieren](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e).


### <a name="connect-your-domain"></a>Verbinden Ihrer Domäne

> [!NOTE]
> Wenn Sie sich für die Verwendung der. onmicrosoft-Domäne entschieden oder Azure AD Connect zum Einrichten von Benutzern verwendet haben, wird dieser Schritt nicht angezeigt.
  
Zum Einrichten von Diensten müssen Sie einige Datensätze bei Ihrem DNS-Host oder Ihrer Domänenregistrierungsstelle aktualisieren.
  
1. Der Setup-Assistent erkennt normalerweise Ihre Registrierungsstelle und stellt einen Link zu Schritt-für-Schritt-Anweisungen zum Aktualisieren der NS-Einträge auf der Registrierungsstellen Website bereit. Wenn dies nicht der Fall ist, ändern Sie Namen [Server, um Office 365 bei einer beliebigen Domänenregistrierungsstelle einzurichten](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2). 

    - Wenn Sie über vorhandene DNS-Einträge verfügen, beispielsweise eine vorhandene Website, Ihr DNS-Host jedoch für die [Domäne Connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect)aktiviert ist, wählen Sie **für mich Datensätze hinzufügen**aus. 
    - Wenn Sie über vorhandene DNS-Einträge mit anderen DNS-Hosts verfügen (nicht für Domäne Connect aktiviert), sollten Sie Ihre eigenen DNS-Einträge verwalten, um sicherzustellen, dass die vorhandenen Dienste verbunden bleiben. Weitere Informationen finden Sie unter [Domain Basics](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) .

        ![Verbinden Sie Ihre Domänen Seite mit ich werde meine eigenen DNS-Einträge verwalten.](media/connectyourdomainpage.png)

2. Führen Sie die Schritte im Assistenten aus, und e-Mail und andere Dienste werden für Sie eingerichtet.

### <a name="set-up-security-policies-and-device-configurations"></a>Einrichten von Sicherheitsrichtlinien und Gerätekonfigurationen 

Die Richtlinien, die Sie im Assistenten eingerichtet haben, werden automatisch auf eine [Sicherheitsgruppe](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) mit dem Namen " *alle Benutzer*" angewendet. Sie können auch weitere Gruppen zum Zuweisen von Richtlinien im Admin Center erstellen.

1. Wählen Sie auf der Seite zum **Schützen Ihrer Arbeitsdateien auf mobilen Geräten** standardmäßig die Option **Arbeitsdateien schützen, wenn Geräte verloren gehen oder gestohlen werden** . Sie haben die Möglichkeit, die **Verwaltung der Benutzerzugriffe auf Office-Dateien auf mobilen Geräten**zu aktivieren, und dies wird empfohlen.

    ![Screenshot der Seite Arbeitsdateien auf mobilen Geräten schützen.](media/protectworkfilesondevices.png)

     - Erweitern Sie **Protect work Files, wenn Geräte verloren gehen oder gestohlen werden** , um die [Standardwerte](protect-work-files-on-lost-or-stolen-device.md)anzuzeigen:

        ![Screenshot der Standardwerte zum Schützen von Dateien auf verlorenen Geräten.](media/protectworkfilesondevicesdefault.png)

    - Wählen Sie **verwalten, wie Benutzer auf Office-Dateien auf mobilen Geräten zugreifen** , und erweitern Sie diese, um die [Standardwerte](manage-user-access-on-mobile-devices.md)anzuzeigen. Es wird empfohlen, während des Setups die Standardwerte zu übernehmen, um Anwendungsrichtlinien für Android, IOS und Windows 10 zu erstellen, die für alle Benutzer gelten. Nach Abschluss des Setups können Sie weitere Richtlinien erstellen.

        ![Screenshot der Schutzeinstellungen für Office-Dateien auf mobilen Geräten](media/useraccessonmobile.png)

2. Der letzte Schritt zum Schutz von Daten und Geräten ermöglicht Ihnen das Einrichten von Richtlinien für die Sicherung von Windows 10-Geräten. Diese Einstellungen werden automatisch angewendet, wenn Windows 10 eines Benutzers eine Verbindung mit Ihrer Organisation herstellt. Sie können **sichere Windows 10-Geräte** erweitern, um die [Standardwerte](secure-windows-10-devices.md)anzuzeigen und zu ändern.
3. Sie können auch festlegen, dass Office auf Windows 10-Geräten [automatisch installiert](install-office-on-windows-10-during-setup.md) wird.

    ![Screenshot der Seite "Windows 10-Gerätekonfiguration festlegen".](media/setwin10config.png)



## <a name="deploy-office-365-client-apps"></a>Bereitstellen von Office 365-Client-apps

Wenn Sie Office-Apps während der Einrichtung automatisch in installieren, werden die apps auf den Windows 10-Geräten installiert, sobald sich die Benutzer bei Azure AD von Ihren Windows-Geräten mit ihren Arbeits Anmeldeinformationen angemeldet haben.
Informationen zum Installieren von Office auf mobilen IOS-oder Android-Geräten finden Sie unter [Einrichten von mobilen Geräten für Microsoft 365 Business-Benutzer](set-up-mobile-devices.md).

Sie können Office auch einzeln installieren. Anweisungen finden Sie unter [Installieren von Office auf einem PC oder Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658) .
