---
title: Planen des Setups von Office 365 für Unternehmen
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- MET150
- MOE150
ms.assetid: eb926624-018b-4486-bf11-5fba6ee4d645
description: Erfahren Sie, was Sie tun müssen, um Ihre Office 365 für Unternehmen einzurichten.
ms.openlocfilehash: 3b38f0092b323175c6a12170105e781fab21934d
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42243922"
---
# <a name="plan-your-setup-of-office-365-for-business"></a>Planen des Setups von Office 365 für Unternehmen

Dieser Artikel ist für Personen bestimmt, die einen Office 365 Business-Plan abonniert haben.
  
Es gibt ein paar Dinge, die Sie entscheiden müssen, und Informationen, die Sie zur Hand haben müssen, bevor Sie Ihre Organisation nach Office 365 verschieben.
  
## <a name="info-to-have-on-hand-before-you-run-the-office-365-setup-wizard"></a>Diese Informationen müssen Sie vor dem Ausführen des Office 365-Setup-Assistenten griffbereit haben

Wenn Sie bereit sind, den Office 365-Setup-Assistenten auszuführen und Ihre Domäne auf Office 365 umzustellen, müssen diese Informationen verfügbar sein:
  
- Die Liste der Personen, die Office 365 hinzugefügt werden sollen. Auch, wenn Sie diese Personen bereits zu Office 365 hinzugefügt haben, wenn Sie Ihre Domäneninformationen aktualisieren, müssen Sie ihre Namen hier eingeben.

- Das Verfahren, mit dem Sie Ihren Mitarbeitern ihre Office 365-Benutzer-ID und das Kennwort mitteilen, damit sie sich anmelden können. Möchten Sie ihnen die Informationen telefonisch mitteilen? Oder sie an ihre private E-Mail-Adresse senden? Auf die Office 365-E-Mail besteht noch kein Zugriff, daher können Sie diese Option nicht verwenden.

- Wenn Sie über einen Domänennamen für Ihre Organisation (beispielsweise contoso.com) verfügen **und** die Verwendung von Office 365 e-Mail planen, müssen Sie wissen, wo Ihre Domäne registriert ist und über Anmeldeinformationen verfügt.

## <a name="what-happens-when-you-run-the-office-365-setup-wizard"></a>Was passiert, wenn Sie den Office 365-Setup-Assistenten ausführen?

Der Setup-Assistent führt Sie durch die Installation der Office 365-apps auf Ihrem Computer, hinzufügen und Überprüfen Ihrer Domäne, Hinzufügen von Benutzern und Zuweisen von Lizenzen und verbinden Ihrer Domäne.

> [!NOTE]
> Wenn Sie den Benutzern, die Sie im Assistenten hinzufügen, [Administratorrollen in Office 365 für Unternehmen zuweisen](../add-users/assign-admin-roles.md) müssen, können Sie dies später auf der Seite **Benutzer** tun. 
  
Wenn Sie den Setup-Assistenten nicht abschließen, können Sie Setupaufgaben jederzeit über das**Setup**von [Admin Center](https://go.microsoft.com/fwlink/p/?linkid=2024339) > ausführen. Von hier aus können Sie e-Mails und Kontakte aus einem anderen e-Mail-Dienst migrieren, die Domäne Ihres Administratorkontos ändern, Ihre Abrechnungsinformationen verwalten, Benutzer hinzufügen oder entfernen, Kennwörter zurücksetzen und andere Geschäftsfunktionen ausführen. Weitere Informationen zu den Unterschieden zwischen dem Setup-Assistenten und der Seite **Setup** finden Sie unter [Differences of the Office 365 Setup Wizard and the Setup Page](o365-setup-wizard-and-setup-page.md).

Wenn Sie an einer Stelle nicht weiterkommen, rufen Sie uns an. [Wir helfen Ihnen gerne!](../contact-support-for-business-products.md)
  
## <a name="when-not-to-use-the-setup-wizard-active-directory-synchronization-and-hybrid-environments"></a>Wann der Setup-Assistent nicht verwendet werden sollte Active Directory-Synchronisierung und Hybridumgebungen

Es gibt eine Reihe von Szenarien, die entweder das Migrieren von Daten oder Benutzern aus lokalen Umgebungen oder das Einrichten eines Hybridsystems umfassen, das die Verzeichnissynchronisierung umfasst. Wenn Sie sich in einer der beiden Kategorien befinden, befolgen Sie die Anweisungen in den folgenden Artikeln:
  
- Informationen zum Einrichten der Verzeichnissynchronisierung mit dem lokalen Active Directory finden Sie unter [Einrichten der Verzeichnissynchronisierung in Office 365](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization) und Informationen zum Verstehen der verschiedenen Identitätsmodelle in Office 365 finden Sie unter [Grundlegendes zu Office 365-Identitäten und Azure Active Directory](https://docs.microsoft.com/office365/enterprise/about-office-365-identity).

- Die vollständigen Anweisungen zum Einrichten einer Exchange-Hybridbereitstellung, die Sie durch alle verschiedenen Möglichkeiten zum Einrichten einer Exchange-Hybridbereitstellung führen (einschließlich der Einrichtung von DNS-Einträgen) finden Sie hier: [Bereitstellungs-Assistent für Exchange Server](https://aka.ms/exdeploy)

- Informationen zum Einrichten einer SharePoint-Hybridbereitstellung, insbesondere zum Einrichten der Hybridsuche und von Websitefunktionen finden Sie unter [Hybridsuche in SharePoint](https://docs.microsoft.com/SharePoint/hybrid/hybrid-search-in-sharepoint).

## <a name="move-to-office-365-all-at-once-or-in-stages"></a>In Office 365 alle gleichzeitig oder in Phasen umsteigen

- **Möchten Sie Ihre Organisation auf einmal in Office 365 umsetzen?** In diesem Fall sollten Sie planen, Ihre Domäne gleich zu Anfang auf Office 365 umzustellen. Beginnen Sie, indem Sie den Office 365-Setup-Assistenten ausführen; er fordert Sie zur Einrichtung Ihrer Domäne auf.

- **Möchten Sie nach und nach Office 365 umsteigen?** Wenn Sie in Phasen auf Office 365 umstellen möchten, überspringen Sie die Ausführung des Office 365-Setup-Assistenten, und erwägen Sie, die Office 365-Funktionen in der folgenden Reihenfolge zu übernehmen:

    1. [Fügen Sie Ihre Mitarbeiter zu Office 365 hinzu](../add-users/add-users.md) , damit sie die Office-Apps herunterladen und installieren können.

    2. [Laden Sie die Office-Apps herunter, und installieren Sie sie](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658.aspx), um Word, Excel und PowerPoint auf Ihrem Computer und Ihren Geräten zu verwenden.

    3. [Richten Sie Microsoft Teams](#plan-for-teams) ein, die für Ihre Besprechungen verwendet werden sollen.

    4. [Migrieren Sie Ihre Inhalte in Office 365 cloudspeicher](set-up-file-storage-and-sharing.md) (OneDrive oder SharePoint-Teamwebsites).

    5. Wenn Sie fertig sind, wählen Sie im [Admin Center](https://go.microsoft.com/fwlink/p/?linkid=2024339)im linken Navigationsbereich die Option **Setup** aus, und verwenden Sie die Seite **Setup** , um [Ihre Domäne und e-Mail zu migrieren](add-domain.md).

## <a name="check-that-your-devices-meet-system-requirements"></a>Überprüfen Sie, ob Ihre Geräte die Systemanforderungen erfüllen

Jede Person in Ihrer Organisation kann die Office 2016 Suite von apps (Word, Excel, PowerPoint usw.) auf bis zu fünf PCs und Macs installieren. Weitere Informationen finden Sie unter den Betriebssystem- und Computeranforderungen für die Installation von [Office 2016-Suiten](https://go.microsoft.com/fwlink/?LinkId=534827) für Unternehmen.
  
Mobile Apps können auf Ios-, Android-und Windows-Geräten installiert werden. Informationen zur Unterstützung mobiler Geräte und zur Browserunterstützung finden Sie unter den [Systemanforderungen für Office](https://go.microsoft.com/fwlink/?LinkId=534827).
  
## <a name="plan-for-email"></a>Planung von E-Mail

Wenn Sie planen, von einem vorhandenen e-Mail-Dienst zu Office 365 zu wechseln, dauert es in der Regel zwei Tage, um den Switch zu erstellen.
  
### <a name="plan-for-email-downtime"></a>Planen von E-Mail-Ausfallzeiten
  
Wenn Sie Office 365 für Ihre E-Mail verwenden möchten:
  
- Um Ihre geschäftliche e-Mail-Adresse (beispielsweise *Rob@contoso.com*) aus einem anderen e-Mail-Dienst in Office 365 zu übertragen, müssen Sie die Zustellung Ihrer e-Mails an das neue Office 365 Postfach weiterleiten. Dazu wählen Sie auf der Seite **Setup** die Option **die Daten der Benutzer migrieren** aus, wo wir Sie Schritt für Schritt durch die Updates führen, die Sie auf Ihrem Domänenhost vornehmen müssen.

- Nach der Aktualisierung des Domänenhosts wird die Änderung normalerweise innerhalb von nur ein bis zwei Stunden wirksam. Beachten Sie jedoch, dass es manchmal bis zu 72 Stunden dauern kann, bis die Änderungen über das Internet aktualisiert werden.

- Da auf diese Weise Ausfallzeiten bei der E-Mail auftreten können, empfehlen wir Ihnen, die Umstellung der E-Mail auf Office 365 an einem Abend oder Wochenende zu planen, wenn Sie weniger E-Mails empfangen.

### <a name="plan-to-move-your-existing-email-contacts-and-calendar"></a>Planen der Verschiebung von vorhandenen E-Mails, Kontakten und Kalendern
  
Wenn Sie Office 365 für Ihr E-Mail-Konto verwenden, können Sie Ihre vorhandenen E-Mails, Kontakte und Kalender mitnehmen. Auf der Seite **Setup** können Sie Ihre vorhandenen e-Mails und Kontakte für die meisten Szenarien migrieren. Wir bieten außerdem schrittweise Anleitungen für das Verschieben einzelner oder vieler Postfächer.
  
|**Wie viele Postfächer?**|**Empfehlung**|
|:-----|:-----|
|Nur einige  <br/> |Wenn Sie die Postfächer nicht mithilfe der **Setup** -Seite migrieren möchten, können Postfachbesitzer ihre eigenen e-Mails und Kontakte migrieren lassen. Weitere Informationen finden Sie unter [Migrieren von E-Mails und Kontakten zu Office 365 Business](migrate-email-and-contacts-admin.md)  <br/> |
|Mehrere  <br/> |Wenn Sie von Gmail migrieren, lesen Sie [Migrieren von G Suite-Postfächern zu Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/migrating-imap-mailboxes/migrate-g-suite-mailboxes).  <br/> Wenn Sie von einem anderen e-Mail-Anbieter migrieren, einschließlich Exchange, finden Sie unter [Ways to migrate Multiple e-Mail Accounts to Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration).  <br/> |

## <a name="plan-for-file-storage-and-migration"></a>Planen von Dateispeicherung und -migration

Office 365 bietet cloudspeicher für Einzelpersonen, kleine Organisationen und Unternehmen. Anleitungen dazu, was Sie wo speichern sollten, finden Sie unter [Speicherorte für Dokumente in Office 365](https://support.office.com/article/c7c20284-bc94-47f4-9728-d28e9daf0790.aspx).
  
- **Sie können Hunderte von Dateien** in [OneDrive](https://support.office.com/article/45114744-6D42-45CD-8975-F9617819BDEB.aspx) oder eine [SharePoint-Teamwebsite](https://support.office.com/article/da549fb1-1fcb-4167-87d0-4693e93cb7a0.aspx#__toc384119242)migrieren. Dabei können jeweils 100 Dateien zugleich hochgeladen werden. Laden Sie keine Dateien mit mehr als 2 GB hoch (dies ist standardmäßig die maximale Dateigröße).
  
- **Wenn Sie mehrere Tausend Dateien in den Office 365-Speicher verschieben möchten**, überprüfen Sie die [SharePoint Online-Grenzwerte](https://go.microsoft.com/fwlink/p/?LinkID=856113). Wir empfehlen die Verwendung eines Migrationstools oder die Verpflichtung eines [Partners](https://go.microsoft.com/fwlink/?linkid=391089) zu Ihrer Unterstützung bei der Migration. Informationen zum Migrieren einer noch größeren Anzahl von Dateien finden Sie unter [SharePoint Online und OneDrive-Migrationsbenutzerhandbuch](https://go.microsoft.com/fwlink/?LinkId=723574).
  
## <a name="plan-for-teams"></a>Planen von Teams

Sie können Microsoft Teams verwenden, um Anrufe an andere Personen in Ihrer Organisation zu tätigen, die sich in Ihrem Abonnement befinden. Wenn Ihre Organisation beispielsweise über 10 Mitarbeiter verfügt, können Sie mit Microsoft Teams ohne spezielles Setup miteinander chatten und sich gegenseitig aufrufen. Weitere Informationen finden Sie unter [Erste Schritte mit Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/get-started-with-teams-quick-start).

Informationen zu größeren Organisationen oder wenn Sie mit Skype for Business, lokalen oder hybridbereitstellungen beginnen, finden Sie unter [How to Roll Out Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/how-to-roll-out-teams).
  
## <a name="plan-for-integration-with-active-directory-or-other-software"></a>Planen der Integration mit Active Directory oder sonstiger Software

- **Wünschen Sie eine Integration mit Ihrem lokalen Active Directory?** Sie können Ihr lokales Active Directory mithilfe von Azure Active Directory Connect mit Office 365 integrieren. Anweisungen finden Sie unter [Einrichten der Verzeichnissynchronisierung in Office 365](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization).
  
- **Möchten Sie Office 365 mit Software von anderen Unternehmen integrieren?** Wenn Sie Office 365 mit anderer Software in Ihrer Organisation integrieren müssen, empfehlen wir Ihnen, [einen Partner](https://go.microsoft.com/fwlink/?linkid=391089) zur Unterstützung Ihrer Bereitstellung zu mieten.
  
## <a name="do-you-want-someone-to-help-you-set-up-office-365"></a>Möchten Sie sich von jemand beim Einrichten von Office 365 helfen lassen?

- **Wenn Sie weniger als 50 Mitarbeiter beschäftigen:**

  - **Fragen Sie nach Hilfe, und wir rufen Sie an**. Nachdem Sie Office 365 erworben haben, können Sie auf das Admin Center zugreifen (Sie müssen Setup nicht ausführen, um es zu erhalten). Wählen Sie unten im Admin Center die Option **Hilfe benötigen?** Beschreiben Sie Ihr Problem, und wir werden Sie anrufen. 
  - **Rufen Sie [Office 365 for Business Support](../contact-support-for-business-products.md) mit Ihren Fragen**an. We're here to help! 
  - **Erwägen Sie das Hinzuziehen eines [Microsoft-Partners](https://go.microsoft.com/fwlink/?linkid=391089)**. Wenn Sie wenig Zeit oder erweiterte Anforderungen haben (wie etwa das Verschieben Tausender Dateien in den Office 365-Cloudspeicher oder die Integration mit anderer Software), kann ein erfahrener Partner eine große Hilfe sein. 

- **Wenn Sie mehr als 50 Mitarbeiter beschäftigen**, steht das [FastTrack Onboarding Center](https://go.microsoft.com/fwlink/?LinkId=517115) bereit, um Sie bei Ihrer Bereitstellung zu unterstützen. 
