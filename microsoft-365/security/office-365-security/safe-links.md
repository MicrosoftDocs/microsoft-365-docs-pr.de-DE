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
description: In diesem Artikel erfahren Administratoren mehr über den Schutz sicherer Links in Defender for Office 365, um ihre Organisation vor Phishing und anderen Angriffen zu schützen, die bösartige URLs verwenden.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 675de13410ac98e18a8b72125c2226d2c9c62821
ms.sourcegitcommit: 4bcac4cb4f9399ebbd7c8cff0abb4d6ecedb731e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/28/2021
ms.locfileid: "52698988"
---
# <a name="safe-links-in-microsoft-defender-for-office-365"></a>Sichere Links in Microsoft Defender für Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> Dieser Artikel richtet sich an Geschäftskunden, die über [Microsoft Defender für Office 365](defender-for-office-365.md) verfügen. Wenn Sie Outlook.com, Microsoft 365 Family oder Microsoft 365 Single verwenden und Informationen zu Safelinks in Outlook suchen, lesen Sie [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

Sichere Links ist ein Feature in [Defender for Office 365,](defender-for-office-365.md) das die URL-Überprüfung und das Neuschreiben eingehender E-Mail-Nachrichten im Nachrichtenfluss sowie die Überprüfung von URLs und Links in E-Mail-Nachrichten und anderen Speicherorten zum Zeitpunkt des Klicks ermöglicht. Die Überprüfung sicherer Links erfolgt zusätzlich zum regulären Antispam- und [Anti-Malware-Schutz in eingehenden E-Mail-Nachrichten](anti-spam-and-anti-malware-protection.md) in Exchange Online Protection (EOP). Die Überprüfung sicherer Links kann Ihre Organisation vor bösartigen Links schützen, die bei Phishing und anderen Angriffen verwendet werden.

Der Schutz sicherer Links ist an den folgenden Speicherorten verfügbar:

- **E-Mail-Nachrichten:** Der Schutz sicherer Links für Links in E-Mail-Nachrichten wird durch Richtlinien für sichere Links gesteuert. Es gibt keine Standardmäßige Richtlinie für sichere Links. Um den Schutz sicherer Links in E-Mail-Nachrichten zu erhalten, müssen Sie eine oder mehrere Richtlinien für sichere **Links erstellen.** Anweisungen finden Sie unter [Set up Safe Links policies in Microsoft Defender for Office 365](set-up-safe-links-policies.md).

  Weitere Informationen zum Schutz sicherer Links für [](#safe-links-settings-for-email-messages) E-Mail-Nachrichten finden Sie im Abschnitt Einstellungen für sichere Links für E-Mail-Nachrichten weiter unten in diesem Artikel.
  
  > [!NOTE]
  > Sichere Links funktionieren nicht für E-Mail-aktivierte öffentliche Ordner.

- **Microsoft Teams** (derzeit in der TAP-Vorschau): Der Schutz sicherer Links für Links in Teams Unterhaltungen, Gruppenchats oder kanälen wird auch durch Richtlinien für sichere Links gesteuert. Es gibt keine Standardrichtlinie für sichere Links. Um den Schutz sicherer Links in Teams zu erhalten, müssen Sie eine oder mehrere Richtlinien für sichere Links **erstellen.**

  Weitere Informationen zum Schutz sicherer Links in Teams finden Sie im Abschnitt Safe [Links settings for Microsoft Teams](#safe-links-settings-for-microsoft-teams) weiter unten in diesem Artikel.

- **Office 365:** Schutz für sichere Links für Office 365 ist in unterstützten Desktop-, Mobile- und Web-Apps verfügbar. Sie **konfigurieren den** Schutz sicherer Links für Office 365 Apps in der globalen Einstellung, die sich **außerhalb** von Richtlinien für sichere Links befinden. Anweisungen finden Sie unter [Configure global settings for Safe Links settings in Microsoft Defender for Office 365](configure-global-settings-for-safe-links.md).

  Der Schutz für sichere Links für Office 365-Apps wird auf alle Benutzer in der Organisation angewendet, die für Defender für Office 365 lizenziert sind, unabhängig davon, ob die Benutzer in aktiven Richtlinien für sichere Links enthalten sind oder nicht.

  Weitere Informationen zum Schutz sicherer Links in Office 365 apps finden Sie im Abschnitt Einstellungen für sichere Links für [Office 365](#safe-links-settings-for-office-365-apps) Apps weiter unten in diesem Artikel.

Dieser Artikel enthält detaillierte Beschreibungen der folgenden Arten von Einstellungen für sichere Links:

- **Einstellungen in Richtlinien** für sichere Links: Diese Einstellungen gelten nur für die Benutzer, die in den spezifischen Richtlinien enthalten sind, und die Einstellungen können zwischen den Richtlinien unterschiedlich sein. Dazu zählen die folgenden Einstellungen:

  - [Einstellungen für sichere Links für E-Mail-Nachrichten](#safe-links-settings-for-email-messages)
  - [Einstellungen für sichere Links für Microsoft Teams](#safe-links-settings-for-microsoft-teams)
  - ["Die folgenden URLs nicht umschreiben" in Richtlinien für sichere Links](#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)

- **Einstellungen für globale sichere** Links: Diese Einstellungen sind global konfiguriert, nicht in Richtlinien für sichere Links. Dazu zählen die folgenden Einstellungen:

  - [Einstellungen für sichere Links für Office 365 Apps](#safe-links-settings-for-office-365-apps)
  - [Liste "Blockieren der folgenden URLs" für sichere Links](#block-the-following-urls-list-for-safe-links)

In der folgenden Tabelle werden Szenarien für sichere Links in Microsoft 365- und Office 365-Organisationen beschrieben, zu denen Defender für Office 365 gehört (mit anderen Worten: Fehlende Lizenzierung ist in den Beispielen nie ein Problem).

<br>

****

|Szenario|Ergebnis|
|---|---|
|Er ist Mitglied der Marketingabteilung. Der Schutz sicherer Links für Office 365 apps ist in den globalen Einstellungen für sichere Links aktiviert, und es gibt eine Richtlinie für sichere Links, die für Mitglieder der Marketingabteilung gilt. In einer E-Mail PowerPoint öffnet Er eine Präsentation und klickt dann auf eine URL in der Präsentation.|"Jean" ist durch sichere Links geschützt. <p> "Jean" ist in einer Richtlinie für sichere Links enthalten, und der Schutz für sichere Links für Office 365 apps ist aktiviert. <p> Weitere Informationen zu den Anforderungen für den Schutz sicherer Links in Office 365 finden Sie im Abschnitt Einstellungen für sichere Links für [Office 365 Apps](#safe-links-settings-for-office-365-apps) weiter unten in diesem Artikel.|
|Chris' organisation Microsoft 365 E5 hat keine Richtlinien für sichere Links konfiguriert. Chris empfängt eine E-Mail von einem externen Absender, der eine URL zu einer schädlichen Website enthält, auf die er schließlich klickt.|Chris ist nicht durch sichere Links geschützt. <p> Ein Administrator muss mindestens eine Richtlinie für sichere Links erstellen, damit jeder benutzer den Schutz für sichere Links in eingehenden E-Mail-Nachrichten erhalten kann. Chris muss in die Bedingungen der Richtlinie einbezogen werden, um schutz vor sicheren Links zu erhalten.|
|In Pats Organisation haben keine Administratoren Richtlinien für sichere Links erstellt, aber der Schutz sicherer Links für Office 365 apps ist aktiviert. Pat öffnet ein Word-Dokument und klickt auf eine URL in der Datei.|Pat ist nicht durch sichere Links geschützt. <p> Obwohl der Schutz sicherer Links für Office 365 Apps global aktiviert ist, ist Pat nicht in aktiven Richtlinien für sichere Links enthalten, sodass der Schutz nicht angewendet werden kann.|
|In Lees Organisation wird in der Liste Blockieren der folgenden URLs in den globalen Einstellungen für `https://tailspintoys.com` sichere Links konfiguriert.  Eine Richtlinie für sichere Links, die Lee enthält, ist bereits vorhanden. Lee empfängt eine E-Mail-Nachricht, die die URL `https://tailspintoys.com/aboutus/trythispage` enthält. Lee klickt auf die URL.|Die URL wird möglicherweise automatisch für Lee blockiert. dies hängt vom URL-Eintrag in der Liste und dem verwendeten E-Mail-Client Lee ab. Weitere Informationen finden Sie im Abschnitt "Blockieren der [folgenden URLs" für](#block-the-following-urls-list-for-safe-links) sichere Links weiter unten in diesem Artikel.|
|Sowohl Füry als auch Julia arbeiten für contoso.com. Vor langer Zeit haben Administratoren Richtlinien für sichere Links konfiguriert, die sowohl für Jamie als auch für Julia gelten. Jamie sendet eine E-Mail an Julia, ohne zu wissen, dass die E-Mail eine schädliche URL enthält.|Julia ist durch sichere **Links** geschützt, wenn die richtlinie für sichere Links, die für sie gilt, so konfiguriert ist, dass sie auf Nachrichten zwischen internen Empfängern angewendet wird. Weitere Informationen finden Sie im Abschnitt Einstellungen für sichere Links für [E-Mail-Nachrichten](#safe-links-settings-for-email-messages) weiter unten in diesem Artikel.|
|

## <a name="safe-links-settings-for-email-messages"></a>Einstellungen für sichere Links für E-Mail-Nachrichten

Sichere Links überprüft eingehende E-Mails auf bekannte schädliche Hyperlinks. Gescannte URLs werden mit dem Microsoft-Standard-URL-Präfix umgeschrieben: `https://nam01.safelinks.protection.outlook.com` . Nachdem der Link umgeschrieben wurde, wird er auf potenziell schädliche Inhalte analysiert.

Nachdem sichere Links eine URL umgeschrieben haben, bleibt die  URL auch dann neu geschrieben, wenn die Nachricht manuell weitergeleitet oder beantwortet wird (sowohl an interne als auch an externe Empfänger). Zusätzliche Links, die der weitergeleiteten oder beantworteten Nachricht hinzugefügt werden, werden nicht umgeschrieben. Bei der automatischen  Weiterleitung durch Posteingangsregeln oder smtp-Weiterleitung wird die URL jedoch nicht in der Nachricht  umgeschrieben, die für den endgültigen Empfänger vorgesehen ist, es sei denn, dieser Empfänger ist auch durch sichere Links geschützt, oder die URL wurde bereits in einer vorherigen Kommunikation umgeschrieben. 

Die Einstellungen in Richtlinien für sichere Links, die für E-Mail-Nachrichten gelten, werden in der folgenden Liste beschrieben:

- **Wählen Sie die Aktion für unbekannte potenziell** schädliche URLs in Nachrichten aus: Aktiviert oder deaktiviert die Überprüfung sicherer Links in E-Mail-Nachrichten. Der empfohlene Wert ist **On**. Das Aktivieren dieser Einstellung führt zu den folgenden Aktionen.

  - Die Überprüfung sicherer Links ist in Outlook (C2R) auf Windows.
  - URLs werden umgeschrieben, und Benutzer werden durch den Schutz sicherer Links geroutet, wenn sie in Nachrichten auf URLs klicken.
  - Wenn Sie darauf klicken, werden URLs mit einer Liste bekannter bösartiger URLs und der Liste "Die folgenden [URLs blockieren" überprüft.](#block-the-following-urls-list-for-safe-links)
  - URLs ohne gültige Reputation werden asynchron im Hintergrund detoniert.

- **Anwenden der Echtzeit-URL-Überprüfung** auf verdächtige Links und Links, die auf Dateien verweisen: Ermöglicht das Scannen von Links in Echtzeit, einschließlich Links in E-Mail-Nachrichten, die auf herunterladbare Inhalte verweisen. Der empfohlene Wert ist aktiviert.
  - **Warten Sie, bis die URL-Überprüfung abgeschlossen ist, bevor Sie die Nachricht senden:**
    - Aktiviert: Nachrichten, die URLs enthalten, werden bis zum Abschluss der Überprüfung gehalten. Nachrichten werden nur zugestellt, nachdem die URLs als sicher bestätigt wurden. Dies ist der empfohlene Wert.
    - Deaktiviert: Wenn die URL-Überprüfung nicht abgeschlossen werden kann, senden Sie die Nachricht trotzdem.

- **Anwenden sicherer Links** auf E-Mail-Nachrichten, die innerhalb der Organisation gesendet werden: Aktiviert oder deaktiviert die Überprüfung sicherer Links auf Nachrichten, die zwischen internen Absendern und internen Empfängern innerhalb derselben Organisation Exchange Online werden. Der empfohlene Wert ist aktiviert.

- **Benutzerklicks** nicht nachverfolgen: Aktiviert oder deaktiviert das Speichern sicherer Links klicken Sie auf Daten für URLs, auf die in E-Mail-Nachrichten geklickt wurde. Der Empfehlungswert besteht in der Unauswahl dieser Einstellung (um Benutzerklicks nachverfolgt zu werden).

  Die URL-Klickverfolgung für Links in E-Mail-Nachrichten, die zwischen internen Absendern und internen Empfängern gesendet werden, wird derzeit nicht unterstützt.

- **Benutzer dürfen nicht zur ursprünglichen URL** durchklicken: Ermöglicht [](#warning-pages-from-safe-links) oder verhindert, dass Benutzer auf die Warnseite zur ursprünglichen URL klicken. Der Empfehlungswert ist aktiviert.

- **Anzeigen des Unternehmensbrandings auf Benachrichtigungs-** und Warnungsseiten: Diese Option zeigt das Branding Ihrer Organisation auf Warnseiten an. Branding hilft Benutzern, legitime Warnungen zu identifizieren, da Standardmäßige Microsoft-Warnseiten häufig von Angreifern verwendet werden. Weitere Informationen zum angepassten Branding finden Sie unter [Customize the Microsoft 365 theme for your organization](../../admin/setup/customize-your-organization-theme.md).

- **Not rewrite the following URLs**: Leaves URLs as they are. Behält eine benutzerdefinierte Liste sicherer URLs bei, die nicht gescannt werden müssen. Die Liste ist für jede Richtlinie für sichere Links eindeutig. Weitere Informationen zur Liste Nicht umschreiben der folgenden **URLs** finden Sie in den Listen "Die folgenden [URLs](#do-not-rewrite-the-following-urls-lists-in-safe-links-policies) nicht umschreiben" im Abschnitt Richtlinien für sichere Links weiter unten in diesem Artikel.

  Weitere Informationen zu den empfohlenen Werten für Standard- und Strikte Richtlinieneinstellungen für Richtlinien für sichere Links finden Sie unter [Richtlinieneinstellungen](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings)für sichere Links .

- **Empfängerfilter:** Sie müssen die Empfängerbedingungen und Ausnahmen angeben, die bestimmen, auf wen die Richtlinie angewendet wird. Sie können die folgenden Eigenschaften für Bedingungen und Ausnahmen verwenden:
  - **Der Empfänger ist**
  - **Die Empfängerdomäne ist**
  - **Der Empfänger ist Mitglied von**

  Sie können eine Bedingung oder Ausnahme nur einmal verwenden, die Bedingung oder Ausnahme kann aber mehrere Werte enthalten. Bei mehreren Werten derselben Bedingung oder Ausnahme wird ODER-Logik verwendet (z. B. _\<recipient1\>_ oder _\<recipient2\>_). Bei unterschiedlichen Bedingungen oder Ausnahmen wird UND-Logik verwendet (z. B. _\<recipient1\>_ und _\<member of group 1\>_).

- **Priorität:** Wenn Sie mehrere Richtlinien erstellen, können Sie die Reihenfolge angeben, in der sie angewendet werden. Keine zwei Richtlinien können die gleiche Priorität aufweisen, und die Richtlinienverarbeitung endet, nachdem die erste Richtlinie angewendet wurde.

  Weitere Informationen über die Prioritätsreihenfolge und darüber, wie mehrere Richtlinien ausgewertet und angewendet werden, finden Sie unter [Reihenfolge und Priorität beim E-Mail-Schutz](how-policies-and-protections-are-combined.md).
  
### <a name="how-safe-links-works-in-email-messages"></a>Funktionsweise sicherer Links in E-Mail-Nachrichten

Auf einer hohen Ebene funktioniert der Schutz sicherer Links bei URLs in E-Mail-Nachrichten:

1. Alle E-Mails werden über EOP gesendet, wobei Internetprotokoll- und Umschlagfilter, signaturbasierter Schadsoftwareschutz, Antispam- und Anti-Malware-Filter vor der Zugestellten Nachricht an das Postfach des Empfängers verwendet werden.

2. Der Benutzer öffnet die Nachricht in ihrem Postfach und klickt auf eine URL in der Nachricht.

3. Sichere Links überprüfen die URL sofort, bevor sie die Website öffnen:

   - Wenn die URL in der Liste Die folgende **URLs** blockieren enthalten ist, wird eine Warnung für [blockierte URLs](#blocked-url-warning) geöffnet.

   - Wenn die URL auf eine Website verweist, die [](#malicious-website-warning) als schädlich ermittelt wurde, wird eine Warnungsseite für schädliche Websites (oder eine andere Warnseite) geöffnet.

   - Wenn die URL auf eine herunterladbare Datei verweist und die Einstellung Url **in** Echtzeit auf verdächtige Links und Links anwenden, die auf Dateien verweisen, in der Richtlinie aktiviert ist, die für den Benutzer gilt, wird die herunterladbare Datei überprüft.

   - Wenn die URL als sicher festgelegt ist, wird die Website geöffnet.

## <a name="safe-links-settings-for-microsoft-teams"></a>Einstellungen für sichere Links für Microsoft Teams

> [!IMPORTANT]
> Ab März 2020 befindet sich dieses Feature in der Vorschau und ist nur für Mitglieder des Microsoft Teams Technology Adoption Program (TAP) verfügbar. Informationen zum Veröffentlichungszeitplan finden Sie in der [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap?rtc=1&filters=&searchterms=Safe%2CLinks%2CProtection%2Cfor%2CMicrosoft%2CTeams).

Sie aktivieren oder deaktivieren den Schutz sicherer Links für Microsoft Teams in Richtlinien für sichere Links. Insbesondere verwenden Sie die Aktion Auswählen für unbekannte oder potenziell **schädliche URLs innerhalb Microsoft Teams** Einstellung. Der empfohlene Wert ist **On**.

Die folgenden Einstellungen in Richtlinien für sichere Links, die für Links in E-Mail-Nachrichten gelten, gelten auch für Links in Teams:

- **Anwenden der Echtzeit-URL-Überprüfung auf verdächtige Links und Links, die auf Dateien verweisen**
- **Benutzerklicks nicht nachverfolgen**
- **Benutzer dürfen nicht zur ursprünglichen URL klicken**

Diese Einstellungen werden zuvor unter Einstellungen für sichere [Links für E-Mail-Nachrichten erläutert.](#safe-links-settings-for-email-messages)

Nachdem Sie den Schutz für sichere Links für Microsoft Teams aktiviert haben, werden URLs in Teams auf eine Liste bekannter schädlicher Links überprüft, wenn der geschützte Benutzer auf den Link klickt (Time-of-Click-Schutz). URLs werden nicht umgeschrieben. Wenn ein Link als bösartig gefunden wird, haben Benutzer die folgenden Erfahrungen:

- Wenn auf den Link in einer Teams, einem Gruppenchat oder kanälen geklickt wurde, wird die Warnseite wie im screenshot unten gezeigt im Standardwebbrowser angezeigt.
- Wenn auf den Link von einer angeheftierten Registerkarte geklickt wurde, wird die Warnungsseite in der Teams auf dieser Registerkarte angezeigt. Die Option zum Öffnen des Links in einem Webbrowser ist aus Sicherheitsgründen deaktiviert.
- Je nachdem, wie die Einstellung Nicht zulassen, dass Benutzer in der Richtlinie auf die ursprüngliche **URL-Einstellung** klicken können, kann der Benutzer auf die ursprüngliche URL klicken ( Weiter trotzdem **(nicht empfohlen)** im Screenshot). Es wird empfohlen, dass Sie die Einstellung Benutzer nicht zulassen aktivieren, um auf die ursprüngliche **URL** zu klicken, damit Benutzer nicht zur ursprünglichen URL klicken können.

Wenn der Benutzer, der den Link gesendet hat, nicht in einer Richtlinie für sichere Links enthalten ist, bei der Teams-Schutz aktiviert ist, kann der Benutzer auf dem Computer oder Gerät auf die ursprüngliche URL klicken.

![Eine Sichere Links für Teams Seite, die einen schädlichen Link meldet.](../../media/tp-safe-links-for-teams-malicious.png)

Wenn Sie auf **der Warnungsseite** auf die Schaltfläche Zurück wechseln klicken, wird der Benutzer an seinen ursprünglichen Kontext- oder URL-Speicherort zurückkehren. Wenn Sie jedoch erneut auf den ursprünglichen Link klicken, werden sichere Links die URL erneut scannen, sodass die Warnungsseite erneut angezeigt wird.

### <a name="how-safe-links-works-in-teams"></a>Funktionsweise sicherer Links in Teams

Auf einer hohen Ebene funktioniert der Schutz sicherer Links für URLs in Microsoft Teams:

1. Ein Benutzer startet die Teams App.

2. Microsoft 365 überprüft, ob die Organisation des Benutzers Microsoft Defender für Office 365 enthält und dass der Benutzer in einer aktiven Richtlinie für sichere Links enthalten ist, in der der Microsoft Teams aktiviert ist.

3. URLs werden zum Zeitpunkt des Klickens für den Benutzer in Chats, Gruppenchats, Kanälen und Registerkarten überprüft.

## <a name="safe-links-settings-for-office-365-apps"></a>Einstellungen für sichere Links für Office 365 Apps

Safe Links Protection for Office 365 apps checks links in Office documents, not links in email messages (but it can check links in attached Office documents in email messages after the document is opened).

Der Schutz sicherer Links für Office 365 apps hat die folgenden Clientanforderungen:

- Microsoft 365 Apps oder Microsoft 365 Business Premium.
  - Aktuelle Versionen von Word, Excel und PowerPoint auf Windows, Mac oder in einem Webbrowser.
  - Office Apps auf iOS- oder Android-Geräten.
  - Visio auf Windows.
  - OneNote in einem Webbrowser.

- Office 365 apps are configured to use modern authentication. Weitere Informationen finden Sie unter Funktionsweise der modernen Authentifizierung für [Office 2013, Office 2016 und Office 2019-Client-Apps](../../enterprise/modern-auth-for-office-2013-and-2016.md).

- Benutzer sind mit ihren Arbeits- oder Schulkonten angemeldet. Weitere Informationen finden Sie unter [Sign in to Office](https://support.microsoft.com/office/b9582171-fd1f-4284-9846-bdd72bb28426).

Sie konfigurieren den Schutz sicherer Links für Office 365 apps in den globalen Einstellungen für sichere Links, nicht in Richtlinien für sichere Links. Der Schutz wird auf alle Benutzer in der Organisation angewendet, die für Defender für Office 365 lizenziert sind, unabhängig davon, ob die Benutzer in aktiven Richtlinien für sichere Links enthalten sind oder nicht.

Die folgenden Einstellungen für sichere Links sind für Office 365 verfügbar:

- **Office 365:** Aktiviert oder deaktiviert die Überprüfung sicherer Links in unterstützten Office 365 Apps. Der Standardwert und der empfohlene Wert ist **On**.

- Nicht nachverfolgen, wenn Benutzer auf Sichere Links **klicken:** Aktiviert oder deaktiviert das Speichern sicherer Links klicken Sie auf Daten für URLs, auf die in den Desktopversionen Word, Excel, PowerPoint und Visio. Der empfohlene Wert ist **Off**, was bedeutet, dass Benutzerklicks nachverfolgt werden.

- Benutzer dürfen nicht auf sichere Links zur ursprünglichen **URL** klicken: [](#warning-pages-from-safe-links) Ermöglicht oder blockiert Benutzern das Klicken über die Warnseite zur ursprünglichen URL in den Desktopversionen Word, Excel, PowerPoint und Visio. Der Standardwert und der empfohlene Wert ist **On**.

Informationen zum Konfigurieren der Einstellungen für sichere Links Office 365 Apps finden Sie unter [Configure Safe Links protection for Office 365 apps](configure-global-settings-for-safe-links.md#configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center).

Weitere Informationen zu den empfohlenen Werten für Standard- und Strict-Richtlinieneinstellungen finden Sie unter [Globale Einstellungen für sichere Links](recommended-settings-for-eop-and-office365.md#global-settings-for-safe-links).

### <a name="how-safe-links-works-in-office-365-apps"></a>Funktionsweise sicherer Links in Office 365 Apps

Auf einer hohen Ebene funktioniert der Schutz sicherer Links für URLs in Office 365 Apps. Die unterstützten Office 365 werden im vorherigen Abschnitt beschrieben.

1. Ein Benutzer meldet sich mit dem Arbeits- oder Schulkonto in einer Organisation an, die Microsoft 365 Apps oder Microsoft 365 Business Premium.

2. Der Benutzer öffnet und klickt auf einen Link, Office in einem unterstützten Dokument Office-App.

3. Sichere Links überprüft die URL unmittelbar vor dem Öffnen der Zielwebsite:

   - Wenn die URL in der Liste enthalten ist, die die Überprüfung sicherer Links überspringt (in der Liste Blockieren der folgenden **URLs),** wird eine Warnungsseite für blockierte [URLs](#blocked-url-warning) geöffnet.

   - Wenn die URL auf eine Website verweist, die [](#malicious-website-warning) als schädlich ermittelt wurde, wird eine Warnungsseite für schädliche Websites (oder eine andere Warnseite) geöffnet.

   - Wenn die URL auf eine herunterladbare Datei verweist und die Richtlinie für sichere Links, die für den Benutzer gilt, so konfiguriert ist, dass Links zu herunterladbaren Inhalten überprüft werden ( Anwenden der **Echtzeit-URL-Überprüfung** auf verdächtige Links und Links, die auf Dateien verweisen), wird die herunterladbare Datei überprüft.

   - Wenn die URL als sicher betrachtet wird, wird der Benutzer zur Website übernommen.

   - Wenn die Überprüfung sicherer Links nicht abgeschlossen werden kann, wird der Schutz sicherer Links nicht ausgelöst. In Office Desktopclients wird der Benutzer gewarnt, bevor er zur Zielwebsite weitergeht.

> [!NOTE]
> Es kann mehrere Sekunden am Anfang jeder Sitzung dauern, um zu überprüfen, ob der Benutzer über sichere Links für Office verfügt.

## <a name="block-the-following-urls-list-for-safe-links"></a>Liste "Blockieren der folgenden URLs" für sichere Links

In **der Liste Blockieren der folgenden URLs** werden die Links definiert, die immer von der Überprüfung sicherer Links an den folgenden Speicherorten blockiert werden:

- E-Mail-Nachrichten.
- Dokumente in Office 365 apps in Windows und Mac.
- Dokumente in Office für iOS und Android.

Wenn ein Benutzer in einer aktiven Richtlinie für sichere Links auf einen blockierten Link in einer unterstützten App klickt, wird er zur Warnungsseite Blockierte [URL](#blocked-url-warning) weitergeleitet.

Sie konfigurieren die Liste der URLs in den globalen Einstellungen für sichere Links. Anweisungen finden Sie unter [Configure the "Block the following URLs" list](configure-global-settings-for-safe-links.md#configure-the-block-the-following-urls-list-in-the-security--compliance-center).

**Hinweise**:

- Eine wirklich universelle Liste der überall blockierten URLs finden Sie unter [Manage the Tenant Allow/Block List](tenant-allow-block-list.md).
- Grenzwerte für die **Liste Blockieren der folgenden URLs:**
  - Die maximale Anzahl von Einträgen beträgt 500.
  - Die maximale Länge eines Eintrags beträgt 128 Zeichen.
  - Alle Einträge dürfen 10.000 Zeichen nicht überschreiten.
- Schließen Sie am Ende der URL keinen Schrägstrich ( `/` ) ein. Verwenden Sie beispielsweise `https://www.contoso.com` , nicht `https://www.contoso.com/` .
- Eine nur Domänen-URL (z. B. oder ) blockiert jede `contoso.com` `tailspintoys.com` URL, die die Domäne enthält.
- Sie können eine Unterdomäne blockieren, ohne die vollständige Domäne zu blockieren. Blockiert beispielsweise jede URL, die die Unterdomäne enthält, aber nicht `toys.contoso.com*` URLs, die die vollständige Domäne `contoso.com` enthalten.
- Sie können bis zu drei Platzhalter ( ) pro `*` URL-Eintrag angeben.

### <a name="entry-syntax-for-the-block-the-following-urls-list"></a>Eintragssyntax für die Liste "Die folgenden URLs blockieren"

Beispiele für die Werte, die Sie eingeben können, und deren Ergebnisse werden in der folgenden Tabelle beschrieben:

<br>

****

|Wert|Ergebnis|
|---|---|
|`contoso.com` <p> oder <p> `*contoso.com*`|Blockiert die Domäne, Unterdomänen und Pfade. Beispielsweise `https://www.contoso.com` , `https://sub.contoso.com` und `https://contoso.com/abc` werden blockiert.|
|`https://contoso.com/a`|Blöcke, `https://contoso.com/a` aber keine zusätzlichen Unterpfade wie `https://contoso.com/a/b` .|
|`https://contoso.com/a*`|Blöcke `https://contoso.com/a` und zusätzliche Unterpfade wie `https://contoso.com/a/b` .|
|`https://toys.contoso.com*`|Blockiert eine Unterdomäne (in diesem Beispiel), lässt jedoch Klicks auf andere `toys` Domänen-URLs zu (z. B. `https://contoso.com` oder `https://home.contoso.com` ).|
|

## <a name="do-not-rewrite-the-following-urls-lists-in-safe-links-policies"></a>"Die folgenden URLs nicht umschreiben" in Richtlinien für sichere Links

> [!NOTE]
> Wenn Ihre Organisation Richtlinien für sichere Links verwendet, sind die Folgenden **URLs-Listen** nicht umschreiben die einzige unterstützte Methode für Phishingtests von Drittanbietern.

Jede Richtlinie für sichere Links enthält die folgende **URLs-Liste** nicht umschreiben, mit der Sie URLs angeben können, die nicht von der Überprüfung sicherer Links umgeschrieben werden. Mit anderen Worten, die Liste ermöglicht Benutzern, die in der Richtlinie enthalten sind, den Zugriff auf die angegebenen URLs, die andernfalls durch sichere Links blockiert würden. Sie können verschiedene Listen in verschiedenen Richtlinien für sichere Links konfigurieren. Die Richtlinienverarbeitung wird beendet, nachdem die erste Richtlinie (wahrscheinlich die höchste Priorität) auf den Benutzer angewendet wurde. Daher wird nur eine Liste Nicht umschreiben die folgende **URLs-Liste** auf einen Benutzer angewendet, der in mehreren aktiven Richtlinien für sichere Links enthalten ist.

Informationen zum Hinzufügen von Einträgen zur Liste in neuen oder vorhandenen Richtlinien für sichere Links finden Sie unter [Create Safe Links policies](set-up-safe-links-policies.md#use-the-security--compliance-center-to-create-safe-links-policies) or Modify Safe Links [policies](set-up-safe-links-policies.md#use-the-security--compliance-center-to-modify-safe-links-policies).

**Hinweise**:

- Die folgenden Clients erkennen die Folgenden **URLs-Listen** in Richtlinien für sichere Links nicht umschreiben. Benutzer, die in den Polizeien enthalten sind, können basierend auf den Ergebnissen der Überprüfung sicherer Links in diesen Clients am Zugriff auf die URLs blockiert werden:
  - Microsoft Teams
  - Office-Web-Apps

  Eine wirklich universelle Liste der überall zulässigen URLs finden Sie unter [Manage the Tenant Allow/Block List](tenant-allow-block-list.md).

- Erwägen Sie, der Liste häufig verwendete interne URLs hinzuzufügen, um die Benutzerfreundlichkeit zu verbessern. Wenn Sie beispielsweise über lokale Dienste wie Skype for Business oder SharePoint verfügen, können Sie diese URLs hinzufügen, um sie vom Scannen auszuschließen.
- Wenn Sie die folgenden **URLs-Einträge** in Ihren Richtlinien für sichere Links noch nicht umgeschrieben haben, überprüfen Sie unbedingt die Listen, und fügen Sie bei Bedarf Platzhalter hinzu. Ihre Liste hat z. B. einen Eintrag wie, und Sie entscheiden sich später dafür, `https://contoso.com/a` Unterpfade wie `https://contoso.com/a/b` hinzuzufügen. Anstatt einen neuen Eintrag hinzuzufügen, fügen Sie dem vorhandenen Eintrag einen Platzhalter hinzu, sodass er zu `https://contoso.com/a/*` wird.
- Sie können bis zu drei Platzhalter ( ) pro `*` URL-Eintrag angeben. Platzhalter enthalten explizit Präfixe oder Unterdomänen. Beispielsweise ist der Eintrag nicht identisch mit , da Personen Unterdomänen und Pfade in der `contoso.com` `*.contoso.com/*` `*.contoso.com/*` angegebenen Domäne besuchen können.
- Wenn eine URL die automatische Umleitung für HTTP zu HTTPS verwendet (z. B. 302-Umleitung für ), und Sie versuchen, http- und HTTPS-Einträge für dieselbe URL in die Liste ein eingeben, wird möglicherweise festgestellt, dass der zweite URL-Eintrag den ersten `http://www.contoso.com` `https://www.contoso.com` URL-Eintrag ersetzt. Dieses Verhalten tritt nicht auf, wenn die HTTP- und DIE HTTPS-Versionen der URL vollständig getrennt sind.

### <a name="entry-syntax-for-the-do-not-rewrite-the-following-urls-list"></a>Eintragssyntax für die Liste "Die folgenden URLs nicht umschreiben"

Beispiele für die Werte, die Sie eingeben können, und deren Ergebnisse werden in der folgenden Tabelle beschrieben:

<br>

****

|Wert|Ergebnis|
|---|---|
|`contoso.com`|Ermöglicht den Zugriff `https://contoso.com` auf Unterdomänen oder Pfade.|
|`*.contoso.com/*`|Ermöglicht den Zugriff auf eine Domäne, Unterdomänen und Pfade (z. B. `https://www.contoso.com` `https://www.contoso.com` , , oder `https://maps.contoso.com` `https://www.contoso.com/a` ). <p> Dieser Eintrag ist grundsätzlich besser als , da er potenziell betrügerische Websites wie oder `*contoso.com*` `https://www.falsecontoso.com``https://www.false.contoso.completelyfalse.com`|
|`https://contoso.com/a`|Ermöglicht den Zugriff `https://contoso.com/a` auf , aber nicht auf Unterpfade wie `https://contoso.com/a/b`|
|`https://contoso.com/a/*`|Ermöglicht den Zugriff `https://contoso.com/a` auf und Unterpfade wie `https://contoso.com/a/b`|
|

## <a name="warning-pages-from-safe-links"></a>Warnungsseiten von sicheren Links

Dieser Abschnitt enthält Beispiele für die verschiedenen Warnseiten, die durch den Schutz sicherer Links ausgelöst werden, wenn Sie auf eine URL klicken.

Beachten Sie, dass mehrere Warnseiten aktualisiert wurden. Wenn die aktualisierten Seiten noch nicht angezeigt werden, werden Sie bald folgen. Die aktualisierten Seiten enthalten ein neues Farbschema, weitere Details und die Möglichkeit, trotz der angegebenen Warnung und Empfehlungen mit einer Website fortzufahren.

### <a name="scan-in-progress-notification"></a>Benachrichtigung zur Überprüfung in Bearbeitung

Die geklickte URL wird von sicheren Links überprüft. Möglicherweise müssen Sie einige Minuten warten, bevor Sie den Link erneut ausprobieren.

![Benachrichtigung "Der Link wird gescannt"](../../media/ee8dd5ed-6b91-4248-b054-12b719e8d0ed.png)

Die ursprüngliche Benachrichtigungsseite sah wie dies aus:

![Ursprüngliche Benachrichtigung "Der Link wird gescannt"](../../media/04368763-763f-43d6-94a4-a48291d36893.png)

### <a name="suspicious-message-warning"></a>Warnung vor verdächtigen Nachrichten

Die geklickte URL war in einer E-Mail-Nachricht, die anderen verdächtigen Nachrichten ähnelt. Es wird empfohlen, die E-Mail-Nachricht zu überprüfen, bevor Sie zur Website fortfahren.

![Warnung "Auf einen Link wurde in einer verdächtigen Nachricht geklickt".](../../media/33f57923-23e3-4b0f-838b-6ad589ba897b.png)

### <a name="phishing-attempt-warning"></a>Warnung vor Phishingversuchen

Die angeklickte URL war in einer E-Mail-Nachricht, die als Phishingangriff identifiziert wurde. Als Ergebnis werden alle URLs in der E-Mail-Nachricht blockiert. Es wird empfohlen, nicht mit der Website fortzufahren.

![Warnung "Auf den Link wurde in einer Phishingnachricht geklickt".](../../media/6e544a28-0604-4821-aba6-d5a57bb917e5.png)

### <a name="malicious-website-warning"></a>Warnung vor bösartigen Websites

Die angeklickte URL verweist auf eine Website, die als schädlich identifiziert wurde. Es wird empfohlen, nicht mit der Website fortzufahren.

![Warnung "Diese Website wird als bösartig klassifiziert"](../../media/058883c8-23f0-4672-9c1c-66b084796177.png)

Die ursprüngliche Warnseite sah wie dies aus:

![Ursprüngliche Warnung "Diese Website wurde als bösartig klassifiziert"](../../media/b9efda09-6dd8-46ef-82cb-56e4d538b8f5.png)

### <a name="blocked-url-warning"></a>Warnung für blockierte URL

Die geklickte URL wurde manuell von einem Administrator in Ihrer Organisation blockiert (die Liste "Folgende **URLs** blockieren" in den globalen Einstellungen für sichere Links). Der Link wurde nicht von sicheren Links überprüft, da er manuell blockiert wurde.

Es gibt mehrere Gründe, warum ein Administrator bestimmte URLs manuell blockieren würde. Wenn Sie der Meinung sind, dass die Website nicht blockiert werden sollte, wenden Sie sich an Ihren Administrator.

![Warnung "Diese Website wurde von Ihrem Administrator blockiert"](../../media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)

Die ursprüngliche Warnseite sah wie dies aus:

![Ursprüngliche Warnung "Diese Website wurde durch die URL-Richtlinie Ihrer Organisation blockiert"](../../media/3d6ba028-30bf-45fc-958e-d3aad3defc83.png)

### <a name="error-warning"></a>Fehlerwarnung

Es ist ein Fehler aufgetreten, und die URL kann nicht geöffnet werden.

![Warnung "Die Seite, auf die Sie zugreifen möchten, kann nicht geladen werden"](../../media/2f7465a4-1cf4-4c1c-b7d4-3c07e4b795b4.png)

Die ursprüngliche Warnseite sah wie dies aus:

![Ursprüngliche Warnung "Diese Webseite konnte nicht geladen werden"](../../media/9aaa4383-2f23-48be-bdaa-8efbcb2acc70.png)
