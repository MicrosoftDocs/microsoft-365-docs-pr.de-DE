---
title: Einrichten von Microsoft 365 Business Standard
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
- TRN_SMB
ms.custom:
- TRN_M365B
- OKR_SMB_Videos
- okr_smb
- AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
- BEA160
description: Erfahren Sie, wie Sie Ihr Microsoft 365 Business Standard-Abonnement einrichten.
ms.openlocfilehash: cfc198c749cfcaa76bc3fa6323e1dba8a46e7388
ms.sourcegitcommit: 25afc0c34edc7f8a5eb389d8c701175256c58ec8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2020
ms.locfileid: "47324446"
---
# <a name="set-up-microsoft-business-standard"></a>Einrichten von Microsoft Business Standard

Sehen Sie sich ein kurzes Video zum Einrichten von Microsoft 365 Business Standard an.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4ELKR]

Wenn Sie dieses Video hilfreich fanden, sehen Sie sich bitte die [komplette Schulungsserie für kleine Unternehmen und diejenigen, für die Microsoft 365 neu ist](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816) an.
  
 *Diese Schritte gelten für Unternehmen und [gemeinnützige Einrichtungen](https://go.microsoft.com/fwlink/p/?LinkId=627221), die über den **[Microsoft 365 Business Standard-Plan verfügen.](https://go.microsoft.com/fwlink/p/?LinkId=627220)***

Sehen Sie sich ein kurzes Video zum Einrichten von Microsoft 365 Business Standard (vormals Office 365 Business Premium) an.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/913be1ad-bae1-40c0-9ded-15bb477b828b]

Wenn Sie dieses Video hilfreich fanden, sehen Sie sich bitte die [komplette Schulungsserie für kleine Unternehmen und jene, die neu bei Microsoft 365 sind](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816), an.

## <a name="add-your-domain-to-personalize-sign-in"></a>Hinzufügen Ihrer Domäne zum Personalisieren der Anmeldung

Wenn Sie Microsoft 365 Business Standard erwerben, haben Sie die Möglichkeit, eine Domäne zu verwenden, die Sie besitzen, oder während der Registrierung eine zu erwerben.

- Wenn Sie bei der Registrierung eine neue Domäne erworben haben, ist Ihre Domäne eingerichtet, und Sie können zu [Benutzer hinzufügen und Lizenzen zuweisen](#add-users-and-assign-licenses) wechseln.

1. Melden Sie sich mit den Anmeldeinformationen des globalen Administrators bei [Microsoft 365 Admin Center](https://admin.microsoft.com) an. 

2. Wählen Sie **Zu Setup wechseln** aus, um den Assistenten zu starten.

3. Auf der Seite **Office-Anwendungen installieren** können Sie die Apps optional auf Ihrem eigenen Computer installieren.
    
4. Geben Sie im Schritt **Domäne hinzufügen** den gewünschten Domänennamen ein (z. B. contoso.com).

    > [!IMPORTANT]
    > Wenn Sie während der Registrierung eine Domäne erworben haben, wird der Schritt **eine Domäne hinzufügen** nicht angezeigt. Wechseln Sie stattdessen zu [Benutzer hinzufügen](#add-users-and-assign-licenses).

    
4. Führen Sie die Schritte im Assistenten aus, um [DNS-Einträge bei einem beliebigen DNS-Hostinganbieter für Office 365 zu erstellen](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider), der verifiziert, dass Sie die Domäne besitzen. Wenn Sie Ihren Domänenhost kennen, lesen Sie auch die [hostspezifischen Anweisungen](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).

    Wenn es sich bei Ihrem Hostinganbieter um GoDaddy oder einen anderen Host handelt, der mit [Domain Connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect) arbeitet, ist der Vorgang einfach, und Sie werden aufgefordert, sich anzumelden, um Microsoft in Ihrem Auftrag authentifizieren zu lassen.

    ![Wählen Sie auf der GoDaddy-Seite „Zugriff bestätigen“ den Befehl Autorisieren aus.](../../media/godaddyauth.png)

## <a name="add-users-and-assign-licenses"></a>Benutzer hinzufügen und Lizenzen zuweisen

Sie können Benutzer entweder hier hinzufügen oder Sie können [Benutzer später im Admin Center hinzufügen](../add-users/add-users.md). Wenn Sie einen lokalen Domänencontroller besitzen, können Sie Benutzer zudem mit [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express) hinzufügen.

## <a name="add-users-in-the-wizard"></a>Hinzufügen von Benutzern im Assistenten

Allen Benutzern, die Sie im Assistenten hinzufügen, wird automatisch eine Microsoft 365 Business Standard-Lizenz zugewiesen.

1. Wenn Ihr Microsoft 365 Business Standard-Abonnement bereits Benutzer enthält (z. B. bei vorheriger Verwendung von Azure AD Connect), erhalten Sie die Möglichkeit, diesen Benutzern jetzt Lizenzen zuzuweisen. Setzen Sie den Vorgang fort, und fügen Sie ihnen Lizenzen hinzu.

2. Nachdem Sie die Benutzer hinzugefügrt haben, erhalten Sie außerdem die Möglichkeit, Anmeldeinformationen für die hinzugefügten neuen Benutzer freizugeben. Sie können auswählen, ob diese Informationen ausgedruckt, per E-Mail gesendet oder heruntergeladen werden sollen.

## <a name="connect-your-domain"></a>Ihre Domäne verbinden

> [!NOTE]
> Wenn Sie sich für die Verwendung der .onmicrosoft-Domäne oder die Verwendung von Azure AD Connect zum Einrichten von Benutzern entschieden haben, wird dieser Schritt nicht angezeigt.
  
Zum Einrichten von Diensten müssen Sie einige Einträge bei Ihrem DNS-Host oder Ihrer Domänenregistrierungsstelle aktualisieren.
  
1. In der Regel erkennt der Setup-Assistent Ihre Registrierungsstelle und zeigt einen Link an, über den Sie schrittweise Anleitungen zum Aktualisieren Ihrer NS-Einträge auf der Website der Registrierungsstelle aufrufen können. falls nicht, [Ändern Sie Nameserver zum Einrichten von Office 365 bei einer beliebigen Domänenregistrierungsstelle](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/change-nameservers-at-any-domain-registrar). 

    - Wenn Sie über vorhandene DNS-Einträge verfügen, z. B. eine vorhandene Website, aber Ihr DNS-Host für [Domain Connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect) aktiviert ist, wählen Sie **Einträge für mich hinzufügen** aus. Übernehmen Sie auf der Seite **Wählen Sie Ihre Onlinedienste** die Standardeinstellungen, wählen Sie **Weiter** aus, und wählen Sie auf der Seite Ihres DNS-Hosts **autorisieren** aus.
    - Wenn Sie über vorhandene DNS-Einträge für andere DNS-Hosts (die nicht mit Domain Connect arbeiten) verfügen, können Sie Ihre eigenen DNS-Einträge verwalten, um sicherzustellen, dass die vorhandenen Dienste verbunden bleiben. Weitere Informationen finden Sie unter [Domain-Grundlagen](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics).

2. Befolgen Sie die Schritte im Assistenten, damit E-Mail und andere Dienste für Sie eingerichtet werden.

    Wenn der Registrierungsvorgang abgeschlossen ist, werden Sie zum Admin Center weitergeleitet, wo Sie einem Assistenten folgen, um Office-Apps zu installieren, Ihre Domäne hinzuzufügen, Benutzer hinzuzufügen und Lizenzen zuzuweisen. Nach Abschluss der Ersteinrichtung können Sie die Seite **Setup** im Admin Center verwenden, um mit der Einrichtung und Konfiguration der Dienste fortzufahren, die in Ihren Abonnements enthalten sind.

    Weitere Informationen über den Installationsassistenten und die Seite **Setup** im Admin Center finden Sie unter [Unterschied zwischen dem Installationsassistenten und der Seite "Setup"](o365-setup-wizard-and-setup-page.md).

## <a name="finish-setting-up"></a>Abschließen der Einrichtung

### <a name="set-up-outlook-for-email"></a>Einrichten von Outlook für E-Mail

1. Suchen Sie im Windows-Startmenü nach Outlook, und wählen Sie es aus.

    (Wenn Sie einen Mac verwenden, öffnen Sie Outlook über die Symbolleiste, oder suchen Sie es mit dem Finder.)

    Wenn Sie nur Outlook installiert haben, wählen Sie auf der Willkommensseite **Weiter** aus.

2. Wählen Sie **Datei** \> **Info** \> **Konto hinzufügen** aus.

3. Geben Sie Ihre Microsoft E-Mail-Adresse ein, und wählen Sie **Verbinden** aus.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/9fe86884-8a83-42cc-bca9-61a12e6dad31?autoplay=false]
  
Mehr dazu unter [Einrichten von Outlook für E-Mail](https://support.microsoft.com/office/f5bf0cd1-e1f3-4b0d-a022-ecab17efe86f).
  
### <a name="import-email"></a>Importieren von E-Mails

Wenn Sie Outlook mit einem anderen E-Mail-Konto verwendet haben, können Sie Ihre früheren E-Mails, Kalender und Kontakte in Ihr neues Microsoft-Konto importieren.
  
1. **Exportieren Ihrer alten E-Mails**

    In Outlook, choose **File** \> **Open &amp; Export** \> **Import/Export**.

    Wählen Sie **Exportieren in eine Datei** und folgen Sie dann den Schritten zum Exportieren Ihrer Outlook-Datendatei (.pst) und aller Unterordner.

2. **Importieren Ihrer alten E-Mails**

    In Outlook, choose **File** \> **Open &amp; Export** \> **Import/Export** again.

    Dieses Mal wählen Sie **Aus anderen Programmen oder Dateien importieren** aus, und befolgen die Schritte zum Importieren der Sicherungsdatei, die Sie erstellt haben, als Sie Ihre alten E-Mails exportiert haben.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/40f7df36-9e24-44e5-8791-e9ed0dd8fd21?autoplay=false]
  
Mehr dazu unter [Importieren von E-Mails mit Outlook](https://support.microsoft.com/office/6a3771d4-4c1d-4a25-92a6-0b8e476335de).

Sie können das Exchange Admin Center verwenden, um die E-Mails aller Benutzer zu importieren. Weitere Informationen finden Sie unter [Migrieren mehrerer E-Mail-Konten](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration).
  
### <a name="use-a-public-website"></a>Verwenden einer öffentlichen Website

Microsoft 365 enthält keine öffentliche Website für Ihr Unternehmen. Wenn Sie eine einrichten möchten, überlegen Sie, ob Sie einen Microsoft-Partner, z. B. GoDaddy oder WIX, einbeziehen sollten.
  
1. Wechseln Sie aus dem Admin Center zu **Ressourcen** und wählen Sie **Öffentliche Website** aus.

2. Wählen Sie unter einer der Optionen **Weitere Informationen** aus. Registrieren Sie sich dann bei einem Websitepartner, und verwenden Sie dessen Tools zum Einrichten und Entwerfen Ihrer Website.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/4839abc6-9323-4cbf-a79d-2907235f9ebb]

Mehr dazu unter [Verwenden einer öffentlichen Website](https://support.microsoft.com/office/3325d50e-d131-403c-a278-7f3296fe33a9).