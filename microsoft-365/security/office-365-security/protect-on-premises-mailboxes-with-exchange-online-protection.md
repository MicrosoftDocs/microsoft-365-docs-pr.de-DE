---
title: Schützen von lokalen Postfächern in China mit eigenständigen EoP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
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
description: Administratoren in China mit Office 365, die von 21Vianet betrieben werden, erfahren, wie Sie eigenständige Exchange Online Protection (EoP) verwenden, um Ihre lokalen Postfächer zu schützen.
ms.openlocfilehash: 6ce85e626f9bf4c960de57ad5cd15ac3148954cb
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208294"
---
# <a name="protect-on-premises-mailboxes-in-china-with-standalone-eop"></a>Schützen von lokalen Postfächern in China mit eigenständigen EoP

> [!NOTE]
> Dieser Artikel bezieht sich nur auf Office 365, die von 21Vianet in China betrieben werden.

Selbst wenn Sie planen, einige oder alle ihre Postfächer lokal zu hosten, können Sie die Postfächer dennoch mit Exchange Online Schutz schützen (EoP). Zum Konfigurieren von Connectors muss Ihr Konto ein globaler Administrator oder ein Exchange-Unternehmens Administrator (die Rollengruppe "Organisationsverwaltung") sein. Informationen dazu, wie sich Office 365 Berechtigungen auf Exchange-Berechtigungen beziehen, finden Sie unter [Zuweisen von Administratorrollen in Office 365 betrieben von 21Vianet](https://docs.microsoft.com/office365/admin/add-users/assign-admin-roles?&view=o365-21vianet). Wenn alle Exchange-Postfächer lokal sind, führen Sie die folgenden Schritte aus, um den EoP-Dienst einzurichten.

## <a name="step-1-use-the-microsoft-365-admin-center-to-add-and-verify-your-domain"></a>Schritt 1: Verwenden des Microsoft 365 Admin Center zum Hinzufügen und Überprüfen Ihrer Domäne

1. Navigieren Sie im Microsoft 365 Admin Center zu Setup, um Ihre Domäne dem Dienst hinzuzufügen.

2. Führen Sie die Schritte im Portal aus, um dem DNS-Hosting-Anbieter die entsprechenden DNS-Einträge hinzuzufügen, um den Domänenbesitz zu überprüfen.

> [!TIP]
> [Fügen Sie Ihre Domäne und Benutzer Office 365 betrieben von 21Vianet hinzu](https://docs.microsoft.com/office365/admin/setup/add-domain?&view=o365-21vianet) , und [Erstellen Sie DNS-Einträge für Office 365 beim Verwalten Ihrer DNS-Einträge](https://docs.microsoft.com/office365/admin/services-in-china/create-dns-records-when-you-manage-your-dns-records?&view=o365-21vianet) sind hilfreiche Ressourcen, die Sie beim Hinzufügen Ihrer Domäne zum Dienst und beim Konfigurieren von DNS referenzieren.

### <a name="step-2-add-recipients-and-configure-the-domain-type"></a>Schritt 2: Hinzufügen von Empfängern und Konfigurieren des Domänentyps

Bevor Sie die Übermittlung Ihrer E-Mails zum und vom EOP-Dienst konfigurieren, empfehlen wir, Ihre Empfänger zum Dienst hinzuzufügen. Es gibt dazu verschiedene Möglichkeiten, die in [Verwalten von E-Mail-Benutzern in EOP](manage-mail-users-in-eop.md) dokumentiert sind. Wenn Sie verzeichnisbasierte Edge-Blockierung (Directory Based Edge Blocking, DBEB) aktivieren möchten, um im Dienst eine Empfängerprüfung zu erzwingen, nachdem Sie Ihre Empfänger hinzugefügt haben, müssen Sie den Domänentyp außerdem auf "Autorisierend" festlegen. Weitere Informationen zu Blockierung finden Sie unter [Verwenden der verzeichnisbasierten Edge-Blockierung zum ablehnen von Nachrichten, die an ungültige Empfänger gesendet](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking)werden.

## <a name="step-3-use-the-eac-to-set-up-mail-flow"></a>Schritt 3: Einrichten des Nachrichtenflusses mithilfe der Exchange-Verwaltungskonsole

Erstellen Sie in der Exchange-Verwaltungskonsole (EAC) Connectors, die den Nachrichtenfluss zwischen EOP und Ihren lokalen E-Mail-Servern ermöglichen. Ausführliche Anweisungen finden Sie unter [Configure Mail Flow using Connectors in Office 365](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).

 Woher wissen Sie, dass diese Aufgabe erfolgreich war?

 Weitere Informationen finden Sie unter [Testen des Nachrichtenflusses durch Validieren der Office 365-Konnektoren](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow).

## <a name="step-4-allow-inbound-port-25-smtp-access"></a>Schritt 4: Zulassen eingehender SMTP-Verbindungen an Port 25

Nachdem Sie Connectors konfiguriert haben, sollten Sie 72 Stunden warten, bis Ihre DNS-Datensatzaktualisierungen weitergegeben wurden. Danach können Sie den eingehenden Port-25-SMTP-Datenverkehr auf Ihrer Firewall oder Ihren e-Mail-Servern so einschränken, dass nur e-Mails von den EoP-Rechenzentren akzeptiert werden, insbesondere von den IP-Adressen, die unter [URLs und IP-Adressbereichen für Office 365](https://docs.microsoft.com/office365/enterprise/managing-office-365-endpoints)aufgeführt sind. So schützen Sie Ihre lokale Umgebung, indem Sie den Bereich eingehender Nachrichten einschränken, die Sie empfangen können. Wenn Ihr E-Mail-Server Einstellungen aufweist, welche die IP-Adressen steuern, die für E-Mail-Relay eine Verbindung herstellen dürfen, sollten Sie zusätzlich diese Einstellungen aktualisieren.

> [!TIP]
> Konfigurieren Sie Einstellungen auf dem SMTP-Server mit einem Verbindungstimeout von 60 Sekunden. Diese Einstellung ist in den meisten Fällen sinnvoll, da sie eine gewisse Verzögerung erlaubt, falls z. B. eine Nachricht mit einem großen Anhang gesendet wird.

## <a name="step-5-ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a>Schritt 5: sicherstellen, dass Spam an den Junk-e-Mail-Ordner der einzelnen Benutzer weitergeleitet wird

Sie müssen eine Reihe von Konfigurationsschritten ausführen, um wirklich sicherzustellen, dass Junk-E-Mail (Spam) in die Junk-E-Mail-Ordner der Benutzer umgeleitet werden. Die Schritte werden in [Konfigurieren von eigenständigen EoP zur Zustellung von Spam an den Junk-e-Mail-Ordner in Hybrid Umgebungen](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)bereitgestellt. Wenn Sie keine Nachrichten in den Junk-e-Mail-Ordner der einzelnen Benutzer übertragen möchten, können Sie eine andere Aktion auswählen, indem Sie Ihre Anti-Spam-Richtlinien (auch bekannt als Inhaltsfilter-Richtlinien) bearbeiten. Weitere Informationen finden Sie unter [Konfigurieren von Anti-Spam-Richtlinien in Office 365](configure-your-spam-filter-policies.md).

## <a name="step-6-use-the-microsoft-365-admin-center-to-point-your-mx-record-to-eop"></a>Schritt 6: Verwenden des Microsoft 365 Admin Center zum Verweisen Ihres MX-Eintrags auf EoP

Befolgen Sie die Konfigurationsschritte für Office 365-Domänen, um den MX-Eintrag für die Domäne zu aktualisieren, damit Ihre eingehenden E-Mails über EOP weitergeleitet werden. Weitere Informationen finden Sie erneut [Erstellen von DNS-Einträgen für Office 365, wenn Sie Ihre DNS-Einträge verwalten](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).

Woher wissen Sie, dass diese Aufgabe erfolgreich war?

 Weitere Informationen finden Sie unter [Testen des Nachrichtenflusses durch Validieren der Office 365-Konnektoren](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow).

Zu diesem Zeitpunkt haben Sie die Dienstübermittlung für einen ordnungsgemäß konfigurierten Ausgang auf dem lokalen Connector geprüft und sichergestellt, dass Ihr MX-Eintrag auf EOP verwiesen wurde. Sie können nun zusätzlich die folgenden Tests ausführen, um sicherzustellen, dass der Dienst eine E-Mail erfolgreich an Ihre lokale Umgebung versendet hat:

- Klicken Sie in der Remoteverbindungsuntersuchung auf die Registerkarte **Office 365**, führen Sie anschließend den **Eingehende SMTP-E-Mail**-Test unter **Internet E-Mail-Tests** aus.

- Senden Sie von einem webbasierten E-Mail-Konto eine E-Mail an einen E-Mail-Empfänger in Ihrer Organisation, dessen Domäne der Domäne entspricht, die Sie dem Dienst hinzugefügt haben. Bestätigen Sie mithilfe von Microsoft Outlook oder einem anderen E-Mail-Client die Zustellung der Nachricht an das lokale Postfach.

- Wenn Sie einen Test für ausgehende E-Mails durchführen möchten, können Sie von einem Benutzer in Ihrer Organisation aus eine E-Mail an ein webbasiertes E-Mail-Konto senden und überprüfen, ob die Nachricht übermittelt wurde.

## <a name="less-common-a-hybrid-setup-with-mailboxes-on-premises-and-in-the-cloud"></a>Seltener: ein Hybrid-Setup mit lokalen und in der Cloud bereitgestellten Postfächern

Wenn Sie lokale Exchange-Postfächer und mindestens ein Postfach in der Cloud in Exchange Online haben, haben Sie ein *hybrides* Setup. In einem hybriden Setup arbeiten Features wie frei/gebucht-Kalenderfreigabe und e-Mail-Routing in Ihren lokalen und Cloud-Umgebungen zusammen. Möglicherweise haben Sie ein hybrides Setup eingerichtet, während Sie Postfächer zu Exchange Online wechseln. Eine Hybridumgebung ist anders als EoP eigenständiger Schutz eingerichtet.

Sie können ein Hybrid Szenario auswählen, um Cloud-basierte e-Mails für die meisten ihrer Mitarbeiter zu nutzen. Sie können dies tun, während Sie auch einige Postfächer lokal hosten; beispielsweise für Ihre Rechtsabteilung.

Ein hybrides Setup kann komplex sein, bietet aber viele Vorteile. Weitere Informationen zum Einrichten von Hybrid Szenarien mit Exchange finden Sie unter [Exchange Server hybridbereitstellungen](https://docs.microsoft.com/Exchange/exchange-hybrid).
