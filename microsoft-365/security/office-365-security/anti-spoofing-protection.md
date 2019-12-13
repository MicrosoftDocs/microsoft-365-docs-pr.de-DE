---
title: Antispoofingschutz in Office 365
ms.author: tracyp
author: MSFTtracyp
manager: dansimp
ms.date: 08/30/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
search.appverid:
- MET150
ms.assetid: d24bb387-c65d-486e-93e7-06a4f1a436c0
ms.collection:
- M365-security-compliance
- Strat_O365_IP
ms.custom: TopSMBIssues
localization_priority: Priority
description: In diesem Artikel wird beschrieben, wie Office 365 vor Phishingangriffen schützt, die gefälschte Absenderdomänen verwenden, d. h.Spoofdomänen. Dies wird erzielt, indem Nachrichten analysiert werden und diejenigen blockiert werden, die weder mithilfe von standardmäßigen E-Mail-Authentifizierungsmethoden noch anderen Absenderzuverlässigkeitsmethoden authentifiziert werden können. Diese Änderung wurde implementiert, um die Anzahl der Phishingangriffe zu reduzieren, denen Organisationen in Office 365 ausgesetzt sind.
ms.openlocfilehash: 5685fc29f97c9aa41e472926c4e1f26bfcfd1432
ms.sourcegitcommit: 5710ce729c55d95b8b452d99ffb7ea92b5cb254a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2019
ms.locfileid: "39971993"
---
# <a name="anti-spoofing-protection-in-office-365"></a>Antispoofingschutz in Office 365

In diesem Artikel wird beschrieben, wie Office 365 vor Phishingangriffen schützt, die gefälschte Absenderdomänen verwenden, d. h.Spoofdomänen. Dies wird erzielt, indem Nachrichten analysiert werden und diejenigen blockiert werden, die nicht mithilfe von standardmäßigen E-Mail-Authentifizierungsmethoden und anderen Absenderzuverlässigkeitsmethoden authentifiziert werden können. Diese Änderung wurde implementiert, um die Anzahl der Phishingangriffe zu reduzieren, denen Organisationen in Office 365 ausgesetzt sind.

In diesem Artikel wird erläutert, warum diese Änderung vorgenommen wurde, wie sich Kunden auf diese Änderung vorbereiten können, wie Sie Nachrichten anzeigen, die betroffen sind, wie Nachrichten gemeldet werden können, wie Sie falsch positive Ergebnisse vermeiden und wie sich Absender, die Nachrichten an Microsoft senden, auf diese Änderung vorbereiten können.

Die Antispoofingtechnologie von Microsoft wurde ursprünglich für die Organisationen bereitgestellt, die ein Office 365 Enterprise E5-Abonnement hatten oder das Add-On Office 365 Advanced Threat Protection (ATP) für ihr Abonnement erworben haben. Ab Oktober 2018 wurde der Schutz auf Organisationen erweitert, die über Exchange Online Protection (EOP) verfügen. Darüber hinaus können aufgrund der Art und Weise, wie alle unsere Filter voneinander lernen, Outlook.com-Benutzern ebenfalls betroffen sein.

## <a name="how-spoofing-is-used-in-phishing-attacks"></a>Verwenden von Spoofing bei Phishingangriffen

Wenn es um den Schutz der Benutzer geht, nimmt Microsoft die Bedrohung durch Phishing ernst. Eine der Methoden, die Spammer und Phisher häufig verwenden, ist Spoofing. Hierbei ist der Absender gefälscht, und eine Nachricht stammt von einer anderen Person oder von anderswo als der eigentlichen Quelle. Diese Methode wird häufig bei Phishingkampagnen verwendet, die darauf abzielen, Anmeldeinformationen des Benutzers abzurufen. Die Antispoofingtechnologie von Microsoft untersucht speziell die Fälschung des „Von-Felds“, das in einem E-Mail-Client wie Outlook angezeigt wird. Wenn das Von-Feld mit hoher Wahrscheinlichkeit gefälscht ist, wird die Nachricht von der Technologie als Spoof identifiziert.

Spoofingnachrichten weisen in der Praxis zwei negative Auswirkungen für Benutzer auf:

### <a name="1-spoofed-messages-deceive-users"></a>1. Gefälschte Nachrichten täuschen Benutzer

Erstens kann eine gefälschte Nachricht einen Benutzer dazu bringen, auf einen Link zu klicken und seine Anmeldeinformationen anzugeben, Malware herunterzuladen oder auf eine Nachricht mit vertraulichen Inhalten zu antworten (Letzteres wird als Business Email Compromise bezeichnet). Es folgt ein Beispiel für eine Phishingnachricht mit einem gefälschten Absender msoutlook94@service.outlook.com:

![Phishingnachricht, die die Identität von service.outlook.com angenommen hat](../media/1a441f21-8ef7-41c7-90c0-847272dc5350.jpg)

Die obige Nachricht stammt nicht von service.outlook.com, sondern wurde vom Phisher gefälscht, damit es so aussieht, als würde sie von dieser Domäne gesendet. Mit dieser Nachricht wird versucht, einen Benutzer dazu zu bringen, auf den Link in der Nachricht zu klicken.

Im nächsten Beispiel wurde die Identität von contoso.com angenommen:

![Phishingnachricht – Business Email Compromise](../media/da15adaa-708b-4e73-8165-482fc9182090.jpg)

Die Nachricht sieht seriös aus, in Wirklichkeit handelt es sich um Spoof. Diese Phishingnachricht ist eine Art von BEC-Angriffen (Business Email Compromise), die eine Unterkategorie von Phishing ist.

### <a name="2-users-confuse-real-messages-for-fake-ones"></a>2. Benutzer verwechseln echte und gefälschte Nachrichten

Zweitens sorgen gefälschte Nachrichten für Unsicherheit bei Benutzern, die sich mit Phishingnachrichten auskennen, jedoch nicht den Unterschied zwischen einer echten Nachricht und einer gefälschten Nachricht benennen können. Es folgt ein Beispiel für eine echte Nachricht zur Kennwortzurücksetzung von der E-Mail-Adresse des Microsoft Security-Kontos:

![Seriöse Nachricht zur Kennwortzurücksetzung von Microsoft](../media/58a3154f-e83d-4f86-bcfe-ae9e8c87bd37.jpg)

Die obige Nachricht wurde von Microsoft gesendet. Gleichzeitig sind Benutzer es Benutzer jedoch gewohnt, Phishingnachrichten zu erhalten, die Sie dazu bringen sollen, auf einen Link zu klicken und ihre Anmeldeinformationen anzugeben, Malware herunterzuladen oder auf eine Nachricht mit vertraulichen Inhalten zu antworten. Da es schwierig ist, zwischen einer echten Kennwortzurücksetzung und einer gefälschten zu unterscheiden, ignorieren viele Benutzer diese Nachrichten, melden sie als Spam oder senden diese Nachrichten als nicht erkannte Phishing-Versuche an Microsoft zurück.

Um Spoofing zu stoppen, wurden von der E-Mail-Filterungsbranche E-Mail-Authentifizierungsprotokolle wie [SPF](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing), [DKIM](https://docs.microsoft.com/office365/SecurityCompliance/use-dkim-to-validate-outbound-email) und [DMARC](https://docs.microsoft.com/office365/SecurityCompliance/use-dmarc-to-validate-email) entwickelt. DMARC verhindert, dass Spoofing den Absender einer Nachricht überprüft. Dies ist der Absender, den die Benutzer in Ihrem E-Mail-Client sehen (in den obigen Beispielen sind das service.outlook.com, outlook.com und accountprotection.microsoft.com). Darüber hinaus können die Benutzer auch sehen, dass die Domäne SPF oder DKIM überschritten hat. Dies bedeutet, dass die Domäne authentifiziert wurde und daher kein Spoofing erfolgt. Detaillierte Informationen dazu finden Sie im späteren Verlauf dieses Artikels im Abschnitt „*Warum E-Mail-Authentifizierung nicht immer ausreicht, um Spoofing zu stoppen“* 

Das Problem ist jedoch, dass die E-Mail-Authentifizierungsdatensätze optional sind, nicht erforderlich. Während Domänen mit Richtlinien für sichere Authentifizierung wie microsoft.com und skype.com vor Spoofing geschützt sind, werden Domänen mit schwächeren oder ohne Authentifizierungsrichtlinien Ziel für Spoofing sind. Seit März 2018 verfügen nur 9 % der Domänen der Fortune 500-Unternehmen über Richtlinien für sichere E-Mail-Authentifizierung. Die verbleibenden 91 % können von einem Phisher gefälscht werden und werden, wenn sie nicht von einem E-Mail-Filter anhand einer anderen Richtlinie als solche erkannt werden, an den Endbenutzer übermittelt und können diesen täuschen:

![DMARC-Richtlinien von Fortune 500-Unternehmen](../media/84e77d34-2073-4a8e-9f39-f109b32d06df.jpg)

Der Anteil kleiner und mittelständischer Unternehmen, die keine Fortune 500-Unternehmen sind und Richtlinien für sichere E-Mail-Authentifizierung veröffentlichen, ist kleiner und noch kleiner für Domänen außerhalb von Nordamerika und Westeuropa.

Dies ist ein großes Problem, denn während Unternehmen möglicherweise nicht wissen, wie die E-Mail-Authentifizierung funktioniert, wissen Phisher den Mangel auszunutzen.

Informationen zum Einrichten von SPF, DKIM und DMARC finden Sie im späteren Verlauf dieses Dokuments im Abschnitt „*Kunden von Office 365“*.

## <a name="stopping-spoofing-with-implicit-email-authentication"></a>Stoppen von Spoofing mit impliziter E-Mail-Authentifizierung

Da Phishing und Spear-Phishing ein solches Problem darstellen und die Einführung von Richtlinien für sichere E-Mail-Authentifizierung begrenzt ist, arbeitet Microsoft weiterhin daran, investiert Microsoft weiterhin in Möglichkeiten zum Schutz seiner Kunden. Daher arbeitet Microsoft daran, die *implizite E-Mail-Authentifizierung* voranzutreiben – Wenn eine Domäne nicht authentifiziert ist, wird sie von Microsoft so behandelt, als ob sie E-Mail-Authentifizierungsdatensätze veröffentlicht hätte, und wird entsprechend behandelt, wenn sie sie nicht übergibt.

Zu diesem Zweck hat Microsoft zahlreiche Erweiterungen zur normalen E-Mail-Authentifizierung entwickelt, darunter Absenderzuverlässigkeit, Absender/Empfängerverlauf, Verhaltensanalyse und weitere erweiterte Methoden. Eine Nachricht von einer Domäne, die keine E-Mail-Authentifizierung veröffentlicht, wird als Spoof gekennzeichnet, wenn sie nicht auf andere Weise signalisiert, dass es sich dabei um eine seriöse Nachricht handelt.

So können Endbenutzer darauf vertrauen, dass es sich bei einer E-Mail, die an sie gesendet wurde, nicht um eine gefälschte Nachricht handelt und niemand die Identität dieser Domäne angenommen hat. Kunden von Office 365 können sogar besseren Schutz wie Schutz vor Identitätswechsel bieten.

Eine allgemeine Ankündigung von Microsoft finden Sie unter [A Sea of Phish Part 2 – Enhanced Anti-spoofing in Office 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Schooling-A-Sea-of-Phish-Part-2-Enhanced-Anti-spoofing/ba-p/176209).

## <a name="identifying-that-a-message-is-classified-as-spoofed"></a>Erkennen, dass eine Nachricht als gefälscht eingestuft ist

### <a name="composite-authentication"></a>Zusammengesetzte Authentifizierung

Obwohl SPF, DKIM und DMARC an sich hilfreich sind, wird hier der Authentifizierungsstatus nicht ausreichend kommuniziert, wenn eine Nachricht keine expliziten Authentifizierungsdatensätze enthält. Daher hat Microsoft einen Algorithmus entwickelt, der mehrere Signale in einem einzelnen Wert kombiniert, auch als Composite Authentication (zusammengesetzte Authentifizierung) oder Compauth bezeichnet. Office 365-Kunden verfügen über Compauth-Werte im *Authentication-Results*-Header in den Nachrichtenköpfen.

```
Authentication-Results:
  compauth=<fail|pass|softpass|none> reason=<yyy>

```

|**CompAuth-Ergebnis**|**Beschreibung**|
|:-----|:-----|
|fail|Die explizite Authentifizierung (sendende Domäne hat explizit Datensätze im DNS veröffentlicht) oder implizite Authentifizierung (sendende Domäne hat keine Datensätze im DNS veröffentlicht, sodass Office 365 das Ergebnis interpoliert hat, als ob sie Datensätze veröffentlicht hätte) für die Nachricht ist fehlgeschlagen.|
|pass|Die Nachricht hat die explizite Authentifizierung bestanden (Nachricht hat DMARC oder [Best Guess Passed DMARC](https://blogs.msdn.microsoft.com/tzink/2015/05/06/what-is-dmarc-bestguesspass-in-office-365) übergeben) oder die implizite Authentifizierung mit einem vertrauenswürdigen Ergebnis bestanden (sendende Domäne hat keine E-Mail-Authentifizierungsdatensätze veröffentlicht, Office 365 hat jedoch starke Back-End-Signale erhalten, die angeben, dass die Nachricht wahrscheinlich seriös ist).|
|softpass|Nachricht hat die implizite Authentifizierung mit niedrigem bis mittlerem vertrauenswürdigen Ergebnis bestanden (sendende Domäne hat keine E-Mail-Authentifizierung veröffentlicht, Office 365 hat jedoch starke Back-End-Signale erhalten, die angeben, dass die Nachricht seriös ist, die Stärke des Signals ist jedoch schwächer).|
|none|Die Nachricht wurde nicht authentifiziert (oder wurde authentifiziert, jedoch nicht ausgerichtet), die zusammengesetzte Authentifizierung wurde jedoch aufgrund der Absenderzuverlässigkeit oder anderer Faktoren nicht angewendet.|

|||
|:-----|:-----|
|**Grund**|**Beschreibung**|
|0xx |Die zusammengesetzte Authentifizierung für die Nachricht ist fehlgeschlagen.<br/>**000** gibt an, dass DMARC für die Nachricht mit einer Aktion der Ablehnung oder Quarantäne fehlgeschlagen ist.  <br/>**001** gibt an, dass die implizite E-Mail-Authentifizierung für die Nachricht fehlgeschlagen ist. Das bedeutet, dass die sendende Domäne keinen E-Mail-Authentifizierungsdatensätze veröffentlicht hat, oder wenn sie sie veröffentlicht hat, sie eine schwächere Fehlerrichtlinie hatten (SPF Soft Fail oder neutral, DMARC-Richtlinie von p = none).  <br/>**002** gibt an, dass die Organisation über eine Richtlinie für das Absender/Domänepaar verfügt, für die das Senden von gefälschten E-Mails explizit untersagt ist. Diese Einstellung wird manuell vom Administrator festgelegt.  <br/>**010** gibt an, dass DMARC für die Nachricht mit einer Aktion der Ablehnung oder Quarantäne fehlgeschlagen ist und die sendende Domäne eine der in der Organisation zulässigen Domänen ist (Dies ist Teil von Self-to-Self Spoofing oder organisationsinternem Spoofing).|
|1xx, 2xx, 3xx, 4xx und 5xx|Entspricht verschiedenen internen Codes, warum die implizite Authentifizierung für eine Nachricht erfolgreich war oder warum keine Authentifizierung stattgefunden hat, aber keine Aktion angewendet wurde.|
|6xx|Gibt an, dass die implizite E-Mail-Authentifizierung für die Nachricht fehlgeschlagen ist und die sendende Domäne eine der in der Organisation zulässigen Domänen ist (Dies ist Teil von Self-to-Self Spoofing oder organisationsinternem Spoofing).|

Anhand der Kopfzeilen einer Nachricht kann ein Administrator oder ein Endbenutzer erkennen, wie Office 365 zu dem Ergebnis kommt, dass es sich bei dem Absender um einen gefälschten Absender handeln könnte.

### <a name="differentiating-between-different-types-of-spoofing"></a>Unterscheidung zwischen verschiedenen Typen von Spoofing

Microsoft unterscheidet zwei verschiedene Typen von Spoofingnachrichten:

 **Organisationsinternes Spoofing**

Dies wird auch als Self-to-Self-Spoofing bezeichnet und tritt auf, wenn die Domäne in der „Von:“-Adresse der Empfängerdomäne oder wenn die Empfängerdomäne eine der in der Organisation [akzeptierten Domänen](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) entspricht oder wenn die Domäne in der „Von:“-Adresse Teil der gleichen Organisation ist.

Im folgenden Beispiel weist der Absender und der Empfänger die gleiche Domäne (contoso.com) auf. Leerzeichen werden in die E-Mail-Adresse eingefügt, um das Spambot-Harvesting auf dieser Seite zu verhindern):

Von: absender @ contoso.com

An: empfänger @ contoso.com

Im Folgenden weisen die Absender- und Empfängerdomäne die Organisationsdomäne (fabrikam.com) auf:

Von: absender @ foo.fabrikam.com

An: empfänger @ bar.fabrikam.com

Im folgenden Beispiel sind die Absender- und Empfängerdomänen unterschiedlich (microsoft.com und bing.com), sie gehören jedoch derselben Organisation an (d. h. beide sind Teil der in der Organisation akzeptierten Domänen):

Von: absender @ microsoft.com

An: empfänger @ bing.com

Nachrichten, für die das organisationsinternte Spoofing fehlschlägt, enthalten die folgenden Werte im Nachrichtenkopf:

X-Forefront-Antispam-Report: ...CAT:SPM/HSPM/PHSH;...SFTY:9.11

CAT ist die Kategorie der Nachricht. Sie wird in der Regel als SPM (Spam) gekennzeichnet, gelegentlich kann dies jedoch HSPM (Nachricht mit hoher Spamwahrscheinlichkeit) oder PHISH (Phishing) sein, je nachdem, welche anderen Typen von Mustern in der Nachricht auftreten.

SFTY ist die Sicherheitsstufe der Nachricht. Die erste Ziffer (9) gibt an, dass es sich bei der Nachricht um Phishing handelt, und die zweite Gruppe von Ziffern nach dem Punkt (11) gibt an, dass es sich um organisationsinternes Spoofing handelt.

Es gibt keinen spezifischen Ursachencode für die zusammengesetzte Authentifizierung für organisationsinternes Spoofing, der später in 2018 gekennzeichnet ist (Zeitachse noch nicht definiert).

 **Domänenübergreifendes Spoofing**

Dies tritt auf, wenn die sendende Domäne in der „Von“-Adresse eine externe Domäne für die empfangende Organisation ist. Nachrichten, für die die zusammengesetzte Authentifizierung aufgrund von domänenübergreifendem Spoofing fehlschlägt, enthalten die folgenden Werte in der Nachrichtenkopfzeile:

Authentication-Results: … compauth=fail reason=000/001

X-Forefront-Antispam-Report: ...CAT:SPOOF;...SFTY:9.22

In beiden Fällen ist die Nachricht mit einem roten Sicherheitstipp oder einer Entsprechung gekennzeichnet, die an die Sprache des Empfängerpostfachs angepasst ist:

![Roter Sicherheitstipp – Betrugserkennung](../media/a366156a-14e8-4c14-bfe5-2031b21936f8.jpg)

Sie können anhand der „Von“-Adresse und der Empfänger-E-Mail-Adresse oder anhand der E-Mail-Kopfzeilen zwischen organisationsinternem oder domänenübergreifendem Spoofing unterscheiden.

## <a name="how-customers-of-office-365-can-prepare-themselves-for-the-new-anti-spoofing-protection"></a>Vorbereitung von Office 365-Kunden auf den neuen Antispoofingschutz

### <a name="information-for-administrators"></a>Informationen für Administratoren

Als Administrator einer Organisation in Office 365 sollten Sie die folgenden Informationen beachten.

### <a name="understanding-why-email-authentication-is-not-always-enough-to-stop-spoofing"></a>Warum E-Mail-Authentifizierung nicht immer ausreicht, um Spoofing zu stoppen

Der neue Antispoofingschutz basiert auf der E-Mail-Authentifizierung (SPF, DKIM und DMARC), um eine Nachricht nicht als Spoofing zu kennzeichnen. Ein gängiges Beispiel hierfür ist, wenn die sendende Domäne bisher keine SPF-Datensätze veröffentlicht hat. Wenn SPF-Datensätze nicht vorhanden oder nicht ordnungsgemäß eingerichtet wurden, wird eine gesendete Nachricht als Spoofnachricht gekennzeichnet, solange die Nachricht nicht von der Back-End-Intelligenz von Microsoft als seriös eingestuft wird.

Bevor Antispoofing bereitgestellt wurde, sah eine Nachricht ohne SPF-, DKIM- und DMARC-Datensatz möglicherweise wie folgt aus:

```
Authentication-Results: spf=none (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=none
  action=none header.from=example.com;
From: sender @ example.com
To: receiver @ contoso.com
```
Nach dem Antispoofing wies sie den folgenden CompAuth-Wert auf, wenn Office 365 Enterprise E5, EOP oder ATP verwendet wurde:

```
Authentication-Results: spf=none (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=none
  action=none header.from=example.com; compauth=fail reason=001
From: sender @ example.com
To: receiver @ contoso.com

```

Wenn example.com dies durch Einrichten eines SPF-Eintrags, aber nicht eines DKIM-Eintrags behoben hat, würde die Nachricht die zusammengesetzte Authentifizierung bestehen, da die Domäne, die SPF übergeben hat, der Domäne in der „Von-Adresse entspricht:

```
Authentication-Results: spf=pass (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=bestguesspass
  action=none header.from=example.com; compauth=pass reason=109
From: sender @ example.com
To: receiver @ contoso.com
```

Wenn ein DKIM-Eintrag jedoch nicht ein SPF-Eintrag eingerichtet wurde, würde die Nachricht die zusammengesetzte Authentifizierung auch bestehen, da die Domäne in der DKIM-Signatur der Domäne in der „Von“-Adresse entspricht:

```
Authentication-Results: spf=none (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; contoso.com; dkim=pass
  (signature was verified) header.d=outbound.example.com;
  contoso.com; dmarc=bestguesspass action=none
  header.from=example.com; compauth=pass reason=109
From: sender @ example.com
To: receiver @ contoso.com
```

Ein Phisher kann möglicherweise auch SPF und DKIM einrichten und die Nachricht mit einer eigenen Domäne signieren, jedoch eine andere Domäne in der „Von“-Adresse angeben. Weder SPF noch DKIM erfordert, dass die Domäne mit der Domäne in der „Von“-Adresse übereinstimmt. Solange also example.com keine DMARC-Datensätze veröffentlicht hat, wird die Nachricht unter Verwendung von DMARC nicht als Spoofnachricht gekennzeichnet:

```
Authentication-Results: spf=pass (sender IP is 5.6.7.8)
  smtp.mailfrom=maliciousDomain.com; contoso.com; dkim=pass
  (signature was verified) header.d=maliciousDomain.com;
  contoso.com; dmarc=none action=none header.from=example.com;
From: sender @ example.com
To: receiver @ contoso.com
```

Im E-Mail-Client (Outlook, Outlook im Web oder einem anderen E-Mail-Client) wird nur die „Von“-Domäne angezeigt, nicht die Domäne in SPF oder DKIM. Dies kann dazu führen, dass der Benutzer in die Irre geführt wird und davon ausgeht, dass die Nachricht von example.com gesendet wurde, während sie jedoch tatsächlich von maliciousDomain.com stammt.

![Authentifizierte Nachricht, „Von“-Domäne stimmt jedoch nicht mit der Domäne überein, die von SPF oder DKIM übergeben wurde](../media/a9b5ab2a-dfd3-47c6-8ee8-e3dab2fae528.jpg)

Aus diesem Grund erfordert Office 365, dass die Domäne in der „Von“-Adresse der Domäne in der SPF- oder DKIM-Signatur entspricht. Wenn dies nicht der Fall ist, muss sie andere interne Signale aufweisen, die darauf hindeuten, dass es sich dabei um eine seriöse Nachricht handelt. Andernfalls wäre die zusammengesetzte Authentifizierung für die Nachricht fehlgeschlagen.

```
Authentication-Results: spf=none (sender IP is 5.6.7.8)
  smtp.mailfrom=maliciousDomain.com; contoso.com; dkim=pass
  (signature was verified) header.d=maliciousDomain.com;
  contoso.com; dmarc=none action=none header.from=contoso.com;
  compauth=fail reason=001
From: sender@contoso.com
To: someone@example.com
```

Der Antispoofingschutz von Office 365 schützt folglich vor Domänen ohne Authentifizierung und Domänen, die eine Authentifizierung eingerichtet haben, die Domäne in der „Von“-Adresse jedoch nicht der Domäne entspricht, die dem Benutzer als Absender der Nachricht angezeigt wird. Dies gilt sowohl für Domänen außerhalb und innerhalb Ihrer Organisation.

Sollten Sie jemals eine Nachricht empfangen, für die die zusammengesetzte Authentifizierung fehlgeschlagen ist und die als Spoofnachricht gekennzeichnet ist, obwohl SPF und DKIM erfolgreich waren, bedeutet dies, dass die Domäne, für die SPF und DKIM erfolgreich waren, nicht der Domäne in der „Von“-Adresse entspricht.

### <a name="understanding-changes-in-how-spoofed-emails-are-treated"></a>Grundlegendes zu Änderungen bei Behandlung von Spoof-E-Mails

Derzeit werden für alle Organisationen in Office 365 – ATP und Nicht-ATP – Nachrichten, für die DMARC mit einer Richtlinie zur Ablehnung oder Quarantäne fehlschlägt, als Spam markiert und es werden Aktionen für Nachrichten mit hoher Spamwahrscheinlichkeit oder normale Spamaktionen durchgeführt (je nachdem, ob andere Spamregeln sie zuerst als Spam kennzeichnen). Bei Erkennung von organisationsinternem Spoofing werden reguläre Spamaktionen durchgeführt. Dieses Verhalten muss nicht aktiviert werden und kann auch nicht deaktiviert werden.

Für domänenübergreifende Spoofingnachrichten wurden vor dieser Änderung jedoch reguläre Spam-, Phishing- und Malwareprüfungen durchgeführt, und wenn andere Teile des Filters diese als verdächtig eingestuft haben, wurden sie entsprechend als Spam, Phishing oder Malware gekennzeichnet. Mit dem neuen domänenübergreifenden Spoofingschutz werden für alle Nachrichten, die standardmäßig nicht authentifiziert werden können, die Aktionen durchgeführt, die unter „Antiphishing“ \> „Antispoofingrichtlinie“ definiert sind. Wenn eine nicht definiert ist, wird die Nachricht in den Junk-E-Mail-Ordner des Benutzers verschoben. In einigen Fällen werden auch verdächtigere Nachrichten mit dem roten Sicherheitstipp versehen.

Dies kann dazu führen, dass einige Nachrichten, die zuvor als Spam gekennzeichnet waren, weiterhin als Spam gekennzeichnet und zusätzlich mit einem roten Sicherheitstipp versehen sind; In anderen Fällen werden Nachrichten, die zuvor nicht als Spam gekennzeichnet waren, jetzt als Spam gekennzeichnet (CAT:SPOOF) und mit einem roten Sicherheitstipp versehen. In wieder anderen Fällen, werden die Spam- und Phishingnachrichten, die zuvor von Kunden in Quarantäne verschoben wurden, in den Junk-E-Mail-Ordner verschoben (Informationen zum Ändern dieses Verhaltens finden Sie unter [Ändern der Antispoofing-Einstellungen](#changing-your-anti-spoofing-settings)).

Es gibt viele verschiedene Typen von Spoofing (siehe [Unterscheidung zwischen verschiedenen Typen von Spoofing](#differentiating-between-different-types-of-spoofing) weiter oben in diesem Artikel), seit März 2018 ist jedoch die Art, die diese Nachrichten von Office 365 gehandhabt werden, noch nicht vereinheitlicht. Die folgende Tabelle enthält eine kurze Zusammenfassung, wobei das neue Verhalten beim domänenübergreifenden Spoofingschutz berücksichtigt wird:

|**Spoofingtyp**|**Kategorie**|**Sicherheitstipp hinzugefügt?**|**Gilt für**|
|:-----|:-----|:-----|:-----|
|DMARC fehlgeschlagen (Quarantäne oder ablehnen)|HSPM (Standard), kann auch SPM oder PHSH sein|Nein (derzeit nicht)|Alle Office 365-Kunden, Outlook.com|
|Self-to-Self|SPM|Ja|Alle Office 365-Organisationen, Outlook.com|
|Domänenübergreifend|SPOOF|Ja|Office 365 Advanced Threat Protection (ATP)- und E5-Kunden|

### <a name="changing-your-anti-spoofing-settings"></a>Ändern der Antispoofing-Einstellungen

Um die Antispoofing-Einstellungen zu erstellen oder zu ändern, navigieren Sie im Security &amp; Compliance Center unter der Registerkarte „Bedrohungsmanagement“ \> „Richtlinie“ zu „Antiphishing“ \> „Antispoofing-Einstellungen“. Wenn Sie noch keine Antiphishing-Einstellungen erstellt haben, müssen Sie sie erstellen:

![Antiphishing – Erstellen einer neuen Richtlinie](../media/9337ec91-270e-4fa7-9dfa-a51a2d1eb95e.jpg)

Wenn Sie bereits Einstellungen erstellt haben, können Sie sie zum Ändern auswählen:

![Antiphishing – Ändern eines vorhandenen Richtlinie](../media/75457a7c-882e-4984-80d1-21a12b42c53a.jpg)

Wählen Sie die Richtlinie aus, die Sie soeben erstellt haben, und fahren Sie mit den Schritten unter [Weitere Informationen zu Spoofintelligenz](learn-about-spoof-intelligence.md) fort.

![Aktivieren oder Deaktivieren von Antispoofing](../media/c49e2147-c954-443c-9144-1cbd139e1166.jpg)

![Aktivieren oder Deaktivieren von Antispoofing-Sicherheitstipps](../media/eec7c407-31fc-4f73-8325-307d82d1fb53.jpg)

So erstellen Sie eine neue Richtlinie mithilfe von PowerShell:

```powershell
$org = Get-OrganizationConfig
$name = "My first anti-phishing policy for " + $org.Name
# Note: The name should not exclude 64 characters, including spaces.
# If it does, you will need to pick a smaller name.
# Next, create a new anti-phishing policy with the default values
New-AntiphishPolicy -Name $Name
# Select the domains to scope it to
# Multiple domains are specified in a comma-separated list
$domains = "domain1.com, domain2.com, domain3.com"
# Next, create the anti-phishing rule, scope it to the anti-phishing rule
New-AntiphishRule -Name $name -AntiphishPolicy $name -RecipientDomainIs $domains
```

Möglicherweise möchten Sie die Antiphishing-Richtlinienparameter mithilfe von PowerShell entsprechend der Dokumentation unter [Set-AntiphishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Set-AntiPhishPolicy) ändern. Möglicherweise möchten Sie $name als Parameter angeben:

```powershell
Set-AntiphishPolicy -Identity $name <fill in rest of parameters>
```

Später in 2018 wird eine Richtlinie erstellt, die für alle Empfänger in der Organisation gilt, statt dass sie eine Standardrichtlinie erstellen und manuell angeben müssen (die nachstehenden Screenshots können vor der endgültigen Implementierung geändert werden).

![Standardrichtlinie für Antiphising](../media/1f27a0bf-e202-4e12-bbac-24baf013c8f9.jpg)

Im Gegensatz zu einer Richtlinie, die Sie erstellen, können Sie die Standardrichtlinie weder löschen, noch ihre Priorität ändern noch Benutzer, Domänen oder Gruppen auswählen, für die diese gelten soll.

![Details zur Antiphishing-Standardrichtlinie](../media/30c21ceb-df52-4c93-aa65-f44a55dc1009.jpg)

So richten Sie den Standardschutz mithilfe von PowerShell ein:

```powershell
$defaultAntiphishPolicy = Get-AntiphishPolicy | ? {$_.IsDefault -eq $true}
Set-AntiphishPolicy -Identity $defaultAntiphishPolicy.Name -EnableAntispoofEnforcement <$true|$false>
```

Sie sollten den Antispoofingschutz nur deaktivieren, wenn Sie einen anderen E-Mail-Server vor Office 365 verwenden (Weitere Informationen finden Sie unter „Legitime Szenarien zum Deaktivieren von Antispoofing“).

```powershell
$defaultAntiphishPolicy = Get-AntiphishiPolicy | ? {$_.IsDefault $true}
Set-AntiphishPolicy -Identity $defaultAntiphishPolicy.Name -EnableAntispoofEnforcement $false
```

> [!IMPORTANT]
> Wenn der erste Hop des E-Mail-Pfads Office 365 ist und zu viele seriöse E-Mails als Spoof gekennzeichnet werden, sollten Sie zunächst Absender festlegen, die Spoofing-E-Mails an Ihre Domäne senden dürfen (siehe Abschnitt *„Verwalten seriöser Absender, die nicht authentifiziert E-Mails senden“*). Wenn Sie immer noch zu viele falsch positive Ergebnisse erhalten (d. h. wenn seriöse Nachrichten als Spoofingnachrichten gekennzeichnet werden), wird nicht empfohlen, den Antispoofingschutz vollständig zu deaktivieren. In diesem Fall wird empfohlen, grundlegenden Schutz anstelle von hohem Schutz auszuwählen. Es ist besser, sich durch falsch positive Ergebnisse durchzuarbeiten, als Ihre Organisation Spoofing-E-Mails auszusetzen, die langfristig deutlich höhere Kosten verursachen könnten.

### <a name="managing-legitimate-senders-who-are-sending-unauthenticated-email"></a>Verwalten seriöser Absender, die nicht authentifizierte E-Mails senden

Office 365 verfolgt, wer nicht authentifizierte E-Mails an Ihre Organisation sendet. Wenn der Dienst annimmt, dass der Absender nicht seriös ist, wird die Nachricht als *Compauth*-Fehler gekennzeichnet. Die Nachricht wird als SPOOF eingestuft, obwohl dies von der Antispoofingrichtlinie abhängt, die auf die Nachricht angewendet wurde.

Als Administrator können Sie jedoch angeben, welche Absender Spoofingnachrichten senden dürfen und die Einstufung von Office 365 außer Kraft setzen.

#### <a name="method-1---if-your-organization-owns-the-domain-set-up-email-authentication"></a>Methode 1: Einrichten der E-Mail-Authentifizierung, wenn Ihre Organisation die Domäne besitzt

Diese Methode kann verwendet werden, um Probleme mit organisationsinternem und domänenübergreifendem Spoofing zu beheben, wenn Sie mehrere Mandanten besitzen oder mit diesen interagieren. Sie kann auch zum Beheben von Problemen mit domänenübergreifenden Spoofing verwendet werden, wenn Sie Nachrichten an andere Kunden innerhalb von Office 365 und an Drittanbieter senden, die von anderen Anbietern gehostet werden.

Weitere Informationen finden Sie unter [Office 365-Kunden](#customers-of-office-365).

#### <a name="method-2---use-spoof-intelligence-to-configure-permitted-senders-of-unauthenticated-email"></a>Methode 2: Verwenden der Spoofingintelligenz zum Konfigurieren zulässiger Absender nicht authentifizierter E-Mails

Sie können Sie auch [Spoofingintelligenz](learn-about-spoof-intelligence.md) verwenden, damit Absender nicht authentifizierte Nachrichten an Ihre Organisation senden können.

Für externe Domänen ist der gefälschte Benutzer die Domäne in der „Von“-Adresse. Die sendende Infrastruktur ist entweder die sendende IP-Adresse (aufgeteilt in CIDR-Bereiche von /24) oder die Organisationsdomäne des PTR-Eintrags (im folgenden Screenshot könnte die sendende IP 131.107.18.4 lauten, deren PTR-Eintrag outbound.mail.protection.outlook.com ist. Dies wird als outlook.com für die sendende Infrastruktur angezeigt).

Damit dieser Absender nicht authentifizierte E-Mails senden kann, ändern Sie die Einstellung von **No** zu **Yes**.

![Einrichten von zulässigen Spoofingabsendern](../media/d4334921-d820-4334-8217-788279701e94.jpg)

Sie können auch PowerShell verwenden, um bestimmten Absendern das Spoofing Ihrer Domäne zu gestatten:

```powershell
$file = "C:\My Documents\Summary Spoofed Internal Domains and Senders.csv"
```

```powershell
Get-PhishFilterPolicy -Detailed -SpoofAllowBlockList -SpoofType External | Export-CSV $file
```

![Abrufen von Spoofingabsendern aus Powershell](../media/0e27ffcf-a5db-4c43-a19b-fa62326d5118.jpg)

In der vorherigen Abbildung wurden zusätzliche Zeilenumbrüche hinzugefügt, damit dieses Screenshot an die Seite angepasst ist. Normalerweise stehen alle Werte in einer einzelnen Zeile.

Bearbeiten Sie die Datei, und suchen Sie nach der Zeile, die outlook.com und bing.com entspricht, und ändern Sie den „AllowedToSpoof“-Eintrag von „No“ zu „Yes“:

![Festlegen der Einstellung für Zulassen von Spoofing auf „Yes“ in PowerShell](../media/62340452-62d3-4958-9ce9-afe5275a870d.jpg)

Speichern Sie die Datei, und führen Sie anschließend Folgendes aus:

```powershell
$UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
```

Auf diese Weise kann bing.com nun nicht authentifizierte E-Mails von \*. outlook.com senden.

#### <a name="method-3---create-an-allow-entry-for-the-senderrecipient-pair"></a>Methode 3: Erstellen eines Zulassungseintrags für das Absender/Empfängerpaar

Sie können auch festlegen, dass alle Spamfilterungen für einen bestimmten Absender umgangen werden. Weitere Informationen hierzu finden Sie unter [Sicheres Hinzufügen eines Absenders zur Liste zugelassener Kontakte in Office 365](https://blogs.msdn.microsoft.com/tzink/2017/11/29/how-to-securely-add-a-sender-to-an-allow-list-in-office-365/).

Wenn Sie diese Methode verwenden, werden Spam- und einige Phishingfilterungen übersprungen, jedoch nicht die Malwarefilterung.

#### <a name="method-4---contact-the-sender-and-ask-them-to-set-up-email-authentication"></a>Methode 4: Kontaktieren des Absenders und Bitten um Einrichtung einer E-Mail-Authentifizierung

Aufgrund des Problems mit Spam und Phishing wird von Microsoft empfohlen, dass alle Absender eine E-Mail-Authentifizierung einrichten. Wenn Sie den Administrator der sendenden Domäne kennen, wenden Sie sich an ihn, und fordern Sie ihn an E-Mail-Authentifizierungsdatensätze einzurichten, damit Sie keine Überschreibungen hinzufügen müssen. Weitere Informationen finden Sie im weiteren Verlauf dieses Artikels unter [Administratoren von Domänen, die keine Office 365-Kunden sind](#administrators-of-domains-that-are-not-office-365-customers).

Obwohl es am Anfang möglicherweise schwierig wird, sendende Domänen zur Authentifizierung zu veranlassen, werden sie im Laufe der Zeit, da immer mehr E-Mail-Filter die Nachrichten dieser Domänen als Junk einstufen oder sie sogar ablehnen, die entsprechenden Datensätze einrichten, um eine bessere Zustellung sicherzustellen.

### <a name="viewing-reports-of-how-many-messages-were-marked-as-spoofed"></a>Anzeigen von Berichten über Anzahl von Nachrichten, die als Spoofing eingestuft wurden

Sobald Ihre Antispoofingrichtlinie aktiviert ist, können Sie die Funktionen der Bedrohungsuntersuchung und der Reaktion verwenden, um die Anzahl der Nachrichten anzurufen, die als Phishing eingestuft wurden. Wechseln Sie zu diesem Zweck zum Security &amp; Compliance Center (SCC) unter „Bedrohungsmanagement“ \> „Explorer“, legen Sie für Ansicht „Phishing“ fest, und gruppieren Sie nach Absenderdomäne oder Schutzstatus:

![Anzeigen der Anzahl von Nachrichten, die als Phishing eingestuft wurden](../media/de25009a-44d4-4c5f-94ba-9c75cd9c64b3.jpg)

Sie können die verschiedenen Berichte verwenden, um zu sehen, wie viele Nachrichten als Phishing eingestuft wurden, einschließlich Nachrichten, die als „SPOOF“ gekennzeichnet wurden. Weitere Informationen finden Sie unter [Erste Schritte mit der Office 365-Bedrohungsuntersuchung und -reaktion](office-365-ti.md).

Sie können derzeit jedoch nicht anzeigen, welche Nachrichten aufgrund von Spoofing im Gegensatz zu anderen Typen von Phishing (Allgemeines Phishing, Domänen- und Benutzeridentitätswechsel usw.) als solche gekennzeichnet wurden. Später können Sie dies jedoch über das Security &amp; Compliance Center anzeigen. Sobald Sie dies tun, können Sie diesen Bericht als Ausgangspunkt verwenden, um sendende Domänen zu identifizieren, die möglicherweise seriös sind und aufgrund von fehlgeschlagener Authentifizierung als Spoofing gekennzeichnet wurden.

Im folgenden Screenshot finden Sie ein Beispiel dafür, wie diese Daten aussehen können:

![Anzeigen von Phishingberichten nach Erkennungstyp](../media/dd25d63f-152c-4c55-a07b-184ecda2de81.jpg)

Für Nicht-ATP- und E5-Kunden sind diese Berichte später unter Threat Protection-Statusberichten (TPS) verfügbar, die jedoch mindestens um 24 Stunden verzögert sind. Diese Seite wird aktualisiert, da diese im Security &amp; Compliance Center integriert werden.

### <a name="predicting-how-many-messages-will-be-marked-as-spoof"></a>Vorhersagen zur Anzahl der Nachrichten, die als Spoofing gekennzeichnet werden

Sobald Office 365 entsprechend aktualisiert wurde, dass Sie die Erzwingung von Antispoofing deaktivieren können oder diese mit grundlegendem oder hohem Schutz verwenden können, können Sie anzeigen, wie sich die Anzahl der Nachrichten je nach Einstellungen ändert.  Wenn Antispoofing deaktiviert ist, können Sie sehen, wie viele Nachrichten als Spoofing gekennzeichnet werden, wenn Sie zu grundlegendem Schutz wechseln. Wenn grundlegender Schutz aktiviert ist, können Sie zum Beispiel anzeigen, wie viele Nachrichten als Spoofing gekennzeichnet werden, wenn Sie zum hohen Schutz wechseln.

Dieses Feature befindet sich zurzeit noch in der Entwicklung. Sobald weitere Details definiert sind, werden sowohl die Screenshots vom Security & Compliance Center als auch die PowerShell-Beispiele auf dieser Seite aktualisiert.

![Was-wäre-wenn-Bericht zum Aktivieren von Antispoofing](../media/fdd085ae-02c1-4327-a063-bfe9a32ff1eb.jpg)

![Mögliche UX für das Zulassen eines gefälschten Absenders](../media/53f9f73e-fb01-47f3-9a6d-850c1aef5efe.jpg)

### <a name="legitimate-scenarios-to-disable-anti-spoofing"></a>Legitime Szenarien zum Deaktivieren von Antispoofing

Dank Antispoofingschutz sind Kunden besser vor Phishingangriffen geschützt. Daher wird vom Deaktivieren des Antispoofingschutzes dringend abgeraten. Durch das Deaktivieren können Sie möglicherweise einige kurzfristige falsch positive Ergebnisse beheben, langfristig gesehen werden Sie jedoch einem höheren Risiko ausgesetzt. Der Aufwand für das Einrichten der Authentifizierung auf Absenderseite oder das Anpassen der Phishingrichtlinien ist in der Regel nur einmalig oder es ist nur eine minimale, regelmäßige Wartung erforderlich. Die Kosten für die Wiederherstellung nach einem Phishingangriff, bei dem Daten offengelegt wurden oder Assets kompromittiert wurden, sind jedoch deutlich höher.

Aus diesem Grund ist es besser, sich durch falsch positive Antispoofingergebnisse zu arbeiten, als den Antispoofingschutz zu deaktivieren.

Es gibt jedoch ein legitimes Szenario, in dem Antispoofing deaktiviert werden sollte, und zwar, wenn es zusätzliche E-Mail-Filterungsprodukte im Nachrichtenrouting gibt und Office 365 nicht der erste Hop im E-Mail-Pfad ist:

![Benutzerdefinierter MX-Eintrag verweist nicht auf Office 365](../media/62127c16-cfb8-4880-9cad-3c12d827c67e.jpg)

Der andere Server ist möglicherweise ein lokaler Exchange-E-Mail-Server, ein E-Mail-Filterungsgerät wie Ironport oder ein anderer in der Cloud gehosteter Dienst.

Wenn der MX-Eintrag der Empfängerdomäne nicht auf Office 365 verweist, ist es nicht erforderlich, den Antispoofingschutz zu deaktivieren, da Office 365 nach dem MX-Eintrag der empfangenden Domäne sucht und Antispoofing unterdrückt, wenn dieser auf einen anderen Dienst verweist. Wenn Sie nicht wissen, ob Ihre Domäne über einen anderen Server davor verfügt. können Sie vor einem anderen Server enthält, können Sie eine Website wie MX Toolbox verwenden, um nach dem MX-Eintrag zu suchen. Dieser kann in etwa wie folgt aussehen:

![MX-Eintrag gibt eine Domäne an, die nicht auf Office 365 verweist](../media/d868bb9f-3462-49aa-baea-9447a3ce4877.jpg)

Diese Domäne verfügt über einen MX-Eintrag, der nicht auf Office 365 verweist. Office 365 würde daher die Erzwingung von Antispoofing nicht anwenden.

Wenn der MX-Eintrag der empfangenden Domäne auf Office 365 *verweist*, sollten Sie Antispoofing auch dann deaktivieren, wenn es einen anderen Dienst vor Office 365 gibt. Das häufigste Beispiel ist die Verwendung einer Empfängerumschreibung:

![Routingdiagramm für die Empfängerumschreibung](../media/070d90d1-50a0-42e4-9fd3-920bc99a7cad.jpg)

Der MX-Eintrag der Domäne contoso.com verweist auf den lokalen Server, während der MX-Eintrag der Domäne @office365.contoso.net auf Office 365 verweist, da \*., protection.outlook.com oder \*.eo.outlook.com im MX-Eintrag enthalten ist:

![MX-Eintrag verweist auf Office 365, daher wahrscheinlich Empfängerumschreibung](../media/4101ad51-ef92-4907-b466-b41d14d344ca.jpg)

Unterscheiden Sie unbedingt, wann der MX-Eintrag einer empfangenden Domäne nicht auf Office 365 verweist und wann dieser einer Empfängerumschreibung unterzogen wurde. Es ist wichtig, den Unterschied zwischen diesen zwei Fällen zu erkennen.

Wenn Sie nicht sicher sind, ob Ihre empfangende Domäne einer Empfängerumschreibung unterzogen wurde, hilft es manchmal, die Nachrichtenkopfzeile anzuschauen.

a) Schauen Sie zunächst auf die Kopfzeilen der Nachricht für die Empfängerdomäne im Authentication-Results-Header:

```
Authentication-Results: spf=fail (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; office365.contoso.net; dkim=fail
  (body hash did not verify) header.d=simple.example.com;
  office365.contoso.net; dmarc=none action=none
  header.from=example.com; compauth=fail reason=001
```

Die Empfängerdomäne ist oben als fettformatierter roter Text gekennzeichnet, in diesem Fall ist dies office365.contoso.net. Diese kann möglicherweise von dem Empfänger im „An“-Feld abweichen:

An: Beispielempfänger \<empfänger @ contoso.com\>

Suchen Sie nach dem MX-Eintrag der aktuellen empfangenen Domäne. Wenn der Eintrag \*.protection.outlook.com, mail.messaging.microsoft.com, \*.eo.outlook.com oder mail.global.frontbridge.com enthält, bedeutet dies, dass der MX-Eintrag auf Office 365 verweist.

Wenn diese Werte nicht enthalten sind, verweist der MX-Eintrag nicht auf Office 365. Ein Tool, das Sie verwenden können, um dies zu überprüfen, ist MX Toolbox.

Bei diesem Beispiel besagt Folgendes, dass contoso.com, die Domäne, die wie der Empfänger aussieht, da sie im „An“-Feld enthalten war, einen MX-Eintrag aufweist, der auf einen lokalen Server verweist:

![MX-Eintrag verweist auf lokalen Server](../media/2444144a-9a90-4319-96b2-d115041f669f.jpg)

Der aktuelle Empfänger ist office365.contoso.net, dessen MX-Eintrag auf Office 365 verweist:

![MX verweist auf Office 365, muss eine Empfängerumschreibung sein](../media/10cf3245-9b50-475a-b655-d8a51f99d812.jpg)

Daher wurde diese Nachricht wahrscheinlich einer Empfängerumschreibung unterzogen.

b) Unterscheiden Sie als Nächstes zwischen allgemeinen Anwendungsfällen der Empfängerumschreibung. Wenn Sie beabsichtigen, die Empfängerdomäne in \*.onmicrosoft.com, statt in \*.mail.onmicrosoft.com umzuschreiben.

Nachdem Sie die endgültige Empfängerdomäne identifiziert haben, die hinter einen anderen Server geroutet wird, und der MX-Eintrag der Empfängerdomäne tatsächlich auf Office 365 verweist (wie in den DNS-Einträgen veröffentlicht), können Sie mit dem Deaktivieren von Antispoofing fortfahren.

Beachten Sie, dass Sie Antispoofing nicht deaktivieren sollten, wenn der erste Hop der Domäne in dem Routingpfad Office 365 ist. Sie sollten Antispoofing nur deaktivieren, wenn sich dieser hinter einem oder mehreren Diensten befindet.

### <a name="how-to-disable-anti-spoofing"></a>Deaktivieren von Antispoofing

Wenn Sie bereits eine Antiphishingrichtlinie erstellt haben, legen Sie den EnableAntispoofEnforcement-Parameter auf $false fest:

```
$name = "<name of policy>"
Set-AntiphishPolicy -Identity $name -EnableAntiSpoofEnforcement $false

```

Wenn Sie den Namen der Richtlinie (oder Richtlinien) nicht kennen, die deaktiviert werden soll, können Sie diesen anzeigen:

```
Get-AntiphishPolicy | fl Name
```

Wenn Sie noch keine Antiphishingrichtlinien erstellt haben, können Sie eine erstellen und sie dann deaktivieren (selbst wenn Sie über keine Richtlinie verfügen, wird Antispoofing weiterhin angewendet; später in 2018 wird eine Standardrichtlinie erstellt, die Sie dann deaktivieren können, statt eine neue zu erstellen). Dazu müssen Sie die folgenden Schritte ausführen:

```
$org = Get-OrganizationConfig
$name = "My first anti-phishing policy for " + $org.Name
# Note: If the name is more than 64 characters, you will need to choose a smaller one
```

```
# Next, create a new anti-phishing policy with the default values
New-AntiphishPolicy -Name $Name
# Select the domains to scope it to
# Multiple domains are specified in a comma-separated list
$domains = "domain1.com, domain2.com, domain3.com"
# Next, create the anti-phishing rule, scope it to the anti-phishing rule
New-AntiphishRule -Name $name -AntiphishPolicy -RecipientDomainIs $domains
# Finally, scope the anti-phishing policy to the domains
Set-AntiphishPolicy -Identity $name -EnableAntispoofEnforcement $false

```

Antispoofing kann nur mit dem Cmdlet deaktiviert werden (später ist dies auch über das Security &amp; Compliance Center möglich). Wenn Sie keinen Zugriff auf PowerShell haben, erstellen Sie ein Supportticket.

Beachten Sie, dass dies nur für Domänen mit indirektem Routing beim Senden an Office 365 angewendet werden sollte. Sie sollten es vermeiden, Antispoofing zu deaktivieren, um einige falsch positive Ergebnisse zu vermeiden, da es langfristig gesehen besser ist, diese durchzuarbeiten.

### <a name="information-for-individual-users"></a>Informationen für einzelne Benutzer

Einzelne Benutzer können nur eingeschränkt mit Antispoofing-Sicherheitstipps interagieren. Es gibt jedoch mehrere Möglichkeiten, Probleme bei allgemeinen Szenarien zu beheben.

### <a name="common-scenario-1---discussion-lists"></a>Allgemeines Szenario Nr. 1 – Diskussionslisten

Bei Diskussionslisten sind Probleme mit Antispoofing bekannt, die darin begründet sind, wie Nachrichten weitergeleitet und Inhalte geändert werden, wobei die ursprüngliche „Von“-Adresse beibehalten wird.

Beispiel: Ihre E-Mail-Adresse lautet „user@contoso.com“, Sie interessieren sich für Vögelbeobachtung und treten der Diskussionsliste birdwatchers@example.com bei. Wenn Sie eine Nachricht an die Diskussionsliste senden, wird diese möglicherweise auf folgende Weise gesendet:

**Von:** John Doe \<user @ contoso.com\>

**An:** Diskussionsliste für Vögelbeobachtung \<birdwatchers @ example.com\>

**Betreff:** Großartiger Blick auf Eichelhäher am Mount Rainier diese Woche

Jemand Interesse an diesem Ausblick von dieser Woche am Mount Rainier?

Wenn die E-Mail-Liste die Nachricht erhält, wird die Nachricht formatiert, der Inhalt der Nachricht wird geändert und sie wird an die Mitglieder der Diskussionsliste gesendet, die aus Teilnehmern vieler verschiedener E-Mail-Empfänger besteht.

**Von:** John Doe \<user @ contoso.com\>

**An:** Diskussionsliste für Vögelbeobachtung \<birdwatchers @ example.com\>

**Betreff:** [BIRDWATCHERS] Großartiger Blick auf Eichelhäher am Mount Rainier diese Woche

Jemand Interesse an diesem Ausblick von dieser Woche am Mount Rainier?

---

Diese Nachricht wurde an die Diskussionsgruppe Vögelbeobachtung gesendet. Sie können sich jederzeit wieder abmelden.

Die oben angezeigte Nachricht hat die gleiche „Von“-Adresse (user @ contoso.com), die ursprüngliche Nachricht wurde jedoch geändert, indem der Betreffzeile ein Tag und eine Fußzeile am Ende der Nachricht hinzugefügt wurde. Diese Art von Nachrichtänderung ist in Mailinglisten üblich und kann zu falsch positiven Ergebnissen führen.

Wenn Sie oder andere Personen in Ihrer Organisation Administrator der Mailingliste sind, können Sie sie möglicherweise konfigurieren, damit sie die Antispoofingprüfungen besteht.

- Lesen Sie die häufig gestellten Fragen unter DMARC.org: [I operate a mailing list and I want to interoperate with DMARC, what should I do?](https://dmarc.org/wiki/FAQ#I_operate_a_mailing_list_and_I_want_to_interoperate_with_DMARC.2C_what_should_I_do.3F)

- Lesen Sie die Anweisungen in diesem Blogbeitrag: [A tip for mailing list operators to interoperate with DMARC to avoid failures](https://blogs.msdn.microsoft.com/tzink/2017/03/22/a-tip-for-mailing-list-operators-to-interoperate-with-dmarc-to-avoid-failures/)

- Ziehen Sie es in Erwägung, Updates für diesen Mailinglistserver zu installieren, damit ARC unterstützt wird. Informationen dazu finden Sie unter [https://arc-spec.org](https://arc-spec.org/)

Wenn Sie nicht Besitzer der Mailingliste sind:

- Sie können den Verwalter der Mailingliste dazu auffordern, eine der genannten Optionen zu implementieren (er sollte auch eine E-Mail-Authentifizierung für die Domäne einrichten, von der diese Mailingliste gesendet wird).

- Sie können in Ihrem E-Mail-Client Postfachregeln zum Verschieben von Nachrichten in den Posteingang erstellen. Sie können auch den Administrator Ihrer Organisation auffordern, Zulassungsregeln einzurichten oder diese außer Kraft zu setzen, wie im Abschnitt „Verwalten seriöser Absender, die nicht authentifizierte E-Mails senden“ beschrieben.

- Sie können ein Supportticket für Office 365 erstellen, um eine Außerkraftsetzung für die Mailingliste zu erstellen, damit sie als seriöser Empfänger gehandhabt wird.

### <a name="other-scenarios"></a>Sonstige Szenarien

1. Wenn keine der genannten allgemeinen Szenarien auf Ihre Situation zutrifft, senden Sie die Nachricht als falsch positives Ergebnis an Microsoft zurück. Weitere Informationen finden Sie im weiteren Verlauf dieses Artikels im Abschnitt [Wie kann ich Spamnachrichten oder Nachrichten, die kein Spam sind, an Microsoft melden?](#how-can-i-report-spam-or-non-spam-messages-back-to-microsoft).

2. Sie können auch Ihren E-Mail-Administrator kontaktieren, der ein Supportticket bei Microsoft öffnen kann. Das Microsoft-Entwicklungsteam prüft anschließend, warum die Nachricht als Spoofingnachricht eingestuft wurde.

3. Wenn Sie wissen, wer der Absender ist und darauf vertrauen, dass dieser nicht gespooft wurde, können Sie diesem Absender antworten und angeben, dass er Nachrichten von einem E-Mail-Server sendet, der nicht authentifiziert ist. Dies führt manchmal dazu, der ursprüngliche Absender den IT-Administrator kontaktiert, der die erforderlichen E-Mail-Authentifizierungsdatensätze einrichtet.

Wenn genügend Absender den Domänenbesitzern antworten und darum bitten, E-Mail-Authentifizierungsdatensätze einzurichten, werden diese möglicherweise dazu angespornt, die entsprechenden Maßnahmen zu ergreifen. Microsoft arbeitet zwar auch mit Domänenbesitzern zusammen, um die erforderlichen Datensätze zu veröffentlichen, es hilft jedoch, wenn einzelne Benutzer sie zusätzlich dazu auffordern.

4. Fügen Sie optional den Absender der Liste der sicheren Absender hinzu. Bedenken Sie jedoch, dass wenn dieses Konto von einem Phisher gespooft wurde, wird die Nachricht an Ihr Postfach übermittelt. Daher sollte diese Option nur in Ausnahmefällen verwendet werden.

## <a name="how-senders-to-microsoft-should-prepare-for-anti-spoofing-protection"></a>Vorbereitung der Absender, die Nachrichten an Microsoft senden, auf den Antispoofingschutz

Wenn Sie ein Administrator sind, der derzeit Nachrichten an Microsoft sendet, entweder Office 365 oder Outlook.com, sollten Sie sicherstellen, dass Ihre E-Mail ordnungsgemäß authentifiziert wird, da sie andernfalls als Spam oder Phishing eingestuft wird.

### <a name="customers-of-office-365"></a>Office 365-Kunden

Wenn Sie Office 365-Kunde sind und Office 365 zum Senden ausgehender E-Mails verwenden:

- [Richten Sie für Ihre Domänen SPF in Office 365 zum Verhindern von Spoofing ein](set-up-spf-in-office-365-to-help-prevent-spoofing.md).

- [Verwenden Sie für Ihre primären Domänen DKIM zum Überprüfen ausgehender E-Mails, die von Ihrer benutzerdefinierten Domäne in Office 365 gesendet werden](use-dkim-to-validate-outbound-email.md).

- [Ziehen Sie es in Erwägung, DMARC-Einträge für Ihre Domäne](use-dmarc-to-validate-email.md) einzurichten, um zu ermitteln, wer zu Ihren seriösen Absendern zählt.

Microsoft bietet keine detaillierten Implementierungsrichtlinien für SPF, DKIM und DMARC. Es gibt jedoch eine Menge Informationen, die online veröffentlicht sind. Es gibt auch Drittanbieter, die Ihrer Organisation dabei helfen, E-Mail-Authentifizierungsdatensätze einzurichten.

### <a name="administrators-of-domains-that-are-not-office-365-customers"></a>Administratoren von Domänen, die keine Office 365-Kunden sind

Wenn Sie ein Domänenadministrator, jedoch kein Office 365-Kunde sind:

- Sie sollten SPF einrichten, um die sendenden IP-Adressen Ihrer Domäne zu veröffentlichen, und DKIM (falls verfügbar) zum digitalen Signieren von Nachrichten einrichten. Sie können auch das Einrichten von DMARC-Datensätzen in Erwägung ziehen.

- Wenn Sie Massen-E-Mail-Absender haben, die in Ihrem Auftrag E-Mails senden, sollten Sie mit diesen daran arbeiten, E-Mails so senden, dass die sendende Domäne in der „Von“-Adresse (falls Sie der Besitzer sind) der Domäne entspricht, die SPF oder DMAR besteht.

- Wenn Sie über lokale E-Mail-Server verfügen oder Nachrichten von einem Software-as-a-Service-Anbieter oder einem in der Cloud gehosteten Dienst wie Microsoft Azure, GoDaddy, Rackspace, Amazon Web Services gesendet werden, sollten Sie sicherstellen, dass diesen der SPF-Eintrag hinzugefügt wird.

- Wenn es sich bei Ihrer Domäne um eine kleine Domäne handelt, die von einem ISP gehostet wird, sollten Sie den SPF-Eintrag entsprechend den Anweisungen einrichten, die Ihnen von Ihrem ISP bereitgestellt wurden. Die meisten Internetdienstanbieter stellen diese Art von Anweisungen bereit. Diese finden Sie auf den Supportseiten des jeweiligen Anbieters.

- Auch wenn Sie bisher keine E-Mail-Authentifizierungsdatensätze veröffentlichen mussten und alles einwandfrei funktioniert hat, müssen Sie trotzdem E-Mail-Authentifizierungsdatensätze veröffentlichen, um Nachrichten an Microsoft zu senden. Auf diese Weise helfen Sie bei der Bekämpfung von Phishing und dabei, das Risiko zu reduzieren, dass entweder Sie oder Organisationen an die Sie Nachrichten senden, Opfer von Phishing werden.

### <a name="what-if-you-dont-know-who-sends-email-as-your-domain"></a>Was tun, wenn ich nicht weiß, wer E-Mails als meine Domäne sendet?

Viele Domänen veröffentlichen keine SPF-Einträge, da sie nicht wissen, wer all die Absender sind. Das ist in Ordnung. Sie müssen sie nicht alle kennen. Sie sollten stattdessen damit beginnen, einen SPF-Eintrag für diejenigen zu veröffentlichen, die Sie kennen, insbesondere diejenigen, wo sich der Datenverkehr Ihres Unternehmens befindet, und eine neutrale SPF-Richtlinie veröffentlichen: ?all:

example.com IN TXT "v=spf1 include:spf.example.com ?all"

Eine neutrale SPF-Richtlinie bedeutet, dass jede E-Mail, die von Ihrer Unternehmensinfrastruktur stammt, die E-Mail-Authentifizierung bei allen anderen E-Mail-Empfängern besteht. Eine E-Mail, die von Absendern stammt, die Sie nicht kennen, fällt auf neutral zurück, was fast damit gleichzusetzen ist, dass keine SPF-Einträge veröffentlicht wurden.

Beim Senden an Office 365 wird E-Mail, die vom Unternehmensdatenverkehr stammt, als authentifiziert gekennzeichnet. Eine E.Mail, die jedoch aus anderen Quellen stammt, die Sie nicht kennen, wird möglicherweise weiterhin als Spoofing gekennzeichnet (je nachdem, ob Office 365 sie authentifizieren kann). Dies stellt jedoch immer noch eine Verbesserung dazu dar, dass alle E-Mails von Office 365 als Spoofing markiert wurden.

Sobald Sie mit einem SPF-Eintrag mit einer Fallbackrichtlinie von „?all“ begonnen haben, können Sie schrittweise immer mehr sendende Infrastruktur hinzufügen und dann eine strengere Richtlinie veröffentlichen.

### <a name="what-if-you-are-the-owner-of-a-mailing-list"></a>Was tun, wenn ich der Besitzer der Mailingliste bin?

Siehe [Allgemeines Szenario Nr. 1 – Diskussionslisten](#common-scenario-1---discussion-lists).

### <a name="what-if-you-are-an-infrastructure-provider-such-as-an-internet-service-provider-isp-email-service-provider-esp-or-cloud-hosting-service"></a>Was tun, wenn ich ein Infrastrukturanbieter wie Internetdienstanbieter (ISP), E-Mail-Dienstanbieter (ESP) oder gehosteter Clouddienst bin?

Wenn Sie E-Mails einer Domäne hosten und diese E-Mails sendet oder eine Hostinginfrastruktur anbieten, die E-Mails senden kann, sollten Sie wie folgt vorgehen:

- Stellen Sie sicher, dass Sie Ihren Kunden die nötige Dokumentation mit den Informationen dazu bereitstellen, was in den SPF-Einträgen veröffentlicht werden muss.

- Ziehen Sie in Erwägung, ausgehende E-Mails mit DKIM-Signaturen zu signieren, selbst wenn der Kunde dies nicht explizit eingerichtet hat (Signieren mit Standarddomäne). Sie können die E-Mail sogar doppelt mit DKIM-Signaturen signieren (mit der Domäne des Kunden, falls eingerichtet, und mit der DKIM-Signatur Ihres Unternehmens).

Die Zustellbarkeit an Microsoft ist auch nicht, wenn Sie E-Mails, die von Ihrer Plattform stammen, authentifizieren, es wird jedoch zumindest sichergestellt, dass Ihre E-Mail nicht als Junk-E-Mail von Microsoft eingestuft wird, weil sie nicht authentifiziert ist. Weitere Informationen zu E-Mail-Filterung in Outlook.com finden Sie auf der [Outlook.com Postmaster-Seite](https://postmaster.live.com/pm/postmaster.aspx).

Weitere Informationen zu bewährten Methoden für Dienstanbieter finden Sie unter [M3AAWG Mobile Messaging Best Practices for Service Providers](https://www.m3aawg.org/sites/default/files/M3AAWG-Mobile-Messaging-Best-Practices-Service-Providers-2015-08.pdf).

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

### <a name="why-is-microsoft-making-this-change"></a>Warum nimmt Microsoft diese Änderung vor?

Aufgrund der Auswirkungen von Phishingangriffen und der Tatsache, dass es die E-Mail-Authentifizierung seit über 15 Jahren gibt, ist Microsoft der Ansicht, dass das Risiko, nicht authentifizierte E-Mails weiterhin zuzulassen, höher ist, als das Risiko, dass seriöse E-Mails verloren gehen könnten.

### <a name="will-this-change-cause-legitimate-email-to-be-marked-as-spam"></a>Wird diese Änderung auch dazu führen, dass seriöse E-Mails als Spam gekennzeichnet werden?

Zunächst werden einige Nachrichten als Spam gekennzeichnet. Im Laufe der Zeit werden Absender jedoch entsprechende Anpassungen vornehmen und die Menge der fälschlicherweise als Spoofingnachrichten gekennzeichneten Nachrichten wird für die meisten E-Mail-Pfade überschaubar sein.

Microsoft selbst hat diese Funktion einige Wochen vor der Bereitstellung für die Kunden implementiert. Zunächst gab es zwar Störungen, diese gingen jedoch allmählich zurück.

### <a name="will-microsoft-bring-this-feature-to-outlookcom-and-non-advanced-threat-protection-customers-of-office-365"></a>Wird diese Funktion auch für Outlook.com und Office 365-Kunden ohne Advanced Threat Protection implementiert?

Die Antispoofingtechnologie von Microsoft wurde ursprünglich für die Organisationen bereitgestellt, die ein Office 365 Enterprise E5-Abonnement hatten oder das Add-On Office 365 Advanced Threat Protection (ATP) für ihr Abonnement erworben haben. Ab Oktober 2018 wurde der Schutz auf Organisationen erweitert, die über Exchange Online Protection (EOP) verfügen. In Zukunft wird der Schutz möglicherweise auf Outlook.com erweitert. Sollte dies der Fall sein, werden möglicherweise einige Funktionen wie Berichterstellung und benutzerdefinierte Außerkraftsetzungen nicht angewendet.

### <a name="how-can-i-report-spam-or-non-spam-messages-back-to-microsoft"></a>Wie kann ich Spamnachrichten oder Nachrichten, die kein Spam sind, an Microsoft melden?

Sie können entweder das [Add-In „Nachricht melden“ für Outlook](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2) verwenden oder, falls es nicht installiert ist, [Spamnachrichten, Nachrichten, die kein Spam sind, und Phishingnachrichten zur Analyse an Microsoft übermitteln](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md).

### <a name="im-a-domain-administrator-who-doesnt-know-who-all-my-senders-are"></a>Ich bin ein Domänenadministrator, der nicht alle Absender kennt.

Siehe [Administratoren von Domänen, die keine Office 365-Kunden sind](#administrators-of-domains-that-are-not-office-365-customers).

### <a name="what-happens-if-i-disable-anti-spoofing-protection-for-my-organization-even-though-office-365-is-my-primary-filter"></a>Was passiert, wenn ich den Antispoofingschutz für meine Organisation deaktiviere, wenn Office 365 mein primärer Filter ist?

Dies wird nicht empfohlen, da dies dazu führt, dass mehr Nachrichten nicht als Phishing- und Spamnachrichten erkannt werden. Nicht alle Phishingnachrichten sind Spoofingnachrichten und nicht alle Spoofingnachrichten werden übersehen. Ihr Risiko ist jedenfalls höher als bei einem Kunden, der Antispoofing aktiviert.

### <a name="does-enabling-anti-spoofing-protection-mean-i-will-be-protected-from-all-phishing"></a>Bin ich vor allen Phishingangriffen geschützt, wenn ich den Antispoofingschutz aktiviere?

Leider nicht, denn Phisher werden sich darauf einstellen und andere Verfahren wie kompromittierte Konten oder Einrichten von Konten von kostenlosen Diensten verwenden. Der Antiphishingschutz funktioniert jedoch viel besser für die Erkennung dieser Arten von Phishingmethoden, da die Schutzebenen von Office 365 zusammenwirken und aufeinander aufbauen.

### <a name="do-other-large-email-receivers-block-unauthenticated-email"></a>Werden nicht authentifizierte E-Mails von anderen großen E-Mail-Empfängern blockiert?

Fast alle großen E-Mail-Empfänger implementieren die herkömmlichen Standards wie SPF, DKIM und DMARC. Einige Empfänger verfügen über andere Prüfungen, die strenger als diese Standards sind, nur wenige gehen jedoch soweit wie Office 365, dass nicht authentifizierte E-Mails blockiert und wie Spoofing-E-Mails gehandhabt werden. Allerdings wird der Großteil der Branche bei dieser speziellen Art von E-Mails zunehmend strenger, insbesondere aufgrund des Problems mit Phishingangriffen.

### <a name="do-i-still-need-the-advanced-spam-filtering-option-enabled-for-spf-hard-fail-if-i-enable-anti-spoofing"></a>Muss die Option „Erweiterte Spamfilterung“ für „SPF Hard Fail“ weiterhin aktiviert sein, wenn der Antispoofingschutz aktiviert ist?

Nein, diese Option ist nicht mehr erforderlich, da der Antispoofingschutz nicht nur „SPF Hard Fails“ berücksichtigt, sondern viel umfassendere Kriterien. Wenn der Antispoofingschutz und die Option „SPF Hard Fail“ aktiviert sind, erhalten Sie wahrscheinlich mehr falsch positive Ergebnisse. Es wird empfohlen, diese Funktion zu deaktivieren, da sie fast keinen zusätzlichen Schutz vor Spam oder Phishing bietet und meistens falsch positive Ergebnisse generiert.

### <a name="does-sender-rewriting-scheme-srs-help-fix-forwarded-email"></a>Hilft Sender Rewriting Scheme (SRS) beim Beheben von Problemen mit weitergeleiteten E-Mails?

Mit SRS kann das Problem mit weitergeleiteten E-Mails nur teilweise behoben werden. Durch die Umschreibung von „SMTP MAIL FROM“ kann SRS sicherstellen, dass die weitergeleitete Nachricht die SPF-Prüfung am nächsten besteht. Da Antispoofing jedoch auf der „Von“-Adresse in Kombination mit MAIL FROM oder der signierenden DKIM-Domäne (oder anderen Signalen) basiert, reicht es nicht aus, um zu verhindern, dass die weitergeleitete E-Mail als Spoofing-E-Mail eingestuft wird.
