---
title: Automatisierte Untersuchung und Reaktion in Microsoft Defender für Office 365
keywords: AIR, AutoIR, ATP, automatisiert, Untersuchung, Reaktion, Behebung, Bedrohungen, erweitert, Bedrohung, Schutz
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 01/29/2021
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Erste Schritte mit automatisierten Untersuchungs- und Reaktionsfunktionen in Microsoft Defender für Office 365.
ms.custom:
- air
- seo-marvel-mar2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1460deef11a87044530c54c8b10637284829a0cd
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206681"
---
# <a name="automated-investigation-and-response-air-in-microsoft-defender-for-office-365"></a>Automatisierte Untersuchung und Reaktion (AIR) in Microsoft Defender für Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[Microsoft Defender für Office 365](defender-for-office-365.md) umfasst leistungsstarke Funktionen für automatisierte Untersuchung und Reaktion (AIR), mit derEntsprechungsteam Zeit und Aufwand sparen kann. Wenn Warnungen ausgelöst werden, ist es an Ihrem Sicherheitsbetriebsteam, diese Warnungen zu überprüfen, zu priorisieren und darauf zu reagieren. Das Halten mit dem Volumen eingehender Warnungen kann überwältigend sein. Das Automatisieren einiger dieser Aufgaben kann hilfreich sein.

AIR ermöglicht Es Ihrem Sicherheitsteam, effizienter und effektiver zu arbeiten. Zu den AIR-Funktionen gehören automatisierte Untersuchungsprozesse als Reaktion auf bekannte Bedrohungen, die heute vorhanden sind. Geeignete Abhilfemaßnahmen warten auf die Genehmigung, sodass Ihr Sicherheitsbetriebsteam effektiv auf erkannte Bedrohungen reagieren kann. Mit AIR kann sich Ihr Sicherheitsbetriebsteam auf Aufgaben mit höherer Priorität konzentrieren, ohne wichtige ausgelöste Warnungen aus den Augen zu verlieren.

Inhalt dieses Artikels

- Der [Gesamteinfluss von AIR](#the-overall-flow-of-air);
- [How to get AIR](#how-to-get-air); und
- Die [erforderlichen Berechtigungen zum](#required-permissions-to-use-air-capabilities) Konfigurieren oder Verwenden von AIR-Funktionen.
- Änderungen, die in Kürze an Ihrem Security Center vorgenommen werden

Dieser Artikel enthält außerdem [die nächsten Schritte](#next-steps)und Ressourcen, um weitere Informationen zu erhalten.

## <a name="the-overall-flow-of-air"></a>Der Gesamteinfluss von AIR

Eine Warnung wird ausgelöst, und ein Sicherheitsspielbuch startet eine automatisierte Untersuchung, was zu Ergebnissen und empfohlenen Aktionen führt. Hier ist der allgemeine Fluss von AIR, Schritt für Schritt:

1. Eine automatisierte Untersuchung wird auf eine der folgenden Arten initiiert:
   - Eine [Warnung wird entweder durch etwas](#which-alert-policies-trigger-automated-investigations) Verdächtiges in E-Mails ausgelöst (z. B. eine Nachricht, Anlage, URL oder ein gefährdetes Benutzerkonto). Es wird ein Vorfall erstellt, und eine automatisierte Untersuchung beginnt. oder
   - Ein Sicherheitsanalyst [startet eine automatisierte Untersuchung,](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer) während er den [Threat Explorer verwendet.](threat-explorer.md)
2. Während eine automatisierte Untersuchung ausgeführt wird, werden Daten über die in Frage stehenden E-Mails und Entitäten im Zusammenhang mit dieser E-Mail gesammelt. Solche Entitäten können Dateien, URLs und Empfänger enthalten. Der Untersuchungsbereich kann mit dem Auslösen neuer und verwandter Warnungen zunehmen.
3. Während und nach einer automatisierten Untersuchung [stehen Details und Ergebnisse](air-view-investigation-results.md) zur Verfügung. Zu den Ergebnissen [gehören empfohlene Aktionen,](air-remediation-actions.md) mit denen auf gefundene Bedrohungen reagiert und behoben werden kann.
4. Ihr Sicherheitsteam überprüft die Untersuchungsergebnisse [und Empfehlungen](air-view-investigation-results.md)und genehmigt oder lehnt [Korrekturaktionen ab.](air-review-approve-pending-completed-actions.md)
5. Wenn ausstehende Korrekturaktionen genehmigt (oder abgelehnt) werden, wird die automatisierte Untersuchung abgeschlossen.

In Microsoft Defender für Office 365 werden keine Korrekturaktionen automatisch ausgeführt. Abhilfemaßnahmen werden nur nach Genehmigung durch das Sicherheitsteam Ihrer Organisation ausgeführt. Air-Funktionen sparen Ihrem Sicherheitsbetriebsteam Zeit, indem Sie Korrekturaktionen identifizieren und die Details bereitstellen, die für eine fundierte Entscheidung erforderlich sind.

Während und nach jeder automatisierten Untersuchung kann Ihr Sicherheitsteam:

- [Anzeigen von Details zu einer Warnung im Zusammenhang mit einer Untersuchung](air-view-investigation-results.md#view-details-about-an-alert-related-to-an-investigation)
- [Anzeigen der Ergebnisdetails einer Untersuchung](air-view-investigation-results.md#view-details-of-an-investigation)
- [Überprüfen und Genehmigen von Aktionen als Ergebnis einer Untersuchung](air-review-approve-pending-completed-actions.md)

> [!TIP]
> Eine ausführlichere Übersicht finden Sie unter [Funktionsweise von AIR](automated-investigation-response-office.md).

## <a name="how-to-get-air"></a>So erhalten Sie AIR

Air-Funktionen sind in [Microsoft Defender für Office 365](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2)enthalten, sofern Ihre Richtlinien und Warnungen konfiguriert sind. Benötigen Sie Hilfe? Befolgen Sie die Anweisungen unter [Schützen vor Bedrohungen](protect-against-threats.md) zum Einrichten oder Konfigurieren der folgenden Schutzeinstellungen:

- [Überwachungsprotokollierung](../../compliance/turn-audit-log-search-on-or-off.md) (sollte aktiviert sein)
- [Richtlinien für Antischadsoftware](protect-against-threats.md#part-1---anti-malware-protection)
- [Schutz vor Phishing](protect-against-threats.md#part-2---anti-phishing-protection)
- [Antispamschutz](protect-against-threats.md#part-3---anti-spam-protection)
- [Schutz vor Phishing](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#part-2---anti-phishing-protection)
- [Antispamschutz](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#part-3---anti-spam-protection)
- [Sichere Links und sichere Anlagen](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365)
- [Sichere Anlagen für SharePoint, OneDrive und Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#part-5---verify-atp-for-sharepoint-onedrive-and-microsoft-teams-is-turned-on)
- [Automatisches Löschen von E-Mails in null Stunden](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#zero-hour-auto-purge-for-email-in-eop)

Überprüfen Sie außerdem die Warnungsrichtlinien Ihrer [Organisation,](../../compliance/alert-policies.md)insbesondere die Standardrichtlinien in der Kategorie [Bedrohungsverwaltung.](../../compliance/alert-policies.md#default-alert-policies)

## <a name="which-alert-policies-trigger-automated-investigations"></a>Welche Warnungsrichtlinien lösen automatisierte Untersuchungen aus?

Microsoft 365 bietet viele integrierte Warnungsrichtlinien, mit denen Missbrauch von Exchange-Administratorberechtigungen, Schadsoftwareaktivitäten, potenzielle externe und interne Bedrohungen und Risiken der Informationsverwaltung identifiziert werden können. Mehrere der [Standardmäßigen Warnungsrichtlinien können](../../compliance/alert-policies.md#default-alert-policies) automatisierte Untersuchungen auslösen. In der folgenden Tabelle werden die Warnungen beschrieben, die automatisierte Untersuchungen auslösen, ihren Schweregrad im Microsoft 365 Security Center und deren Generierung:

|Warnung|Severity|So wird die Warnung generiert|
|:---|:---|:---|
|Ein potenziell schädlicher URL-Klick wurde erkannt.|**High**|Diese Warnung wird generiert, wenn eine der folgenden Schritte auftritt: <ul><li>Ein durch sichere [Links](safe-links.md) in Ihrer Organisation geschützter Benutzer klickt auf einen schädlichen Link.</li><li>Diktieränderungen für URLs werden von Microsoft Defender für Office 365 identifiziert</li><li>Benutzer überschreiben Warnseiten für sichere Links (basierend auf der Richtlinie für sichere Links in [Ihrer Organisation).](set-up-safe-links-policies.md)</li></ul> <p> Weitere Informationen zu Ereignissen, die diese Warnung auslösen, finden Sie unter [Set up Safe Links policies](set-up-safe-links-policies.md).|
|Eine E-Mail-Nachricht wird von einem Benutzer als Schadsoftware oder Phishing gemeldet.|**Informational**|Diese Warnung wird generiert, wenn Benutzer in Ihrer Organisation Nachrichten mithilfe des [Berichtsnachrichten-Add-Ins](enable-the-report-message-add-in.md) oder [des Phishing-Add-Ins melden als Phishing-E-Mail melden.](enable-the-report-phish-add-in.md)|
|E-Mail-Nachrichten, die Schadsoftware enthalten, werden nach der Zustellung entfernt|**Informational**|Diese Warnung wird generiert, wenn E-Mail-Nachrichten, die Schadsoftware enthalten, an Postfächer in Ihrer Organisation zugestellt werden. Wenn dieses Ereignis auftritt, entfernt Microsoft die infizierten Nachrichten aus Exchange Online-Postfächern mithilfe der automatischen [Null-Stunden-Bereinigung](zero-hour-auto-purge.md).|
|E-Mail-Nachrichten, die Phish-URLs enthalten, werden nach der Zustellung entfernt|**Informational**|Diese Warnung wird generiert, wenn Nachrichten mit Phish an Postfächer in Ihrer Organisation zugestellt werden. Wenn dieses Ereignis auftritt, entfernt Microsoft die infizierten Nachrichten aus Exchange Online-Postfächern mithilfe der automatischen [Null-Stunden-Bereinigung](zero-hour-auto-purge.md).|
|Verdächtige E-Mail-Sendemuster werden erkannt|**Medium**|Diese Warnung wird generiert, wenn jemand in Ihrer Organisation verdächtige E-Mails gesendet hat und das Risiko besteht, dass das Senden von E-Mails eingeschränkt wird. Die Warnung ist eine frühzeitige Warnung für das Verhalten, die darauf hinweisen kann, dass das Konto gefährdet ist, aber nicht streng genug, um den Benutzer einzuschränken. <p> Obwohl es selten ist, kann eine von dieser Richtlinie generierte Warnung eine Anomalie sein. Es ist jedoch eine gute Idee, zu überprüfen, ob [das Benutzerkonto gefährdet ist.](responding-to-a-compromised-email-account.md)|
|Ein Benutzer kann keine E-Mails senden|**High**|Diese Warnung wird generiert, wenn jemand in Ihrer Organisation am Senden ausgehender E-Mails eingeschränkt ist. Diese Warnung führt in der Regel dazu, dass ein [E-Mail-Konto gefährdet ist.](responding-to-a-compromised-email-account.md) <p> Weitere Informationen zu eingeschränkten Benutzern finden Sie unter [Remove blocked users from the Restricted Users portal in Microsoft 365](removing-user-from-restricted-users-portal-after-spam.md).|
|

> [!TIP]
> Weitere Informationen zu Warnungsrichtlinien oder zum Bearbeiten der Standardeinstellungen finden Sie unter [Warnungsrichtlinien im Microsoft 365 Compliance Center](../../compliance/alert-policies.md).

## <a name="required-permissions-to-use-air-capabilities"></a>Erforderliche Berechtigungen für die Verwendung von AIR-Funktionen

Berechtigungen werden über bestimmte Rollen erteilt, z. B. über die in der folgenden Tabelle beschriebenen:

|Aufgabe|Erforderliche Rollen|
|---|---|
|Einrichten von AIR-Features|Eine der folgenden Rollen: <ul><li>Globaler Administrator</li><li>Sicherheitsadministrator</li></ul> <p> Diese Rollen können in [Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles) oder im Security & Compliance Center zugewiesen [werden.](permissions-in-the-security-and-compliance-center.md)|
|Starten einer automatisierten Untersuchung <p> --- oder --- <p> Genehmigen oder Ablehnen empfohlener Aktionen|Eine der folgenden Rollen, die in [Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles) oder im Security & Compliance Center zugewiesen [sind:](permissions-in-the-security-and-compliance-center.md) <ul><li>Globaler Administrator</li><li>Sicherheitsadministrator</li><li>Sicherheitsoperator</li><li>Sicherheitsleseberechtigter <br> --- und --- </li><li>Suchen und Löschen (diese Rolle wird nur im [Security & Compliance Center zugewiesen.](permissions-in-the-security-and-compliance-center.md) Möglicherweise müssen Sie dort eine neue Rollengruppe erstellen und der neuen Rollengruppe die Rolle Suchen und Löschen hinzufügen.</li></ul>|

## <a name="required-licenses"></a>Erforderliche Lizenzen

[Microsoft Defender für Office 365 Plan 2-Lizenzen](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2) sollten zugewiesen werden:

- Sicherheitsadministratoren (einschließlich globaler Administratoren)
- Das Sicherheitsteam Ihrer Organisation (einschließlich Sicherheitsleser und Personen mit der Rolle **Suchen und** Löschen)
- Endbenutzer


## <a name="changes-are-coming-soon-in-your-security-center"></a>Änderungen werden in Kürze in Ihrem Security Center vorgenommen

Wenn Sie bereits die AIR-Funktionen in Microsoft Defender für Office 365 verwenden, sehen Sie einige Änderungen im verbesserten [Microsoft 365 Security Center](../defender/overview-security-center.md). 

:::image type="content" source="../../media/m3d-action-center-unified.png" alt-text="Einheitliches Aktionscenter":::

Das neue und verbesserte Sicherheitscenter vereint die AIR-Funktionen in [Microsoft Defender für Office 365](defender-for-office-365.md) und in Microsoft Defender for [Endpoint](../defender-endpoint/automated-investigations.md). Dank dieser Updates und Verbesserungen kann Ihr Sicherheitsteam Details zu automatisierten Untersuchungen und Abhilfemaßnahmen für Ihre E-Mails, von mehreren Personen gemeinsam erstellte/genutzte Inhalte, Benutzerkonten und Geräte an einem Ort anzeigen.

> [!TIP]
> Das neue Microsoft 365 Security Center ( <https://security.microsoft.com> ) ersetzt die folgenden Center:
>
> - Office 365 Security & Compliance Center ( <https://protection.office.com> )
> - Microsoft Defender Security Center ( <https://securitycenter.windows.com> )
>
> Zusätzlich zum Ändern der URL gibt es ein neues Aussehen und Gefühl, das Ihrem Sicherheitsteam eine optimierte Benutzererfahrung bietet, mit Sichtbarkeit für mehr Bedrohungserkennungen an einem Ort.

### <a name="what-to-expect"></a>Das erwartet Sie

In der folgenden Tabelle sind Änderungen und Verbesserungen aufgeführt, die air in Microsoft Defender für Office 365 bietet.

|Element|Was ändert sich?|
|---|---|
|**Seite "Untersuchungen"**|Die Seite **"Aktualisierte Untersuchungen"** ist konsistenter mit dem, was Sie in [Microsoft Defender for Endpoint sehen.](/windows/security/threat-protection/microsoft-defender-atp/automated-investigations) Es werden einige allgemeine Format- und Formatänderungen angezeigt, die an der neuen, einheitlichen Untersuchungsansicht **ausgerichtet** sind. Das Untersuchungsdiagramm hat beispielsweise ein einheitliches Format.|
|**Registerkarte "Benutzer"**|Die **Registerkarte Benutzer** ist jetzt die Registerkarte **Postfächer.** Details zu Benutzern finden Sie auf der Registerkarte **Postfach.**|
|**Registerkarte "E-Mail"**|Die **Registerkarte E-Mail** wurde entfernt. Besuchen Sie die **Registerkarte Entitäten,** um eine Liste der E-Mail- und E-Mail-Clusterelemente zu sehen.|
|**Registerkarte Entitäten**|Die **Registerkarte Entitäten** verfügt über eine Tab-in-Tab-Formatvorlage, die eine Gesamtzusammenfassungsansicht und die Möglichkeit zum Filtern nach Entitätstyp enthält. Die **Registerkarte Entitäten** enthält nun **zusätzlich** zur Option Öffnen im Explorer eine Option Zum **Aufsuchen** gehen. Sie können jetzt entweder den [Bedrohungs-Explorer](threat-explorer.md) oder die [erweiterte Suche](../defender-endpoint/advanced-hunting-overview.md) verwenden, um Entitäten und Bedrohungen zu finden und nach Ergebnissen zu filtern.|
|**Registerkarte "Aktionen"**|Die Registerkarte **Aktionen aktualisiert** enthält jetzt eine **Registerkarte Ausstehende Aktionen** und eine Registerkarte **Aktionen-Verlauf.** Aktionen können in einem Seitenbereich genehmigt (oder abgelehnt) werden, der geöffnet wird, wenn Sie eine ausstehende Aktion auswählen.|
|**Registerkarte "Nachweis"**|Eine neue **Registerkarte Nachweis** zeigt die wichtigsten Entitätsbefunde im Zusammenhang mit Aktionen. Aktionen im Zusammenhang mit den einzelnen Nachweisen können in einem Seitenbereich genehmigt (oder abgelehnt) werden, der geöffnet wird, wenn Sie eine ausstehende Aktion auswählen.|
|**Info-Center**|Das aktualisierte **Aktionscenter** ( ) führt ausstehende und abgeschlossene Aktionen über E-Mails, [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) Geräte und Identitäten hinweg zusammen. Weitere Informationen finden Sie unter Action Center. (Weitere Informationen finden Sie unter [The Action Center](https://docs.microsoft.com/microsoft-365/security/defender/mtp-action-center).)
|**Seite "Vorfälle"**|Die **Seite Vorfälle** korreliert nun mehrere Untersuchungen, um eine bessere konsolidierte Ansicht der Untersuchungen zu bieten. ([Weitere Informationen zu Vorfällen](https://docs.microsoft.com/microsoft-365/security/defender/incidents-overview).)


## <a name="next-steps"></a>Nächste Schritte

- [Details und Ergebnisse einer automatisierten Untersuchung anzeigen](air-view-investigation-results.md#view-details-of-an-investigation)
- [Überprüfen und Genehmigen ausstehender Aktionen](air-remediation-actions.md)