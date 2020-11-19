---
title: Antispoofingschutz
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
search.appverid:
- MET150
ms.assetid: d24bb387-c65d-486e-93e7-06a4f1a436c0
ms.collection:
- M365-security-compliance
- Strat_O365_IP
- m365initiative-defender-office365
ms.custom:
- TopSMBIssues
- seo-marvel-apr2020
localization_priority: Priority
description: Administratoren können sich über die Anti-Spoofing-Funktionen informieren, die in Exchange Online Protection (EOP) verfügbar sind und die dazu beitragen können, Phishing-Angriffe von gefälschten Absendern und Domänen abzuschwächen.
ms.openlocfilehash: 57d6dc8d9c1935578db15abdbb3e17e72bb64257
ms.sourcegitcommit: ce46d1bd67091d4ed0e2b776dfed55e2d88cdbf4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "49130829"
---
# <a name="anti-spoofing-protection-in-eop"></a>Schutz vor Spoofing in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


In Microsoft 365-Organisationen mit Postfächern in Exchange Online oder eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer enthält EOP Funktionen zum Schutz Ihrer Organisation vor gefälschten Absendern.

Wenn es um den Schutz der Benutzer geht, nimmt Microsoft die Bedrohung durch Phishing ernst. Spoofing ist eine gängige Technik, die von Angreifern verwendet wird. **Diese gefälschten („Spoofing“-)Nachrichten scheinen von einer anderen Quelle als der tatsächlichen Quelle zu stammen**. Diese Methode wird häufig bei Phishingkampagnen verwendet, die darauf abzielen, an Anmeldeinformationen des Benutzers zu gelangen. Die Anti-Spoofing-Technologie in EOP prüft speziell auf Fälschungen des „Von“-Headers im Nachrichtentext (diese Information wird genutzt, um den Absender in E-Mail-Clients anzuzeigen). Wenn EOP mit hoher Wahrscheinlichkeit zu dem Ergebis kommt, dass der „Von“-Header gefälscht ist, wird die Nachricht als Spoof identifiziert.

Die folgenden Anti-Spoofing-Technologien stehen in EOP zur Verfügung:

- **Spoofing Intelligence**: Überprüfen Sie gefälschte Nachrichten von Absendern in internen und externen Domänen und lassen Sie diese Absender zu oder blockieren Sie sie. Weitere Informationen finden Sie unter [Konfigurieren der Spoofintelligenz in Microsoft 365](learn-about-spoof-intelligence.md).

- **Anti-Phishing-Richtlinien**: In EOP können Sie mit Anti-Phishing-Richtlinien Spoofing-Informationen ein- oder ausschalten, nicht authentifizierte Absenderkennung in Outlook ein- oder ausschalten und die Aktion für blockierte Spoofing-Absender festlegen (Verschieben in den Junk-E-Mail-Ordner oder Quarantäne). Erweiterte Anti-Phishing-Richtlinien, die in Microsoft Defender für Office 365 verfügbar sind, umfassen außerdem Einstellungen zum Schutz vor Identitätsvortäuschung (geschützte Absender und Domänen), Postfach-Intelligence-Einstellungen und anpassbare erweiterte Phishing-Schwellenwerte. Weitere Informationen finden Sie unter [Anti-Phishing-Richtlinien in Microsoft 365](set-up-anti-phishing-policies.md).

- **E-Mail-Authentifizierung**: ein wesentlicher Bestandteil aller Anti-Spoofing-Anstrengungen ist die Verwendung von E-Mail-Authentifizierung (auch als E-Mail-Überprüfung bezeichnet) durch SPF-, DKIM- und DMARC-Einträge in DNS. Sie können diese Einträge für Ihre Domänen so konfigurieren, dass Ziel-E-Mail-Systeme die Gültigkeit von Nachrichten überprüfen können, die von Absendern in Ihren Domänen stammen. Bei eingehenden Nachrichten erfordert Microsoft 365 eine E-Mail-Authentifizierung für Absenderdomänen. Weitere Informationen finden Sie unter [E-Mail-Authentifizierung in Microsoft 365](email-validation-and-authentication.md).

Ab Oktober 2018 ist der Anti-Spoofing-Schutz in EOP verfügbar.

EOP analysiert und blockiert Nachrichten, die nicht durch die Kombination von standardmäßigen E-Mail-Authentifizierungsmethoden und Absender-Reputations-Techniken authentifiziert werden können.

![EOP-Anti-Spoofing-Prüfungen](../../media/eop-anti-spoofing-protection.png)

## <a name="how-spoofing-is-used-in-phishing-attacks"></a>Verwenden von Spoofing bei Phishingangriffen

Spoofingnachrichten weisen die folgenden negativen Auswirkungen für Benutzer auf:

- **Gefälschte Nachrichten täuschen Benutzer**: Eine gefälschte Nachricht kann den Empfänger dazu bringen, auf einen Link zu klicken und seine Anmeldeinformationen preiszugeben, Malware herunterzuladen oder mit vertraulichen Inhalten auf eine Nachricht zu antworten (letzteres wird als „Business Email Compromise“, kurz „BEC“, bezeichnet).

  Die folgende Nachricht ist ein Beispiel für Phishing. Sie nutzt den gefälschten Absender msoutlook94@service.outlook.com:

  ![Phishingnachricht, die die Identität von service.outlook.com angenommen hat](../../media/1a441f21-8ef7-41c7-90c0-847272dc5350.jpg)

  Diese Nachricht kam nicht von service.outlook.com, aber der Angreifer hat das **Von**-Kopfzeilenfeld gefälscht, damit es so wirkt, als ob dies der Fall wäre. Dies war ein Versuch, den Empfänger dazu zu bringen, auf den Link **Kennwort ändern** zu klicken, um seine Anmeldeinformationen preiszugeben.

  Die folgende Nachricht ist ein Beispiel für BEC, welche die gefälsche E-Mail-Domäne contoso.com verwendet:

  ![Phishingnachricht – Business Email Compromise](../../media/da15adaa-708b-4e73-8165-482fc9182090.jpg)

  Die Nachricht wirkt legitim, doch der Absender ist gefälscht.

- **Benutzer können echte Nachrichten nicht von gefälschten unterscheiden**: selbst Benutzer, die sich über Phishing informieren, können Schwierigkeiten haben, die Unterschiede zwischen echten und gefälschten Nachrichten zu erkennen.

  Die folgende Nachricht ist ein Beispiel einer echten Nachricht zur Kennwortrücksetzung vom Microsoft Security-Konto:

  ![Seriöse Nachricht zur Kennwortzurücksetzung von Microsoft](../../media/58a3154f-e83d-4f86-bcfe-ae9e8c87bd37.jpg)

  Die Nachricht stammt tatsächlich von Microsoft, jedoch sind Benutzer inzwischen darauf konditioniert, misstrauisch zu sein. Da es schwierig ist, zwischen einer echten Nachricht zur Kennwortzurücksetzung und einer gefälschten zu unterscheiden, könnten Benutzer diese Nachricht ignorieren, sie als Spam melden oder sie unnötigerweise als Phishing-Versuch an Microsoft melden.

## <a name="different-types-of-spoofing"></a>Verschiedene Typen von Spoofing

Microsoft unterscheidet zwei verschiedene Typen von gefälschten Nachrichten:

- **Organisationsinternes Spoofing**: wird auch als _Self-to-Self_-Spoofing bezeichnet. Zum Beispiel:

  - Absender und Empfänger befinden sich in derselben Domäne:
    > Von: chris@contoso.com <br/> An: michelle@contoso.com

  - Absender und Empfänger befinden sich in Subdomänen derselben Domäne:
    > Von: laura@marketing.fabrikam.com <br/> An: julia@engineering.fabrikam.com

  - Der Absender und der Empfänger befinden sich in unterschiedlichen Domänen, die derselben Organisation angehören (dies bedeutet, dass beide Domänen als [akzeptierte Domänen](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) in derselben Organisation konfiguriert sind):
    > Von: absender @ microsoft.com <br/> An: empfänger @ bing.com

    In den E-Mail-Adressen werden Leerzeichen verwendet, um die Sammlung durch Spambots zu verhindern.

  Nachrichten, bei denen die [zusammengesetzte Authentifizierung](email-validation-and-authentication.md#composite-authentication) aufgrund von organisationsinternem Spoofing fehlschlägt, enhalten die folgenden Werte im Header:

  `Authentication-Results: ... compauth=fail reason=6xx`

  `X-Forefront-Antispam-Report: ...CAT:SPOOF;...SFTY:9.11`

  - `reason=6xx` zeigt organisationsinternes Spoofing an.

  - SFTY ist die Sicherheitsstufe der Nachricht. 9 zeigt Phishing an, 11 steht für organisationsinternes Spoofing.

- **Domänenübergreifendes Spoofing**: die Absender- und Empfängerdomäne sind unterschiedlich und es gibt keine Beziehung zueinander (auch als externe Domänen bezeichnet). Zum Beispiel:
    > Von: chris@contoso.com <br/> An: michelle@tailspintoys.com

  Nachrichten, bei denen die [zusammengesetzte Authentifizierung](email-validation-and-authentication.md#composite-authentication) aufgrund von domänenübergreifendem Spoofing fehlschlägt, enhalten die folgenden Werte im Header:

  `Authentication-Results: ... compauth=fail reason=000/001`

  `X-Forefront-Antispam-Report: ...CAT:SPOOF;...SFTY:9.22`

  - `reason=000` gibt an, dass die explizite E-Mail-Authentifizierung der Nachricht fehlerhaft war. Der Wert `reason=001` gibt an, dass die implizite E-Mail-Authentifizierung für die Nachricht fehlgeschlagen ist.

  - SFTY ist die Sicherheitsstufe der Nachricht. 9 zeigt Phishing an, 22 steht für organisationsinternes Spoofing.

Weitere Informationen zu der Kategorie und den Werten der zusammengesetzten Authentifizierung (compauth), die sich auf Spoofing beziehen, finden Sie unter [Anti-Spam-Nachrichtenheader in Microsoft 365](anti-spam-message-headers.md).

Weitere Informationen über DMARC finden Sie unter [Verwenden von DMARC zur Überprüfung von E-Mails in Microsoft 365](use-dmarc-to-validate-email.md).

## <a name="reports-of-how-many-messages-were-marked-as-spoofed"></a>Berichte über die Anzahl von Nachrichten, die als gefälscht eingestuft wurden

EOP-Organisationen können den Bericht **Erkannte Fälschungen** im Berichte-Dashboard im Security & Compliance Center verwenden. Weitere Informationen finden Sie unter [Bericht „Erkannte Fälschungen“](view-email-security-reports.md#spoof-detections-report).

Microsoft Defender für Office 365-Organisationen können den Sicherheitsrisiken-Explorer im Security & Compliance Center verwenden, um Informationen zu Phishingversuchen anzuzeigen. Weitere Informationen finden Sie unter [Microsoft 365 Untersuchung von und Antwort auf Bedrohungen](office-365-ti.md).

## <a name="problems-with-anti-spoofing-protection"></a>Probleme mit dem Antispoofingschutz

Mailinglisten (auch bekannt als Diskussionslisten) haben bekanntermaßen Probleme mit Anti-Spoofing. Dies wird durch die Art verursacht, auf die sie Nachrichten weiterleiten und modifizieren.

Beispielsweise interessiert sich Gabriela Laureano (glaureano@contoso.com) für Vogelbeobachtung, schließt sich der Diskussionsliste birdwatchers@fabrikam.com an und schickt folgende Nachricht an die Liste:

> **Von:** "Gabriela Laureano" \<glaureano@contoso.com\> <br/> **To:** Birdwatcher's Discussion List \<birdwatchers@fabrikam.com\> <br/> **Betreff:** Großartiger Blick auf Eichelhäher am Mount Rainier diese Woche <p> Jemand Interesse an diesem Ausblick von dieser Woche am Mount Rainier?

Der Diskussionslisten-Server empfängt die Nachricht, ändert deren Inhalt und sendet sie an die Mitglieder der Liste. Die an die Mitglieder ausgesendete Nachricht hat zwar die gleiche „Von“-Adresse (glaureano@contoso.com), jedoch wurde der Betreffzeile ein Tag und eine der Nachricht eine Fußzeile hinzugefügt. Diese Art von Änderung ist in Diskussionslisten üblich und kann zu falsch-positiven Ergebnissen der Spoofing-Prüfung führen.

> **Von:** "Gabriela Laureano" \<glaureano@contoso.com\> <br/> **To:** Birdwatcher's Discussion List \<birdwatchers@fabrikam.com\> <br/> **Betreff:** [BIRDWATCHERS] Großartiger Blick auf Eichelhäher am Mount Rainier diese Woche <p> Jemand Interesse an diesem Ausblick von dieser Woche am Mount Rainier? <p> Diese Nachricht wurde an die Diskussionsgruppe Vögelbeobachtung gesendet. Sie können sich jederzeit wieder abmelden.

Um Nachrichten aus Diskussionslisten dabei zu helfen, die Anti-Spoofing-Prüfungen zu bestehen, führen Sie die folgenden Schritte aus, je nachdem, ob Sie die Diskussionsliste kontrollieren:

- Ihre Organisation ist Eigentümer der Diskussionsliste:

  - Lesen Sie die häufig gestellten Fragen unter DMARC.org: [I operate a mailing list and I want to interoperate with DMARC, what should I do?](https://dmarc.org/wiki/FAQ#I_operate_a_mailing_list_and_I_want_to_interoperate_with_DMARC.2C_what_should_I_do.3F).

  - Lesen Sie die Anweisungen in diesem Blogbeitrag: [A tip for mailing list operators to interoperate with DMARC to avoid failures](https://blogs.msdn.microsoft.com/tzink/2017/03/22/a-tip-for-mailing-list-operators-to-interoperate-with-dmarc-to-avoid-failures/).

  - Erwägen Sie bitte, Updates für diesen Verteilerserver zu installieren, damit ARC unterstützt wird. Informationen dazu finden Sie unter <http://arc-spec.org>.

- Ihre Organisation ist nicht Eigentümer der Diskussionsliste:

  - Bitten Sie den Betreuer der Diskussionsliste, die E-Mail-Authentifizierung für die Domäne zu konfigurieren, aus der die Diskussionsliste weitergeleitet wird.

    Wenn genügend Absender den Domänenbesitzern antworten und darum bitten, E-Mail-Authentifizierungsdatensätze einzurichten, werden diese möglicherweise dazu angespornt, die entsprechenden Maßnahmen zu ergreifen. Microsoft arbeitet zwar auch mit Domänenbesitzern zusammen, um die erforderlichen Datensätze zu veröffentlichen, es hilft jedoch, wenn einzelne Benutzer sie zusätzlich dazu auffordern.

  - Erstellen Sie in Ihrem E-Mail-Client Regeln, um die Nachrichten in den Posteingang zu verschieben. Sie können auch Ihre Administratoren bitten, Außerkraftsetzungen so zu konfigurieren, wie dies in [Spoof-Intelligenz zur Konfiguration zulässiger Absender unauthentifizierter E-Mails verwenden](email-validation-and-authentication.md#use-spoof-intelligence-to-configure-permitted-senders-of-unauthenticated-email) beschrieben ist.

  - Erstellen Sie ein Supportticket für Microsoft 365, um eine Außerkraftsetzung für die Diskussionsliste zu erstellen, damit sie als seriöser Empfänger gehandhabt wird. Weitere Informationen finden Sie unter [Kontaktieren des Supports für Business-Produkte – Administratorhilfe](../../admin/contact-support-for-business-products.md).

Falls alles andere fehlschlägt, können Sie die Nachricht als falsch-positiv an Microsoft melden. Weitere Informationen finden Sie unter [Melden von Nachrichten und Dateien an Microsoft](report-junk-email-messages-to-microsoft.md).

Sie können auch Ihren Administrator kontaktieren, der ein Supportticket bei Microsoft öffnen kann. Das Microsoft-Entwicklungsteam prüft anschließend, warum die Nachricht als Spoofingnachricht eingestuft wurde.

## <a name="considerations-for-anti-spoofing-protection"></a>Überlegungen zum Schutz vor Spoofing

Falls Sie ein Administrator sind, der aktuell Nachrichten an Microsoft 365 sendet, müssen Sie sicherstellen, dass Ihre E-Mails ordnungsgemäß authentifiziert werden. Andernfalls werden sie möglicherweise als Spam oder Phishingversuch gekennzeichnet. Weitere Informationen finden Sie unter [Lösungen für seriöse Absender, die nicht-authentifizierte E-Mails senden](email-validation-and-authentication.md#solutions-for-legitimate-senders-who-are-sending-unauthenticated-email).

Absender in einer Liste der sicheren Absender eines einzelnen Benutzers (oder Administrators) umgehen Teile des Filterstapels, einschließlich Spoofschutz. Weitere Informationen finden Sie unter [Outlook Safe Senders](create-safe-sender-lists-in-office-365.md#use-outlook-safe-senders) (Sichere Absender in Outlook).

Administratoren sollten (wenn möglich) die Verwendung von Listen zulässiger Absender oder zulässiger Domänen vermeiden. Diese Absender umgehen alle Schutzmaßnahmen zu Spam, Spoofing und Phishing und außerdem die Absenderauthentifizierung (SPF, DKIM, DMARC). Weitere Informationen finden Sie unter [Use allowed sender lists or allowed domain lists](create-safe-sender-lists-in-office-365.md#use-allowed-sender-lists-or-allowed-domain-lists) (Verwendung von Listen zulässiger Absender oder zulässiger Domänen).
