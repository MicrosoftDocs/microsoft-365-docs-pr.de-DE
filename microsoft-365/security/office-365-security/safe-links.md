---
title: Sichere Links
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: overview
f1_keywords:
- "197503"
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- ZVO160
- ZXL160
- ZPP160
- ZWD160
ms.assetid: dd6a1fef-ec4a-4cf4-a25a-bb591c5811e3
description: In diesem Artikel erfahren Administratoren mehr über den Schutz sicherer Links in Defender für Office 365, um ihre Organisation vor Phishing und anderen Angriffen zu schützen, die bösartige URLs verwenden.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d42d7563b5267f805756125d1764d506f1700e13
ms.sourcegitcommit: f3d1009840513703c38bab99a6e13a3656eae5ee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/07/2021
ms.locfileid: "52793028"
---
# <a name="safe-links-in-microsoft-defender-for-office-365"></a>Sichere Links in Microsoft Defender für Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> Dieser Artikel richtet sich an Geschäftskunden, die über [Microsoft Defender für Office 365](defender-for-office-365.md) verfügen. Wenn Sie Outlook.com, Microsoft 365 Family oder Microsoft 365 Single verwenden und Informationen zu Safelinks in Outlook suchen, finden Sie informationen unter [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

Sichere Links sind ein Feature in [Defender für Office 365,](defender-for-office-365.md) das das ÜBERPRÜFEN und Umschreiben von eingehenden E-Mail-Nachrichten im E-Mail-Fluss sowie die Überprüfung von URLs und Links in E-Mail-Nachrichten und anderen Speicherorten zum Zeitpunkt des Klickens ermöglicht. Die Überprüfung sicherer Links erfolgt zusätzlich zum regulären [Antispam- und Antischadsoftwareschutz](anti-spam-and-anti-malware-protection.md) in eingehenden E-Mail-Nachrichten in Exchange Online Protection (EOP). Die Überprüfung sicherer Links kann Dazu beitragen, Ihre Organisation vor bösartigen Links zu schützen, die bei Phishing- und anderen Angriffen verwendet werden.

Der Schutz sicherer Links ist an den folgenden Speicherorten verfügbar:

- **E-Mail-Nachrichten:** Der Schutz sicherer Links für Links in E-Mail-Nachrichten wird durch Richtlinien für sichere Links gesteuert. Es gibt keine Standardrichtlinie für sichere Links. **Um den Schutz von sicheren Links in E-Mail-Nachrichten zu erhalten, müssen Sie eine oder mehrere Richtlinien** für sichere Links erstellen. Anweisungen finden Sie unter [Einrichten von Richtlinien für sichere Links in Microsoft Defender für Office 365](set-up-safe-links-policies.md).

  Weitere Informationen zum Schutz sicherer Links für E-Mail-Nachrichten finden Sie im Abschnitt ["Einstellungen für sichere Links" für E-Mail-Nachrichten](#safe-links-settings-for-email-messages) weiter unten in diesem Artikel.
  
  > [!NOTE]
  > Sichere Links funktionieren nicht für E-Mail-aktivierte öffentliche Ordner.

- **Microsoft Teams** (derzeit in TAP Preview): Der Schutz sicherer Links für Links in Teams Unterhaltungen, Gruppenchats oder von Kanälen wird ebenfalls durch Richtlinien für sichere Links gesteuert. Es gibt keine Standardrichtlinie für sichere Links. **Um den Schutz von sicheren Links in Teams zu erhalten, müssen Sie eine oder mehrere Richtlinien** für sichere Links erstellen.

  Weitere Informationen zum Schutz sicherer Links in Teams finden Sie in den [Einstellungen für sichere Links für Microsoft Teams](#safe-links-settings-for-microsoft-teams) Abschnitt weiter unten in diesem Artikel.

- **Office 365 Apps:** Der Schutz sicherer Links für Office 365 Apps ist in unterstützten Desktop-, Mobil- und Web-Apps verfügbar. Sie **konfigurieren** den Schutz für sichere Links für Office 365 Apps in der globalen Einstellung, die **sich außerhalb** der Richtlinien für sichere Links befinden. Anweisungen finden Sie unter [Konfigurieren globaler Einstellungen für Einstellungen für sichere Links in Microsoft Defender für Office 365.](configure-global-settings-for-safe-links.md)

  Der Schutz sicherer Links für Office 365 Apps wird auf alle Benutzer in der Organisation angewendet, die für Defender für Office 365 lizenziert sind, unabhängig davon, ob die Benutzer in den aktiven Richtlinien für sichere Links enthalten sind oder nicht.

  Weitere Informationen zum Schutz sicherer Links in Office 365 Apps finden Sie im Abschnitt ["Einstellungen für sichere Links" für Office 365 Apps](#safe-links-settings-for-office-365-apps) weiter unten in diesem Artikel.

Dieser Artikel enthält ausführliche Beschreibungen der folgenden Typen von Einstellungen für sichere Links:

- **Einstellungen in Richtlinien für sichere Links:** Diese Einstellungen gelten nur für die Benutzer, die in den spezifischen Richtlinien enthalten sind, und die Einstellungen können zwischen richtlinien unterschiedlich sein. Dazu zählen die folgenden Einstellungen:

  - [Einstellungen für sichere Links für E-Mail-Nachrichten](#safe-links-settings-for-email-messages)
  - [Einstellungen für sichere Links für Microsoft Teams](#safe-links-settings-for-microsoft-teams)
  - [Listen "Die folgenden URLs nicht umschreiben" in Richtlinien für sichere Links](#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)

- **Einstellungen für globale sichere Links:** Diese Einstellungen werden global konfiguriert, nicht in Richtlinien für sichere Links. Dazu zählen die folgenden Einstellungen:

  - [Einstellungen für sichere Links für Office 365 Apps](#safe-links-settings-for-office-365-apps)
  - [Liste "Blockieren der folgenden URLs" für sichere Links](#block-the-following-urls-list-for-safe-links)

In der folgenden Tabelle werden Szenarien für sichere Links in Microsoft 365 und Office 365 Organisationen beschrieben, die Defender für Office 365 enthalten (d. h. fehlende Lizenzierung ist in den Beispielen nie ein Problem).

<br>

****

|Szenario|Ergebnis|
|---|---|
|Einer ist Mitglied der Marketingabteilung. Der Schutz sicherer Links für Office 365 Apps ist in den globalen Einstellungen für sichere Links aktiviert, und es gibt eine Richtlinie für sichere Links, die für Mitglieder der Marketingabteilung gilt. Doppelklickt in einer E-Mail-Nachricht auf eine PowerPoint Präsentation und klickt dann auf eine URL in der Präsentation.|Der Hyperlink ist durch sichere Links geschützt. <p> Der Sichere Links-Schutz ist in einer Richtlinie für sichere Links enthalten, und der Schutz vor sicheren Links für Office 365 Apps ist aktiviert. <p> Weitere Informationen zu den Anforderungen für den Schutz sicherer Links in Office 365 Apps finden Sie im Abschnitt ["Einstellungen für sichere Links" für Office 365 Apps](#safe-links-settings-for-office-365-apps) weiter unten in diesem Artikel.|
|Chriss Microsoft 365 E5 Organisation hat keine Richtlinien für sichere Links konfiguriert. Chris empfängt eine E-Mail von einem externen Absender, die eine URL zu einer schädlichen Website enthält, auf die er letztendlich klickt.|Chris ist nicht durch sichere Links geschützt. <p> Ein Administrator muss mindestens eine Richtlinie für sichere Links erstellen, damit jeder schutz vor sicheren Links in eingehenden E-Mail-Nachrichten erhalten kann. Chris muss in die Bedingungen der Richtlinie einbezogen werden, um den Schutz für sichere Links zu erhalten.|
|In Pats Organisation haben keine Administratoren Richtlinien für sichere Links erstellt, aber der Schutz sicherer Links für Office 365 Apps ist aktiviert. Pat öffnet ein Word-Dokument und klickt auf eine URL in der Datei.|Pat ist nicht durch sichere Links geschützt. <p> Obwohl der Schutz sicherer Links für Office 365 Apps global aktiviert ist, ist Pat nicht in aktiven Richtlinien für sichere Links enthalten, sodass der Schutz nicht angewendet werden kann.|
|In Lees Organisation `https://tailspintoys.com` ist in der Liste **"Blockieren der folgenden URLs"** in den globalen Einstellungen für sichere Links konfiguriert. Eine Richtlinie für sichere Links, die Lee enthält, ist bereits vorhanden. Lee empfängt eine E-Mail-Nachricht, die die URL `https://tailspintoys.com/aboutus/trythispage` enthält. Lee klickt auf die URL.|Die URL wird möglicherweise automatisch für Lee blockiert. sie hängt vom URL-Eintrag in der Liste und dem verwendeten E-Mail-Client Ab. Weitere Informationen finden Sie im Abschnitt ["Blockieren der folgenden URLs" für sichere Links](#block-the-following-urls-list-for-safe-links) weiter unten in diesem Artikel.|
|Jamie und Jamie arbeiten beide für contoso.com. Vor langer Zeit haben Administratoren Richtlinien für sichere Links konfiguriert, die sowohl für Jamie als auch für Jamie gelten. Jamie sendet eine E-Mail an Schade, ohne zu wissen, dass die E-Mail eine schädliche URL enthält.|Sie ist durch sichere Links **geschützt, wenn** die für sie geltenden Richtlinie für sichere Links so konfiguriert ist, dass sie auf Nachrichten zwischen internen Empfängern angewendet wird. Weitere Informationen finden Sie im Abschnitt ["Einstellungen für sichere Links" für E-Mail-Nachrichten](#safe-links-settings-for-email-messages) weiter unten in diesem Artikel.|
|

## <a name="safe-links-settings-for-email-messages"></a>Einstellungen für sichere Links für E-Mail-Nachrichten

Sichere Links durchsucht eingehende E-Mails auf bekannte böswillige Hyperlinks. Gescannte URLs werden mithilfe des Standard-URL-Präfixes von Microsoft umgeschrieben: `https://nam01.safelinks.protection.outlook.com` . Nachdem der Link umgeschrieben wurde, wird er auf potenziell schädliche Inhalte analysiert.

Nachdem sichere Links eine URL umgeschrieben haben, bleibt die URL auch dann neu geschrieben, wenn die Nachricht *manuell* weitergeleitet oder beantwortet wird (sowohl an interne als auch an externe Empfänger). Zusätzliche Links, die der weitergeleiteten oder beantworteten Nachricht hinzugefügt werden, werden nicht umgeschrieben. Bei der *automatischen* Weiterleitung durch Posteingangsregeln oder smtp-Weiterleitung wird die URL jedoch nicht in der Nachricht umgeschrieben, die für den endgültigen Empfänger vorgesehen ist, *es sei denn,* dieser Empfänger ist auch durch sichere Links geschützt oder die URL wurde bereits in einer vorherigen Kommunikation umgeschrieben. 

Die Einstellungen in Richtlinien für sichere Links, die für E-Mail-Nachrichten gelten, werden in der folgenden Liste beschrieben:

- **Wählen Sie die Aktion für unbekannte potenziell schädliche URLs in Nachrichten** aus: Aktiviert oder deaktiviert die Überprüfung sicherer Links in E-Mail-Nachrichten. Der empfohlene Wert ist **On**. Wenn Sie diese Einstellung aktivieren, werden die folgenden Aktionen ausgeführt.

  - Die Überprüfung sicherer Links ist in Outlook (C2R) auf Windows aktiviert.
  - URLs werden umgeschrieben, und Benutzer werden über den Schutz für sichere Links weitergeleitet, wenn sie in Nachrichten auf URLs klicken.
  - Wenn darauf geklickt wird, werden URLs anhand einer Liste bekannter bösartiger URLs und der [Liste "Die folgenden URLs blockieren"](#block-the-following-urls-list-for-safe-links)überprüft.
  - URLs, die keinen gültigen Ruf haben, werden asynchron im Hintergrund detoniert.

- **Anwenden der Echtzeit-URL-Überprüfung auf verdächtige Links und Links, die auf Dateien verweisen:** Ermöglicht die Echtzeitüberprüfung von Links, einschließlich Links in E-Mail-Nachrichten, die auf herunterladbare Inhalte verweisen. Der empfohlene Wert ist aktiviert.
  - **Warten Sie, bis die URL-Überprüfung abgeschlossen ist, bevor Sie die Nachricht übermitteln:**
    - Aktiviert: Nachrichten, die URLs enthalten, werden gehalten, bis die Überprüfung abgeschlossen ist. Nachrichten werden erst übermittelt, nachdem die URLs als sicher bestätigt wurden. Dies ist der empfohlene Wert.
    - Deaktiviert: Wenn die URL-Überprüfung nicht abgeschlossen werden kann, übermitteln Sie die Nachricht trotzdem.

- **Anwenden von sicheren Links auf innerhalb der Organisation gesendete E-Mail-Nachrichten:** Aktiviert oder deaktiviert die Überprüfung sicherer Links auf Nachrichten, die zwischen internen Absendern und internen Empfängern innerhalb derselben Exchange Online Organisation gesendet werden. Der empfohlene Wert ist aktiviert.

- **Benutzerklicks nicht nachverfolgen:** Aktiviert oder deaktiviert das Speichern von Klickdaten für sichere Links für URLs, auf die in E-Mail-Nachrichten geklickt wurde. Der empfohlene Wert besteht darin, diese Einstellung nicht ausgewählt zu lassen (um Benutzerklicks nachzuverfolgen).

  Die URL-Klickverfolgung für Links in E-Mail-Nachrichten, die zwischen internen Absendern und internen Empfängern gesendet werden, wird derzeit nicht unterstützt.

- **Zulassen, dass Benutzer nicht zur ursprünglichen URL klicken:** Ermöglicht oder blockiert, dass Benutzer über die [Warnseite](#warning-pages-from-safe-links) zur ursprünglichen URL klicken. Der Empfohlene Wert ist aktiviert.

- **Anzeigen des Organisationsbrandings auf Benachrichtigungs- und Warnseiten:** Diese Option zeigt das Branding Ihrer Organisation auf Warnseiten an. Branding hilft Benutzern bei der Identifizierung legitimer Warnungen, da standardmäßige Microsoft-Warnseiten häufig von Angreifern verwendet werden. Weitere Informationen zum angepassten Branding finden Sie unter [Anpassen des Microsoft 365 Designs für Ihre Organisation.](../../admin/setup/customize-your-organization-theme.md)

- **Not rewrite the following URLs:** Leaves URLs as they are. Behält eine benutzerdefinierte Liste sicherer URLs bei, die nicht gescannt werden müssen. Die Liste ist für jede Richtlinie für sichere Links eindeutig. Weitere Informationen zur Liste "Die **folgenden URLs nicht umschreiben"** finden Sie in den [Listen "Die folgenden URLs nicht neu schreiben" im Abschnitt "Richtlinien für sichere Links"](#do-not-rewrite-the-following-urls-lists-in-safe-links-policies) weiter unten in diesem Artikel.

  Weitere Informationen zu den empfohlenen Werten für Standard- und Strict-Richtlinieneinstellungen für Richtlinien für sichere Links finden Sie unter ["Richtlinieneinstellungen für sichere Links".](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings)

- **Empfängerfilter:** Sie müssen die Empfängerbedingungen und -ausnahmen angeben, die bestimmen, für wen die Richtlinie gilt. Sie können die folgenden Eigenschaften für Bedingungen und Ausnahmen verwenden:
  - **Der Empfänger ist**
  - **Die Empfängerdomäne ist**
  - **Der Empfänger ist Mitglied von**

  Sie können eine Bedingung oder Ausnahme nur einmal verwenden, die Bedingung oder Ausnahme kann aber mehrere Werte enthalten. Bei mehreren Werten derselben Bedingung oder Ausnahme wird ODER-Logik verwendet (z. B. _\<recipient1\>_ oder _\<recipient2\>_). Bei unterschiedlichen Bedingungen oder Ausnahmen wird UND-Logik verwendet (z. B. _\<recipient1\>_ und _\<member of group 1\>_).

- **Priorität:** Wenn Sie mehrere Richtlinien erstellen, können Sie die Reihenfolge angeben, in der sie angewendet werden. Keine zwei Richtlinien können die gleiche Priorität aufweisen, und die Richtlinienverarbeitung endet, nachdem die erste Richtlinie angewendet wurde.

  Weitere Informationen über die Prioritätsreihenfolge und darüber, wie mehrere Richtlinien ausgewertet und angewendet werden, finden Sie unter [Reihenfolge und Priorität beim E-Mail-Schutz](how-policies-and-protections-are-combined.md).
  
### <a name="how-safe-links-works-in-email-messages"></a>Funktionsweise sicherer Links in E-Mail-Nachrichten

Auf hoher Ebene funktioniert der Schutz sicherer Links auf URLs in E-Mail-Nachrichten:

1. Alle E-Mails werden über EOP gesendet, wobei internetprotokoll (IP) und Umschlagfilter, signaturbasierter Schutz vor Schadsoftware, Antispam- und Antischadsoftwarefilter vor der Zustellung der Nachricht an das Postfach des Empfängers gesendet werden.

2. Der Benutzer öffnet die Nachricht in ihrem Postfach und klickt auf eine URL in der Nachricht.

3. Sichere Links überprüfen sofort die URL, bevor Sie die Website öffnen:

   - Wenn die URL in der Liste **der folgenden URLs blockieren** enthalten ist, wird eine Warnung zu [blockierten URLs](#blocked-url-warning) geöffnet.

   - Wenn die URL auf eine Website verweist, die als bösartig eingestuft wurde, wird eine Warnungsseite für [bösartige Websites](#malicious-website-warning) (oder eine andere Warnseite) geöffnet.

   - Wenn die URL auf eine herunterladbare Datei zeigt und die **Echtzeit-URL-Überprüfung auf verdächtige Links und Links, die auf Dateien verweisen,** in der Richtlinie aktiviert ist, die für den Benutzer gilt, wird die herunterladbare Datei überprüft.

   - Wenn die URL als sicher eingestuft wird, wird die Website geöffnet.

## <a name="safe-links-settings-for-microsoft-teams"></a>Einstellungen für sichere Links für Microsoft Teams

> [!IMPORTANT]
> Seit März 2020 befindet sich dieses Feature in der Vorschau und ist nur für Mitglieder des Microsoft Teams Technology Adoption Program (TAP) verfügbar. Informationen zum Veröffentlichungszeitplan finden Sie in der [Microsoft 365 Roadmap.](https://www.microsoft.com/microsoft-365/roadmap?rtc=1&filters=&searchterms=Safe%2CLinks%2CProtection%2Cfor%2CMicrosoft%2CTeams)

Sie aktivieren oder deaktivieren den Schutz für sichere Links für Microsoft Teams in Richtlinien für sichere Links. Insbesondere verwenden Sie **die Aktion auswählen für unbekannte oder potenziell schädliche URLs innerhalb Microsoft Teams** Einstellung. Der empfohlene Wert ist **On**.

Die folgenden Einstellungen in Richtlinien für sichere Links, die für Links in E-Mail-Nachrichten gelten, gelten auch für Links in Teams:

- **Anwenden der Echtzeit-URL-Überprüfung auf verdächtige Links und Links, die auf Dateien verweisen**
- **Benutzerklicks nicht nachverfolgen**
- **Benutzern nicht gestatten, zur ursprünglichen URL zu klicken**

Diese Einstellungen werden zuvor in den [Einstellungen für sichere Links für E-Mail-Nachrichten](#safe-links-settings-for-email-messages)erläutert.

Nachdem Sie den Schutz für sichere Links für Microsoft Teams aktiviert haben, werden URLs in Teams anhand einer Liste bekannter bösartiger Links überprüft, wenn der geschützte Benutzer auf den Link klickt (Schutz zum Zeitpunkt des Klickens). URLs werden nicht umgeschrieben. Wenn ein Link als bösartig eingestuft wird, haben Benutzer die folgenden Erfahrungen:

- Wenn auf den Link in einer Teams Unterhaltung, einem Gruppenchat oder von Kanälen geklickt wurde, wird die Warnseite wie im folgenden Screenshot dargestellt im Standardwebbrowser angezeigt.
- Wenn auf der angehefteten Registerkarte auf den Link geklickt wurde, wird die Warnseite auf der Teams-Schnittstelle auf dieser Registerkarte angezeigt. Die Option zum Öffnen des Links in einem Webbrowser ist aus Sicherheitsgründen deaktiviert.
- Je nachdem, wie die Einstellung "Benutzer nicht bis **zur ursprünglichen URL durchklicken"** in der Richtlinie konfiguriert ist, kann der Benutzer auf die ursprüngliche URL klicken (**Fahren Sie trotzdem (nicht empfohlen)** im Screenshot fort). Es wird empfohlen, dass Sie die Einstellung **"Benutzer dürfen nicht bis zur ursprünglichen URL-Einstellung klicken"** aktivieren, damit Benutzer nicht auf die ursprüngliche URL klicken können.

Wenn der Benutzer, der den Link gesendet hat, nicht in einer Richtlinie für sichere Links enthalten ist, in der Teams Schutz aktiviert ist, kann der Benutzer auf dem Computer oder Gerät auf die ursprüngliche URL klicken.

![Eine sichere Links für Teams Seite, die einen bösartigen Link meldet.](../../media/tp-safe-links-for-teams-malicious.png)

Durch Klicken auf die Schaltfläche **"Zurück"** auf der Warnseite wird der Benutzer an den ursprünglichen Kontext- oder URL-Speicherort zurückgegeben. Wenn Sie jedoch erneut auf den ursprünglichen Link klicken, wird die URL durch sichere Links erneut scannt, sodass die Warnseite erneut angezeigt wird.

### <a name="how-safe-links-works-in-teams"></a>Funktionsweise sicherer Links in Teams

Auf hoher Ebene funktioniert der Schutz sicherer Links für URLs in Microsoft Teams:

1. Ein Benutzer startet die Teams-App.

2. Microsoft 365 überprüft, ob die Organisation des Benutzers Microsoft Defender für Office 365 enthält und ob der Benutzer in einer aktiven Richtlinie für sichere Links enthalten ist, in der der Schutz für Microsoft Teams aktiviert ist.

3. URLs werden zum Zeitpunkt des Klickens für den Benutzer in Chats, Gruppenchats, Kanälen und Registerkarten überprüft.

## <a name="safe-links-settings-for-office-365-apps"></a>Einstellungen für sichere Links für Office 365 Apps

Schutz vor sicheren Links für Office 365 Apps überprüft Links in Office Dokumenten, keine Links in E-Mail-Nachrichten (er kann jedoch Links in angefügten Office Dokumenten in E-Mail-Nachrichten überprüfen, nachdem das Dokument geöffnet wurde).

Der Schutz sicherer Links für Office 365 Apps hat die folgenden Clientanforderungen:

- Microsoft 365 Apps oder Microsoft 365 Business Premium.
  - Aktuelle Versionen von Word, Excel und PowerPoint auf Windows, Mac oder in einem Webbrowser.
  - Office Apps auf iOS- oder Android-Geräten.
  - Visio auf Windows.
  - OneNote in einem Webbrowser.

- Office 365 Apps sind für die Verwendung der modernen Authentifizierung konfiguriert. Weitere Informationen finden Sie unter ["Funktionsweise der modernen Authentifizierung für Office 2013-, Office 2016- und Office 2019-Client-Apps".](../../enterprise/modern-auth-for-office-2013-and-2016.md)

- Benutzer sind mit ihren Geschäfts-, Schul- oder Unikonten angemeldet. Weitere Informationen finden Sie unter [Anmelden bei Office](https://support.microsoft.com/office/b9582171-fd1f-4284-9846-bdd72bb28426).

Sie konfigurieren den Schutz sicherer Links für Office 365 Apps in den globalen Einstellungen für sichere Links und nicht in den Richtlinien für sichere Links. Der Schutz wird auf alle Benutzer in der Organisation angewendet, die für Defender für Office 365 lizenziert sind, unabhängig davon, ob die Benutzer in den aktiven Richtlinien für sichere Links enthalten sind oder nicht.

Die folgenden Einstellungen für sichere Links sind für Office 365 Apps verfügbar:

- **Office 365 Anwendungen:** Aktiviert oder deaktiviert die Überprüfung sicherer Links in unterstützten Office 365-Apps. Der Standardwert und der empfohlene Wert ist **"On".**

- **Verfolgen Sie nicht, wenn Benutzer auf "Sichere Links" klicken:** Aktiviert oder deaktiviert das Speichern von Klickdaten für sichere Links für URLs, auf die in den Desktopversionen Word, Excel, PowerPoint und Visio geklickt wurde. Der empfohlene Wert ist **"Aus",** was bedeutet, dass Benutzerklicks nachverfolgt werden.

- **Benutzer dürfen nicht durch sichere Links zur ursprünglichen URL klicken:** Ermöglicht oder blockiert, dass Benutzer in [den](#warning-pages-from-safe-links) Desktopversionen Word, Excel, PowerPoint und Visio auf die ursprüngliche URL klicken. Der Standardwert und der empfohlene Wert ist **"On".**

Informationen zum Konfigurieren der Einstellungen für sichere Links für Office 365 Apps finden Sie unter Konfigurieren des [Schutzes für sichere Links für Office 365 Apps.](configure-global-settings-for-safe-links.md#configure-safe-links-protection-for-office-365-apps-in-the-security-center)

Weitere Informationen zu den empfohlenen Werten für Standard- und Strict-Richtlinieneinstellungen finden Sie unter ["Globale Einstellungen für sichere Links".](recommended-settings-for-eop-and-office365.md#global-settings-for-safe-links)

### <a name="how-safe-links-works-in-office-365-apps"></a>Funktionsweise sicherer Links in Office 365-Apps

Auf hoher Ebene funktioniert der Schutz sicherer Links für URLs in Office 365-Apps. Die unterstützten Office 365 Apps werden im vorherigen Abschnitt beschrieben.

1. Ein Benutzer meldet sich mit einem Geschäfts-, Schul- oder Unikonto in einer Organisation an, das Microsoft 365 Apps oder Microsoft 365 Business Premium enthält.

2. Der Benutzer öffnet ein Office Dokument in einem unterstützten Office-App und klickt auf einen Link.

3. Sichere Links überprüfen sofort die URL, bevor Sie die Zielwebsite öffnen:

   - Wenn die URL in der Liste enthalten ist, die die Überprüfung sicherer Links überspringt (die Liste **der folgenden URLs blockieren),** wird eine [Warnseite für blockierte URLs](#blocked-url-warning) geöffnet.

   - Wenn die URL auf eine Website verweist, die als bösartig eingestuft wurde, wird eine Warnungsseite für [bösartige Websites](#malicious-website-warning) (oder eine andere Warnseite) geöffnet.

   - Wenn die URL auf eine herunterladbare Datei verweist und die richtlinie für sichere Links, die für den Benutzer gilt, so konfiguriert ist, dass Links zu herunterladbaren Inhalten gescannt werden (**Anwenden der Echtzeit-URL-Überprüfung auf verdächtige Links und Links, die auf Dateien verweisen),** wird die herunterladbare Datei überprüft.

   - Wenn die URL als sicher gilt, wird der Benutzer zur Website weitergeleitet.

   - Wenn die Überprüfung sicherer Links nicht abgeschlossen werden kann, wird der Schutz sicherer Links nicht ausgelöst. In Office Desktopclients wird der Benutzer gewarnt, bevor er zur Zielwebsite wechselt.

> [!NOTE]
> Es kann zu Beginn jeder Sitzung mehrere Sekunden dauern, um zu überprüfen, ob der Benutzer sichere Links für Office aktiviert hat.

## <a name="block-the-following-urls-list-for-safe-links"></a>Liste "Blockieren der folgenden URLs" für sichere Links

The **Block the following URLs** list defines the links that are always blocked by Safe Links scanning in the following locations:

- E-Mail-Nachrichten.
- Dokumente in Office 365 Apps in Windows und Mac.
- Dokumente in Office für iOS und Android.

Wenn ein Benutzer in einer aktiven Richtlinie für sichere Links auf einen blockierten Link in einer unterstützten App klickt, wird er zur Warnseite für [blockierte URL](#blocked-url-warning) weitergeleitet.

Sie konfigurieren die Liste der URLs in den globalen Einstellungen für sichere Links. Anweisungen finden Sie unter [Konfigurieren der Liste "Blockieren der folgenden URLs".](configure-global-settings-for-safe-links.md#configure-the-block-the-following-urls-list-in-the-security-center)

**Hinweise**:

- Eine wirklich universelle Liste der URLs, die überall blockiert sind, finden Sie unter [Verwalten der Mandanten-Zulassungs-/Sperrliste.](tenant-allow-block-list.md)
- Grenzwerte für die Liste **der folgenden URLs blockieren:**
  - Die maximale Anzahl von Einträgen beträgt 500.
  - Die maximale Länge eines Eintrags beträgt 128 Zeichen.
  - Alle Einträge dürfen 10.000 Zeichen nicht überschreiten.
- Schließen Sie keinen Schrägstrich ( `/` ) am Ende der URL ein. Verwenden Sie z. B. `https://www.contoso.com` nicht `https://www.contoso.com/` .
- Eine Nur-Domänen-URL (z. `contoso.com` B. oder `tailspintoys.com` ) blockiert jede URL, die die Domäne enthält.
- Sie können eine Unterdomäne blockieren, ohne die vollständige Domäne zu blockieren. Blockiert beispielsweise `toys.contoso.com*` jede URL, die die Unterdomäne enthält, aber keine URLs, die die vollständige Domäne `contoso.com` enthalten.
- Sie können bis zu drei Platzhalter ( `*` ) pro URL-Eintrag einschließen.

### <a name="entry-syntax-for-the-block-the-following-urls-list"></a>Eintragssyntax für die Liste "Blockieren der folgenden URLs"

Beispiele für die Werte, die Sie eingeben können, und deren Ergebnisse werden in der folgenden Tabelle beschrieben:

<br>

****

|Wert|Ergebnis|
|---|---|
|`contoso.com` <p> oder <p> `*contoso.com*`|Blockiert die Domäne, Unterdomänen und Pfade. Beispielsweise `https://www.contoso.com` , `https://sub.contoso.com` und `https://contoso.com/abc` werden blockiert.|
|`https://contoso.com/a`|Blockiert, `https://contoso.com/a` aber keine zusätzlichen Unterpfade wie `https://contoso.com/a/b` .|
|`https://contoso.com/a*`|Blöcke `https://contoso.com/a` und zusätzliche Unterpfade wie `https://contoso.com/a/b` .|
|`https://toys.contoso.com*`|Blockiert eine Unterdomäne ( `toys` in diesem Beispiel), lässt aber Klicks auf andere Domänen-URLs zu (z. B. `https://contoso.com` oder `https://home.contoso.com` ).|
|

## <a name="do-not-rewrite-the-following-urls-lists-in-safe-links-policies"></a>Listen "Die folgenden URLs nicht umschreiben" in Richtlinien für sichere Links

> [!NOTE]
> Wenn Ihre Organisation Richtlinien für sichere Links verwendet, werden **die folgenden URLs-Listen nicht neu geschrieben.** Dies ist die einzige unterstützte Methode für Phishingtests von Drittanbietern.

Jede Richtlinie für sichere Links enthält eine Liste der **folgenden URLs nicht neu** schreiben, die Sie verwenden können, um URLs anzugeben, die nicht durch die Überprüfung sicherer Links umgeschrieben werden. Anders ausgedrückt: Die Liste ermöglicht Benutzern, die in der Richtlinie enthalten sind, auf die angegebenen URLs zuzugreifen, die andernfalls durch sichere Links blockiert würden. Sie können verschiedene Listen in verschiedenen Richtlinien für sichere Links konfigurieren. Die Richtlinienverarbeitung wird beendet, nachdem die erste Richtlinie (wahrscheinlich die höchste Priorität) auf den Benutzer angewendet wurde. Daher wird auf einen Benutzer, der in mehreren aktiven Richtlinien für sichere Links enthalten ist, nur ein Benutzer angewendet, **der die folgende URLs-Liste nicht neu schreibt.**

Informationen zum Hinzufügen von Einträgen zur Liste in neuen oder vorhandenen Richtlinien für sichere Links finden Sie unter [Erstellen von Richtlinien für sichere Links](set-up-safe-links-policies.md#use-the-security--compliance-center-to-create-safe-links-policies) oder Ändern von Richtlinien für sichere [Links.](set-up-safe-links-policies.md#use-the-security--compliance-center-to-modify-safe-links-policies)

**Hinweise**:

- Die folgenden Clients erkennen nicht, dass **die folgenden URLs-Listen** in Richtlinien für sichere Links nicht neu geschrieben werden. Benutzer, die in den Richtlinien enthalten sind, können basierend auf den Ergebnissen der Überprüfung sicherer Links in diesen Clients am Zugriff auf die URLs gehindert werden:
  - Microsoft Teams
  - Office Web-Apps

  Eine wirklich universelle Liste der URLs, die überall zulässig sind, finden Sie unter [Verwalten der Mandanten-Zulassungs-/Sperrliste.](tenant-allow-block-list.md)

- Erwägen Sie, häufig verwendete interne URLs zur Liste hinzuzufügen, um die Benutzererfahrung zu verbessern. Wenn Sie beispielsweise über lokale Dienste wie Skype for Business oder SharePoint verfügen, können Sie diese URLs hinzufügen, um sie von der Überprüfung auszuschließen.
- Wenn Sie **die folgenden URLs-Einträge** in den Richtlinien für sichere Links nicht neu geschrieben haben, überprüfen Sie die Listen, und fügen Sie nach Bedarf Platzhalter hinzu. Ihre Liste weist beispielsweise einen Eintrag wie `https://contoso.com/a` auf, und Sie entscheiden sich später, Unterpfade wie `https://contoso.com/a/b` . Anstatt einen neuen Eintrag hinzuzufügen, fügen Sie dem vorhandenen Eintrag einen Platzhalter hinzu, damit er so `https://contoso.com/a/*` wird.
- Sie können bis zu drei Platzhalter ( `*` ) pro URL-Eintrag einschließen. Platzhalter enthalten explizit Präfixe oder Unterdomänen. Beispielsweise ist der Eintrag `contoso.com` nicht identisch mit , da Personen `*.contoso.com/*` `*.contoso.com/*` Unterdomänen und Pfade in der angegebenen Domäne besuchen können.
- Wenn eine URL die automatische Umleitung für HTTP zu HTTPS verwendet (z. B. 302-Umleitung `http://www.contoso.com` zu ), und Sie `https://www.contoso.com` versuchen, sowohl HTTP- als auch HTTPS-Einträge für dieselbe URL in die Liste einzugeben, werden Sie feststellen, dass der zweite URL-Eintrag den ersten URL-Eintrag ersetzt. Dieses Verhalten tritt nicht auf, wenn die HTTP- und HTTPS-Versionen der URL vollständig voneinander getrennt sind.

### <a name="entry-syntax-for-the-do-not-rewrite-the-following-urls-list"></a>Eintragssyntax für die Liste "Die folgenden URLs nicht umschreiben"

Beispiele für die Werte, die Sie eingeben können, und deren Ergebnisse werden in der folgenden Tabelle beschrieben:

<br>

****

|Wert|Ergebnis|
|---|---|
|`contoso.com`|Ermöglicht den Zugriff auf `https://contoso.com` Unterdomänen oder Pfade, aber nicht.|
|`*.contoso.com/*`|Ermöglicht den Zugriff auf eine Domäne, Unterdomänen und Pfade (z. B. `https://www.contoso.com` , `https://www.contoso.com` oder `https://maps.contoso.com` `https://www.contoso.com/a` ). <p> Dieser Eintrag ist grundsätzlich besser als `*contoso.com*` , da er potenziell betrügerische Websites wie `https://www.falsecontoso.com` oder `https://www.false.contoso.completelyfalse.com`|
|`https://contoso.com/a`|Ermöglicht den Zugriff auf `https://contoso.com/a` , aber keine Unterpfade wie `https://contoso.com/a/b`|
|`https://contoso.com/a/*`|Ermöglicht den Zugriff auf `https://contoso.com/a` und Unterpfade wie `https://contoso.com/a/b`|
|

## <a name="warning-pages-from-safe-links"></a>Warnseiten von sicheren Links

Dieser Abschnitt enthält Beispiele für die verschiedenen Warnseiten, die durch den Schutz sicherer Links ausgelöst werden, wenn Sie auf eine URL klicken.

Beachten Sie, dass mehrere Warnseiten aktualisiert wurden. Wenn die aktualisierten Seiten noch nicht angezeigt werden, werden Sie dies in Kürze tun. Die aktualisierten Seiten enthalten ein neues Farbschema, weitere Details und die Möglichkeit, trotz der gegebenen Warnung und Empfehlungen zu einer Website zu gelangen.

### <a name="scan-in-progress-notification"></a>Benachrichtigung zur Überprüfung in Bearbeitung

Die angeklickte URL wird von sicheren Links gescannt. Möglicherweise müssen Sie einige Sekunden warten, bevor Sie den Link erneut versuchen.

![Benachrichtigung "Der Link wird gescannt"](../../media/ee8dd5ed-6b91-4248-b054-12b719e8d0ed.png)

Die ursprüngliche Benachrichtigungsseite sieht wie folgt aus:

![Ursprüngliche Benachrichtigung "Der Link wird gescannt"](../../media/04368763-763f-43d6-94a4-a48291d36893.png)

### <a name="suspicious-message-warning"></a>Warnung bei verdächtigen Nachrichten

Die angeklickte URL befand sich in einer E-Mail-Nachricht, die anderen verdächtigen Nachrichten ähnelt. Es wird empfohlen, die E-Mail-Nachricht zu überprüfen, bevor Sie mit der Website fortfahren.

![Warnung "Ein Link wurde aus einer verdächtigen Nachricht angeklickt"](../../media/33f57923-23e3-4b0f-838b-6ad589ba897b.png)

### <a name="phishing-attempt-warning"></a>Warnung bei Phishingversuchen

Die angeklickte URL befand sich in einer E-Mail-Nachricht, die als Phishingangriff identifiziert wurde. Daher werden alle URLs in der E-Mail-Nachricht blockiert. Es wird empfohlen, nicht mit der Website fortzufahren.

![Warnung "Der Link wurde aus einer Phishingnachricht angeklickt"](../../media/6e544a28-0604-4821-aba6-d5a57bb917e5.png)

### <a name="malicious-website-warning"></a>Warnung vor bösartigen Websites

Die angeklickte URL verweist auf eine Website, die als bösartig identifiziert wurde. Es wird empfohlen, nicht mit der Website fortzufahren.

![Warnung "Diese Website wird als bösartig klassifiziert"](../../media/058883c8-23f0-4672-9c1c-66b084796177.png)

Die ursprüngliche Warnseite sieht wie folgt aus:

![Ursprüngliche Warnung "Diese Website wurde als bösartig klassifiziert"](../../media/b9efda09-6dd8-46ef-82cb-56e4d538b8f5.png)

### <a name="blocked-url-warning"></a>Warnung zu blockierten URLs

Die angeklickte URL wurde von einem Administrator in Ihrer Organisation manuell blockiert (die Liste **der folgenden URLs** in den globalen Einstellungen für sichere Links blockieren). Der Link wurde nicht von sicheren Links gescannt, da er manuell blockiert wurde.

Es gibt mehrere Gründe, warum ein Administrator bestimmte URLs manuell blockieren würde. Wenn Sie der Meinung sind, dass die Website nicht blockiert werden sollte, wenden Sie sich an Ihren Administrator.

![Warnung "Diese Website wurde von Ihrem Administrator blockiert"](../../media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)

Die ursprüngliche Warnseite sieht wie folgt aus:

![Ursprüngliche Warnung "Diese Website wurde gemäß der URL-Richtlinie Ihrer Organisation blockiert"](../../media/3d6ba028-30bf-45fc-958e-d3aad3defc83.png)

### <a name="error-warning"></a>Fehlerwarnung

Es ist ein Fehler aufgetreten, und die URL kann nicht geöffnet werden.

![Warnung "Die Seite, auf die Sie zugreifen möchten, kann nicht geladen werden"](../../media/2f7465a4-1cf4-4c1c-b7d4-3c07e4b795b4.png)

Die ursprüngliche Warnseite sieht wie folgt aus:

![Ursprüngliche Warnung "Diese Webseite konnte nicht geladen werden"](../../media/9aaa4383-2f23-48be-bdaa-8efbcb2acc70.png)
