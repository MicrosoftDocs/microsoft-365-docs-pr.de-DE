---
title: Einrichten von Microsoft 365 Basic
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
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
- AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
- BEA160
description: Erfahren Sie, wie Sie Ihr Microsoft 365 Business Basic-Abonnement einrichten.
ms.openlocfilehash: d0ac9835be25377496893d62076a5cdc426f3b9e
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53227739"
---
# <a name="set-up-microsoft-365-business-basic"></a>Einrichten von Microsoft 365 Basic

## <a name="watch-set-up-microsoft-365-business-basic"></a>Ansehen: Einrichten von Microsoft 365 Business Basic

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vk3W]

Wenn Sie dieses Video hilfreich fanden, sehen Sie sich bitte die [komplette Schulungsserie für kleine Unternehmen und jene, die neu bei Microsoft 365 sind](../../business-video/index.yml), an.

## <a name="add-your-domain-to-personalize-sign-in"></a>Hinzufügen Ihrer Domäne zum Personalisieren der Anmeldung

Wenn Sie Microsoft 365 Business Basic erwerben, haben Sie die Möglichkeit, eine Domäne zu verwenden, die Sie besitzen, oder während der Registrierung eine zu erwerben.

- Wenn Sie bei der Registrierung eine neue Domäne erworben haben, ist Ihre Domäne eingerichtet, und Sie können zu [Benutzer hinzufügen und Lizenzen zuweisen](#add-users-and-assign-licenses) wechseln.

 ::: moniker range="o365-worldwide"

1. Wechseln Sie zum Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.

::: moniker-end

::: moniker range="o365-germany"

1. Wechseln Sie zum Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. Wechseln Sie zum Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.

::: moniker-end 

2. Wählen Sie **Zu Setup wechseln** aus, um den Assistenten zu starten.
    
3. Geben Sie im Schritt **Domäne hinzufügen** den gewünschten Domänennamen ein (z. B. contoso.com).

    > [!IMPORTANT]
    > Wenn Sie während der Registrierung eine Domäne erworben haben, wird der Schritt **eine Domäne hinzufügen** nicht angezeigt. Wechseln Sie stattdessen zu [Benutzer hinzufügen](#add-users-and-assign-licenses).

    
4. Führen Sie die Schritte im Assistenten aus, um [DNS-Einträge bei einem beliebigen DNS-Hostinganbieter für Office 365 zu erstellen](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider), der verifiziert, dass Sie die Domäne besitzen. Wenn Sie Ihren Domänenhost kennen, lesen Sie auch [Hinzufügen einer Domäne zu Microsoft 365](/microsoft-365/admin/setup/add-domain).

    Wenn es sich bei Ihrem Hostinganbieter um GoDaddy oder einen anderen Host handelt, der mit [Domain Connect](/office365/admin/get-help-with-domains/domain-connect) arbeitet, ist der Vorgang einfach, und Sie werden aufgefordert, sich anzumelden, um Microsoft in Ihrem Auftrag authentifizieren zu lassen.

    ![Wählen Sie auf der GoDaddy-Seite „Zugriff bestätigen“ den Befehl Autorisieren aus.](../../media/godaddyauth.png)

## <a name="add-users-and-assign-licenses"></a>Benutzer hinzufügen und Lizenzen zuweisen

Sie können Benutzer entweder hier hinzufügen oder Sie können [Benutzer später im Admin Center hinzufügen](../add-users/add-users.md). Wenn Sie einen lokalen Domänencontroller besitzen, können Sie Benutzer zudem mit [Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-express) hinzufügen.

## <a name="add-users-in-the-wizard"></a>Hinzufügen von Benutzern im Assistenten

Allen Benutzern, die Sie im Assistenten hinzufügen, wird automatisch eine Microsoft 365 Business Basic-Lizenz zugewiesen.

1. Wenn Ihr Microsoft 365 Business Basic-Abonnement bereits Benutzer enthält (z. B. bei vorheriger Verwendung von Azure AD Connect), erhalten Sie die Möglichkeit, diesen Benutzern jetzt Lizenzen zuzuweisen. Setzen Sie den Vorgang fort, und fügen Sie ihnen ebenfalls Lizenzen hinzu.

2. Nachdem Sie die Benutzer hinzugefügrt haben, erhalten Sie außerdem die Möglichkeit, Anmeldeinformationen für die hinzugefügten neuen Benutzer freizugeben. Sie können auswählen, ob diese Informationen ausgedruckt, per E-Mail gesendet oder heruntergeladen werden sollen.

## <a name="connect-your-domain"></a>Ihre Domäne verbinden

> [!NOTE]
> Wenn Sie sich für die Verwendung der .onmicrosoft-Domäne oder die Verwendung von Azure AD Connect zum Einrichten von Benutzern entschieden haben, wird dieser Schritt nicht angezeigt.
  
Zum Einrichten von Diensten müssen Sie einige Einträge bei Ihrem DNS-Host oder Ihrer Domänenregistrierungsstelle aktualisieren.
  
1. In der Regel erkennt der Setup-Assistent Ihre Registrierungsstelle und zeigt einen Link an, über den Sie schrittweise Anleitungen zum Aktualisieren Ihrer NS-Einträge auf der Website der Registrierungsstelle aufrufen können. falls nicht, [Ändern Sie Nameserver zum Einrichten von Office 365 bei einer beliebigen Domänenregistrierungsstelle](../get-help-with-domains/change-nameservers-at-any-domain-registrar.md). 

    - Wenn Sie über vorhandene DNS-Einträge verfügen, z. B. eine vorhandene Website, aber Ihr DNS-Host für [Domain Connect](/office365/admin/get-help-with-domains/domain-connect) aktiviert ist, wählen Sie **Einträge für mich hinzufügen** aus. Übernehmen Sie auf der Seite **Wählen Sie Ihre Onlinedienste** die Standardeinstellungen, wählen Sie **Weiter** aus, und wählen Sie auf der Seite Ihres DNS-Hosts **autorisieren** aus.
    - Wenn Sie über vorhandene DNS-Einträge für andere DNS-Hosts (die nicht mit Domain Connect arbeiten) verfügen, können Sie Ihre eigenen DNS-Einträge verwalten, um sicherzustellen, dass die vorhandenen Dienste verbunden bleiben. Weitere Informationen finden Sie unter [Domain-Grundlagen](/office365/admin/get-help-with-domains/dns-basics).

2. Befolgen Sie die Schritte im Assistenten, damit E-Mail und andere Dienste für Sie eingerichtet werden.

    Wenn der Registrierungsvorgang abgeschlossen ist, werden Sie zum Admin Center weitergeleitet, wo Sie Benutzer hinzufügen und Lizenzen zuweisen können. Nach Abschluss der Ersteinrichtung können Sie die Seite **Setup** im Admin Center verwenden, um mit der Einrichtung und Konfiguration der Dienste fortzufahren, die in Ihren Abonnements enthalten sind.

    Weitere Informationen über den Installationsassistenten und die Seite **Setup** im Admin Center finden Sie unter [Unterschied zwischen dem Installationsassistenten und der Seite "Setup"](o365-setup-wizard-and-setup-page.md).