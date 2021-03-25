---
title: Verhaltensblockierung und -eindämmung
description: Erfahren Sie mehr über die Funktionen zum Blockieren und Eindämmung von Verhaltensweisen in Microsoft Defender ATP
keywords: Microsoft Defender ATP, EDR im Blockmodus, Blockieren des passiven Modus
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
author: denisebmsft
ms.author: deniseb
manager: dansimp
ms.reviewer: shwetaj
audience: ITPro
ms.topic: article
ms.prod: m365-security
localization_priority: Normal
ms.custom:
- next-gen
- edr
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.technology: mde
ms.openlocfilehash: dcad3b7233f2efd444d41c15916eaae195634c8c
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166233"
---
# <a name="behavioral-blocking-and-containment"></a>Verhaltensblockierung und -eindämmung

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="overview"></a>Übersicht

Die heutige Bedrohungslandschaft wird [](https://docs.microsoft.com/windows/security/threat-protection/intelligence/fileless-threats) von schadloser Schadsoftware überrollt, die vom Land lebt, hochgradig polymorphe Bedrohungen, die schneller mutieren, als herkömmliche Lösungen mithalten können, und vom Menschen betriebene Angriffe, die sich an das anpassen, was Gegner auf gefährdeten Geräten finden. Herkömmliche Sicherheitslösungen reichen nicht aus, um solche Angriffe zu beenden. Sie benötigen unterstützte Funktionen für künstliche Intelligenz (KI) und Device Learning (ML), z. B. Verhaltensblockierung und -eindämmung, die in [Defender for Endpoint enthalten sind.](https://docs.microsoft.com/windows/security) 

Verhaltensblockierungs- und -eindämmungsfunktionen können dazu beitragen, Bedrohungen basierend auf ihrem Verhalten und ihren Prozessstrukturen zu identifizieren und zu beenden, selbst wenn die Bedrohung mit der Ausführung begonnen hat. Komponenten und Features der nächsten Generation für Schutz, EDR und Defender for Endpoint arbeiten bei den Funktionen zum Blockieren und Eindämmung von Verhaltensweisen zusammen. 

:::image type="content" source="images/mdatp-next-gen-EDR-behavblockcontain.png" alt-text="Verhaltensblockierung und -eindämmung":::

Verhaltensblockierungs- und Eindämmungsfunktionen funktionieren mit mehreren Komponenten und Features von Defender for Endpoint, um Angriffe sofort zu beenden und zu verhindern, dass Angriffe ausgeführt werden.

- [Der Schutz der nächsten](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) Generation (einschließlich Microsoft Defender Antivirus) kann Bedrohungen erkennen, indem verhaltensweisen analysiert werden und Bedrohungen beendet werden, die bereits ausgeführt wurden.

- [Endpunkterkennung und -reaktion](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) (Endpoint Detection and Response, EDR) empfängt Sicherheitssignale in Ihrem Netzwerk, Ihren Geräten und ihrem Kernelverhalten. Wenn Bedrohungen erkannt werden, werden Warnungen erstellt. Mehrere Warnungen desselben Typs werden in Vorfälle aggregiert, was es Ihrem Sicherheitsteam erleichtert, zu untersuchen und zu reagieren.

- [Defender for Endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) verfügt über eine breite Palette von Optiken für Identitäten, E-Mails, Daten und Apps sowie über netzwerk-, Endpunkt- und Kernelverhaltenssignale, die über EDR empfangen werden. Eine Komponente von [Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/defender/microsoft-threat-protection), Defender for Endpoint verarbeitet und korreliert diese Signale, löst Erkennungswarnungen aus und verbindet verwandte Warnungen bei Vorfällen.

Mit diesen Funktionen können weitere Bedrohungen verhindert oder blockiert werden, auch wenn sie gestartet werden. Wenn verdächtiges Verhalten erkannt wird, ist die Bedrohung enthalten, Warnungen werden erstellt, und Bedrohungen werden in ihren Spuren beendet. 

Die folgende Abbildung zeigt ein Beispiel für eine Warnung, die durch verhaltene Blockierungs- und Eindämmungsfunktionen ausgelöst wurde:

:::image type="content" source="images/blocked-behav-alert.png" alt-text="Beispiel für eine Warnung durch Verhaltensblockierung und Eindämmung":::

## <a name="components-of-behavioral-blocking-and-containment"></a>Komponenten von Verhaltensblockierung und -eindämmung

- Richtliniengesteuerte Regeln zur Reduzierung der **[Angriffsfläche](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/attack-surface-reduction)** auf dem Client Vordefinierte allgemeine Angriffsverhalten werden gemäß den Regeln zur Reduzierung der Angriffsfläche an der Ausführung gehindert. Wenn solche Verhaltensweisen ausgeführt werden sollen, werden sie im Microsoft Defender Security Center als [https://securitycenter.windows.com](https://securitycenter.windows.com) Informationswarnungen angezeigt. (Regeln zur Reduzierung der Angriffsfläche sind standardmäßig nicht aktiviert; Sie konfigurieren Ihre Richtlinien im Microsoft Defender Security Center.)

- **[Clientverhaltensblockierung](client-behavioral-blocking.md)** Bedrohungen für Endpunkte werden durch maschinelles Lernen erkannt und dann automatisch blockiert und behoben. (Clientverhaltensblockierung ist standardmäßig aktiviert.) 

- **[Blockieren von Feedbackschleifen](feedback-loop-blocking.md)** (auch als schneller Schutz bezeichnet) Bedrohungserkennungen werden durch Verhaltensintelligenz beobachtet. Bedrohungen werden angehalten und an der Ausführung auf anderen Endpunkten gehindert. (Das Blockieren von Feedbackschleifen ist standardmäßig aktiviert.) 

- **[Endpunkterkennung und -antwort (EDR) im Blockmodus](edr-in-block-mode.md)** Bösartige Artefakte oder Verhaltensweisen, die durch den Schutz nach der Verletzung beobachtet werden, werden blockiert und enthalten. EDR im Blockmodus funktioniert auch dann, wenn Microsoft Defender Antivirus nicht die primäre Antivirenlösung ist. (EDR im Blockmodus ist standardmäßig nicht aktiviert; Sie aktivieren ihn im Microsoft Defender Security Center.) 

Erwarten Sie mehr im Bereich der Verhaltensblockierung und -eindämmung, da Microsoft die Features und Funktionen des Bedrohungsschutzes weiter verbessert. Informationen zu den geplanten und jetzt veröffentlichten Informationen finden Sie in der [Microsoft 365-Roadmap](https://www.microsoft.com/microsoft-365/roadmap).

## <a name="examples-of-behavioral-blocking-and-containment-in-action"></a>Beispiele für Verhaltensblockierung und Eindämmung in Aktion

Verhaltensblockierungs- und Eindämmungsfunktionen haben Angreifertechniken blockiert, z. B.:

- Abdumping von Anmeldeinformationen aus LSASS
- Prozessübergreifende Einspritzung
- Prozesshing
- Umgehung der Benutzerkontensteuerung
- Manipulation von Antivirenprogrammen (z. B. Deaktivieren oder Hinzufügen der Schadsoftware als Ausschluss)
- Kontaktieren von Command and Control (C&C) zum Herunterladen von Nutzlasten
- Minenmining
- Änderung des Startdatensatzes
- Pass-the-Hash-Angriffe
- Installation des Stammzertifikats
- Ausnutzungsversuch für verschiedene Sicherheitsrisiken

Im Folgenden finden Sie zwei reale Beispiele für das Blockieren und Eindähen von Verhaltensweisen in Aktion.

### <a name="example-1-credential-theft-attack-against-100-organizations"></a>Beispiel 1: Angriff auf den Diebstahl von Anmeldeinformationen gegen 100 Organisationen

Wie unter In hoten verfolgung von schwer fassbaren Bedrohungen [beschrieben: AI-basierte](https://www.microsoft.com/security/blog/2019/10/08/in-hot-pursuit-of-elusive-threats-ai-driven-behavior-based-blocking-stops-attacks-in-their-tracks)verhaltensbasierte Blockierung beendet Angriffe in ihren Spuren, wurde ein Angriff auf Anmeldeinformationendiebstahl gegen 100 Organisationen auf der ganzen Welt durch verhaltensbasierte Blockierungs- und Eindämmungsfunktionen beendet. Spear-Phishing-E-Mail-Nachrichten, die ein Lockendokument enthielten, wurden an die zielgerichteten Organisationen gesendet. Wenn ein Empfänger die Anlage geöffnet hat, konnte ein zugehöriges Remotedokument Code auf dem Gerät des Benutzers ausführen und Lokibot-Schadsoftware laden, die Anmeldeinformationen gestohlen, gestohlene Daten exfiltriert und auf weitere Anweisungen von einem Befehls- und Kontrollserver gewartet hat. 

Verhaltensbasierte Gerätelernmodelle in Defender for Endpoint haben die Techniken des Angreifers an zwei Punkten in der Angriffskette erfasst und beendet:
- Die erste Schutzebene hat das Exploitverhalten erkannt. Gerätelernklassifikatoren in der Cloud identifizierten die Bedrohung ordnungsgemäß als und angewiesenen das Clientgerät sofort, den Angriff zu blockieren.
- Die zweite Schutzschicht, die dazu beit half, Fälle zu beenden, in denen der Angriff über die erste Ebene hinaus kam, erkannte Prozesshohlen, beendete diesen Prozess und entfernte die entsprechenden Dateien (z. B. Lokibot). 

Während der Angriff erkannt und beendet wurde, wurden Warnungen, z. B. eine "Erstzugriffswarnung", ausgelöst und im Microsoft Defender Security Center angezeigt ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ):

:::image type="content" source="images/behavblockcontain-initialaccessalert.png" alt-text="Erstzugriffswarnung im Microsoft Defender Security Center":::

In diesem Beispiel wird gezeigt, wie verhaltensbasierte Gerätelernmodelle in der Cloud neue Schutzebenen gegen Angriffe hinzufügen, auch nachdem sie ausgeführt wurden.

### <a name="example-2-ntlm-relay---juicy-potato-malware-variant"></a>Beispiel 2: NTLM-Relay – Schadsoftwarevariante "Juicy-

Wie im kürzlich veröffentlichten Blogbeitrag [Behavioral blocking and containment: Transforming optics into protection](https://www.microsoft.com/security/blog/2020/03/09/behavioral-blocking-and-containment-transforming-optics-into-protection)beschrieben, hat Defender for Endpoint im Januar 2020 eine Aktivität zur Rechteeskalation auf einem Gerät in einer Organisation erkannt. Eine Warnung mit dem Namen "Mögliche Rechteeskalation mithilfe von NTLM-Relay" wurde ausgelöst.

:::image type="content" source="images/NTLMalertjuicypotato.png" alt-text="NTLM-Warnung für Schadsoftware &quot;Juicy-":::

Die Bedrohung stellte sich als Schadsoftware heraus. Es handelte sich um eine neue, nicht gesehene Variante eines berüchtigten Hackertools namens Juicy Escalation, das von Angreifern verwendet wird, um die Rechteeskalation auf einem Gerät zu erhalten. 

Minuten nach dem Auslösen der Warnung wurde die Datei analysiert und als schädlich bestätigt. Der Prozess wurde angehalten und blockiert, wie in der folgenden Abbildung gezeigt:

:::image type="content" source="images/Artifactblockedjuicypotato.png" alt-text="Artefakt blockiert":::

Wenige Minuten nach dem Blockieren des Artefakts wurden mehrere Instanzen derselben Datei auf demselben Gerät blockiert, was verhindert, dass zusätzliche Angreifer oder andere Schadsoftware auf dem Gerät bereitgestellt werden. 

In diesem Beispiel wird gezeigt, dass bedrohungen bei Denk- und Eindämmungsfunktionen automatisch erkannt, enthalten und blockiert werden. 

## <a name="next-steps"></a>Nächste Schritte

- [Weitere Informationen zu Defender for Endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response)

- [Konfigurieren von Regeln zur Reduzierung der Angriffsfläche](attack-surface-reduction.md)

- [Aktivieren von EDR im Blockmodus](edr-in-block-mode.md)

- [Siehe aktuelle globale Bedrohungsaktivität](https://www.microsoft.com/wdsi/threats)

- [Verschaffen Sie sich eine Übersicht über Microsoft 365 Defender ](https://docs.microsoft.com/microsoft-365/security/defender/microsoft-threat-protection)
