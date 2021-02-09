---
title: Automatisierte Untersuchung und Reaktion in Microsoft Defender für Office 365
keywords: AIR, AutoIR, ATP, automatisiert, Untersuchung, Reaktion, Problembehebung, Bedrohungen, erweitert, Bedrohung, Schutz
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
ms.openlocfilehash: 43728db417e13dfc785731a1ee7b5f596013d6d4
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150195"
---
# <a name="automated-investigation-and-response-air-in-microsoft-defender-for-office-365"></a>Automatisierte Untersuchung und Reaktion (AIR) in Microsoft Defender für Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[Microsoft Defender für Office 365](office-365-atp.md) umfasst leistungsstarke automatisierte Untersuchungs- und Reaktionsfunktionen (AIR), die Zeit und Mühe Ihres Sicherheitsteams sparen können. Wenn Warnungen ausgelöst werden, ist es an Ihrem Sicherheitsteam, diese Warnungen zu überprüfen, zu priorisieren und darauf zu reagieren. Das Halten mit der Anzahl eingehender Warnungen kann überfordernd sein. Das Automatisieren einiger dieser Aufgaben kann hilfreich sein.

AIR ermöglicht Es Ihrem Sicherheitsteam, effizienter und effektiver zu arbeiten. Die Funktionen von AIR umfassen automatisierte Untersuchungsprozesse als Reaktion auf bekannte Bedrohungen, die heute vorhanden sind. Geeignete Abhilfemaßnahmen warten auf Genehmigung, sodass Ihr Sicherheitsteam effektiv auf erkannte Bedrohungen reagieren kann. Mit AIR kann sich Ihr Sicherheitsteam auf Aufgaben mit höherer Priorität konzentrieren, ohne wichtige ausgelöste Warnungen aus den Augen zu verlieren.

Inhalt dieses Artikels

- Der [allgemeine Fluss von AIR](#the-overall-flow-of-air);
- [So erhalten Sie AIR](#how-to-get-air); und 
- Die [erforderlichen Berechtigungen zum](#required-permissions-to-use-air-capabilities) Konfigurieren oder Verwenden von AIR-Funktionen. 
- Änderungen, die in Kürze in Ihrem Security Center zur Anwendung kommen

Dieser Artikel enthält außerdem [die nächsten Schritte](#next-steps)und Ressourcen, um mehr zu erfahren.

## <a name="the-overall-flow-of-air"></a>Der allgemeine Fluss von AIR

Eine Warnung wird ausgelöst, und ein Sicherheitsspielbuch startet eine automatisierte Untersuchung, was zu Ergebnissen und empfohlenen Aktionen führt. Hier ist der allgemeine Fluss von AIR Schritt für Schritt:

1. Eine automatisierte Untersuchung wird auf eine der folgenden Arten initiiert: 
   - Eine [Warnung wird entweder durch eine](#which-alert-policies-trigger-automated-investigations) verdächtige E-Mail ausgelöst (z. B. eine Nachricht, anlage, URL oder ein gefährdetes Benutzerkonto). Ein Vorfall wird erstellt, und eine automatisierte Untersuchung beginnt. oder
   - Ein Sicherheitsanalyst [startet eine automatisierte Untersuchung](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer) während der Verwendung von Threat [Explorer.](threat-explorer.md)
2. Während eine automatisierte Untersuchung ausgeführt wird, werden Daten über die entsprechende E-Mail und Entitäten im Zusammenhang mit dieser E-Mail gesammelt. Solche Entitäten können Dateien, URLs und Empfänger enthalten. Der Umfang der Untersuchung kann sich erhöhen, wenn neue und verwandte Warnungen ausgelöst werden.
3. Während und nach einer automatischen Untersuchung sind [Details und Ergebnisse](air-view-investigation-results.md) verfügbar. Die Ergebnisse umfassen [empfohlene Maßnahmen,](air-remediation-actions.md) die ergriffen werden können, um auf gefundene Bedrohungen zu reagieren und diese zu bedrohen.
4. Ihr Sicherheitsteam überprüft die Untersuchungsergebnisse [und Empfehlungen](air-view-investigation-results.md)und genehmigt oder lehnt [Abhilfemaßnahmen ab.](air-review-approve-pending-completed-actions.md)
5. Wenn ausstehende Abhilfemaßnahmen genehmigt (oder abgelehnt) werden, wird die automatisierte Untersuchung abgeschlossen.

In Microsoft Defender für Office 365 werden keine Korrekturaktionen automatisch ausgeführt. Abhilfemaßnahmen werden nur nach Genehmigung durch das Sicherheitsteam Ihrer Organisation ausgeführt. Die Funktionen von AIR sparen Ihrem Sicherheitsteam Zeit, indem Sie Abhilfemaßnahmen identifizieren und die Details bereitstellen, die für eine fundierte Entscheidung erforderlich sind.

Während und nach jeder automatisierten Untersuchung kann Ihr Sicherheitsteam:

- [Anzeigen von Details zu einer Warnung im Zusammenhang mit einer Untersuchung](air-view-investigation-results.md#view-details-about-an-alert-related-to-an-investigation)
- [Anzeigen der Ergebnisdetails einer Untersuchung](air-view-investigation-results.md#view-details-of-an-investigation)
- [Überprüfen und Genehmigen von Aktionen als Ergebnis einer Untersuchung](air-review-approve-pending-completed-actions.md)

> [!TIP]
> Eine ausführlichere Übersicht finden Sie unter [Funktionsweise von AIR.](automated-investigation-response-office.md)

## <a name="how-to-get-air"></a>So erhalten Sie AIR

Die Funktionen von AIR sind in [Microsoft Defender für Office 365](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2)enthalten, vorausgesetzt, Ihre Richtlinien und Warnungen sind konfiguriert. Benötigen Sie Hilfe? Befolgen Sie die Anweisungen unter ["Schutz vor Bedrohungen",](protect-against-threats.md) um die folgenden Schutzeinstellungen einrichten oder konfigurieren zu können:

- [Überwachungsprotokollierung](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off) (sollte aktiviert sein)
- [Richtlinien für Antischadsoftware](protect-against-threats.md#part-1---anti-malware-protection)
- [Schutz vor Phishing](protect-against-threats.md#part-2---anti-phishing-protection)
- [Antispamschutz](protect-against-threats.md#part-3---anti-spam-protection)
- [Schutz vor Phishing](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?part-2---anti-phishing-protection)
- [Antispamschutz](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?part-3---anti-spam-protection)
- [Sichere Links und sichere Anlagen](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365)
- [Sichere Anlagen für SharePoint, OneDrive und Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?part-5---verify-atp-for-sharepoint-onedrive-and-microsoft-teams-is-turned-on)
- [Automatisches Löschen zur Nullstunde für E-Mails](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?zero-hour-auto-purge-for-email-in-eop)
- [Sichere Anlagen für SharePoint, OneDrive und Microsoft Teams](protect-against-threats.md#part-5---verify-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams-is-turned-on)
- [Automatische Bereinigung zur Nullstunde für E-Mails.](protect-against-threats.md#zero-hour-auto-purge-for-email-in-eop)

Überprüfen Sie außerdem die Warnungsrichtlinien Ihrer [Organisation,](https://docs.microsoft.com/microsoft-365/compliance/alert-policies)insbesondere die Standardrichtlinien in der Kategorie ["Bedrohungsverwaltung".](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?default-alert-policies)

## <a name="which-alert-policies-trigger-automated-investigations"></a>Welche Warnungsrichtlinien lösen automatisierte Untersuchungen aus?

Microsoft 365 bietet viele integrierte Warnungsrichtlinien, mit denen Der Missbrauch von Exchange-Administratorberechtigungen, Schadsoftwareaktivitäten, potenzielle externe und interne Bedrohungen sowie Risiken der Informationsverwaltung identifiziert werden können. Einige der [standardmäßigen Warnungsrichtlinien können](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#default-alert-policies) automatisierte Untersuchungen auslösen. In der folgenden Tabelle werden die Warnungen beschrieben, die automatisierte Untersuchungen auslösen, ihren Schweregrad im Microsoft 365 Security Center und deren Generierung:

|Warnung|Severity|Wie die Warnung generiert wird|
|:---|:---|:---|
|Ein potenziell schädlicher URL-Klick wurde erkannt.|**High**|Diese Warnung wird generiert, wenn eine der folgenden Bedingungen auftritt: <ul><li>Ein Benutzer, der durch [sichere Links](atp-safe-links.md) in Ihrer Organisation geschützt ist, klickt auf einen schädlichen Link.</li><li>Von Microsoft Defender für Office 365 identifizierte Änderungen der Diktats für URLs</li><li>Benutzer überschreiben Warnseiten für sichere Links (basierend auf der Richtlinie für sichere [Links in Ihrer Organisation).](set-up-atp-safe-links-policies.md)</li></ul> <p> Weitere Informationen zu Ereignissen, die diese Warnung auslösen, finden Sie unter ["Einrichten von Richtlinien für sichere Links".](set-up-atp-safe-links-policies.md)|
|Eine E-Mail-Nachricht wird von einem Benutzer als Schadsoftware oder Phishing gemeldet.|**Informational**|Diese Warnung wird generiert, wenn Benutzer in Ihrer Organisation Nachrichten mithilfe des [Add-Ins](enable-the-report-message-add-in.md) "Nachricht melden" oder "Phishing melden" als [Phishing-E-Mail melden.](enable-the-report-phish-add-in.md)|
|E-Mail-Nachrichten, die Schadsoftware enthalten, werden nach der Zustellung entfernt|**Informational**|Diese Warnung wird generiert, wenn E-Mail-Nachrichten, die Schadsoftware enthalten, an Postfächer in Ihrer Organisation zugestellt werden. Wenn dieses Ereignis auftritt, entfernt Microsoft die infizierten Nachrichten aus Exchange Online-Postfächern, indem die automatische Bereinigung zur [Nullstunde verwendet wird.](zero-hour-auto-purge.md)|
|E-Mail-Nachrichten mit Phishing-URLs werden nach der Zustellung entfernt.|**Informational**|Diese Warnung wird generiert, wenn Nachrichten mit Phishing an Postfächer in Ihrer Organisation zugestellt werden. Wenn dieses Ereignis auftritt, entfernt Microsoft die infizierten Nachrichten aus Exchange Online-Postfächern, indem die automatische Bereinigung zur [Nullstunde verwendet wird.](zero-hour-auto-purge.md)|
|Verdächtige Muster für das Senden von E-Mails werden erkannt|**Medium**|Diese Warnung wird generiert, wenn jemand in Ihrer Organisation verdächtige E-Mails gesendet hat und das Senden von E-Mails eingeschränkt werden kann. Die Warnung ist eine frühe Warnung für verhalten, die darauf hinweisen könnte, dass das Konto gefährdet ist, aber nicht streng genug, um den Benutzer einzuschränken. <p> Obwohl es selten ist, kann eine durch diese Richtlinie generierte Warnung eine Anomalie sein. Es ist jedoch eine gute Idee zu überprüfen, ob [das Benutzerkonto gefährdet ist.](responding-to-a-compromised-email-account.md)|
|Ein Benutzer kann keine E-Mails senden|**High**|Diese Warnung wird generiert, wenn jemand in Ihrer Organisation am Senden ausgehender E-Mails eingeschränkt ist. Diese Warnung wird in der Regel angezeigt, wenn [ein E-Mail-Konto gefährdet ist.](responding-to-a-compromised-email-account.md) <p> Weitere Informationen zu eingeschränkten Benutzern finden Sie unter "Entfernen blockierter Benutzer aus dem Portal für [eingeschränkte Benutzer" in Microsoft 365.](removing-user-from-restricted-users-portal-after-spam.md)|
|

> [!TIP]
> Weitere Informationen zu Warnungsrichtlinien oder zum Bearbeiten der Standardeinstellungen finden Sie unter Warnungsrichtlinien im [Microsoft 365 Compliance Center.](https://docs.microsoft.com/microsoft-365/compliance/alert-policies)

## <a name="required-permissions-to-use-air-capabilities"></a>Erforderliche Berechtigungen für die Verwendung von AIR-Funktionen

Berechtigungen werden über bestimmte Rollen erteilt, z. B. die in der folgenden Tabelle beschriebenen:

|Aufgabe|Rolle(en) erforderlich|
|---|---|
|Einrichten von AIR-Features|Eine der folgenden Rollen: <ul><li>Globaler Administrator</li><li>Sicherheitsadministrator</li></ul> <p> Diese Rollen können in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) oder im Security & Compliance Center zugewiesen [werden.](permissions-in-the-security-and-compliance-center.md)|
|Starten einer automatisierten Untersuchung <p> --- oder --- <p> Genehmigen oder Ablehnen empfohlener Aktionen|Eine der folgenden Rollen, die in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) oder im Security & Compliance Center zugewiesen [sind:](permissions-in-the-security-and-compliance-center.md) <ul><li>Globaler Administrator</li><li>Sicherheitsadministrator</li><li>Sicherheitsoperator</li><li>Sicherheitsleseberechtigter <br> --- und --- </li><li>Suchen und Löschen (diese Rolle wird nur im [Security & Compliance Center zugewiesen.](permissions-in-the-security-and-compliance-center.md) Möglicherweise müssen Sie dort eine neue Rollengruppe erstellen und die Rolle "Suchen und Löschen" zu dieser neuen Rollengruppe hinzufügen.</li></ul>|

## <a name="required-licenses"></a>Erforderliche Lizenzen

[Microsoft Defender für Office 365 Plan 2-Lizenzen](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) sollten zugewiesen werden für:

- Sicherheitsadministratoren (einschließlich globaler Administratoren)
- Das Sicherheitsteam Ihrer Organisation (einschließlich Sicherheitsleser und Personen mit der Rolle "Suchen und **Löschen")**
- Endbenutzer


## <a name="changes-are-coming-soon-in-your-security-center"></a>Änderungen werden in Kürze in Ihrem Security Center vorgenommen

Wenn Sie bereits die FUNKTIONEN von AIR in Microsoft Defender für Office 365 verwenden, werden Sie einige Änderungen im verbesserten [Microsoft 365 Security Center sehen.](../mtp/overview-security-center.md) 

:::image type="content" source="../../media/m3d-action-center-unified.png" alt-text="Einheitliches Aktionscenter":::

Das neue und verbesserte Sicherheitscenter vereint die FUNKTIONEN von AIR in [Microsoft Defender für Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) und in Microsoft Defender für [Endpunkt.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations) Mit diesen Updates und Verbesserungen kann Ihr Sicherheitsteam Details zu automatisierten Untersuchungen und Abhilfemaßnahmen über Ihre E-Mails, Inhalte für die Zusammenarbeit, Benutzerkonten und Geräte hinweg anzeigen.

> [!TIP]
> Das neue Microsoft 365 Security Center ( [https://security.microsoft.com](https://security.microsoft.com) ) ersetzt die folgenden Center:
> - Office 365 Security & Compliance Center ( [https://protection.office.com](https://protection.office.com) )
> - Microsoft Defender Security Center ( [https://securitycenter.windows.com](https://securitycenter.windows.com) )
>
> Zusätzlich zur Änderung der URL gibt es ein neues Aussehen und Gefühl, das Ihrem Sicherheitsteam eine optimierte Benutzererfahrung mit Sichtbarkeit für mehr Bedrohungserkennungen an einem Ort bietet. 

### <a name="what-to-expect"></a>Was Sie erwarten können

In der folgenden Tabelle sind Änderungen und Verbesserungen aufgeführt, die in AIR in Microsoft Defender für Office 365 verfügbar sind.

|Element  |Was ändert sich?  |
|---------|---------|
|**Seite "Untersuchungen"**     | Die aktualisierte **Seite "Untersuchungen"** ist konsistenter mit dem, was Sie in [Microsoft Defender for Endpoint sehen.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations) Es werden einige allgemeine Format- und Formatierungsänderungen angezeigt, die an der neuen, einheitlichen Ansicht **"Untersuchungen"** ausgerichtet sind. Das Untersuchungsdiagramm hat beispielsweise ein einheitliches Format.        |
|**Registerkarte "Benutzer"** |Die **Registerkarte "Benutzer"** ist jetzt die Registerkarte **"Postfächer".** Details zu Benutzern werden auf der Registerkarte **"Postfach"** aufgeführt. |
|**Registerkarte "E-Mail"** |Die **Registerkarte "E-Mail"** wurde entfernt. Besuchen Sie **die Registerkarte "Entitäten",** um eine Liste der E-Mail- und E-Mail-Clusterelemente zu sehen. |
|**Registerkarte "Entitäten"** | Die **Registerkarte "Entitäten"** verfügt über ein Tab-in-Registerkartenformat, das eine Übersichtsansicht und die Möglichkeit zum Filtern nach Entitätstyp enthält. Die **Registerkarte "Entitäten"** enthält **jetzt** zusätzlich zur Option "Im Explorer öffnen" die Option "Suche **wechseln".** Sie können jetzt entweder den [Bedrohungs-Explorer oder](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer) die erweiterte [Suche](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview) verwenden, um Entitäten und Bedrohungen zu finden und nach Ergebnissen zu filtern. | 
|**Registerkarte "Aktionen"** |Die aktualisierte **Registerkarte "Aktionen"** enthält jetzt eine Registerkarte **"Ausstehende** Aktionen" und eine Registerkarte **"Aktionsverlauf".** Aktionen können in einem Seitenbereich genehmigt (oder abgelehnt) werden, der geöffnet wird, wenn Sie eine ausstehende Aktion auswählen. |
|**Registerkarte "Nachweis"** | Auf einer neuen **Registerkarte "Nachweis"** werden die wichtigsten Entitätsergebnisse im Zusammenhang mit Aktionen angezeigt. Aktionen im Zusammenhang mit jedem Nachweis können in einem Seitenbereich genehmigt (oder abgelehnt) werden, der geöffnet wird, wenn Sie eine ausstehende Aktion auswählen. |
|**Aktionscenter** |Das aktualisierte **Aktionscenter** ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) vereint ausstehende und abgeschlossene Aktionen über E-Mails, Geräte und Identitäten hinweg. Weitere Informationen finden Sie im Action Center. (Weitere Informationen finden Sie im [Aktionscenter.)](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
|**Seite "Vorfälle"** |Die **Seite "Vorfälle"** korreliert nun mehrere Untersuchungen zusammen, um eine bessere konsolidierte Ansicht der Untersuchungen zu bieten. ([Weitere Informationen zu Vorfällen.)](https://docs.microsoft.com/microsoft-365/security/mtp/incidents-overview)


## <a name="next-steps"></a>Nächste Schritte

- [Details und Ergebnisse einer automatisierten Untersuchung anzeigen](air-view-investigation-results.md#view-details-of-an-investigation)
- [Überprüfen und Genehmigen ausstehender Aktionen](air-remediation-actions.md)
