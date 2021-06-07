---
title: Automatisierte Untersuchung und Reaktion in Microsoft Defender für Office 365
keywords: AIR, autoIR, Microsoft Defender für Endpunkt, automatisiert, Untersuchung, Reaktion, Korrektur, Bedrohungen, erweitert, Bedrohung, Schutz
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
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
ms.openlocfilehash: c3a86436706b350557e9a39f81c1ef6430ac88ff
ms.sourcegitcommit: f3d1009840513703c38bab99a6e13a3656eae5ee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/07/2021
ms.locfileid: "52793160"
---
# <a name="automated-investigation-and-response-air-in-microsoft-defender-for-office-365"></a>Automatisierte Untersuchung und Reaktion (AIR) in Microsoft Defender für Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[Microsoft Defender für Office 365](defender-for-office-365.md) umfasst leistungsstarke AIR-Funktionen (Automated Investigation and Response), mit denen Ihr Sicherheitsteam Zeit und Mühe sparen kann. Wenn Warnungen ausgelöst werden, liegt es an Ihrem Sicherheitsteam, diese Warnungen zu überprüfen, zu priorisieren und darauf zu reagieren. Es kann überwältigend sein, mit dem Volumen der eingehenden Warnungen Schritt zu halten. Die Automatisierung einiger dieser Aufgaben kann hilfreich sein.

AIR ermöglicht Es Ihrem Sicherheitsteam, effizienter und effektiver zu arbeiten. AIR-Funktionen umfassen automatisierte Untersuchungsprozesse als Reaktion auf bekannte Bedrohungen, die heute vorhanden sind. Geeignete Korrekturmaßnahmen warten auf die Genehmigung, sodass Ihr Sicherheitsteam effektiv auf erkannte Bedrohungen reagieren kann. Mit AIR kann sich Ihr Sicherheitsteam auf Aufgaben mit höherer Priorität konzentrieren, ohne wichtige ausgelöste Warnungen aus den Augen zu verlieren.

Inhalt dieses Artikels

- Der [allgemeine Fluss von AIR;](#the-overall-flow-of-air)
- [So erhalten Sie AIR](#how-to-get-air); Und
- Die [erforderlichen Berechtigungen](#required-permissions-to-use-air-capabilities) zum Konfigurieren oder Verwenden von AIR-Funktionen.
- Änderungen, die in Kürze in Ihrem Sicherheitscenter verfügbar sind

Dieser Artikel enthält auch [die nächsten Schritte](#next-steps)und Ressourcen, um mehr zu erfahren.

## <a name="the-overall-flow-of-air"></a>Der allgemeine Fluss von AIR

Eine Warnung wird ausgelöst, und ein Sicherheits-Playbook startet eine automatisierte Untersuchung, die zu Ergebnissen und empfohlenen Aktionen führt. Hier sehen Sie den gesamten Air-Fluss, Schritt für Schritt:

1. Eine automatisierte Untersuchung wird auf eine der folgenden Arten initiiert:
   - Eine [Warnung wird](#which-alert-policies-trigger-automated-investigations) entweder durch etwas Verdächtiges in einer E-Mail ausgelöst (z. B. eine Nachricht, eine Anlage, eine URL oder ein kompromittiertes Benutzerkonto). Ein Vorfall wird erstellt, und eine automatisierte Untersuchung beginnt; Oder
   - Ein Sicherheitsanalyst [startet eine automatisierte Untersuchung,](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer) während [er den Bedrohungs-Explorer verwendet.](threat-explorer.md)
2. Während eine automatisierte Untersuchung ausgeführt wird, werden Daten über die betreffende E-Mail und Entitäten im Zusammenhang mit dieser E-Mail gesammelt. Solche Entitäten können Dateien, URLs und Empfänger enthalten. Der Umfang der Untersuchung kann sich erhöhen, wenn neue und verwandte Warnungen ausgelöst werden.
3. Während und nach einer automatisierten Untersuchung können [Details und Ergebnisse](air-view-investigation-results.md) angezeigt werden. Zu den Ergebnissen gehören [empfohlene Maßnahmen,](air-remediation-actions.md) die ergriffen werden können, um auf gefundene Bedrohungen zu reagieren und sie zu beheben.
4. Ihr Sicherheitsteam überprüft die [Untersuchungsergebnisse und Empfehlungen](air-view-investigation-results.md)und [genehmigt oder lehnt Abhilfemaßnahmen ab.](air-review-approve-pending-completed-actions.md)
5. Sobald ausstehende Abhilfemaßnahmen genehmigt (oder abgelehnt) werden, wird die automatisierte Untersuchung abgeschlossen.

In Microsoft Defender für Office 365 werden keine Korrekturmaßnahmen automatisch ausgeführt. Abhilfemaßnahmen werden nur nach Genehmigung durch das Sicherheitsteam Ihrer Organisation ausgeführt. AIR-Funktionen sparen Ihrem Sicherheitsteam Zeit, indem Sie Abhilfemaßnahmen identifizieren und die details bereitstellen, die für eine fundierte Entscheidung erforderlich sind.

Während und nach jeder automatisierten Untersuchung kann Ihr Sicherheitsteam:

- [Anzeigen von Details zu einer Warnung im Zusammenhang mit einer Untersuchung](air-view-investigation-results.md#view-details-about-an-alert-related-to-an-investigation)
- [Anzeigen der Ergebnisdetails einer Untersuchung](air-view-investigation-results.md#view-details-of-an-investigation)
- [Überprüfen und Genehmigen von Aktionen als Ergebnis einer Untersuchung](air-review-approve-pending-completed-actions.md)

> [!TIP]
> Eine detailliertere Übersicht finden Sie unter ["Funktionsweise von AIR".](automated-investigation-response-office.md)

## <a name="how-to-get-air"></a>So erhalten Sie AIR

AIR-Funktionen sind in [Microsoft Defender für Office 365](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2)enthalten, sofern Ihre Richtlinien und Warnungen konfiguriert sind. Benötigen Sie Hilfe? Befolgen Sie die Anleitungen unter ["Schutz vor Bedrohungen",](protect-against-threats.md) um die folgenden Schutzeinstellungen einzurichten oder zu konfigurieren:

- [Überwachungsprotokollierung](../../compliance/turn-audit-log-search-on-or-off.md) (sollte aktiviert sein)
- [Schutz vor Schadsoftware](protect-against-threats.md#part-1---anti-malware-protection-in-eop)
- [Antiphishingschutz](../office-365-security/protect-against-threats.md#part-2---anti-phishing-protection-in-eop-and-defender-for-office-365)
- [Antispamschutz](protect-against-threats.md#part-3---anti-spam-protection-in-eop)
- [Sichere Links und sichere Anlagen](protect-against-threats.md#part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365)
- [Sichere Anlagen für SharePoint, OneDrive und Microsoft Teams](protect-against-threats.md#part-5---verify-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams-is-turned-on)
- [Automatische Bereinigung zur Nullstunde für E-Mails](protect-against-threats.md#zero-hour-auto-purge-for-email-in-eop)

Überprüfen Sie außerdem die [Warnungsrichtlinien Ihrer Organisation,](../../compliance/alert-policies.md)insbesondere die [Standardrichtlinien in der Kategorie "Bedrohungsverwaltung".](../../compliance/alert-policies.md#default-alert-policies)

## <a name="which-alert-policies-trigger-automated-investigations"></a>Welche Warnungsrichtlinien lösen automatisierte Untersuchungen aus?

Microsoft 365 bietet viele integrierte Warnungsrichtlinien, die dazu beitragen, Exchange Missbrauch von Administratorberechtigungen, Schadsoftwareaktivitäten, potenzielle externe und interne Bedrohungen und Informationsgovernance-Risiken zu identifizieren. Mehrere der [Standardwarnungsrichtlinien](../../compliance/alert-policies.md#default-alert-policies) können automatisierte Untersuchungen auslösen. In der folgenden Tabelle werden die Warnungen beschrieben, die automatisierte Untersuchungen auslösen, deren Schweregrad im Microsoft 365 Security Center und ihre Generierung:

|Warnung|Severity|Generieren der Warnung|
|---|---|---|
|Ein potenziell schädlicher URL-Klick wurde erkannt.|**High**|Diese Warnung wird generiert, wenn eine der folgenden Aktionen auftritt: <ul><li>Ein Benutzer, der durch [sichere Links](safe-links.md) in Ihrer Organisation geschützt ist, klickt auf einen schädlichen Link</li><li>Bewertungsänderungen für URLs werden von Microsoft Defender für Office 365</li><li>Benutzer überschreiben Warnseiten für sichere Links (basierend auf der [Richtlinie für sichere Links](set-up-safe-links-policies.md)In Ihrer Organisation).</li></ul> <p> Weitere Informationen zu Ereignissen, die diese Warnung auslösen, finden Sie unter [Einrichten von Richtlinien für sichere Links.](set-up-safe-links-policies.md)|
|Eine E-Mail-Nachricht wird von einem Benutzer als Schadsoftware oder Phishing gemeldet.|**Zur Information**|Diese Warnung wird generiert, wenn Benutzer in Ihrer Organisation Nachrichten mithilfe des [Add-Ins "Nachricht melden"](enable-the-report-message-add-in.md) oder des [Add-Ins "Phishing melden" als Phishing-E-Mail](enable-the-report-phish-add-in.md)melden.|
|E-Mail-Nachrichten mit Schadsoftware werden nach der Zustellung entfernt.|**Zur Information**|Diese Warnung wird generiert, wenn E-Mail-Nachrichten mit Schadsoftware an Postfächer in Ihrer Organisation übermittelt werden. Wenn dieses Ereignis auftritt, entfernt Microsoft die infizierten Nachrichten aus Exchange Online Postfächern mithilfe der [automatischen Bereinigung zur Nullstunde.](zero-hour-auto-purge.md)|
|E-Mail-Nachrichten mit Phishing-URLs werden nach der Zustellung entfernt.|**Zur Information**|Diese Warnung wird generiert, wenn Nachrichten mit Phishing an Postfächer in Ihrer Organisation übermittelt werden. Wenn dieses Ereignis auftritt, entfernt Microsoft die infizierten Nachrichten aus Exchange Online Postfächern mithilfe der [automatischen Bereinigung zur Nullstunde.](zero-hour-auto-purge.md)|
|Verdächtige E-Mail-Sendemuster werden erkannt|**Medium**|Diese Warnung wird generiert, wenn jemand in Ihrer Organisation verdächtige E-Mails gesendet hat und das Risiko besteht, dass das Senden von E-Mails eingeschränkt wird. Die Warnung ist eine frühe Warnung für Verhaltensweisen, die darauf hindeuten können, dass das Konto kompromittiert ist, aber nicht schwerwiegend genug ist, um den Benutzer einzuschränken. <p> Obwohl dies selten ist, kann eine von dieser Richtlinie generierte Warnung eine Anomalie sein. Es empfiehlt sich jedoch zu [überprüfen, ob das Benutzerkonto kompromittiert ist.](responding-to-a-compromised-email-account.md)|
|Ein Benutzer kann keine E-Mails senden|**High**|Diese Warnung wird generiert, wenn eine Person in Ihrer Organisation daran gehindert wird, ausgehende E-Mails zu senden. Diese Warnung wird in der Regel ausgelöst, wenn ein [E-Mail-Konto kompromittiert ist.](responding-to-a-compromised-email-account.md) <p> Weitere Informationen zu eingeschränkten Benutzern finden Sie unter [Entfernen blockierter Benutzer aus dem Portal für eingeschränkte Benutzer in Microsoft 365](removing-user-from-restricted-users-portal-after-spam.md).|
|

> [!TIP]
> Weitere Informationen zu Warnungsrichtlinien oder zum Bearbeiten der Standardeinstellungen finden Sie [unter "Warnungsrichtlinien" im Microsoft 365 Compliance Center.](../../compliance/alert-policies.md)

## <a name="required-permissions-to-use-air-capabilities"></a>Erforderliche Berechtigungen für die Verwendung von AIR-Funktionen

Berechtigungen werden über bestimmte Rollen erteilt, z. B. über die in der folgenden Tabelle beschriebenen Rollen:

|Aufgabe|Rolle(n) erforderlich|
|---|---|
|Einrichten von AIR-Features|Eine der folgenden Rollen: <ul><li>Globaler Administrator</li><li>Sicherheitsadministrator</li></ul> <p> Diese Rollen können in [Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles) oder im [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md)zugewiesen werden.|
|Beginnen einer automatische Untersuchung <p> --- oder --- <p> Genehmigen oder Ablehnen empfohlener Aktionen|Eine der folgenden Rollen, die in [Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles) oder im [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md)zugewiesen ist: <ul><li>Globaler Administrator</li><li>Sicherheitsadministrator</li><li>Sicherheitsoperator</li><li>Sicherheitsleseberechtigter <br> --- und --- </li><li>Suchen und Löschen (diese Rolle wird nur im [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md)zugewiesen. Möglicherweise müssen Sie dort eine neue Rollengruppe erstellen und der neuen Rollengruppe die Rolle "Suchen und Löschen" hinzufügen.</li></ul>|

## <a name="required-licenses"></a>Erforderliche Lizenzen

[Microsoft Defender für Office 365 Plan 2-Lizenzen](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2) sollten zugewiesen werden:

- Sicherheitsadministratoren (einschließlich globaler Administratoren)
- Sicherheitsteam Ihrer Organisation (einschließlich Sicherheitsleser und Personen mit der Rolle **"Suchen und Löschen")**
- Endbenutzer

## <a name="changes-are-coming-soon-in-your-security-center"></a>Änderungen werden in Kürze in Ihrem Security Center verfügbar sein.

Wenn Sie bereits AIR-Funktionen in Microsoft Defender für Office 365 verwenden, werden Einige Änderungen im [verbesserten Microsoft 365 Security Center angezeigt.](../defender/overview-security-center.md)

:::image type="content" source="../../media/m3d-action-center-unified.png" alt-text="Einheitliches Info-Center":::

Das neue und verbesserte Sicherheitscenter vereint AIR-Funktionen in [Microsoft Defender für Office 365](defender-for-office-365.md) und in Microsoft Defender für [Endpunkt.](../defender-endpoint/automated-investigations.md) Dank dieser Updates und Verbesserungen kann Ihr Sicherheitsteam Details zu automatisierten Untersuchungen und Abhilfemaßnahmen für Ihre E-Mails, von mehreren Personen gemeinsam erstellte/genutzte Inhalte, Benutzerkonten und Geräte an einem Ort anzeigen.

> [!TIP]
> Das neue Microsoft 365 Security Center ( <https://security.microsoft.com> ) ersetzt die folgenden Center:
>
> - Office 365 Security & Compliance Center ( <https://protection.office.com> )
> - Microsoft Defender Security Center ( <https://securitycenter.windows.com> )
>
> Zusätzlich zur Änderung der URL gibt es ein neues Aussehen und Verhalten, das Ihrem Sicherheitsteam eine optimierte Umgebung mit Sichtbarkeit für mehr Bedrohungserkennungen an einem Ort bietet.

### <a name="what-to-expect"></a>Das erwartet Sie

In der folgenden Tabelle sind Änderungen und Verbesserungen aufgeführt, die AIR in Microsoft Defender für Office 365.

|Element|Was ändert sich?|
|---|---|
|**Seite "Untersuchungen"**|Die aktualisierte Seite **"Untersuchungen"** ist konsistenter mit den Informationen in [Microsoft Defender für Endpunkt.](/windows/security/threat-protection/microsoft-defender-atp/automated-investigations) Es werden einige allgemeine Format- und Formatierungsänderungen angezeigt, die mit der neuen, einheitlichen Ansicht **"Untersuchungen"** übereinstimmen. Beispielsweise weist das Untersuchungsdiagramm ein einheitlicheres Format auf.|
|Registerkarte **"Benutzer"**|Die Registerkarte **"Benutzer"** ist jetzt die Registerkarte **"Postfächer".** Details zu Benutzern sind auf der Registerkarte **"Postfach"** aufgeführt.|
|Registerkarte **"E-Mail"**|Die Registerkarte **"E-Mail"** wurde entfernt. besuchen Sie die Registerkarte **"Entitäten",** um eine Liste der E-Mail- und E-Mail-Clusterelemente anzuzeigen.|
|Registerkarte **"Entitäten"**|Die Registerkarte **"Entitäten"** verfügt über eine Registerkartenformatvorlage, die eine Zusammenfassungsansicht und die Möglichkeit zum Filtern nach Entitätstyp enthält. Die Registerkarte **"Entitäten"** enthält jetzt zusätzlich zur Option **"Im Explorer öffnen"** eine Option **"Gehe zu suchen".** Sie können jetzt entweder [den Bedrohungs-Explorer](threat-explorer.md) oder [die erweiterte Suche](../defender-endpoint/advanced-hunting-overview.md) verwenden, um Entitäten und Bedrohungen zu finden und nach Ergebnissen zu filtern.|
|Registerkarte **"Aktionen"**|Die aktualisierte Registerkarte **"Aktionen"** enthält jetzt eine Registerkarte **"Ausstehende Aktionen"** und eine Registerkarte **"Aktionsverlauf".** Aktionen können in einem Seitenbereich genehmigt (oder abgelehnt) werden, der geöffnet wird, wenn Sie eine ausstehende Aktion auswählen.|
|**Registerkarte "Nachweis"**|Eine neue Registerkarte **"Nachweis"** zeigt die wichtigsten Entitätsergebnisse im Zusammenhang mit Aktionen an. Aktionen im Zusammenhang mit jedem Nachweis können in einem Seitenbereich genehmigt (oder abgelehnt) werden, der geöffnet wird, wenn Sie eine ausstehende Aktion auswählen.|
|**Info-Center**|Das aktualisierte **Info-Center** ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) vereint ausstehende und abgeschlossene Aktionen über E-Mails, Geräte und Identitäten hinweg. Weitere Informationen finden Sie im Info-Center. (Weitere Informationen finden Sie [im Info-Center.)](../defender/m365d-action-center.md)|
|Seite **"Vorfälle"**|Die Seite **"Vorfälle"** korreliert nun mehrere Untersuchungen zusammen, um eine bessere konsolidierte Ansicht der Untersuchungen bereitzustellen. ([Weitere Informationen zu Vorfällen](../defender/incidents-overview.md).)|
|

## <a name="next-steps"></a>Nächste Schritte

- [Details und Ergebnisse einer automatisierten Untersuchung anzeigen](air-view-investigation-results.md#view-details-of-an-investigation)
- [Überprüfen und Genehmigen ausstehender Aktionen](air-remediation-actions.md)
