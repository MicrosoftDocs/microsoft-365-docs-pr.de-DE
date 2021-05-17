---
title: Schützen von lokalen Postfächern in China mit EOP als eigenständige Lösung
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- GEU150
- GMA150
- GPA150
- MET150
ms.assetid: c5e95951-da67-4ec7-92c5-982abd477e69
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Administratoren in China, die Office 365 21Vianet verwenden, können erfahren, wie Sie eigenständige Exchange Online Protection (EOP) verwenden, um ihre lokalen Postfächer zu schützen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4258d64721fc2042297bb15eaeecafa90dcf4bc1
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206674"
---
# <a name="protect-on-premises-mailboxes-in-china-with-standalone-eop"></a>Schützen von lokalen Postfächern in China mit EOP als eigenständige Lösung

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> Dieser Artikel gilt nur für Office 365, die von 21Vianet in China betrieben werden.

Auch wenn Sie planen, einige oder alle Postfächer lokal zu hosten, können Sie die Postfächer dennoch mit Exchange Online Protection (EOP) schützen. Zum Konfigurieren von Connectors muss Ihr Konto ein globaler Administrator oder ein Exchange (die Rollengruppe Organisationsverwaltung) sein. Informationen dazu, wie Office 365 Berechtigungen Exchange Berechtigungen beziehen, finden Sie unter [Assigning admin roles in Office 365 operated by 21Vianet](../../admin/add-users/assign-admin-roles.md?preserve-view=true&view=o365-21vianet). Wenn alle Ihre Exchange lokal sind, führen Sie die folgenden Schritte aus, um Ihren EOP-Dienst zu einrichten.

## <a name="step-1-use-the-microsoft-365-admin-center-to-add-and-verify-your-domain"></a>Schritt 1: Verwenden Microsoft 365 Admin Center zum Hinzufügen und Überprüfen Ihrer Domäne

1. Navigieren Sie Microsoft 365 Admin Center zu Setup, um Ihre Domäne dem Dienst hinzuzufügen.

2. Führen Sie die Schritte im Portal aus, um die entsprechenden DNS-Einträge zu Ihrem DNS-Hostinganbieter hinzuzufügen, um den Domänenbesitz zu überprüfen.

> [!TIP]
> Fügen Sie Ihre Domäne und Ihre Benutzer zu Office 365 betrieben von [21Vianet](../../admin/setup/add-domain.md?preserve-view=true&view=o365-21vianet) hinzu, und erstellen Sie DNS-Einträge für Office 365 wenn Sie Ihre [DNS-Einträge](../../admin/services-in-china/create-dns-records-when-you-manage-your-dns-records.md?preserve-view=true&view=o365-21vianet) verwalten, sind hilfreiche Ressourcen, auf die Verwiesen werden kann, wenn Sie Ihre Domäne zum Dienst hinzufügen und DNS konfigurieren.

### <a name="step-2-add-recipients-and-configure-the-domain-type"></a>Schritt 2: Hinzufügen von Empfängern und Konfigurieren des Domänentyps

Bevor Sie die Übermittlung Ihrer E-Mails zum und vom EOP-Dienst konfigurieren, empfehlen wir, Ihre Empfänger zum Dienst hinzuzufügen. Es gibt dazu verschiedene Möglichkeiten, die in [Verwalten von E-Mail-Benutzern in EOP](manage-mail-users-in-eop.md) dokumentiert sind. Wenn Sie verzeichnisbasierte Edge-Blockierung (Directory Based Edge Blocking, DBEB) aktivieren möchten, um im Dienst eine Empfängerprüfung zu erzwingen, nachdem Sie Ihre Empfänger hinzugefügt haben, müssen Sie den Domänentyp außerdem auf "Autorisierend" festlegen. Weitere Informationen zu DBEB finden Sie unter [Use Directory Based Edge Blocking to reject messages sent to invalid recipients](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking).

## <a name="step-3-use-the-eac-to-set-up-mail-flow"></a>Schritt 3: Einrichten des Nachrichtenflusses mithilfe der Exchange-Verwaltungskonsole

Erstellen Sie in der Exchange-Verwaltungskonsole (EAC) Connectors, die den Nachrichtenfluss zwischen EOP und Ihren lokalen E-Mail-Servern ermöglichen. Ausführliche Anweisungen finden Sie unter [Configure mail flow using connectors in Office 365](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).

 Woher wissen Sie, dass diese Aufgabe erfolgreich war?

 Weitere [Informationen finden Sie unter Test mail flow by validating your Office 365 connectors](/exchange/mail-flow-best-practices/test-mail-flow).

## <a name="step-4-allow-inbound-port-25-smtp-access"></a>Schritt 4: Zulassen eingehender SMTP-Verbindungen an Port 25

Nachdem Sie Connectors konfiguriert haben, sollten Sie 72 Stunden warten, bis Ihre DNS-Datensatzaktualisierungen weitergegeben wurden. Beschränken Sie anschließend den eingehenden Port-25-SMTP-Datenverkehr auf Ihrer Firewall oder Ihren E-Mail-Servern, um E-Mails nur von den EOP-Rechenzentren zu akzeptieren, insbesondere von den UNTER [URLs](../../enterprise/managing-office-365-endpoints.md)und IP-Adressbereichen für Office 365 . So schützen Sie Ihre lokale Umgebung, indem Sie den Bereich eingehender Nachrichten einschränken, die Sie empfangen können. Wenn Ihr E-Mail-Server Einstellungen aufweist, welche die IP-Adressen steuern, die für E-Mail-Relay eine Verbindung herstellen dürfen, sollten Sie zusätzlich diese Einstellungen aktualisieren.

> [!TIP]
> Konfigurieren Sie Einstellungen auf dem SMTP-Server mit einem Verbindungstimeout von 60 Sekunden. Diese Einstellung ist in den meisten Fällen sinnvoll, da sie eine gewisse Verzögerung erlaubt, falls z. B. eine Nachricht mit einem großen Anhang gesendet wird.

## <a name="step-5-ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a>Schritt 5: Sicherstellen, dass Spam an den Junk-E-Mail-Ordner jedes Benutzers geroutet wird

Sie müssen eine Reihe von Konfigurationsschritten ausführen, um wirklich sicherzustellen, dass Junk-E-Mail (Spam) in die Junk-E-Mail-Ordner der Benutzer umgeleitet werden. Die Schritte finden Sie unter [Configure standalone EOP to deliver spam to the Junk Email folder in hybrid environments](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md). Wenn Sie Nachrichten nicht in den Junk-E-Mail-Ordner der einzelnen Benutzer verschieben möchten, können Sie eine andere Aktion auswählen, indem Sie Ihre Antispamrichtlinien bearbeiten (auch als Inhaltsfilterrichtlinien bekannt). Weitere Informationen finden Sie unter [Konfigurieren von Anti-Spam-Richtlinien in Office 365](configure-your-spam-filter-policies.md).

## <a name="step-6-use-the-microsoft-365-admin-center-to-point-your-mx-record-to-eop"></a>Schritt 6: Verwenden Microsoft 365 Admin Center, um Ihren MX-Eintrag auf EOP zu verweisen

Befolgen Sie die Konfigurationsschritte für Office 365-Domänen, um den MX-Eintrag für die Domäne zu aktualisieren, damit Ihre eingehenden E-Mails über EOP weitergeleitet werden. Weitere Informationen finden Sie unter Create DNS records for Office 365, wenn [Sie Ihre DNS-Einträge verwalten.](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md?preserve-view=true&view=o365-21vianet)

Woher wissen Sie, dass diese Aufgabe erfolgreich war?

 Weitere [Informationen finden Sie unter Test mail flow by validating your Office 365 connectors](/exchange/mail-flow-best-practices/test-mail-flow).

Zu diesem Zeitpunkt haben Sie die Dienstübermittlung für einen ordnungsgemäß konfigurierten Ausgang auf dem lokalen Connector geprüft und sichergestellt, dass Ihr MX-Eintrag auf EOP verwiesen wurde. Sie können nun zusätzlich die folgenden Tests ausführen, um sicherzustellen, dass der Dienst eine E-Mail erfolgreich an Ihre lokale Umgebung versendet hat:

- Klicken Sie in der Remoteverbindungsuntersuchung auf die Registerkarte **Office 365**, führen Sie anschließend den **Eingehende SMTP-E-Mail**-Test unter **Internet E-Mail-Tests** aus.

- Senden Sie von einem webbasierten E-Mail-Konto eine E-Mail an einen E-Mail-Empfänger in Ihrer Organisation, dessen Domäne der Domäne entspricht, die Sie dem Dienst hinzugefügt haben. Bestätigen Sie mithilfe von Microsoft Outlook oder einem anderen E-Mail-Client die Zustellung der Nachricht an das lokale Postfach.

- Wenn Sie einen Test für ausgehende E-Mails durchführen möchten, können Sie von einem Benutzer in Ihrer Organisation aus eine E-Mail an ein webbasiertes E-Mail-Konto senden und überprüfen, ob die Nachricht übermittelt wurde.

## <a name="less-common-a-hybrid-setup-with-mailboxes-on-premises-and-in-the-cloud"></a>Weniger häufig: Hybrideinrichtung mit lokalen Postfächern und in der Cloud

Wenn Sie Exchange lokalen Postfächern und einem oder mehreren Postfächern in der Cloud in Exchange Online, verfügen Sie über eine *Hybrideinrichtung.* In einer Hybrideinrichtung arbeiten Features wie frei/gebucht-Kalenderfreigabe und E-Mail-Routing in Ihren lokalen und Cloudumgebungen zusammen. Möglicherweise haben Sie eine Hybrideinrichtung eingerichtet, während Sie Postfächer in eine Exchange Online. Eine Hybridumgebung ist anders als der eigenständige EOP-Schutz eingerichtet.

Sie können ein Hybridszenario auswählen, um cloudbasierte E-Mails für die meisten Ihrer Mitarbeiter zu nutzen. Sie können dies tun und gleichzeitig einige Postfächer lokal hosten. z. B. für Ihre Rechtsabteilung.

Eine Hybrideinrichtung kann komplex sein, hat aber viele Vorteile. Weitere Informationen zum Einrichten von Hybridszenarien mit Exchange finden Sie [unter Exchange Server Hybridbereitstellungen](/Exchange/exchange-hybrid).