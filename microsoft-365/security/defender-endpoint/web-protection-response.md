---
title: Reagieren auf Webbedrohungen in Microsoft Defender for Endpoint
description: Reagieren Sie auf Warnungen im Zusammenhang mit schädlichen und unerwünschten Websites. Verstehen, wie der Schutz von Webbedrohungen Endbenutzer über ihre Webbrowser und Windows-Benachrichtigungen informiert
keywords: Webschutz, Webbedrohungenschutz, Webbrowsing, Warnungen, Antwort, Sicherheit, Phishing, Schadsoftware, Exploit, Websites, Netzwerkschutz, Edge, Internet Explorer, Chrome, Firefox, Webbrowser, Benachrichtigungen, Endbenutzer, Windows-Benachrichtigungen, Sperrseite,
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 110b379863b4c6e23c947c56faf831e136231237
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51688477"
---
# <a name="respond-to-web-threats"></a>Reagieren auf Internetbedrohungen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

Mit web protection in Microsoft Defender for Endpoint können Sie Warnungen im Zusammenhang mit schädlichen Websites und Websites in Ihrer benutzerdefinierten Indikatorliste effizient untersuchen und darauf reagieren.

## <a name="view-web-threat-alerts"></a>Anzeigen von Webbedrohungswarnungen
Microsoft Defender for Endpoint generiert die folgenden [Warnungen für](manage-alerts.md) böswillige oder verdächtige Webaktivitäten:
- **Verdächtige** Verbindung, die vom Netzwerkschutz blockiert wird – diese Warnung wird generiert, wenn der Versuch, auf eine schädliche Website oder eine Website in Ihrer benutzerdefinierten Indikatorliste zu zugreifen, durch den Netzwerkschutz im  *Sperrmodus beendet* wird.
- **Verdächtige** Verbindung, die vom Netzwerkschutz erkannt wird – diese Warnung wird generiert, wenn ein Versuch, auf eine schädliche Website oder eine Website in Ihrer benutzerdefinierten Indikatorliste zu zugreifen, vom Netzwerkschutz im Überwachungsmodus erkannt *wird.*

Jede Warnung enthält die folgenden Informationen: 
- Gerät, das versucht hat, auf die blockierte Website zu zugreifen
- Anwendung oder Programm zum Senden der Webanforderung
- Bösartige URL oder URL in der Liste der benutzerdefinierten Indikatoren
- Empfohlene Aktionen für Responder

![Abbildung einer Warnung im Zusammenhang mit dem Schutz von Webbedrohungen](images/wtp-alert.png)

>[!Note]
>Um das Volumen der Warnungen zu reduzieren, konsolidiert Microsoft Defender for Endpoint die Erkennung von Webbedrohungen für dieselbe Domäne auf demselben Gerät jeden Tag in einer einzelnen Warnung. Es wird nur eine Warnung generiert und in den [Webschutzbericht gezählt.](web-protection-monitoring.md)

## <a name="inspect-website-details"></a>Überprüfen von Websitedetails
Sie können tiefer gehen, indem Sie die URL oder Domäne der Website in der Warnung auswählen. Dadurch wird eine Seite zu dieser bestimmten URL oder Domäne mit verschiedenen Informationen geöffnet, einschließlich:
- Geräte, die versucht haben, auf die Website zu zugreifen
- Vorfälle und Warnungen im Zusammenhang mit der Website
- Wie häufig die Website in Ereignissen in Ihrer Organisation gesehen wurde

    ![Abbildung der Seite "Domänen- oder URL-Entitätsdetails"](images/wtp-website-details.png)

[Weitere Informationen zu URL- oder Domänenentitätsseiten](investigate-domain.md)

## <a name="inspect-the-device"></a>Überprüfen des Geräts
Sie können auch das Gerät überprüfen, das versucht hat, auf eine blockierte URL zu zugreifen. Wenn Sie den Namen des Geräts auf der Warnungsseite auswählen, wird eine Seite mit umfassenden Informationen zum Gerät geöffnet.

[Weitere Informationen zu Geräteentitätsseiten](investigate-machines.md)

## <a name="web-browser-and-windows-notifications-for-end-users"></a>Webbrowser- und Windows-Benachrichtigungen für Endbenutzer

Mit dem Webschutz in Microsoft Defender for Endpoint werden Endbenutzer daran gehindert, schädliche oder unerwünschte Websites mit Microsoft Edge oder anderen Browsern zu besuchen. Da das Blockieren durch den [Netzwerkschutz ausgeführt wird,](network-protection.md)wird ein allgemeiner Fehler vom Webbrowser angezeigt. Außerdem wird eine Benachrichtigung von Windows angezeigt.

![Abbildung von Microsoft Edge mit einem 403-Fehler und der Windows-Benachrichtigungswebbedrohung, die ](images/wtp-browser-blocking-page.png)
 *auf Microsoft Edge blockiert ist*

![Abbildung des Chrome-Webbrowsers, der eine Warnung für sichere Verbindungen und die Windows-Benachrichtigungswebbedrohung zeigt, die ](images/wtp-chrome-browser-blocking-page.png)
 *in Chrome blockiert ist*

## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über Internetschutz](web-protection-overview.md)
- [Internet-Inhaltsfilterung](web-content-filtering.md)
- [Internet-Bedrohungsschutz](web-threat-protection.md)
- [Überwachen der Websicherheit](web-protection-monitoring.md)
