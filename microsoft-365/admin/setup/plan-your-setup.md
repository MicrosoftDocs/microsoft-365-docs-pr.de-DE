---
title: Planen der Einrichtung von Microsoft 365 Business
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
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- MET150
- MOE150
ms.assetid: eb926624-018b-4486-bf11-5fba6ee4d645
description: Erfahren Sie mehr über die Anforderungen und Überlegungen für den Wechsel zu Microsoft 365 Business.
ms.openlocfilehash: 7ec1fae211ec42afd510ee431a3ea7e17e2fd16b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914066"
---
# <a name="plan-your-setup-of-microsoft-365-for-business"></a>Planen der Einrichtung von Microsoft 365 Business

Dieser Artikel gilt für Personen, die einen Microsoft 365 For Business-Plan abonniert haben.
  
Bevor Sie Ihre Organisation zu Microsoft 365 verschieben, gibt es Anforderungen, die Sie erfüllen müssen, Informationen, die Sie zur Hand haben müssen, und Entscheidungen, die Sie treffen müssen.


  
## <a name="info-to-have-on-hand-before-you-run-the-setup-wizard"></a>Informationen, die vor dem Ausführen des Setup-Assistenten zur Hand sein müssen

Wenn Sie bereit sind, den Setup-Assistenten ausführen und Ihre Domäne zu Microsoft 365 verschieben, finden Sie hier die Informationen, die Sie zur Hand haben müssen:
  
- Liste der Personen, die Sie Microsoft 365 hinzufügen möchten. Auch wenn Sie sie bereits zu Microsoft 365 hinzugefügt haben, müssen Sie ihre Namen hier eingeben, wenn Sie Ihre Domäneninformationen aktualisieren.

- Wie Sie Ihre Mitarbeiter über ihre Benutzer-ID und ihr Kennwort benachrichtigen, damit sie sich anmelden können. Möchten Sie ihnen die Informationen telefonisch mitteilen? Oder sie an ihre private E-Mail-Adresse senden? Sie haben keinen Zugriff auf ihre E-Mails, daher können Sie sie nicht verwenden.

- Wenn Sie über einen Domänennamen für Ihre Organisation (z. B. **contoso.com)** verfügen und die Verwendung von Microsoft-E-Mails planen, müssen Sie wissen, wo Ihre Domäne registriert ist und über Anmeldeinformationen verfügen.

## <a name="what-happens-when-you-run-the-microsoft-365-setup-wizard"></a>Was geschieht, wenn Sie den Microsoft 365-Setup-Assistenten ausführen

Der Setup-Assistent führt Sie durch das Installieren der Microsoft 365-Apps auf Ihrem Computer, das Hinzufügen und Überprüfen Ihrer Domäne, das Hinzufügen von Benutzern und das Zuweisen von Lizenzen zu ihnen und das Verbinden Ihrer Domäne.

> [!NOTE]
> Wenn Sie den Benutzern, die Sie im Assistenten hinzufügen, [Administratorrollen in Microsoft 365 Business](../add-users/assign-admin-roles.md) zuweisen müssen, können Sie dies später auf der Seite **Benutzer** tun. 
  
Wenn Sie den Setup-Assistenten nicht abschließen, können Sie setup tasks jederzeit über [das Admin Center](https://go.microsoft.com/fwlink/p/?linkid=2024339)Setup  >  **ausführen.** Von hier aus können Sie E-Mails und Kontakte von einem anderen E-Mail-Dienst migrieren, die Domäne Ihres Administratorkontos ändern, Ihre Abrechnungsinformationen verwalten, Benutzer hinzufügen oder entfernen, Kennwörter zurücksetzen und andere Geschäftsfunktionen ausführen. Weitere Informationen zu den Unterschieden zwischen dem Setup-Assistenten und der Seite **Setup** finden Sie unter Unterschiede zwischen dem [Microsoft 365-Setup-Assistenten](o365-setup-wizard-and-setup-page.md)und der Setupseite .

Wenn Sie an einer Stelle nicht weiterkommen, rufen Sie uns an. [Wir helfen Ihnen gerne!](../contact-support-for-business-products.md)
  
## <a name="when-not-to-use-the-setup-wizard-active-directory-synchronization-and-hybrid-environments"></a>Wann der Setup-Assistent nicht verwendet werden sollte Active Directory-Synchronisierung und Hybridumgebungen

Es gibt einige Szenarien, die entweder das Migrieren von Daten oder Benutzern aus lokalen Umgebungen oder das Einrichten eines Hybridsystems umfassen, das die Verzeichnissynchronisierung umfasst. Wenn Sie in einer der beiden Kategorien sind, befolgen Sie die Anweisungen in den folgenden Artikeln:
  
- Informationen zum Einrichten der Verzeichnissynchronisierung mit Ihrem lokalen Active Directory finden Sie unter Einrichten der Verzeichnissynchronisierung für [Microsoft 365,](../../enterprise/set-up-directory-synchronization.md)und Informationen zu den verschiedenen Identitätsmodellen in Microsoft 365 finden Sie unter [Understanding Microsoft 365 identity and Azure Active Directory](../../enterprise/about-microsoft-365-identity.md).

- Die vollständigen Anweisungen zum Einrichten einer Exchange-Hybridbereitstellung, die Sie durch alle verschiedenen Möglichkeiten zum Einrichten einer Exchange-Hybridbereitstellung führen (einschließlich der Einrichtung von DNS-Einträgen) finden Sie hier: [Bereitstellungs-Assistent für Exchange Server](/exchange/exchange-deployment-assistant)

- Informationen zum Einrichten einer SharePoint-Hybridbereitstellung, insbesondere zum Einrichten der Hybridsuche und von Websitefunktionen finden Sie unter [Hybridsuche in SharePoint](/SharePoint/hybrid/hybrid-search-in-sharepoint).

## <a name="move-to-microsoft-365-all-at-once-or-in-stages"></a>Wechseln zu Microsoft 365 alle gleichzeitig oder in Phasen

- **Möchten Sie Ihre Organisation auf einmal zu Microsoft 365 verschieben?** Wenn ja, planen Sie, Ihre Domäne sofort zu Microsoft 365 zu verschieben. Starten Sie mit dem Microsoft 365-Setup-Assistenten. Sie werden aufgefordert, Ihre Domäne zu einrichten.

- **Möchten Sie schrittweise zu Microsoft 365 wechseln?** Wenn Sie phasenweise zu Microsoft 365 wechseln möchten, überspringen Sie die Ausführung des Microsoft 365-Setup-Assistenten, und erwägen Sie, Microsoft 365-Features in der folgenden Reihenfolge zu übernehmen:

    1. [Fügen Sie Ihre Mitarbeiter zu Microsoft 365 hinzu,](../add-users/add-users.md) damit sie die Office-Apps herunterladen und installieren können.

    2. [Laden Sie die Office-Apps herunter, und installieren Sie sie](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658), um Word, Excel und PowerPoint auf Ihrem Computer und Ihren Geräten zu verwenden.

    3. [Richten Sie Microsoft Teams für](#plan-for-teams) Ihre Besprechungen ein.

    4. [Verschieben Sie Ihre Inhalte in den Microsoft 365-Cloudspeicher](set-up-file-storage-and-sharing.md) (OneDrive- oder SharePoint-Teamwebsites).

    5. Wenn Sie bereit sind, wählen Sie  im [Admin Center](https://go.microsoft.com/fwlink/p/?linkid=2024339)im linken Navigationsbereich Setup aus, und verwenden Sie die Seite **Setup,** um Ihre Domäne und [E-Mail zu verschieben.](add-domain.md)

## <a name="check-that-your-devices-meet-system-requirements"></a>Überprüfen Sie, ob Ihre Geräte die Systemanforderungen erfüllen

Jede Person in Ihrer Organisation kann die Office 2016-Suite von Apps (Word, Excel, PowerPoint und so weiter) auf bis zu fünf PCs und Macs installieren. Weitere Informationen finden Sie unter den Betriebssystem- und Computeranforderungen für die Installation von [Office 2016-Suiten](https://go.microsoft.com/fwlink/?LinkId=534827) für Unternehmen.
  
Mobile Apps können auf iOS-, Android- und Windows-Geräten installiert werden. Informationen zur Unterstützung mobiler Geräte und zur Browserunterstützung finden Sie unter den [Systemanforderungen für Office](https://go.microsoft.com/fwlink/?LinkId=534827).
  
## <a name="plan-for-email"></a>Planung von E-Mail

Wenn Sie planen, von einem vorhandenen E-Mail-Dienst zu Microsoft 365 zu wechseln, dauert es in der Regel zwei Tage, bis sie wechseln.
  
### <a name="plan-for-email-downtime"></a>Planen von E-Mail-Ausfallzeiten
  
Wenn Sie Microsoft 365 für Ihre E-Mail verwenden möchten:
  
- Um Ihre geschäftliche E-Mail-Adresse (z. B. *rob \@ contoso.com*) von einem anderen E-Mail-Dienst zu Microsoft 365 zu verschieben, müssen Sie Ihre E-Mails an Ihr neues Microsoft 365-Postfach senden. Wählen Sie dazu **auf** der Seite **Setup** die Option Migrieren der Benutzerdaten aus, auf der wir Sie Schritt für Schritt durch die Updates führen, die Sie auf Ihrem Domänenhost ausführen müssen.

- Nach der Aktualisierung des Domänenhosts wird die Änderung normalerweise innerhalb von nur ein bis zwei Stunden wirksam. Beachten Sie jedoch, dass es manchmal bis zu 72 Stunden dauern kann, bis die Änderungen über das Internet aktualisiert werden.

- Da es zu E-Mail-Ausfallzeiten kommen kann, wird empfohlen, dass Sie an einem Abend oder Wochenende zu Microsoft-E-Mails wechseln, wenn Sie weniger E-Mails erhalten.

### <a name="plan-to-move-your-existing-email-contacts-and-calendar"></a>Planen der Verschiebung von vorhandenen E-Mails, Kontakten und Kalendern
  
Wenn Sie Microsoft 365 für Ihr E-Mail-Konto verwenden möchten, können Sie Ihre vorhandenen E-Mails, Kontakte und Kalender mitbringen. Auf **der Seite Setup** können Sie Ihre vorhandenen E-Mails und Kontakte für die meisten Szenarien verschieben. Wir bieten außerdem schrittweise Anleitungen für das Verschieben einzelner oder vieler Postfächer.
  
|**Wie viele Postfächer?**|**Empfehlung**|
|:-----|:-----|
|Nur einige  <br/> |Wenn Sie die Setupseite  nicht zum Migrieren der Postfächer verwenden möchten, können Sie Postfachbesitzern die Migration ihrer eigenen E-Mails und Kontakte gestatten. Weitere [Informationen finden Sie unter Migrieren von E-Mails und Kontakten zu Microsoft 365 Business](migrate-email-and-contacts-admin.md).  <br/> |
|Mehrere  <br/> |Wenn Sie von Gmail migrieren, lesen Sie Migrieren von [G Suite-Postfächern zu Microsoft 365](/Exchange/mailbox-migration/migrating-imap-mailboxes/migrate-g-suite-mailboxes).  <br/> Wenn Sie von einem anderen E-Mail-Anbieter, einschließlich Exchange, migrieren, lesen Sie Methoden zum Migrieren mehrerer E-Mail-Konten [zu Microsoft 365](/Exchange/mailbox-migration/mailbox-migration).  <br/> |

## <a name="plan-for-file-storage-and-migration"></a>Planen von Dateispeicherung und -migration

Microsoft 365 bietet Cloudspeicher für Einzelpersonen, kleine Organisationen und Unternehmen. Anleitungen dazu, was wo gespeichert werden soll, finden Sie unter [Where you can store documents in Microsoft 365](https://support.microsoft.com/office/c7c20284-bc94-47f4-9728-d28e9daf0790).
  
- **Sie können Hunderte von Dateien zu** [OneDrive oder](https://support.microsoft.com/office/45114744-6D42-45CD-8975-F9617819BDEB) zu einer [SharePoint-Teamwebsite verschieben.](https://support.microsoft.com/office/da549fb1-1fcb-4167-87d0-4693e93cb7a0#__toc384119242) Dabei können jeweils 100 Dateien zugleich hochgeladen werden. Laden Sie keine Dateien mit mehr als 2 GB hoch (dies ist standardmäßig die maximale Dateigröße).
  
- **Wenn Sie mehrere tausend Dateien in** Microsoft 365-Speicher verschieben möchten, lesen Sie die [SharePoint Online-Beschränkungen.](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits) Wir empfehlen die Verwendung eines Migrationstools oder die Verpflichtung eines [Partners](https://go.microsoft.com/fwlink/?linkid=391089) zu Ihrer Unterstützung bei der Migration. Informationen zum Migrieren einer noch größeren Anzahl von Dateien finden Sie unter [SharePoint Online und OneDrive-Migrationsbenutzerhandbuch](/sharepointmigration/upload-on-premises-content-to-sharepoint-online-using-powershell-cmdlets).
  
## <a name="plan-for-teams"></a>Planen von Teams

Sie können Microsoft Teams verwenden, um Anrufe an andere Personen in Ihrer Organisation zu senden, die sich in Ihrem Abonnement befinden. Wenn Ihre Organisation z. B. über 10 Personen verfügt, können Sie sich über Teams ohne spezielles Setup gegenseitig anrufen und anrufen. Weitere Informationen finden Sie unter [Erste Schritte mit Microsoft Teams](/MicrosoftTeams/get-started-with-teams-quick-start).

Für größere Organisationen oder wenn Sie mit Skype for Business, lokalen oder Hybridbereitstellungen beginnen, finden Sie weitere Informationen unter [Rollout von Microsoft Teams](/MicrosoftTeams/how-to-roll-out-teams).
  
## <a name="plan-for-integration-with-active-directory-or-other-software"></a>Planen der Integration mit Active Directory oder sonstiger Software

- **Wünschen Sie eine Integration mit Ihrem lokalen Active Directory?** Sie können Ihr lokales Active Directory mithilfe von Azure Active Directory Connect in Microsoft 365 integrieren. Anweisungen finden Sie unter [Einrichten der Verzeichnissynchronisierung für Microsoft 365](../../enterprise/set-up-directory-synchronization.md).
  
- **Möchten Sie Microsoft 365 in Software anderer Unternehmen integrieren?** Wenn Sie Microsoft 365 in andere Software in Ihrer [](https://go.microsoft.com/fwlink/?linkid=391089) Organisation integrieren müssen, empfehlen wir Ihnen, einen Partner zu stellen, der Ihnen bei Ihrer Bereitstellung hilft.
  
## <a name="do-you-want-someone-to-help-you-set-up-microsoft-365"></a>Möchten Sie, dass Ihnen jemand bei der Einrichtung von Microsoft 365 hilft?

- **Wenn Sie weniger als 50 Mitarbeiter beschäftigen:**

  - **Bitten Sie um Hilfe, und wir rufen Sie an.** Nachdem Sie Microsoft 365 gekauft haben, können Sie auf das Admin Center zugreifen (Sie müssen setup nicht ausführen, um zu diesem Zutritt zu kommen). Wählen Sie unten im Admin Center Hilfe **benötigen aus.** Beschreiben Sie Ihr Problem, und wir rufen Sie auf. 
  - **Rufen [Sie den Microsoft 365 Business Support mit](../contact-support-for-business-products.md) Ihren Fragen an.** We're here to help! 
  - **Erwägen Sie das Hinzuziehen eines [Microsoft-Partners](https://go.microsoft.com/fwlink/?linkid=391089)**. Wenn Sie wenig Zeit haben oder über erweiterte Anforderungen verfügen (z. B. Tausende von Dateien in Microsoft 365-Cloudspeicher verschieben oder in andere Software integrieren), kann ein erfahrener Partner eine große Hilfe sein. 

- **Wenn Sie mehr als 50 Mitarbeiter beschäftigen**, steht das [FastTrack Onboarding Center](https://go.microsoft.com/fwlink/?LinkId=517115) bereit, um Sie bei Ihrer Bereitstellung zu unterstützen.