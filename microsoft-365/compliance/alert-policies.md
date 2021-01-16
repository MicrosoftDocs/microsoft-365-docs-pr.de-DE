---
title: Warnungsrichtlinien im Security and Compliance Center
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
ms.assetid: 8927b8b9-c5bc-45a8-a9f9-96c732e58264
ms.custom:
- seo-marvel-apr2020
description: Erstellen Sie Warnungsrichtlinien im Security and Compliance Center in Office 365 und Microsoft 365, um potenzielle Bedrohungen, Datenverluste und Berechtigungsprobleme zu überwachen.
ms.openlocfilehash: a0bf22b8dc4f8b3c40b60509b4230922ba762024
ms.sourcegitcommit: 31be333178b934c519f419656f4c3a53e1beffdc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2021
ms.locfileid: "49881818"
---
# <a name="alert-policies-in-the-security-and-compliance-center"></a>Warnungsrichtlinien im Security & Compliance Center

Sie können die Tools für die Warnungsrichtlinie und das Warnungsdashboard im Microsoft 365 Security and Compliance Center verwenden, um Warnungsrichtlinien zu erstellen und dann die Warnungen anzuzeigen, die generiert werden, wenn Benutzer Aktivitäten ausführen, die den Bedingungen einer Warnungsrichtlinie entsprechen. Es gibt mehrere Standardmäßige Benachrichtigungsrichtlinien, mit deren Hilfe Sie Aktivitäten überwachen können, z. B. das Zuweisen von Administratorrechten in Exchange Online, Schadsoftwareangriffe, Phishingkampagnen und ungewöhnliche Ebenen der Dateilöschung und externen Freigabe.

Mit Warnungsrichtlinien können Sie die durch eine Richtlinie ausgelösten Warnungen kategorisieren, die Richtlinie auf alle Benutzer in Ihrer Organisation anwenden, einen Schwellenwert festlegen, wenn eine Warnung ausgelöst wird, und entscheiden, ob E-Mail-Benachrichtigungen empfangen werden sollen, wenn Warnungen ausgelöst werden. Es gibt auch  eine Seite "Benachrichtigungen anzeigen" im Security and Compliance Center, auf der Sie Warnungen anzeigen und filtern, einen Warnungsstatus festlegen können, der Ihnen bei der Verwaltung von Warnungen hilft, und dann Warnungen schließen können, nachdem Sie den zugrunde liegenden Vorfall behoben oder behoben haben.

> [!NOTE]
> Warnungsrichtlinien sind für Organisationen mit einem Microsoft 365 Enterprise-, Office 365 Enterprise- oder Office 365 US Government E1/F1/G1-, E3/F3/G3- oder E5/G5-Abonnement verfügbar. Erweiterte Funktionen sind nur für Organisationen mit einem E5/G5-Abonnement oder für Organisationen mit einem E1/F1/G1- oder E3/F3/G3-Abonnement und einem Microsoft Defender für Office 365 P2 oder einem Microsoft 365 E5 Compliance- oder E5 eDiscovery- und Audit-Add-On-Abonnement verfügbar. Die Funktionalität, die ein E5/G5- oder Add-On-Abonnement erfordert, wird in diesem Thema hervorgehoben. Beachten Sie außerdem, dass Warnungsrichtlinien in Office 365 GCC-, GCC High- und DoD US-Behördenumgebungen verfügbar sind.

## <a name="how-alert-policies-work"></a>Funktionsweise von Warnungsrichtlinien

Hier finden Sie eine kurze Übersicht über die Funktionsweise von Warnungsrichtlinien und die Warnungen, die ausgelöst werden, wenn Benutzer- oder Administratoraktivitäten den Bedingungen einer Warnungsrichtlinie entspricht.

![Übersicht über die Funktionsweise von Warnungsrichtlinien](../media/e02a622d-b429-448b-8107-dd1a4770b4e0.png)

1. Ein Administrator in Ihrer Organisation erstellt, konfiguriert und aktiviert  eine Warnungsrichtlinie mithilfe der Seite "Warnungsrichtlinien" im Security and Compliance Center. Sie können Benachrichtigungsrichtlinien auch mithilfe des [Cmdlets New-ProtectionAlert](https://docs.microsoft.com/powershell/module/exchange/new-protectionalert) in Security & Compliance Center PowerShell erstellen.

   Zum Erstellen von Warnungsrichtlinien muss Ihnen die Rolle "Benachrichtigungen verwalten" oder die Rolle "Organisationskonfiguration" im Security and Compliance Center zugewiesen werden.

   > [!NOTE]
   > Es dauert bis zu 24 Stunden nach dem Erstellen oder Aktualisieren einer Warnungsrichtlinie, bevor Warnungen durch die Richtlinie ausgelöst werden können. Dies liegt daran, dass die Richtlinie mit dem Warnungserkennungsmodul synchronisiert werden muss.

2. Ein Benutzer führt eine Aktivität aus, die den Bedingungen einer Warnungsrichtlinie entspricht. Bei Schadsoftwareangriffen lösen infizierte E-Mail-Nachrichten, die an Benutzer in Ihrer Organisation gesendet werden, eine Warnung aus.

3. Microsoft 365 generiert eine Warnung, die  auf der Seite Benachrichtigungen anzeigen im Security & Compliance Center angezeigt wird. Wenn E-Mail-Benachrichtigungen für die Warnungsrichtlinie aktiviert sind, sendet Microsoft außerdem eine Benachrichtigung an eine Liste von Empfängern. Die Warnungen, die ein Administrator oder andere Benutzer auf der Seite Benachrichtigungen anzeigen sehen können, werden durch die Rollen bestimmt, die dem Benutzer zugewiesen sind. Weitere Informationen finden Sie unter [RBAC-Berechtigungen, die zum Anzeigen von Warnungen erforderlich sind.](#rbac-permissions-required-to-view-alerts)

4. Ein Administrator verwaltet Warnungen im Security and Compliance Center. Das Verwalten von Warnungen besteht darin, einen Warnungsstatus zuzuordnen, um Untersuchungen nachverfolgt und zu verwalten.

## <a name="alert-policy-settings"></a>Warnungsrichtlinieneinstellungen

Eine Warnungsrichtlinie besteht aus einer Reihe von Regeln und Bedingungen, die die Benutzer- oder Administratoraktivität definieren, die eine Warnung generiert, eine Liste der Benutzer, die die Warnung auslösen, wenn sie die Aktivität ausführen, und einem Schwellenwert, der definiert, wie oft die Aktivität erfolgen muss, bevor eine Warnung ausgelöst wird. Außerdem kategorisieren Sie die Richtlinie und weisen ihr einen Schweregrad zu. Diese beiden Einstellungen helfen Ihnen bei der Verwaltung von Warnungsrichtlinien (und den Warnungen, die ausgelöst werden, wenn die Richtlinienbedingungen erfüllt werden), da Sie beim Verwalten von Richtlinien und Anzeigen von Warnungen im Security and Compliance Center nach diesen Einstellungen filtern können. Beispielsweise können Sie Warnungen anzeigen, die den Bedingungen derselben Kategorie entsprechen, oder Warnungen mit demselben Schweregrad anzeigen.

Um Warnungsrichtlinien anzuzeigen und zu erstellen, wechseln Sie zu [https://protection.office.com](https://protection.office.com) Benachrichtigungsrichtlinien, und wählen Sie  \> **diese aus.**

![Wählen Sie im Security and Compliance Center Warnungen aus, und wählen Sie dann Benachrichtigungsrichtlinien aus, um Benachrichtigungsrichtlinien anzuzeigen und zu erstellen.](../media/09ebd451-8e84-44e1-aefc-63e70bba4d97.png)

Eine Warnungsrichtlinie besteht aus den folgenden Einstellungen und Bedingungen.

- **Aktivität,** die die Warnung verfolgt – Sie erstellen eine Richtlinie zum Nachverfolgen einer Aktivität oder in einigen Fällen einiger verwandter Aktivitäten, z. B. das Freigeben einer Datei für einen externen Benutzer, indem Sie sie freigeben, Zugriffsberechtigungen zuweisen oder einen anonymen Link erstellen. Wenn ein Benutzer die durch die Richtlinie definierte Aktivität ausführt, wird eine Warnung basierend auf den Einstellungen für den Warnungsschwellenwert ausgelöst.

    > [!NOTE]
    > Die Aktivitäten, die Sie nachverfolgen können, hängen vom Office 365 Enterprise- oder Office 365 US Government-Plan Ihrer Organisation ab. Im Allgemeinen erfordern Aktivitäten im Zusammenhang mit Schadsoftwarekampagnen und Phishingangriffen ein E5/G5-Abonnement oder ein E1/F1/G1- oder E3/F3/G3-Abonnement mit einem [Defender für Office 365](../security/office-365-security/office-365-atp.md) Plan 2-Add-On-Abonnement.

- **Aktivitätsbedingungen:** Für die meisten Aktivitäten können Sie zusätzliche Bedingungen definieren, die erfüllt sein müssen, um eine Warnung auszulösen. Häufige Bedingungen umfassen IP-Adressen (sodass eine Warnung ausgelöst wird, wenn der Benutzer die Aktivität auf einem Computer mit einer bestimmten IP-Adresse oder innerhalb eines IP-Adressbereichs ausführt), ob eine Warnung ausgelöst wird, wenn ein bestimmter Benutzer diese Aktivität ausführt, und ob die Aktivität für einen bestimmten Dateinamen oder eine bestimmte URL ausgeführt wird. Sie können auch eine Bedingung konfigurieren, die eine Warnung auslöst, wenn die Aktivität von einem beliebigen Benutzer in Ihrer Organisation ausgeführt wird. Die verfügbaren Bedingungen sind von der ausgewählten Aktivität abhängig.

- **Wenn die Warnung ausgelöst wird:** Sie können eine Einstellung konfigurieren, die definiert, wie oft eine Aktivität auftreten kann, bevor eine Warnung ausgelöst wird. Auf diese Weise können Sie eine Richtlinie einrichten, um immer dann eine Warnung zu generieren, wenn eine Aktivität den Richtlinienbedingungen entspricht, wenn ein bestimmter Schwellenwert überschritten wird oder wenn das Auftreten der Aktivität, die die Warnung verfolgt, für Ihre Organisation ungewöhnlich wird.

    ![Konfigurieren, wie Warnungen ausgelöst werden, basierend auf dem Auftreten der Aktivität, einem Schwellenwert oder einer ungewöhnlichen Aktivität für Ihre Organisation](../media/97ee1ed2-e7a9-47a2-a980-5f9f63872c65.png)

    Wenn Sie die Einstellung basierend auf ungewöhnlichen Aktivitäten auswählen, richtet Microsoft einen Basiswert ein, der die normale Häufigkeit für die ausgewählte Aktivität definiert. Es dauert bis zu sieben Tage, bis dieser Basisplan festgelegt ist, in dem keine Warnungen generiert werden. Nachdem der Basisplan eingerichtet wurde, wird eine Warnung ausgelöst, wenn die Häufigkeit der von der Warnungsrichtlinie nachverfolgten Aktivität den Basiswert erheblich überschreitet. Für überwachungsbezogene Aktivitäten (z. B. Datei- und Ordneraktivitäten) können Sie einen Basisplan auf der Grundlage eines einzelnen Benutzers oder aller Benutzer in Ihrer Organisation einrichten. für Aktivitäten im Zusammenhang mit Schadsoftware können Sie einen Basisplan basierend auf einer einzelnen Schadsoftwarefamilie, einem einzelnen Empfänger oder allen Nachrichten in Ihrer Organisation einrichten.

    > [!NOTE]
    > Die Möglichkeit, Warnungsrichtlinien basierend auf einem Schwellenwert oder auf ungewöhnlichen Aktivitäten zu konfigurieren, erfordert ein E5/G5-Abonnement oder ein E1/F1/G1- oder E3/F3/G3-Abonnement mit einem Microsoft Defender für Office 365 P2-, Microsoft 365 E5 Compliance- oder Microsoft 365 eDiscovery- und Audit-Add-On-Abonnement. Organisationen mit einem E1/F1/G1- und E3/F3/G3-Abonnement können nur Warnungsrichtlinien erstellen, bei denen bei jeder Aktivität eine Warnung ausgelöst wird.

- **Warnungskategorie:** Zur Unterstützung der Nachverfolgung und Verwaltung der von einer Richtlinie generierten Warnungen können Sie einer Richtlinie eine der folgenden Kategorien zuweisen.

  - Verhinderung von Datenverlust

  - Informationsverwaltung

  - Nachrichtenübermittlung

  - Berechtigungen

  - Bedrohungsverwaltung

  - Sonstige

  Wenn eine Aktivität auftritt, die den Bedingungen der Warnungsrichtlinie entspricht, wird die generierte Warnung mit der in dieser Einstellung definierten Kategorie markiert. Auf diese Weise können Sie Warnungen nachverfolgen und  verwalten, die auf der Seite Benachrichtigungen anzeigen im Security and Compliance Center die gleiche Kategorieeinstellung haben, da Sie Warnungen basierend auf der Kategorie sortieren und filtern können.

- **Warnungsschweregrad:** Ähnlich wie bei der Warnungskategorie weisen Sie Warnungsrichtlinien ein Schweregradattribut (**Niedrig,** **Mittel,** Hoch oder **Informational)** zu. Wenn wie bei der Warnungskategorie eine Aktivität stattfindet, die den Bedingungen der Warnungsrichtlinie entspricht, wird die generierte Warnung mit demselben Schweregrad markiert, der für die Warnungsrichtlinie festgelegt ist. Auch hier können Sie Warnungen mit demselben Schweregrad auf der Seite "Warnungen anzeigen" nachverfolgen **und** verwalten. Beispielsweise können Sie die Liste der Warnungen filtern, sodass nur Warnungen mit einem hohen Schweregrad angezeigt werden. 

    > [!TIP]
    > Erwägen Sie beim Einrichten einer Warnungsrichtlinie, Aktivitäten, die zu schwerwiegenden negativen Folgen führen können, einen höheren Schweregrad zuzuordnen, z. B. das Erkennen von Schadsoftware nach der Übermittlung an Benutzer, das Anzeigen vertraulicher oder klassifizierter Daten, das Freigeben von Daten für externe Benutzer oder andere Aktivitäten, die zu Datenverlust oder Sicherheitsbedrohungen führen können. Dies kann Ihnen helfen, Warnungen und die Aktionen, die Sie zum Untersuchen und Beheben der zugrunde liegenden Ursachen ergreifen, zu priorisieren.

-  E-Mail-Benachrichtigungen : Sie können die Richtlinie so einrichten, dass E-Mail-Benachrichtigungen an eine Liste von Benutzern gesendet (oder nicht) werden, wenn eine Warnung ausgelöst wird. Sie können auch ein tägliches Benachrichtigungslimit festlegen, sodass nach Erreichen der maximalen Anzahl von Benachrichtigungen an diesem Tag keine weiteren Benachrichtigungen für die Warnung gesendet werden. Zusätzlich zu E-Mail-Benachrichtigungen können Sie oder andere Administratoren die Warnungen anzeigen, die von einer Richtlinie auf der Seite **Benachrichtigungen anzeigen ausgelöst** werden. Erwägen Sie das Aktivieren von E-Mail-Benachrichtigungen für Warnungsrichtlinien einer bestimmten Kategorie oder mit einer Einstellung mit höherem Schweregrad.

## <a name="default-alert-policies"></a>Standardbenachrichtigungsrichtlinien

Microsoft stellt integrierte Warnungsrichtlinien zur Verfügung, mit denen Der Missbrauch von Exchange-Administratorberechtigungen, Schadsoftwareaktivitäten, potenzielle externe und interne Bedrohungen sowie Risiken der Informationsverwaltung identifiziert werden können. Auf der **Seite "Warnungsrichtlinien"** sind die Namen dieser integrierten Richtlinien fett formatiert, und der Richtlinientyp ist als **System definiert.** Diese Richtlinien sind standardmäßig aktiviert. Sie können diese Richtlinien deaktivieren (oder erneut aktivieren), eine Liste von Empfängern einrichten, an die E-Mail-Benachrichtigungen gesendet werden sollen, und ein tägliches Benachrichtigungslimit festlegen. Die anderen Einstellungen für diese Richtlinien können nicht bearbeitet werden.

In der folgenden Tabelle werden die verfügbaren Standardbenachrichtigungsrichtlinien und die Kategorie aufgeführt und beschrieben, der die einzelnen Richtlinien zugewiesen sind. Die Kategorie wird verwendet, um zu bestimmen, welche Warnungen ein Benutzer auf der Seite Benachrichtigungen anzeigen anzeigen kann. Weitere Informationen finden Sie unter [RBAC-Berechtigungen, die zum Anzeigen von Warnungen erforderlich sind.](#rbac-permissions-required-to-view-alerts)

In der Tabelle sind auch die office 365 Enterprise- und Office 365 US Government-Pläne aufgeführt, die jeweils erforderlich sind. Einige Standardbenachrichtigungsrichtlinien sind verfügbar, wenn Ihre Organisation zusätzlich zu einem E1/F1/G1- oder E3/F3/G3-Abonnement über das entsprechende Add-On-Abonnement verfügt.

| Standardwarnungsrichtlinie | Beschreibung | Kategorie | Enterprise-Abonnement |
|:-----|:-----|:-----|:-----|
|**Ein potenziell schädlicher URL-Klick wurde erkannt.**|Generiert eine Warnung, wenn ein Benutzer, der durch sichere [Links](../security/office-365-security/atp-safe-links.md) in Ihrer Organisation geschützt ist, auf einen schädlichen Link klickt. Dieses Ereignis wird ausgelöst, wenn Änderungen der URL-Beanknung von Microsoft Defender für Office 365 identifiziert werden oder wenn Benutzer die Seiten für sichere Links außer Kraft setzen (basierend auf der Microsoft 365 Business-Richtlinie für sichere Links in Ihrer Organisation). Diese Warnungsrichtlinie hat eine **Einstellung mit** hohem Schweregrad. Für Kunden von Defender für Office 365 P2, E5 und G5 löst diese Warnung automatisch eine automatische Untersuchung und Reaktion [in Office 365 aus.](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) Weitere Informationen zu Ereignissen, die diese Warnung auslösen, finden Sie unter ["Einrichten von Richtlinien für sichere Links".](../security/office-365-security/set-up-atp-safe-links-policies.md)|Bedrohungsverwaltung|E5/G5 oder Defender für Office 365 P2-Add-On-Abonnement|
|**Ergebnis der Administratorübermittlung abgeschlossen**|Generiert eine Warnung, wenn eine [Administratorübermittlung](../security/office-365-security/admin-submission.md) den erneuten Scan der übermittelten Entität abgeschlossen hat. Eine Warnung wird jedes Mal ausgelöst, wenn ein ErneutesScanergebnis aus einer Administratorübermittlung gerendert wird. Diese Warnungen sollen Sie daran erinnern, die Ergebnisse der vorherigen Übermittlungen zu [überprüfen,](https://protection.office.com/reportsubmission)vom Benutzer gemeldete Nachrichten zu übermitteln, um die neueste Richtlinienüberprüfung zu erhalten, sowie Überprüfungen erneut zu überprüfen, und Ihnen helfen zu bestimmen, ob die Filterrichtlinien in Ihrer Organisation die beabsichtigten Auswirkungen haben. Diese Richtlinie hat eine **Einstellung mit** niedrigem Schweregrad.|Bedrohungsverwaltung|E1/F1, E3/F3 oder E5|
|**Administrator hat manuelle Untersuchung von E-Mails ausgelöst**|Generiert eine Warnung, wenn ein Administrator die manuelle Untersuchung einer E-Mail aus dem Bedrohungs-Explorer auslöst. Weitere Informationen finden Sie unter [Beispiel: Ein Sicherheitsadministrator löst eine Untersuchung von Threat Explorer aus] ( https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office#example-a-security-administrator-triggers-an-investigation-from-threat-explorer) . Diese Warnung benachrichtigt Ihre Organisation, dass die Untersuchung gestartet wurde. Die Warnung enthält Informationen darüber, wer sie ausgelöst hat, und enthält einen Link zur Untersuchung. Diese Richtlinie hat eine Einstellung für den Informationsschweregrad. |Bedrohungsverwaltung| E5/G5- oder Microsoft Defender für Office 365 P2-Add-On-Abonnement| 
|**Erstellen einer Weiterleitungs-/Umleitungsregel**|Generiert eine Warnung, wenn eine Person in Ihrer Organisation eine Posteingangsregel für ihr Postfach erstellt, die Nachrichten an ein anderes E-Mail-Konto weiterleite oder umleite. Diese Richtlinie verfolgt nur Posteingangsregeln, die mit Outlook im Web (früher als Outlook Web App bezeichnet) oder Exchange Online PowerShell erstellt werden. Diese Richtlinie hat eine **Einstellung mit** niedrigem Schweregrad. Weitere Informationen zur Verwendung von Posteingangsregeln zum Weiterleiten und Umleiten von E-Mails in Outlook im Web finden Sie unter Verwenden von Regeln in Outlook im Web, um Nachrichten automatisch an ein anderes [Konto weiterzuleiten.](https://support.office.com/article/1433e3a0-7fb0-4999-b536-50e05cb67fed)|Bedrohungsverwaltung|E1/F1/G1, E3/F3/G3 oder E5/G5|
|**eDiscovery-Suche gestartet oder exportiert**|Generiert eine Warnung, wenn jemand das Tool für die Inhaltssuche im Security and Compliance Center verwendet. Eine Warnung wird ausgelöst, wenn die folgenden Inhaltssuchaktivitäten ausgeführt werden: <br/><br/>* Eine Inhaltssuche wurde gestartet<br/>* Die Ergebnisse einer Inhaltssuche werden exportiert.<br/>* Ein Inhaltssuchbericht wird exportiert<br/><br/>Warnungen werden auch ausgelöst, wenn die vorherigen Inhaltssuchaktivitäten in Verbindung mit einem eDiscovery-Fall ausgeführt werden. Diese Richtlinie hat einen **mittleren** Schweregrad. Weitere Informationen zu Inhaltssuchaktivitäten finden Sie im Überwachungsprotokoll unter [Suchen nach eDiscovery-Aktivitäten.](search-for-ediscovery-activities-in-the-audit-log.md#ediscovery-activities)|Bedrohungsverwaltung|E1/F1/G1, E3/F3/G3 oder E5/G5|
|**Rechteerweiterung von Exchange-Administratorrechten**|Generiert eine Warnung, wenn einer Person Administratorberechtigungen in Ihrer Exchange Online-Organisation zugewiesen sind. Beispielsweise, wenn der Rollengruppe "Organisationsverwaltung" in Exchange Online ein Benutzer hinzugefügt wird. Diese Richtlinie hat eine **Einstellung mit** niedrigem Schweregrad.|Berechtigungen|E1/F1/G1, E3/F3/G3 oder E5/G5|
|**E-Mail-Nachrichten mit Schadsoftware, die nach der Zustellung entfernt wurden**|Generiert eine Warnung, wenn Nachrichten, die Schadsoftware enthalten, an Postfächer in Ihrer Organisation zugestellt werden. Wenn dieses Ereignis auftritt, entfernt Microsoft die infizierten Nachrichten aus Exchange Online-Postfächern, indem die automatische Bereinigung zur [Nullstunde verwendet wird.](../security/office-365-security/zero-hour-auto-purge.md) Diese Richtlinie hat eine Einstellung **für** den Informationsschweregrad und löst automatisch eine automatisierte Untersuchung und Reaktion [in Office 365 aus.](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)|Bedrohungsverwaltung|E5/G5- oder Microsoft Defender für Office 365 P2-Add-On-Abonnement|
|**E-Mail-Nachrichten mit phish-URLs, die nach der Zustellung entfernt wurden**|Generiert eine Warnung, wenn Nachrichten mit Phishing an Postfächer in Ihrer Organisation zugestellt werden. Wenn dieses Ereignis auftritt, entfernt Microsoft die infizierten Nachrichten aus Exchange Online-Postfächern, indem die automatische Bereinigung zur [Nullstunde verwendet wird.](../security/office-365-security/zero-hour-auto-purge.md) Diese Richtlinie hat eine Einstellung **für** den Informationsschweregrad und löst automatisch eine automatisierte Untersuchung und Reaktion [in Office 365 aus.](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)|Bedrohungsverwaltung|E5/G5 oder Defender für Office 365 P2-Add-On-Abonnement|
|**Vom Benutzer als Schadsoftware oder Phishing gemeldete E-Mail**|Generiert eine Warnung, wenn Benutzer in Ihrer Organisation Nachrichten mithilfe des Add-Ins "Nachricht melden" als Phishing-E-Mail melden. Diese Richtlinie hat eine Einstellung für den Informationsschweregrad.  Weitere Informationen zu diesem Add-In finden Sie unter [Verwenden des Berichtsnachrichten-Add-Ins.](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2) Für Kunden von Defender für Office 365 P2, E5 und G5 löst diese Warnung automatisch eine automatische Untersuchung und Reaktion [in Office 365 aus.](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)|Bedrohungsverwaltung|E1/F1/G1, E3/F3/G3 oder E5/G5|
|**Grenzwert für das Senden von E-Mails überschritten**|Generiert eine Warnung, wenn eine Person in Ihrer Organisation mehr E-Mails gesendet hat, als in der Richtlinie für ausgehende Spamnachrichten zulässig sind. Dies ist in der Regel ein Hinweis darauf, dass der Benutzer zu viele E-Mails sendet oder dass das Konto möglicherweise gefährdet ist. Diese Richtlinie hat einen **mittleren** Schweregrad. Wenn Sie eine Warnung erhalten, die durch diese Warnungsrichtlinie generiert wird, sollten Sie überprüfen, ob das Benutzerkonto [gefährdet ist.](../security/office-365-security/responding-to-a-compromised-email-account.md)|Bedrohungsverwaltung|E1/F1/G1, E3/F3/G3 oder E5/G5|
|**Formular aufgrund eines potenziellen Phishingversuchs blockiert**|Generiert eine Warnung, wenn eine Person in Ihrer Organisation aufgrund von wiederholten Phishingversuchen an der Freigabe von Formularen und dem Sammeln von Antworten mithilfe von Microsoft Forms eingeschränkt wurde. Diese Richtlinie hat eine **Einstellung mit hohem Schweregrad.**|Bedrohungsverwaltung|E1, E3/F3 oder E5|
|**Formular als Phishing gekennzeichnet und bestätigt**|Generiert eine Warnung, wenn ein in Microsoft Forms erstelltes Formular in Ihrer Organisation als potenzieller Phishingversuch durch "Missbrauch melden" erkannt und von Microsoft als Phishing bestätigt wurde. Diese Richtlinie hat eine **Einstellung** mit hohem Schweregrad.|Bedrohungsverwaltung|E1, E3/F3 oder E5|
|**Nachrichten wurden verzögert**|Generiert eine Warnung, wenn Microsoft keine E-Mail-Nachrichten über einen Connector an Ihre lokale Organisation oder einen Partnerserver senden kann. In diesem Fall wird die Nachricht in die Warteschlange in Office 365 eingereiht. Diese Warnung wird ausgelöst, wenn mehr als 2.000 Nachrichten in die Warteschlange gestellt wurden. Diese Richtlinie hat eine **Einstellung** mit hohem Schweregrad.|Nachrichtenübermittlung|E1/F1/G1, E3/F3/G3 oder E5/G5|
|**Schadsoftwarekampagne nach Zustellung erkannt**|Generiert eine Warnung, wenn eine ungewöhnlich große Anzahl von Nachrichten mit Schadsoftware an Postfächer in Ihrer Organisation zugestellt wird. Wenn dieses Ereignis auftritt, entfernt Microsoft die infizierten Nachrichten aus Exchange Online-Postfächern. Diese Richtlinie hat eine **Einstellung** mit hohem Schweregrad.|Bedrohungsverwaltung|E5/G5- oder Microsoft Defender für Office 365 P2-Add-On-Abonnement|
|**Schadsoftwarekampagne erkannt und blockiert**|Generiert eine Warnung, wenn jemand versucht hat, eine ungewöhnlich große Anzahl von E-Mail-Nachrichten mit einer bestimmten Art von Schadsoftware an Benutzer in Ihrer Organisation zu senden. Wenn dieses Ereignis auftritt, werden die infizierten Nachrichten von Microsoft blockiert und nicht an Postfächer zugestellt. Diese Richtlinie hat eine **Einstellung mit** niedrigem Schweregrad.|Bedrohungsverwaltung|E5/G5 oder Defender für Office 365 P2-Add-On-Abonnement|
|**Schadsoftwarekampagne in SharePoint und OneDrive erkannt**|Generiert eine Warnung, wenn in Dateien auf #A0 oder #A1 in Ihrer Organisation ungewöhnlich viele Schadsoftware oder Viren erkannt werden. Diese Richtlinie hat eine **Einstellung** mit hohem Schweregrad.|Bedrohungsverwaltung|E5/G5 oder Defender für Office 365 P2-Add-On-Abonnement|
|**Schadsoftware wird nicht abgeschnitten, da ZAP deaktiviert ist**| Generiert eine Warnung, wenn Microsoft die Zustellung einer Schadsoftwarenachricht an ein Postfach erkennt, Zero-Hour automatische Bereinigung für Phishingnachrichten deaktiviert ist. Diese Richtlinie hat eine Einstellung für den Informationsschweregrad.  |Bedrohungsverwaltung|E5/G5 oder Defender für Office 365 P2-Add-On-Abonnement|
|**Phish delivered because a user's Junk Mail folder is disabled**|Generiert eine Warnung, wenn Microsoft erkennt, dass der Junk-E-Mail-Ordner eines Benutzers deaktiviert ist, sodass eine Phishingnachricht mit hoher Confidence an ein Postfach gesendet werden kann. Diese Richtlinie hat eine Einstellung für den Informationsschweregrad. |Bedrohungsverwaltung|E5/G5 oder Defender für Office 365 P1- oder P2-Add-On-Abonnement|
|**Phish, der aufgrund einer Außerkraftsetzung der ETR übermittelt wurde**|Generiert eine Warnung, wenn Microsoft eine Exchange-Transport-Regel (ETR) erkennt, die die Zustellung einer Phishingnachricht mit hoher Confidence an ein Postfach zugelassen hat. Diese Richtlinie hat eine Einstellung für den Informationsschweregrad.  Weitere Informationen zu Exchange-Transportregeln (Nachrichtenflussregeln) finden Sie unter [Nachrichtenflussregeln (Transportregeln) in Exchange Online.](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)|Bedrohungsverwaltung|E5/G5 oder Defender für Office 365 P1- oder P2-Add-On-Abonnement|
|**Phishing, der aufgrund einer Richtlinie für das Zulassen von IP übermittelt wurde**|Generiert eine Warnung, wenn Microsoft eine Richtlinie für zugelassene IP-Adressen erkennt, die die Zustellung einer Phishingnachricht mit hoher Confidence an ein Postfach zugelassen hat. Diese Richtlinie hat eine Einstellung für den Informationsschweregrad.  Weitere Informationen zur Richtlinie für zulässige IP-Adressen (Verbindungsfilterung) finden Sie unter ["Konfigurieren der Standardmäßigen Verbindungsfilterrichtlinie - Office 365".](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-the-connection-filter-policy)|Bedrohungsverwaltung|E5/G5 oder Defender für Office 365 P1- oder P2-Add-On-Abonnement|
|**Phish not zapped because ZAP is disabled**| Generiert eine Warnung, wenn Microsoft die Zustellung einer Phishingnachricht mit hoher Confidence an ein Postfach erkennt, da Zero-Hour automatische Bereinigung für Phishingnachrichten deaktiviert ist. Diese Richtlinie hat eine Einstellung für den Informationsschweregrad. |Bedrohungsverwaltung|E5/G5 oder Defender für Office 365 P2-Add-On-Abonnement|
|**Phish delivered due to tenant or user override**<sup>1</sup>|Generiert eine Warnung, wenn Microsoft erkennt, dass ein Administrator oder ein Benutzer die Zustellung einer Phishingnachricht an ein Postfach zugelassen hat. Beispiele für Außerkraftsetzungen sind ein Posteingang oder eine Nachrichtenflussregel, die Nachrichten von einem bestimmten Absender oder einer bestimmten Domäne zulässt, oder eine Antispamrichtlinie, die Nachrichten von bestimmten Absendern oder Domänen zulässt. Diese Richtlinie hat eine **Einstellung** mit hohem Schweregrad.|Bedrohungsverwaltung|E5/G5 oder Defender für Office 365 P2-Add-On-Abonnement|
|**Verdächtige E-Mail-Weiterleitungsaktivität**|Generiert eine Warnung, wenn eine Person in Ihrer Organisation automatisch E-Mails an ein verdächtiges externes Konto gesendet hat. Dies ist eine frühe Warnung für verhalten, die darauf hinweisen kann, dass das Konto gefährdet ist, aber nicht streng genug, um den Benutzer einzuschränken. Diese Richtlinie hat einen **mittleren** Schweregrad. Obwohl es selten ist, kann eine von dieser Richtlinie generierte Warnung eine Anomalie sein. Es ist eine gute Idee zu [überprüfen, ob das Benutzerkonto gefährdet ist.](../security/office-365-security/responding-to-a-compromised-email-account.md)|Bedrohungsverwaltung|E1/F1/G1, E3/F3/G3 oder E5/G5|
|**Verdächtige E-Mail-Sendemuster erkannt**|Generiert eine Warnung, wenn eine Person in Ihrer Organisation verdächtige E-Mails gesendet hat und das Senden von E-Mails eingeschränkt werden kann. Dies ist eine frühe Warnung für verhalten, die darauf hinweisen kann, dass das Konto gefährdet ist, aber nicht streng genug, um den Benutzer einzuschränken. Diese Richtlinie hat einen **mittleren** Schweregrad. Obwohl es selten ist, kann eine von dieser Richtlinie generierte Warnung eine Anomalie sein. Es ist jedoch eine gute Idee zu überprüfen, ob [das Benutzerkonto gefährdet ist.](../security/office-365-security/responding-to-a-compromised-email-account.md)|Bedrohungsverwaltung|E1/F1/G1, E3/F3/G3 oder E5/G5  |
|**Mandant kann keine E-Mails senden**|Generiert eine Warnung, wenn der großteil des E-Mail-Datenverkehrs von Ihrer Organisation als verdächtig erkannt wurde und Microsoft Das Senden von E-Mails in Ihrer Organisation eingeschränkt hat. Untersuchen Sie potenziell gefährdete Benutzer- und Administratorkonten, neue Connectors oder offene Relays, und wenden Sie sich dann an den Microsoft-Support, um die Blockierung Ihrer Organisation auföffnen. Diese Richtlinie hat eine **Einstellung** mit hohem Schweregrad. Weitere Informationen dazu, warum Organisationen blockiert werden, finden Sie unter Beheben von Problemen mit der Zustellung von E-Mails bei [Fehlercode 5.7.7xx in Exchange Online.](https://go.microsoft.com/fwlink/?linkid=2022138)|Bedrohungsverwaltung|E1/F1/G1, E3/F3/G3 oder E5/G5|
|**Ungewöhnliche Dateiaktivität für externe Benutzer**|Generiert eine Warnung, wenn eine ungewöhnlich große Anzahl von Aktivitäten für Dateien in SharePoint oder OneDrive von Benutzern außerhalb Ihrer Organisation ausgeführt wird. Dazu gehören Aktivitäten wie der Zugriff auf Dateien, das Herunterladen von Dateien und das Löschen von Dateien. Diese Richtlinie hat eine **Einstellung** mit hohem Schweregrad.|Informationsverwaltung|E5/G5, Microsoft Defender für Office 365 P2 oder Microsoft 365 E5-Add-On-Abonnement|
|**Ungewöhnliches Volumen der externen Dateifreigabe**|Generiert eine Warnung, wenn eine ungewöhnlich große Anzahl von Dateien in SharePoint oder OneDrive für Benutzer außerhalb Ihrer Organisation freigegeben wird. Diese Richtlinie hat einen **mittleren** Schweregrad.|Informationsverwaltung|E5/G5, Defender für Office 365 P2 oder Microsoft 365 E5-Add-On-Abonnement|
|**Ungewöhnliches Volumen des Löschens von Dateien**|Generiert eine Warnung, wenn eine ungewöhnlich große Anzahl von Dateien in SharePoint oder OneDrive innerhalb eines kurzen Zeitrahmens gelöscht wird. Diese Richtlinie hat einen **mittleren** Schweregrad.|Informationsverwaltung|E5/G5, Defender für Office 365 P2 oder Microsoft 365 E5-Add-On-Abonnement|
|**Ungewöhnlicher Anstieg der als Phishing gemeldeten E-Mails**|Generiert eine Warnung, wenn die Anzahl der Personen in Ihrer Organisation, die das Add-In "Nachricht melden" in Outlook verwenden, um Nachrichten als Phishing-E-Mails zu melden, erheblich erhöht wird. Diese Richtlinie hat eine **Einstellung** mit hohem Schweregrad. Weitere Informationen zu diesem Add-In finden Sie unter [Verwenden des Berichtsnachrichten-Add-Ins.](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)|Bedrohungsverwaltung|E5/G5 oder Defender für Office 365 P2-Add-On-Abonnement|
|**Phish des Benutzerwechsels an Posteingang/Ordner**<sup>1,</sup><sup>2</sup>|Generiert eine Warnung, wenn Microsoft erkennt, dass eine Außerkraftsetzung durch einen Administrator oder Benutzer die Zustellung einer Phishingnachricht im Identitätswechsel an den Posteingang (oder einen anderen benutzer zugänglichen Ordner) eines Postfachs zugelassen hat. Beispiele für Außerkraftsetzungen sind ein Posteingang oder eine Nachrichtenflussregel, die Nachrichten von einem bestimmten Absender oder einer bestimmten Domäne zulässt, oder eine Antispamrichtlinie, die Nachrichten von bestimmten Absendern oder Domänen zulässt. Diese Richtlinie hat einen **mittleren** Schweregrad.|Bedrohungsverwaltung|E5/G5 oder Defender für Office 365 P2-Add-On-Abonnement|
|**Benutzer, der am Senden von E-Mails eingeschränkt ist**|Generiert eine Warnung, wenn jemand in Ihrer Organisation am Senden ausgehender E-Mails eingeschränkt ist. Dies führt in der Regel dazu, dass ein  Konto gefährdet ist und der Benutzer auf der Seite "Eingeschränkte Benutzer" im Security & Compliance Center aufgeführt wird. (To access this page, go to **Threat management > Review > Restricted Users**). Diese Richtlinie hat eine **Einstellung** mit hohem Schweregrad. Weitere Informationen zu eingeschränkten Benutzern finden Sie unter Entfernen eines Benutzers, einer Domäne oder einer IP-Adresse aus einer Sperrliste nach dem Senden [von Spam-E-Mails.](https://docs.microsoft.com/office365/securitycompliance/removing-user-from-restricted-users-portal-after-spam)|Bedrohungsverwaltung|E1/F1/G1, E3/F3/G3 oder E5/G5|
|**Benutzer, der auf die Freigabe von Formularen und das Sammeln von Antworten beschränkt ist**|Generiert eine Warnung, wenn eine Person in Ihrer Organisation aufgrund von wiederholten Phishingversuchen an der Freigabe von Formularen und dem Sammeln von Antworten mithilfe von Microsoft Forms eingeschränkt wurde. Diese Richtlinie hat eine **Einstellung** mit hohem Schweregrad.|Bedrohungsverwaltung|E1, E3/F3 oder E5|
|||||

> [!NOTE]
> <sup>1</sup> Wir haben diese standardmäßige Warnungsrichtlinie basierend auf Kundenfeedback vorübergehend entfernt. We're working to improve it, and will replace it with a new version in the near future. Bis dahin können Sie eine benutzerdefinierte Warnungsrichtlinie erstellen, um diese Funktionalität durch die folgenden Einstellungen zu ersetzen:<br/>&nbsp; * Aktivität ist Phishing-E-Mail, die zum Zeitpunkt der Zustellung erkannt wurde<br/>&nbsp; * Mail is not ZAP'd<br/>&nbsp; * Die E-Mail-Richtung ist "Inbound".<br/>&nbsp; * Der Status der E-Mail-Zustellung wird übermittelt.<br/>&nbsp; * Erkennungstechnologie ist die Aufbewahrung bösartiger URLs, URL-Detonation, erweiterter Phishingfilter, allgemeiner Phishingfilter, Domänen-Identitätswechsel, Benutzer-Identitätswechsel und Markenwechsel<br/><br/>&nbsp;&nbsp;&nbsp;Weitere Informationen zu Antiphishing in Office 365 finden Sie unter [Einrichten von Antiphishing- und Antiphishingrichtlinien.](../security/office-365-security/set-up-anti-phishing-policies.md)<br/><br/><sup>2 Um</sup> diese Warnungsrichtlinie neu zu erstellen, befolgen Sie die Anweisungen in der vorherigen Fußnote, wählen Sie jedoch den Benutzerwechsel als einzige Erkennungstechnologie aus.

Die ungewöhnliche Aktivität, die von einigen der integrierten Richtlinien überwacht wird, basiert auf demselben Prozess wie die zuvor beschriebene Einstellung für den Warnungsschwellenwert. Microsoft richtet einen Basiswert ein, der die normale Häufigkeit für "übliche" Aktivitäten definiert. Warnungen werden dann ausgelöst, wenn die Häufigkeit von Aktivitäten, die von der integrierten Warnungsrichtlinie nachverfolgt werden, den Basiswert erheblich überschreitet.

## <a name="viewing-alerts"></a>Anzeigen von Warnungen

Wenn eine Aktivität, die von Benutzern in Ihrer Organisation ausgeführt wird, den  Einstellungen einer Warnungsrichtlinie entspricht, wird eine Warnung generiert und auf der Seite Benachrichtigungen anzeigen im Security and Compliance Center angezeigt. Je nach den Einstellungen einer Warnungsrichtlinie wird auch eine E-Mail-Benachrichtigung an eine Liste der angegebenen Benutzer gesendet, wenn eine Warnung ausgelöst wird. Für jede Warnung zeigt  das Dashboard auf der Seite Benachrichtigungen anzeigen den Namen der entsprechenden Warnungsrichtlinie, den Schweregrad und die Kategorie für die Warnung (definiert in der Warnungsrichtlinie) und die Anzahl der Aktivitäten an, die zum Generieren der Warnung geführt haben. Dieser Wert basiert auf der Schwellenwerteinstellung der Warnungsrichtlinie. Das Dashboard zeigt auch den Status für jede Warnung an. Weitere Informationen zur Verwendung der Statuseigenschaft zum Verwalten von Warnungen finden Sie unter ["Verwalten von Warnungen".](#managing-alerts)

Wenn Sie Warnungen anzeigen möchten, [https://protection.office.com](https://protection.office.com) wechseln Sie zu Warnungen, und wählen Sie dann Warnungen  \> **anzeigen aus.**

![Wählen Sie in den Sicherheits- und Kompatibilitätseinstellungen "Warnungen" und dann "Warnungen anzeigen" aus, um Warnungen anzuzeigen.](../media/ec5ea59b-bf61-459f-8b65-970ab4bb8bcc.png)

Sie können die folgenden Filter verwenden, um eine Teilmenge aller Warnungen auf der Seite Benachrichtigungen **anzeigen** anzuzeigen.

- **Status.** Verwenden Sie diesen Filter, um Warnungen anzuzeigen, denen ein bestimmter Status zugewiesen ist. Der Standardstatus ist **"Aktiv".** Sie oder andere Administratoren können den Statuswert ändern.

- **Richtlinie.** Verwenden Sie diesen Filter, um Warnungen anzuzeigen, die mit der Einstellung einer oder mehreren Warnungsrichtlinien übereinstimmen. Sie können auch alle Warnungen für alle Warnungsrichtlinien anzeigen.

- **Zeitraum.** Verwenden Sie diesen Filter, um Warnungen anzuzeigen, die innerhalb eines bestimmten Datums- und Uhrzeitbereichs generiert wurden.

- **Schweregrad.** Verwenden Sie diesen Filter, um Warnungen anzuzeigen, denen ein bestimmter Schweregrad zugewiesen ist.

- **Kategorie.** Verwenden Sie diesen Filter, um Warnungen aus einer oder mehreren Warnungskategorien anzuzeigen.

- **Tags.** Verwenden Sie diesen Filter, um Warnungen von einem oder mehreren Benutzertags anzuzeigen. Tags werden basierend auf markierten Postfächern oder Benutzern angezeigt, die in den Warnungen angezeigt werden. Weitere [Informationen finden Sie unter Benutzertags in Office 356 ATP.](..\security\office-365-security\user-tags.md)

- **Quelle.** Verwenden Sie diesen Filter, um Warnungen anzuzeigen, die durch Warnungsrichtlinien im Security and Compliance Center oder durch Office 365 Cloud App Security-Richtlinien oder beides ausgelöst wurden. Weitere Informationen zu Office 365 Cloud App Security-Warnungen finden Sie unter [Anzeigen von Cloud App Security-Warnungen.](#viewing-cloud-app-security-alerts)

> [!IMPORTANT]
> Das Filtern und Sortieren nach Benutzertags befindet sich derzeit in der öffentlichen Vorschau.
> Es kann erheblich geändert werden, bevor es kommerziell veröffentlicht wird. Microsoft über garantiert keine ausdrücklichen oder impliziten Gewährleistungen in Bezug auf die informationen, die darüber bereitgestellt werden.

## <a name="alert-aggregation"></a>Benachrichtigungsaggregation

Wenn mehrere Ereignisse, die den Bedingungen einer Warnungsrichtlinie entsprechen, mit einem kurzen Zeitraum auftreten, werden sie einer vorhandenen Warnung durch einen Prozess namens *Warnungsaggregation hinzugefügt.* Wenn ein Ereignis eine Warnung auslöst, wird die  Warnung generiert und auf der Seite Benachrichtigungen anzeigen angezeigt, und es wird eine Benachrichtigung gesendet. Wenn das gleiche Ereignis innerhalb des Aggregationsintervalls auftritt, fügt Microsoft 365 Details zum neuen Ereignis zur vorhandenen Warnung hinzu, anstatt eine neue Warnung auszulösen. Das Ziel der Benachrichtigungsaggregation besteht in der Reduzierung der Warnungsermüdung, und Sie können sich auf weniger Warnungen für das gleiche Ereignis konzentrieren und Maßnahmen ergreifen.

Die Länge des Aggregationsintervalls hängt von Ihrem Office 365- oder Microsoft 365-Abonnement ab.

|Abonnement|Aggregationsintervall|
|:---------|:---------:|
|Office 365 oder Microsoft 365 E5/G5|1 Minute|
|Defender für Office 365 Plan 2 |1 Minute|
|E5 Compliance-Add-On oder E5-Discovery- und -Überwachungs-Add-On|1 Minute|
|Office 365 oder Microsoft 365 E1/F1/G1 oder E3/F3/G3|15 Minuten|
|Defender für Office 365 Plan 1 oder Exchange Online Protection|15 Minuten|
|||

Wenn Ereignisse, die derselben Warnungsrichtlinie entsprechen, innerhalb des Aggregationsintervalls auftreten, werden Details zum nachfolgenden Ereignis der ursprünglichen Warnung hinzugefügt. Für alle Ereignisse werden Informationen zu aggregierten Ereignissen im Detailfeld angezeigt, und die Anzahl der Ereignisse, die mit dem Aggregationsintervall aufgetreten sind, wird im Aktivitäts-/Trefferanzahlfeld angezeigt. Sie können weitere Informationen zu allen aggregierten Ereignisinstanzen anzeigen, indem Sie die Aktivitätsliste anzeigen.

Der folgende Screenshot zeigt eine Warnung mit vier aggregierten Ereignissen. Die Aktivitätsliste enthält Informationen zu den vier E-Mail-Nachrichten, die für die Warnung relevant sind.

![Beispiel für die Benachrichtigungsaggregation](../media/AggregatedAlertExample.png)

Beachten Sie bei der Benachrichtigungsaggregation Folgendes:

- Warnungen, die durch den Klick auf eine potenziell schädliche URL ausgelöst wurden, wurden **erkannt,** dass die Standardwarnungsrichtlinie nicht aggregiert wurde. [](#default-alert-policies) Dies liegt daran, dass durch diese Richtlinie ausgelöste Warnungen für jeden Benutzer und jede E-Mail-Nachricht eindeutig sind.

- Zu diesem Zeitpunkt gibt die **Warnungseigenschaft** "Trefferanzahl" nicht die Anzahl der aggregierten Ereignisse für alle Warnungsrichtlinien an. Für Warnungen, die durch diese Warnungsrichtlinien ausgelöst  werden, können  Sie die aggregierten Ereignisse anzeigen, indem Sie in der Warnung auf "Nachrichtenliste anzeigen" oder "Aktivität anzeigen" klicken. Wir arbeiten daran, die Anzahl der aggregierten  Ereignisse, die in der Warnungseigenschaft für die Trefferanzahl aufgeführt sind, für alle Warnungsrichtlinien verfügbar zu machen.

## <a name="rbac-permissions-required-to-view-alerts"></a>Zum Anzeigen von Warnungen erforderliche rbAC-Berechtigungen

Die den Benutzern in Ihrer Organisation zugewiesenen Berechtigungen für die rollenbasierte Zugriffssteuerung (Role Based Access Control, RBAC) bestimmen, welche Warnungen einem Benutzer auf der Seite Benachrichtigungen **anzeigen angezeigt** werden können. Wie wird dies erreicht? Die Den Benutzern zugewiesenen Verwaltungsrollen (basierend auf ihrer Mitgliedschaft in Rollengruppen im Security & Compliance Center) bestimmen, welche Warnungskategorien einem Benutzer auf der Seite Benachrichtigungen anzeigen angezeigt **werden.** Im Folgenden finden Sie einige Beispiele:

- Mitglieder der Rollengruppe "Datensatzverwaltung" können nur die Warnungen anzeigen, die von Warnungsrichtlinien generiert werden, denen die **Kategorie "Informationsverwaltung" zugewiesen** ist.

- Mitglieder der Rollengruppe "Complianceadministrator" können keine Warnungen anzeigen, die von Warnungsrichtlinien generiert werden, denen die Kategorie **"Bedrohungsverwaltung" zugewiesen** ist.

- Mitglieder der Rollengruppe "eDiscovery-Manager" können keine Warnungen anzeigen, da keine der zugewiesenen Rollen die Berechtigung zum Anzeigen von Warnungen aus einer Warnungskategorie bietet.

Mit diesem Entwurf (basierend auf rbAC-Berechtigungen) können Sie bestimmen, welche Warnungen von Benutzern in bestimmten Rollen in Ihrer Organisation angezeigt (und verwaltet) werden können.

In der folgenden Tabelle sind die Rollen aufgeführt, die zum Anzeigen von Warnungen aus den sechs verschiedenen Warnungskategorien erforderlich sind. In der ersten Spalte der Tabellen sind alle Rollen im Security & Compliance Center aufgeführt.  Ein Häkchen gibt an, dass ein Benutzer, dem diese Rolle zugewiesen ist, Warnungen aus der entsprechenden Warnungskategorie anzeigen kann, die in der obersten Zeile aufgeführt ist.

Informationen zur Kategorie, der eine Standardwarnungsrichtlinie zugewiesen ist, finden Sie in der Tabelle in den [Standardbenachrichtigungsrichtlinien.](#default-alert-policies)

|Rolle|Informationsverwaltung|Verhinderung von Datenverlust|Nachrichtenübermittlung|Berechtigungen|Bedrohungsverwaltung|Sonstige|
|:---------|:---------:|:---------:|:---------:|:---------:|:---------:|:---------:|
|Überwachungsprotokolle|||||||
|Fallverwaltung|||||||
|Complianceadministrator|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||![Häkchen](../media/checkmark.png)||![Häkchen](../media/checkmark.png)|
|Compliance-Suche|||||||
|Geräteverwaltung|||||||
|Dispositionsverwaltung|||||||
|Verwaltung der DLP-Compliance||![Häkchen](../media/checkmark.png)|||||
|Exportieren|||||||
|Hold|||||||
|Benachrichtigungen verwalten||||||![Häkchen](../media/checkmark.png)|
|Organisationskonfiguration||||||![Häkchen](../media/checkmark.png)|
|Vorschau|||||||
|Datensatzverwaltung|![Häkchen](../media/checkmark.png)||||||
|Aufbewahrungsverwaltung|![Häkchen](../media/checkmark.png)||||||
|Überprüfung|||||||
|RMS Decrypt|||||||
|Rollenverwaltung||||![Häkchen](../media/checkmark.png)|||
|Suchen und Löschen|||||||
|Sicherheitsadministrator||![Häkchen](../media/checkmark.png)||![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|
|Sicherheitsleseberechtigter||![Häkchen](../media/checkmark.png)||![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)
|Service Assurance View|||||||
|Aufsichtsüberprüfungsadministrator|||||||
|Überwachungsprotokolle nur anzeigen|||||||
|View-Only Geräteverwaltung|||||||
|View-Only von DLP Compliance Management||![Häkchen](../media/checkmark.png)|||||
|View-Only Verwalten von Warnungen||||||![Häkchen](../media/checkmark.png)|
|Schreibgeschützte Empfänger|||![Häkchen](../media/checkmark.png)||||
|View-Only Datensatzverwaltung|![Häkchen](../media/checkmark.png)||||||
|View-Only Der Aufbewahrungsverwaltung|![Häkchen](../media/checkmark.png)||||||
|||||||

> [!TIP]
> Führen Sie die folgenden Befehle in Security & Compliance Center PowerShell aus, um die Rollen anzuzeigen, die den einzelnen Standardrollengruppen zugewiesen sind:
> 
> ```powershell
> $RoleGroups = Get-RoleGroup
> ```
> 
> ```powershell
> $RoleGroups | foreach {Write-Output -InputObject `r`n,$_.Name,"-----------------------"; Get-RoleGroup $_.Identity | Select-Object -ExpandProperty Roles}
> ```
> 
> Sie können auch die Einer Rollengruppe zugewiesenen Rollen im Security & Compliance Center anzeigen. Wechseln Sie zur Seite **"Berechtigungen",** und wählen Sie eine Rollengruppe aus. Die zugewiesenen Rollen werden auf der Flyoutseite aufgeführt.

## <a name="managing-alerts"></a>Verwalten von Warnungen

Nachdem Warnungen generiert und auf  der Seite "Benachrichtigungen anzeigen" im Security and Compliance Center angezeigt wurden, können Sie sie ermitteln, untersuchen und beheben. Hier sind einige Aufgaben, die Sie zum Verwalten von Warnungen ausführen können.

- **Weisen Sie Warnungen einen Status zu.** Sie können einen der folgenden Status zu Warnungen zuweisen: **Aktiv** (Standardwert), **Investigating**, **Resolved** oder **Dismissed**. Anschließend können Sie nach dieser Einstellung filtern, um Warnungen mit derselben Statuseinstellung anzuzeigen. Mit dieser Statuseinstellung kann der Prozess der Verwaltung von Warnungen nachverfolgt werden.

- **Anzeigen von Warnungsdetails.** Sie können eine Warnung auswählen, um eine Flyoutseite mit Details zur Warnung anzuzeigen. Die detaillierten Informationen hängen von der entsprechenden Warnungsrichtlinie ab, umfassen jedoch in der Regel folgendes: den Namen des tatsächlichen Vorgangs, der die Warnung ausgelöst hat (z. B. ein Cmdlet), eine Beschreibung der Aktivität, die die Warnung ausgelöst hat, den Benutzer (oder die Liste der Benutzer), der die Warnung ausgelöst hat, und den Namen (und Link zu) der entsprechenden Warnungsrichtlinie.

  - Der Name des tatsächlichen Vorgangs, der die Warnung ausgelöst hat, z. B. ein Cmdlet oder ein Überwachungsprotokollvorgang.

  - Eine Beschreibung der Aktivität, die die Warnung ausgelöst hat.

  - Der Benutzer, der die Warnung ausgelöst hat. Dies ist nur für Warnungsrichtlinien enthalten, die zum Nachverfolgen eines einzelnen Benutzers oder einer einzelnen Aktivität eingerichtet sind.

  - Die Anzahl der Von der Warnung nachverfolgten Aktivitäten. Diese Anzahl ist möglicherweise nicht mit der tatsächlichen Anzahl verwandter Warnungen auf der Seite Benachrichtigungen anzeigen übereinstimmen, da möglicherweise mehr Warnungen ausgelöst wurden.

  - Ein Link zu einer Aktivitätsliste, die ein Element für jede Aktivität enthält, die ausgeführt wurde, die die Warnung ausgelöst hat. Jeder Eintrag in dieser Liste gibt an, wann die Aktivität stattgefunden hat, den Namen des tatsächlichen Vorgangs (z. B. "FileDeleted") und den Benutzer, der die Aktivität ausgeführt hat, das Objekt (z. B. eine Datei, ein eDiscovery-Fall oder ein Postfach), für das die Aktivität ausgeführt wurde, und die #A0 des Computers des Benutzers. Bei Warnungen im Zusammenhang mit Schadsoftware ist dies eine Verknüpfung mit einer Nachrichtenliste.

  - Der Name (und link zu) der entsprechenden Warnungsrichtlinie.

- **Unterdrücken von E-Mail-Benachrichtigungen.** Sie können E-Mail-Benachrichtigungen von der Flyoutseite für eine Warnung deaktivieren (oder unterdrücken). Wenn Sie E-Mail-Benachrichtigungen unterdrücken, sendet Microsoft keine Benachrichtigungen, wenn Aktivitäten oder Ereignisse den Bedingungen der Warnungsrichtlinie entsprechen. Warnungen werden jedoch ausgelöst, wenn Aktivitäten, die von Benutzern ausgeführt werden, den Bedingungen der Warnungsrichtlinie entsprechen. Sie können E-Mail-Benachrichtigungen auch deaktivieren, indem Sie die Warnungsrichtlinie bearbeiten.

- **Beheben sie Warnungen.** Sie können eine Warnung auf der Flyoutseite für eine Warnung als aufgelöst markieren (wodurch der Status der Warnung auf **"Gelöst" setzt wird).** Wenn Sie den Filter nicht ändern, werden aufgelöste Warnungen nicht auf der Seite Benachrichtigungen **anzeigen** angezeigt.

## <a name="viewing-cloud-app-security-alerts"></a>Anzeigen von Cloud App Security-Warnungen

Warnungen, die durch Office 365 Cloud App Security-Richtlinien ausgelöst werden, werden jetzt auf der Seite "Warnungen anzeigen" im Security and Compliance Center angezeigt.  Dazu gehören Warnungen, die durch Aktivitätsrichtlinien und Warnungen ausgelöst werden, die durch Anomalieerkennungsrichtlinien in Office 365 Cloud App Security ausgelöst werden. Dies bedeutet, dass Sie alle Warnungen im Security and Compliance Center anzeigen können. Office 365 Cloud App Security ist nur für Organisationen mit einem Office 365 Enterprise E5- oder Office 365 US Government G5-Abonnement verfügbar. Weitere Informationen finden Sie unter [Übersicht über Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security).

Organisationen, die Microsoft Cloud App Security als Teil eines Enterprise Mobility + Security E5-Abonnements oder als eigenständiger Dienst haben, können auch Cloud App Security-Warnungen im Zusammenhang mit Office 365-Apps und -Diensten im Security & Compliance Center anzeigen.

Um nur Cloud App Security-Warnungen im Security  and Compliance Center anzuzeigen, verwenden Sie den Quellfilter, und wählen Sie **Cloud App Security aus.**

![Verwenden des Quellfilters zum Anzeigen von nur Cloud App Security-Warnungen](../media/FilterCASAlerts.png)

Ähnlich wie bei einer Warnung, die durch eine Warnungsrichtlinie im Security and Compliance Center ausgelöst wird, können Sie eine Cloud App Security-Warnung auswählen, um eine Flyoutseite mit Details zu der Warnung anzuzeigen. Die Warnung enthält einen Link zum Anzeigen der Details und Verwalten der Warnung im Cloud App Security-Portal sowie einen Link zur entsprechenden Cloud App Security-Richtlinie, die die Warnung ausgelöst hat. Siehe ["Überwachen von Warnungen in Cloud App Security".](https://docs.microsoft.com/cloud-app-security/monitor-alerts)

![Warnungsdetails enthalten Links zum Cloud App Security-Portal](../media/CASAlertDetail.png)

> [!IMPORTANT]
> Wenn Sie den Status einer Cloud App Security-Warnung im Security and Compliance Center ändern, wird der Lösungsstatus für dieselbe Warnung im Cloud App Security-Portal nicht aktualisiert. Wenn Sie beispielsweise den Status der Warnung im Security and **Compliance** Center als "Gelöst" markieren, bleibt der Status der Warnung im Cloud App Security-Portal unverändert. Um eine Cloud App Security-Warnung zu beheben oder zu schließen, verwalten Sie die Warnung im Cloud App Security-Portal.
