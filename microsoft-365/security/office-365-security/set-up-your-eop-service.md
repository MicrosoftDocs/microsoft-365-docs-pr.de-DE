---
title: Einrichten des eigenständigen EOP-Diensts
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.custom:
- seo-marvel-apr2020
localization_priority: Normal
ms.assetid: d74c6ddf-11b0-43ee-b298-8bb0340895f0
description: Administratoren erfahren, wie Sie eigenständige Exchange Online Protection (EOP) zum Schutz von lokalen E-Mail-Umgebungen einrichten.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: bbad39475f87be27a83edc0c27e2bbe46f8e39ac
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206831"
---
# <a name="set-up-your-standalone-eop-service"></a>Einrichten des eigenständigen EOP-Diensts

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
-  [Exchange Online Protection eigenständig](exchange-online-protection-overview.md)

In diesem Thema wird erläutert, wie Sie eigenständige Exchange Online Protection (EOP) einrichten. Wenn Sie vom Office 365-Assistenten für Domänen hierher geführt wurden, wechseln Sie zurück zum Office 365-Assistenten für Domänen, wenn Sie Exchange Online Protection nicht verwenden möchten. Wenn Sie weitere Informationen zum Konfigurieren von Connectors suchen, finden Sie diese unter [Configure mail flow using connectors in Office 365](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).

> [!NOTE]
> In diesem Thema wird davon ausgegangen, dass lokale Postfächer verwendet werden, die mit EOP geschützt werden sollen - dies wird als eigenständiges Szenario bezeichnet. Wenn Sie alle Postfächer in der Cloud mit Exchange Online hosten möchten, müssen Sie nicht alle Schritte in diesem Artikel ausführen. Wechseln Sie [zu Compare Exchange Online plans](https://products.office.com/exchange/compare-microsoft-exchange-online-plans) to sign up and purchase cloud mailboxes.
>
> Wenn Sie die Postfächer teils lokal und teils in der Cloud hosten möchten, handelt es sich um ein hybrides Szenario. Für ein solches Szenario sind erweiterte Nachrichtenflusseinstellungen erforderlich. [Exchange Server Hybridbereitstellungen](/exchange/exchange-hybrid) erläutert den Hybrid-E-Mail-Fluss und enthält Links zu Ressourcen, die zeigen, wie sie eingerichtet werden.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Geschätzte Zeit bis zum Abschließen dieser Aufgabe: 1 Stunde

- Bevor Sie die Verfahren in diesem Artikel Exchange Online Protection, müssen Ihnen die entsprechenden Berechtigungen zugewiesen werden. Insbesondere benötigen Sie die **Rolle Remote-** und akzeptierte Domänen, die standardmäßig den Rollengruppen **Organisationsverwaltung** **(globale** Administratoren) und Mail Flow Administrator zugewiesen ist. Weitere Informationen finden Sie unter [Permissions in standalone EOP](feature-permissions-in-eop.md) und [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).

- Wenn Sie sich noch nicht bei EOP registriert haben, rufen Sie [Exchange Online Protection](https://products.office.com/exchange/exchange-email-security-spam-protection) auf, und erwerben oder testen Sie den Dienst.

- Informationen zu Tastenkombinationen, die für die Verfahren in diesem Artikel gelten können, finden Sie unter Tastenkombinationen für das [Exchange Admin Center in Exchange Online](/Exchange/accessibility/keyboard-shortcuts-in-admin-center).

> [!TIP]
> Liegt ein Problem vor? Bitten Sie im [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE)-Forum um Hilfe.

## <a name="step-1-use-the-microsoft-365-admin-center-to-add-and-verify-your-domain"></a>Schritt 1: Verwenden Microsoft 365 Admin Center zum Hinzufügen und Überprüfen Ihrer Domäne

1. Wechseln Sie [Microsoft 365 Admin Center](../../admin/admin-overview/about-the-admin-center.md)zu **Setup,** um Ihre Domäne dem Dienst hinzuzufügen.

2. Befolgen Sie die Schritte, um Ihrem DNS-Hostinganbieter die entsprechenden DNS-Datensätze hinzuzufügen, um die Domäneneigentümerschaft zu überprüfen.

> [!TIP]
> [Hinzufügen einer Domäne zu Office 365](../../admin/setup/add-domain.md) und Erstellen von DNS-Einträgen bei einem beliebigen DNS-Hostinganbieter für [Office 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md) sind hilfreiche Ressourcen, auf die Verwiesen werden kann, wenn Sie Ihre Domäne zum Dienst hinzufügen und DNS konfigurieren.

## <a name="step-2-add-recipients-and-optionally-enable-dbeb"></a>Schritt 2: Hinzufügen von Empfängern und optionales Aktivieren der verzeichnisbasierten Edge-Blockierung (DBEB)

Bevor Sie die Übermittlung Ihrer E-Mails zum und vom EOP-Dienst konfigurieren, empfehlen wir, Ihre Empfänger zum Dienst hinzuzufügen. Es gibt dazu verschiedene Möglichkeiten, die in [Verwalten von E-Mail-Benutzern in EOP](manage-mail-users-in-eop.md) dokumentiert sind. Wenn Sie verzeichnisbasierte Edge-Blockierung (Directory Based Edge Blocking, DBEB) aktivieren möchten, um im Dienst eine Empfängerprüfung zu erzwingen, nachdem Sie Ihre Empfänger hinzugefügt haben, müssen Sie den Domänentyp außerdem auf "Autorisierend" festlegen. Weitere Informationen zur verzeichnisbasierten Edge-Blockierung finden Sie unter [Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking).

## <a name="step-3-use-the-eac-to-set-up-mail-flow"></a>Schritt 3: Einrichten des Nachrichtenflusses mithilfe der Exchange-Verwaltungskonsole

Erstellen Sie in der Exchange-Verwaltungskonsole (EAC) Connectors, die den Nachrichtenfluss zwischen EOP und Ihren lokalen E-Mail-Servern ermöglichen. Ausführliche Anweisungen finden Sie unter [Set up connectors to route mail between Microsoft 365 and your own email servers](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail).

### <a name="how-do-you-know-this-task-worked"></a>Woher wissen Sie, dass diese Aufgabe erfolgreich war?

Überprüfen sie den Nachrichtenfluss zwischen dem Dienst und Ihrer Umgebung. Weitere Informationen finden Sie unter [Test mail flow by validating your Microsoft 365 connectors](/exchange/mail-flow-best-practices/test-mail-flow).

## <a name="step-4-allow-inbound-port-25-smtp-access"></a>Schritt 4: Zulassen eingehender SMTP-Verbindungen an Port 25

Warten Sie nach dem Konfigurieren von Connectors 72 Stunden, um die Verteilung Ihrer DNS-Eintragsupdates zu ermöglichen. Schränken Sie anschließend in Ihrer Firewall oder auf Ihren E-Mail-Servern den eingehenden SMTP-Datenverkehr für Port 25 so ein, dass nur E-Mails von EOP-Rechenzentren, genauer gesagt von den unter [Exchange Online Protection-IP-Adressen](../../enterprise/urls-and-ip-address-ranges.md) aufgeführten IP-Adressen, zugelassen werden. So schützen Sie Ihre lokale Umgebung, indem Sie den Bereich eingehender Nachrichten einschränken, die Sie empfangen können. Wenn Ihr E-Mail-Server Einstellungen aufweist, welche die IP-Adressen steuern, die für E-Mail-Relay eine Verbindung herstellen dürfen, sollten Sie zusätzlich diese Einstellungen aktualisieren.

> [!TIP]
> Konfigurieren Sie Einstellungen auf dem SMTP-Server mit einem Verbindungstimeout von 60 Sekunden. Diese Einstellung ist für die meisten Situationen akzeptabel, sodass z. B. bei einer Nachricht, die mit einer großen Anlage gesendet wird, eine gewisse Verzögerung möglich ist.

## <a name="step-5-ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a>Schritt 5: Sicherstellen, dass Spam an den Junk-E-Mail-Ordner jedes Benutzers geroutet wird

Sie müssen eine Reihe von Konfigurationsschritten ausführen, um wirklich sicherzustellen, dass Junk-E-Mail (Spam) in die Junk-E-Mail-Ordner der Benutzer umgeleitet werden. Die Schritte finden Sie unter [Configure standalone EOP to deliver spam to the Junk Email folder in hybrid environments](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).

Wenn Sie Nachrichten nicht in den Junk-E-Mail-Ordner jedes Benutzers verschieben möchten, können Sie eine andere Aktion auswählen, indem Sie Ihre Antispamrichtlinien bearbeiten. Weitere Informationen finden Sie unter [Konfigurieren von Anti-Spam-Richtlinien in Office 365](configure-your-spam-filter-policies.md).

## <a name="step-6-use-the-microsoft-365-admin-center-to-point-your-mx-record-to-eop"></a>Schritt 6: Verwenden Microsoft 365 Admin Center, um Ihren MX-Eintrag auf EOP zu verweisen

Führen Sie die Domänenkonfigurationsschritte aus, um Ihren MX-Eintrag für Ihre Domäne zu aktualisieren, sodass Ihre eingehenden E-Mails über EOP fließen. Stellen Sie sicher, dass Ihr MX-Eintrag direkt auf EOP verweist, damit kein Filterungsdienstrelais eines Drittanbieters eine E-Mail an EOP schreibt. Weitere Informationen finden Sie auch hierzu unter [Erstellen von DNS-Einträgen für Office 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).

> [!NOTE]
> Wenn Sie Ihren MX-Eintrag auf einen anderen Server oder Dienst verweisen müssen, der sich vor EOP befindet, finden Sie weitere Informationen unter [Enhanced Filtering for Connectors in Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).

### <a name="how-do-you-know-this-task-worked"></a>Woher wissen Sie, dass diese Aufgabe erfolgreich war?

Zu diesem Zeitpunkt haben Sie die Dienstübermittlung für einen ordnungsgemäß konfigurierten Ausgang auf dem lokalen Connector geprüft und sichergestellt, dass Ihr MX-Eintrag auf EOP verwiesen wurde. Sie können nun zusätzlich die folgenden Tests ausführen, um sicherzustellen, dass der Dienst eine E-Mail erfolgreich an Ihre lokale Umgebung versendet hat:

- Überprüfen sie den Nachrichtenfluss zwischen dem Dienst und Ihrer Umgebung. Weitere Informationen finden Sie unter [Test mail flow by validating your Microsoft 365 connectors](/exchange/mail-flow-best-practices/test-mail-flow).

- Senden Sie von einem webbasierten E-Mail-Konto eine E-Mail an einen E-Mail-Empfänger in Ihrer Organisation, dessen Domäne der Domäne entspricht, die Sie dem Dienst hinzugefügt haben. Bestätigen Sie mithilfe von Microsoft Outlook oder einem anderen E-Mail-Client die Zustellung der Nachricht an das lokale Postfach.

- Wenn Sie einen Test für ausgehende E-Mails durchführen möchten, können Sie von einem Benutzer in Ihrer Organisation aus eine E-Mail an ein webbasiertes E-Mail-Konto senden und überprüfen, ob die Nachricht übermittelt wurde.

> [!TIP]
> Nachdem Sie das Setup abgeschlossen haben, müssen Sie nichts weiter tun, um EOP für das Entfernen von Spam und Malware zu konfigurieren. Spam und Malware werden von EOP automatisch entfernt. Sie können Ihre Einstellungen jedoch basierend auf Ihren Geschäftlichen Anforderungen optimieren. Weitere Informationen finden Sie unter [Antispam- und](anti-spam-and-anti-malware-protection.md) Schadsoftwareschutz in Office 365 und Konfigurieren von [Spoof Intelligence](learn-about-spoof-intelligence.md).
>
> Nachdem Ihr Dienst ausgeführt wird, empfehlen wir, bewährte Methoden zum Konfigurieren von [EOP](best-practices-for-configuring-eop.md)zu lesen, in dem empfohlene Einstellungen und Überlegungen für nach dem Einrichten von EOP beschrieben werden.