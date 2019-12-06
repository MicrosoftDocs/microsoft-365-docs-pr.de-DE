---
title: Überwachen auf Lecks für personenbezogene Daten
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 02/07/2018
audience: ITPro
ms.topic: overview
ms.collection:
- Strat_O365_Enterprise
- Ent_O365
- GDPR
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
description: Lernen Sie drei Tools kennen, mit denen Sie Lecks für personenbezogene Daten aufspüren können.
ms.openlocfilehash: 995f0b273753d7b3a92b8c5acef6eb94d51458b3
ms.sourcegitcommit: 2468bcb01625f97a322459814d81b9faad717859
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2019
ms.locfileid: "39872101"
---
# <a name="monitor-for-leaks-of-personal-data"></a>Überwachen auf Lecks für personenbezogene Daten

Es gibt viele Tools, die zum Überwachen der Verwendung und Übertragung personenbezogener Daten verwendet werden können. In diesem Thema werden drei Tools beschrieben, die gut funktionieren.

![Tools zum Überwachen der Verwendung und Übertragung personenbezogener Daten](../media/Monitor-for-leaks-of-personal-data-image1.png)

In der Darstellung sehen Sie Folgendes:

-   Beginnen Sie mit Office 365-Berichten zur Verhinderung von Datenverlust, um personenbezogene Daten in SharePoint Online, OneDrive for Business und E-Mails bei der Übertragung zu überwachen. Diese bieten die größtmögliche Detailebene für die Überwachung von personenbezogenen Daten. Diese Berichte enthalten jedoch nicht alle Dienste in Office 365.

-   Verwenden Sie anschließend die Warnungsrichtlinien und das Office 365-Überwachungsprotokoll, um die Aktivitäten in Office 365-Diensten zu überwachen. Richten Sie kontinuierliche Überwachung ein, oder untersuchen Sie einen Vorfall anhand des Überwachungsprotokolls. Das Office 365-Überwachungsprotokoll kann auf Office 365-Dienste, Sway, PowerBI, eDiscovery, Dynamics 365, Microsoft Flow, Microsoft Teams, Administratoraktivität, OneDrive for Business, SharePoint Online, E-Mail in der Übertragung und ruhende Postfächer angewendet werden. Skype-Unterhaltungen sind in ruhenden Postfächern enthalten.

-   Zum Schluss verwenden Sie Microsoft Cloud App Security, um Dateien mit vertraulichen Daten in anderen SaaS-Anbietern zu überwachen. In Kürze können vertrauliche Informationstypen von Office 365 und einheitliche Beschriftungen für Azure Information Protection und Office mit Cloud App Security verwendet werden. Sie können Richtlinien einrichten, die für alle Ihre SaaS-Apps oder für bestimmte Apps (beispielsweise Box) gelten. Mit Cloud App Security können keine Dateien in Exchange Online ermittelt werden, auch keine an E-Mails angefügten Dateien.

## <a name="office-365-data-loss-prevention-reports"></a>Berichte zur Verhinderung von Datenverlust in Office 365

Nachdem Sie DLP-Richtlinien (Data Loss Prevention, Verhinderung von Datenverlust) erstellt haben, müssen Sie sicherstellen, dass diese wie gewünscht funktionieren und Sie bei der Richtlinieneinhaltung unterstützen. Mithilfe der DLP-Berichte in Office 365 können Sie schnell die Anzahl der DLP-Richtlinienentsprechungen, -Außerkraftsetzungen oder falsch positiven Resultate anzeigen, ermitteln, ob sie im Laufe der Zeit einen Aufwärts- oder Abwärtstrend aufweisen, den Bericht auf verschiedene Weisen filtern und zusätzliche Details anzeigen, indem Sie einen Punkt in einer Zeile oder im Diagramm auswählen.

Sie können die DLP-Berichte für Folgendes verwenden:

-   Sie können sich auf bestimmte Zeiträume konzentrieren und so mehr über die Gründe für Spitzen und Trends erfahren.

-   Sie können die Geschäftsprozesse ermitteln, die gegen die DLP-Richtlinien Ihrer Organisation verstoßen.

-   Sie können die geschäftlichen Auswirkungen der DLP-Richtlinien besser nachvollziehen.

-   Zeigen Sie die Begründungen an, die von Benutzern gesendet werden, wenn diese einen Richtlinientipp durch Außerkraftsetzen der Richtlinie oder durch Melden eines falsch positiven Resultats lösen.

-   Sie können die Einhaltung einer bestimmten DLP-Richtlinie durch Anzeigen von Übereinstimmungen für diese Richtlinie überprüfen.

-   Sie können Detailbereich eine Liste von Dateien mit vertraulichen Daten anzeigen, die mit den DLP-Richtlinien übereinstimmen.

Darüber hinaus können Sie anhand der DLP-Berichte Ihre DLP-Richtlinien bei der Ausführung im Testmodus genauer anpassen.

DLP-Berichte finden sich im Security Center und Compliance Center. Navigieren Sie zu Berichte \> Berichte anzeigen. Wechseln Sie unter „Verhinderung von Datenverlust (Data Loss Prevention, DLP)“ entweder zu „DLP-Richtlinien- und -Regelübereinstimmungen“ oder zu „Falsch positive Meldungen der DLP-Richtlinie und Außerkraftsetzungen“.

Weitere Informationen finden Sie unter [Anzeigen der Berichte zur Verhinderung von Datenverlust](https://support.office.com/article/View-the-reports-for-data-loss-prevention-41eb4324-c513-4fa5-91c8-8fbd8aaba83b).

![Bericht mit DLP-Richtlinienübereinstimmungen](../media/Monitor-for-leaks-of-personal-data-image2.png)

## <a name="office-365-audit-log-and-alert-policies"></a>Office 365-Überwachungsprotokoll und Warnungsrichtlinien

Das Office 365-Überwachungsprotokoll enthält Ereignisse von Exchange Online, SharePoint Online, OneDrive for Business, Azure Active Directory, Microsoft Teams, Power BI, Sway und anderen Office 365-Diensten.

Security Center und Compliance Center bieten zwei Möglichkeiten zum Überwachen und Berichten anhand des Office 365-Überwachungsprotokolls:

-   Einrichten von Warnungsrichtlinien, Anzeigen von Warnungen und überwachen von Trends – Verwenden Sie die Warnungsrichtlinien- und Warnungsdashboardtools im Security oder Compliance Center.

-   Direktes Durchsuchen des Überwachungsprotokolls – Suchen Sie nach allen Ereignissen in einem bestimmten Datumsbereich. Oder filtern Sie die Ergebnisse nach bestimmten Kriterien, z. B. nach dem Benutzer, der die Aktion ausgeführt hat, der Aktion oder dem Zielobjekt.

Informationenssicherheits- und Compliance-Teams können diese Tools verwenden, um von Endbenutzern und Administratoren in Office 365-Diensten ausgeführte Aktivitäten proaktiv zu überprüfen. Automatische Warnungen können konfiguriert werden, sodass E-Mail-Benachrichtigungen gesendet werden, wenn bestimmte Aktivitäten für bestimmte Websitesammlungen auftreten – z. B., wenn Inhalte von Websites freigegeben werden, die bekanntermaßen DSGVO-relevante Informationen enthalten. Dadurch können sich die Teams gezielt an die Benutzer wenden, um sicherzustellen, dass die Sicherheitsrichtlinien des Unternehmens eingehalten werden. Oder sie können zusätzliche Schulung bereitstellen.

Informationssicherheitsteams können auch das Überwachungsprotokoll durchsuchen, um einen vermeintlichen Datenmissbrauch zu untersuchen sowie Ursache und Ausmaß der Verletzung zu bestimmen. Diese integrierte Funktionalität erleichtert die Einhaltung der Artikel 33 und 34 der DSGVO. Diese verlangen bei einer Datenpanne die Benachrichtigung der Aufsichtsbehörde der DSGVO und der betroffenen Person selbst innerhalb eines bestimmten Zeitraums. Einträge im Überwachungsprotokoll werden nur 90 Tage lang im Dienst aufbewahrt. Häufig empfiehlt es sich, und viele Organisationen erfordern dies, dass die Protokolle länger aufbewahrt werden.

Es sind Lösungen verfügbar, die über die Microsoft Verwaltungsaktivitäts-API die einheitlichen Überwachungsprotokolle (Unified Audit Logs) abonnieren und beide Protokolleinträge nach Bedarf speichern können. Diese bieten erweiterte Dashboards und Warnungen. Ein Beispiel hierfür ist [Microsoft Operations Management Suite (OMS)](https://docs.microsoft.com/azure/operations-management-suite/oms-solution-office-365).

Weitere Informationen zu Warnungsrichtlinien und zum Durchsuchen des Überwachungsprotokolls finden Sie unter:

- [Warnungsrichtlinien im Microsoft 365 Security oder Compliance Center](https://support.office.com/article/Alert-policies-in-the-Office-365-Security-Compliance-Center-8927B8B9-C5BC-45A8-A9F9-96C732E58264)

- [Durchsuchen des Überwachungsprotokolls nach Benutzer- und Administratoraktivitäten in Office 365](https://support.office.com/article/Search-the-audit-log-for-user-and-admin-activity-in-Office-365-57CA5138-0AE0-4D34-BD40-240441EF2FB6) (Einführung)

- [Aktivieren oder Deaktivieren der Office 365-Überwachungsprotokollsuche](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014)

- [Durchsuchen des Überwachungsprotokolls](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c?ui=en-US&rs=en-US&ad=US)

- [Search-UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-unifiedauditlog) (Cmdlet)

- [Detaillierte Eigenschaften im Office 365-Überwachungsprotokoll](https://support.office.com/article/Detailed-properties-in-the-Office-365-audit-log-ce004100-9e7f-443e-942b-9b04098fcfc3)

## <a name="microsoft-cloud-app-security"></a>Microsoft Cloud App Security

Microsoft Cloud App Security hilft Ihnen bei der Ermittlung weiterer SaaS-Apps, die im Netzwerk verwendet werden, und vertraulicher Daten, die an diese und von diesen Apps gesendet werden.

Microsoft Cloud App Security ist ein umfassender Dienst, der tiefe Einsichten, differenzierte Kontrolle und erweiterten Bedrohungsschutz für Ihre Cloud-Apps bietet. Mehr als 15.000 Cloudanwendungen in Ihrem Netzwerk – von allen Geräten – werden identifiziert und durch kontinuierliche Risikobewertung und Analyse bewertet. Es sind keine Agenten erforderlich: Die Informationen werden von den Firewalls und Proxys erhoben, um Ihnen einen vollständigen Einblick und Kontext für die Cloudverwendung und Schatten-IT zu liefern.

Zum besseren Verständnis Ihrer Cloudumgebung bietet das Untersuchungsfeature von Cloud App Security umfassende Einblicke in alle Aktivitäten, Dateien und Konten für sanktionierte und verwaltete Apps. Sie können ausführliche Informationen auf Dateiebene erhalten und ermitteln, wo Daten zwischen den Cloud-Apps übertragen werden.

Die folgende Abbildung veranschaulicht zwei Cloud App Security-Richtlinien, die für die DSGVO hilfreich sind.

![Beispielrichtlinien für Cloud App Security](../media/Monitor-for-leaks-of-personal-data-image3.png)

Die erste Richtlinie gibt eine Warnung aus, wenn Dateien mit einem vordefinierten PII-Attribut oder einem ausgewählten benutzerdefinierten Ausdruck außerhalb der Organisation von den ausgewählten SaaS-Apps freigegeben werden.

Die zweite Richtlinie blockiert Downloads von Dateien auf alle nicht verwalteten Geräte. Sie wählen die Attribute in den Dateien aus, nach denen gesucht wird, und die SaaS-Apps, für die die Richtlinie gelten soll.

Die folgenden Attributtypen werden in Kürze in Cloud App Security verfügbar sein:

-   Typen vertraulicher Informationen in Office 365

-   Einheitliche Beschriftungen in Office 365 und Azure Information Protection

### <a name="cloud-app-security-dashboard"></a>Cloud App Security-Dashboard

Wenn Sie noch nicht der Verwendung von Cloud App Security begonnen haben, starten Sie es zunächst. So starten Sie Cloud App Security: <https://portal.cloudappsecurity.com>

Hinweis: Aktivieren Sie unbedingt „Automatisch Dateien auf Azure Information Protection-Klassifizierungsbezeichnungen überprüfen“ (in den allgemeinen Einstellungen), entweder bei den ersten Schritten mit Cloud App Security oder bevor Sie Bezeichnungen zuweisen. Nach der Installation überprüft Cloud App Security vorhandene Dateien erst wieder, wenn sie geändert werden.

![Dashboard mit Informationen zu Warnungen](../media/Monitor-for-leaks-of-personal-data-image4.png)

Weitere Informationen:

-   [Bereitstellen von Cloud App Security](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security)

-   [Weitere Informationen zu Microsoft Cloud App Security](https://www.microsoft.com/cloud-platform/cloud-app-security)

-   [Blockieren von Downloads vertraulicher Daten mithilfe des Microsoft Cloud App Security-Proxys](https://docs.microsoft.com/cloud-app-security/use-case-proxy-block-session-aad)

## <a name="example-file-and-activity-policies-to-detect-sharing-of-personal-data"></a>Beispieldatei und Aktivitätsrichtlinien zum Erkennen der Freigabe von personenbezogenen Daten

### <a name="detect-sharing-of-files-containing-pii--credit-card-number"></a>Freigabe von Dateien mit PII erkennen – Kreditkartennummer

Benachrichtigen, wenn eine Datei mit einer Kreditkartennummer von einer genehmigten Cloud-App freigegeben wird.

<table>
<thead>
<tr class="header">
<th align="left"><strong>Steuerelement</strong></th>
<th align="left"><strong>Einstellungen</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Richtlinientyp</td>
<td align="left">Dateirichtlinie</td>
</tr>
<tr class="even">
<td align="left">Richtlinienvorlage</td>
<td align="left">Keine Vorlage</td>
</tr>
<tr class="odd">
<td align="left">Schweregrad der Richtlinie</td>
<td align="left">Hoch</td>
</tr>
<tr class="even">
<td align="left">Kategorie</td>
<td align="left">DLP</td>
</tr>
<tr class="odd">
<td align="left">Filtereinstellungen</td>
<td align="left"><p>Zugriffsebene = Öffentlich (Internet), Öffentlich, Extern</p>
<p>App = &lt;Apps auswählen&gt; (verwenden Sie diese Einstellung, wenn Sie bestimmte SaaS-Apps überwachen möchten)</p></td>
</tr>
<tr class="even">
<td align="left">Übernehmen für</td>
<td align="left">Alle Dateien, alle Besitzer</td>
</tr>
<tr class="odd">
<td align="left">Inhaltsuntersuchung</td>
<td align="left"><p>Schließt Dateien ein, die einem vorhanden Ausdruck entsprechen: Alle Länder: Finanzen: Kreditkartennummer</p>
<p>Kein relevanter Kontext erforderlich: deaktiviert (Dies entspricht sowohl Schlüsselwörtern als auch RegEx)</p>
<p>Schließt Dateien mit mindestens 1 Übereinstimmung ein</p>
<p>Maskierung der letzten 4 Zeichen eines Verstoßes aufheben: aktiviert</p></td>
</tr>
<tr class="even">
<td align="left">Warnungen</td>
<td align="left"><p>Warnung für jede übereinstimmende Datei erstellen: aktiviert</p>
<p>Limit für tägliche Warnungen: 1000</p>
<p>Warnung als E-Mail auswählen: aktiviert</p>
<p>An: infosec@contoso.com</p></td>
</tr>
<tr class="odd">
<td align="left">Governance</td>
<td align="left"><p>Microsoft OneDrive for Business</p>
<p>Als privat festlegen: Aktivieren Sie „Externe Benutzer entfernen“</p>
<p>Alle anderen Einstellungen: deaktiviert</p>
<p>Microsoft SharePoint Online</p>
<p>Als privat festlegen: Aktivieren Sie „Externe Benutzer entfernen“</p>
<p>Alle anderen Einstellungen: deaktiviert</p></td>
</tr>
</tbody>
</table>

Ähnliche Richtlinien:

-   Ermitteln der Freigabe von Dateien mit PII – E-Mail-Adresse

-   Ermitteln der Freigabe von Dateien mit PII – Reisepassnummer

### <a name="detect-customer-or-hr-data-in-box-or-onedrive-for-business"></a>Ermitteln von Kunden- oder Personaldaten in Box oder OneDrive for Business

Benachrichtigen, wenn eine Datei mit der Bezeichnung „Kundendaten“ oder „Personaldaten“ in OneDrive for Business oder Box hochgeladen wird.

Hinweise:

-   Zum Überwachen von Box muss mithilfe des API-Connector-SDK ein Connector konfiguriert werden.

-   Diese Richtlinie erfordert Funktionen, die sich derzeit im privaten Vorschaumodus befinden.

<table>
<thead>
<tr class="header">
<th align="left"><strong>Steuerelement</strong></th>
<th align="left"><strong>Einstellungen</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Richtlinientyp</td>
<td align="left">Aktivitätsrichtlinie</td>
</tr>
<tr class="even">
<td align="left">Richtlinienvorlage</td>
<td align="left">Keine Vorlage</td>
</tr>
<tr class="odd">
<td align="left">Schweregrad der Richtlinie</td>
<td align="left">Hoch</td>
</tr>
<tr class="even">
<td align="left">Kategorie</td>
<td align="left">Freigabesteuerelement</td>
</tr>
<tr class="odd">
<td align="left">Aktion ausführen bei</td>
<td align="left">Einzelne Aktivität</td>
</tr>
<tr class="even">
<td align="left">Filtereinstellungen</td>
<td align="left"><p>Aktivitätstyp = Dateiupload</p>
<p>App = Microsoft OneDrive for Business und Box</p>
<p>Klassifizierungsbezeichnung (derzeit im privaten Vorschaumodus): Azure Information Protection = Kundendaten, Personalwesen – Gehaltsinformationen, Personalwesen – Mitarbeiterdaten</p></td>
</tr>
<tr class="odd">
<td align="left">Warnungen</td>
<td align="left"><p>Warnung erstellen: aktiviert</p>
<p>Limit für tägliche Warnungen: 1000</p>
<p>Warnung als E-Mail auswählen: aktiviert</p>
<p>An: infosec@contoso.com</p></td>
</tr>
<tr class="even">
<td align="left">Governance</td>
<td align="left"><p>Alle Apps</p>
<p>Unter Benutzerquarantäne stellen: aktiviert</p>
<p>Alle anderen Einstellungen: deaktiviert</p>
<p>Office 365</p>
<p>Unter Benutzerquarantäne stellen: aktiviert</p>
<p>Alle anderen Einstellungen: deaktiviert</p></td>
</tr>
</tbody>
</table>

Ähnliche Richtlinien:

-   Erkennung umfangreicher Downloads von Kundendaten oder Personaldaten – Warnung, wenn eine große Anzahl von Dateien mit Kundendaten oder Personaldaten erkannt wurden, die von einem einzelnen Benutzer innerhalb eines kurzen Zeitraums heruntergeladen werden.

-   Erkennung der Freigabe von Kunden- und Personaldaten – Warnung, wenn Dateien mit Kunden- oder Personaldaten freigegeben werden.
