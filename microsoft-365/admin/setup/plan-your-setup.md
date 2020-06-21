---
title: Planen des Setups von Microsoft 365 for Business
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
ms.assetid: eb926624-018b-4486-bf11-5fba6ee4d645
description: Erfahren Sie, was Sie tun müssen, um Ihr Microsoft 365 for Business einzurichten.
ms.openlocfilehash: 7509e2c4801adbca492e5f5446c5b97eae31dccf
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/17/2020
ms.locfileid: "44778949"
---
# <a name="plan-your-setup-of-microsoft-365-for-business"></a>Planen des Setups von Microsoft 365 for Business

Dieser Artikel richtet sich an Personen, die einen Microsoft 365 for Business-Plan abonniert haben.
  
Es gibt ein paar Dinge, die Sie entscheiden müssen, und Informationen, die Sie zur Hand haben müssen, bevor Sie Ihre Organisation auf Microsoft 365 verschieben.
  
## <a name="info-to-have-on-hand-before-you-run-the-setup-wizard"></a>Informationen zur Hand, bevor Sie den Setup-Assistenten ausführen

Wenn Sie bereit sind, den Setup-Assistenten auszuführen und Ihre Domäne nach Microsoft 365 zu migrieren, finden Sie hier die erforderlichen Informationen zur Hand:
  
- Liste der Personen, die Sie Microsoft 365 hinzufügen möchten. Selbst wenn Sie Sie bereits zu Microsoft 365 hinzugefügt haben, müssen Sie, wenn Sie Ihre Domäneninformationen aktualisieren, ihre Namen hier eingeben.

- Wie Sie Ihre Mitarbeiter über Ihre Benutzer-ID und Ihr Kennwort informieren, damit Sie sich anmelden können. Möchten Sie ihnen die Informationen telefonisch mitteilen? Oder sie an ihre private E-Mail-Adresse senden? Sie haben keinen Zugriff auf Ihre e-Mails, sodass Sie diese nicht verwenden können.

- Wenn Sie über einen Domänennamen für Ihre Organisation (beispielsweise contoso.com) verfügen **und** die Verwendung von Microsoft e-Mail planen, müssen Sie wissen, wo Ihre Domäne registriert ist und über Anmeldeinformationen verfügt.

## <a name="what-happens-when-you-run-the-microsoft-365-setup-wizard"></a>Was geschieht, wenn Sie den Microsoft 365-Setup-Assistenten ausführen

Der Setup-Assistent führt Sie durch die Installation der Microsoft 365-apps auf Ihrem Computer, hinzufügen und Überprüfen Ihrer Domäne, Hinzufügen von Benutzern und Zuweisen von Lizenzen und verbinden Ihrer Domäne.

> [!NOTE]
> Wenn Sie den Benutzern, die Sie im Assistenten hinzufügen, [Administratorrollen in Microsoft 365 for Business zuweisen](../add-users/assign-admin-roles.md) müssen, können Sie dies später auf der Seite **Benutzer** tun. 
  
Wenn Sie den Setup-Assistenten nicht abschließen, können Sie Setupaufgaben jederzeit über das Setup von [Admin Center](https://go.microsoft.com/fwlink/p/?linkid=2024339)ausführen  >  **Setup**. Von hier aus können Sie e-Mails und Kontakte aus einem anderen e-Mail-Dienst migrieren, die Domäne Ihres Administratorkontos ändern, Ihre Abrechnungsinformationen verwalten, Benutzer hinzufügen oder entfernen, Kennwörter zurücksetzen und andere Geschäftsfunktionen ausführen. Weitere Informationen zu den Unterschieden zwischen dem Setup-Assistenten und der Seite **Setup** finden Sie unter [Differences From the Microsoft 365 Setup Wizard and the Setup Page](o365-setup-wizard-and-setup-page.md).

Wenn Sie an einer Stelle nicht weiterkommen, rufen Sie uns an. [Wir helfen Ihnen gerne!](../contact-support-for-business-products.md)
  
## <a name="when-not-to-use-the-setup-wizard-active-directory-synchronization-and-hybrid-environments"></a>Wann der Setup-Assistent nicht verwendet werden sollte Active Directory-Synchronisierung und Hybridumgebungen

Es gibt eine Reihe von Szenarien, die entweder das Migrieren von Daten oder Benutzern aus lokalen Umgebungen oder das Einrichten eines Hybridsystems umfassen, das die Verzeichnissynchronisierung umfasst. Wenn Sie sich in einer der beiden Kategorien befinden, befolgen Sie die Anweisungen in den folgenden Artikeln:
  
- Informationen zum Einrichten der Verzeichnissynchronisierung mit Ihren lokalen Active Directory finden Sie unter [Einrichten der Verzeichnissynchronisierung für Microsoft 365](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization)und verstehen der unterschiedlichen Identitäts Modelle in Microsoft 365, lesen [Grundlegendes zur Microsoft 365-Identität und Azure-Active Directory](https://docs.microsoft.com/office365/enterprise/about-office-365-identity).

- Die vollständigen Anweisungen zum Einrichten einer Exchange-Hybridbereitstellung, die Sie durch alle verschiedenen Möglichkeiten zum Einrichten einer Exchange-Hybridbereitstellung führen (einschließlich der Einrichtung von DNS-Einträgen) finden Sie hier: [Bereitstellungs-Assistent für Exchange Server](https://aka.ms/exdeploy)

- Informationen zum Einrichten einer SharePoint-Hybridbereitstellung, insbesondere zum Einrichten der Hybridsuche und von Websitefunktionen finden Sie unter [Hybridsuche in SharePoint](https://docs.microsoft.com/SharePoint/hybrid/hybrid-search-in-sharepoint).

## <a name="move-to-microsoft-365-all-at-once-or-in-stages"></a>Wechsel zu Microsoft 365 auf einmal oder in Phasen

- **Möchten Sie Ihre Organisation auf einmal auf Microsoft 365 migrieren?** Wenn dies der Fall ist, planen Sie die Verlagerung ihrer Domäne auf Microsoft 365 sofort. Beginnen Sie mit der Ausführung des Setup-Assistenten für Microsoft 365; Sie werden aufgefordert, Ihre Domäne einzurichten.

- **Möchten Sie schrittweise zu Microsoft 365 umsteigen?** Wenn Sie in Phasen zu Microsoft 365 wechseln möchten, überspringen Sie den Microsoft 365-Setup-Assistenten, und nehmen Sie Microsoft 365-Features in der folgenden Reihenfolge an:

    1. [Fügen Sie Ihre Mitarbeiter zu Microsoft 365 hinzu,](../add-users/add-users.md) damit Sie die Office-apps herunterladen und installieren können.

    2. [Laden Sie die Office-Apps herunter, und installieren Sie sie](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658), um Word, Excel und PowerPoint auf Ihrem Computer und Ihren Geräten zu verwenden.

    3. [Richten Sie Microsoft Teams](#plan-for-teams) ein, die für Ihre Besprechungen verwendet werden sollen.

    4. [Migrieren Sie Ihre Inhalte zu Microsoft 365 Cloud Storage](set-up-file-storage-and-sharing.md) (OneDrive oder SharePoint-Teamwebsites).

    5. Wenn Sie fertig sind, wählen Sie im [Admin Center](https://go.microsoft.com/fwlink/p/?linkid=2024339)im linken Navigationsbereich die Option **Setup** aus, und verwenden Sie die Seite **Setup** , um [Ihre Domäne und e-Mail zu migrieren](add-domain.md).

## <a name="check-that-your-devices-meet-system-requirements"></a>Überprüfen Sie, ob Ihre Geräte die Systemanforderungen erfüllen

Jede Person in Ihrer Organisation kann die Office 2016 Suite von apps (Word, Excel, PowerPoint usw.) auf bis zu fünf PCs und Macs installieren. Weitere Informationen finden Sie unter den Betriebssystem- und Computeranforderungen für die Installation von [Office 2016-Suiten](https://go.microsoft.com/fwlink/?LinkId=534827) für Unternehmen.
  
Mobile Apps können auf Ios-, Android-und Windows-Geräten installiert werden. Informationen zur Unterstützung mobiler Geräte und zur Browserunterstützung finden Sie unter den [Systemanforderungen für Office](https://go.microsoft.com/fwlink/?LinkId=534827).
  
## <a name="plan-for-email"></a>Planung von E-Mail

Wenn Sie planen, von einem vorhandenen e-Mail-Dienst zu Microsoft 365 zu wechseln, dauert es in der Regel zwei Tage, um den Switch zu erstellen.
  
### <a name="plan-for-email-downtime"></a>Planen von E-Mail-Ausfallzeiten
  
Wenn Sie Microsoft 365 für Ihre e-Mail verwenden möchten:
  
- Um Ihre geschäftliche e-Mail-Adresse (wie *Rob \@ contoso.com*) aus einem anderen e-Mail-Dienst zu Microsoft 365 zu migrieren, müssen Sie Ihre e-Mails an Ihr neues Microsoft 365-Postfach senden. Dazu wählen Sie auf der Seite **Setup** die Option **die Daten der Benutzer migrieren** aus, wo wir Sie Schritt für Schritt durch die Updates führen, die Sie auf Ihrem Domänenhost vornehmen müssen.

- Nach der Aktualisierung des Domänenhosts wird die Änderung normalerweise innerhalb von nur ein bis zwei Stunden wirksam. Beachten Sie jedoch, dass es manchmal bis zu 72 Stunden dauern kann, bis die Änderungen über das Internet aktualisiert werden.

- Da es möglicherweise zu einer e-Mail-Ausfallzeit kommt, empfehlen wir Ihnen, an einem Abend oder an einem Wochenende zu Microsoft e-Mail zu wechseln, wenn Sie weniger e-Mails erhalten möchten.

### <a name="plan-to-move-your-existing-email-contacts-and-calendar"></a>Planen der Verschiebung von vorhandenen E-Mails, Kontakten und Kalendern
  
Wenn Sie Microsoft 365 für Ihr e-Mail-Konto verwenden möchten, können Sie Ihre vorhandenen e-Mails, Kontakte und Kalender mitbringen. Auf der Seite **Setup** können Sie Ihre vorhandenen e-Mails und Kontakte für die meisten Szenarien migrieren. Wir bieten außerdem schrittweise Anleitungen für das Verschieben einzelner oder vieler Postfächer.
  
|**Wie viele Postfächer?**|**Empfehlung**|
|:-----|:-----|
|Nur einige  <br/> |Wenn Sie die Postfächer nicht mithilfe der **Setup** -Seite migrieren möchten, können Postfachbesitzer ihre eigenen e-Mails und Kontakte migrieren lassen. Weitere Informationen finden Sie unter [Migrieren von e-Mails und Kontakten zu Microsoft 365 for Business](migrate-email-and-contacts-admin.md).  <br/> |
|Mehrere  <br/> |Wenn Sie von Gmail migrieren, lesen Sie [Migrieren von G Suite-Postfächern zu Microsoft 365](https://docs.microsoft.com/Exchange/mailbox-migration/migrating-imap-mailboxes/migrate-g-suite-mailboxes).  <br/> Wenn Sie von einem anderen e-Mail-Anbieter migrieren, einschließlich Exchange, finden Sie unter [Ways to migrate Multiple e-Mail Accounts to Microsoft 365](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration).  <br/> |

## <a name="plan-for-file-storage-and-migration"></a>Planen von Dateispeicherung und -migration

Microsoft 365 bietet cloudspeicher für Einzelpersonen, kleine Organisationen und Unternehmen. Anleitungen zum Speichern von Where finden Sie unter [where you can Store Documents in Microsoft 365](https://support.microsoft.com/office/c7c20284-bc94-47f4-9728-d28e9daf0790).
  
- **Sie können Hunderte von Dateien** in [OneDrive](https://support.microsoft.com/office/45114744-6D42-45CD-8975-F9617819BDEB) oder eine [SharePoint-Teamwebsite](https://support.microsoft.com/office/da549fb1-1fcb-4167-87d0-4693e93cb7a0#__toc384119242)migrieren. Dabei können jeweils 100 Dateien zugleich hochgeladen werden. Laden Sie keine Dateien mit mehr als 2 GB hoch (dies ist standardmäßig die maximale Dateigröße).
  
- **Wenn Sie mehrere tausend Dateien** in Microsoft 365 Storage migrieren möchten, überprüfen Sie die [SharePoint Online Grenzen](https://go.microsoft.com/fwlink/p/?LinkID=856113). Wir empfehlen die Verwendung eines Migrationstools oder die Verpflichtung eines [Partners](https://go.microsoft.com/fwlink/?linkid=391089) zu Ihrer Unterstützung bei der Migration. Informationen zum Migrieren einer noch größeren Anzahl von Dateien finden Sie unter [SharePoint Online und OneDrive-Migrationsbenutzerhandbuch](https://go.microsoft.com/fwlink/?LinkId=723574).
  
## <a name="plan-for-teams"></a>Planen von Teams

Sie können Microsoft Teams verwenden, um Anrufe an andere Personen in Ihrer Organisation zu tätigen, die sich in Ihrem Abonnement befinden. Wenn Ihre Organisation beispielsweise über 10 Mitarbeiter verfügt, können Sie mit Microsoft Teams ohne spezielles Setup miteinander chatten und sich gegenseitig aufrufen. Weitere Informationen finden Sie unter [Erste Schritte mit Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/get-started-with-teams-quick-start).

Informationen zu größeren Organisationen oder wenn Sie mit Skype for Business, lokalen oder hybridbereitstellungen beginnen, finden Sie unter [How to Roll Out Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/how-to-roll-out-teams).
  
## <a name="plan-for-integration-with-active-directory-or-other-software"></a>Planen der Integration mit Active Directory oder sonstiger Software

- **Wünschen Sie eine Integration mit Ihrem lokalen Active Directory?** Sie können Ihre lokalen Active Directory mithilfe von Azure Active Directory Connect in Microsoft 365 integrieren. Anweisungen finden Sie unter [Einrichten der Verzeichnissynchronisierung für Microsoft 365](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization).
  
- **Möchten Sie Microsoft 365 mit Software integrieren, die von anderen Unternehmen erstellt wurde?** Wenn Sie Microsoft 365 mit anderer Software in Ihrer Organisation integrieren müssen, empfehlen wir Ihnen, [einen Partner](https://go.microsoft.com/fwlink/?linkid=391089) zur Unterstützung Ihrer Bereitstellung zu mieten.
  
## <a name="do-you-want-someone-to-help-you-set-up-microsoft-365"></a>Möchten Sie, dass Ihnen jemand helfen kann, Microsoft 365 einzurichten?

- **Wenn Sie weniger als 50 Mitarbeiter beschäftigen:**

  - **Fragen Sie nach Hilfe, und wir rufen Sie an**. Nachdem Sie Microsoft 365 erworben haben, können Sie auf das Admin Center zugreifen (Sie müssen Setup nicht ausführen, um es zu erhalten). Wählen Sie unten im Admin Center die Option **Hilfe benötigen?** Beschreiben Sie Ihr Problem, und wir werden Sie anrufen. 
  - **Rufen Sie [Microsoft 365 for Business Support](../contact-support-for-business-products.md) mit Ihren Fragen**an. We're here to help! 
  - **Erwägen Sie das Hinzuziehen eines [Microsoft-Partners](https://go.microsoft.com/fwlink/?linkid=391089)**. Wenn Sie wenig Zeit haben oder erweiterte Anforderungen haben (wie das Verschieben von Tausenden von Dateien in Microsoft 365 Cloud Storage oder die Integration in andere Software), kann ein erfahrener Partner eine große Hilfe sein. 

- **Wenn Sie mehr als 50 Mitarbeiter beschäftigen**, steht das [FastTrack Onboarding Center](https://go.microsoft.com/fwlink/?LinkId=517115) bereit, um Sie bei Ihrer Bereitstellung zu unterstützen. 
