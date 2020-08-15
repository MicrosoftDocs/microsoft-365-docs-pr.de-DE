---
title: Externe DNS-Einträge für Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 10/21/2019
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0
description: Eine Referenzliste für externe DNS-Einträge, die bei der Planung einer Office 365-Bereitstellung zu verwenden sind.
ms.openlocfilehash: da5a9a1095e50de779ee2fc148803e31583426a2
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690828"
---
# <a name="external-domain-name-system-records-for-office-365"></a>Externe DNS-Einträge für Office 365

|||
|:-----|:-----|
|![Domäne](../media/e05b1c78-1df0-4200-ba40-6e26b7ead68f.png)|**Möchten Sie eine angepasste Liste der DNS-Einträge für Ihre Office 365-Organisation anzeigen?** Dann führen Sie eine [Suche nach den erforderlichen Informationen zum Erstellen von Office 365 DNS-Einträgen](https://support.office.microsoft.com/article/Gather-the-information-you-need-to-create-Office-365-DNS-records-77f90d4a-dc7f-4f09-8972-c1b03ea85a67) für Ihre Domäne in Office 365 aus. <br/> **Benötigen Sie schrittweise Hilfe zum Hinzufügen dieser Einträge auf dem DNS-Host Ihrer Domäne, etwa auf GoDaddy oder eNom?** [Suchen von Links zu schrittweisen Anweisungen für viele beliebte DNS-Hosts](https://go.microsoft.com/fwlink/?LinkId=286745). <br/>  **Sie möchten die Referenzliste für Ihre eigene benutzerdefinierte Bereitstellung verwenden?** Die Liste unten sollte als Referenz für die benutzerdefinierte Office 365-Bereitstellung verwendet werden. Sie müssen auswählen, welche Einträge für Ihre Organisation gelten, und die entsprechenden Werte eintragen. <br/> **Zurück zu** [Netzwerkplanung und Leistungsoptimierung für Office 365](https://aka.ms/tune).  <br/> |

Die SPF- und MX-Einträge sind oft am schwierigsten zu ermitteln. Wir haben unsere SPF-Eintragsanweisungen am Ende dieses Artikels aktualisiert. Beachten Sie, dass Sie _nur über einen einzigen SPF-Eintrag für Ihre Domäne verfügen können_. Mehrere MX-Einträge sind zwar möglich, dies kann jedoch zu Problemen bei der Nachrichtenübermittlung führen. Mit einem einzigen MX-Eintrag, der E-Mails an ein E-Mail-System weiterleitet, werden viele potenzielle Probleme ausgeschlossen.
  
Die Abschnitte unten sind nach Diensten in Office 365 geordnet. Um eine angepasste Liste der Office 365 DNS-Einträge für Ihre Domäne anzuzeigen, melden Sie sich bei Office 365 an, und [sammeln Sie die erforderlichen Informationen zum Erstellen von Office 365 DNS-Einträgen](https://support.office.com/article/77f90d4a-dc7f-4f09-8972-c1b03ea85a67).
  
## <a name="external-dns-records-required-for-office-365-core-services"></a>Für Office 365 erforderliche externe DNS-Einträge (Hauptdienste):
<a name="BKMK_ReqdCore"> </a>

Jeder Office 365-Kunde muss zwei Einträge zu seinem externen DNS hinzufügen. Der erste CNAME-Eintrag stellt sicher, dass Office 365 Arbeitsstationen anweisen kann, sich bei der passenden Identitätsplattform zu authentifizieren. Der zweite erforderliche Eintrag dient zum Nachweis, dass Sie der Besitzer des Domänennamens sind.
  
||||
|:-----|:-----|:-----|
|**DNS-Eintrag** <br/> |**Zweck** <br/> |**Zu verwendender Wert** <br/> |
|**CNAME** <br/> **(Suite)** <br/> |Von Office 365 zum Weiterleiten der Authentifizierung an die richtige Identitätsplattform verwendet. [Weitere Informationen](https://go.microsoft.com/fwlink/p/?LinkId=322005) <br/> **Hinweis:** Dieser CNAME gilt nur für Office 365, betrieben von 21Vianet. [Weitere Informationen](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-operated-by-21vianet)  |**Alias:** msoID  <br/> **Ziel:** clientconfig.partner.microsoftonline-p.net.cn  <br/> |
|**TXT** <br/> **(Domänenüberprüfung)** <br/> |Von Office 365 ausschließlich zur Überprüfung verwendet, ob Sie der Besitzer Ihrer Domäne sind. Dieser Wert hat keine weiteren Auswirkungen.  <br/> |**Host:** @ (oder, bei einigen DNS-Hostinganbietern, Ihr Domänenname)  <br/> **TXT Value (TXT-Wert):** _Eine von_ Office 365 bereitgestellte Textzeichenfolge  <br/> Der Office 365-Assistent zur **Domäneneinrichtung** stellt die Werte zur Verfügung, die Sie zum Erstellen dieses Eintrags verwenden.  <br/> |


## <a name="external-dns-records-required-for-email-in-office-365-exchange-online"></a>Für E-Mail in Office 365 (Exchange Online) erforderliche externe DNS-Einträge
<a name="BKMK_ReqdCore"> </a>

E-Mail in Office 365 erfordert mehrere unterschiedliche Einträge. Die drei primären Einträge, die alle Kunden verwenden sollten, sind der AutoErmittlungs-, MX- und SPF-Eintrag.
  
- Der **AutoErmittlungseintrag** ermöglicht es Clientcomputern, Exchange automatisch zu finden und den Client ordnungsgemäß zu konfigurieren.

- **Der MX-Eintrag** teilt anderen Mailsystemen mit, wohin E-Mails für Ihre Domäne gesendet werden sollen. **Hinweis:** Wenn Sie Ihr E-Mail-System auf Office 365 ändern, indem Sie den MX-Eintrag der Domäne ändern, werden von nun an alle an diese Domäne gesendeten E-Mails an Office 365 gesendet.  
Möchten Sie nur einige wenige E-Mail-Adressen auf Office 365 umstellen? Sie können [Office 365 mit ein paar E-Mail-Adressen in der eigenen benutzerdefinierten Domäne einführen](https://support.office.com/article/39cee536-6a03-40cf-b9c1-f301bb6001d7).

- **Anhand des TXT-Eintrags für SPF** überprüfen E-Mail-Systeme der Empfänger, ob es sich bei dem Server, der Ihre E-Mail sendet, um einen von Ihnen genehmigten Server handelt. Dies hilft, Probleme wie E-Mail-Spoofing und -Phishing zu verhindern. Lesen Sie [Für SPF erforderliche externe DNS-Einträge](external-domain-name-system-records.md#BKMK_SPFrecords) im vorliegenden Artikel, um besser zu verstehen, was Sie zu ihrem Datensatz hinzufügen sollten.

E-Mail-Benutzer, die Exchange-Partnerverbund verwenden, benötigen außerdem einen zusätzlichen CNAME- und TXT-Eintrag, der am unteren Rand der Tabelle aufgeführt ist.
  
||||
|:-----|:-----|:-----|
|**DNS-Eintrag** <br/> |**Zweck** <br/> |**Zu verwendender Wert** <br/> |
|**CNAME** <br/> **(Exchange Online)** <br/> |Unterstützt Outlook-Clients bei der einfachen Verbindung mit dem Exchange-Online-Dienst mithilfe des AutoErmittlungs-Diensts. Die AutoErmittlung sucht automatisch den korrekten Exchange Server-Host und konfiguriert Outlook für Benutzer.  <br/> |**Alias:** Autodiscover  <br/> **Target (Ziel):** autodiscover.outlook.com  <br/> |
|**MX** <br/> **(Exchange Online)** <br/> |Sendet eingehende Mails für Ihre Domäne an den Exchange Online-Dienst in Office 365.  <br/> [!NOTE] Sobald E-Mails an Exchange Online übertragen werden, sollten Sie die MX-Einträge entfernen, die auf Ihr altes System verweisen.   |**Domain (Domäne):** Beispielsweise contoso.com  <br/> **Target email server (E-Mail-Zielserver):**\<MX token\>.mail.protection.outlook.com  <br/> **Preference/Priority (Präferenz/Priorität):** Niedriger als alle anderen MX-Einträge (dies stellt sicher, dass E-Mail an Exchange Online übermittelt wird) – z. B. 1 oder "low" (niedrig)  <br/>  Suchen Sie den \<MX token\>, indem Sie diesen Schritten folgen:  <br/>  Melden Sie sich bei Office 365 an, und wechseln Sie zu "Office 365-Administrator" \> "Domänen".  <br/>  Wählen Sie in der Spalte "Aktion" für Ihre Domäne "Probleme beheben" aus.  <br/>  Wählen Sie im Abschnitt für MX-Einträge die Option "Was korrigiere ich?" aus.  <br/>  Folgen Sie den Anweisungen auf dieser Seite, um den MX-Eintrag zu aktualisieren.  <br/> [Was ist MX-Priorität?](https://go.microsoft.com/fwlink/p/?LinkId=396471) <br/> |
|**SPF (TXT)** <br/> **(Exchange Online)**  <br/> |Dadurch kann verhindert werden, dass Dritte Ihre Domäne verwenden, um Spam oder andere schädliche E-Mails zu senden. SPF-Einträge (Sender Policy Framework) identifizieren die Server, die autorisiert sind, um E-Mails Ihrer Domäne zu senden.  <br/> |[Für SPF erforderliche externe DNS-Einträge](external-domain-name-system-records.md#BKMK_SPFrecords) <br/> |
|**TXT** <br/> **(Exchange-Partnerverbund)** <br/> |Für Exchange-Partnerverbund für Hybridbereitstellungen verwendet.  <br/> |**TXT-Eintrag 1:** Beispiel: contoso.com und zugeordneter, benutzergenerierter Hash-Text zum Nachweis für die Domäne (Beispiel: Y96nu89138789315669824)  <br/> **TXT-Eintrag 2:** Beispiel: exchangedelegation.contoso.com und zugeordneter, kundengenerierter Hash-Text zum Nachweis für die Domäne (Beispiel: Y3259071352452626169)  <br/> |
|**CNAME** <br/> **(Exchange-Partnerverbund)** <br/> |Unterstützt Outlook-Clients bei der einfachen Verbindung mit dem Exchange Online-Dienst mithilfe des AutoErmittlungs-Diensts für den Fall, dass Ihr Unternehmen Exchange-Partnerverbund einsetzt. Die AutoErmittlung sucht automatisch den korrekten Exchange Server-Host und konfiguriert Outlook für Ihre Benutzer.  <br/> |**Alias:** Beispiel: Autodiscover.service.contoso.com  <br/> **Target (Ziel):** autodiscover.outlook.com  <br/> |


## <a name="external-dns-records-required-for-skype-for-business-online"></a>Für Skype for Business Online erforderliche externe DNS-Einträge
<a name="BKMK_ReqdCore"> </a>

Wenn Sie [Office 365-URLs und IP-Adressbereiche](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2#BKMK_LYO) verwenden, müssen bestimmte Schritte ausgeführt werden, um sicherzustellen, dass Ihr Netzwerk ordnungsgemäß konfiguriert ist.

> [!NOTE]
> Diese DNS-Einträge gelten auch für Teams – insbesondere in einem Hybridszenario mit Teams und Skype for Business, bei dem bestimmte Verbundprobleme auftreten könnten.
  
||||
|:-----|:-----|:-----|
|**DNS-Eintrag** <br/> |**Zweck** <br/> |**Zu verwendender Wert** <br/> |
|**SRV** <br/> **(Skype for Business Online)** <br/> |Ermöglicht Ihrer Office 365-Domäne die gemeinsame Verwendung von Chatfunktionen mit externen Clients durch Aktivieren von SIP-Partnerverbund. Weitere Informationen über [Office 365-URLs und IP-Adressbereiche](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2#BKMK_LYO). <br/> |**Service (Dienst):** sipfederationtls  <br/> **Protocol (Protokoll):** TCP  <br/> **Priority (Priorität):** 100  <br/> **Weight (Gewichtung):** 1  <br/> **Port:** 5061  <br/> **Target (Ziel):** sipfed.online.lync.com  <br/> **Hinweis:** Wenn die Firewall oder der Proxy-Server SRV-Lookups auf einem externen DNS blockiert, sollten Sie diesen Eintrag außerdem dem internen DNS-Eintrag hinzufügen.   |
|**SRV** <br/> **(Skype for Business Online)** <br/> |Von Skype for Business zur Koordinierung des Informationsflusses zwischen Lync-Clients verwendet.  <br/> |**Service (Dienst):** sip  <br/> **Protocol (Protokoll):** TLS  <br/> **Priority (Priorität):** 100  <br/> **Weight (Gewichtung):** 1  <br/> **Port:** 443  <br/> **Target (Ziel):** sipdir.online.lync.com  <br/> |
|**CNAME** <br/> **(Skype for Business Online)** <br/> |Vom Lync-Client zur Unterstützung der Suche nach dem Skype for Business Online-Dienst und der Anmeldung verwendet.  <br/> |**Alias:** sip  <br/> **Target (Ziel):** sipdir.online.lync.com  <br/> Weitere Informationen finden Sie unter [Office 365-URLs und -IP-Adressbereiche](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2#BKMK_LYO).  <br/> |
|**CNAME** <br/> **(Skype for Business Online)** <br/> |Vom mobilen Lync-Client zur Unterstützung der Suche nach dem Skype for Business Online-Dienst und der Anmeldung verwendet.  <br/> |**Alias:** lyncdiscover  <br/> **Target (Ziel):** webdir.online.lync.com  <br/> |

## <a name="external-dns-records-required-for-office-365-single-sign-on"></a>Für das einmalige Anmelden bei Office 365 erforderliche externe DNS-Einträge
<a name="BKMK_ReqdCore"> </a>

||||
|:-----|:-----|:-----|
|**DNS-Eintrag** <br/> |**Zweck** <br/> |**Zu verwendender Wert** <br/> |
|**Host (A)** <br/> |Für einmaliges Anmelden (SSO) verwendet. Stellt den Endpunkt für Ihre externen Benutzer (sowie, falls gewünscht, auch für Ihre lokalen Benutzer) bereit, um eine Verbindung mit den Proxyservern Ihrer Active Directory-Verbunddienste (AD FS) oder einer virtuellen IP (VIP) zum Lastenausgleich herzustellen.  <br/> |**Target (Zielwert):** Beispielsweise sts.contoso.com  <br/> |

## <a name="external-dns-records-required-for-spf"></a>Für SPF erforderliche externe DNS-Einträge
<a name="BKMK_SPFrecords"> </a>

> [!IMPORTANT]
> Zwar soll SPF Spoofing verhindern, jedoch gibt es Spoofingtechniken, vor denen SPF keinen Schutz bietet. Zum Einrichten eines entsprechenden Schutzes sollten Sie nach dem Einrichten von SPF auch DKIM und DMARC für Office 365 konfigurieren. Die ersten Schritte finden Sie unter [Use DKIM to validate outbound email sent from your domain in Office 365](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx). Lesen Sie anschließend [Use DMARC to validate email in Office 365](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx).
  
SPF-Einträge und TXT-Einträge helfen zu verhindern, dass Dritte Ihre Domäne verwenden, um Spam oder andere schädliche E-Mails zu senden. SPF-Einträge (Sender Policy Framework) identifizieren die Server, die autorisiert sind, um E-Mails Ihrer Domäne zu senden.
  
Sie können pro Domäne nur einen SPF-Eintrag (also einen TXT-Eintrag mit der Definition von SPF) verwenden. Dieser einzelne Eintrag darf eine Reihe verschiedener Einschlüsse aufweisen, die Gesamtzahl der resultierenden DNS-Lookups darf 10 jedoch nicht übersteigen (dies unterstützt die Verhinderung von Denial-of-Service-Angriffen). Informationen zum Erstellen oder Aktualisieren der richtigen Werte für den SPF-Eintrag für Ihre Umgebung finden Sie in der Tabelle und den weiteren Beispielen unten.
  
### <a name="structure-of-an-spf-record"></a>Struktur eines SPF-Eintrags

Alle SPF-Einträge enthalten drei Teile: die Deklaration, dass es sich um einen SPF-Eintrag handelt, die Domänen und IP-Adressen, die E-Mails senden sollen, sowie eine Regel für die Durchsetzung. In einem gültigen SPF-Eintrag benötigen Sie alle drei. Dies ist ein Beispiel für einen häufig verwendeten SPF-Eintrag für Office 365, wenn Sie ausschließlich Exchange Online-E-Mail verwenden:
  
``` dns
TXT Name @
Values: v=spf1 include:spf.protection.outlook.com -all
```

Ein E-Mail-System, das eine E-Mail über Ihre Domäne empfängt, prüft den SPF-Eintrag, und wenn es sich bei dem E-Mail-Server, der die Nachricht gesendet hat, um einen Office 365-Server handelte, wird die Nachricht akzeptiert. Wenn es sich bei dem Server, der die Nachricht gesendet hat, beispielsweise um Ihr altes Mailsystem oder ein bösartiges System im Internet handelt, kann die SPF-Prüfung fehlschlagen, und die Nachricht wird nicht zugestellt. Überprüfungen wie diese helfen, Spoofing- und Phishingnachrichten zu verhindern.
  
### <a name="choose-the-spf-record-structure-you-need"></a>Auswählen der benötigten Struktur des SPF-Eintrags

In Szenarien, in denen Sie nicht nur Exchange Online-E-Mail für Office 365 verwenden (beispielsweise, wenn Sie außerdem mit E-Mails arbeiten, die von SharePoint Online stammen), verwenden Sie die folgende Tabelle, um zu bestimmen, was in den Wert des Eintrags aufgenommen werden soll.
  
> [!NOTE]
> In komplizierten Szenarien, die beispielsweise Edge-E-Mail-Server zum Verwalten des E-Mail-Verkehrs über Ihre Firewall hinweg umfassen, muss ein mit mehr Details versehener SPF-Eintrag eingerichtet werden. Hier erfahren Sie mehr: [Einrichten von SPF-Einträgen in Office 365 zur Unterstützung der Vermeidung von Spoofing](https://go.microsoft.com/fwlink/?LinkId=787656). Darüber hinaus können Sie viel mehr über die Funktionsweise von SPF im Zusammenspiel mit Office 365 aus [Verwenden des Sender Policy Framework (SPF) durch Office 365 zum Verhindern von Spoofing](https://go.microsoft.com/fwlink/?LinkId=787065) erfahren.
  
| Zahl|Wenn Sie Folgendes verwenden...  <br/> |Zweck  <br/> |Diese Einschlüsse hinzufügen  <br/> |
|:-----|:-----|:-----|:-----|
|1  <br/> |Alle E-Mail-Systeme (erforderlich)  <br/> |Alle SPF-Einträge beginnen mit dem folgenden Wert  <br/> |v=spf1  <br/> |
|2  <br/> |Exchange Online (verbreitet)  <br/> |Bei ausschließlicher Nutzung von Exchange Online verwenden  <br/> |include:spf.protection.outlook.com  <br/> |
|3  <br/> |Drittanbieter-E-Mail-Systeme (weniger verbreitet)  <br/> ||include:\<email system like mail.contoso.com\>  <br/> |
|4  <br/> |Lokales E-Mail-System (weniger verbreitet)  <br/> |Verwenden Sie dies, wenn Sie Exchange Online Protection oder Exchange Online zusammen mit einem anderen Mailsystem verwenden.  <br/> |ip4:\<0.0.0.0\>  <br/> ip6:\< : : \>  <br/> enthalten:\<mail.contoso.com\>  <br/> Die Werte in spitzen Klammern (\<\>) sollten andere E-Mail-Systeme sein, die E-Mails für Ihre Domäne senden.  <br/> |
|5  <br/> |Alle E-Mail-Systeme (erforderlich)  <br/> ||-all  <br/> |

### <a name="example-adding-to-an-existing-spf-record"></a>Beispiel: Hinzufügen zu einem vorhandenen SPF-Eintrag
<a name="bkmk_addtospf"> </a>

Wenn Sie bereits über einen SPF-Eintrag verfügen, müssen Sie Werte für Office 365 hinzufügen oder aktualisieren. Nehmen wir beispielsweise an, dies wäre Ihr vorhandener SPF-Eintrag für contoso.com:
  
``` dns
TXT Name @
Values: v=spf1 ip4:60.200.100.30 include:smtp.adatum.com -all
```

Nun aktualisieren Sie den SPF-Eintrag für Office 365. Sie bearbeiten Ihren aktuellen Eintrag so, dass Sie über einen SPF-Eintrag verfügen, der die benötigten Werte enthält. Für Office 365: "spf.protection.outlook.com".
  
Richtig:
  
``` dns
TXT Name @
Values: v=spf1 ip4:60.200.100.30 include:spf.protection.outlook.com include:smtp.adatum.com -all
```

Falsch:
  
``` dns
Record 1:
TXT Name @
Values: v=spf1 ip4:60.200.100.30 include:smtp.adatum.com -all
Record 2:
Values: v=spf1 include:spf.protection.outlook.com -all
```

### <a name="more-examples-of-common-spf-values"></a>Weitere Beispiele für häufig verwendete SPF-Werte
<a name="bkmk_addtospf"> </a>

Wenn Sie die gesamte Office 365-Suite verwenden und "MailChimp" zum Versenden von Marketing-E-Mails in Ihrem Auftrag nutzen, kann Ihr SPF-Eintrag bei "contoso.com" dem folgenden ähneln, bei dem die Zeilen 1, 3 und 5 aus der Tabelle oben verwendet werden. Denken Sie daran, dass die Zeilen 1 und 5 erforderlich sind.
  
``` dns
TXT Name @
Values: v=spf1 include:spf.protection.outlook.com include:servers.mcsv.net -all
```

Alternativ kann bei einer Exchange-Hybridkonfiguration, in der E-Mails sowohl von Office 365 als auch von Ihrem lokalen E-Mail-System gesendet werden, der SPF-Eintrag bei contoso.com wie folgt aussehen:
  
``` dns
TXT Name @
Values: v=spf1 include:spf.protection.outlook.com include:mail.contoso.com -all
```

Dies sind einige gängige Beispiele, die Ihnen beim Anpassen Ihres vorhandenen SPF-Eintrags beim Hinzufügen Ihrer Domäne zu Office 365 für E-Mail helfen können. In komplizierten Szenarien, die beispielsweise Edge-E-Mail-Server zum Verwalten des E-Mail-Verkehrs über Ihre Firewall hinweg umfassen, muss ein mit mehr Details versehener SPF-Eintrag eingerichtet werden. Hier erfahren Sie mehr: [Einrichten von SPF-Einträgen in Office 365 zur Unterstützung der Vermeidung von Spoofing](https://go.microsoft.com/fwlink/?LinkId=787656).
  
Mit diesem kurzen Link gelangen Sie wieder hierher zurück: [https://aka.ms/o365edns](https://aka.ms/o365edns)
