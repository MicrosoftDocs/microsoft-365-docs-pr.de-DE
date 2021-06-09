---
title: Konfigurieren und Verwalten Microsoft-Bedrohungsexperten Funktionen über Microsoft 365 Defender
description: Abonnieren Sie Microsoft-Bedrohungsexperten über Microsoft 365 Defender, um es für Ihre täglichen Sicherheitsvorgänge und Die Sicherheitsverwaltung zu konfigurieren, zu verwalten und zu verwenden.
keywords: Microsoft-Bedrohungsexperten, verwalteter Dienst für die Bedrohungssuche, MTE, von Microsoft verwalteter Suchdienst
search.product: Windows 10
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-maave
author: martyav
localization_priority: normal
manager: dansimp
audience: ITPro
ms.topic: article
ms.openlocfilehash: 0ccb8482dae94de4a9f43a5ecaf7c701e6dd82a5
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844790"
---
# <a name="configure-and-manage-microsoft-threat-experts-capabilities-through-microsoft-365-defender"></a>Konfigurieren und Verwalten Microsoft-Bedrohungsexperten Funktionen über Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gilt für:**

- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)

[!INCLUDE [Prerelease](../includes/prerelease.md)]

## <a name="before-you-begin"></a>Bevor Sie beginnen

> [!IMPORTANT]
> Bevor Sie sich bewerben, sollten Sie die Berechtigungsanforderungen für die Microsoft-Bedrohungsexperten – Benachrichtigungen über gezielte Angriffe verwaltete Bedrohungssuche mit Ihrem Microsoft Technical Service-Anbieter und Ihrem Kontoteam besprechen.

Um Benachrichtigungen über gezielte Angriffe zu erhalten, müssen Sie Microsoft 365 Defender mit registrierten Geräten bereitgestellt haben. Übermitteln Sie dann eine Anwendung über das M365-Portal für Microsoft-Bedrohungsexperten – Benachrichtigungen über gezielte Angriffe.

Wenden Sie sich an Ihr Kontoteam oder einen Microsoft-Mitarbeiter, um Microsoft-Bedrohungsexperten – Experts on Demand zu abonnieren. Bei Bedarf können Sie sich mit unseren Bedrohungsexperten beraten, wie Sie Ihre Organisation vor relevanten Erkennungen und Angreifern schützen können.

## <a name="apply-for-microsoft-threat-experts---targeted-attack-notifications-service"></a>Anwenden auf Microsoft-Bedrohungsexperten – Dienst für gezielte Angriffsbenachrichtigungen

Wenn Sie bereits über Microsoft Defender für Endpunkt und Microsoft 365 Defender verfügen, können Sie Microsoft-Bedrohungsexperten – Benachrichtigungen über gezielte Angriffe über das Microsoft 365 Defender-Portal beantragen.  Benachrichtigungen über gezielte Angriffe gewähren Ihnen spezielle Einblicke und Analysen, um die kritischsten Bedrohungen für Ihre Organisation zu identifizieren, damit Sie schnell darauf reagieren können.

1. Wechseln Sie im Navigationsbereich zu **Einstellungen > Endpunkte > Allgemeine > Erweiterte Features > Microsoft-Bedrohungsexperten – Benachrichtigungen über gezielte Angriffe.**

2. Wählen Sie **Anwenden** aus.

    ![Abbildung Microsoft-Bedrohungsexperten Einstellungen](../../media/mte/mte-collaboratewithmte.png)

3. Geben Sie Ihren Namen und Ihre E-Mail-Adresse ein, damit Microsoft Sie bezüglich Ihrer Anwendung kontaktieren kann.

    ![Abbildung Microsoft-Bedrohungsexperten Anwendung](../../media/mte/mte-apply.png)

4. Lesen Sie die [Datenschutzerklärung,](https://privacy.microsoft.com/en-us/privacystatement)und wählen Sie **"Übermitteln"** aus, wenn Sie fertig sind. Sie erhalten eine Willkommens-E-Mail, sobald Ihre Anwendung genehmigt wurde.

    ![Abbildung Microsoft-Bedrohungsexperten Anwendungsbestätigung](../../media/mte/mte-applicationconfirmation.png)

5. Nachdem Sie Ihre Willkommens-E-Mail erhalten haben, erhalten Sie automatisch gezielte Angriffsbenachrichtigungen.

6. Sie können Ihren Status überprüfen, indem Sie **Einstellungen > Endpunkte > Allgemeine > Erweiterte Features** besuchen. Nach der Genehmigung wird die **Umschaltfläche Microsoft-Bedrohungsexperten – Benachrichtigung über gezielte Angriffe** angezeigt und eingeschaltet. 

## <a name="where-youll-see-the-targeted-attack-notifications-from-microsoft-threat-experts"></a>Wo die Benachrichtigungen über gezielte Angriffe von Microsoft-Bedrohungsexperten

Sie können eine gezielte Angriffsbenachrichtigung von Microsoft-Bedrohungsexperten über die folgenden Medien erhalten:

- Die Seite **"Vorfälle"** des Microsoft 365 Defender-Portals
- Das **Benachrichtigungsdashboard** des Microsoft 365 Defender-Portals
- [OData-Warnungs-API](/windows/security/threat-protection/microsoft-defender-atp/get-alerts) und [REST-API](/windows/security/threat-protection/microsoft-defender-atp/pull-alerts-using-rest-api)
- [DeviceAlertEvents-Tabelle](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-devicealertevents-table) in der erweiterten Suche
- Ihr Posteingang, wenn Sie benutzerorientierte Angriffsbenachrichtigungen per E-Mail an Sie senden möchten. Weitere Informationen finden Sie unten unter [Erstellen einer E-Mail-Benachrichtigungsregel.](#create-an-email-notification-rule)

### <a name="create-an-email-notification-rule"></a>Erstellen einer E-Mail-Benachrichtigungsregel

Sie können Regeln zum Senden von E-Mail-Benachrichtigungen für Benachrichtigungsempfänger erstellen. Ausführliche Informationen finden Sie unter  [Konfigurieren von Benachrichtigungen](/windows/security/threat-protection/microsoft-defender-atp/configure-email-notifications) zum Erstellen, Bearbeiten, Löschen oder Beheben von E-Mail-Benachrichtigungen.

## <a name="view-targeted-attack-notifications"></a>Anzeigen von Benachrichtigungen über gezielte Angriffe

Sie erhalten eine gezielte Angriffsbenachrichtigung von Microsoft-Bedrohungsexperten in Ihrer E-Mail, nachdem Sie Ihr System für den Empfang von E-Mail-Benachrichtigungen konfiguriert haben.

1. Wählen Sie den Link in der E-Mail aus, um zum entsprechenden Warnungskontext im Dashboard zu wechseln, das mit **Bedrohungsexperten** gekennzeichnet ist.

2. Wählen Sie auf der Seite **"Warnungen"** das gleiche Warnungsthema aus wie das, das Sie in der E-Mail erhalten haben, um weitere Details anzuzeigen.

## <a name="subscribe-to-microsoft-threat-experts---experts-on-demand"></a>Abonnieren von Microsoft-Bedrohungsexperten – Experts on Demand

Wenn Sie bereits Ein Kunde von Microsoft Defender für Endpunkt sind, können Sie sich an Ihren Microsoft-Vertreter wenden, um Microsoft-Bedrohungsexperten – Experts on Demand zu abonnieren.

## <a name="consult-a-microsoft-threat-expert-about-suspicious-cybersecurity-activities-in-your-organization"></a>Wenden Sie sich an einen Microsoft-Bedrohungsexperten zu verdächtigen Cybersicherheitsaktivitäten in Ihrer Organisation.

Sie können Microsoft-Bedrohungsexperten im Microsoft 365 Defender-Portal kontaktieren. Experten können Ihnen dabei helfen, komplexe Bedrohungen und Benachrichtigungen über gezielte Angriffe zu verstehen. Arbeiten Sie mit Experten zusammen, um weitere Details zu Warnungen und Vorfällen oder Ratschläge zum Umgang mit Kompromittierungen zu erhalten. Erhalten Sie Einen Einblick in den Kontext der Bedrohungserkennung, der von Ihrem Portal-Dashboard beschrieben wird.

> [!NOTE]
>
> - Warnungsanfragen im Zusammenhang mit den benutzerdefinierten Threat Intelligence-Daten Ihrer Organisation werden derzeit nicht unterstützt. Wenden Sie sich an Ihr Sicherheitsteam oder das Team für die Reaktion auf Sicherheitsvorfälle, um Weitere Informationen zu erhalten.
> - Sie müssen über die Berechtigung **"Sicherheitseinstellungen im Security Center verwalten"** im Microsoft 365 Defender-Portal verfügen, um eine Anfrage über das Formular **"Einen Bedrohungsexperten konsultieren"** zu übermitteln.

1. Navigieren Sie zur Portalseite, die sich auf die Informationen bezieht, die Sie untersuchen möchten: z. B. **Gerät,** **Warnung** oder **Vorfall.** Stellen Sie sicher, dass die Portalseite im Zusammenhang mit Ihrer Anfrage angezeigt wird, bevor Sie eine Untersuchungsanfrage senden.

2. Wählen Sie im oberen Menü **? Wenden Sie sich an einen Bedrohungsexperten.**

    ![Abbildung von Microsoft-Bedrohungsexperten Experts on Demand aus dem Menü](../../media/mte/incidents-action-mte-highlighted.png)

    Ein Flyoutbildschirm wird geöffnet.

    Der Header gibt an, ob Sie ein Testabonnement oder ein vollständiges Microsoft-Bedrohungsexperten – Experten-on-Demand-Abonnement haben.

    ![Abbildung des Testabonnements für Microsoft-Bedrohungsexperten Experts on Demand](../../media/mte/mte-trial.png)

    Das **Feld "Untersuchungsthema"** wird bereits mit dem Link zur entsprechenden Seite für Ihre Anforderung ausgefüllt.

3. Geben Sie im nächsten Feld genügend Informationen an, um dem Microsoft-Bedrohungsexperten genügend Kontext zu geben, um die Untersuchung zu starten.

4. Geben Sie die E-Mail-Adresse ein, die Sie verwenden möchten, um Microsoft-Bedrohungsexperten zu entsprechen.

> [!NOTE]
> Wenn Sie den Status Ihrer Experts on Demand-Fälle über Den Microsoft Services Hub nachverfolgen möchten, wenden Sie sich an Ihren technischen Account Manager.

Sehen Sie sich dieses Video an, um einen schnellen Überblick über den Microsoft Services Hub zu geben.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4pk9f]

## <a name="sample-investigation-topics"></a>Beispiele für Untersuchungsthemen

### <a name="alert-information"></a>Warnungsinformationen

- Wir haben eine neue Art von Warnung für eine Binärdatei außerhalb des Landes gesehen. Wir können die Warnungs-ID angeben. Können Sie uns mehr über diese Warnung mitteilen und wie wir sie weiter untersuchen können?
- Wir haben zwei ähnliche Angriffe beobachtet, die beide versuchen, schädliche PowerShell-Skripts auszuführen, aber unterschiedliche Warnungen generieren. Eine ist "Verdächtige PowerShell-Befehlszeile" und die andere ist "Eine schädliche Datei wurde basierend auf der Von O365 bereitgestellten Anzeige erkannt". Was ist der Unterschied?
- Wir haben heute eine ungerade Warnung zu einer ungewöhnlichen Anzahl fehlgeschlagener Anmeldungen vom Gerät eines Profilbenutzers erhalten. Wir können keine weiteren Nachweise für diese Versuche finden. Wie können Microsoft 365 Defender diese Versuche sehen? Welche Anmeldetypen werden überwacht?
- Können Sie mehr Kontext oder Einblicke in die Warnung "Verdächtiges Verhalten durch ein Systemhilfsprogramm wurde beobachtet" geben?
- Ich habe eine Warnung mit dem Titel "Erstellen einer Weiterleitungs-/Umleitungsregel" beobachtet. Ich bin der Meinung, dass die Aktivität gutartig ist. Können Sie mir mitteilen, warum ich eine Warnung erhalten habe?

### <a name="possible-machine-compromise"></a>Mögliche Computerkompromitt

- Können Sie erklären, warum auf vielen Geräten in unserer Organisation eine Meldung oder Warnung zu "Unbekannter Prozess beobachtet" angezeigt wird? Wir freuen uns über jede Eingabe, um zu verdeutlichen, ob diese Nachricht oder Warnung mit böswilligen Aktivitäten zusammenhängt.
- Können Sie helfen, eine mögliche Kompromittierung auf dem folgenden System zu überprüfen, die in der letzten Woche zurückgeht? Es verhält sich ähnlich wie eine vorherige Schadsoftwareerkennung auf demselben System vor sechs Monaten.

### <a name="threat-intelligence-details"></a>Details zur Bedrohungserkennung

- Wir haben eine Phishing-E-Mail erkannt, die ein schädliches Word-Dokument an einen Benutzer übermittelt hat. Das Dokument verursachte eine Reihe verdächtiger Ereignisse, die mehrere Warnungen für eine bestimmte Schadsoftwarefamilie auslösten. Haben Sie Informationen zu dieser Schadsoftware? Wenn ja, können Sie uns einen Link senden?
- Wir haben kürzlich einen Blogbeitrag über eine Bedrohung gesehen, die auf unsere Branche ausgerichtet ist. Können Sie uns helfen zu verstehen, welchen Schutz Microsoft 365 Defender gegen diesen Bedrohungsakteur bietet?
- Wir haben kürzlich eine Phishing-Kampagne gegen unsere Organisation beobachtet. Können Sie uns mitteilen, ob dies speziell auf unser Unternehmen oder unsere Vertikale ausgerichtet war?

### <a name="microsoft-threat-experts-alert-communications"></a>Microsoft-Bedrohungsexperten-Warnungskommunikation

- Kann Ihr Team für die Reaktion auf Vorfälle uns dabei helfen, die Benachrichtigung über gezielte Angriffe zu beheben, die wir erhalten haben?
- Wir haben diese Benachrichtigung über gezielte Angriffe von Microsoft-Bedrohungsexperten erhalten. Wir haben kein eigenes Team für die Reaktion auf Vorfälle. Was können wir jetzt tun und wie können wir den Vorfall eindämmen?
- Wir haben eine gezielte Angriffsbenachrichtigung von Microsoft-Bedrohungsexperten erhalten. Welche Daten können Sie uns zur Verfügung stellen, die wir an unser Team zur Behandlung von Sicherheitsvorfällen weitergeben können?

> [!NOTE]
> Microsoft-Bedrohungsexperten ist ein verwalteter Dienst zur Bedrohungssuche und kein Vorfallreaktionsdienst. Die Experten können die Untersuchung jedoch bei Bedarf nahtlos in die Dienste des Erkennungs- und Reaktionsteams (DETECTION and Response Team, DART) der Microsoft Cybersecurity Solutions Group (CSG) übertragen. Sie können sich auch für die Zusammenarbeit mit Ihrem eigenen Team zur Reaktion auf Vorfälle entscheiden, um Probleme zu beheben, die eine Reaktion auf Vorfälle erfordern.

## <a name="scenario"></a>Szenario

### <a name="receive-a-progress-report-about-your-managed-hunting-inquiry"></a>Erhalten eines Statusberichts zu Ihrer verwalteten Suche

Die Antwort von Microsoft-Bedrohungsexperten variiert je nach Anfrage. Im Allgemeinen erhalten Sie eine der folgenden Antworten:

- Weitere Informationen sind erforderlich, um mit der Untersuchung fortzufahren.
- Eine Datei oder mehrere Dateibeispiele sind erforderlich, um den technischen Kontext zu ermitteln.
- Untersuchung erfordert mehr Zeit
- Die ersten Informationen reichten aus, um die Untersuchung abzuschließen.

Wenn ein Experte weitere Informationen oder Dateibeispiele anfordert, ist es wichtig, schnell zu reagieren, um die Untersuchung in Gang zu halten.

## <a name="see-also"></a>Siehe auch

- [Microsoft-Bedrohungsexperten – Übersicht](microsoft-threat-experts.md)
