---
title: Warnungsrichtlinien im Security and Compliance Center
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: conceptual
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
ms.openlocfilehash: 9f05fe464b4945d739c5920282e45e07f9fcb344
ms.sourcegitcommit: 0f48beaca3afa4df12d41847014975d50a4ebe7d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/02/2020
ms.locfileid: "48338428"
---
# <a name="alert-policies-in-the-security-and-compliance-center"></a>Warnungsrichtlinien im Security & Compliance Center

Sie können die Warnungsrichtlinien-und Benachrichtigungs-Dashboard-Tools im Microsoft 365 Security and Compliance Center verwenden, um Warnungsrichtlinien zu erstellen und dann die Warnungen anzuzeigen, die generiert werden, wenn Benutzeraktivitäten ausführen, die den Bedingungen einer Warnungs Richtlinie entsprechen. Es gibt verschiedene Standard Warnungsrichtlinien, mit denen Sie Aktivitäten wie das Zuweisen von Administratorrechten in Exchange Online, Malwareangriffe, Phishing-Kampagnen und ungewöhnliche Ebenen von Dateilöschungen und externer Freigabe überwachen können.

Mithilfe von Warnungsrichtlinien können Sie die Warnungen kategorisieren, die von einer Richtlinie ausgelöst werden, die Richtlinie auf alle Benutzer in Ihrer Organisation anwenden, für den Zeitpunkt, zu dem eine Warnung ausgelöst wird, eine Schwellenwertstufe festlegen und entscheiden, ob e-Mail-Benachrichtigungen beim Auslösen von Warnungen empfangen werden sollen. Es gibt auch eine Seite **Benachrichtigungen anzeigen** im Security and Compliance Center, in der Sie Warnungen anzeigen und Filtern, einen Warnungsstatus festlegen können, der Ihnen bei der Verwaltung von Warnungen hilft, und dann Warnungen nach dem angesprochenen oder behobenen Vorfall ignorieren.

> [!NOTE]
> Warnungsrichtlinien sind für Organisationen mit einem Microsoft 365 Enterprise-, Office 365 Enterprise-oder Office 365 US Government E1/F1/G1, E3/G3 oder E5/G5-Abonnement verfügbar. Erweiterte Funktionen sind nur für Organisationen mit einem E5/G5-Abonnement oder für Organisationen mit einem E1/F1/G1-oder E3/G3-Abonnement und einem Office 365 Advanced Threat Protection (ATP) P2 oder Microsoft 365 E5 Compliance oder Microsoft 365 E5 eDiscovery und Audit Add-on-Abonnement verfügbar. Die Funktionalität, die ein E5/G5-oder Add-on-Abonnement erfordert, ist in diesem Thema hervorgehoben. Beachten Sie außerdem, dass Warnungsrichtlinien in den US-Regierungs Umgebungen Office 365 gcc, gcc High und DoD verfügbar sind.

## <a name="how-alert-policies-work"></a>Funktionsweise von Warnungsrichtlinien

Im folgenden finden Sie einen kurzen Überblick über die Funktionsweise von Warnungsrichtlinien und die Warnungen, die ausgelöst werden, wenn Benutzer-oder Administratoraktivitäten mit den Bedingungen einer Warnungs Richtlinie übereinstimmen.

![Übersicht über die Funktionsweise von Warnungsrichtlinien](../media/e02a622d-b429-448b-8107-dd1a4770b4e0.png)

1. Ein Administrator in Ihrer Organisation erstellt, konfiguriert und aktiviert eine Warnungs Richtlinie mithilfe der Seite " **Warnungsrichtlinien** " im Security and Compliance Center. Sie können auch Warnungsrichtlinien erstellen, indem Sie das **New-protectionalert können-** Cmdlet in Security & Compliance Center PowerShell verwenden. Zum Erstellen von Warnungsrichtlinien müssen Sie im Security and Compliance Center die Rolle "Warnungen verwalten" oder "Organisationskonfiguration" zugewiesen haben.

   > [!NOTE]
   > Es dauert bis zu 24 Stunden nach dem Erstellen oder Aktualisieren einer Warnungs Richtlinie, bevor Warnungen von der Richtlinie ausgelöst werden können. Dies liegt daran, dass die Richtlinie mit dem Warnungs Erkennungsmodul synchronisiert werden muss.

2. Ein Benutzer führt eine Aktivität aus, die mit den Bedingungen einer Warnungs Richtlinie übereinstimmt. Im Fall von Malwareangriffen lösen infizierte e-Mail-Nachrichten, die an Benutzer in Ihrer Organisation gesendet werden, eine Warnung aus.

3. Microsoft 365 generiert eine Warnung, die auf der Seite **Benachrichtigungen anzeigen** im Security & Compliance Center angezeigt wird. Wenn e-Mail-Benachrichtigungen für die Warnungs Richtlinie aktiviert sind, sendet Microsoft außerdem eine Benachrichtigung an eine Liste der Empfänger. Die Warnungen, die ein Administrator oder andere Benutzer sehen können, werden auf der Seite Benachrichtigungen anzeigen durch die dem Benutzer zugewiesenen Rollen bestimmt. Weitere Informationen finden Sie im Abschnitt [RBAC Permissions Required to View Alerts](#rbac-permissions-required-to-view-alerts) .

4. Ein Administrator verwaltet Warnungen im Security and Compliance Center. Das Verwalten von Benachrichtigungen besteht aus dem Zuweisen eines Warnungsstatus zur Unterstützung beim Nachverfolgen und Verwalten von Untersuchungen.

## <a name="alert-policy-settings"></a>Warnungsrichtlinien Einstellungen

Eine Warnungs Richtlinie besteht aus einer Reihe von Regeln und Bedingungen, die den Benutzer oder die Administrator Aktivität definieren, die eine Warnung generiert, eine Liste der Benutzer, die die Warnung auslösen, wenn Sie die Aktivität ausführen, und einen Schwellenwert, der definiert, wie oft die Aktivität ausgeführt werden muss, bevor eine Warnung ausgelöst wird. Sie kategorisieren auch die Richtlinie und weisen ihr einen Schweregrad zu. Diese beiden Einstellungen unterstützen Sie beim Verwalten von Warnungsrichtlinien (und Warnungen, die ausgelöst werden, wenn die Richtlinienbedingungen übereinstimmen), da Sie diese Einstellungen beim Verwalten von Richtlinien und beim Anzeigen von Warnungen im Security and Compliance Center filtern können. Beispielsweise können Sie Warnungen anzeigen, die den Bedingungen aus der gleichen Kategorie entsprechen, oder Warnungen mit dem gleichen Schweregrad anzeigen.

Wechseln Sie zum Anzeigen und Erstellen von Warnungsrichtlinien zu [https://protection.office.com](https://protection.office.com) und wählen **Alerts** Sie Alerts Alert \> **Policies**aus.

![Wählen Sie im Security and Compliance Center Alerts aus, und wählen Sie dann Warnungsrichtlinien zum Anzeigen und Erstellen von Warnungsrichtlinien aus.](../media/09ebd451-8e84-44e1-aefc-63e70bba4d97.png)

Eine Warnungs Richtlinie besteht aus den folgenden Einstellungen und Bedingungen.

- **Aktivität, die die Warnung verfolgt** – Sie erstellen eine Richtlinie zum Nachverfolgen einer Aktivität oder in einigen Fällen einige verwandte Aktivitäten, beispielsweise das Freigeben einer Datei mit einem externen Benutzer, indem Sie Sie freigeben, Zugriffsberechtigungen zuweisen oder einen anonymen Link erstellen. Wenn ein Benutzer die durch die Richtlinie definierte Aktivität ausführt, wird basierend auf den Warnungsschwellenwert Einstellungen eine Warnung ausgelöst.

    > [!NOTE]
    > Die Aktivitäten, die Sie nachverfolgen können, hängen von der Office 365 Enterprise Ihrer Organisation oder Office 365 US Government Plan ab. Im Allgemeinen erfordern Aktivitäten im Zusammenhang mit Malware Kampagnen und Phishing-Angriffen ein E5/G5-Abonnement oder ein E1/F1/G1-oder E3/G3-Abonnement mit einem Add-on-Abonnement für [Office 365 Advanced Threat Protection](../security/office-365-security/office-365-atp.md) Plan 2.

- **Aktivitätsbedingungen** – für die meisten Aktivitäten können Sie zusätzliche Bedingungen definieren, die erfüllt sein müssen, um eine Warnung auszulösen. Zu den allgemeinen Bedingungen gehören IP-Adressen (damit eine Warnung ausgelöst wird, wenn der Benutzer die Aktivität auf einem Computer mit einer bestimmten IP-Adresse oder in einem IP-Adressbereich ausführt), ob eine Warnung ausgelöst wird, wenn ein bestimmter Benutzer diese Aktivität ausführt, und ob die Aktivität für einen bestimmten Dateinamen oder eine bestimmte URL ausgeführt wird. Sie können auch eine Bedingung konfigurieren, die eine Warnung auslöst, wenn die Aktivität von einem beliebigen Benutzer in Ihrer Organisation ausgeführt wird. Die verfügbaren Bedingungen hängen von der ausgewählten Aktivität ab.

- **Wenn die Warnung ausgelöst wird** , können Sie eine Einstellung konfigurieren, die definiert, wie oft eine Aktivität auftreten kann, bevor eine Warnung ausgelöst wird. Auf diese Weise können Sie eine Richtlinie einrichten, um eine Warnung jedes Mal zu generieren, wenn eine Aktivität mit den Richtlinienbedingungen übereinstimmt, wenn ein bestimmter Schwellenwert überschritten wird oder wenn das Auftreten der Aktivität, die die Warnung verfolgt, für Ihre Organisation ungewöhnlich wird.

    ![Konfigurieren, wie Warnungen ausgelöst werden, basierend auf der Aktivität, einem Schwellenwert oder einer ungewöhnlichen Aktivität für Ihre Organisation](../media/97ee1ed2-e7a9-47a2-a980-5f9f63872c65.png)

    Wenn Sie die Einstellung basierend auf ungewöhnlichen Aktivitäten auswählen, richtet Microsoft einen Basisplan-Wert ein, der die normale Häufigkeit für die ausgewählte Aktivität definiert. Es dauert bis zu sieben Tage, diesen Basisplan einzurichten, während dessen keine Benachrichtigungen generiert werden. Nachdem der Basisplan eingerichtet wurde, wird eine Warnung ausgelöst, wenn die von der Warnungs Richtlinie verfolgte Häufigkeit der Aktivität den Basis Wert erheblich überschreitet. Für Überwachungsbezogene Aktivitäten (beispielsweise Datei-und Ordner Aktivitäten) können Sie einen Basisplan basierend auf einem einzelnen Benutzer oder basierend auf allen Benutzern in Ihrer Organisation einrichten. bei Malware bezogenen Aktivitäten können Sie einen Basisplan basierend auf einer einzelnen Schadsoftware-Familie, einem einzelnen Empfänger oder allen Nachrichten in Ihrer Organisation einrichten.

    > [!NOTE]
    > Die Möglichkeit zum Konfigurieren von Warnungsrichtlinien basierend auf einem Schwellenwert oder basierend auf ungewöhnlichen Aktivitäten erfordert ein E5/G5-Abonnement oder ein E1/F1/G1-oder E3/G3-Abonnement mit einem Office 365 ATP P2, Microsoft 365 E5 Compliance oder Microsoft 365 eDiscovery und Audit Add-on-Abonnement. Organisationen mit einem E1/F1/G1-und E3/G3-Abonnement können nur Warnungsrichtlinien erstellen, bei denen bei jedem Auftreten einer Aktivität eine Warnung ausgelöst wird.

- **Warnungskategorie** : um das Nachverfolgen und Verwalten von Warnungen zu unterstützen, die von einer Richtlinie generiert werden, können Sie einer Richtlinie eine der folgenden Kategorien zuweisen.

  - Verhinderung von Datenverlust

  - Informationsverwaltung

  - Nachrichtenübermittlung

  - Berechtigungen

  - Bedrohungsverwaltung

  - Sonstige

  Wenn eine Aktivität auftritt, die den Bedingungen der Warnungs Richtlinie entspricht, wird die generierte Warnung mit der Kategorie markiert, die in dieser Einstellung definiert ist. Auf diese Weise können Sie Warnungen nachverfolgen und verwalten, die die gleiche Kategorieeinstellungen auf der Seite **Benachrichtigungen anzeigen** im Security and Compliance Center haben, da Sie Warnungen basierend auf der Kategorie sortieren und Filtern können.

- **Warnungsschweregrad** – ähnlich wie bei der Warnungskategorie weisen Sie Warnungsrichtlinien ein Severity-Attribut (**niedrig**, **Mittel**, **hoch**oder **ininformational**) zu. Wie bei der Warnungskategorie wird bei einer Aktivität, die den Bedingungen der Warnungs Richtlinie entspricht, die generierte Warnung mit dem gleichen Schweregrad markiert, der für die Warnungs Richtlinie festgelegt ist. Auf diese Weise können Sie auch Warnungen nachverfolgen und verwalten, die auf der Seite **Benachrichtigungen anzeigen** die gleiche Dringlichkeits Einstellung aufweisen. Sie können beispielsweise die Liste der Warnungen filtern, sodass nur Warnungen mit einem **hohen** Schweregrad angezeigt werden.

    > [!TIP]
    > Bei der Einrichtung einer Warnungs Richtlinie sollten Sie den Aktivitäten einen höheren Schweregrad zuweisen, die zu schwerwiegenden negativen Folgen führen können, beispielsweise die Erkennung von Schadsoftware nach der Zustellung an Benutzer, das Anzeigen vertraulicher oder klassifizierter Daten, die gemeinsame Nutzung von Daten mit externen Benutzern oder andere Aktivitäten, die zu Datenverlust oder Sicherheitsbedrohungen führen können. Dies kann Ihnen helfen, Warnungen und die Aktionen, die Sie zum untersuchen und beheben der zugrunde liegenden Ursachen durchführen, zu priorisieren.

- **E-Mail-Benachrichtigungen** : Sie können die Richtlinie so einrichten, dass e-Mail-Benachrichtigungen an eine Liste von Benutzern gesendet (oder nicht gesendet) werden, wenn eine Warnung ausgelöst wird. Sie können auch einen Grenzwert für tägliche Benachrichtigungen festlegen, sodass während dieses Tages keine Benachrichtigungen mehr für die Benachrichtigung gesendet werden, wenn die maximale Anzahl von Benachrichtigungen erreicht wurde. Neben e-Mail-Benachrichtigungen können Sie oder andere Administratoren die Benachrichtigungen anzeigen, die von einer Richtlinie auf der Seite **Benachrichtigungen anzeigen** ausgelöst werden. Sie können e-Mail-Benachrichtigungen für Warnungsrichtlinien einer bestimmten Kategorie aktivieren oder die Einstellung für einen höheren Schweregrad verwenden.

## <a name="default-alert-policies"></a>Standard Warnungsrichtlinien

Microsoft stellt integrierte Warnungsrichtlinien zur Verfügung, die die Identifizierung von Exchange-Administratorberechtigungen, Malwareaktivitäten, potenziellen externen und internen Bedrohungen sowie Risiken bei der Informationssteuerung ermöglichen. Auf der Seite " **Warnungsrichtlinien** " sind die Namen dieser integrierten Richtlinien fett formatiert, und der Richtlinientyp ist als **System**definiert. Diese Richtlinien sind standardmäßig aktiviert. Sie können diese Richtlinien deaktivieren (oder wieder einschalten), eine Liste der Empfänger einrichten, an die e-Mail-Benachrichtigungen gesendet werden sollen, und einen Grenzwert für tägliche Benachrichtigungen festlegen. Die anderen Einstellungen für diese Richtlinien können nicht bearbeitet werden.

In der folgenden Tabelle werden die verfügbaren Standard Warnungsrichtlinien und die Kategorie beschrieben, der jede Richtlinie zugewiesen ist. Die Kategorie wird verwendet, um zu bestimmen, welche Warnungen ein Benutzer auf der Seite Benachrichtigungen anzeigen anzeigen kann. Weitere Informationen finden Sie im Abschnitt [RBAC Permissions Required to View Alerts](#rbac-permissions-required-to-view-alerts) .

In der Tabelle werden außerdem die Office 365 Enterprise und Office 365 US Government-Plan angegeben, der für jeden erforderlich ist. Einige standardmäßige Warnungsrichtlinien sind verfügbar, wenn Ihre Organisation zusätzlich zu einem E1/F1/G1-oder E3/G3-Abonnement über das entsprechende Add-on-Abonnement verfügt.

| Standardmäßige Warnungs Richtlinie | Beschreibung | Kategorie | Office 365 Enterprise Abonnement |
|:-----|:-----|:-----|:-----|
|**Ein potenziell böswilliger URL-Klick wurde erkannt.**|Generiert eine Warnung, wenn ein Benutzer, der durch [Office 365 sichere ATP-Links](../security/office-365-security/atp-safe-links.md) in Ihrer Organisation geschützt wird, auf einen bösartigen Link klickt. Dieses Ereignis wird ausgelöst, wenn URL-Urteils Änderungen durch Office 365 ATP identifiziert werden oder wenn Benutzer die Office 365 ATP-sichere Links Seiten außer Kraft setzen (basierend auf der Microsoft 365 for Business ATP-Richtlinie für sichere Links in Ihrer Organisation). Diese Warnungs Richtlinie weist eine Einstellung mit **hohem** Schweregrad auf. Für Office 365 ATP P2, E5, G5-Kunden, löst diese Warnung automatisch die [Automatische Untersuchung und Antwort in Office 365 aus](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air). Weitere Informationen zu Ereignissen, die diese Warnung auslösen, finden Sie unter [Einrichten Office 365 ATP-Richtlinien für sichere Links](../security/office-365-security/set-up-atp-safe-links-policies.md).|Bedrohungsverwaltung|E5/G5 oder Office 365 Add-on-Abonnement für ATP P2|
|**Ergebnis der Administrator Übermittlung abgeschlossen**|Generiert eine Warnung, wenn eine [Administrator Übermittlung](../security/office-365-security/admin-submission.md) den erneuten Scan der übermittelten Entität abgeschlossen hat. Eine Warnung wird jedes Mal ausgelöst, wenn ein erneutes Scanergebnis aus einer Administrator Übermittlung gerendert wird. Diese Warnungen sollen Sie daran erinnern, [die Ergebnisse früherer Übermittlungen zu überprüfen](https://protection.office.com/reportsubmission), Benutzer gemeldete Nachrichten zu übermitteln, um die neuesten Urteile zur Richtlinienüberprüfung und erneuten Überprüfung zu erhalten, und Ihnen helfen, festzustellen, ob die Filterrichtlinien in Ihrer Organisation die beabsichtigte Auswirkung haben. Diese Richtlinie weist eine Einstellung mit **niedrigem** Schweregrad auf.|Bedrohungsverwaltung|E1/F1, E3 oder E5|
|**Manuelles untersuchen von e-Mails durch den Administrator ausgelöst**|Generiert eine Warnung, wenn ein Administrator die manuelle Untersuchung einer e-Mail aus dem Threat Explorer auslöst. Weitere Informationen finden Sie unter [Example: A Security Administrator Triggers a Investigation from Threat Explorer] ( https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office#example-a-security-administrator-triggers-an-investigation-from-threat-explorer) . Diese Warnung benachrichtigt Ihre Organisation, dass die Untersuchung gestartet wurde. Die Benachrichtigung enthält Informationen darüber, wer Sie ausgelöst hat, und enthält einen Link zu der Untersuchung. Diese Richtlinie weist eine Einstellung für den **Informations** Grad auf.|Bedrohungsverwaltung| E5/G5 oder Office 365 Add-on-Abonnement für ATP P2| 
|**Erstellen der Weiterleitungs-/Umleitungsregel**|Generiert eine Warnung, wenn jemand in Ihrer Organisation eine Posteingangsregel für Ihr Postfach erstellt, die Nachrichten an ein anderes e-Mail-Konto weiterleitet oder leitet. Diese Richtlinie verfolgt nur Posteingangsregeln, die mit Outlook im Internet (früher als Outlook Web App bezeichnet) oder Exchange Online PowerShell erstellt wurden. Diese Richtlinie weist eine Einstellung mit **niedrigem** Schweregrad auf. Weitere Informationen zum Verwenden von Posteingangsregeln zum Weiterleiten und Umleiten von e-Mails in Outlook im Internet finden Sie unter [Use Rules in Outlook im Internet, um Nachrichten automatisch an ein anderes Konto weiter](https://support.office.com/article/1433e3a0-7fb0-4999-b536-50e05cb67fed)zuleiten.|Bedrohungsverwaltung|E1/F1/G1, E3/G3 oder E5/G5|
|**eDiscovery-Suche gestartet oder exportiert**|Generiert eine Warnung, wenn ein Benutzer das Tool für die Inhaltssuche im Security and Compliance Center verwendet. Eine Warnung wird ausgelöst, wenn die folgenden Inhalts Suchaktivitäten ausgeführt werden: <br/><br/>* Eine Inhaltssuche wird gestartet<br/>* Die Ergebnisse einer Inhaltssuche werden exportiert.<br/>* Ein Inhalts Suchbericht wird exportiert.<br/><br/>Warnungen werden auch ausgelöst, wenn die vorherigen Inhalts Suchaktivitäten in Verbindung mit einem eDiscovery-Fall ausgeführt werden. Diese Richtlinie weist eine Einstellung mit **mittlerem** Schweregrad auf. Weitere Informationen zu Inhalts Suchaktivitäten finden Sie unter [Suchen nach eDiscovery-Aktivitäten im Überwachungsprotokoll](search-for-ediscovery-activities-in-the-audit-log.md#ediscovery-activities).|Bedrohungsverwaltung|E1/F1/G1, E3/G3 oder E5/G5|
|**Erhöhung der Exchange-Administratorberechtigung**|Generiert eine Warnung, wenn jemandem Administratorrechte in Ihrer Exchange Online Organisation zugewiesen sind. Beispiel: Wenn ein Benutzer der Rollengruppe "Organisationsverwaltung" in Exchange Online hinzugefügt wird. Diese Richtlinie weist eine Einstellung mit **niedrigem** Schweregrad auf.|Berechtigungen|E1/F1/G1, E3/G3 oder E5/G5|
|**E-Mail-Nachrichten mit Schadsoftware nach der Zustellung entfernt**|Generiert eine Warnung, wenn Nachrichten mit Schadsoftware an Postfächer in Ihrer Organisation übermittelt werden. Wenn dieses Ereignis auftritt, entfernt Microsoft die infizierten Nachrichten aus Exchange Online-Postfächern, wobei die [Automatische Bereinigung ohne Stunden](../security/office-365-security/zero-hour-auto-purge.md)erfolgt. Diese Richtlinie weist eine Einstellung für den **Informations** Grad auf und löst automatisch die [Automatische Untersuchung und Antwort in Office 365 aus](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air).|Bedrohungsverwaltung|E5/G5 oder Office 365 Add-on-Abonnement für ATP P2|
|**E-Mail-Nachrichten mit Phishing-URLs nach der Zustellung entfernt**|Generiert eine Warnung, wenn Nachrichten mit Phishing an Postfächer in Ihrer Organisation übermittelt werden. Wenn dieses Ereignis auftritt, entfernt Microsoft die infizierten Nachrichten aus Exchange Online-Postfächern, wobei die [Automatische Bereinigung ohne Stunden](../security/office-365-security/zero-hour-auto-purge.md)erfolgt. Diese Richtlinie weist eine Einstellung für den **Informations** Grad auf und löst automatisch die [Automatische Untersuchung und Antwort in Office 365 aus](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air).|Bedrohungsverwaltung|E5/G5 oder Office 365 Add-on-Abonnement für ATP P2|
|**Vom Benutzer als Schadsoftware oder Phishing gemeldete e-Mail**|Generiert eine Warnung, wenn Benutzer in Ihrer Organisation Nachrichten als Phishing-e-Mails mithilfe des Berichtsnachrichten-Add-Ins melden. Diese Richtlinie weist eine Einstellung für den **Informations** Grad auf. Weitere Informationen zu diesem Add-in finden Sie unter [Verwenden des Berichtsnachrichten-Add-ins](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2). Für Office 365 ATP P2, E5, G5-Kunden, löst diese Warnung automatisch die [Automatische Untersuchung und Antwort in Office 365 aus](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air).|Bedrohungsverwaltung|E1/F1/G1, E3/G3 oder E5/G5|
|**E-Mail-Sende Grenzwert überschritten**|Generiert eine Warnung, wenn jemand in Ihrer Organisation mehr e-Mails gesendet hat, als es die ausgehende Spam Richtlinie erlaubt. Dies ist normalerweise ein Hinweis darauf, dass der Benutzer zu viele e-Mails sendet oder dass das Konto kompromittiert werden kann. Diese Richtlinie weist eine Einstellung mit **mittlerem** Schweregrad auf. Wenn Sie eine von dieser Warnungs Richtlinie generierte Warnung erhalten, sollten Sie [überprüfen, ob das Benutzerkonto kompromittiert wurde](../security/office-365-security/responding-to-a-compromised-email-account.md).|Bedrohungsverwaltung|E1/F1/G1, E3/G3 oder E5/G5|
|**Nachrichten wurden verzögert**|Generiert eine Warnung, wenn Microsoft keine e-Mail-Nachrichten über einen Connector an Ihre lokale Organisation oder einen Partnerserver übermittelt. In diesem Fall wird die Nachricht in Office 365 in die Warteschlange eingereiht. Diese Warnung wird ausgelöst, wenn 2.000 Nachrichten oder mehr als eine Stunde lang in die Warteschlange eingereiht wurden. Diese Richtlinie weist eine Einstellung mit **hohem** Schweregrad auf.|Nachrichtenübermittlung|E1/F1/G1, E3/G3 oder E5/G5|
|**Schadsoftware-Kampagne nach Zustellung erkannt**|Generiert eine Warnung, wenn eine ungewöhnlich große Anzahl von Nachrichten mit Schadsoftware an Postfächer in Ihrer Organisation übermittelt werden. Wenn dieses Ereignis auftritt, entfernt Microsoft die infizierten Nachrichten aus Exchange Online Postfächern. Diese Richtlinie weist eine Einstellung mit **hohem** Schweregrad auf.|Bedrohungsverwaltung|E5/G5 oder Office 365 Add-on-Abonnement für ATP P2|
|**Schadsoftware-Kampagne erkannt und blockiert**|Generiert eine Warnung, wenn jemand versucht hat, eine ungewöhnlich große Anzahl von e-Mail-Nachrichten zu senden, die eine bestimmte Art von Schadsoftware für Benutzer in Ihrer Organisation enthalten. Wenn dieses Ereignis eintritt, werden die infizierten Nachrichten von Microsoft blockiert und nicht an Postfächerüber mittelt. Diese Richtlinie weist eine Einstellung mit **niedrigem** Schweregrad auf.|Bedrohungsverwaltung|E5/G5 oder Office 365 Add-on-Abonnement für ATP P2|
|**In SharePoint und OneDrive erkannte Malware Kampagne**|Generiert eine Warnung, wenn in Dateien, die sich in SharePoint-Websites oder OneDrive-Konten in Ihrer Organisation befinden, eine ungewöhnlich hohe Menge an Schadsoftware oder Viren erkannt wird. Diese Richtlinie weist eine Einstellung mit **hohem** Schweregrad auf.|Bedrohungsverwaltung|E5/G5 oder Office 365 Add-on-Abonnement für ATP P2|
|**Aufgrund von Mandanten-oder Benutzer Überschreibung 1 gesendeter Phishing**<sup>1</sup> -Schutz|Generiert eine Warnung, wenn Microsoft eine Administrator-oder Benutzer Überschreibung erkennt, die die Zustellung einer Phishing-Nachricht an ein Postfach erlaubt. Beispiele für Außerkraftsetzungen sind ein Posteingang oder eine Nachrichtenfluss Regel, die Nachrichten von einem bestimmten Absender oder einer bestimmten Domäne oder eine Antispampolitik zulässt, die Nachrichten von bestimmten Absendern oder Domänen zulässt. Diese Richtlinie weist eine Einstellung mit **hohem** Schweregrad auf.|Bedrohungsverwaltung|E5/G5 oder Office 365 Add-on-Abonnement für ATP P2|
|**Erkannte verdächtige e-Mail-Sende Muster**|Generiert eine Warnung, wenn jemand in Ihrer Organisation verdächtige e-Mails gesendet hat und das Risiko besteht, dass e-Mails nicht gesendet werden. Dies ist eine frühzeitige Warnung für das Verhalten, die darauf hindeuten kann, dass das Konto gefährdet ist, aber nicht schwer genug, um den Benutzer zu beschränken. Diese Richtlinie weist eine Einstellung mit **mittlerem** Schweregrad auf. Obwohl es selten ist, kann eine von dieser Richtlinie generierte Warnung eine Anomalie sein. Es empfiehlt sich jedoch, zu [überprüfen, ob das Benutzerkonto kompromittiert wurde](../security/office-365-security/responding-to-a-compromised-email-account.md).|Bedrohungsverwaltung|E1/F1/G1, E3/G3 oder E5/G5  |
|**Mandanten vom Senden von e-Mails eingeschränkt**|Generiert eine Warnung, wenn der Großteil des e-Mail-Datenverkehrs aus Ihrer Organisation als verdächtig erkannt wurde und Microsoft Ihre Organisation vom Senden von e-Mails eingeschränkt hat. Untersuchen Sie potenziell gefährdete Benutzer-und Administratorkonten, neue Connectors oder offene Relays, und wenden Sie sich an den Microsoft-Support, um die Blockierung Ihrer Organisation aufzuheben. Diese Richtlinie weist eine Einstellung mit **hohem** Schweregrad auf. Weitere Informationen dazu, warum Organisationen blockiert werden, finden Sie unter [Beheben von Problemen mit der Zustellung von e-Mails für den Fehlercode 5.7.7 XX in Exchange Online](https://go.microsoft.com/fwlink/?linkid=2022138).|Bedrohungsverwaltung|E1/F1/G1, E3/G3 oder E5/G5|
|**Ungewöhnliche Dateiaktivität für externe Benutzer**|Generiert eine Warnung, wenn eine ungewöhnlich große Anzahl von Aktivitäten für Dateien in SharePoint oder OneDrive von Benutzern außerhalb Ihrer Organisation ausgeführt wird. Dazu gehören Aktivitäten wie der Zugriff auf Dateien, das Herunterladen von Dateien und das Löschen von Dateien. Diese Richtlinie weist eine Einstellung mit **hohem** Schweregrad auf.|Informationsverwaltung|E5/G5, Office 365 ATP P2 oder Microsoft 365 E5-Add-on-Abonnement|
|**Ungewöhnlich Umfang der externen Dateifreigabe**|Generiert eine Warnung, wenn eine ungewöhnlich große Anzahl von Dateien in SharePoint oder OneDrive für Benutzer außerhalb Ihrer Organisation freigegeben wird. Diese Richtlinie weist eine Einstellung mit **mittlerem** Schweregrad auf.|Informationsverwaltung|E5/G5, Office 365 ATP P2 oder Microsoft 365 E5-Add-on-Abonnement|
|**Ungewöhnlicher Umfang der Dateilöschung**|Generiert eine Warnung, wenn eine ungewöhnlich große Anzahl von Dateien in SharePoint oder OneDrive innerhalb eines kurzen Zeitrahmens gelöscht wird. Diese Richtlinie weist eine Einstellung mit **mittlerem** Schweregrad auf.|Informationsverwaltung|E5/G5, Office 365 ATP P2 oder Microsoft 365 E5-Add-on-Abonnement|
|**Ungewöhnlich höhere e-Mail-Zuwachs Meldung als Phishing**|Generiert eine Warnung, wenn sich die Anzahl der Personen in Ihrer Organisation mit dem Berichtsnachrichten-Add-in in Outlook erheblich erhöht, um Nachrichten als Phishing-e-Mails zu melden. Diese Richtlinie weist eine Einstellung mit **hohem** Schweregrad auf. Weitere Informationen zu diesem Add-in finden Sie unter [Verwenden des Berichtsnachrichten-Add-ins](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).|Bedrohungsverwaltung|E5/G5 oder Office 365 Add-on-Abonnement für ATP P2|
|**Benutzeridentitätswechsel – Phishing im Posteingang/Ordner**<sup>1,</sup><sup>2</sup>|Generiert eine Warnung, wenn Microsoft erkennt, dass eine Administrator-oder Benutzer Überschreibung die Zustellung einer Phishing-Nachricht für den Benutzeridentitätswechsel in den Posteingang (oder einen anderen Benutzer zugänglichen Ordner) eines Postfachs zulässig ist. Beispiele für Außerkraftsetzungen sind ein Posteingang oder eine Nachrichtenfluss Regel, die Nachrichten von einem bestimmten Absender oder einer bestimmten Domäne oder eine Antispampolitik zulässt, die Nachrichten von bestimmten Absendern oder Domänen zulässt. Diese Richtlinie weist eine Einstellung mit **mittlerem** Schweregrad auf.|Bedrohungsverwaltung|E5/G5 oder Office 365 Add-on-Abonnement für ATP P2|
|**Benutzer vom Senden von e-Mails eingeschränkt**|Generiert eine Warnung, wenn jemand in Ihrer Organisation vom Senden von ausgehenden e-Mails eingeschränkt ist. Dies ergibt sich normalerweise, wenn ein Konto kompromittiert wird und der Benutzer auf der Seite " **eingeschränkte Benutzer** " im Security & Compliance Center aufgeführt ist. (Um auf diese Seite zuzugreifen, wechseln Sie zu **Threat Management > überprüfen > eingeschränkten Benutzern**). Diese Richtlinie weist eine Einstellung mit **hohem** Schweregrad auf. Weitere Informationen zu eingeschränkten Benutzern finden Sie unter [Entfernen eines Benutzers, einer Domäne oder einer IP-Adresse aus einer Sperrliste nach dem Senden von Spam-e-Mails](https://docs.microsoft.com/office365/securitycompliance/removing-user-from-restricted-users-portal-after-spam).|Bedrohungsverwaltung|E1/F1/G1, E3/G3 oder E5/G5|
|||||

> [!NOTE]
> <sup>1</sup> wir haben diese Standard Warn Richtlinie vorübergehend basierend auf Kundenfeedback entfernt. Wir arbeiten daran, Sie zu verbessern, und werden Sie in naher Zukunft durch eine neue Version ersetzen. Bis dahin können Sie eine benutzerdefinierte Warnungs Richtlinie erstellen, um diese Funktionalität mithilfe der folgenden Einstellungen zu ersetzen:<br/>&nbsp; * Aktivitäten sind Phishing-e-Mails, die zum Zeitpunkt der Zustellung erkannt werden<br/>&nbsp; * E-Mail ist nicht zap 'd<br/>&nbsp; * E-Mail-Richtung ist eingehend<br/>&nbsp; * E-Mail-Zustellungsstatus wird zugestellt<br/>&nbsp; * Erkennungstechnologie: böswillige URL-Aufbewahrung, URL-Detonation, erweiterter Phishing-Filter, allgemeiner Phishingfilter, Domänen Identitätswechsel, Benutzeridentitätswechsel und Marken Identitätswechsel<br/><br/>&nbsp;&nbsp;&nbsp;Weitere Informationen zum Anti-Phishing in Office 365 finden Sie unter [Einrichten von Anti-Phishing-und Anti-Phishing-Richtlinien](../security/office-365-security/set-up-anti-phishing-policies.md).<br/><br/><sup>2</sup> um diese Warnungs Richtlinie erneut zu erstellen, führen Sie die Anweisungen in der vorherigen Fußnote aus, aber wählen Sie als einzige Erkennungstechnologie den Benutzeridentitätswechsel aus.

Die ungewöhnliche Aktivität, die von einigen der integrierten Richtlinien überwacht wird, basiert auf dem gleichen Prozess wie die zuvor beschriebene Warnungsschwellenwert Einstellung. Microsoft legt einen Baseline-Wert fest, der die normale Häufigkeit für "übliche" Aktivitäten definiert. Benachrichtigungen werden dann ausgelöst, wenn die Häufigkeit der Aktivitäten, die von der integrierten Warnungs Richtlinie verfolgt werden, den Basisplan erheblich überschreitet.

## <a name="viewing-alerts"></a>Anzeigen von Warnungen

Wenn eine von Benutzern in Ihrer Organisation ausgeführte Aktivität mit den Einstellungen einer Warnungs Richtlinie übereinstimmt, wird eine Warnung generiert und auf der Seite **Benachrichtigungen anzeigen** im Security and Compliance Center angezeigt. In Abhängigkeit von den Einstellungen einer Warnungs Richtlinie wird eine e-Mail-Benachrichtigung auch an eine Liste der angegebenen Benutzer gesendet, wenn eine Warnung ausgelöst wird. Für jede Warnung zeigt das Dashboard auf der Seite **Benachrichtigungen anzeigen** den Namen der entsprechenden Warnungs Richtlinie, den Schweregrad und die Kategorie für die Warnung (definiert in der Warnungs Richtlinie) sowie die Häufigkeit an, mit der eine Aktivität aufgetreten ist, die dazu führte, dass die Warnung generiert wurde. Dieser Wert basiert auf der Schwellenwerteinstellung der Warnungs Richtlinie. Das Dashboard zeigt außerdem den Status jeder Warnung an. Weitere Informationen zur Verwendung der Status-Eigenschaft zum Verwalten von Warnungen finden Sie im Abschnitt [Managing Alerts](#managing-alerts) .

Um Warnungen anzuzeigen, wechseln [https://protection.office.com](https://protection.office.com) Sie zu und wählen Sie **Alerts** Benachrichtigungen \> **anzeigen**aus.

![Wählen Sie in der Sicherheits-und Konformitätsstufe Warnungen aus, und wählen Sie Warnungen anzeigen aus, um Warnungen anzuzeigen.](../media/ec5ea59b-bf61-459f-8b65-970ab4bb8bcc.png)

Sie können die folgenden Filter verwenden, um eine Teilmenge aller Benachrichtigungen auf der Seite **Benachrichtigungen anzeigen** anzuzeigen.

- **Status.** Verwenden Sie diesen Filter, um Warnungen anzuzeigen, denen ein bestimmter Status zugewiesen ist. Der Standardstatus ist **aktiv**. Sie oder andere Administratoren können den Statuswert ändern.

- **Richtlinie.** Verwenden Sie diesen Filter, um Warnungen anzuzeigen, die mit der Einstellung einer oder mehrerer Warnungsrichtlinien übereinstimmen. Sie können auch alle Benachrichtigungen für alle Warnungsrichtlinien anzeigen.

- **Zeitbereich.** Verwenden Sie diesen Filter, um Warnungen anzuzeigen, die innerhalb eines bestimmten Datums-und Zeitbereichs generiert wurden.

- **Schwere.** Verwenden Sie diesen Filter, um Warnungen anzuzeigen, denen ein bestimmter Schweregrad zugewiesen ist.

- **Kategorie.** Verwenden Sie diesen Filter, um Warnungen aus einer oder mehreren Warnungs Kategorien anzuzeigen.

- **Quelle.** Verwenden Sie diesen Filter, um Warnungen anzuzeigen, die von Warnungsrichtlinien im Security and Compliance Center ausgelöst wurden, oder Warnungen, die durch Office 365 Cloud App-Sicherheitsrichtlinien ausgelöst wurden, oder beides. Weitere Informationen zu Office 365 Cloud App-Sicherheitswarnungen finden Sie im Abschnitt zum [Anzeigen von Cloud-App-Sicherheitswarnungen](#viewing-cloud-app-security-alerts) .

## <a name="alert-aggregation"></a>Warnungs Aggregation

Wenn mehrere Ereignisse mit den Bedingungen einer Warnungs Richtlinie mit einer kurzen Zeitspanne auftreten, werden Sie einer vorhandenen Warnung durch einen Prozess namens " *Warnungs Aggregation*" hinzugefügt. Wenn ein Ereignis eine Warnung auslöst, wird die Warnung generiert und auf der Seite **Benachrichtigungen anzeigen** angezeigt, und eine Benachrichtigung wird gesendet. Wenn das gleiche Ereignis innerhalb des Aggregations Intervalls auftritt, fügt Microsoft 365 der vorhandenen Warnung Details zu dem neuen Ereignis hinzu, anstatt eine neue Warnung auszulösen. Das Ziel der Warnungs Aggregation besteht darin, die Warnung "Ermüdung" zu reduzieren und Sie zu konzentrieren und Aktionen für weniger Warnungen für dasselbe Ereignis durchführen zu können.

Die Länge des Aggregations Intervalls hängt von Ihrem Office 365-oder Microsoft 365-Abonnement ab.

|Abonnement|Aggregations Intervall|
|:---------|:---------:|
|Office 365 oder Microsoft 365 E5/G5|1 Minute|
|Office 365 ATP Plan 2 |1 Minute|
|E5-Konformitäts-Add-on oder E5-Ermittlungs-und Überwachungs-Add-on|1 Minute|
|Office 365 oder Microsoft 365 E1/F1/G1 oder E3/F3/G3|15 Minuten|
|Office 365 ATP-Plan 1 oder Exchange Online Protection|15 Minuten|
|||

Wenn Ereignisse mit derselben Warnungs Richtlinie innerhalb des Aggregations Intervalls auftreten, werden der ursprünglichen Warnung Details zum nachfolgenden Ereignis hinzugefügt. Für alle Ereignisse werden Informationen über aggregierte Ereignisse im Feld Details angezeigt, und die Häufigkeit, mit der ein Ereignis mit dem Aggregations Intervall aufgetreten ist, wird im Feld Aktivität/Trefferanzahl angezeigt. Sie können weitere Informationen zu allen Instanzen von aggregierten Ereignissen anzeigen, indem Sie die Aktivitätsliste anzeigen.

Der folgende Screenshot zeigt eine Warnung mit vier aggregierten Ereignissen. Die Aktivitätsliste enthält Informationen zu den vier e-Mail-Nachrichten, die für die Warnung relevant sind.

![Beispiel für eine Warnungs Aggregation](../media/AggregatedAlertExample.png)

Beachten Sie die folgenden Aspekte bei der Warnungs Aggregation:

- Warnungen, die durch das **Klicken auf eine potenziell bösartige URL ausgelöst wurden, wurde erkannt** [Standard Warnungs Richtlinie](#default-alert-policies) wird nicht aggregiert. Dies liegt daran, dass von dieser Richtlinie ausgelöste Warnungen für jeden Benutzer und jede e-Mail-Nachricht eindeutig sind.

- Zu diesem Zeitpunkt gibt die Alert-Eigenschaft der **Trefferanzahl** nicht die Anzahl aggregierter Ereignisse für alle Warnungsrichtlinien an. Für Warnungen, die durch diese Warnungsrichtlinien ausgelöst werden, können Sie die aggregierten Ereignisse anzeigen, indem Sie in der Benachrichtigung auf **Nachrichtenliste anzeigen** oder **Aktivität anzeigen** klicken. Wir arbeiten daran, die Anzahl aggregierter Ereignisse, die in der Alert-Eigenschaft der **Trefferanzahl** aufgeführt sind, für alle Warnungsrichtlinien zu erstellen.

## <a name="rbac-permissions-required-to-view-alerts"></a>Erforderliche RBAC-Berechtigungen zum Anzeigen von Warnungen

Die Berechtigungen für die rollenbasierte Zugriffssteuerung (Role Based Access Control, RBAC), die Benutzern in Ihrer Organisation zugewiesen sind, bestimmen, welche Warnungen ein Benutzer auf der Seite **Benachrichtigungen anzeigen** sehen kann. Wie wird dies erreicht? Die Verwaltungsrollen, die Benutzern zugewiesen sind (basierend auf Ihrer Mitgliedschaft in Rollengruppen im Security & Compliance Center), bestimmen, welche Warnungs Kategorien ein Benutzer auf der Seite **Benachrichtigungen anzeigen** sehen kann. Im Folgenden finden Sie einige Beispiele:

- Mitglieder der Rollengruppe "Datensatzverwaltung" können nur die Warnungen anzeigen, die von Warnungsrichtlinien generiert werden, denen die Kategorie " **Information Governance** " zugewiesen ist.

- Mitglieder der Rollengruppe "Compliance-Administrator" können keine Warnungen anzeigen, die von Warnungsrichtlinien generiert werden, denen die Kategorie " **Threat Management** " zugewiesen ist.

- Mitglieder der Rollengruppe "eDiscovery-Manager" können keine Warnungen anzeigen, da keine der zugewiesenen Rollen die Berechtigung zum Anzeigen von Warnungen aus jeder Warnungskategorie bereitstellt.

Mit diesem Entwurf (basierend auf RBAC-Berechtigungen) können Sie bestimmen, welche Warnungen von Benutzern in bestimmten Auftrags Rollen in Ihrer Organisation angezeigt (und verwaltet) werden können.

In der folgenden Tabelle sind die Rollen aufgeführt, die zum Anzeigen von Warnungen aus den sechs verschiedenen Warnungs Kategorien erforderlich sind. In der ersten Spalte in den Tabellen werden alle Rollen im Security & Compliance Center aufgeführt.  Ein Häkchen zeigt an, dass ein Benutzer, dem diese Rolle zugewiesen ist, Warnungen aus der entsprechenden Warnungskategorie anzeigen kann, die in der obersten Zeile aufgeführt ist.

Informationen zur Kategorie, der eine standardmäßige Warnungs Richtlinie zugewiesen ist, finden Sie in der Tabelle im Abschnitt [standardmäßige Warnungsrichtlinien](#default-alert-policies) .

|Rolle|Informationsverwaltung|Verhinderung von Datenverlust|Nachrichtenübermittlung|Berechtigungen|Bedrohungsverwaltung|Sonstige|
|:---------|:---------:|:---------:|:---------:|:---------:|:---------:|:---------:|
|Überwachungsprotokolle|||||||
|Fallverwaltung|||||||
|Complianceadministrator|![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|Compliance-Suche|||||||
|Geräteverwaltung|||||||
|Dispositionsverwaltung|||||||
|DLP-Konformitätsverwaltung||![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|||||
|Exportieren|||||||
|Hold|||||||
|Benachrichtigungen verwalten||||||![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|Organisationskonfiguration||||||![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|Vorschau|||||||
|Datensatzverwaltung|![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||||||
|Aufbewahrungsverwaltung|![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||||||
|Überprüfung|||||||
|RMS-Entschlüsselung|||||||
|Rollenverwaltung||||![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|||
|Suchen und löschen|||||||
|Sicherheitsadministrator||![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|Sicherheitsleseberechtigter||![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)
|Service Assurance-Ansicht|||||||
|Aufsichts Überprüfungs Administrator|||||||
|Überwachungsprotokolle nur anzeigen|||||||
|Geräteverwaltung mit Ansichts Schutz|||||||
|DLP-Konformitätsverwaltung mit Ansichts Schutz||![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|||||
|Benachrichtigungen nur anzeigen verwalten||||||![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|Schreibgeschützte Empfänger|||  ![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||||
|Datensatzverwaltung mit Ansichts Schutz|![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||||||
|Aufbewahrungsverwaltung mit Ansichts Schutz|![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||||||
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
> Sie können auch die einer Rollengruppe zugewiesenen Rollen im Security & Compliance Center anzeigen. Wechseln Sie zur Seite **Berechtigungen** , und wählen Sie eine Rollengruppe aus. Die zugewiesenen Rollen werden auf der Flyout-Seite aufgelistet.

## <a name="managing-alerts"></a>Verwalten von Warnungen

Nachdem Benachrichtigungen generiert und auf der Seite **Benachrichtigungen anzeigen** im Security and Compliance Center angezeigt wurden, können Sie diese selektieren, untersuchen und beheben. Hier sind einige Aufgaben, die Sie zum Verwalten von Warnungen ausführen können.

- **Weisen Sie Warnungen einen Status zu.** Sie können Alerts einen der folgenden Status zuweisen: **aktiv** (Standardwert), unter **Suchen**, **aufgelöst**oder **entlassen**. Anschließend können Sie nach dieser Einstellung filtern, um Warnungen mit der gleichen Statuseinstellung anzuzeigen. Diese Statuseinstellung kann helfen, den Prozess der Verwaltung von Warnungen zu verfolgen.

- **Anzeigen von Warnungsdetails.** Sie können eine Warnung auswählen, um eine Flyout-Seite mit Details zur Warnung anzuzeigen. Die detaillierten Informationen hängen von der entsprechenden Warnungs Richtlinie ab, enthält aber in der Regel Folgendes: Name des tatsächlichen Vorgangs, der die Warnung ausgelöst hat (beispielsweise ein Cmdlet), eine Beschreibung der Aktivität, die die Warnung ausgelöst hat, der Benutzer (oder die Liste der Benutzer), der die Warnung ausgelöst hat, sowie der Name (und der Link zu) der entsprechenden Warnungs Richtlinie.

  - Der Name des tatsächlichen Vorgangs, der die Warnung ausgelöst hat, beispielsweise ein Cmdlet oder ein Überwachungsprotokoll Vorgang.

  - Eine Beschreibung der Aktivität, die die Warnung ausgelöst hat.

  - Der Benutzer, der die Warnung ausgelöst hat. Dies ist nur für Warnungsrichtlinien enthalten, die für die Nachverfolgung eines einzelnen Benutzers oder einer einzelnen Aktivität eingerichtet sind.

  - Gibt an, wie oft die von der Warnung verfolgte Aktivität ausgeführt wurde. Diese Nummer stimmt möglicherweise nicht mit der tatsächlichen Anzahl der zugehörigen Warnungen überein, die auf der Seite Benachrichtigungen anzeigen aufgeführt sind, da möglicherweise weitere Warnungen ausgelöst wurden.

  - Ein Link zu einer Aktivitätsliste, die ein Element für jede Aktivität enthält, die ausgeführt wurde, die die Warnung ausgelöst hat. Jeder Eintrag in dieser Liste gibt an, wann die Aktivität aufgetreten ist, den Namen des tatsächlichen Vorgangs (wie "filedeleted") und den Benutzer, der die Aktivität ausgeführt hat, das Objekt (wie eine Datei, ein eDiscovery-Fall oder ein Postfach), unter dem die Aktivität ausgeführt wurde, und die IP-Adresse des Benutzercomputers. Bei Malware bezogenen Warnungen wird diese mit einer Nachrichtenliste verknüpft.

  - Der Name (und Link zu) der entsprechenden Warnungs Richtlinie.

- **E-Mail-Benachrichtigungen unterdrücken.** Sie können e-Mail-Benachrichtigungen von der Flyout-Seite für eine Warnung deaktivieren (oder unterdrücken). Wenn Sie e-Mail-Benachrichtigungen unterdrücken, sendet Microsoft keine Benachrichtigungen, wenn Aktivitäten oder Ereignisse mit den Bedingungen der Warnungs Richtlinie übereinstimmen. Warnungen werden jedoch ausgelöst, wenn von Benutzern ausgeführte Aktivitäten den Bedingungen der Warnungs Richtlinie entsprechen. Sie können e-Mail-Benachrichtigungen auch deaktivieren, indem Sie die Warnungs Richtlinie bearbeiten.

- **Warnungen auflösen.** Sie können eine Warnung auf der Flyout-Seite als aufgelöst für eine Warnung markieren (wodurch der Status der Warnung auf " **aufgelöst**" festgelegt wird). Wenn Sie den Filter nicht ändern, werden auf der Seite **Benachrichtigungen anzeigen** keine aufgelösten Warnungen angezeigt.

## <a name="viewing-cloud-app-security-alerts"></a>Anzeigen von Cloud-App-Sicherheitswarnungen

Warnungen, die von Office 365-Cloud-App-Sicherheitsrichtlinien ausgelöst werden, werden jetzt auf der Seite **Benachrichtigungen anzeigen** im Security and Compliance Center angezeigt. Dies umfasst Warnungen, die von Aktivitätsrichtlinien und Warnungen ausgelöst werden, die durch anomale Erkennungsrichtlinien in Office 365 Cloud-App-Sicherheit ausgelöst werden. Dies bedeutet, dass Sie alle Benachrichtigungen im Security and Compliance Center anzeigen können. Office 365 Cloud-App-Sicherheit ist nur für Organisationen mit einem Office 365 Enterprise E5-oder Office 365 US Government G5-Abonnement verfügbar. Weitere Informationen finden Sie unter [Overview of Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security).

Organisationen mit Microsoft Cloud App Security als Teil eines Enterprise Mobility + Security E5-Abonnements oder als eigenständiger Dienst können auch Cloud App-Sicherheitswarnungen anzeigen, die im Zusammenhang mit Office 365-apps und-Diensten im Security & Compliance Center stehen.

Wenn Sie nur Cloud-App-Sicherheitswarnungen im Security and Compliance Center anzeigen möchten, verwenden Sie den **Quell** Filter, und wählen Sie **Cloud App Security**aus.

![Verwenden des Quell Filters zum Anzeigen nur von Cloud-App-Sicherheitswarnungen](../media/FilterCASAlerts.png)

Ähnlich wie bei einer Warnung, die durch eine Warnungs Richtlinie im Security and Compliance Center ausgelöst wurde, können Sie eine Cloud-App-Sicherheitswarnung auswählen, um eine Flyout-Seite mit Details zur Warnung anzuzeigen. Die Benachrichtigung enthält einen Link zum Anzeigen der Details und zum Verwalten der Warnung im Cloud-App-Sicherheitsportal und einen Link zu der entsprechenden Cloud-App-Sicherheitsrichtlinie, die die Warnung ausgelöst hat. Weitere Informationen finden Sie unter [Monitor Alerts in Cloud App Security](https://docs.microsoft.com/cloud-app-security/monitor-alerts).

![Warnungsdetails enthalten Links zum Cloud-App-Sicherheitsportal](../media/CASAlertDetail.png)

> [!IMPORTANT]
> Wenn Sie den Status einer Cloud App-Sicherheitswarnung im Security and Compliance Center ändern, wird der Auflösungsstatus für dieselbe Warnung im Cloud App Security-Portal nicht aktualisiert. Wenn Sie beispielsweise den Status der Warnung im Security and Compliance Center als **aufgelöst** kennzeichnen, wird der Status der Warnung im Cloud-App-Sicherheitsportal unverändert. Um eine Cloud-App-Sicherheitswarnung aufzulösen oder zu schließen, verwalten Sie die Warnung im Cloud-App-Sicherheitsportal.
