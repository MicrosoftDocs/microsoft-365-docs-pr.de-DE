---
title: Wiederherstellen nach einem Ransomware-Angriff
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.article: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: Microsoft 365-Administratoren erfahren, wie Sie nach einem Ransomware-Angriff wiederherstellen können.
ms.openlocfilehash: a1369e64821902e3c2a3061acd1bbebeeb6c85ac
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357097"
---
# <a name="recover-from-a-ransomware-attack-in-microsoft-365"></a>Wiederherstellen nach einem Ransomware-Angriff in Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Selbst wenn Sie alle Vorkehrungen treffen, um Ihre Organisation zu schützen, können Sie dennoch einem [Ransomware](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware) -Angriff zum Opfer fallen. Ransomware ist ein großes Unternehmen, und die Angriffe sind sehr hoch entwickelt.

Die Schritte in diesem Artikel bieten Ihnen die beste Möglichkeit, Daten wiederherzustellen und die interne Verbreitung von Infektionen zu beenden. Bevor Sie beginnen, sollten Sie die folgenden Punkte beachten:

- Es gibt keine Garantie, dass durch das bezahlen des Lösegelds der Zugriff auf Ihre Dateien zurückgegeben wird. Tatsächlich können Sie mit dem Lösegeld ein Ziel für mehr Ransomware machen.

  Wenn Sie bereits bezahlt haben, aber ohne Verwendung der Lösung des Angreifers wiederhergestellt haben, wenden Sie sich an Ihre Bank, um zu prüfen, ob Sie die Transaktion blockieren kann.

  Außerdem wird empfohlen, dass Sie den Ransomware-Angriff an Strafverfolgungs-, Scam-berichterstellungswebsites und Microsoft melden, wie weiter unten in diesem Artikel beschrieben.

- Es ist wichtig, dass Sie schnell auf den Angriff und seine Konsequenzen reagieren. Je länger Sie warten, desto wahrscheinlicher ist es, dass Sie die betroffenen Daten wiederherstellen können.

## <a name="step-1-verify-your-backups"></a>Schritt 1: Überprüfen der Sicherungen

Wenn Sie Offlinesicherungen haben, können Sie die verschlüsselten Daten möglicherweise wiederherstellen, **nachdem** Sie die Ransomware-Nutzlast (Schadsoftware) aus Ihrer Umgebung entfernt haben.

Wenn Sie keine Sicherungen haben oder Ihre Sicherungen auch von der Ransomware betroffen sind, können Sie diesen Schritt überspringen.

## <a name="step-2-disable-exchange-activesync-and-onedrive-sync"></a>Schritt 2: Deaktivieren von Exchange ActiveSync und OneDrive Sync

Der entscheidende Punkt ist, dass die Verbreitung der Datenverschlüsselung durch das Ransomware gestoppt wird.

Wenn Sie vermuten, dass e-Mails als Ziel der Ransomware-Verschlüsselung verdächtigt werden, deaktivieren Sie vorübergehend den Benutzer Zugriff auf Postfächer. Exchange ActiveSync synchronisiert Daten zwischen Geräten und Exchange Online Postfächern.

Informationen zum Deaktivieren von Exchange ActiveSync für ein Postfach finden Sie unter [Deaktivieren von Exchange ActiveSync für Benutzer in Exchange Online](https://support.microsoft.com/help/2795303).

Informationen zum Deaktivieren anderer Zugriffstypen auf ein Postfach finden Sie unter:

- [Aktivieren oder Deaktivieren von MAPI für ein Postfach](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi).

- [Aktivieren oder Deaktivieren des POP3-oder IMAP4-Zugriffs für einen Benutzer](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)

Durch das Anhalten der OneDrive-Synchronisierung können Sie verhindern, dass Ihre Cloud-Daten von potenziell infizierten Geräten aktualisiert werden. Weitere Informationen finden Sie unter [Anhalten und Fortsetzen der Synchronisierung in OneDrive](https://support.microsoft.com/office/2152bfa4-a2a5-4d3a-ace8-92912fb4421e).

## <a name="step-3-remove-the-malware-from-the-affected-devices"></a>Schritt 3: Entfernen der Schadsoftware von den betroffenen Geräten

Führen Sie eine vollständige, aktuelle Virenüberprüfung auf allen vermuteten Computern und Geräten aus, um die dem Ransomware zugeordnete Nutzlast zu erkennen und zu entfernen.

Vergessen Sie nicht, Geräte zu überprüfen, die Daten synchronisieren, oder die Ziele von zugeordneten Netzlaufwerken.

Sie können [Windows Defender](https://www.microsoft.com/windows/comprehensive-security) oder (für ältere Clients) [Microsoft Security Essentials](https://www.microsoft.com/download/details.aspx?id=5201)verwenden.

Eine Alternative, die Ihnen auch beim Entfernen von Ransomware oder Schadsoftware helfen wird, ist das Tool zum Entfernen [bösartiger Software (MSRT)](https://www.microsoft.com/download/details.aspx?id=9905).

Wenn diese Optionen nicht funktionieren, können Sie [Windows Defender Offline](https://support.microsoft.com/help/17466) ausprobieren oder [Probleme beim erkennen und Entfernen von Schadsoftware beheben](https://support.microsoft.com/help/4466982).

## <a name="step-4-recover-files-on-a-cleaned-computer-or-device"></a>Schritt 4: Wiederherstellen von Dateien auf einem gesäuberten Computer oder Gerät

Nachdem Sie den vorherigen Schritt ausgeführt haben, um die Ransomware-Nutzlast aus Ihrer Umgebung zu entfernen (wodurch das Verschlüsseln oder Entfernen von Dateien durch Ransomware verhindert wird), können Sie den [Dateiverlauf](https://support.microsoft.com/help/17128) in Windows 10 und Windows 8.1 oder den System Schutz in Windows 7 verwenden, um zu versuchen, ihre lokalen Dateien und Ordner wiederherzustellen.

**Hinweise**:

- In einigen Ransomware werden auch die Sicherungsversionen verschlüsselt oder gelöscht, sodass Sie den Dateiverlauf oder den System Schutz nicht zum Wiederherstellen von Dateien verwenden können. In diesem Fall müssen Sie Sicherungen auf externen Laufwerken oder Geräten verwenden, die nicht von der Ransomware oder OneDrive betroffen waren, wie im nächsten Abschnitt beschrieben.

- Wenn ein Ordner mit OneDrive synchronisiert wird und Sie nicht die neueste Version von Windows verwenden, gibt es möglicherweise einige Einschränkungen mithilfe des Dateiverlaufs.

## <a name="step-5-recover-your-files-in-your-onedrive-for-business"></a>Schritt 5: Wiederherstellen der Dateien im OneDrive für Unternehmen

Durch die Wiederherstellung von Dateien in OneDrive für Unternehmen können Sie die gesamte OneDrive innerhalb der letzten 30 Tage auf einen vorherigen Zeitpunkt zurücksetzen. Weitere Informationen finden Sie unter [Wiederherstellen der OneDrive](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15).

## <a name="step-6-recover-deleted-email"></a>Schritt 6: Wiederherstellen gelöschter e-Mails

In dem seltenen Fall, dass die Ransomware alle Ihre e-Mails gelöscht hat, können Sie die gelöschten Elemente wahrscheinlich wiederherstellen. Weitere Informationen finden Sie unter:

- [Wiederherstellen von gelöschten Nachrichten im Postfach eines Benutzers](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages)

- [Wiederherstellen gelöschter Elemente in Outlook für Windows](https://support.microsoft.com/office/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce)

## <a name="step-7-re-enable-exchange-activesync-and-onedrive-sync"></a>Schritt 7: Erneutes Aktivieren von Exchange ActiveSync und OneDrive Sync

Nachdem Sie Ihre Computer und Geräte bereinigt und Ihre Daten wiederhergestellt haben, können Sie die zuvor in [Schritt 2](#step-2-disable-exchange-activesync-and-onedrive-sync)deaktivierte Exchange ActiveSync-und OneDrive-Synchronisierung erneut aktivieren.

## <a name="step-8-optional-block-onedrive-sync-for-specific-file-extensions"></a>Schritt 8 (optional): Blockieren der OneDrive-Synchronisierung für bestimmte Dateierweiterungen

Nachdem Sie sich wieder erholt haben, können Sie verhindern, dass OneDrive für Unternehmen Clients die von diesem Ransomware betroffenen Dateitypen synchronisieren. Weitere Informationen finden Sie unter [festlegen-SPOTenantSyncClientRestriction](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)

## <a name="report-the-attack"></a>Melden des Angriffs

### <a name="contact-law-enforcement"></a>Kontakt Strafverfolgungsbehörden

Wenden Sie sich an Ihre lokalen oder Bundes Strafverfolgungsbehörden. Wenn Sie sich beispielsweise in den Vereinigten Staaten befinden, können Sie sich an das [FBI local Field Office](https://www.fbi.gov/contact-us/field), [IC3](http://www.ic3.gov/complaint/default.aspx) oder [Secret Service](http://www.secretservice.gov/)wenden.

### <a name="submit-a-report-to-your-countrys-scam-reporting-website"></a>Senden eines Berichts an die Scam-Berichtswebsite Ihres Landes

Scam-berichterstellungswebsites bieten Informationen zum verhindern und vermeiden von Scams. Sie bieten auch Mechanismen zum melden, wenn Sie Opfer von Betrug wurden.

- Australien: [SCAMwatch](http://www.scamwatch.gov.au/)

- Kanada: [kanadisches Betrugs](http://www.antifraudcentre-centreantifraude.ca/) Bekämpfungs Zentrum

- Frankreich: [Agence nationale de la sécurité des Systèmes Letter](http://www.ssi.gouv.fr/)

- Deutschland: [Bundesamt für Sicherheit in der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)

- Irland: [an Garda Síochána](http://www.garda.ie/)

- Neuseeland: [Scams für Verbraucherfragen](http://www.consumeraffairs.govt.nz/scams)

- Vereinigtes Königreich: [Aktions betrug](http://www.actionfraud.police.uk/)

- Vereinigte Staaten: [On Guard Online](http://www.onguardonline.gov/)

Wenn Ihr Land nicht aufgeführt ist, wenden Sie sich an Ihre lokalen oder Bundes Strafverfolgungsbehörden.

### <a name="submit-email-messages-to-microsoft"></a>Senden von e-Mail-Nachrichten an Microsoft

Sie können Phishing-Nachrichten melden, die Ransomware enthalten, indem Sie eine von mehreren Methoden verwenden. Weitere Informationen finden Sie unter [Melden von Nachrichten und Dateien an Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="see-also"></a>Siehe auch

- [Ransomware](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware)

- [Ransomware-Antwort – zu zahlen oder nicht zu zahlen?](https://www.microsoft.com/security/blog/2019/12/16/ransomware-response-to-pay-or-not-to-pay/)

- [Norsk Hydro reagiert auf Ransomware-Angriff mit Transparenz](https://www.microsoft.com/security/blog/2019/12/17/norsk-hydro-ransomware-attack-transparency/)

- [Ransomware-Erkennung und erneutes bedecken Ihrer Dateien in OneDrive](https://support.microsoft.com/office/0d90ec50-6bfd-40f4-acc7-b8c12c73637f)

- [Microsoft Security Intelligence-Bericht](https://www.microsoft.com/securityinsights/)

- [Aktivieren oder Deaktivieren von Makros in Office-Dateien](https://support.microsoft.com/office/12b036fd-d140-4e74-b45e-16fed1a7e5c6)

- [Empfohlene Einstellungen für EoP und Microsoft Defender für Office 365 Sicherheit](recommended-settings-for-eop-and-office365-atp.md)

- [Ein würdiges Upgrade: Sicherheit der nächsten Generation unter Windows 10 erweist sich als widerstandsfähig gegen Ransomware-ausbruche in 2017](https://www.microsoft.com/security/blog/2018/01/10/a-worthy-upgrade-next-gen-security-on-windows-10-proves-resilient-against-ransomware-outbreaks-in-2017/)

- [Keine mas, Samas: Was ist in diesem Ransomware-Modus operandi?](https://www.microsoft.com/security/blog/2016/03/17/no-mas-samas-whats-in-this-ransomwares-modus-operandi/)

- [Locky Schadsoftware, Lucky to Avoid IT](https://www.microsoft.com/security/blog/2016/02/24/locky-malware-lucky-to-avoid-it/)

- [MSRT July 2016: Cerber Ransomware](https://www.microsoft.com/security/blog/2016/07/12/msrt-july-2016-cerber-ransomware/)

- [Die drei Köpfe der Cerberus-like Cerber Ransomware](https://www.microsoft.com/security/blog/2016/03/09/the-three-heads-of-the-cerberus-like-cerber-ransomware/)

- [Troldesh Ransomware beeinflusst von (dem) da Vinci-Code](https://www.microsoft.com/security/blog/2016/07/13/troldesh-ransomware-influenced-by-the-da-vinci-code/)
