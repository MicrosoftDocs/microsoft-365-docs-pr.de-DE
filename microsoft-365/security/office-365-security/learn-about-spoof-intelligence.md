---
title: Einblick in spoof intelligence
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 978c3173-3578-4286-aaf4-8a10951978bf
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Administratoren können mehr über den Einblick in spoof intelligence in Exchange Online Protection (EOP) erfahren.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 37c5bcb6f2c15c3814fafa198f2905e23b12ba01
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538747"
---
# <a name="spoof-intelligence-insight-in-eop"></a>Einblick in spoof intelligence in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> Die in diesem Artikel beschriebenen Features befinden sich in Vorschau, können geändert werden und sind nicht in allen Organisationen verfügbar. Wenn Ihre Organisation nicht über die in diesem Artikel beschriebenen Features verfügt, lesen Sie die ältere [Spoofverwaltungserfahrung unter Manage spoofed senders using the spoof intelligence policy and spoof intelligence insight in EOP](walkthrough-spoof-intelligence-insight.md).

In Microsoft 365 Organisationen mit Postfächern in Exchange Online oder eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online Postfächer werden eingehende E-Mail-Nachrichten automatisch vor Spoofing geschützt. EOP verwendet **Spoof Intelligence** als Teil der allgemeinen Verteidigung Ihrer Organisation gegen Phishing. Weitere Informationen finden Sie unter Schutz vor [Spoofing in EOP](anti-spoofing-protection.md).

Wenn ein Absender eine E-Mail-Adresse spooft, scheint er ein Benutzer in einer der Domänen Ihrer Organisation oder ein Benutzer in einer externen Domäne zu sein, die E-Mails an Ihre Organisation sendet. Angreifer, die Absender zum Senden von Spam- oder Phishing-E-Mails spoofen, müssen blockiert werden. Es gibt jedoch Szenarien, in denen legitime Absender Spoofing verwenden. Beispiel:

- Legitime Szenarien für das Spoofing interner Domänen:
  - Drittanbietersender verwenden Ihre Domäne, um Massen-E-Mails für Unternehmensumfragen an Ihre eigenen Mitarbeiter zu senden.
  - Ein externes Unternehmen generiert und sendet Werbe- oder Produktupdates in Ihrem Auftrag.
  - Ein Assistent muss regelmäßig E-Mails für eine andere Person in Ihrer Organisation senden.
  - Eine interne Anwendung sendet E-Mail-Benachrichtigungen.

- Legitime Szenarien für das Spoofing externer Domänen:
  - Der Absender befindet sich in einer Mailingliste (auch als Diskussionsliste bezeichnet), und die Mailingliste leitet E-Mails vom ursprünglichen Absender an alle Teilnehmer in der Mailingliste weiter.
  - Ein externes Unternehmen sendet E-Mails im Auftrag eines anderen Unternehmens (z. B. einen automatisierten Bericht oder ein Software-as-a-Service-Unternehmen).

Sie können den Einblick in **spoof** intelligence im Security & Compliance Center verwenden, um spoofierte Absender schnell zu identifizieren, die Ihnen legitimerweise nicht authentifizierte E-Mails senden (Nachrichten von Domänen, die keine SPF-, DKIM- oder DMARC-Prüfungen bestehen) und diese Absender manuell zulassen.

Indem Sie bekannten Absendern erlauben, gefälschte Nachrichten von bekannten Speicherorten zu senden, können Sie falsch positive Ergebnisse reduzieren (gute E-Mails sind als ungültig gekennzeichnet). Durch die Überwachung der zugelassenen gefälschten Absender bieten Sie eine zusätzliche Sicherheitsebene, um zu verhindern, dass unsichere Nachrichten in Ihrer Organisation ankommen.

Ebenso können Sie spoofierte Absender überprüfen, die durch Spoof intelligence zugelassen wurden, und diese Absender manuell von der Spoof Intelligence-Einsicht blockieren.

Im rest dieses Artikels wird erläutert, wie Sie den Einblick in spoof intelligence im Security & Compliance Center und in PowerShell (Exchange Online PowerShell für Microsoft 365-Organisationen mit Postfächern in Exchange Online; eigenständige EOP PowerShell für Organisationen ohne Exchange Online-Postfächer) verwenden.

> [!NOTE]
>
> - Nur spoofierte Absender, die von spoof intelligence erkannt wurden, werden in der Spoof Intelligence-Einsicht angezeigt. Wenn Sie das Zulassen oder Blockieren des Urteils in der Einsicht außer Kraft setzen, wird der gefälschte Absender zu einem manuellen Zulassen oder Blockieren eines Eintrags, der nur auf der Registerkarte **Spoof** in der Mandanten-Zulassen-/Sperrliste angezeigt wird. Sie können auch manuell Zulassen oder Blockieren von Einträgen für spoofierte Absender erstellen, bevor sie von Spoof Intelligence erkannt werden. Weitere Informationen finden Sie [unter Manage the Tenant Allow/Block List in EOP](tenant-allow-block-list.md).
>
> - Der Einblick in spoof intelligence und die Registerkarte **Spoof** in der Liste Mandanten zulassen/blockieren ersetzen die Funktionalität der Spoof Intelligence-Richtlinie, die auf der Seite Antispamrichtlinie im Security & Compliance Center verfügbar war.
>
>- Der Einblick in spoof intelligence zeigt Daten im Wert von 7 Tagen an. Das **Cmdlet Get-SpoofIntelligenceInsight** zeigt Daten im Wert von 30 Tagen an.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>. Um direkt zur Seite **"Antiphishing" zu** wechseln, verwenden Sie <https://protection.office.com/antiphishing> .

- Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell). Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Sie müssen in **Exchange Online** Berechtigungen erhalten, bevor Sie die in diesem Artikel beschriebenen Schritte ausführen können:
  - Um die Spoof Intelligence-Richtlinie zu ändern oder Spoof Intelligence zu  aktivieren oder zu deaktivieren, müssen Sie Mitglied der Rollengruppen Organisationsverwaltung oder **Sicherheitsadministrator** sein.
  - Für den schreibgeschützten Zugriff auf die Spoof Intelligence-Richtlinie müssen Sie Mitglied der Rollengruppen **"Globaler Leser"** oder **"Sicherheitsleser"** sein.

  Weitere Informationen finden Sie unter [Berechtigungen in Exchange Online](/exchange/permissions-exo/permissions-exo).

  **Hinweise**:

  - Durch Hinzufügen von Benutzern zur entsprechenden Azure Active Directory-Rolle im Microsoft 365 Admin Center erhalten Benutzer die erforderlichen Berechtigungen _und_ Berechtigungen für andere Features in Microsoft 365. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).
  - Die Rollengruppe **Organisationsverwaltung mit Leserechten** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) ermöglicht auch einen schreibgeschützten Zugriff auf das Feature.

- Sie aktivieren und deaktivieren Spoof Intelligence in Antiphishingrichtlinien in EOP und Microsoft Defender für Office 365. Spoof intelligence ist standardmäßig aktiviert. Weitere Informationen finden Sie unter [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md) oder [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).

- Unsere empfohlenen Einstellungen für spoof intelligence finden Sie unter [EOP default anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).

## <a name="open-the-spoof-intelligence-insight-in-the-security--compliance-center"></a>Öffnen Sie den Einblick in spoof intelligence im Security & Compliance Center

1. Wechseln Sie im Security & Compliance Center zu Richtlinie für die **Bedrohungsverwaltung** \>  \> **Antiphishing**.

2. Auf der **Hauptseite antiphishing** hat der Einblick in spoof intelligence zwei Modi:

   - **Einblicksmodus:** Wenn Spoofintelligenz aktiviert ist, zeigt die Einblicke, wie viele Nachrichten in den letzten sieben Tagen durch Spoofintelligenz erkannt wurden.
   - **Was wäre,** wenn Der Modus : Wenn die Spoofintelligenz deaktiviert ist, zeigt die Einsicht, wie viele Nachrichten in den letzten sieben Tagen durch Spoofintelligenz erkannt worden wären. 

   So oder so sind die spoofierten Domänen, die in der Einsicht angezeigt werden, in zwei Kategorien unterteilt: Verdächtige **Domänen** und **Nicht verdächtige Domänen.**

   - **Verdächtige** Domänen sind:

     - Hochsicherer Spoof: Basierend auf den historischen Sendemustern und der Reputationsnote der Domänen sind wir sehr sicher, dass die Domänen Spoofing sind, und Nachrichten von diesen Domänen sind mit hoher Wahrscheinlichkeit bösartig.

     - Moderater Konfidenzs spoof: Basierend auf historischen Sendemustern und der Reputationsnote der Domänen sind wir moderat davon überzeugt, dass die Domänen Spoofing sind und dass nachrichten, die von diesen Domänen gesendet werden, legitim sind. Falsch positive Ergebnisse sind in dieser Kategorie wahrscheinlicher als spoof mit hoher Wahrscheinlichkeit.

   **Nicht verdächtige Domänen:** Die explizite E-Mail-Authentifizierung der Domäne hat [SPF,](how-office-365-uses-spf-to-prevent-spoofing.md) [DKIM](use-dkim-to-validate-outbound-email.md)und [DMARC nicht überprüft.](use-dmarc-to-validate-email.md) Die Domäne hat jedoch unsere impliziten E-Mail-Authentifizierungsprüfungen ([zusammengesetzte Authentifizierung](email-validation-and-authentication.md#composite-authentication)) bestanden. Aus diesem Grund wurde keine Antis spoofing-Aktion für die Nachricht ergriffen.

### <a name="view-information-about-spoofed-messages"></a>Anzeigen von Informationen zu gefälschten Nachrichten

Klicken Sie auf der Spionintelligenz auf Verdächtige **Domänen** oder nicht verdächtige **Domänen,** um zur **Seite Spoof Intelligence Insight zu** wechseln. Die Seite enthält die folgenden Informationen:

- **Spoofed domain:** Die Domäne des spoofierten Benutzers, die im Feld **Von** in E-Mail-Clients angezeigt wird. Diese Adresse wird auch als Adresse `5322.From` bezeichnet.
- **Infrastruktur**: Wird auch als sendende _Infrastruktur bezeichnet._ Dies ist einer der folgenden Werte:
  - Die Domäne in einer Reverse-DNS-Suche (PTR-Eintrag) der IP-Adresse des Quell-E-Mail-Servers.
  - Wenn die Quell-IP-Adresse keinen PTR-Eintrag enthält, wird die sendende Infrastruktur als \<source IP\> /24 identifiziert (z. B. 192.168.100.100/24).
- **Nachrichtenanzahl**: Die Anzahl der Nachrichten aus der  Kombination der spoofierten Domäne und der sendenden Infrastruktur an Ihre Organisation innerhalb der letzten 7 Tage.
- **Zuletzt gesehen:** Das letzte Datum, an dem eine Nachricht von der sendenden Infrastruktur empfangen wurde, die die spoofierte Domäne enthält.
- **Spooftyp**: Einer der folgenden Werte:
  - **Intern:** Der gefälschte Absender befindet sich in einer Domäne, die zu Ihrer Organisation gehört (eine [akzeptierte Domäne](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)).
  - **Extern:** Der gefälschte Absender befindet sich in einer externen Domäne.
- **Spoofing** zulässig: Der Wert hängt  davon ab, ob Sie auf Verdächtige Domänen oder **nicht verdächtige** Domänen geklickt haben:
  - **Verdächtige** Domänen: Der **Wert "Zugelassen zum Spoofen"** ist immer **Nein**. Nachrichten aus der Kombination aus spoofed _domain_ und sending infrastructure werden durch Spoof Intelligence als schlecht gekennzeichnet. Die Aktion, die für die gefälschten Nachrichten ergriffen wird, wird durch die standardmäßige Antiphishingrichtlinie oder benutzerdefinierte Antiphishingrichtlinien gesteuert (der Standardwert ist **Move message to Junk Email folder**). Weitere Informationen finden Sie unter [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).
  - **Nicht verdächtige Domänen:** Der **Wert für das Spoofen** ist immer **Ja**. Nachrichten aus der Kombination aus spoofed domain _und_ sending infrastructure werden durch Spoof Intelligence als gut gekennzeichnet.

Sie können auf ausgewählte Spaltenüberschriften klicken, um die Ergebnisse zu sortieren.

Zum Filtern der Ergebnisse haben Sie die folgenden Optionen:

- Verwenden Sie **das Feld Spoofingdomäne filtern,** um eine durch Kommas getrennte Liste mit spoofierten Domänenwerten ein eingeben, um die Ergebnisse zu filtern.
- Verwenden Sie **das Feld Infrastruktur filtern,** um eine durch Kommas getrennte Liste von Infrastrukturwerten ein, um die Ergebnisse zu filtern.
- Klicken Sie auf die Schaltfläche **Filter,** um die Ergebnisse nach **Spooftyp zu filtern.**

### <a name="view-details-about-spoofed-messages"></a>Anzeigen von Details zu gefälschten Nachrichten

Wählen Sie ein Element in der Liste aus, um Details anzuzeigen. Ein Flyout wird mit den folgenden Informationen und Features angezeigt:

- **Spoofing zulässig:** Verwenden Sie diese Umschalte, um das Spoof intelligence-Urteil außer Kraft zu setzen:
  - Wenn Sie ursprünglich **verdächtige Domänen** in der Einsicht ausgewählt haben, ist **Spoofing** zugelassen deaktiviert. Um ihn zu aktivieren, der den Eintrag aus dem Einblick in spoof intelligence in die Mandanten-Zulassen-/Sperrliste als zulässigen Eintrag für Spoofs verschiebt, verschieben Sie den Umschalter auf ein: ![ Umschalten auf ](../../media/scc-toggle-on.png) .
  - Wenn Sie ursprünglich **nicht verdächtige Domänen** in der Einsicht ausgewählt haben, ist **Spoofing** zugelassen aktiviert. Um es zu deaktivieren, wodurch der Eintrag aus dem Einblick in die Spionintelligenz in die Mandanten zulassen/Blockieren-Liste als Blockeintrag für Spoofs bewegt wird, verschieben Sie den Umschalter zu deaktivieren: ![ Umschalten aus ](../../media/scc-toggle-off.png) .

- Warum wir dies erwischt haben.
- Was Sie tun müssen.
- Eine Domänenzusammenfassung, die die meisten der gleichen Informationen von der Hauptseite für spoof intelligence enthält.
- WhoIs-Daten über den Absender.
- Ähnliche Nachrichten, die wir in Ihrem Mandanten vom gleichen Absender gesehen haben.

### <a name="about-allowed-spoofed-senders"></a>Informationen zu zugelassenen spoofierten Absendern

Ein zugelassener gefälschter Absender **in** nicht verdächtigen Domänen in der Einblick in spoof intelligence oder ein blockierter Absender **in**  verdächtigen Domänen, den Sie manuell in **Spoofing** geändert haben, erlaubt nur Nachrichten aus der Kombination aus der spoofierten Domäne und der sendenden Infrastruktur. Es lässt weder E-Mails von der spoofierten Domäne von einer Quelle noch E-Mails von der sendenden Infrastruktur für eine Beliebige Domäne zu.

Der folgende gefälschte Absender darf z. B. spoofen:

- **Domäne**: gmail.com
- **Infrastruktur**: tms.mx.com

Nur E-Mails von diesem Domänen-/Sendeinfrastrukturpaar dürfen spoofen. Andere Absender, die versuchen, gmail.com zu spoofen, sind nicht automatisch zulässig. Nachrichten von Absendern in anderen Domänen, die von tms.mx.com stammen, werden weiterhin durch Spoof Intelligence überprüft und können blockiert werden.

## <a name="use-the-spoof-intelligence-insight-in-exchange-online-powershell-or-standalone-eop-powershell"></a>Verwenden der Einblicke in spoof intelligence in Exchange Online PowerShell oder eigenständiger EOP PowerShell

In PowerShell verwenden Sie das **Cmdlet Get-SpoofIntelligenceInsight,** um zugelassene und blockierte spoofierte Absender zu anzeigen, die von Spoof Intelligence erkannt wurden.  Zum manuellen Zulassen oder Blockieren der gefälschten Absender müssen Sie das **Cmdlet New-TenantAllowBlockListSpoofItems** verwenden. Weitere Informationen finden Sie unter [Use PowerShell to configure the Tenant Allow/Block List](tenant-allow-block-list.md#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list).

Führen Sie den folgenden Befehl aus, um die Informationen in der Spoof Intelligence-Einsicht anzeigen zu können:

```powershell
Get-SpoofIntelligenceInsight
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-SpoofIntelligenceInsight](/powershell/module/exchange/get-spoofintelligenceinsight).

## <a name="other-ways-to-manage-spoofing-and-phishing"></a>Weitere Möglichkeiten zum Verwalten von Spoofing und Phishing

Sind Sie sorgfältig beim Thema Spoofing und Phishingschutz. Hier finden Sie verwandte Möglichkeiten, um Absender zu überprüfen, die Ihre Domäne spoofieren, und sie daran zu hindern, Ihre Organisation zu beschädigen:

- Überprüfen Sie **den Spoof-E-Mail-Bericht**. Sie können diesen Bericht häufig zum Anzeigen und Verwalten gefälschter Absender verwenden. Weitere Informationen finden Sie unter [Spoof Detections report](view-email-security-reports.md#spoof-detections-report).

- Überprüfen Sie die Konfiguration des Sender Policy Framework (SPF). Eine kurze Einführung in SPF und seine schnelle Konfiguration finden Sie unter [Einrichten von SPF in Microsoft 365 zur Verhinderung von Spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md). Ausführlichere Informationen zur Verwendung von SPF durch Office 365 oder zur Problembehandlung oder zu nicht standardmäßigen Bereitstellungen, z. B. Hybridbereitstellungen, finden Sie unter [How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md).

- Überprüfen Sie Die Konfiguration von "DomainKeys Identified Mail" (DKIM). Sie sollten DKIM zusätzlich zu SPF und DMARC verwenden, um zu verhindern, dass Angreifer Nachrichten senden, die so aussehen, als würden sie von Ihrer Domäne kommen. Mit DKIM können Sie E-Mail-Nachrichten in der Kopfzeile der Nachricht eine digitale Signatur hinzufügen. Weitere Informationen finden Sie unter [Use DKIM to validate outbound email sent from your custom domain in Office 365](use-dkim-to-validate-outbound-email.md).

- Überprüfen Sie Die Domänenbasierte Nachrichtenauthentifizierung, -berichterstellung und -konformität (DMARC). Die Implementierung von DMARC zusammen mit SPF und DKIM bietet zusätzlichen Schutz vor Spoofing- und Phishing-E-Mails. DMARC unterstützt die E-Mail-Systeme der Empfänger bei der Behandlung von Nachrichten, die von Ihrer Domäne gesendet wurden, jedoch die SPF- oder DKIM-Prüfungen nicht bestanden haben. Weitere Informationen finden Sie unter [Use DMARC to validate email in Office 365](use-dmarc-to-validate-email.md).
