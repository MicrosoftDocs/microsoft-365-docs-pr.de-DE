---
title: Warnungsrichtlinien im Security & Compliance Center
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
description: Erstellen Sie Warnungsrichtlinien im Security and Compliance Center in Office 365 und Microsoft 365, um potenzielle Bedrohungen, Datenverlust und Berechtigungsprobleme zu überwachen.
ms.openlocfilehash: 2fe23f3e6d6889c3fc80b94be6a07095e06d3d68
ms.sourcegitcommit: 959c3c3633e40b7b0f5e2c8372409778005a24db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/15/2021
ms.locfileid: "52950119"
---
# <a name="alert-policies-in-the-security-and-compliance-center"></a>Warnungsrichtlinien im Security & Compliance Center

Sie können die Warnungsrichtlinien- und Warnungsdashboard-Tools im Microsoft 365 Security and Compliance Center verwenden, um Warnungsrichtlinien zu erstellen und dann die Warnungen anzuzeigen, die generiert werden, wenn Benutzer Aktivitäten ausführen, die den Bedingungen einer Warnungsrichtlinie entsprechen. Es gibt mehrere Standardwarnungsrichtlinien, mit denen Sie Aktivitäten überwachen können, z. B. das Zuweisen von Administratorrechten in Exchange Online, Schadsoftwareangriffe, Phishingkampagnen und ungewöhnliche Ebenen von Dateilöschungen und externer Freigabe.

Mit Warnungsrichtlinien können Sie die Warnungen kategorisieren, die durch eine Richtlinie ausgelöst werden, die Richtlinie auf alle Benutzer in Ihrer Organisation anwenden, einen Schwellenwert für den Zeitpunkt festlegen, an dem eine Warnung ausgelöst wird, und entscheiden, ob E-Mail-Benachrichtigungen empfangen werden sollen, wenn Warnungen ausgelöst werden. There's also a **View alerts** page in the security and compliance center where you can view and filter alerts, set an alert status to help you manage alerts, and then dismiss alerts after you've addressed or resolved the underlying incident.

> [!NOTE]
> Warnungsrichtlinien sind für Organisationen mit einem Microsoft 365 Enterprise-, Office 365 Enterprise- oder Office 365 US Government E1/F1/G1-, E3/F3/G3- oder E5/G5-Abonnement verfügbar. Erweiterte Funktionen sind nur für Organisationen mit einem E5/G5-Abonnement oder für Organisationen mit einem E1/F1/G1- oder E3/F3/G3-Abonnement und einem Microsoft Defender für Office 365 P2 oder einem Microsoft 365 E5 Compliance oder einem E5 eDiscovery- und Audit-Add-On-Abonnement verfügbar. Die Funktionalität, die ein E5/G5- oder Add-On-Abonnement erfordert, wird in diesem Thema hervorgehoben. Beachten Sie außerdem, dass Warnungsrichtlinien in Office 365 GCC-, GCC High- und DoD-US-Behördenumgebungen verfügbar sind.

## <a name="how-alert-policies-work"></a>Funktionsweise von Warnungsrichtlinien

Hier finden Sie eine kurze Übersicht über die Funktionsweise von Warnungsrichtlinien und die Warnungen, die ausgelöst werden, wenn Benutzer- oder Administratoraktivitäten den Bedingungen einer Warnungsrichtlinie entsprechen.

![Übersicht über die Funktionsweise von Warnungsrichtlinien](../media/e02a622d-b429-448b-8107-dd1a4770b4e0.png)

1. An admin in your organization creates, configures, and turns on an alert policy by using the **Alert policies** page in the security and compliance center. Sie können Warnungsrichtlinien auch mithilfe des [Cmdlets "New-ProtectionAlert"](/powershell/module/exchange/new-protectionalert) in Security & Compliance Center PowerShell erstellen.

   Um Warnungsrichtlinien zu erstellen, müssen Sie der Rolle "Warnungen verwalten" oder der Rolle "Organisationskonfiguration" im Security & Compliance Center zugewiesen werden.

   > [!NOTE]
   > Es dauert bis zu 24 Stunden nach dem Erstellen oder Aktualisieren einer Warnungsrichtlinie, bevor Warnungen durch die Richtlinie ausgelöst werden können. Dies liegt daran, dass die Richtlinie mit dem Warnungserkennungsmodul synchronisiert werden muss.

2. Ein Benutzer führt eine Aktivität aus, die den Bedingungen einer Warnungsrichtlinie entspricht. Bei Schadsoftwareangriffen lösen infizierte E-Mail-Nachrichten, die an Benutzer in Ihrer Organisation gesendet werden, eine Warnung aus.

3. Microsoft 365 generiert eine Warnung, die auf der Seite **"Warnungen anzeigen"** im Security & Compliance Center angezeigt wird. Wenn E-Mail-Benachrichtigungen für die Warnungsrichtlinie aktiviert sind, sendet Microsoft außerdem eine Benachrichtigung an eine Liste von Empfängern. Die Warnungen, die ein Administrator oder andere Benutzer sehen können, die auf der Seite "Warnungen anzeigen" durch die Rollen bestimmt werden, die dem Benutzer zugewiesen sind. Weitere Informationen finden Sie unter [RBAC-Berechtigungen, die zum Anzeigen von Warnungen erforderlich sind.](#rbac-permissions-required-to-view-alerts)

4. Ein Administrator verwaltet Warnungen im Security and Compliance Center. Das Verwalten von Warnungen besteht darin, einen Warnungsstatus zuzuweisen, um untersuchungen nachzuverfolgen und zu verwalten.

## <a name="alert-policy-settings"></a>Warnungsrichtlinieneinstellungen

Eine Warnungsrichtlinie besteht aus einer Reihe von Regeln und Bedingungen, die die Benutzer- oder Administratoraktivität definieren, die eine Warnung generiert, eine Liste der Benutzer, die die Warnung auslösen, wenn sie die Aktivität ausführen, und einen Schwellenwert, der definiert, wie oft die Aktivität auftreten muss, bevor eine Warnung ausgelöst wird. Außerdem kategorisieren Sie die Richtlinie und weisen ihr einen Schweregrad zu. Diese beiden Einstellungen helfen Ihnen beim Verwalten von Warnungsrichtlinien (und der Warnungen, die ausgelöst werden, wenn die Richtlinienbedingungen übereinstimmen), da Sie beim Verwalten von Richtlinien und Anzeigen von Warnungen im Security & Compliance Center nach diesen Einstellungen filtern können. Sie können z. B. Warnungen anzeigen, die den Bedingungen derselben Kategorie entsprechen, oder Warnungen mit demselben Schweregrad anzeigen.

Um Warnungsrichtlinien anzuzeigen und zu erstellen, wechseln Sie zu [https://protection.office.com](https://protection.office.com) Warnungsrichtlinien, und wählen Sie dann  \> **Warnungsrichtlinien** aus.

![Wählen Sie im Security and Compliance Center "Warnungen" und dann "Warnungsrichtlinien" aus, um Warnungsrichtlinien anzuzeigen und zu erstellen.](../media/09ebd451-8e84-44e1-aefc-63e70bba4d97.png)

Eine Warnungsrichtlinie besteht aus den folgenden Einstellungen und Bedingungen.

- **Aktivität, die von der Warnung nachverfolgt wird** – Sie erstellen eine Richtlinie zum Nachverfolgen einer Aktivität oder in einigen Fällen einige verwandte Aktivitäten, z. B. die Freigabe einer Datei für einen externen Benutzer, indem Sie sie freigeben, Zugriffsberechtigungen zuweisen oder einen anonymen Link erstellen. Wenn ein Benutzer die durch die Richtlinie definierte Aktivität ausführt, wird basierend auf den Einstellungen für den Warnungsschwellenwert eine Warnung ausgelöst.

    > [!NOTE]
    > Welche Aktivitäten Sie nachverfolgen können, hängt vom plan ihrer Organisation Office 365 Enterprise oder Office 365 US Government ab. Im Allgemeinen erfordern Aktivitäten im Zusammenhang mit Schadsoftwarekampagnen und Phishingangriffen ein E5/G5-Abonnement oder ein E1/F1/G1- oder E3/F3/G3-Abonnement mit einem [Defender for Office 365](../security/office-365-security/defender-for-office-365.md) Plan 2-Add-On-Abonnement.

- **Aktivitätsbedingungen** – Für die meisten Aktivitäten können Sie zusätzliche Bedingungen definieren, die erfüllt sein müssen, um eine Warnung auszulösen. Häufige Bedingungen sind IP-Adressen (damit eine Warnung ausgelöst wird, wenn der Benutzer die Aktivität auf einem Computer mit einer bestimmten IP-Adresse oder innerhalb eines IP-Adressbereichs ausführt), ob eine Warnung ausgelöst wird, wenn ein bestimmter Benutzer diese Aktivität ausführt, und ob die Aktivität unter einem bestimmten Dateinamen oder einer bestimmten URL ausgeführt wird. Sie können auch eine Bedingung konfigurieren, die eine Warnung auslöst, wenn die Aktivität von einem beliebigen Benutzer in Ihrer Organisation ausgeführt wird. Die verfügbaren Bedingungen sind von der ausgewählten Aktivität abhängig.

- **Wenn die Warnung ausgelöst wird–** Sie können eine Einstellung konfigurieren, die definiert, wie oft eine Aktivität auftreten kann, bevor eine Warnung ausgelöst wird. Auf diese Weise können Sie eine Richtlinie einrichten, um eine Warnung jedes Mal zu generieren, wenn eine Aktivität den Richtlinienbedingungen entspricht, wenn ein bestimmter Schwellenwert überschritten wird oder wenn das Auftreten der Aktivität, die die Warnung nachzeichnet, für Ihre Organisation ungewöhnlich wird.

    ![Konfigurieren, wie Warnungen ausgelöst werden, basierend auf dem Zeitpunkt der Aktivität, einem Schwellenwert oder einer ungewöhnlichen Aktivität für Ihre Organisation](../media/97ee1ed2-e7a9-47a2-a980-5f9f63872c65.png)

    Wenn Sie die Einstellung basierend auf ungewöhnlichen Aktivitäten auswählen, richtet Microsoft einen Basiswert ein, der die normale Häufigkeit für die ausgewählte Aktivität definiert. Es dauert bis zu sieben Tage, bis dieser Basisplan erstellt wird, während dem keine Warnungen generiert werden. Nachdem der Basisplan eingerichtet wurde, wird eine Warnung ausgelöst, wenn die Häufigkeit der aktivität, die von der Warnungsrichtlinie nachverfolgt wird, den Basiswert erheblich überschreitet. Für überwachungsbezogene Aktivitäten (z. B. Datei- und Ordneraktivitäten) können Sie eine Basislinie basierend auf einem einzelnen Benutzer oder basierend auf allen Benutzern in Ihrer Organisation einrichten. für Aktivitäten im Zusammenhang mit Schadsoftware können Sie eine Basislinie basierend auf einer einzelnen Schadsoftwarefamilie, einem einzelnen Empfänger oder allen Nachrichten in Ihrer Organisation einrichten.

    > [!NOTE]
    > Die Möglichkeit, Warnungsrichtlinien basierend auf einem Schwellenwert oder basierend auf ungewöhnlichen Aktivitäten zu konfigurieren, erfordert ein E5/G5-Abonnement oder ein E1/F1/G1- oder E3/F3/G3-Abonnement mit einem Microsoft Defender für Office 365 P2-, Microsoft 365 E5 Compliance- oder Microsoft 365 eDiscovery- und Überwachungs-Add-On-Abonnement. Organisationen mit einem E1/F1/G1- und E3/F3/G3-Abonnement können nur Warnungsrichtlinien erstellen, bei denen bei jedem Auftreten einer Aktivität eine Warnung ausgelöst wird.

- **Warnungskategorie** – Um die von einer Richtlinie generierten Warnungen nachzuverfolgen und zu verwalten, können Sie einer Richtlinie eine der folgenden Kategorien zuweisen.

  - Verhinderung von Datenverlust

  - Informationsgovernance

  - Nachrichtenübermittlung

  - Berechtigungen

  - Bedrohungsverwaltung

  - Sonstige

  Wenn eine Aktivität auftritt, die den Bedingungen der Warnungsrichtlinie entspricht, wird die generierte Warnung mit der in dieser Einstellung definierten Kategorie gekennzeichnet. This allows you to track and manage alerts that have the same category setting on the **View alerts** page in the security and compliance center because you can sort and filter alerts based on category.

- **Warnungsschweregrad** – Ähnlich wie bei der Warnungskategorie weisen Sie Warnungsrichtlinien ein Schweregradattribut (**Niedrig**, **Mittel**, **Hoch** oder **Information )** zu. Wenn eine Aktivität auftritt, die den Bedingungen der Warnungsrichtlinie entspricht, wird die generierte Warnung wie die Warnungskategorie mit demselben Schweregrad gekennzeichnet, der für die Warnungsrichtlinie festgelegt ist. Auch hier können Sie Warnungen mit dem gleichen Schweregrad auf der Seite **"Warnungen anzeigen"** nachverfolgen und verwalten. Sie können z. B. die Liste der Warnungen filtern, sodass nur Warnungen mit **hohem** Schweregrad angezeigt werden.

    > [!TIP]
    > Beim Einrichten einer Warnungsrichtlinie sollten Sie aktivitäten, die zu schwerwiegenden negativen Folgen führen können, einen höheren Schweregrad zuweisen, z. B. die Erkennung von Schadsoftware nach der Übermittlung an Benutzer, das Anzeigen vertraulicher oder klassifizierter Daten, das Teilen von Daten mit externen Benutzern oder andere Aktivitäten, die zu Datenverlusten oder Sicherheitsbedrohungen führen können. Dies kann Ihnen helfen, Warnungen und die Maßnahmen zu priorisieren, die Sie ergreifen, um die zugrunde liegenden Ursachen zu untersuchen und zu beheben.

- **E-Mail-Benachrichtigungen** – Sie können die Richtlinie so einrichten, dass E-Mail-Benachrichtigungen an eine Liste von Benutzern gesendet (oder nicht gesendet) werden, wenn eine Warnung ausgelöst wird. Sie können auch ein tägliches Benachrichtigungslimit festlegen, sodass nach Erreichen der maximalen Anzahl von Benachrichtigungen an diesem Tag keine weiteren Benachrichtigungen für die Warnung gesendet werden. Zusätzlich zu E-Mail-Benachrichtigungen können Sie oder andere Administratoren die Warnungen anzeigen, die durch eine Richtlinie auf der Seite **"Warnungen anzeigen"** ausgelöst werden. Erwägen Sie die Aktivierung von E-Mail-Benachrichtigungen für Warnungsrichtlinien einer bestimmten Kategorie oder mit einer Einstellung mit höherem Schweregrad.

## <a name="default-alert-policies"></a>Standardwarnungsrichtlinien

Microsoft bietet integrierte Warnungsrichtlinien, mit denen Exchange Missbrauch von Administratorberechtigungen, Schadsoftwareaktivitäten, potenziellen externen und internen Bedrohungen und Informationsgovernancerisiken identifiziert werden können. Auf der Seite **"Warnungsrichtlinien"** sind die Namen dieser integrierten Richtlinien fett formatiert, und der Richtlinientyp wird als **System** definiert. Diese Richtlinien sind standardmäßig aktiviert. Sie können diese Richtlinien deaktivieren (oder erneut aktivieren), eine Liste der Empfänger einrichten, an die E-Mail-Benachrichtigungen gesendet werden sollen, und ein tägliches Benachrichtigungslimit festlegen. Die anderen Einstellungen für diese Richtlinien können nicht bearbeitet werden.

In der folgenden Tabelle sind die verfügbaren Standardwarnungsrichtlinien und die Kategorie, der jede Richtlinie zugewiesen ist, aufgeführt und beschrieben. Die Kategorie wird verwendet, um zu bestimmen, welche Warnungen ein Benutzer auf der Seite "Warnungen anzeigen" anzeigen kann. Weitere Informationen finden Sie unter [RBAC-Berechtigungen, die zum Anzeigen von Warnungen erforderlich sind.](#rbac-permissions-required-to-view-alerts)

In der Tabelle sind auch die Office 365 Enterprise und Office 365 US Government-Pläne aufgeführt, die für jeden erforderlich sind. Einige Standardwarnungsrichtlinien sind verfügbar, wenn Ihre Organisation zusätzlich zu einem E1/F1/G1- oder E3/F3/G3-Abonnement über das entsprechende Add-On-Abonnement verfügt.

| Standardwarnungsrichtlinie | Beschreibung | Kategorie | Enterprise-Abonnement |
|:-----|:-----|:-----|:-----|
|**Ein potenziell schädlicher URL-Klick wurde erkannt.**|Generiert eine Warnung, wenn ein Benutzer, der durch [Safe Links](../security/office-365-security/safe-links.md) in Ihrer Organisation geschützt ist, auf einen bösartigen Link klickt. Dieses Ereignis wird ausgelöst, wenn Änderungen an der URL-Bewertung von Microsoft Defender für Office 365 identifiziert werden oder wenn Benutzer die Safe Links-Seiten außer Kraft setzen (basierend auf der Microsoft 365 for Business Safe Links-Richtlinie Ihrer Organisation). Diese Warnungsrichtlinie hat die Einstellung **"Hoher** Schweregrad". Für Defender für Office 365 P2-, E5-, G5-Kunden löst diese Warnung automatisch [eine automatisierte Untersuchung und Reaktion in Office 365](../security/office-365-security/office-365-air.md)aus. Weitere Informationen zu Ereignissen, die diese Warnung auslösen, finden Sie unter [Einrichten Safe Verknüpfungsrichtlinien.](../security/office-365-security/set-up-safe-links-policies.md)|Bedrohungsverwaltung|E5/G5 oder Defender für Office 365 P2-Add-On-Abonnement|
|**Ergebnis Administrator-Übermittlung abgeschlossen**|Generiert eine Warnung, wenn eine [Administratorübermittlung](../security/office-365-security/admin-submission.md) den erneuten Scan der übermittelten Entität abgeschlossen hat. Eine Warnung wird jedes Mal ausgelöst, wenn ein erneutes Scanergebnis aus einer Administratorübermittlung gerendert wird. Diese Warnungen sollen Sie daran erinnern, [die Ergebnisse vorheriger Übermittlungen](https://protection.office.com/reportsubmission)zu überprüfen, von Benutzern gemeldete Nachrichten zu übermitteln, um die neuesten Richtlinienüberprüfungen und Neuscanbewertungen zu erhalten, und Ihnen helfen, festzustellen, ob die Filterrichtlinien in Ihrer Organisation die beabsichtigten Auswirkungen haben. Diese Richtlinie weist eine Einstellung für den **Schweregrad "Information"** auf.|Bedrohungsverwaltung|E1/F1, E3/F3 oder E5|
|**Der Administrator hat eine manuelle Untersuchung von E-Mails ausgelöst**|Generiert eine Warnung, wenn ein Administrator die manuelle Untersuchung einer E-Mail aus dem Bedrohungs-Explorer auslöst. Weitere Informationen finden Sie unter [Beispiel: Ein Sicherheitsadministrator löst eine Untersuchung aus dem Bedrohungs-Explorer aus.](../security/office-365-security/automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer) Diese Warnung benachrichtigt Ihre Organisation, dass die Untersuchung gestartet wurde. Die Warnung enthält Informationen darüber, wer sie ausgelöst hat, und enthält einen Link zur Untersuchung. Diese Richtlinie weist eine Einstellung für den **Schweregrad "Information"** auf.|Bedrohungsverwaltung| E5/G5 oder Microsoft Defender für Office 365 P2-Add-On-Abonnement| 
|**Erstellung einer Weiterleitungs-/Umleitungsregel**|Generiert eine Warnung, wenn eine Person in Ihrer Organisation eine Posteingangsregel für ihr Postfach erstellt, die Nachrichten an ein anderes E-Mail-Konto weiterleitet oder umleitet. Diese Richtlinie verfolgt nur Posteingangsregeln nach, die mit Outlook im Web (früher als Outlook Web App bezeichnet) oder Exchange Online PowerShell erstellt werden. Diese Richtlinie weist eine Einstellung für den **Schweregrad "Information"** auf. Weitere Informationen zur Verwendung von Posteingangsregeln zum Weiterleiten und Umleiten von E-Mails in Outlook im Web finden Sie unter [Verwenden von Regeln in Outlook im Web, um Nachrichten automatisch an ein anderes Konto weiterzuleiten.](https://support.office.com/article/1433e3a0-7fb0-4999-b536-50e05cb67fed)|Bedrohungsverwaltung|E1/F1/G1, E3/F3/G3 oder E5/G5|
|**eDiscovery-Suche gestartet oder exportiert**|Generiert eine Warnung, wenn jemand das Tool für die Inhaltssuche im Security and Compliance Center verwendet. Eine Warnung wird ausgelöst, wenn die folgenden Inhaltssucheaktivitäten ausgeführt werden: <br/><br/>* Eine Inhaltssuche wird gestartet<br/>* Die Ergebnisse einer Inhaltssuche werden exportiert.<br/>* Ein Inhaltssuchbericht wird exportiert<br/><br/>Warnungen werden auch ausgelöst, wenn die vorherigen Inhaltssuche-Aktivitäten in Verbindung mit einem eDiscovery-Fall ausgeführt werden. Diese Richtlinie weist eine Einstellung für den **Schweregrad "Information"** auf. Weitere Informationen zu Inhaltssuchaktivitäten finden Sie unter [Suchen nach eDiscovery-Aktivitäten im Überwachungsprotokoll.](search-for-ediscovery-activities-in-the-audit-log.md#ediscovery-activities)|Bedrohungsverwaltung|E1/F1/G1, E3/F3/G3 oder E5/G5|
|**Erhöhung Exchange Administratorrechte**|Generiert eine Warnung, wenn jemand Administratorberechtigungen in Ihrer Exchange Online Organisation zugewiesen sind. Beispielsweise, wenn ein Benutzer der Rollengruppe "Organisationsverwaltung" in Exchange Online hinzugefügt wird. Diese Richtlinie hat die Einstellung **"Niedriger** Schweregrad".|Berechtigungen|E1/F1/G1, E3/F3/G3 oder E5/G5|
|**E-Mail-Nachrichten mit Schadsoftware wurden nach der Zustellung entfernt**|Generiert eine Warnung, wenn Nachrichten mit Schadsoftware an Postfächer in Ihrer Organisation übermittelt werden. Wenn dieses Ereignis auftritt, entfernt Microsoft die infizierten Nachrichten aus Exchange Online Postfächern mithilfe der [automatischen Bereinigung zur Nullstunde.](../security/office-365-security/zero-hour-auto-purge.md) Diese Richtlinie hat eine Einstellung für **den Schweregrad "Information"** und löst automatisch [eine automatisierte Untersuchung und Reaktion in Office 365](../security/office-365-security/office-365-air.md)aus.|Bedrohungsverwaltung|E5/G5 oder Microsoft Defender für Office 365 P2-Add-On-Abonnement|
|**E-Mail-Nachrichten mit Phishing-URLs wurden nach der Zustellung entfernt**|Generiert eine Warnung, wenn Nachrichten mit Phishing an Postfächer in Ihrer Organisation übermittelt werden. Wenn dieses Ereignis auftritt, entfernt Microsoft die infizierten Nachrichten aus Exchange Online Postfächern mithilfe der [automatischen Bereinigung zur Nullstunde.](../security/office-365-security/zero-hour-auto-purge.md) Diese Richtlinie hat eine Einstellung für **den Schweregrad "Information"** und löst automatisch [eine automatisierte Untersuchung und Reaktion in Office 365](../security/office-365-security/office-365-air.md)aus.|Bedrohungsverwaltung|E5/G5 oder Defender für Office 365 P2-Add-On-Abonnement|
|**Vom Benutzer als Schadsoftware oder Phishing-Mail gemeldete E-Mails**|Generiert eine Warnung, wenn Benutzer in Ihrer Organisation Nachrichten mithilfe des Add-Ins "Nachricht melden" als Phishing-E-Mail melden. Diese Richtlinie hat die Einstellung **"Niedriger** Schweregrad". Weitere Informationen zu diesem Add-In finden Sie unter [Verwenden des Add-Ins "Nachricht melden".](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2) Für Defender für Office 365 P2-, E5-, G5-Kunden löst diese Warnung automatisch [eine automatisierte Untersuchung und Reaktion in Office 365](../security/office-365-security/office-365-air.md)aus.|Bedrohungsverwaltung|E1/F1/G1, E3/F3/G3 oder E5/G5|
|**E-Mail-Sendegrenzwert überschritten**|Generiert eine Warnung, wenn eine Person in Ihrer Organisation mehr E-Mails gesendet hat, als gemäß der Richtlinie für ausgehende Spamnachrichten zulässig sind. Dies ist in der Regel ein Hinweis darauf, dass der Benutzer zu viele E-Mails sendet oder dass das Konto möglicherweise kompromittiert ist. Diese Richtlinie hat eine Einstellung **für den mittleren** Schweregrad. Wenn Sie eine Warnung erhalten, die von dieser Warnungsrichtlinie generiert wird, sollten Sie [überprüfen, ob das Benutzerkonto kompromittiert ist.](../security/office-365-security/responding-to-a-compromised-email-account.md)|Bedrohungsverwaltung|E1/F1/G1, E3/F3/G3 oder E5/G5|
|**Formular aufgrund eines potenziellen Phishingversuchs blockiert**|Generiert eine Warnung, wenn eine Person in Ihrer Organisation aufgrund eines erkannten wiederholten Phishingversuchs auf die Freigabe von Formularen und das Sammeln von Antworten mitHilfe von Microsoft Forms eingeschränkt wurde. Diese Richtlinie hat die Einstellung **"Hoher Schweregrad".**|Bedrohungsverwaltung|E1, E3/F3 oder E5|
|**Formular als Phishing gekennzeichnet und bestätigt**|Generiert eine Warnung, wenn ein in Microsoft Forms erstelltes Formular innerhalb Ihrer Organisation als potenzielles Phishing durch "Bericht missbraucht" erkannt und von Microsoft als Phishing bestätigt wurde. Diese Richtlinie hat die Einstellung **"Hoher** Schweregrad".|Bedrohungsverwaltung|E1, E3/F3 oder E5|
|**Nachrichten wurden verzögert**|Generiert eine Warnung, wenn Microsoft keine E-Mail-Nachrichten mithilfe eines Connectors an Ihre lokale Organisation oder einen Partnerserver übermitteln kann. In diesem Fall wird die Nachricht in Office 365 in die Warteschlange eingereiht. Diese Warnung wird ausgelöst, wenn mindestens 2.000 Nachrichten länger als eine Stunde in die Warteschlange gestellt wurden. Diese Richtlinie hat die Einstellung **"Hoher** Schweregrad".|Nachrichtenübermittlung|E1/F1/G1, E3/F3/G3 oder E5/G5|
|**Schadsoftwarekampagne nach der Zustellung erkannt**|Generiert eine Warnung, wenn ungewöhnlich viele Nachrichten mit Schadsoftware an Postfächer in Ihrer Organisation übermittelt werden. Wenn dieses Ereignis auftritt, entfernt Microsoft die infizierten Nachrichten aus Exchange Online Postfächern. Diese Richtlinie hat die Einstellung **"Hoher** Schweregrad".|Bedrohungsverwaltung|E5/G5 oder Microsoft Defender für Office 365 P2-Add-On-Abonnement|
|**Schadsoftwarekampagne erkannt und blockiert**|Generiert eine Warnung, wenn jemand versucht hat, eine ungewöhnlich große Anzahl von E-Mail-Nachrichten mit einer bestimmten Art von Schadsoftware an Benutzer in Ihrer Organisation zu senden. Wenn dieses Ereignis auftritt, werden die infizierten Nachrichten von Microsoft blockiert und nicht an Postfächer übermittelt. Diese Richtlinie hat die Einstellung **"Niedriger** Schweregrad".|Bedrohungsverwaltung|E5/G5 oder Defender für Office 365 P2-Add-On-Abonnement|
|**In SharePoint und OneDrive erkannte Schadsoftwarekampagne**|Generiert eine Warnung, wenn in Dateien, die sich auf SharePoint Websites oder in OneDrive Konten in Ihrer Organisation befinden, eine ungewöhnlich große Menge an Schadsoftware oder Viren erkannt wird. Diese Richtlinie hat die Einstellung **"Hoher** Schweregrad".|Bedrohungsverwaltung|E5/G5 oder Defender für Office 365 P2-Add-On-Abonnement|
|**Schadsoftware nicht angespippt, weil ZAP deaktiviert ist**| Generiert eine Warnung, wenn Microsoft die Zustellung einer Schadsoftwarenachricht an ein Postfach erkennt, da Zero-Hour automatische Bereinigung für Phishingnachrichten deaktiviert ist. Diese Richtlinie weist eine Einstellung für den **Schweregrad "Information"** auf. |Bedrohungsverwaltung|E5/G5 oder Defender für Office 365 P2-Add-On-Abonnement|
|**Zugestellte Phishingnachrichten, da der Junk-E-Mail-Ordner eines Benutzers deaktiviert ist**|Generiert eine Warnung, wenn Microsoft erkennt, dass der Junk-E-Mail-Ordner eines Benutzers deaktiviert ist, sodass eine Phishingnachricht mit hoher Vertrauenswürdigkeit an ein Postfach gesendet werden kann. Diese Richtlinie weist eine Einstellung für den **Schweregrad "Information"** auf.|Bedrohungsverwaltung|E5/G5 oder Defender für Office 365 P1- oder P2-Add-On-Abonnement|
|**Phish, der aufgrund einer ETR-Außerkraftsetzung bereitgestellt wird**|Generiert eine Warnung, wenn Microsoft eine Exchange Transport Rule (ETR) erkennt, die die Zustellung einer Phishingnachricht mit hoher Vertrauenswürdigkeit an ein Postfach ermöglicht. Diese Richtlinie weist eine Einstellung für den **Schweregrad "Information"** auf. Weitere Informationen zu Exchange Transportregeln (Nachrichtenflussregeln) finden Sie unter [Nachrichtenflussregeln (Transportregeln) in Exchange Online](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).|Bedrohungsverwaltung|E5/G5 oder Defender für Office 365 P1- oder P2-Add-On-Abonnement|
|**Aufgrund einer IP-Zulassungsrichtlinie übermittelte Phishing-Daten**|Generiert eine Warnung, wenn Microsoft eine IP-Zulassungsrichtlinie erkennt, die die Übermittlung einer Phishingnachricht mit hoher Vertrauenswürdigkeit an ein Postfach erlaubt. Diese Richtlinie weist eine Einstellung für den **Schweregrad "Information"** auf. Weitere Informationen zur IP-Zulassungsrichtlinie (Verbindungsfilterung) finden Sie unter [Konfigurieren der Standardverbindungsfilterrichtlinie – Office 365](../security/office-365-security/configure-the-connection-filter-policy.md).|Bedrohungsverwaltung|E5/G5 oder Defender für Office 365 P1- oder P2-Add-On-Abonnement|
|**Phishing nicht abgespippt, da ZAP deaktiviert ist**| Generiert eine Warnung, wenn Microsoft die Zustellung einer Phishingnachricht mit hoher Vertrauenswürdigkeit an ein Postfach erkennt, da Zero-Hour automatische Bereinigung für Phishingnachrichten deaktiviert ist. Diese Richtlinie weist eine Einstellung für den **Schweregrad "Information"** auf.|Bedrohungsverwaltung|E5/G5 oder Defender für Office 365 P2-Add-On-Abonnement|
|**Phishing-Phishing aufgrund von Mandanten- oder Benutzerüberschreibung**<sup>1</sup>|Generiert eine Warnung, wenn Microsoft erkennt, dass eine Administrator- oder Benutzerüberschreibung die Zustellung einer Phishingnachricht an ein Postfach zugelassen hat. Beispiele für Außerkraftsetzungen sind eine Posteingangs- oder Nachrichtenflussregel, die Nachrichten von einem bestimmten Absender oder einer Bestimmten Domäne zulässt, oder eine Antispamrichtlinie, die Nachrichten von bestimmten Absendern oder Domänen zulässt. Diese Richtlinie hat die Einstellung **"Hoher** Schweregrad".|Bedrohungsverwaltung|E5/G5 oder Defender für Office 365 P2-Add-On-Abonnement|
|**Verdächtige E-Mail-Weiterleitunsaktivitäten**|Generiert eine Warnung, wenn jemand in Ihrer Organisation automatisch E-Mails an ein verdächtiges externes Konto gesendet hat. Dies ist eine frühe Warnung für Verhalten, das darauf hindeuten kann, dass das Konto kompromittiert ist, aber nicht schwerwiegend genug, um den Benutzer einzuschränken. Diese Richtlinie hat die Einstellung **"Hoher** Schweregrad". Obwohl dies selten ist, kann eine von dieser Richtlinie generierte Warnung eine Anomalie sein. Es empfiehlt sich zu [überprüfen, ob das Benutzerkonto kompromittiert ist.](../security/office-365-security/responding-to-a-compromised-email-account.md)|Bedrohungsverwaltung|E1/F1/G1, E3/F3/G3 oder E5/G5|
|**Verdächtige E-Mail-Sendemuster erkannt**|Generiert eine Warnung, wenn jemand in Ihrer Organisation verdächtige E-Mails gesendet hat und das Risiko besteht, dass das Senden von E-Mails eingeschränkt wird. Dies ist eine frühe Warnung für Verhaltensweisen, die möglicherweise darauf hindeuten, dass das Konto kompromittiert ist, aber nicht schwerwiegend genug ist, um den Benutzer einzuschränken. Diese Richtlinie hat eine Einstellung **für den mittleren** Schweregrad. Obwohl dies selten ist, kann eine von dieser Richtlinie generierte Warnung eine Anomalie sein. Es empfiehlt sich jedoch zu [überprüfen, ob das Benutzerkonto kompromittiert ist.](../security/office-365-security/responding-to-a-compromised-email-account.md)|Bedrohungsverwaltung|E1/F1/G1, E3/F3/G3 oder E5/G5  |
|**Mandant kann keine E-Mails senden**|Generiert eine Warnung, wenn der großteil des E-Mail-Datenverkehrs aus Ihrer Organisation als verdächtig erkannt wurde und Microsoft Ihre Organisation am Senden von E-Mails gehindert hat. Untersuchen Sie potenziell kompromittierte Benutzer- und Administratorkonten, neue Connectors oder offene Relays, und wenden Sie sich dann an den Microsoft-Support, um die Blockierung Ihrer Organisation aufzuheben. Diese Richtlinie hat die Einstellung **"Hoher** Schweregrad". Weitere Informationen dazu, warum Organisationen blockiert werden, finden Sie unter Beheben von Problemen bei der [E-Mail-Zustellung für Fehlercode 5.7.7xx in Exchange Online](/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/fix-error-code-5-7-700-through-5-7-750).|Bedrohungsverwaltung|E1/F1/G1, E3/F3/G3 oder E5/G5|
|**Ungewöhnliche Externe Benutzerdateiaktivität**|Generiert eine Warnung, wenn ungewöhnlich viele Aktivitäten für Dateien in SharePoint oder OneDrive von Benutzern außerhalb Ihrer Organisation ausgeführt werden. Dies umfasst Aktivitäten wie den Zugriff auf Dateien, das Herunterladen von Dateien und das Löschen von Dateien. Diese Richtlinie hat die Einstellung **"Hoher** Schweregrad".|Informationsgovernance|E5/G5, Microsoft Defender für Office 365 P2 oder Microsoft 365 E5-Add-On-Abonnement|
|**Ungewöhnliches Volumen der externen Dateifreigabe**|Generiert eine Warnung, wenn ungewöhnlich viele Dateien in SharePoint oder OneDrive für Benutzer außerhalb Ihrer Organisation freigegeben werden. Diese Richtlinie hat eine Einstellung **für den mittleren** Schweregrad.|Informationsgovernance|E5/G5, Defender für Office 365 P2 oder Microsoft 365 E5-Add-On-Abonnement|
|**Ungewöhnliches Volumen des Löschens von Dateien**|Generiert eine Warnung, wenn ungewöhnlich viele Dateien innerhalb eines kurzen Zeitraums in SharePoint oder OneDrive gelöscht werden. Diese Richtlinie hat eine Einstellung **für den mittleren** Schweregrad.|Informationsgovernance|E5/G5, Defender für Office 365 P2 oder Microsoft 365 E5-Add-On-Abonnement|
|**Ungewöhnliche Zunahme von E-Mails, die als Phishing-Mails gemeldet wurden**|Generiert eine Warnung, wenn die Anzahl der Personen in Ihrer Organisation, die das Add-In "Nachricht melden" in Outlook zum Melden von Nachrichten als Phishing-E-Mail verwenden, erheblich zunimmt. Diese Richtlinie hat eine Einstellung **für den mittleren** Schweregrad. Weitere Informationen zu diesem Add-In finden Sie unter [Verwenden des Add-Ins "Nachricht melden".](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)|Bedrohungsverwaltung|E5/G5 oder Defender für Office 365 P2-Add-On-Abonnement|
|**Benutzeridentitätsphishing, übermittelt an Posteingang/Ordner**<sup>1,</sup><sup>2</sup>|Generiert eine Warnung, wenn Microsoft erkennt, dass eine Administrator- oder Benutzerüberschreibung die Zustellung einer Phishingnachricht mit Benutzeridentitätswechsel an den Posteingang (oder einen anderen ordner, auf den der Benutzer zugreifen kann) eines Postfachs zugelassen hat. Beispiele für Außerkraftsetzungen sind eine Posteingangs- oder Nachrichtenflussregel, die Nachrichten von einem bestimmten Absender oder einer Bestimmten Domäne zulässt, oder eine Antispamrichtlinie, die Nachrichten von bestimmten Absendern oder Domänen zulässt. Diese Richtlinie hat eine Einstellung **für den mittleren** Schweregrad.|Bedrohungsverwaltung|E5/G5 oder Defender für Office 365 P2-Add-On-Abonnement|
|**Benutzer, der das Senden von E-Mails eingeschränkt hat**|Generiert eine Warnung, wenn eine Person in Ihrer Organisation auf das Senden ausgehender E-Mails beschränkt ist. Dies führt in der Regel dazu, dass ein Konto kompromittiert wird und der Benutzer auf der Seite **"Eingeschränkte Benutzer"** im Security & Compliance Center aufgeführt wird. (To access this page, go to **Threat Management > Review > Restricted Users**). Diese Richtlinie hat die Einstellung **"Hoher** Schweregrad". Weitere Informationen zu eingeschränkten Benutzern finden Sie unter [Entfernen eines Benutzers, einer Domäne oder einer IP-Adresse aus einer Sperrliste nach dem Senden von Spam-E-Mails.](/office365/securitycompliance/removing-user-from-restricted-users-portal-after-spam)|Bedrohungsverwaltung|E1/F1/G1, E3/F3/G3 oder E5/G5|
|**Benutzer, die die Freigabe von Formularen und das Sammeln von Antworten eingeschränkt haben**|Generiert eine Warnung, wenn eine Person in Ihrer Organisation aufgrund eines erkannten wiederholten Phishingversuchs auf die Freigabe von Formularen und das Sammeln von Antworten mitHilfe von Microsoft Forms eingeschränkt wurde. Diese Richtlinie hat die Einstellung **"Hoher** Schweregrad".|Bedrohungsverwaltung|E1, E3/F3 oder E5|
|||||

> [!NOTE]
> <sup>1</sup> Wir haben diese Standardmäßige Warnungsrichtlinie aufgrund des Kundenfeedbacks vorübergehend entfernt. Wir arbeiten daran, es zu verbessern, und werden es in Kürze durch eine neue Version ersetzen. Bis dahin können Sie eine benutzerdefinierte Warnungsrichtlinie erstellen, um diese Funktionalität mithilfe der folgenden Einstellungen zu ersetzen:<br/>&nbsp; * Aktivität ist Phishing-E-Mail, die zum Zeitpunkt der Zustellung erkannt wurde<br/>&nbsp; * E-Mail ist nicht ZAP'd<br/>&nbsp; * E-Mail-Richtung ist eingehend<br/>&nbsp; * E-Mail-Zustellungsstatus wird zugestellt<br/>&nbsp; * Erkennungstechnologie ist bösartige URL-Aufbewahrung, URL-Detonation, Erweiterter Phishingfilter, Allgemeiner Phishingfilter, Domänenidentitätswechsel, Benutzeridentitätswechsel und Markenidentitätswechsel<br/><br/>&nbsp;&nbsp;&nbsp;Weitere Informationen zum Antiphishing in Office 365 finden Sie unter ["Einrichten von Antiphishing- und Antiphishingrichtlinien".](../security/office-365-security/set-up-anti-phishing-policies.md)<br/><br/><sup>2</sup> Um diese Warnungsrichtlinie neu zu erstellen, folgen Sie den Anweisungen in der vorherigen Fußnote, wählen Sie jedoch den Identitätswechsel des Benutzers als einzige Erkennungstechnologie aus.

Die ungewöhnliche Aktivität, die von einigen der integrierten Richtlinien überwacht wird, basiert auf demselben Prozess wie die zuvor beschriebene Einstellung des Warnungsschwellenwerts. Microsoft richtet einen Basiswert ein, der die normale Häufigkeit für "normale" Aktivitäten definiert. Warnungen werden dann ausgelöst, wenn die Häufigkeit von Aktivitäten, die von der integrierten Warnungsrichtlinie nachverfolgt werden, den Basiswert erheblich überschreitet.

## <a name="viewing-alerts"></a>Anzeigen von Warnungen

Wenn eine von Benutzern in Ihrer Organisation ausgeführte Aktivität den Einstellungen einer Warnungsrichtlinie entspricht, wird eine Warnung generiert und auf der Seite **"Warnungen anzeigen"** im Security and Compliance Center angezeigt. Abhängig von den Einstellungen einer Warnungsrichtlinie wird auch eine E-Mail-Benachrichtigung an eine Liste der angegebenen Benutzer gesendet, wenn eine Warnung ausgelöst wird. Für jede Warnung zeigt das Dashboard auf der Seite **"Warnungen anzeigen"** den Namen der entsprechenden Warnungsrichtlinie, den Schweregrad und die Kategorie für die Warnung (definiert in der Warnungsrichtlinie) sowie die Häufigkeit an, mit der eine Aktivität aufgetreten ist, die zur Generierung der Warnung geführt hat. Dieser Wert basiert auf der Schwellenwerteinstellung der Warnungsrichtlinie. Das Dashboard zeigt auch den Status für jede Warnung an. Weitere Informationen zur Verwendung der Statuseigenschaft zum Verwalten von Warnungen finden Sie unter [Verwalten von Warnungen.](#managing-alerts)

Um Warnungen anzuzeigen, wechseln Sie zu [https://protection.office.com](https://protection.office.com) **Warnungen,** und wählen Sie dann \> **Warnungen anzeigen** aus.

![Wählen Sie in "Sicherheit und Compliance" die Option "Warnungen" und dann "Warnungen anzeigen" aus, um Warnungen anzuzeigen.](../media/ec5ea59b-bf61-459f-8b65-970ab4bb8bcc.png)

Sie können die folgenden Filter verwenden, um eine Teilmenge aller Warnungen auf der Seite **"Warnungen anzeigen"** anzuzeigen.

- **Status.** Verwenden Sie diesen Filter, um Warnungen anzuzeigen, denen ein bestimmter Status zugewiesen ist. Der Standardstatus ist **Aktiv**. Sie oder andere Administratoren können den Statuswert ändern.

- **Politik.** Verwenden Sie diesen Filter, um Warnungen anzuzeigen, die der Einstellung einer oder mehrerer Warnungsrichtlinien entsprechen. Sie können auch alle Warnungen für alle Warnungsrichtlinien anzeigen.

- **Zeitbereich.** Verwenden Sie diesen Filter, um Warnungen anzuzeigen, die innerhalb eines bestimmten Datums- und Uhrzeitbereichs generiert wurden.

- **Schweregrad.** Verwenden Sie diesen Filter, um Warnungen anzuzeigen, denen ein bestimmter Schweregrad zugewiesen ist.

- **Kategorie.** Verwenden Sie diesen Filter, um Warnungen aus einer oder mehreren Warnungskategorien anzuzeigen.

- **Schilder.** Verwenden Sie diesen Filter, um Warnungen von einem oder mehreren Benutzertags anzuzeigen. Tags werden basierend auf markierten Postfächern oder Benutzern, die in den Warnungen angezeigt werden, wiedergegeben. Weitere Informationen finden Sie [unter Benutzertags in Office 356 ATP.](../security/office-365-security/user-tags.md)

- **Quelle.** Verwenden Sie diesen Filter, um Warnungen anzuzeigen, die durch Warnungsrichtlinien im Security and Compliance Center oder durch Office 365 Cloud App Security Richtlinien ausgelöste Warnungen oder beides ausgelöst werden. Weitere Informationen zu Office 365 Cloud App Security Warnungen finden Sie unter [Anzeigen Cloud App Security Warnungen.](#viewing-cloud-app-security-alerts)

> [!IMPORTANT]
> Das Filtern und Sortieren nach Benutzertags befindet sich derzeit in der öffentlichen Vorschau.
> Sie kann vor der kommerziellen Veröffentlichung erheblich geändert werden. Microsoft übernimmt keine Garantie, weder ausdrücklich noch konkludent, in Bezug auf die bereitgestellten Informationen.

## <a name="alert-aggregation"></a>Warnungsaggregation

Wenn mehrere Ereignisse, die den Bedingungen einer Warnungsrichtlinie entsprechen, innerhalb eines kurzen Zeitraums auftreten, werden sie einer vorhandenen Warnung durch einen Prozess namens *Warnungsaggregation* hinzugefügt. Wenn ein Ereignis eine Warnung auslöst, wird die Warnung generiert und auf der Seite **"Warnungen anzeigen"** angezeigt, und es wird eine Benachrichtigung gesendet. Wenn dasselbe Ereignis innerhalb des Aggregationsintervalls auftritt, fügt Microsoft 365 der vorhandenen Warnung Details zum neuen Ereignis hinzu, anstatt eine neue Warnung auszulösen. Das Ziel der Warnungsaggregation besteht darin, die Warnungs-"Ermüdung" zu reduzieren und Ihnen zu ermöglichen, sich auf weniger Warnungen für dasselbe Ereignis zu konzentrieren und maßnahmen zu ergreifen.

Die Länge des Aggregationsintervalls hängt von Ihrem Office 365 oder Microsoft 365 Abonnement ab.

|Abonnement|Aggregationsintervall|
|:---------|:---------:|
|Office 365 oder Microsoft 365 E5/G5|1 Minute|
|Microsoft Defender für Office 365 Plan 2 |1 Minute|
|E5 Compliance-Add-On oder E5 Discovery- und Audit-Add-On|1 Minute|
|Office 365 oder Microsoft 365 E1/F1/G1 oder E3/F3/G3|15 Minuten|
|Defender für Office 365 Plan 1 oder Exchange Online Protection|15 Minuten|
|||

Wenn Ereignisse, die mit derselben Warnungsrichtlinie übereinstimmen, innerhalb des Aggregationsintervalls auftreten, werden der ursprünglichen Warnung Details zu dem nachfolgenden Ereignis hinzugefügt. Für alle Ereignisse werden Informationen zu aggregierten Ereignissen im Detailfeld angezeigt, und die Häufigkeit, mit der ein Ereignis mit dem Aggregationsintervall aufgetreten ist, wird im Feld "Aktivitäts-/Trefferanzahl" angezeigt. Sie können weitere Informationen zu allen aggregierten Ereignisinstanzen anzeigen, indem Sie die Aktivitätsliste anzeigen.

Der folgende Screenshot zeigt eine Warnung mit vier aggregierten Ereignissen. Die Aktivitätsliste enthält Informationen zu den vier E-Mail-Nachrichten, die für die Warnung relevant sind.

![Beispiel für die Aggregation von Warnungen](../media/AggregatedAlertExample.png)

Beachten Sie bei der Aggregation von Warnungen die folgenden Punkte:

- Warnungen, die durch den **Klick auf eine potenziell schädliche URL** ausgelöst wurden, wurden als [Standardwarnungsrichtlinie](#default-alert-policies) erkannt und werden nicht aggregiert. Dies liegt daran, dass durch diese Richtlinie ausgelöste Warnungen für jeden Benutzer und jede E-Mail-Nachricht eindeutig sind.

- Zu diesem Zeitpunkt gibt die Warnungseigenschaft **"Trefferanzahl"** nicht die Anzahl der aggregierten Ereignisse für alle Warnungsrichtlinien an. Für Warnungen, die durch diese Warnungsrichtlinien ausgelöst werden, können Sie die aggregierten Ereignisse anzeigen, indem Sie auf **"Nachrichtenliste anzeigen"** oder **"Aktivität anzeigen"** in der Warnung klicken. Wir arbeiten daran, die Anzahl der aggregierten Ereignisse, die in der Warnungseigenschaft **"Trefferanzahl"** aufgelistet sind, für alle Warnungsrichtlinien verfügbar zu machen.

## <a name="rbac-permissions-required-to-view-alerts"></a>Zum Anzeigen von Warnungen erforderliche RBAC-Berechtigungen

Die Rollenbasierte Zugriffssteuerungsberechtigungen (Role Based Access Control, RBAC), die Benutzern in Ihrer Organisation zugewiesen sind, bestimmen, welche Warnungen einem Benutzer auf der Seite **"Warnungen anzeigen"** angezeigt werden. Wie wird dies erreicht? Die Verwaltungsrollen, die Benutzern zugewiesen sind (basierend auf ihrer Mitgliedschaft in Rollengruppen im Security & Compliance Center), bestimmen, welche Warnungskategorien ein Benutzer auf der Seite **"Warnungen anzeigen"** sehen kann. Im Folgenden finden Sie einige Beispiele:

- Mitglieder der Rollengruppe "Datensatzverwaltung" können nur die Warnungen anzeigen, die von Warnungsrichtlinien generiert werden, denen die Kategorie **"Informationsgovernance"** zugewiesen ist.

- Mitglieder der Rollengruppe "Complianceadministrator" können keine Warnungen anzeigen, die von Warnungsrichtlinien generiert werden, denen die Kategorie **"Bedrohungsverwaltung"** zugewiesen ist.

- Mitglieder der Rollengruppe "eDiscovery-Manager" können keine Warnungen anzeigen, da keine der zugewiesenen Rollen die Berechtigung zum Anzeigen von Warnungen aus einer Warnungskategorie bereitstellt.

Mit diesem Design (basierend auf RBAC-Berechtigungen) können Sie bestimmen, welche Warnungen von Benutzern in bestimmten Rollen in Ihrer Organisation angezeigt (und verwaltet) werden können.

In der folgenden Tabelle sind die Rollen aufgeführt, die zum Anzeigen von Warnungen aus den sechs verschiedenen Warnungskategorien erforderlich sind. In der ersten Spalte der Tabellen sind alle Rollen im Security & Compliance Center aufgeführt.  Ein Häkchen gibt an, dass ein Benutzer, dem diese Rolle zugewiesen ist, Warnungen aus der entsprechenden Warnungskategorie anzeigen kann, die in der obersten Zeile aufgeführt ist.

Informationen dazu, welcher Kategorie eine Standardwarnungsrichtlinie zugewiesen ist, finden Sie in der Tabelle in den [Standardwarnungsrichtlinien.](#default-alert-policies)

|Rolle|Informationsgovernance|Verhinderung von Datenverlust|Nachrichtenübermittlung|Berechtigungen|Bedrohungsverwaltung|Sonstige|
|:---------|:---------:|:---------:|:---------:|:---------:|:---------:|:---------:|
|Überwachungsprotokolle|||||||
|Fallverwaltung|||||||
|Complianceadministrator|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||![Häkchen](../media/checkmark.png)||![Häkchen](../media/checkmark.png)|
|Compliance-Suche|||||||
|Geräteverwaltung|||||||
|Dispositionsverwaltung|||||||
|DLP-Complianceverwaltung||![Häkchen](../media/checkmark.png)|||||
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
|Service Assurance-Ansicht|||||||
|Administrator der Aufsichtsüberprüfung|||||||
|Überwachungsprotokolle nur anzeigen|||||||
|View-Only Geräteverwaltung|||||||
|View-Only DLP Compliance Management||![Häkchen](../media/checkmark.png)|||||
|View-Only Verwalten von Warnungen||||||![Häkchen](../media/checkmark.png)|
|Schreibgeschützte Empfänger|||![Häkchen](../media/checkmark.png)||||
|View-Only Datensatzverwaltung|![Häkchen](../media/checkmark.png)||||||
|View-Only-Aufbewahrungsverwaltung|![Häkchen](../media/checkmark.png)||||||
|||||||

> [!TIP]
> Um die Rollen anzuzeigen, die den einzelnen Standardrollengruppen zugewiesen sind, führen Sie die folgenden Befehle in Security & Compliance Center PowerShell aus:
> 
> ```powershell
> $RoleGroups = Get-RoleGroup
> ```
> 
> ```powershell
> $RoleGroups | foreach {Write-Output -InputObject `r`n,$_.Name,"-----------------------"; Get-RoleGroup $_.Identity | Select-Object -ExpandProperty Roles}
> ```
> 
> Sie können auch die Rollen anzeigen, die einer Rollengruppe im Security & Compliance Center zugewiesen sind. Wechseln Sie zur Seite **"Berechtigungen",** und wählen Sie eine Rollengruppe aus. Die zugewiesenen Rollen werden auf der Flyoutseite aufgelistet.

## <a name="managing-alerts"></a>Verwalten von Warnungen

Nachdem Warnungen generiert und auf der Seite **"Warnungen anzeigen"** im Security and Compliance Center angezeigt wurden, können Sie sie selektieren, untersuchen und beheben. Hier sind einige Aufgaben, die Sie zum Verwalten von Warnungen ausführen können.

- **Weisen Sie Warnungen einen Status zu.** Sie können Warnungen einen der folgenden Status zuweisen: **Aktiv** (Standardwert), **Investigating**, **Resolved** oder **Dismissed**. Anschließend können Sie nach dieser Einstellung filtern, um Warnungen mit derselben Statuseinstellung anzuzeigen. Mit dieser Statuseinstellung kann der Prozess der Verwaltung von Warnungen nachverfolgt werden.

- **Anzeigen von Warnungsdetails.** Sie können eine Warnung auswählen, um eine Flyoutseite mit Details zur Warnung anzuzeigen. Die detaillierten Informationen hängen von der entsprechenden Warnungsrichtlinie ab, umfassen jedoch in der Regel Folgendes:

  - Der Name des tatsächlichen Vorgangs, der die Warnung ausgelöst hat, z. B. ein Cmdlet oder ein Überwachungsprotokollvorgang.

  - Eine Beschreibung der Aktivität, die die Warnung ausgelöst hat.

  - Der Benutzer (oder die Liste der Benutzer), der die Warnung ausgelöst hat. Dies gilt nur für Warnungsrichtlinien, die so eingerichtet sind, dass ein einzelner Benutzer oder eine einzelne Aktivität nachverfolgt wird.

  - Gibt an, wie oft die von der Warnung nachverfolgte Aktivität ausgeführt wurde. Diese Anzahl stimmt möglicherweise nicht mit der tatsächlichen Anzahl verwandter Warnungen überein, die auf der Seite "Warnungen anzeigen" aufgeführt sind, da möglicherweise mehr Warnungen ausgelöst wurden.

  - Ein Link zu einer Aktivitätsliste, die ein Element für jede Aktivität enthält, die ausgeführt wurde, die die Warnung ausgelöst hat. Jeder Eintrag in dieser Liste gibt an, wann die Aktivität aufgetreten ist, den Namen des tatsächlichen Vorgangs (z. B. "FileDeleted"), den Benutzer, der die Aktivität ausgeführt hat, das Objekt (z. B. eine Datei, einen eDiscovery-Fall oder ein Postfach), für den die Aktivität ausgeführt wurde, und die IP-Adresse des Computers des Benutzers. Bei Benachrichtigungen im Zusammenhang mit Schadsoftware verweist dies auf eine Nachrichtenliste.

  - Der Name (und Link) der entsprechenden Warnungsrichtlinie.

- **E-Mail-Benachrichtigungen unterdrücken.** Sie können E-Mail-Benachrichtigungen auf der Flyoutseite für eine Warnung deaktivieren (oder unterdrücken). Wenn Sie E-Mail-Benachrichtigungen unterdrücken, sendet Microsoft keine Benachrichtigungen, wenn Aktivitäten oder Ereignisse den Bedingungen der Warnungsrichtlinie entsprechen. Warnungen werden jedoch ausgelöst, wenn von Benutzern ausgeführte Aktivitäten den Bedingungen der Warnungsrichtlinie entsprechen. Sie können E-Mail-Benachrichtigungen auch deaktivieren, indem Sie die Warnungsrichtlinie bearbeiten.

- **Auflösen von Warnungen.** Sie können eine Warnung auf der Flyoutseite für eine Warnung als aufgelöst markieren (wodurch der Status der Warnung auf **"Gelöst"** festgelegt wird). Wenn Sie den Filter nicht ändern, werden aufgelöste Warnungen nicht auf der Seite **"Warnungen anzeigen"** angezeigt.

## <a name="viewing-cloud-app-security-alerts"></a>Anzeigen von Cloud App Security-Warnungen

Warnungen, die von Office 365 Cloud App Security-Richtlinien ausgelöst werden, werden jetzt auf der Seite **"Warnungen anzeigen"** im Security and Compliance Center angezeigt. Dazu gehören Warnungen, die durch Aktivitätsrichtlinien ausgelöst werden, und Warnungen, die durch Anomalieerkennungsrichtlinien in Office 365 Cloud App Security ausgelöst werden. Dies bedeutet, dass Sie alle Warnungen im Security & Compliance Center anzeigen können. Office 365 Cloud App Security ist nur für Organisationen mit einem Office 365 Enterprise E5- oder Office 365 US Government G5-Abonnement verfügbar. Weitere Informationen finden Sie unter ["Übersicht über Cloud App Security".](/cloud-app-security/what-is-cloud-app-security)

Organisationen, die Microsoft Cloud App Security als Teil eines Enterprise Mobility + Security E5-Abonnements oder als eigenständiger Dienst haben, können auch Cloud App Security-Warnungen im Zusammenhang mit Office 365-Apps und -Diensten im Security & Compliance Center anzeigen.

Um nur Cloud App Security-Warnungen im Security and Compliance Center anzuzeigen, verwenden Sie den **Quellfilter,** und wählen Sie **Cloud App Security** aus.

![Verwenden des Quellfilters, um nur Cloud App Security-Warnungen anzuzeigen](../media/FilterCASAlerts.png)

Ähnlich wie bei einer Warnung, die durch eine Warnungsrichtlinie im Security and Compliance Center ausgelöst wird, können Sie eine Cloud App Security-Warnung auswählen, um eine Flyoutseite mit Details zur Warnung anzuzeigen. Die Warnung enthält einen Link zum Anzeigen der Details und zum Verwalten der Warnung im Cloud App Security-Portal sowie einen Link zur entsprechenden Cloud App Security-Richtlinie, die die Warnung ausgelöst hat. Siehe ["Überwachen von Warnungen in Cloud App Security".](/cloud-app-security/monitor-alerts)

![Warnungsdetails enthalten Links zum Cloud App Security-Portal](../media/CASAlertDetail.png)

> [!IMPORTANT]
> Wenn Sie den Status einer Cloud App Security-Warnung im Security and Compliance Center ändern, wird der Auflösungsstatus für dieselbe Warnung im Cloud App Security-Portal nicht aktualisiert. For example, if you mark the status of the alert as **Resolved** in the security and compliance center, the status of the alert in the Cloud App Security portal is unchanged. Um eine Cloud App Security-Warnung aufzulösen oder zu schließen, verwalten Sie die Warnung im Cloud App Security-Portal.
