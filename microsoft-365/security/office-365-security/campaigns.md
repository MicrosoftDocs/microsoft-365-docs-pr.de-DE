---
title: Kampagnen Ansichten in ATP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: mcostea
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Erfahren Sie mehr über die Kampagnenansichten in Office 365 Advanced Threat Protection.
ms.openlocfilehash: 69b11319ffb033b628e59abac931b6a3f30d082c
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43637818"
---
# <a name="campaign-views-in-atp"></a>Kampagnen Ansichten in ATP

Kampagnen Ansichten sind ein Feature in Advanced Threat Protection (ATP) im Security & Compliance Center, das Phishing-Angriffe im Dienst identifiziert und kategorisiert. Kampagnenansichten können Ihnen bei Folgendem helfen:

- Phishing-Angriffe effektiv untersuchen und darauf reagieren.

- Besseres Verständnis des Umfangs des Angriffs.

- Entscheidungsträgern den Nutzen anzeigen.

Mit Kampagnenansichten können Sie das Gesamtbild eines Angriffs schneller und vollständiger erfassen als jeder Mensch.

## <a name="what-is-a-campaign"></a>Was ist eine Kampagne?

Eine Kampagne ist ein koordinierter E-Mail-Angriff gegen eine oder mehrere Organisationen. E-Mail-Angriffe, die Anmeldeinformationen und Unternehmensdaten stehlen, sind eine große und lukrative Branche. Wenn Technologien sich anstrengen, um Angriffe zu stoppen, ändern Angreifer Ihre Methoden, um den weiteren Erfolg sicherzustellen.

Microsoft nutzt die großen Mengen an Anti-Phishing-, Antispam-und Antischadsoftware-Daten im gesamten Dienst, um Kampagnen zu identifizieren. Wir analysieren und klassifizieren die Angriffsinformationen anhand verschiedener Faktoren. Zum Beispiel:

- **Angriffsquellen**: Quell-IP-Adressen und E-Mail-Domänen des Absenders.

- **Eigenschaften der Angriffsnachricht**: Inhalt, Art und Grundstimmung der Angriffsnachrichten.

- **Angriffsempfänger**: Empfängerdomänen, Aufgaben des Empfängers (Administratoren, Führungskräfte usw.), Firmentypen (groß, klein, öffentlich, privat usw.) und Branchen.

- **Angriffsnutzlast**: böswillige Links, Anlagen oder andere Nutzlasten in den Angriffs Nachrichten.

Eine Kampagne kann von kurzer Dauer sein oder mehrere Tage, Wochen oder Monate mit aktiven und inaktiven Zeitspannen umfassen. Möglicherweise wird eine Kampagne für ihre jeweilige Organisation gestartet, oder Ihre Organisation kann Teil einer größeren Kampagne in mehreren Unternehmen sein.

## <a name="campaign-views-the-security--compliance-center"></a>Kampagnen Ansichten das Security & Compliance Center

Kampagnen Ansichten stehen im [Security & Compliance Center](https://protection.office.com) unter **Threat Management** \> **Campaigns**zur Verfügung.

![Kampagnenübersicht im Security & Compliance Center](../../media/campaigns-overview.png)

Sie können auch die Ansicht Kampagnen Aufrufen von:

- **Threat Management** \> **Explorer** \> – **Kampagnen** **anzeigen** \>

- **Threat Management** \> **Explorer** \> **View** \> **alle e-Mail-** \> **Kampagnen** anzeigen

> [!TIP]
> Wenn keine Kampagnendaten angezeigt werden, versuchen Sie, den Zeitraum zu ändern.

Auf der Seite "Übersicht" werden die folgenden Informationen zur Kampagne angezeigt:

- **Name**

- **Beispiel-Betreff**: Betreffzeile einer der Nachrichten in der Kampagne. Beachten Sie, dass alle Nachrichten in der Kampagne nicht unbedingt den gleichen Betreff haben.

- **Typ**: derzeit ist dieser Wert immer **Phish**.

- **Untertyp**: Wenn verfügbar, die Marke, die von dieser Kampagne ausgespäht wird. Wenn die Erkennung von der ATP-Technologie gesteuert wird, wird das Präfix **ATP-** dem Untertyp Wert hinzugefügt.

- **Empfänger**: Die Anzahl der Benutzer, auf die diese Kampagne abzielt.

- **Inboxed**: die Anzahl der Benutzer, die Nachrichten von dieser Kampagne in Ihrem Posteingang empfangen haben (nicht an Junk zugestellt).

- **Geklickt**von: die Anzahl der Benutzer, die auf die URL in der Phishing-Nachricht geklickt haben.

- **Klicken Sie auf Rate**: den Prozentsatz, der von "auf**Posteingang****geklickt** / " berechnet wird. Dieser Wert ist ein Indikator für die Effektivität der Kampagne und gibt an, ob die Empfänger die Nachricht als Phishing identifizieren konnten, und vermeiden Sie das Klicken auf die Nutzlast-URL.

- **Besucht**: Anzahl der Benutzer, die die Nutzlast-Website tatsächlich durchlaufen haben. Wenn auf Werte **geklickt** wird, aber sichere Links den Zugriff auf die Website blockiert haben, ist dieser Wert gleich NULL.

Wenn Sie auf den Namen einer Kampagne klicken, werden die Kampagnendetails in einem Flyout angezeigt.

## <a name="campaign-details"></a>Kampagnendetails

In der Ansicht "Kampagnendetails" stehen viele Informationen zu der Kampagne bereit:

- Kampagneninformationen:

  - **ID**: der eindeutige Kampagnen Bezeichner.

  - **Begonnen** und **Beendet**: Der ausgewählte Datumsfilter.

  - **Symptom**: die folgenden Daten für den ausgewählten Datumsbereichsfilter:
  
    - Die Gesamtzahl der Empfänger.

    - Die Anzahl der Nachrichten, die "Posteingang" (also im Posteingang, nicht an Junk) gesendet wurden.

    - Wie viele Benutzer auf die URL-Nutzlast in der Phishing-Nachricht geklickt haben.

    - Howe viele Benutzer haben die URL besucht.

  - Eine Zeitachse für Kampagnenaktivitäten: Wann die Kampagne begonnen und geendet hat, und die Anzahl der Nachrichten im Zeitverlauf.

### <a name="campaign-flow"></a>Kampagnenfluss

Wichtige Details zur Kampagne werden in einem horizontalen Flussdiagramm (auch als _Sankey_-Diagramm bezeichnet) im Abschnitt **Fluss** dargestellt. Diese Details helfen Ihnen, die Elemente der Kampagne und die potenziellen Auswirkungen in Ihrer Organisation zu verstehen.

![Kampagnendetails, die keine Benutzer-URL-Klicks enthalten](../../media/campaign-details-no-recipient-actions.png)

Wenn Sie im Diagramm auf ein horizontales Band zeigen, sehen Sie die Anzahl der verwandten Nachrichten (z. B. Nachrichten aus einer bestimmten Quell-IP, Nachrichten aus der Quell-IP-Adresse, die die angegebene Absenderdomäne verwenden, usw.).

Das Diagramm enthält die folgenden Informationen:

- **Sender-IPs**

- **Absenderdomänen**

- **Filter Urteile**: die hier aufgeführten Werte beziehen sich auf die verfügbaren Phishing-und Spamfilter Urteile, wie unter [Antispam-Nachrichtenkopfzeilen](anti-spam-message-headers.md)beschrieben. Die verfügbaren Werte werden in der folgenden Tabelle beschrieben:

  |Wert|Spam Filter Urteil|Beschreibung|
  |:-----|:-----|:-----|
  | **Allowed**|`SFV:SKN` <br/><br/> `SFV:SKI`|Die Nachricht wurde durch Spamfilterung (beispielsweisedurch eine e-Mail-Fluss Regel, die auch als Transportregel bezeichnet wird) als nicht-Spam und/oder übersprungene Filterung markiert.<br/><br/>Die Nachricht hat die Spamfilterung aus anderen Gründen übersprungen (beispielsweise scheinen sich der Absender und der Empfänger in derselben Organisation zu befinden).|
  |**Gesperrt**|`SFV:SKS`|Die Nachricht wurde vor der Auswertung durch Spamfilterung (beispielsweisedurch eine Nachrichtenfluss Regel) als Spam markiert.|
  |**Erkannt**|`SFV:SPM`|Die Nachricht wurde von der Spamfilterung als Spam markiert.|
  |**Nicht erkannt**|`SFV:NSPM`|Die Nachricht wurde durch Spamfilterung als nicht Spam gekennzeichnet.|
  |**Veröffentlicht**|`SFV:SKQ`|Die Nachricht hat die Spamfilterung übersprungen, da Sie aus der Quarantäne freigegeben wurde.|
  |**Mandanten zulässig**<sup>\*</sup>|`SFV:SKA`|Die Nachricht hat die Spamfilterung aufgrund von Anti-Spam-Richtlinieneinstellungen übersprungen (beispielsweise war der Absender in der Liste Zugelassene Absender oder zugelassener Domänen).|
  |**Mandanten Block**<sup>\*\*</sup>|`SFV:SKA`|Die Nachricht wurde durch die Spamfilterung aufgrund von Anti-Spam-Richtlinieneinstellungen blockiert (beispielsweise war der Absender in der Liste Zugelassene Absender oder zugelassener Domänen).|
  |**Benutzer zulassen**<sup>\*</sup>|`SFV:SFE`|Die Nachricht hat die Spamfilterung übersprungen, da sich der Absender in Outlook in der Liste sicherer Absender eines Benutzers befand.|
  |**Benutzer Block**<sup>\*\*</sup>|`SFV:BLK`|Die Nachricht wurde durch die Spamfilterung blockiert, da sich der Absender in Outlook in der Liste Blockierte Absender eines Benutzers befand.|
  |**ZAP**|n/v|[Zero-Hour Auto Purge (zap)](zero-hour-auto-purge.md) hat in der zugestellten Nachricht entsprechend den Einstellungen Ihrer Antispampolitik (in den Junk-e-Mail-Ordner verschoben oder isoliert) Aktionen durchgeführt.|

  <sup>\*</sup>Überprüfen Sie Ihre Anti-Spam-Richtlinien, da die zulässige Nachricht wahrscheinlich vom Dienst blockiert wurde.

  <sup>\*\*</sup>Überprüfen Sie Ihre Anti-Spam-Richtlinien, da diese Nachrichten isoliert und nicht zugestellt werden sollen.

- **Übermittlungsorte**: Sie möchten wahrscheinlich Nachrichten überprüfen, die an Empfänger übermittelt wurden (entweder im Posteingang oder Junk-E-Mail-Ordner), auch wenn Benutzer nicht auf die Nutzlast-URL in der Nachricht geklickt haben. Sie können auch die isolierten Nachrichten aus der Quarantäne entfernen. Weitere Informationen finden Sie unter [Quarantäne für e-Mail-Nachrichten in Office 365](quarantine-email-messages.md).

  - **Ordner gelöscht**

  - **Gelöscht**

  - **Extern**: der Empfänger befindet sich in Ihrer lokalen e-Mail-Organisation.

  - **Fehlgeschlagen**

  - **Weitergeleitet**

  - **Posteingang**

  - **Junk-E-Mail-Ordner**

  - **Quarantäne**

  - **Unknown**

> [!NOTE]
> In allen Ebenen, die mehr als 10 Elemente enthalten, werden die oberen 10 Elemente angezeigt, während der Rest in **anderen**zusammengefasst wird.

#### <a name="url-clicks"></a>URL-Klicks

Wenn eine Phishing-Nachricht an einen Empfänger (in den Posteingang oder den Junk-e-Mail-Ordner) zugestellt wird, besteht immer die Möglichkeit, dass der Benutzer auf die Nutzlast-URL klickt. Wenn Sie nicht auf die URL in einer zugestellten Nachricht klicken, ist dies ein kleines Maß an Erfolg, aber Sie müssen herausfinden, warum die Phishing-Nachricht an erster Stelle an Ihr Postfach zugestellt wurde.

Wenn ein Benutzer in der Phishing-Nachricht auf die Nutzlast-URL geklickt hat, werden die Aktionen im Bereich **URL Klicks** des Diagramms in der Ansicht kampagnendetails angezeigt.

- **Allowed**

- **BlockPage**: der Empfänger hat auf die Nutzlast-URL geklickt, aber der Zugriff auf die bösartige Website wurde durch die Richtlinien für [ATP-sichere Links](atp-safe-links.md) in Ihrer Organisation blockiert.

- **BlockPageOverride**: der Empfänger hat auf die Nutzlast-URL in der Nachricht geklickt, die ATP-Sicherheits Links haben versucht, diese zu beenden, aber Sie durften den Block außer Kraft setzen. Sie müssen Ihre [Richtlinien zu sicheren Links](set-up-atp-safe-links-policies.md) untersuchen, um zu ermitteln, warum Benutzer das Urteil "sichere Links" außer Kraft setzen und mit der bösartigen Website fortfahren dürfen.

- **PendingDetonationPage**: ATP Safe Attachments ist gerade dabei, die Nutzlast-URL in einer virtuellen Computerumgebung zu öffnen und zu sehen, was geschieht.

- **PendingDetonationPageOverride**: der Empfänger durfte den detonations Prozess für die Nutzlast außer Kraft setzen und die URL öffnen, ohne auf die Ergebnisse zu warten.

### <a name="tabs"></a>Registerkarten

In der Ansicht „Kampagnendetails“ stehen mehrere Registerkarten zur Verfügung, mit denen Sie die Kampagne weiter untersuchen können.

- **URL Klicks**: Wenn Benutzer nicht auf die Nutzlast-URL in der Phishing-Nachricht geklickt haben, ist dieser Abschnitt leer. Wenn ein Benutzer auf die URL klicken konnte, werden die folgenden Werte aufgefüllt:

  - **Benutzer**<sup>\*</sup>

  - **URL**<sup>\*</sup>

  - **Zeit**

  - **Aktion**

- **Sender-IPs**

  - **Sender-IP**<sup>\*</sup>

  - **Gesamtanzahl**

  - **Anzahl "Posteingang"**

  - **Anzahl "Gesperrt"**

  - **Weitergegebene SPF**: der Absender wurde vom [SPF (Sender Policy Framework)](how-office-365-uses-spf-to-prevent-spoofing.md)authentifiziert. Ein Absender, der die SPF-Überprüfung nicht übergibt, gibt an, dass der Absender nicht authentifiziert ist oder wenn die Nachricht einen legitimen Absender fälscht.

- **Absender**

  - **Absender**: Dies ist die tatsächliche Absenderadresse im SMTP-Mail von-Befehl, die nicht unbedingt die von:-e-Mail-Adresse ist, die Benutzern in Ihren e-Mail-Clients angezeigt wird.

  - **Gesamtanzahl**

  - **Posteingang**

  - **Nicht Posteingang**

  - **DKIM-Übergabe**: der Absender wurde durch Domänenschlüssel authentifiziert, die [Mail (DKIM) identifiziert](support-for-validation-of-dkim-signed-messages.md)haben. Ein Absender, der die DKIM-Überprüfung nicht übergibt, gibt an, dass der Absender nicht authentifiziert ist oder wenn die Nachricht einen legitimen Absender fälscht.

  - **DMARC wurde übergeben**: der Absender wurde durch [domänenbasierte Nachrichtenauthentifizierung, Berichterstellung und Konformität authentifiziert (DMARC)](use-dmarc-to-validate-email.md). Ein Absender, der die DMARC-Überprüfung nicht übergibt, gibt an, dass der Absender nicht authentifiziert ist oder wenn die Nachricht einen legitimen Absender fälscht.

- **Nutzlasten**

  - **URL**<sup>\*</sup>

  - **Gesamtanzahl**

<sup>\*</sup> Wenn Sie auf diesen Wert klicken, wird ein neues Flyout geöffnet, das weitere Details zu dem angegebenen Element (Benutzer, URL usw.) oben in der Ansicht "Kampagnendetails" enthält. Wenn Sie zur Ansicht "Kampagnendetails" zurückkehren möchten, klicken Sie im neuen Flyout auf **Fertig**.

### <a name="buttons"></a>Schaltflächen

Mit den Schaltflächen in der Ansicht "Kampagnendetails" können Sie die Funktionen von Threat Explorer verwenden, um die Kampagne weiter zu untersuchen.

- **Kampagne durchsuchen**: Öffnet eine neue Threat Explorer-Suchregisterkarte mit dem Wert **Kampagnen-ID** als Suchfilter.

- Untersuchen von **Nachrichten im Posteingang**: öffnet eine neue Suchregisterkarte "Threat Explorer" mithilfe der **Kampagnen-ID** und des **Zustellungs Speicherorts: Posteingang** als Suchfilter.
