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
description: Microsoft 365 Administratoren erfahren, wie sie sich von einem Ransomware-Angriff wiederherstellen können.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6c3664cb2a60a7173e345de4abaddefefea6e2b1
ms.sourcegitcommit: 5db5047c24b56f3af90c2bc5c830a7a13eeeccad
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2021
ms.locfileid: "53341436"
---
# <a name="recover-from-a-ransomware-attack-in-microsoft-365"></a>Wiederherstellen von einem Ransomware-Angriff in Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Auch wenn Sie alle Vorsichtsmaßnahmen ergreifen, um Ihre Organisation zu schützen, können Sie dennoch einem [Ransomware-Angriff](/windows/security/threat-protection/intelligence/ransomware-malware) zum Opfer fallen. Ransomware ist ein großes Unternehmen, und die Angriffe sind sehr ausgereift.

Die Schritte in diesem Artikel bieten Ihnen die beste Möglichkeit, Daten wiederherzustellen und die interne Verbreitung der Infektion zu stoppen. Bevor Sie beginnen, sollten Sie die folgenden Punkte beachten:

- Es gibt keine Garantie dafür, dass die Zahlung des Lösegelds den Zugriff auf Ihre Dateien zurückgibt. Tatsächlich kann ihnen die Zahlung des Lösegelds ein Ziel für mehr Ransomware machen.

  Wenn Sie bereits bezahlt haben, aber ohne die Lösung des Angreifers wiederhergestellt haben, wenden Sie sich an Ihre Bank, um festzustellen, ob sie die Transaktion blockieren kann.

  Wir empfehlen außerdem, den Ransomware-Angriff an Strafverfolgungsbehörden, Websites mit Betrugsberichten und Microsoft zu melden, wie weiter unten in diesem Artikel beschrieben.

- Es ist wichtig, dass Sie schnell auf den Angriff und dessen Folgen reagieren. Je länger Sie warten, desto unwahrscheinlicher ist es, dass Sie die betroffenen Daten wiederherstellen können.

## <a name="step-1-verify-your-backups"></a>Schritt 1: Überprüfen Der Sicherungen

Wenn Sie Offlinesicherungen haben, können Sie die verschlüsselten Daten wahrscheinlich wiederherstellen, **nachdem** Sie die Ransomware-Nutzlast (Schadsoftware) aus Ihrer Umgebung entfernt haben.

Wenn Sie keine Sicherungen haben oder wenn Ihre Sicherungen auch von der Ransomware betroffen waren, können Sie diesen Schritt überspringen.

## <a name="step-2-disable-exchange-activesync-and-onedrive-sync"></a>Schritt 2: Deaktivieren von Exchange ActiveSync und OneDrive-Synchronisation

Der wichtigste Punkt hier ist, die Verbreitung der Datenverschlüsselung durch die Ransomware zu stoppen.

Wenn Sie E-Mails als Ziel der Ransomware-Verschlüsselung vermuten, deaktivieren Sie vorübergehend den Benutzerzugriff auf Postfächer. Exchange ActiveSync synchronisiert Daten zwischen Geräten und Exchange Online Postfächern.

Informationen zum Deaktivieren Exchange ActiveSync für ein Postfach finden Sie unter [So deaktivieren Sie Exchange ActiveSync für Benutzer in Exchange Online](https://support.microsoft.com/help/2795303).

Informationen zum Deaktivieren anderer Arten des Zugriffs auf ein Postfach finden Sie unter:

- [Aktivieren oder Deaktivieren der MAPI für ein Postfach.](/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi)

- [Aktivieren oder Deaktivieren des POP3- oder IMAP4-Zugriffs für einen Benutzer](/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)

Das Anhalten OneDrive-Synchronisation schützt Ihre Clouddaten davor, von potenziell infizierten Geräten aktualisiert zu werden. Weitere Informationen finden Sie unter "Anhalten und Fortsetzen der [Synchronisierung in OneDrive."](https://support.microsoft.com/office/2152bfa4-a2a5-4d3a-ace8-92912fb4421e)

## <a name="step-3-remove-the-malware-from-the-affected-devices"></a>Schritt 3: Entfernen der Schadsoftware von den betroffenen Geräten

Führen Sie einen vollständigen, aktuellen Antivirus-Scan auf allen verdächtigen Computern und Geräten aus, um die Nutzlast zu erkennen und zu entfernen, die der Ransomware zugeordnet ist.

Vergessen Sie nicht, Geräte zu scannen, die Daten synchronisieren, oder die Ziele zugeordneter Netzlaufwerke.

Sie können [Windows Defender](https://www.microsoft.com/windows/comprehensive-security) oder (für ältere Clients) [Microsoft Security Essentials](https://www.microsoft.com/download/details.aspx?id=5201)verwenden.

Eine Alternative, die Ihnen auch hilft, Ransomware oder Schadsoftware zu entfernen, ist das [Tool zum Entfernen bösartiger Software (Malicious Software Removal Tool, MSRT).](https://www.microsoft.com/download/details.aspx?id=9905)

Wenn diese Optionen nicht funktionieren, können Sie [versuchen, Windows Defender Offline zu](https://support.microsoft.com/help/17466) Windows Defender oder [Probleme beim Erkennen und Entfernen von Schadsoftware zu beheben.](https://support.microsoft.com/help/4466982)

## <a name="step-4-recover-files-on-a-cleaned-computer-or-device"></a>Schritt 4: Wiederherstellen von Dateien auf einem bereinigten Computer oder Gerät

Nachdem Sie den vorherigen Schritt abgeschlossen haben, um die Ransomware-Nutzlast aus Ihrer Umgebung zu entfernen (wodurch die Ransomware Ihre Dateien nicht verschlüsseln oder entfernen kann), können Sie den [Dateiverlauf](https://support.microsoft.com/help/17128) in Windows 10 und Windows 8.1 oder Systemschutz in Windows 7 verwenden, um zu versuchen, Ihre lokalen Dateien und Ordner wiederherzustellen.

**Hinweise**:

- Einige Ransomware verschlüsselt oder löscht auch die Sicherungsversionen, sodass Sie den Dateiverlauf oder Systemschutz nicht zum Wiederherstellen von Dateien verwenden können. In diesem Fall müssen Sie Sicherungen auf externen Laufwerken oder Geräten verwenden, die nicht von der Ransomware oder OneDrive betroffen waren, wie im nächsten Abschnitt beschrieben.

- Wenn ein Ordner mit OneDrive synchronisiert wird und Sie nicht die neueste Version von Windows verwenden, gibt es möglicherweise einige Einschränkungen beim Verwenden des Dateiverlaufs.

## <a name="step-5-recover-your-files-in-your-onedrive-for-business"></a>Schritt 5: Wiederherstellen Ihrer Dateien in Ihrem OneDrive for Business

Mit der Dateiwiederherstellung in OneDrive for Business können Sie die gesamte OneDrive innerhalb der letzten 30 Tage auf einen früheren Zeitpunkt wiederherstellen. Weitere Informationen finden Sie unter [Wiederherstellen Ihres OneDrive](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15).

## <a name="step-6-recover-deleted-email"></a>Schritt 6: Wiederherstellen gelöschter E-Mails

In dem seltenen Fall, dass die Ransomware alle Ihre E-Mails gelöscht hat, können Sie wahrscheinlich die gelöschten Elemente wiederherstellen. Weitere Informationen finden Sie unter:

- [Wiederherstellen von gelöschten Nachrichten im Postfach eines Benutzers](/exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages)

- [Wiederherstellen gelöschter Elemente in Outlook für Windows](https://support.microsoft.com/office/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce)

## <a name="step-7-re-enable-exchange-activesync-and-onedrive-sync"></a>Schritt 7: Erneutes Aktivieren von Exchange ActiveSync und OneDrive-Synchronisation

Nachdem Sie Ihre Computer und Geräte bereinigt und Ihre Daten wiederhergestellt haben, können Sie Exchange ActiveSync und OneDrive-Synchronisation, die Sie zuvor in [Schritt 2](#step-2-disable-exchange-activesync-and-onedrive-sync)deaktiviert haben, erneut aktivieren.

## <a name="step-8-optional-block-onedrive-sync-for-specific-file-extensions"></a>Schritt 8 (Optional): Blockieren OneDrive-Synchronisation für bestimmte Dateierweiterungen

Nachdem Sie die Wiederherstellung ausgeführt haben, können Sie verhindern, dass OneDrive for Business Clients die Dateitypen synchronisieren, die von dieser Ransomware betroffen waren. Weitere Informationen finden Sie unter ["Set-SPOTenantSyncClientRestriction"](/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)

## <a name="report-the-attack"></a>Melden des Angriffs

### <a name="contact-law-enforcement"></a>Kontakt mit Strafverfolgungsbehörden

Sie sollten sich an Ihre lokalen oder Bundesbehörden für Strafverfolgungsbehörden wenden. Wenn Sie sich beispielsweise in den VEREINIGTEn Staaten befinden, können Sie sich an das [lokale FBI-Außendienst,](https://www.fbi.gov/contact-us/field) [IC3](http://www.ic3.gov/complaint/default.aspx) oder [den Geheimen Dienst](http://www.secretservice.gov/)wenden.

### <a name="submit-a-report-to-your-countrys-scam-reporting-website"></a>Übermitteln eines Berichts an die Website für Betrugsberichte Ihres Landes

Websites für Betrugsberichte bieten Informationen dazu, wie Sie Betrug verhindern und vermeiden können. Sie bieten auch Mechanismen, um zu melden, ob Sie Opfer eines Betrugs waren.

- Australien: [SCAMwatch](http://www.scamwatch.gov.au/)

- Kanada: [Canada Anti-Fraud Center](http://www.antifraudcentre-centreantifraude.ca/)

- Frankreich: [Agence nationale de la sécurité des systèmes d'information](http://www.ssi.gouv.fr/)

- Deutschland: [Doppelklicken für Sicherheit in der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)

- Irland: [An Bali Síochána](http://www.garda.ie/)

- Neuseeland: [Betrug bei Verbraucherfragen](http://www.consumeraffairs.govt.nz/scams)

- Schweiz [Nationales Zentrum für Cybersicherheit NCSC](https://www.ncsc.admin.ch/ncsc/de/home.html)

- Vereinigtes Königreich: [Betrugsaktion](http://www.actionfraud.police.uk/)

- Vereinigte Staaten: [On Guard Online](http://www.onguardonline.gov/)

Wenn Ihr Land nicht aufgeführt ist, fragen Sie Ihre lokalen oder bundeseigenen Strafverfolgungsbehörden.

### <a name="submit-email-messages-to-microsoft"></a>Senden von E-Mail-Nachrichten an Microsoft

Sie können Phishingnachrichten, die Ransomware enthalten, mithilfe einer von mehreren Methoden melden. Weitere Informationen finden Sie unter [Melden von Nachrichten und Dateien an Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="additional-ransomware-resources"></a>Zusätzliche Ransomware-Ressourcen

[Übersicht über die von Menschen betriebene Ransomware](/security/compass/human-operated-ransomware)

[Schneller Schutz vor Ransomware und Erpressung](/security/compass/protect-against-ransomware)

[Die neueste Microsoft Security Intelligence-Berichts-PDF)](https://www.microsoft.com/securityinsights/) (Suche nach "Ransomware")

**Ransomware: Ein verbreiteter und fortlaufender Bedrohungsbericht** im **Knoten "Bedrohungsanalyse"** des Microsoft 365 Defender-Portals

Microsoft 365 Schutz:

- [Ransomware-Erkennung und Wiederherstellung Ihrer Dateien in OneDrive](https://support.microsoft.com/office/0d90ec50-6bfd-40f4-acc7-b8c12c73637f)
- [Aktivieren oder Deaktivieren von Makros in Office Dateien](https://support.microsoft.com/office/12b036fd-d140-4e74-b45e-16fed1a7e5c6)
- [Empfohlene Einstellungen für EOP und Microsoft Defender für Office 365 Sicherheit](recommended-settings-for-eop-and-office365.md)

Blogbeiträge des Microsoft Security-Teams:

- [Ausfallsicherheit durch Das Verständnis von Cybersicherheitsrisiken: Teil 4 – Navigieren in aktuellen Bedrohungen (Mai 2021)](https://www.microsoft.com/security/blog/2021/05/26/becoming-resilient-by-understanding-cybersecurity-risks-part-4-navigating-current-threats/)

  Weitere Informationen finden Sie im Abschnitt **"Ransomware".**

- [Von Menschen betriebene Ransomware-Angriffe: Ein verhindbares Notfall (März 2020)](https://www.microsoft.com/security/blog/2020/03/05/human-operated-ransomware-attacks-a-preventable-disaster/)
- [Ransomware-Antwort – zum Bezahlen oder nicht zum Bezahlen? (Dezember 2019)](https://www.microsoft.com/security/blog/2019/12/16/ransomware-response-to-pay-or-not-to-pay/)
- [NorskAntwort reagiert mit Transparenz auf Ransomware-Angriffe (Dezember 2019)](https://www.microsoft.com/security/blog/2019/12/17/norsk-hydro-ransomware-attack-transparency/)
- [Ein angemessenes Upgrade: Sicherheit der nächsten Generation auf Windows 10 erweist sich 2017 als stabil gegen Ransomware-Fälle (Januar 2018)](https://www.microsoft.com/security/blog/2018/01/10/a-worthy-upgrade-next-gen-security-on-windows-10-proves-resilient-against-ransomware-outbreaks-in-2017/)

