---
title: Überwachen auf Lecks für personenbezogene Daten
f1.keywords:
- NOCSH
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
ms.openlocfilehash: 617f0fde0e4b15a014658ba0fc3cf2def4b88d81
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42088392"
---
# <a name="monitor-for-leaks-of-personal-data"></a><span data-ttu-id="12d16-103">Überwachen auf Lecks für personenbezogene Daten</span><span class="sxs-lookup"><span data-stu-id="12d16-103">Monitor for leaks of personal data</span></span>

<span data-ttu-id="12d16-p101">Es gibt viele Tools, die zum Überwachen der Verwendung und Übertragung personenbezogener Daten verwendet werden können. In diesem Thema werden drei Tools beschrieben, die gut funktionieren.</span><span class="sxs-lookup"><span data-stu-id="12d16-p101">There are many tools that can be used to monitor the use and transport of personal data. This topic describes three tools that work well.</span></span>

![Tools zum Überwachen der Verwendung und Übertragung personenbezogener Daten](../../media/Monitor-for-leaks-of-personal-data-image1.png)

<span data-ttu-id="12d16-107">In der Abbildung sehen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="12d16-107">In the illustration:</span></span>

- <span data-ttu-id="12d16-p102">Beginnen Sie mit Office 365-Berichten zur Verhinderung von Datenverlust, um personenbezogene Daten in SharePoint Online, OneDrive for Business und E-Mails bei der Übertragung zu überwachen. Diese bieten die größtmögliche Detailebene für die Überwachung von personenbezogenen Daten. Diese Berichte enthalten jedoch nicht alle Dienste in Office 365.</span><span class="sxs-lookup"><span data-stu-id="12d16-p102">Start with Office 365 data loss prevention reports for monitoring personal data in SharePoint Online, OneDrive for Business, and email in transit. These provide the greatest level of detail for monitoring personal data. However, these reports don't include all services in Office 365.</span></span>

- <span data-ttu-id="12d16-p103">Verwenden Sie anschließend die Warnungsrichtlinien und das Office 365-Überwachungsprotokoll, um die Aktivitäten in Office 365-Diensten zu überwachen. Richten Sie kontinuierliche Überwachung ein, oder untersuchen Sie einen Vorfall anhand des Überwachungsprotokolls. Das Office 365-Überwachungsprotokoll kann auf Office 365-Dienste, Sway, PowerBI, eDiscovery, Dynamics 365, Microsoft Flow, Microsoft Teams, Administratoraktivität, OneDrive for Business, SharePoint Online, E-Mail in der Übertragung und ruhende Postfächer angewendet werden. Skype-Unterhaltungen sind in ruhenden Postfächern enthalten.</span><span class="sxs-lookup"><span data-stu-id="12d16-p103">Next, use alert policies and the Office 365 audit log to monitor activity across Office 365 services. Setup ongoing monitoring or search the audit log to investigate an incident. The Office 365 audit log works across Office 365 services — Sway, PowerBI, eDiscovery, Dynamics 365, Microsoft Flow, Microsoft Teams, Admin activity, OneDrive for Business, SharePoint Online, mail in transit, and mailboxes at rest. Skype conversations are included in mailboxes at rest.</span></span>

- <span data-ttu-id="12d16-p104">Zum Schluss verwenden Sie Microsoft Cloud App Security, um Dateien mit vertraulichen Daten in anderen SaaS-Anbietern zu überwachen. In Kürze können Typen vertraulicher Informationen von Office 365 und einheitliche Beschriftungen für Azure Information Protection und Office mit Cloud App Security verwendet werden. Sie können Richtlinien einrichten, die für alle Ihre SaaS-Apps oder für bestimmte Apps (beispielsweise Box) gelten. Mit Cloud App Security können keine Dateien in Exchange Online ermittelt werden, auch keine an E-Mails angefügten Dateien.</span><span class="sxs-lookup"><span data-stu-id="12d16-p104">Finally, Use Microsoft Cloud App Security to monitor files with sensitive data in other SaaS providers. Coming soon is the ability to use Office 365 sensitive information types and unified labels across Azure Information Protection and Office with Cloud App Security. You can setup policies that apply to all of your SaaS apps or specific apps (like Box). Cloud App Security doesn't discover files in Exchange Online, including files attached to email.</span></span>

## <a name="office-365-data-loss-prevention-reports"></a><span data-ttu-id="12d16-119">Berichte zur Verhinderung von Datenverlust in Office 365</span><span class="sxs-lookup"><span data-stu-id="12d16-119">Office 365 data loss prevention reports</span></span>

<span data-ttu-id="12d16-p105">Nachdem Sie DLP-Richtlinien (Data Loss Prevention, Verhinderung von Datenverlust) erstellt haben, müssen Sie sicherstellen, dass diese wie gewünscht funktionieren und Sie bei der Richtlinieneinhaltung unterstützen. Mithilfe der DLP-Berichte in Office 365 können Sie schnell die Anzahl der DLP-Richtlinienentsprechungen, -Außerkraftsetzungen oder falsch positiven Resultate anzeigen, ermitteln, ob sie im Laufe der Zeit einen Aufwärts- oder Abwärtstrend aufweisen, den Bericht auf verschiedene Weisen filtern und zusätzliche Details anzeigen, indem Sie einen Punkt in einer Zeile oder im Diagramm auswählen.</span><span class="sxs-lookup"><span data-stu-id="12d16-p105">After you create your data loss prevention (DLP) policies, you'll want to verify that they're working as you intended and helping you to stay compliant. With the DLP reports in Office 365, you can quickly view the number of DLP policy matches, overrides, or false positives; see whether they're trending up or down over time; filter the report in different ways; and view additional details by selecting a point on a line on the graph.</span></span>

<span data-ttu-id="12d16-122">Sie können die DLP-Berichte für Folgendes verwenden:</span><span class="sxs-lookup"><span data-stu-id="12d16-122">You can use the DLP reports to:</span></span>

- <span data-ttu-id="12d16-123">Sie können sich auf bestimmte Zeiträume konzentrieren und so mehr über die Gründe für Spitzen und Trends erfahren.</span><span class="sxs-lookup"><span data-stu-id="12d16-123">Focus on specific time periods and understand the reasons for spikes and trends.</span></span>

- <span data-ttu-id="12d16-124">Sie können die Geschäftsprozesse ermitteln, die gegen die DLP-Richtlinien Ihrer Organisation verstoßen.</span><span class="sxs-lookup"><span data-stu-id="12d16-124">Discover business processes that violate your organization's DLP policies.</span></span>

- <span data-ttu-id="12d16-125">Sie können die geschäftlichen Auswirkungen der DLP-Richtlinien besser nachvollziehen.</span><span class="sxs-lookup"><span data-stu-id="12d16-125">Understand any business impact of the DLP policies.</span></span>

- <span data-ttu-id="12d16-126">Zeigen Sie die Begründungen an, die von Benutzern gesendet werden, wenn diese einen Richtlinientipp durch Außerkraftsetzen der Richtlinie oder durch Melden eines falsch positiven Resultats lösen.</span><span class="sxs-lookup"><span data-stu-id="12d16-126">View the justifications submitted by users when they resolve a policy tip by overriding the policy or reporting a false positive.</span></span>

- <span data-ttu-id="12d16-127">Sie können die Einhaltung einer bestimmten DLP-Richtlinie durch Anzeigen von Übereinstimmungen für diese Richtlinie überprüfen.</span><span class="sxs-lookup"><span data-stu-id="12d16-127">Verify compliance with a specific DLP policy by showing any matches for that policy.</span></span>

- <span data-ttu-id="12d16-128">Sie können Detailbereich eine Liste von Dateien mit vertraulichen Daten anzeigen, die mit den DLP-Richtlinien übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="12d16-128">View a list of files with sensitive data that matches your DLP policies in the details pane.</span></span>

<span data-ttu-id="12d16-129">Darüber hinaus können Sie anhand der DLP-Berichte Ihre DLP-Richtlinien bei der Ausführung im Testmodus genauer anpassen.</span><span class="sxs-lookup"><span data-stu-id="12d16-129">In addition, you can use the DLP reports to fine tune your DLP policies as you run them in test mode.</span></span>

<span data-ttu-id="12d16-130">DLP-Berichte finden sich im Security Center und Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="12d16-130">DLP reports are in the security center and the compliance center.</span></span> <span data-ttu-id="12d16-131">Navigieren Sie zu Berichte \> Berichte anzeigen.</span><span class="sxs-lookup"><span data-stu-id="12d16-131">Navigate to Reports \> View reports.</span></span> <span data-ttu-id="12d16-132">Wechseln Sie unter „Verhinderung von Datenverlust (Data Loss Prevention, DLP)“ entweder zu „DLP-Richtlinien- und -Regelübereinstimmungen“ oder zu „Falsch positive Meldungen der DLP-Richtlinie und Außerkraftsetzungen“.</span><span class="sxs-lookup"><span data-stu-id="12d16-132">Under Data loss prevention (DLP), go to either DLP policy and rule matches or DLP false positives and overrides.</span></span>

<span data-ttu-id="12d16-133">Weitere Informationen finden Sie unter [Anzeigen der Berichte zur Verhinderung von Datenverlust](https://docs.microsoft.com/microsoft-365/compliance/view-the-dlp-reports).</span><span class="sxs-lookup"><span data-stu-id="12d16-133">For more information, see [View the reports for data loss prevention](https://docs.microsoft.com/microsoft-365/compliance/view-the-dlp-reports).</span></span>

![Bericht mit DLP-Richtlinienübereinstimmungen](../../media/Monitor-for-leaks-of-personal-data-image2.png)

## <a name="office-365-audit-log-and-alert-policies"></a><span data-ttu-id="12d16-135">Office 365-Überwachungsprotokoll und Warnungsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="12d16-135">Office 365 audit log and alert policies</span></span>

<span data-ttu-id="12d16-136">Das Office 365-Überwachungsprotokoll enthält Ereignisse von Exchange Online, SharePoint Online, OneDrive for Business, Azure Active Directory, Microsoft Teams, Power BI, Sway und anderen Office 365-Diensten.</span><span class="sxs-lookup"><span data-stu-id="12d16-136">The Office 365 audit log contains events from Exchange Online, SharePoint Online, OneDrive for Business, Azure Active Directory, Microsoft Teams, Power BI, Sway, and other Office 365 services.</span></span>

<span data-ttu-id="12d16-137">Security Center und Compliance Center bieten zwei Möglichkeiten zum Überwachen und Berichten anhand des Office 365-Überwachungsprotokolls:</span><span class="sxs-lookup"><span data-stu-id="12d16-137">The security center and compliance center provide two ways to monitor and report against the Office 365 audit log:</span></span>

- <span data-ttu-id="12d16-138">Einrichten von Warnungsrichtlinien, Anzeigen von Warnungen und überwachen von Trends – Verwenden Sie die Warnungsrichtlinien- und Warnungsdashboardtools im Security oder Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="12d16-138">Setup alert policies, view alerts, and monitor trends — Use the alert policy and alert dashboard tools in either the security center or compliance center.</span></span>

- <span data-ttu-id="12d16-p107">Direktes Durchsuchen des Überwachungsprotokolls – Suchen Sie nach allen Ereignissen in einem bestimmten Datumsbereich. Oder filtern Sie die Ergebnisse nach bestimmten Kriterien, z. B. nach dem Benutzer, der die Aktion ausgeführt hat, der Aktion oder dem Zielobjekt.</span><span class="sxs-lookup"><span data-stu-id="12d16-p107">Search the audit log directly — Search for all events in a specified date rage. Or you can filter the results based on specific criteria, such as the user who performed the action, the action, or the target object.</span></span>

<span data-ttu-id="12d16-p108">Informationenssicherheits- und Compliance-Teams können diese Tools verwenden, um von Endbenutzern und Administratoren in Office 365-Diensten ausgeführte Aktivitäten proaktiv zu überprüfen. Automatische Warnungen können konfiguriert werden, sodass E-Mail-Benachrichtigungen gesendet werden, wenn bestimmte Aktivitäten für bestimmte Websitesammlungen auftreten – z. B., wenn Inhalte von Websites freigegeben werden, die bekanntermaßen DSGVO-relevante Informationen enthalten. Dadurch können sich die Teams gezielt an die Benutzer wenden, um sicherzustellen, dass die Sicherheitsrichtlinien des Unternehmens eingehalten werden. Oder sie können zusätzliche Schulung bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="12d16-p108">Information security and compliance teams can use these tools to proactively review activities performed by both end users and administrators across Office 365 services. Automatic alerts can be configured to send email notifications when certain activities occur on specific site collections - for example when content is shared from sites known to contain GDPR related information. This allows those teams to follow up with users to ensure that corporate security policies are followed, or to provide additional training.</span></span>

<span data-ttu-id="12d16-p109">Informationssicherheitsteams können auch das Überwachungsprotokoll durchsuchen, um einen vermeintlichen Datenmissbrauch zu untersuchen sowie Ursache und Ausmaß der Verletzung zu bestimmen. Diese integrierte Funktionalität erleichtert die Einhaltung der Artikel 33 und 34 der DSGVO. Diese verlangen bei einer Datenpanne die Benachrichtigung der Aufsichtsbehörde der DSGVO und der betroffenen Person selbst innerhalb eines bestimmten Zeitraums. Einträge im Überwachungsprotokoll werden nur 90 Tage lang im Dienst aufbewahrt. Häufig empfiehlt es sich, und viele Organisationen erfordern dies, dass die Protokolle länger aufbewahrt werden.</span><span class="sxs-lookup"><span data-stu-id="12d16-p109">Information security teams can also search the audit log to investigate suspected data breaches and determine both root cause and the extent of the breach. This built in capability facilitates compliance with article 33 and 34 of the GDPR, which require notifications be provided to the GDPR supervisory authority and to the data subjects themselves of a data breach within a specific time period. Audit log entries are only retained for 90 days within the service - it is often recommended and many organizations required that these logs be retained for longer periods of time.</span></span>

<span data-ttu-id="12d16-p110">Es sind Lösungen verfügbar, die über die Microsoft Verwaltungsaktivitäts-API die einheitlichen Überwachungsprotokolle (Unified Audit Logs) abonnieren und beide Protokolleinträge nach Bedarf speichern können. Diese bieten erweiterte Dashboards und Warnungen. Ein Beispiel hierfür ist [Microsoft Operations Management Suite (OMS)](https://docs.microsoft.com/azure/operations-management-suite/oms-solution-office-365).</span><span class="sxs-lookup"><span data-stu-id="12d16-p110">Solutions are available which subscribe to the Unified Audit Logs through the Microsoft Management Activity API and can both store log entries as needed, and provide advanced dashboards and alerts. One example is [Microsoft Operations Management Suite (OMS)](https://docs.microsoft.com/azure/operations-management-suite/oms-solution-office-365).</span></span>

<span data-ttu-id="12d16-149">Weitere Informationen zu Warnungsrichtlinien und zum Durchsuchen des Überwachungsprotokolls finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="12d16-149">More information about alert policies and searching the audit log:</span></span>

- [<span data-ttu-id="12d16-150">Warnungsrichtlinien im Microsoft 365 Security oder Compliance Center</span><span class="sxs-lookup"><span data-stu-id="12d16-150">Alert policies in the Microsoft 365 security and compliance centers</span></span>](https://docs.microsoft.com/microsoft-365/compliance/alert-policies)

- <span data-ttu-id="12d16-151">[Durchsuchen des Überwachungsprotokolls nach Benutzer- und Administratoraktivitäten in Office 365](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log) (Einführung)</span><span class="sxs-lookup"><span data-stu-id="12d16-151">[Search the audit log for user and admin activity in Office 365](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log) (introduction)</span></span>

- [<span data-ttu-id="12d16-152">Aktivieren oder Deaktivieren der Office 365-Überwachungsprotokollsuche</span><span class="sxs-lookup"><span data-stu-id="12d16-152">Turn Office 365 audit log search on or off</span></span>](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off)

- [<span data-ttu-id="12d16-153">Durchsuchen des Überwachungsprotokolls</span><span class="sxs-lookup"><span data-stu-id="12d16-153">Search the audit log</span></span>](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)

- <span data-ttu-id="12d16-154">[Search-UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-unifiedauditlog) (Cmdlet)</span><span class="sxs-lookup"><span data-stu-id="12d16-154">[Search-UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-unifiedauditlog) (cmdlet)</span></span>

- [<span data-ttu-id="12d16-155">Detaillierte Eigenschaften im Office 365-Überwachungsprotokoll</span><span class="sxs-lookup"><span data-stu-id="12d16-155">Detailed properties in the Office 365 audit log</span></span>](https://docs.microsoft.com/microsoft-365/compliance/detailed-properties-in-the-office-365-audit-log)

## <a name="microsoft-cloud-app-security"></a><span data-ttu-id="12d16-156">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="12d16-156">Microsoft Cloud App Security</span></span>

<span data-ttu-id="12d16-157">Microsoft Cloud App Security hilft Ihnen bei der Ermittlung weiterer SaaS-Apps, die im Netzwerk verwendet werden, und vertraulicher Daten, die an diese und von diesen Apps gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="12d16-157">Microsoft Cloud App Security helps you discover other SaaS apps in use across your networks and sensitive data that is sent to and from these apps.</span></span>

<span data-ttu-id="12d16-p111">Microsoft Cloud App Security ist ein umfassender Dienst, der tiefe Einsichten, differenzierte Kontrolle und erweiterten Bedrohungsschutz für Ihre Cloud-Apps bietet. Mehr als 15.000 Cloudanwendungen in Ihrem Netzwerk – von allen Geräten – werden identifiziert und durch kontinuierliche Risikobewertung und Analyse bewertet. Es sind keine Agenten erforderlich: Die Informationen werden von den Firewalls und Proxys erhoben, um Ihnen einen vollständigen Einblick und Kontext für die Cloudverwendung und Schatten-IT zu liefern.</span><span class="sxs-lookup"><span data-stu-id="12d16-p111">Microsoft Cloud App Security is a comprehensive service providing deep visibility, granular controls and enhanced threat protection for your cloud apps. It identifies more than 15,000 cloud applications in your network-from all devices-and provides risk scoring and ongoing risk assessment and analytics. No agents required: information is collected from your firewalls and proxies to give you complete visibility and context for cloud usage and shadow IT.</span></span>

<span data-ttu-id="12d16-p112">Zum besseren Verständnis Ihrer Cloudumgebung bietet das Untersuchungsfeature von Cloud App Security umfassende Einblicke in alle Aktivitäten, Dateien und Konten für sanktionierte und verwaltete Apps. Sie können ausführliche Informationen auf Dateiebene erhalten und ermitteln, wo Daten zwischen den Cloud-Apps übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="12d16-p112">To better understand your cloud environment, Cloud App Security investigate feature provides deep visibility into all activities, files and accounts for sanctioned and managed apps. You can gain detailed information on a file level and discover where data travels in the cloud apps.</span></span>

<span data-ttu-id="12d16-163">Die folgende Abbildung veranschaulicht zwei Cloud App Security-Richtlinien, die für die DSGVO hilfreich sind.</span><span class="sxs-lookup"><span data-stu-id="12d16-163">For examples, the following illustration demonstrates two Cloud App Security policies that can help with GDPR.</span></span>

![Beispielrichtlinien für Cloud App Security](../../media/Monitor-for-leaks-of-personal-data-image3.png)

<span data-ttu-id="12d16-165">Die erste Richtlinie gibt eine Warnung aus, wenn Dateien mit einem vordefinierten PII-Attribut oder einem ausgewählten benutzerdefinierten Ausdruck außerhalb der Organisation von den ausgewählten SaaS-Apps freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="12d16-165">The first policy alerts when files with a predefined PII attribute or custom expression that you choose is shared outside the organization from the SaaS apps that you choose.</span></span>

<span data-ttu-id="12d16-p113">Die zweite Richtlinie blockiert Downloads von Dateien auf alle nicht verwalteten Geräte. Sie wählen die Attribute in den Dateien aus, nach denen gesucht wird, und die SaaS-Apps, für die die Richtlinie gelten soll.</span><span class="sxs-lookup"><span data-stu-id="12d16-p113">The second policy blocks downloads of files to any unmanaged device. You choose the attributes within the files to look for and the SaaS apps you want the policy to apply to.</span></span>

<span data-ttu-id="12d16-168">Die folgenden Attributtypen werden in Kürze in Cloud App Security verfügbar sein:</span><span class="sxs-lookup"><span data-stu-id="12d16-168">These attribute types are coming soon to Cloud App Security:</span></span>

- <span data-ttu-id="12d16-169">Typen vertraulicher Informationen in Office 365</span><span class="sxs-lookup"><span data-stu-id="12d16-169">Office 365 sensitive information types</span></span>

- <span data-ttu-id="12d16-170">Einheitliche Beschriftungen in Office 365 und Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="12d16-170">Unified labels across Office 365 and Azure Information Protection</span></span>

### <a name="cloud-app-security-dashboard"></a><span data-ttu-id="12d16-171">Cloud App Security-Dashboard</span><span class="sxs-lookup"><span data-stu-id="12d16-171">Cloud App Security dashboard</span></span>

<span data-ttu-id="12d16-p114">Wenn Sie Cloud App Security noch nicht verwenden, starten Sie es zunächst. So greifen Sie auf Cloud App Security zu: <https://portal.cloudappsecurity.com></span><span class="sxs-lookup"><span data-stu-id="12d16-p114">If you haven't yet started to use Cloud App Security, begin by starting it up. To access Cloud App Security: <https://portal.cloudappsecurity.com>.</span></span>

<span data-ttu-id="12d16-p115">Hinweis: Aktivieren Sie unbedingt „Automatisch Dateien auf Azure Information Protection-Klassifizierungsbezeichnungen überprüfen“ (in den allgemeinen Einstellungen), entweder bei den ersten Schritten mit Cloud App Security oder bevor Sie Bezeichnungen zuweisen. Nach der Installation überprüft Cloud App Security vorhandene Dateien erst wieder, wenn sie geändert werden.</span><span class="sxs-lookup"><span data-stu-id="12d16-p115">Note: Be sure to enable 'Automatically scan files for Azure Information Protection classification labels' (in General settings) when getting started with Cloud App Security or before you assign labels. After setup, Cloud App Security does not scan existing files again until they are modified.</span></span>

![Dashboard mit Informationen zu Warnungen](../../media/Monitor-for-leaks-of-personal-data-image4.png)

<span data-ttu-id="12d16-177">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="12d16-177">More information:</span></span>

- [<span data-ttu-id="12d16-178">Bereitstellen von Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="12d16-178">Deploy Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security)

- [<span data-ttu-id="12d16-179">Weitere Informationen zu Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="12d16-179">More information about Microsoft Cloud App Security</span></span>](https://www.microsoft.com/cloud-platform/cloud-app-security)

- [<span data-ttu-id="12d16-180">Blockieren von Downloads vertraulicher Daten mithilfe des Microsoft Cloud App Security-Proxys</span><span class="sxs-lookup"><span data-stu-id="12d16-180">Block downloads of sensitive information using the Microsoft Cloud App Security proxy</span></span>](https://docs.microsoft.com/cloud-app-security/use-case-proxy-block-session-aad)

## <a name="example-file-and-activity-policies-to-detect-sharing-of-personal-data"></a><span data-ttu-id="12d16-181">Beispieldatei und Aktivitätsrichtlinien zum Erkennen der Freigabe von personenbezogenen Daten</span><span class="sxs-lookup"><span data-stu-id="12d16-181">Example file and activity policies to detect sharing of personal data</span></span>

### <a name="detect-sharing-of-files-containing-pii--credit-card-number"></a><span data-ttu-id="12d16-182">Freigabe von Dateien mit PII erkennen – Kreditkartennummer</span><span class="sxs-lookup"><span data-stu-id="12d16-182">Detect sharing of files containing PII — Credit card number</span></span>

<span data-ttu-id="12d16-183">Benachrichtigen, wenn eine Datei mit einer Kreditkartennummer von einer genehmigten Cloud-App freigegeben wird.</span><span class="sxs-lookup"><span data-stu-id="12d16-183">Alert when a file containing a credit card number is shared from an approved cloud app.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="12d16-184"><strong>Steuerelement</strong></span><span class="sxs-lookup"><span data-stu-id="12d16-184"><strong>Control</strong></span></span></th>
<th align="left"><span data-ttu-id="12d16-185"><strong>Einstellungen</strong></span><span class="sxs-lookup"><span data-stu-id="12d16-185"><strong>Settings</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="12d16-186">Richtlinientyp</span><span class="sxs-lookup"><span data-stu-id="12d16-186">Policy type</span></span></td>
<td align="left"><span data-ttu-id="12d16-187">Dateirichtlinie</span><span class="sxs-lookup"><span data-stu-id="12d16-187">File policy</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="12d16-188">Richtlinienvorlage</span><span class="sxs-lookup"><span data-stu-id="12d16-188">Policy template</span></span></td>
<td align="left"><span data-ttu-id="12d16-189">Keine Vorlage</span><span class="sxs-lookup"><span data-stu-id="12d16-189">No template</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="12d16-190">Schweregrad der Richtlinie</span><span class="sxs-lookup"><span data-stu-id="12d16-190">Policy severity</span></span></td>
<td align="left"><span data-ttu-id="12d16-191">Hoch</span><span class="sxs-lookup"><span data-stu-id="12d16-191">High</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="12d16-192">Kategorie</span><span class="sxs-lookup"><span data-stu-id="12d16-192">Category</span></span></td>
<td align="left"><span data-ttu-id="12d16-193">DLP</span><span class="sxs-lookup"><span data-stu-id="12d16-193">DLP</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="12d16-194">Filtereinstellungen</span><span class="sxs-lookup"><span data-stu-id="12d16-194">Filter settings</span></span></td>
<td align="left"><p><span data-ttu-id="12d16-195">Zugriffsebene = Öffentlich (Internet), Öffentlich, Extern</span><span class="sxs-lookup"><span data-stu-id="12d16-195">Access level = Public (Internet), Public, External</span></span></p>
<p><span data-ttu-id="12d16-196">App = &lt;Apps auswählen&gt; (verwenden Sie diese Einstellung, wenn Sie bestimmte SaaS-Apps überwachen möchten)</span><span class="sxs-lookup"><span data-stu-id="12d16-196">App = &lt;select apps&gt; (use this setting if you want to limit monitoring to specific SaaS apps)</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="12d16-197">Übernehmen für</span><span class="sxs-lookup"><span data-stu-id="12d16-197">Apply to</span></span></td>
<td align="left"><span data-ttu-id="12d16-198">Alle Dateien, alle Besitzer</span><span class="sxs-lookup"><span data-stu-id="12d16-198">All files, all owners</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="12d16-199">Inhaltsuntersuchung</span><span class="sxs-lookup"><span data-stu-id="12d16-199">Content inspection</span></span></td>
<td align="left"><p><span data-ttu-id="12d16-200">Schließt Dateien ein, die einem vorhanden Ausdruck entsprechen: Alle Länder: Finanzen: Kreditkartennummer</span><span class="sxs-lookup"><span data-stu-id="12d16-200">Includes files that match a present expression: All countries: Finance: Credit card number</span></span></p>
<p><span data-ttu-id="12d16-201">Kein relevanter Kontext erforderlich: deaktiviert (Dies entspricht sowohl Schlüsselwörtern als auch RegEx)</span><span class="sxs-lookup"><span data-stu-id="12d16-201">Don't require relevant context: unchecked (this will match keywords as well as regex)</span></span></p>
<p><span data-ttu-id="12d16-202">Schließt Dateien mit mindestens 1 Übereinstimmung ein</span><span class="sxs-lookup"><span data-stu-id="12d16-202">Includes files with at least 1 match</span></span></p>
<p><span data-ttu-id="12d16-203">Maskierung der letzten 4 Zeichen eines Verstoßes aufheben: aktiviert</span><span class="sxs-lookup"><span data-stu-id="12d16-203">Unmask the last 4 characters of the violation: checked</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="12d16-204">Warnungen</span><span class="sxs-lookup"><span data-stu-id="12d16-204">Alerts</span></span></td>
<td align="left"><p><span data-ttu-id="12d16-205">Warnung für jede übereinstimmende Datei erstellen: aktiviert</span><span class="sxs-lookup"><span data-stu-id="12d16-205">Create an alert for each matching file: checked</span></span></p>
<p><span data-ttu-id="12d16-206">Limit für tägliche Warnungen: 1000</span><span class="sxs-lookup"><span data-stu-id="12d16-206">Daily alert limit: 1000</span></span></p>
<p><span data-ttu-id="12d16-207">Warnung als E-Mail auswählen: aktiviert</span><span class="sxs-lookup"><span data-stu-id="12d16-207">Select an alert as email: checked</span></span></p>
<p><span data-ttu-id="12d16-208">An: infosec@contoso.com</span><span class="sxs-lookup"><span data-stu-id="12d16-208">To: infosec@contoso.com</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="12d16-209">Governance</span><span class="sxs-lookup"><span data-stu-id="12d16-209">Governance</span></span></td>
<td align="left"><p><span data-ttu-id="12d16-210">Microsoft OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="12d16-210">Microsoft OneDrive for Business</span></span></p>
<p><span data-ttu-id="12d16-211">Als privat festlegen: Aktivieren Sie „Externe Benutzer entfernen“</span><span class="sxs-lookup"><span data-stu-id="12d16-211">Make private: check Remove External Users</span></span></p>
<p><span data-ttu-id="12d16-212">Alle anderen Einstellungen: deaktiviert</span><span class="sxs-lookup"><span data-stu-id="12d16-212">All other settings: unchecked</span></span></p>
<p><span data-ttu-id="12d16-213">Microsoft SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="12d16-213">Microsoft SharePoint Online</span></span></p>
<p><span data-ttu-id="12d16-214">Als privat festlegen: Aktivieren Sie „Externe Benutzer entfernen“</span><span class="sxs-lookup"><span data-stu-id="12d16-214">Make private: check Remove External Users</span></span></p>
<p><span data-ttu-id="12d16-215">Alle anderen Einstellungen: deaktiviert</span><span class="sxs-lookup"><span data-stu-id="12d16-215">All other settings: unchecked</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="12d16-216">Ähnliche Richtlinien:</span><span class="sxs-lookup"><span data-stu-id="12d16-216">Similar policies:</span></span>

- <span data-ttu-id="12d16-217">Ermitteln der Freigabe von Dateien mit PII – E-Mail-Adresse</span><span class="sxs-lookup"><span data-stu-id="12d16-217">Detect sharing of Files containing PII - Email Address</span></span>

- <span data-ttu-id="12d16-218">Ermitteln der Freigabe von Dateien mit PII – Reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="12d16-218">Detect sharing of Files containing PII - Passport Number</span></span>

### <a name="detect-customer-or-hr-data-in-box-or-onedrive-for-business"></a><span data-ttu-id="12d16-219">Ermitteln von Kunden- oder Personaldaten in Box oder OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="12d16-219">Detect Customer or HR Data in Box or OneDrive for Business</span></span>

<span data-ttu-id="12d16-220">Benachrichtigen, wenn eine Datei mit der Bezeichnung „Kundendaten“ oder „Personaldaten“ in OneDrive for Business oder Box hochgeladen wird.</span><span class="sxs-lookup"><span data-stu-id="12d16-220">Alert when a file labeled as Customer Data or HR Data is uploaded to OneDrive for Business or Box.</span></span>

<span data-ttu-id="12d16-221">Hinweise:</span><span class="sxs-lookup"><span data-stu-id="12d16-221">Notes:</span></span>

- <span data-ttu-id="12d16-222">Zum Überwachen von Box muss mithilfe des API-Connector-SDK ein Connector konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="12d16-222">Box monitoring requires a connector be configured using the API Connector SDK.</span></span>

- <span data-ttu-id="12d16-223">Diese Richtlinie erfordert Funktionen, die sich derzeit im privaten Vorschaumodus befinden.</span><span class="sxs-lookup"><span data-stu-id="12d16-223">This policy requires capabilities that are currently in private preview.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="12d16-224"><strong>Steuerelement</strong></span><span class="sxs-lookup"><span data-stu-id="12d16-224"><strong>Control</strong></span></span></th>
<th align="left"><span data-ttu-id="12d16-225"><strong>Einstellungen</strong></span><span class="sxs-lookup"><span data-stu-id="12d16-225"><strong>Settings</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="12d16-226">Richtlinientyp</span><span class="sxs-lookup"><span data-stu-id="12d16-226">Policy type</span></span></td>
<td align="left"><span data-ttu-id="12d16-227">Aktivitätsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="12d16-227">Activity policy</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="12d16-228">Richtlinienvorlage</span><span class="sxs-lookup"><span data-stu-id="12d16-228">Policy template</span></span></td>
<td align="left"><span data-ttu-id="12d16-229">Keine Vorlage</span><span class="sxs-lookup"><span data-stu-id="12d16-229">No template</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="12d16-230">Schweregrad der Richtlinie</span><span class="sxs-lookup"><span data-stu-id="12d16-230">Policy severity</span></span></td>
<td align="left"><span data-ttu-id="12d16-231">Hoch</span><span class="sxs-lookup"><span data-stu-id="12d16-231">High</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="12d16-232">Kategorie</span><span class="sxs-lookup"><span data-stu-id="12d16-232">Category</span></span></td>
<td align="left"><span data-ttu-id="12d16-233">Freigabesteuerelement</span><span class="sxs-lookup"><span data-stu-id="12d16-233">Sharing Control</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="12d16-234">Aktion ausführen bei</span><span class="sxs-lookup"><span data-stu-id="12d16-234">Act on</span></span></td>
<td align="left"><span data-ttu-id="12d16-235">Einzelne Aktivität</span><span class="sxs-lookup"><span data-stu-id="12d16-235">Single activity</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="12d16-236">Filtereinstellungen</span><span class="sxs-lookup"><span data-stu-id="12d16-236">Filter settings</span></span></td>
<td align="left"><p><span data-ttu-id="12d16-237">Aktivitätstyp = Dateiupload</span><span class="sxs-lookup"><span data-stu-id="12d16-237">Activity type = Upload File</span></span></p>
<p><span data-ttu-id="12d16-238">App = Microsoft OneDrive for Business und Box</span><span class="sxs-lookup"><span data-stu-id="12d16-238">App = Microsoft OneDrive for Business and Box</span></span></p>
<p><span data-ttu-id="12d16-239">Klassifizierungsbezeichnung (derzeit im privaten Vorschaumodus): Azure Information Protection = Kundendaten, Personalwesen – Gehaltsinformationen, Personalwesen – Mitarbeiterdaten</span><span class="sxs-lookup"><span data-stu-id="12d16-239">Classification Label (currently in private preview): Azure Information Protection = Customer Data, Human Resources—Salary Data, Human Resources—Employee Data</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="12d16-240">Warnungen</span><span class="sxs-lookup"><span data-stu-id="12d16-240">Alerts</span></span></td>
<td align="left"><p><span data-ttu-id="12d16-241">Warnung erstellen: aktiviert</span><span class="sxs-lookup"><span data-stu-id="12d16-241">Create an alert: checked</span></span></p>
<p><span data-ttu-id="12d16-242">Limit für tägliche Warnungen: 1000</span><span class="sxs-lookup"><span data-stu-id="12d16-242">Daily alert limit: 1000</span></span></p>
<p><span data-ttu-id="12d16-243">Warnung als E-Mail auswählen: aktiviert</span><span class="sxs-lookup"><span data-stu-id="12d16-243">Select an alert as email: checked</span></span></p>
<p><span data-ttu-id="12d16-244">An: infosec@contoso.com</span><span class="sxs-lookup"><span data-stu-id="12d16-244">To: infosec@contoso.com</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="12d16-245">Governance</span><span class="sxs-lookup"><span data-stu-id="12d16-245">Governance</span></span></td>
<td align="left"><p><span data-ttu-id="12d16-246">Alle Apps</span><span class="sxs-lookup"><span data-stu-id="12d16-246">All apps</span></span></p>
<p><span data-ttu-id="12d16-247">Unter Benutzerquarantäne stellen: aktiviert</span><span class="sxs-lookup"><span data-stu-id="12d16-247">Put user in quarantine: check</span></span></p>
<p><span data-ttu-id="12d16-248">Alle anderen Einstellungen: deaktiviert</span><span class="sxs-lookup"><span data-stu-id="12d16-248">All other settings: unchecked</span></span></p>
<p><span data-ttu-id="12d16-249">Office 365</span><span class="sxs-lookup"><span data-stu-id="12d16-249">Office 365</span></span></p>
<p><span data-ttu-id="12d16-250">Unter Benutzerquarantäne stellen: aktiviert</span><span class="sxs-lookup"><span data-stu-id="12d16-250">Put user in quarantine: check</span></span></p>
<p><span data-ttu-id="12d16-251">Alle anderen Einstellungen: deaktiviert</span><span class="sxs-lookup"><span data-stu-id="12d16-251">All other settings: unchecked</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="12d16-252">Ähnliche Richtlinien:</span><span class="sxs-lookup"><span data-stu-id="12d16-252">Similar policies:</span></span>

- <span data-ttu-id="12d16-253">Erkennung umfangreicher Downloads von Kundendaten oder Personaldaten – Warnung, wenn eine große Anzahl von Dateien mit Kundendaten oder Personaldaten erkannt wurden, die von einem einzelnen Benutzer innerhalb eines kurzen Zeitraums heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="12d16-253">Detect large downloads of Customer data or HR Data — Alert when a large number of files containing customer data or HR data have been detected being downloaded by a single user within a short period of time.</span></span>

- <span data-ttu-id="12d16-254">Erkennung der Freigabe von Kunden- und Personaldaten – Warnung, wenn Dateien mit Kunden- oder Personaldaten freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="12d16-254">Detect Sharing of Customer and HR Data — Alert when files containing Customer or HR Data are shared.</span></span>
