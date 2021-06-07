---
title: Konfigurieren und Verwalten der Funktionen von Microsoft-Bedrohungsexperten
ms.reviewer: ''
description: Registrieren Sie sich bei Microsoft-Bedrohungsexperten, um es für Ihre täglichen Sicherheitsvorgänge und Die Sicherheitsverwaltung zu konfigurieren, zu verwalten und zu verwenden.
keywords: Microsoft-Bedrohungsexperten, verwalteter Dienst für die Bedrohungssuche, MTE, von Microsoft verwalteter Suchdienst
search.product: Windows 10
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 226fc389aab24dda2425a17f5fb8d49da93e35d8
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770661"
---
# <a name="configure-and-manage-microsoft-threat-experts-capabilities"></a>Konfigurieren und Verwalten der Funktionen von Microsoft-Bedrohungsexperten

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Möchten Sie Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="before-you-begin"></a>Bevor Sie beginnen 
> [!NOTE]
> Besprechen Sie die Berechtigungsanforderungen mit Ihrem Microsoft Technical Service-Anbieter und Ihrem Kontoteam, bevor Sie sich auf Microsoft-Bedrohungsexperten – Verwalteter Bedrohungssuchedienst für gezielte Angriffsbenachrichtigungen – bewerben.

Stellen Sie sicher, dass Defender für Endpunkt in Ihrer Umgebung mit registrierten Geräten und nicht nur in einem Labor bereitgestellt wurde.

Wenn Sie Defender für Endpunkt-Kunde sind, müssen Sie Microsoft-Bedrohungsexperten – **Benachrichtigungen** über gezielte Angriffe beantragen, um spezielle Einblicke und Analysen zu erhalten, um die kritischsten Bedrohungen zu identifizieren, damit Sie schnell darauf reagieren können. Wenden Sie sich an Ihr Kontoteam oder einen Microsoft-Mitarbeiter, um Microsoft-Bedrohungsexperten zu abonnieren **– Experten bei Bedarf,** um sich mit unseren Bedrohungsexperten zu relevanten Erkennungen und Angreifern zu beraten.

## <a name="apply-for-microsoft-threat-experts---targeted-attack-notifications-service"></a>Anwenden auf Microsoft-Bedrohungsexperten – Dienst für gezielte Angriffsbenachrichtigungen 
Wenn Sie bereits Defender für Endpunkt-Kunde sind, können Sie sich über die Microsoft Defender Security Center bewerben. 

1. Wechseln Sie im Navigationsbereich zu **Einstellungen > Allgemeinen > Erweiterten Features > Microsoft-Bedrohungsexperten – Benachrichtigungen über gezielte Angriffe.**

2. Klicken Sie auf **Anwenden**.

    ![Abbildung der Einstellungen für Microsoft-Bedrohungsexperten](images/mte-collaboratewithmte.png)

3. Geben Sie Ihren Namen und Ihre E-Mail-Adresse ein, damit Microsoft zu Ihnen in Ihrer Anwendung zurückkehren kann.

    ![Abbildung der Microsoft-Bedrohungsexperten Anwendung](images/mte-apply.png)

4. Lesen Sie die [Datenschutzerklärung,](https://privacy.microsoft.com/en-us/privacystatement)und klicken Sie dann auf **"Übermitteln",** wenn Sie fertig sind. Sie erhalten eine Willkommens-E-Mail, sobald Ihre Anwendung genehmigt wurde.

    ![Abbildung Microsoft-Bedrohungsexperten Anwendungsbestätigung](images/mte-applicationconfirmation.png)

Wenn Sie akzeptiert werden, erhalten Sie eine Willkommens-E-Mail, und die Schaltfläche **"Übernehmen"** wird in eine Umschaltfläche geändert, die "ein" ist. Wenn Sie sich selbst aus dem Dienst für Benachrichtigungen über gezielte Angriffe herausnehmen möchten, ziehen Sie die Umschaltfläche "aus" und klicken Sie unten auf der Seite auf **"Einstellungen speichern".** 

## <a name="where-youll-see-the-targeted-attack-notifications-from-microsoft-threat-experts"></a>Wo die Benachrichtigungen über gezielte Angriffe von Microsoft-Bedrohungsexperten 
Sie können eine gezielte Angriffsbenachrichtigung von Microsoft-Bedrohungsexperten über das folgende Medium erhalten:  
- Die Seite **"Vorfälle"** des Defender für Endpunkt-Portals 
- Warnungsdashboard des  Defender für Endpunkt-Portals  
- [OData-Warnungs-API](/windows/security/threat-protection/microsoft-defender-atp/get-alerts) und [REST-API](/windows/security/threat-protection/microsoft-defender-atp/pull-alerts-using-rest-api)
- [DeviceAlertEvents-Tabelle](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-devicealertevents-table) in der erweiterten Suche
- Ihre E-Mail, wenn Sie sie konfigurieren möchten 

Um gezielte Angriffsbenachrichtigungen per E-Mail zu erhalten, erstellen Sie eine E-Mail-Benachrichtigungsregel.

### <a name="create-an-email-notification-rule"></a>Erstellen einer E-Mail-Benachrichtigungsregel 
Sie können Regeln zum Senden von E-Mail-Benachrichtigungen für Benachrichtigungsempfänger erstellen. Weitere Informationen finden Sie unter  [Konfigurieren von Benachrichtigungen](configure-email-notifications.md) zum Erstellen, Bearbeiten, Löschen oder Beheben von Problemen mit E-Mail-Benachrichtigungen.

## <a name="view-the-targeted-attack-notification"></a>Anzeigen der Benachrichtigung über gezielte Angriffe  
Sie erhalten eine gezielte Angriffsbenachrichtigung von Microsoft-Bedrohungsexperten in Ihrer E-Mail, nachdem Sie Ihr System für den Empfang von E-Mail-Benachrichtigungen konfiguriert haben.  

1. Klicken Sie auf den Link in der E-Mail, um zum entsprechenden Warnungskontext im Dashboard zu wechseln, das mit **Bedrohungsexperten** gekennzeichnet ist. 

2. Wählen Sie im Dashboard das gleiche Warnungsthema aus, das Sie aus der E-Mail erhalten haben, um die Details anzuzeigen.  

## <a name="subscribe-to-microsoft-threat-experts---experts-on-demand"></a>Abonnieren von Microsoft-Bedrohungsexperten – Experten bei Bedarf
Dies ist als Abonnementdienst verfügbar. Wenn Sie bereits Defender für Endpunkt-Kunde sind, können Sie sich an Ihren Microsoft-Vertreter wenden, um Microsoft-Bedrohungsexperten – Experts on Demand zu abonnieren. 

## <a name="consult-a-microsoft-threat-expert-about-suspicious-cybersecurity-activities-in-your-organization"></a>Wenden Sie sich an einen Microsoft-Bedrohungsexperten zu verdächtigen Cybersicherheitsaktivitäten in Ihrer Organisation. 
Sie können mit Microsoft-Bedrohungsexperten zusammenarbeiten, die direkt innerhalb der Microsoft Defender Security Center für eine zeitnahe und genaue Antwort eingebunden werden können. Experten bieten Einblicke, um komplexe Bedrohungen, Benachrichtigungen über gezielte Angriffe, die Sie erhalten, oder wenn Sie weitere Informationen zu den Warnungen, einem potenziell kompromittierten Gerät oder einem Kontext der Bedrohungserkennung benötigen, der auf Ihrem Portaldashboard angezeigt wird, besser zu verstehen. 

> [!NOTE]
> - Warnungsanfragen im Zusammenhang mit den angepassten Threat Intelligence-Daten Ihrer Organisation werden derzeit nicht unterstützt. Wenden Sie sich an Ihr Sicherheitsteam oder das Team für die Reaktion auf Vorfälle, um Weitere Informationen zu erhalten.
> - Sie müssen über die Berechtigung **"Sicherheitseinstellungen verwalten"** im Security Center-Portal verfügen, um eine Anfrage "Fragen eines Bedrohungsexperten" übermitteln zu können.

1. Navigieren Sie zur Portalseite mit den relevanten Informationen, die Sie untersuchen möchten, z. B. die **Vorfallseite.** Stellen Sie sicher, dass die Seite für die entsprechende Warnung oder das entsprechende Gerät angezeigt wird, bevor Sie eine Untersuchungsanforderung senden. 

2. Klicken Sie im oberen rechten Menü auf das **?** aus. Wählen Sie dann **"Bedrohungsexperten** konsultieren" aus. 

    ![Abbildung von Microsoft-Bedrohungsexperten Experts on Demand aus dem Menü](images/mte-eod-menu.png)

    Ein Flyoutbildschirm wird geöffnet. Der folgende Bildschirm zeigt, wenn Sie ein Testabonnement haben.

    ![Abbildung Microsoft-Bedrohungsexperten Bildschirm "Experten bei Bedarf"](images/mte-eod.png)

    Der folgende Bildschirm zeigt, wenn Sie ein vollständiges Microsoft-Bedrohungsexperten – Experts on-Demand-Abonnement haben.

    ![Abbildung des vollständigen Abonnementbildschirms von Microsoft-Bedrohungsexperten Experts on Demand](images/mte-eod-fullsubscription.png)

    Das **Themenfeld Anfrage** ist mit dem Link zur entsprechenden Seite für Ihre Untersuchungsanfrage ausgefüllt. Beispielsweise ein Link zur Seite "Vorfall", "Warnung" oder "Gerätedetails", auf der Sie sich befanden, als Sie die Anforderung gestellt haben.

3.  Geben Sie im nächsten Feld genügend Informationen an, um dem Microsoft-Bedrohungsexperten genügend Kontext zu geben, um die Untersuchung zu starten.
  
4. Geben Sie die E-Mail-Adresse ein, die Sie verwenden möchten, um Microsoft-Bedrohungsexperten zu entsprechen.

> [!NOTE]
> Wenn Sie den Status Ihrer Experts on Demand-Fälle über den Microsoft Services Hub nachverfolgen möchten, wenden Sie sich an Ihren Technical Account Manager. 

Sehen Sie sich dieses Video an, um einen schnellen Überblick über den Microsoft Services Hub zu geben.

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4pk9f] 


   
## <a name="sample-investigation-topics-that-you-can-consult-with-microsoft-threat-experts---experts-on-demand"></a>Beispiele für Untersuchungsthemen, die Sie mit Microsoft-Bedrohungsexperten - Experts on Demand 

**Warnungsinformationen**
- Wir sehen eine neue Art von Warnung für eine Binärdatei außerhalb des Landes: [AlertID]. Können Sie uns etwas mehr über diese Warnung mitteilen und wie wir weitere Untersuchungen durchführen können?
- Wir haben zwei ähnliche Angriffe beobachtet, die versuchen, schädliche PowerShell-Skripts auszuführen, aber unterschiedliche Warnungen generieren. Eine ist "Verdächtige PowerShell-Befehlszeile" und die andere ist "Eine schädliche Datei wurde basierend auf der Von O365 bereitgestellten Anzeige erkannt". Was ist der Unterschied?
- Ich erhalte heute eine ungerade Warnung für die anormale Anzahl fehlgeschlagener Anmeldungen vom Gerät eines Profilbenutzers. Ich kann keine weiteren Nachweise für diese Anmeldeversuche finden. Wie können diese Versuche von Defender für Endpunkt angezeigt werden? Welche Art von Anmeldungen wird überwacht?
- Können Sie mehr Kontext oder Einblicke zu dieser Warnung geben: "Verdächtiges Verhalten durch ein Systemhilfsprogramm wurde beobachtet". 

**Mögliche Computerkompromitt**
- Können Sie antworten, warum "Unbekannter Prozess beobachtet" angezeigt wird? Diese Meldung oder Warnung wird häufig auf vielen Geräten angezeigt. Wir freuen uns über jede Eingabe, um zu verdeutlichen, ob diese Nachricht oder Warnung mit böswilligen Aktivitäten zusammenhängt.
- Können Sie dazu beitragen, eine mögliche Gefährdung auf dem folgenden System am [Datum] mit ähnlichen Verhaltensweisen wie die vorherige [Schadsoftwarename]-Schadsoftwareerkennung auf demselben System in [Monat] zu überprüfen?

**Details zur Bedrohungserkennung**
- Wir haben eine Phishing-E-Mail erkannt, die ein schädliches Word-Dokument an einen Benutzer übermittelt hat. Das schädliche Word-Dokument verursachte eine Reihe verdächtiger Ereignisse, die mehrere Microsoft Defender-Warnungen für Schadsoftware [Malwarename] auslösten. Haben Sie Informationen zu dieser Schadsoftware? Wenn ja, können Sie mir einen Link senden?
- Ich habe kürzlich einen Beitrag [Social Media-Referenz, z. B. Twitter oder Blog] über eine Bedrohung gesehen, die auf meine Branche ausgerichtet ist. Können Sie mir helfen zu verstehen, welchen Schutz Defender für Endpunkt gegen diesen Bedrohungsakteur bietet? 

**Microsoft-Bedrohungsexperten-Warnungskommunikation** 
- Kann Ihr Team für die Reaktion auf Vorfälle uns dabei helfen, die Benachrichtigung über gezielte Angriffe zu beheben, die wir erhalten haben?
- Ich habe diese Benachrichtigung über gezielte Angriffe von Microsoft-Bedrohungsexperten erhalten. Wir haben kein eigenes Team für die Reaktion auf Vorfälle. Was können wir jetzt tun und wie können wir den Vorfall eindämmen?
- Ich habe eine gezielte Angriffsbenachrichtigung von Microsoft-Bedrohungsexperten erhalten. Welche Daten können Sie uns zur Verfügung stellen, die wir an unser Team zur Behandlung von Sicherheitsvorfällen weitergeben können?

  >[!NOTE]
  >Microsoft-Bedrohungsexperten ist ein verwalteter Dienst für die Cybersicherheitssuche und kein Vorfallreaktionsdienst. Die Experten können die Untersuchung jedoch bei Bedarf nahtlos in die Dienste des Erkennungs- und Reaktionsteams (DETECTION and Response Team, DART) der Microsoft Cybersecurity Solutions Group (CSG) übertragen. Sie können sich auch für die Zusammenarbeit mit Ihrem eigenen Team zur Reaktion auf Vorfälle entscheiden, um Probleme zu beheben, die eine Reaktion auf Vorfälle erfordern. 

## <a name="scenario"></a>Szenario

### <a name="receive-a-progress-report-about-your-managed-hunting-inquiry"></a>Erhalten eines Statusberichts zu Ihrer verwalteten Suche 
Die Antwort von Microsoft-Bedrohungsexperten variiert je nach Anfrage. Sie erhalten innerhalb von zwei Tagen einen Statusbericht zu Ihrer Anfrage **eines Bedrohungsexperten,** um den Untersuchungsstatus aus den folgenden Kategorien zu kommunizieren: 
- Weitere Informationen sind erforderlich, um mit der Untersuchung fortzufahren. 
- Eine Datei oder mehrere Dateibeispiele sind erforderlich, um den technischen Kontext zu ermitteln. 
- Untersuchung erfordert mehr Zeit   
- Die ersten Informationen reichten aus, um die Untersuchung abzuschließen. 

Es ist wichtig, schnell zu reagieren, um die Untersuchung in Gang zu halten. 

## <a name="related-topic"></a>Verwandtes Thema
- [Microsoft-Bedrohungsexperten – Übersicht](microsoft-threat-experts.md)
- [Microsoft-Bedrohungsexperten in Microsoft 365 Overview](/microsoft-365/security/mtp/microsoft-threat-experts)
