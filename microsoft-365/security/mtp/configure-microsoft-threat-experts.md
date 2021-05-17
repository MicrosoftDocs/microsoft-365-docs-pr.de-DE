---
title: Konfigurieren und Verwalten Microsoft-Bedrohungsexperten Funktionen über Microsoft 365 Defender
description: Abonnieren Sie Microsoft Threats Experts über Microsoft 365 Defender, um ihn zu konfigurieren, zu verwalten und in Ihren täglichen Sicherheitsvorgängen und der Sicherheitsverwaltung zu verwenden.
keywords: Microsoft-Bedrohungsexperten, Managed Threat Hunting Service, MTE, Microsoft Managed Hunting Service
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
ms.openlocfilehash: 38bf768f1a5603fa3da0d7a3acc8f409ed6372de
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765527"
---
# <a name="configure-and-manage-microsoft-threat-experts-capabilities-through-microsoft-365-defender"></a>Konfigurieren und Verwalten Microsoft-Bedrohungsexperten Funktionen über Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gilt für:**

- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)

[!INCLUDE [Prerelease](../includes/prerelease.md)]

## <a name="before-you-begin"></a>Bevor Sie beginnen

> [!IMPORTANT]
> Bevor Sie sich bewerben, stellen Sie sicher, dass Sie die Berechtigungsanforderungen für den verwalteten Dienst für die Suche nach Bedrohungen Microsoft-Bedrohungsexperten – Gezielte Angriffsbenachrichtigungen mit Ihrem Microsoft Technical Service-Anbieter und -Kontoteam besprechen.

Um Benachrichtigungen über gezielte Angriffe zu erhalten, müssen Sie Microsoft 365 Defender mit registrierten Geräten bereitstellen. Übermitteln Sie dann eine Anwendung über das M365-Portal für Microsoft-Bedrohungsexperten – Benachrichtigungen über gezielte Angriffe.

Wenden Sie sich an Ihr Kontoteam oder Ihren Microsoft-Vertreter, um Microsoft-Bedrohungsexperten – Experten bei Bedarf zu abonnieren. Experten bei Bedarf können Sie sich mit unseren Bedrohungsexperten darüber beraten, wie Sie Ihre Organisation vor relevanten Erkennungen und Gegnern schützen können.

## <a name="apply-for-microsoft-threat-experts---targeted-attack-notifications-service"></a>Bewerben für Microsoft-Bedrohungsexperten – Dienst für gezielte Angriffsbenachrichtigungen

Wenn Sie bereits über Microsoft Defender for Endpoint und Microsoft 365 Defender verfügen, können Sie Microsoft-Bedrohungsexperten – Targeted Attack Notifications über das Microsoft 365 Defender-Portal beantragen.  Gezielte Angriffsbenachrichtigungen bieten Ihnen spezielle Einblicke und Analysen, um die wichtigsten Bedrohungen für Ihre Organisation zu identifizieren, damit Sie schnell darauf reagieren können.

1. Wechseln Sie im Navigationsbereich zu **Einstellungen > Endpoints > General > Advanced features > Microsoft-Bedrohungsexperten – Targeted Attack Notifications**.

2. Wählen Sie **Anwenden** aus.

    ![Abbildung der Microsoft-Bedrohungsexperten Einstellungen](../../media/mte/mte-collaboratewithmte.png)

3. Geben Sie Ihren Namen und Ihre E-Mail-Adresse ein, damit Microsoft Sie über Ihre Anwendung kontaktieren kann.

    ![Abbildung der Microsoft-Bedrohungsexperten Anwendung](../../media/mte/mte-apply.png)

4. Lesen Sie [die Datenschutzbestimmungen,](https://privacy.microsoft.com/en-us/privacystatement)und wählen Sie **dann Senden** aus, wenn Sie fertig sind. Sobald Ihre Anwendung genehmigt wurde, erhalten Sie eine Willkommens-E-Mail.

    ![Abbildung der Microsoft-Bedrohungsexperten Anwendungsbestätigung](../../media/mte/mte-applicationconfirmation.png)

5. Nachdem Sie Ihre Willkommens-E-Mail erhalten haben, erhalten Sie automatisch gezielte Angriffsbenachrichtigungen.

6. Sie können Ihren Status überprüfen, indem Sie **Einstellungen > Endpoints > General > Advanced features besuchen.** Nach der Genehmigung wird **Microsoft-Bedrohungsexperten - Targeted Attack Notification-Umschalter** angezeigt und **aktiviert.**

## <a name="where-youll-see-the-targeted-attack-notifications-from-microsoft-threat-experts"></a>Dort werden die gezielten Angriffsbenachrichtigungen von Microsoft-Bedrohungsexperten

Sie können gezielte Angriffsbenachrichtigungen von Microsoft-Bedrohungsexperten über die folgenden Medien erhalten:

- Die Microsoft 365 des **Defender-Portals**
- Das Microsoft 365 des Benachrichtigungsdashboards des **Defender-Portals**
- OData-Warnungs-API und [REST-API](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/pull-alerts-using-rest-api) [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/get-alerts)
- [DeviceAlertEvents-Tabelle](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-devicealertevents-table) in erweiterte Suche
- Ihr Posteingang, wenn Sie auswählen, dass Ihnen gezielte Angriffsbenachrichtigungen per E-Mail gesendet werden. Weitere [Informationen finden Sie unter Erstellen einer E-Mail-Benachrichtigungsregel](#create-an-email-notification-rule) unten.

### <a name="create-an-email-notification-rule"></a>Erstellen einer E-Mail-Benachrichtigungsregel

Sie können Regeln zum Senden von E-Mail-Benachrichtigungen für Benachrichtigungsempfänger erstellen. Ausführliche Informationen finden Sie unter  [Configure alert notifications](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-email-notifications) to create, edit, delete, or troubleshoot email notification.

## <a name="view-targeted-attack-notifications"></a>Anzeigen von Benachrichtigungen über gezielte Angriffe

Nachdem Sie Ihr System für den Empfang von E-Mail-Benachrichtigungen konfiguriert Microsoft-Bedrohungsexperten, erhalten Sie eine Benachrichtigung über gezielte Angriffe.

1. Wählen Sie den Link in der E-Mail aus, um zum entsprechenden Warnungskontext im Dashboard zu wechseln, das mit **Bedrohungsexperten markiert ist.**

2. Wählen Sie **auf** der Seite Warnungen dasselbe Warnungsthema aus wie das, das Sie in der E-Mail erhalten haben, um weitere Details anzuzeigen.

## <a name="subscribe-to-microsoft-threat-experts---experts-on-demand"></a>Abonnieren von Microsoft-Bedrohungsexperten – Experten bei Bedarf

Wenn Sie bereits Ein Microsoft Defender for Endpoint-Kunde sind, können Sie sich an Ihren Microsoft-Vertreter wenden, um Microsoft-Bedrohungsexperten - Experts on Demand zu abonnieren.

## <a name="consult-a-microsoft-threat-expert-about-suspicious-cybersecurity-activities-in-your-organization"></a>Wenden Sie sich an einen Microsoft-Bedrohungsexperten zu verdächtigen Cybersicherheitsaktivitäten in Ihrer Organisation.

Sie können die Microsoft-Bedrohungsexperten innerhalb des Microsoft 365 Defender-Portals kontaktieren. Experten helfen Ihnen, komplexe Bedrohungen und gezielte Angriffsbenachrichtigungen zu verstehen. Partner with experts for further details about alerts and incidents, or advice on handling compromise. Erhalten Sie Einblick in den Bedrohungsintelligenzkontext, der vom Portaldashboard beschrieben wird.

> [!NOTE]
>
> - Warnungsanfragen im Zusammenhang mit den angepassten Daten der Bedrohungsintelligenz Ihrer Organisation werden derzeit nicht unterstützt. Wenden Sie sich an Ihr Sicherheits- oder Vorfallreaktionsteam, um Weitere Informationen zu erhalten.
> - Sie benötigen die Berechtigung Sicherheitseinstellungen **in Security Center** verwalten im Microsoft 365 Defender-Portal, um eine Anfrage über das Formular "Experten für **Bedrohungen konsultieren" zu** übermitteln.

1. Navigieren Sie zur Portalseite im Zusammenhang mit den Informationen, die Sie untersuchen möchten: z. B. **Device**, **Alert** oder **Incident**. Stellen Sie sicher, dass die Portalseite im Zusammenhang mit Ihrer Anfrage angezeigt wird, bevor Sie eine Untersuchungsanfrage senden.

2. Wählen Sie im oberen Menü **? Wenden Sie sich an einen Bedrohungsexperten.**

    ![Abbildung der Microsoft-Bedrohungsexperten Experten bei Bedarf aus dem Menü](../../media/mte/incidents-action-mte-highlighted.png)

    Ein Flyoutbildschirm wird geöffnet.

    Die Kopfzeile gibt an, ob Sie ein Testabonnement oder ein vollständiges Microsoft-Bedrohungsexperten - Experts on-Demand-Abonnement haben.

    ![Abbildung des Microsoft-Bedrohungsexperten Von Experten bei Bedarf testabonnement bildschirm](../../media/mte/mte-trial.png)

    Das **Thema "Untersuchung"** wird bereits mit dem Link zur relevanten Seite für Ihre Anforderung aufgefüllt.

3. Geben Sie im nächsten Feld genügend Informationen ein, um dem Microsoft-Bedrohungsexperten genügend Kontext zu geben, um die Untersuchung zu starten.

4. Geben Sie die E-Mail-Adresse ein, die Sie zum Korrespondieren mit Microsoft-Bedrohungsexperten.

> [!NOTE]
> Wenn Sie den Status Ihrer Experts on Demand-Fälle über Microsoft Services Hub nachverfolgen möchten, erreichen Sie Ihren technischen Account Manager.

Sehen Sie sich dieses Video an, um einen schnellen Überblick über den Microsoft Services Hub zu erhalten.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4pk9f]

## <a name="sample-investigation-topics"></a>Beispieluntersuchungsthemen

### <a name="alert-information"></a>Warnungsinformationen

- Wir haben eine neue Art von Warnung für eine binäre "living-off-the-land" gesehen. Wir können die Warnungs-ID bereitstellen. Können Sie uns mehr über diese Warnung mitteilen und wie wir sie weiter untersuchen können?
- Wir haben zwei ähnliche Angriffe beobachtet, die beide versuchen, schädliche PowerShell-Skripts auszuführen, aber unterschiedliche Warnungen generieren. Die eine ist "Verdächtige PowerShell-Befehlszeile", die andere ist "Eine schädliche Datei wurde basierend auf der Angabe von O365 erkannt". Was ist der Unterschied?
- Wir haben heute eine ungerade Warnung über eine abnorme Anzahl fehlgeschlagener Anmeldungen vom Gerät eines profilierten Benutzers erhalten. Weitere Nachweise für diese Versuche finden wir nicht. Wie kann Microsoft 365 defender diese Versuche sehen? Welche Anmeldetypen werden überwacht?
- Können Sie mehr Kontext oder Einblicke in die Warnung "Verdächtiges Verhalten durch ein Systemprogramm wurde beobachtet" geben?
- Ich habe eine Warnung mit dem Titel "Erstellung einer Weiterleitungs-/Umleitungsregel" beobachtet. Ich bin der Meinung, dass die Aktivität gutartig ist. Können Sie mir mitteilen, warum ich eine Warnung erhalten habe?

### <a name="possible-machine-compromise"></a>Mögliche Computerkompromisse

- Können Sie erläutern, warum auf vielen Geräten in unserer Organisation eine Nachricht oder Warnung für "Unbekannter Prozess beobachtet" angezeigt wird? Wir freuen uns über jede Eingabe, um zu klären, ob diese Nachricht oder Warnung im Zusammenhang mit böswilligen Aktivitäten steht.
- Können Sie einen möglichen Kompromiss mit dem folgenden System aus der letzten Woche überprüfen? Es verhält sich ähnlich wie eine vorherige Schadsoftwareerkennung auf demselben System vor sechs Monaten.

### <a name="threat-intelligence-details"></a>Details zur Bedrohungsintelligenz

- Wir haben eine Phishing-E-Mail erkannt, die einem Benutzer ein schädliches Word-Dokument zugestellt hat. Das Dokument verursachte eine Reihe verdächtiger Ereignisse, die mehrere Warnungen für eine bestimmte Schadsoftwarefamilie auslösten. Haben Sie Informationen zu dieser Schadsoftware? Wenn ja, können Sie uns einen Link senden?
- Wir haben kürzlich einen Blogbeitrag über eine Bedrohung gesehen, die auf unsere Branche zielt. Können Sie uns helfen, zu verstehen, welchen Microsoft 365 Defender vor diesem Bedrohungsakteur bietet?
- Wir haben kürzlich eine Phishingkampagne beobachtet, die gegen unsere Organisation durchgeführt wurde. Können Sie uns mitteilen, ob dies speziell auf unser Unternehmen oder unsere Vertikalen ausgerichtet war?

### <a name="microsoft-threat-experts-alert-communications"></a>Microsoft-Bedrohungsexperten Benachrichtigung

- Kann Ihr Team für die Reaktion auf Vorfälle uns dabei helfen, die Benachrichtigung über den gezielten Angriff zu adressieren, die wir erhalten haben?
- Wir haben diese gezielte Angriffsbenachrichtigung von Microsoft-Bedrohungsexperten. Wir verfügen nicht über ein eigenes Team zur Reaktion auf Vorfälle. Was können wir jetzt tun, und wie können wir den Vorfall eindähen?
- Wir haben eine gezielte Angriffsbenachrichtigung von Microsoft-Bedrohungsexperten. Welche Daten können Sie uns zur Verfügung stellen, die wir an unser Team für die Reaktion auf Vorfälle übergeben können?

> [!NOTE]
> Microsoft-Bedrohungsexperten ist ein verwalteter Bedrohungssuchedienst und kein Dienst zur Reaktion auf Vorfälle. Die Experten können die Untersuchung jedoch bei Bedarf nahtlos auf die Erkennungs- und Reaktionsteamdienste (Detection and Response Team, DART) der Microsoft Cybersecurity Solutions Group (CSG) umstiegen. Sie können sich auch dafür entscheiden, sich mit Ihrem eigenen Team für die Reaktion auf Vorfälle zu beschäftigen, um Probleme zu beheben, die eine Reaktion auf Vorfälle erfordern.

## <a name="scenario"></a>Szenario

### <a name="receive-a-progress-report-about-your-managed-hunting-inquiry"></a>Erhalten eines Fortschrittsberichts zu Ihrer anfrage verwalteten Suche

Die Antwort von Microsoft-Bedrohungsexperten variiert je nach Ihrer Anfrage. Sie erhalten im Allgemeinen eine der folgenden Antworten:

- Weitere Informationen sind erforderlich, um die Untersuchung fortsetzen zu können.
- Eine Datei oder mehrere Dateibeispiele sind erforderlich, um den technischen Kontext zu bestimmen.
- Untersuchung erfordert mehr Zeit
- Erste Informationen reichten aus, um die Untersuchung zu schließen.

Wenn ein Experte weitere Informationen oder Dateibeispiele anfordert, ist es wichtig, schnell zu reagieren, um die Untersuchung in Bewegung zu halten.

## <a name="see-also"></a>Siehe auch

- [Microsoft-Bedrohungsexperten – Übersicht](microsoft-threat-experts.md)
