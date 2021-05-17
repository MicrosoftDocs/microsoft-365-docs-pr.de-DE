---
title: Wiederherstellen nach einem Ransomware-Angriff
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Microsoft 365 Administratoren können erfahren, wie Sie sich nach einem Ransomware-Angriff wiederherstellen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 242a4a2f43bd91d75caeaeaa0488f23a5ba4319d
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205762"
---
# <a name="recover-from-a-ransomware-attack-in-microsoft-365"></a>Wiederherstellen nach einem Ransomware-Angriff in Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Selbst wenn Sie alle Vorsichtsmaßnahmen ergreifen, um Ihre Organisation zu schützen, können Sie dennoch Opfer eines [Ransomware-Angriffs](/windows/security/threat-protection/intelligence/ransomware-malware) werden. Ransomware ist groß, und die Angriffe sind sehr ausgefeilt.

Die Schritte in diesem Artikel bieten Ihnen die beste Möglichkeit, Daten wiederhergestellt und die interne Ausbreitung der Infektion zu beenden. Bevor Sie beginnen, sollten Sie die folgenden Punkte beachten:

- Es gibt keine Garantie, dass die Zahlung des Lösegelds den Zugriff auf Ihre Dateien zurück gibt. Tatsächlich kann das Bezahlen des Lösegelds Sie zu einem Ziel für mehr Ransomware machen.

  Wenn Sie bereits bezahlt haben, aber ohne die Lösung des Angreifers wiederhergestellt haben, wenden Sie sich an Ihre Bank, um zu erfahren, ob sie die Transaktion blockieren kann.

  Es wird außerdem empfohlen, den Ransomware-Angriff wie weiter unten in diesem Artikel beschrieben an strafverfolgungs-, betrugsberichtswebsites und Microsoft zu melden.

- Es ist wichtig, dass Sie schnell auf den Angriff und seine Folgen reagieren. Je länger Sie warten, desto geringer ist die Wahrscheinlichkeit, dass Sie die betroffenen Daten wiederherstellen können.

## <a name="step-1-verify-your-backups"></a>Schritt 1: Überprüfen der Sicherungen

Wenn Sie über Offlinesicherungen verfügen,  können Sie die verschlüsselten Daten wahrscheinlich wiederherstellen, nachdem Sie die Ransomware-Nutzlast (Schadsoftware) aus Ihrer Umgebung entfernt haben.

Wenn Sie keine Sicherungen haben oder wenn Ihre Sicherungen auch von der Ransomware betroffen waren, können Sie diesen Schritt überspringen.

## <a name="step-2-disable-exchange-activesync-and-onedrive-sync"></a>Schritt 2: Deaktivieren Exchange ActiveSync und OneDrive Synchronisierung

Der wichtigste Punkt hier ist, die Verbreitung der Datenverschlüsselung durch die Ransomware zu beenden.

Wenn Sie E-Mails als Ziel der Ransomware-Verschlüsselung vermuten, deaktivieren Sie vorübergehend den Benutzerzugriff auf Postfächer. Exchange ActiveSync synchronisiert Daten zwischen Geräten und Exchange Online Postfächern.

Informationen zum Exchange ActiveSync für ein Postfach finden Sie unter Deaktivieren von Exchange ActiveSync für Benutzer [in Exchange Online](https://support.microsoft.com/help/2795303).

Informationen zum Deaktivieren anderer Arten von Zugriff auf ein Postfach finden Sie unter:

- [Aktivieren oder Deaktivieren von MAPI für ein Postfach](/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi).

- [Aktivieren oder Deaktivieren des POP3- oder IMAP4-Zugriffs für einen Benutzer](/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)

Das Anhalten OneDrive Synchronisierung schützt Ihre Clouddaten vor der Aktualisierung durch potenziell infizierte Geräte. Weitere Informationen finden Sie unter [How to Pause and Resume sync in OneDrive](https://support.microsoft.com/office/2152bfa4-a2a5-4d3a-ace8-92912fb4421e).

## <a name="step-3-remove-the-malware-from-the-affected-devices"></a>Schritt 3: Entfernen der Schadsoftware von den betroffenen Geräten

Führen Sie einen vollständigen, aktuellen Antivirenscan auf allen mutmaßlichen Computern und Geräten aus, um die Nutzlast zu erkennen und zu entfernen, die der Ransomware zugeordnet ist.

Vergessen Sie nicht, Geräte zu überprüfen, die Daten synchronisieren, oder die Ziele zugeordneter Netzwerklaufwerke.

Sie können [Windows Defender](https://www.microsoft.com/windows/comprehensive-security) oder (für ältere Clients) [Microsoft Security Essentials.](https://www.microsoft.com/download/details.aspx?id=5201)

Eine Alternative, die Sie auch dabei unterstützt, Ransomware oder Schadsoftware zu entfernen, ist das Tool zum Entfernen bösartiger [Software (Malicious Software Removal Tool, MSRT).](https://www.microsoft.com/download/details.aspx?id=9905)

Wenn diese Optionen nicht funktionieren, können Sie versuchen, Windows Defender [Offline](https://support.microsoft.com/help/17466) zu verwenden oder Probleme beim Erkennen und Entfernen [von Schadsoftware zu beheben.](https://support.microsoft.com/help/4466982)

## <a name="step-4-recover-files-on-a-cleaned-computer-or-device"></a>Schritt 4: Wiederherstellen von Dateien auf einem bereinigten Computer oder Gerät

Nachdem Sie den vorherigen Schritt zum Entfernen der Ransomware-Nutzlast aus Ihrer Umgebung abgeschlossen haben (was die Ransomware daran hindern wird, Ihre Dateien zu verschlüsseln oder zu entfernen), können Sie den Dateiverlauf [in](https://support.microsoft.com/help/17128) Windows 10 und Windows 8.1 oder System Protection in Windows 7 verwenden, um zu versuchen, Ihre lokalen Dateien und Ordner wiederhergestellt zu werden.

**Hinweise**:

- Einige Ransomware verschlüsselt oder löscht auch die Sicherungsversionen, sodass Sie Dateiverlauf oder Systemschutz nicht zum Wiederherstellen von Dateien verwenden können. In diesem Fall müssen Sie Sicherungen auf externen Laufwerken oder Geräten verwenden, die nicht von ransomware oder OneDrive wie im nächsten Abschnitt beschrieben.

- Wenn ein Ordner mit OneDrive synchronisiert wird und Sie nicht die neueste Version von Windows verwenden, gibt es möglicherweise einige Einschränkungen mit dem Dateiverlauf.

## <a name="step-5-recover-your-files-in-your-onedrive-for-business"></a>Schritt 5: Wiederherstellen ihrer Dateien in OneDrive for Business

Die Wiederherstellung von Dateien in OneDrive for Business ermöglicht es Ihnen, den gesamten OneDrive innerhalb der letzten 30 Tage auf einen früheren Zeitpunkt wiederherzustellen. Weitere Informationen finden Sie unter [Restore your OneDrive](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15).

## <a name="step-6-recover-deleted-email"></a>Schritt 6: Wiederherstellen gelöschter E-Mails

In dem seltenen Fall, dass die Ransomware alle Ihre E-Mails gelöscht hat, können Sie die gelöschten Elemente wahrscheinlich wiederherstellen. Weitere Informationen finden Sie unter:

- [Wiederherstellen von gelöschten Nachrichten im Postfach eines Benutzers](/exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages)

- [Wiederherstellen gelöschter Elemente in Outlook für Windows](https://support.microsoft.com/office/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce)

## <a name="step-7-re-enable-exchange-activesync-and-onedrive-sync"></a>Schritt 7: Erneutes Aktivieren Exchange ActiveSync und OneDrive Synchronisierung

Nachdem Sie Ihre Computer und Geräte bereinigt und Ihre Daten wiederhergestellt haben, können Sie die zuvor in Schritt 2 deaktivierte Exchange ActiveSync und OneDrive Synchronisierung erneut [aktivieren.](#step-2-disable-exchange-activesync-and-onedrive-sync)

## <a name="step-8-optional-block-onedrive-sync-for-specific-file-extensions"></a>Schritt 8 (Optional): Blockieren OneDrive Synchronisierung für bestimmte Dateierweiterungen

Nach der Wiederherstellung können Sie verhindern, dass OneDrive for Business Die Dateitypen synchronisiert werden, die von dieser Ransomware betroffen waren. Weitere Informationen finden Sie unter [Set-SPOTenantSyncClientRestriction](/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)

## <a name="report-the-attack"></a>Melden des Angriffs

### <a name="contact-law-enforcement"></a>Wenden Sie sich an die Strafverfolgungsbehörden

Sie sollten sich an Ihre lokalen oder Bundesbehörden wenden. Wenn Sie sich z. B. in den USA befinden, können Sie sich an das [lokale Feldbüro](https://www.fbi.gov/contact-us/field)des FBI, [IC3](http://www.ic3.gov/complaint/default.aspx) oder [den Secret Service wenden.](http://www.secretservice.gov/)

### <a name="submit-a-report-to-your-countrys-scam-reporting-website"></a>Übermitteln eines Berichts an die Website zur Betrugsberichterstattung in Ihrem Land

Websites zur Berichterstattung über Betrug bieten Informationen zum Verhindern und Vermeiden von Betrug. Sie bieten auch Mechanismen, um zu melden, ob Sie Opfer von Betrug wurden.

- Australien: [SCAMwatch](http://www.scamwatch.gov.au/)

- Kanada: [Canadian Anti-Fraud Centre](http://www.antifraudcentre-centreantifraude.ca/)

- Frankreich: [Agence nationale de la sécurité des systèmes d'information](http://www.ssi.gouv.fr/)

- Deutschland: [Bundesamt für Sicherheit in der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)

- Irland: [An Garda Síochána](http://www.garda.ie/)

- Neuseeland: [Betrugsversuche im Verbraucherschutz](http://www.consumeraffairs.govt.nz/scams)

- Vereinigtes Königreich: [Aktionsbetrug](http://www.actionfraud.police.uk/)

- Vereinigte Staaten: [On Guard Online](http://www.onguardonline.gov/)

Wenn Ihr Land nicht aufgeführt ist, fragen Sie Ihre lokalen oder Bundesbehörden.

### <a name="submit-email-messages-to-microsoft"></a>Senden von E-Mail-Nachrichten an Microsoft

Sie können Phishingnachrichten melden, die Ransomware enthalten, indem Sie eine von mehreren Methoden verwenden. Weitere Informationen finden Sie unter [Melden von Nachrichten und Dateien an Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="see-also"></a>Siehe auch

- [Ransomware](/windows/security/threat-protection/intelligence/ransomware-malware)

- [Ransomware-Antwort– um zu zahlen oder nicht zu bezahlen?](https://www.microsoft.com/security/blog/2019/12/16/ransomware-response-to-pay-or-not-to-pay/)

- [Norsk -Wasserkraft reagiert auf Ransomware-Angriff mit Transparenz](https://www.microsoft.com/security/blog/2019/12/17/norsk-hydro-ransomware-attack-transparency/)

- [Ransomware-Erkennung und Wiederherstellung Ihrer Dateien in OneDrive](https://support.microsoft.com/office/0d90ec50-6bfd-40f4-acc7-b8c12c73637f)

- [Microsoft Security Intelligence Bericht](https://www.microsoft.com/securityinsights/)

- [Aktivieren oder Deaktivieren von Makros in Office Dateien](https://support.microsoft.com/office/12b036fd-d140-4e74-b45e-16fed1a7e5c6)

- [Empfohlene Einstellungen für EOP und Microsoft Defender für Office 365 Sicherheit](recommended-settings-for-eop-and-office365.md)

- [Ein würdiges Upgrade: Sicherheit der nächsten Generation auf Windows 10 2017 widerstandsfähig gegen Ransomware-Ausbrüche](https://www.microsoft.com/security/blog/2018/01/10/a-worthy-upgrade-next-gen-security-on-windows-10-proves-resilient-against-ransomware-outbreaks-in-2017/)

- [Kein Mas, Samas: Was ist im Modus operandi dieser Ransomware?](https://www.microsoft.com/security/blog/2016/03/17/no-mas-samas-whats-in-this-ransomwares-modus-operandi/)

- [Sperrige Schadsoftware, glücklich, sie zu vermeiden](https://www.microsoft.com/security/blog/2016/02/24/locky-malware-lucky-to-avoid-it/)

- [MSRT Juli 2016: Cerber Ransomware](https://www.microsoft.com/security/blog/2016/07/12/msrt-july-2016-cerber-ransomware/)

- [Die drei Haupte der Cerberus-like Cerber Ransomware](https://www.microsoft.com/security/blog/2016/03/09/the-three-heads-of-the-cerberus-like-cerber-ransomware/)

- [Troldesh Ransomware, beeinflusst durch (den) Da-Vinci-Code](https://www.microsoft.com/security/blog/2016/07/13/troldesh-ransomware-influenced-by-the-da-vinci-code/)