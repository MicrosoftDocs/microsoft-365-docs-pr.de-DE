---
title: Aktivieren der Evaluierungsumgebung für Microsoft Defender für Office 365 in Ihrer Produktionsumgebung, Aktivieren der Auswertung, Aktivierung
description: Schritte zum Aktivieren der Microsoft Defender für Office 365-Evaluierung mit Testlizenzen, MX-Datensatzbehandlung, & Überwachung akzeptierter Domänen und eingehenden Verbindungen.
keywords: Microsoft 365 Defender Testversion, testen Sie Microsoft 365 Defender, bewerten Sie Microsoft 365 Defender, Microsoft 365 Defender Evaluierungslabor, Microsoft 365 Defender Pilotprojekt, Cybersicherheit, erweiterte dauerhafte Bedrohung, Unternehmenssicherheit, Geräte, Gerät, Identität, Benutzer, Daten, Anwendungen, Vorfälle, automatisierte Untersuchung und Behebung, erweiterte Suche
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.date: 07/01/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: how-to
ms.technology: m365d
ms.openlocfilehash: c0736b93c314c3086f8a52477622c6bcfa4096a0
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458365"
---
# <a name="enable-the-evaluation-environment"></a>Aktivieren der Evaluierungsumgebung

**Gilt für:**
- Microsoft 365 Defender

Dieser Artikel ist [Schritt 2 von 3](eval-defender-office-365-overview.md) beim Einrichten der Evaluierungsumgebung für Microsoft Defender für Office 365. Weitere Informationen zu diesem Prozess finden Sie im [Übersichtsartikel.](eval-defender-office-365-overview.md)

Führen Sie die folgenden Schritte aus, um die Auswertung für Microsoft Defender für Office 365 zu aktivieren.


![Schritte zum Aktivieren von Microsoft Defender für Office 365 in der Microsoft Defender-Evaluierungsumgebung](../../media/defender/m365-defender-office-eval-enable-steps.png)

- [Schritt 1: Aktivieren von Testlizenzen](#step-1-activate-trial-licenses)
- [Schritt 2: Überwachen und Überprüfen des öffentlichen MX-Eintrags](#step-2-audit-and-verify-the-public-mx-record)
- [Schritt 3: Überwachen akzeptierter Domänen](#step-3-audit-accepted-domains)
- [Schritt 4: Überwachen eingehender Connectors](#step-4-audit-inbound-connectors)
- [Schritt 5: Aktivieren der Auswertung](#step-5-activate-the-evaluation)

## <a name="step-1-activate-trial-licenses&quot;></a>Schritt 1: Aktivieren von Testlizenzen

Melden Sie sich bei Ihrer vorhandenen Microsoft Defender for Office 365-Umgebung oder dem Mandantenverwaltungsportal an.

1. Navigieren Sie zum Verwaltungsportal.
2. Wählen Sie in der Schnellstartleiste &quot;Dienste kaufen&quot; aus.

:::image type=&quot;content&quot; source=&quot;../../media/mdo-eval/1_m365-purchase-services.png&quot; alt-text=&quot;Klicken Sie im Navigationsbereich von Office 365 auf &quot;Dienste kaufen&quot;.&quot;:::

3.  Scrollen Sie nach unten zum Add-On Abschnitt (oder suchen Sie nach &quot;Defender"), um den Microsoft Defender für Office 365 Pläne zu suchen.
4.  Klicken Sie auf "Details" neben dem Plan, den Sie auswerten möchten.

:::image type="content" source="../../media/mdo-eval/2_mdo-eval-license-details.png" alt-text="Klicken Sie als Nächstes auf die Schaltfläche &quot;Details&quot;.":::

5. Klicken Sie auf den Link *"Kostenlose Testversion starten".*

:::image type="content" source="../../media/mdo-eval/3-m365-purchase-button.png" alt-text="Klicken Sie in diesem Bereich auf die kostenlose Testversion *Hyperlink*.":::

6. Bestätigen Sie Ihre Anforderung, und klicken Sie auf die Schaltfläche *"Jetzt testen".*

:::image type="content" source="../../media/mdo-eval/4_mdo-trial-order.png" alt-text="Klicken Sie nun auf die Schaltfläche &quot;Jetzt testen*&quot;.":::

## <a name="step-2-audit-and-verify-the-public-mx-record"></a>Schritt 2: Überwachen und Überprüfen des öffentlichen MX-Eintrags

Um Microsoft Defender für Office 365 effektiv zu bewerten, ist es wichtig, dass eingehende externe E-Mails über die ihrem Mandanten zugeordnete Exchange Online Protection instanz (EOP) weitergeleitet werden.

1. Melden Sie sich beim M365-Verwaltungsportal an, erweitern Sie Einstellungen, und wählen Sie "Domänen" aus.
2. Wählen Sie Ihre überprüfte E-Mail-Domäne aus, und klicken Sie auf "DNS verwalten".
3. Notieren Sie sich den MX-Eintrag, der generiert und Ihrem EOP-Mandanten zugewiesen wurde.
4. Greifen Sie auf Ihre externe (öffentliche) DNS-Zone zu, und überprüfen Sie den primären MX-Eintrag, der Ihrer E-Mail-Domäne zugeordnet ist.
    - *Wenn Ihr öffentlicher MX-Eintrag derzeit mit der zugewiesenen EOP-Adresse übereinstimmt (z. B. tenant-com.mail.protection.outlook.com), sollten keine weiteren Routingänderungen erforderlich sein.*
    - Wenn Ihr öffentlicher MX-Eintrag derzeit in ein SMTP-Gateway eines Drittanbieters oder lokalen Anbieters aufgelöst wird, sind möglicherweise zusätzliche Routingkonfigurationen erforderlich.
    - Wenn Ihr öffentlicher MX-Eintrag derzeit in lokale Exchange aufgelöst wird, befinden Sie sich möglicherweise immer noch in einem Hybridmodell, in dem einige Empfängerpostfächer noch nicht zu EXO migriert wurden.

## <a name="step-3-audit-accepted-domains"></a>Schritt 3: Überwachen akzeptierter Domänen

1. Melden Sie sich im Exchange Online Admin Portal an, wählen Sie "E-Mail Flow" aus, und klicken Sie dann auf "Akzeptierte Domänen".
2. Notieren Sie sich aus der Liste der akzeptierten Domänen, die in Ihrem Mandanten hinzugefügt und überprüft wurden, den **Domänentyp** für Ihre primäre E-Mail-Domäne.
    - Wenn der Domänentyp auf ***Autoritativ*** festgelegt ist, wird davon ausgegangen, dass sich alle Empfängerpostfächer für Ihre Organisation derzeit in Exchange Online befinden.
    - Wenn der Domänentyp auf ***"Internes Relay"*** festgelegt ist, befinden Sie sich möglicherweise noch in einem Hybridmodell, in dem sich einige Empfängerpostfächer weiterhin lokal befinden.

## <a name="step-4-audit-inbound-connectors"></a>Schritt 4: Überwachen eingehender Connectors

1. Melden Sie sich im Exchange Online Admin Portal an, wählen Sie E-Mail-Flow aus, und klicken Sie dann auf Connectors.
2. Notieren Sie sich aus der Liste der konfigurierten Connectors alle Einträge, die aus der **Partnerorganisation** stammen und mit einem SMTP-Gateway eines Drittanbieters korrelieren können.
3. Notieren Sie sich aus der Liste der konfigurierten Connectors alle Einträge, die **vom E-Mail-Server Ihrer Organisation** bezeichnet werden, was möglicherweise darauf hinweist, dass Sie sich noch in einem Hybridszenario befinden.

## <a name="step-5-activate-the-evaluation"></a>Schritt 5: Aktivieren der Auswertung

Verwenden Sie die hier aufgeführten Anweisungen, um Microsoft Defender für Office 365 Auswertung über das Microsoft 365 Defender Portal zu aktivieren.

1. Melden Sie sich bei Ihrem Mandanten mit einem Konto an, das Zugriff auf das Microsoft 365 Defender-Portal hat.
2. Wählen Sie aus, ob Sie das **Microsoft 365 Defender-Portal** zur Standardschnittstelle für Microsoft Defender für Office 365 Verwaltung machen möchten (empfohlen).

:::image type="content" source="../../media/mdo-eval/1_mdo-eval-activate-eval.png" alt-text="Klicken Sie auf die Schaltfläche &quot;Einstellungen aktivieren&quot;, um das zentrale und verbesserte Microsoft 365 Defender-Portal für die Verwaltung zu verwenden.":::

3. Wählen Sie im Navigationsmenü **"Richtlinien & Regeln"** unter *"E-Mail & Zusammenarbeit"* aus.

:::image type="content" source="../../media/mdo-eval/2_mdo-eval-activate-eval.png" alt-text="Hier sehen Sie ein Bild des Menüs &quot;E-Mail & Zusammenarbeit&quot;, das auf Richtlinien & Regeln zeigt. Klicken Sie darauf!":::

4. Klicken Sie im Dashboard *"Richtlinie & Regeln"* auf **"Bedrohungsrichtlinien".**

:::image type="content" source="../../media/mdo-eval/3_mdo-eval-activate-eval.png" alt-text="Abbildung des Richtlinien-&-Regeldashboards und eines Pfeils, der auf Bedrohungsrichtlinien zeigt. Klicken Sie als Nächstes darauf!":::

5. Scrollen Sie nach unten zu *zusätzlichen Richtlinien,* und wählen Sie die Kachel **"Defender für Office 365 auswerten".**

:::image type="content" source="../../media/mdo-eval/4_mdo-eval-activate-eval.png" alt-text="Die Kachel &quot;Eval Defender für Office 365&quot; gibt an, dass es sich um eine 30-tägige Testversion über E-Mail-& Zusammenarbeitsvektoren handelt. Klicken Sie durch.":::

6. Wählen Sie nun aus, ob externe E-Mails direkt an Exchange Online oder an ein Gateway oder einen Dienst eines Drittanbieters weitergeroutet werden, und klicken Sie auf "Weiter".

:::image type="content" source="../../media/mdo-eval/5_mdo-eval-activate-eval.png" alt-text="Defender für Office 365 wertet das Senden von E-Mails an Ihre Exchange Online Postfächer aus. Geben Sie details dazu an, wie Ihre E-Mails jetzt weitergeleitet werden, einschließlich des Namens des ausgehenden Connectors, der Ihre E-Mails leitet. Wenn Sie nur Exchange Online Protection (EOP) verwenden, verfügen Sie nicht über einen Connector. Wählen Sie einen von mir, der einen Drittanbieter oder lokalen Anbieter verwendet, oder verwenden Sie nur EOP.":::

7. Wenn Sie ein Drittanbietergateway verwenden, wählen Sie den Namen des Anbieters in der Dropdownliste zusammen mit dem eingehenden Connector aus, der dieser Lösung zugeordnet ist. Wenn Sie Ihre Antworten aufgelistet haben, klicken Sie auf "Weiter".

:::image type="content" source="../../media/mdo-eval/6-mdo-eval-activate-eval-settings.png" alt-text="In diesem Dialogfeld wählen Sie den Drittanbieterdienst aus, den Ihre Organisation verwendet, oder wählen *Other* aus. Wählen Sie im nächsten Dialogfeld nach unten den eingehenden Connector aus. Klicken Sie dann auf &quot;Weiter&quot;.":::

8. Überprüfen Sie Ihre Einstellungen, und klicken Sie auf die Schaltfläche **"Evaluierung erstellen".**

|  |  |
|---------|---------|
|  :::image type="content" source="../../media/mdo-eval/7-mdo-eval-activate-review.png" alt-text="Dieser Bereich enthält eine Dropdownliste, um Ihre Einstellungen zu überprüfen. Sie verfügt auch über einen klickbaren Link zum Bearbeiten des Routingtyps, falls erforderlich. Wenn Sie fertig sind, klicken Sie auf die große blaue Schaltfläche &quot;Auswertung erstellen&quot;.":::   |   :::image type="content" source="../../media/mdo-eval/8-mdo-eval-activate-complete.png" alt-text="Und jetzt ist die Einrichtung abgeschlossen. Die blaue Schaltfläche auf dieser Seite lautet &quot;Zur Auswertung wechseln&quot;.":::      |

## <a name="next-steps"></a>Nächste Schritte

Schritt 3 von 3: Einrichten des Pilotprojekts für Microsoft Defender für Office 365

Kehren Sie zur Übersicht über [das Auswerten von Microsoft Defender für Office 365](eval-defender-office-365-overview.md)

Kehren Sie zur Übersicht für [Evaluierungs- und Pilot-Microsoft 365 Defender](eval-overview.md)