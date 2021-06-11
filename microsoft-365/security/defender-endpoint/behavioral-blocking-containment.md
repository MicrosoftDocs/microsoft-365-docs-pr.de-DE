---
title: Verhaltensbasiertes Blockieren und Eindämmen
description: Erfahren Sie mehr über die Funktionen zum Blockieren und Eindämmen von Verhaltensweisen in Microsoft Defender für Endpunkt
keywords: Microsoft Defender für Endpunkt, EDR im Blockierungsmodus, Blockieren des passiven Modus
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
ms.openlocfilehash: f2de1f6bf35f4454ed6ab286c0bc8004a0d6301b
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904068"
---
# <a name="behavioral-blocking-and-containment"></a>Verhaltensbasiertes Blockieren und Eindämmen

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Möchten Sie Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="overview"></a>Übersicht

Die heutige Bedrohungslandschaft wird von [dateiloser Schadsoftware](/windows/security/threat-protection/intelligence/fileless-threats) übersprungen, die sich außerhalb des Landes befindet, hochgradig polymorphe Bedrohungen, die schneller als herkömmliche Lösungen mithalten können, und von Menschen betriebene Angriffe, die sich an das anpassen, was Angreifer auf kompromittierten Geräten finden. Herkömmliche Sicherheitslösungen sind nicht ausreichend, um solche Angriffe zu stoppen. Sie benötigen künstliche Intelligenz (KI) und Gerätelernfunktionen (ML), die in [Defender für Endpunkt](/windows/security)enthalten sind, z. B. Verhaltensblockierung und -eindämmung. 

Funktionen zum Blockieren und Eindämmen von Verhaltensweisen können dazu beitragen, Bedrohungen basierend auf ihren Verhaltensweisen und Prozessstrukturen zu erkennen und zu stoppen, selbst wenn die Bedrohung mit der Ausführung begonnen hat. Die Komponenten und Features von Schutz, EDR und Defender für Endpunkt der nächsten Generation arbeiten bei der Blockierung und Eindämmung von Verhaltensweisen zusammen. 

:::image type="content" source="images/mdatp-next-gen-EDR-behavblockcontain.png" alt-text="Verhaltensbasiertes Blockieren und Eindämmen":::

Funktionen zum Blockieren und Eindämmen von Verhaltensweisen funktionieren mit mehreren Komponenten und Features von Defender für Endpunkt, um Angriffe sofort zu stoppen und angriffe zu verhindern.

- [Der Schutz](microsoft-defender-antivirus-in-windows-10.md) der nächsten Generation (der Microsoft Defender Antivirus umfasst) kann Bedrohungen erkennen, indem Verhaltensweisen analysiert und Bedrohungen, die gestartet wurden, beendet werden.

- [Die Endpunkterkennung und -antwort](overview-endpoint-detection-response.md) (EDR) empfängt Sicherheitssignale in Ihrem Netzwerk, Ihren Geräten und Ihrem Kernelverhalten. Wenn Bedrohungen erkannt werden, werden Warnungen erstellt. Mehrere Warnungen des gleichen Typs werden zu Vorfällen aggregiert, was es Ihrem Sicherheitsteam erleichtert, zu untersuchen und zu reagieren.

- [Defender für Endpunkt](overview-endpoint-detection-response.md) verfügt über eine breite Palette von Optiken in Identitäten, E-Mails, Daten und Apps sowie über das Netzwerk-, Endpunkt- und Kernelverhaltenssignale, die über EDR empfangen werden. Eine Komponente von [Microsoft 365 Defender](../defender/microsoft-365-defender.md), Defender für Endpunkt verarbeitet und korreliert diese Signale, löst Erkennungswarnungen aus und verbindet zugehörige Warnungen in Vorfällen.

Mit diesen Funktionen können weitere Bedrohungen verhindert oder blockiert werden, auch wenn sie gestartet werden. Wenn verdächtiges Verhalten erkannt wird, ist die Bedrohung eingedämmt, Warnungen werden erstellt und Bedrohungen werden auf ihren Spuren gestoppt. 

Die folgende Abbildung zeigt ein Beispiel für eine Warnung, die durch Funktionen zum Blockieren und Eindämmen von Verhaltensweisen ausgelöst wurde:

:::image type="content" source="images/blocked-behav-alert.png" alt-text="Beispiel für eine Warnung durch Verhaltensblockierung und -eindämmung":::

## <a name="components-of-behavioral-blocking-and-containment"></a>Komponenten des Blockierens und Eindämmens von Verhaltensweisen

- Regeln zur Reduzierung der **[Angriffsfläche](attack-surface-reduction.md)** auf dem Client Vordefinierte allgemeine Angriffsverhaltensweisen werden gemäß den Regeln zur Verringerung der Angriffsfläche daran gehindert. Wenn solche Verhaltensweisen ausgeführt werden, werden sie im Microsoft 365 Defender ( [https://security.microsoft.com](https://security.microsoft.com) ) als informationsbezogene Warnungen angezeigt. Regeln zur Verringerung der Angriffsfläche sind standardmäßig nicht aktiviert. Sie konfigurieren Ihre Richtlinien im [Microsoft 365 Defender](microsoft-defender-security-center.md).

- **[Blockieren von Clientverhalten](client-behavioral-blocking.md)** Bedrohungen auf Endpunkten werden durch maschinelles Lernen erkannt und dann automatisch blockiert und behoben. (Das Blockieren von Clientverhalten ist standardmäßig aktiviert.) 

- Das Blockieren von **[Feedbackschleifen](feedback-loop-blocking.md)** (auch als schneller Schutz bezeichnet) Bedrohungserkennungen werden durch Verhaltensintelligenz beobachtet. Bedrohungen werden angehalten und daran gehindert, auf anderen Endpunkten ausgeführt zu werden. (Das Blockieren von Feedbackschleifen ist standardmäßig aktiviert.) 

- **[Endpunkterkennung und -antwort (EDR) im Blockierungsmodus](edr-in-block-mode.md)** Bösartige Artefakte oder Verhaltensweisen, die durch den Schutz nach der Verletzung beobachtet werden, werden blockiert und eingedämmt. EDR im Blockierungsmodus funktioniert auch dann, wenn Microsoft Defender Antivirus nicht die primäre Antivirenlösung ist. (EDR im Blockierungsmodus ist nicht standardmäßig aktiviert, sie wird in Microsoft 365 Defender aktiviert.) 

Erwarten Sie mehr im Bereich der Blockierung und Eindämmung von Verhaltensweisen, da Microsoft die Funktionen und Funktionen für den Bedrohungsschutz weiter verbessert. Wenn Sie sehen möchten, was jetzt geplant ist und wie es jetzt ausgeführt wird, besuchen Sie die [Roadmap für Microsoft 365.](https://www.microsoft.com/microsoft-365/roadmap)

## <a name="examples-of-behavioral-blocking-and-containment-in-action"></a>Beispiele für Verhaltensblockierung und -eindämmung in Aktion

Verhaltensbasierte Blockierungs- und Eindämmungsfunktionen haben Angreifertechniken blockiert, z. B. die folgenden:

- Anmeldeinformationen von LSASS
- Prozessübergreifende Einfügung
- Prozessbeendung
- Umgehung der Benutzerkontensteuerung
- Manipulation von Antivirensoftware (z. B. Deaktivieren oder Hinzufügen der Schadsoftware als Ausschluss)
- Kontaktieren von Befehl und Steuerelement (C&C) zum Herunterladen von Nutzlasten
- Minen von Münzen
- Änderung des Startdatensatzes
- Pass-the-Hash-Angriffe
- Installation des Stammzertifikats
- Ausnutzungsversuch für verschiedene Sicherheitsrisiken

Im Folgenden finden Sie zwei praxisbezogene Beispiele für Verhaltensblockierung und -eindämmung in Aktion.

### <a name="example-1-credential-theft-attack-against-100-organizations"></a>Beispiel 1: Diebstahl von Anmeldeinformationen gegen 100 Organisationen

Wie unter "Bedrohungen, die [nur schwer zu erkennen sind" beschrieben: Ki-gesteuertes verhaltensbasiertes Blockieren stoppt Angriffe in ihren Spuren,](https://www.microsoft.com/security/blog/2019/10/08/in-hot-pursuit-of-elusive-threats-ai-driven-behavior-based-blocking-stops-attacks-in-their-tracks)ein Angriff auf den Diebstahl von Anmeldeinformationen gegen 100 Organisationen auf der ganzen Welt wurde durch Verhaltensblockierungs- und Eindämmungsfunktionen gestoppt. Spear-Phishing-E-Mail-Nachrichten, die ein Lockdokument enthielten, wurden an die Zielorganisationen gesendet. Wenn ein Empfänger die Anlage öffnete, konnte ein verwandtes Remotedokument Code auf dem Gerät des Benutzers ausführen und Lokibot-Schadsoftware laden, die Anmeldeinformationen gestohlen, gestohlene Daten exfiltriert und auf weitere Anweisungen von einem Befehls- und Steuerungsserver gewartet hat. 

Verhaltensbasierte Gerätelernmodelle in Defender für Endpunkt haben die Techniken des Angreifers an zwei Punkten in der Angriffskette abgefangen und beendet:

- Die erste Schutzebene hat das Exploit-Verhalten erkannt. Gerätelernklassifizierungen in der Cloud haben die Bedrohung richtig erkannt und das Clientgerät sofort angewiesen, den Angriff zu blockieren.
- Die zweite Schutzebene, die dazu beigetragen hat, Fälle zu stoppen, in denen der Angriff über die erste Ebene hinausgehe, prozessabfällig wurde, diesen Prozess beendete und die entsprechenden Dateien entfernte (z. B. Lokibot). 

Während der Angriff erkannt und beendet wurde, wurden Warnungen, z. B. eine "Warnung zum ersten Zugriff", ausgelöst und im [Microsoft 365 Defender-Portal](microsoft-defender-security-center.md) (früher Microsoft Defender Security Center) angezeigt:

:::image type="content" source="images/behavblockcontain-initialaccessalert.png" alt-text="Warnung zum ersten Zugriff im Microsoft 365 Defender-Portal":::

Dieses Beispiel zeigt, wie verhaltensbasierte Gerätelernmodelle in der Cloud neue Schutzebenen vor Angriffen hinzufügen, auch nachdem sie gestartet wurden.

### <a name="example-2-ntlm-relay---juicy-potato-malware-variant"></a>Beispiel 2: NTLM-Relay – Schadsoftwarevariante "Juicy Variant"

Wie im kürzlich veröffentlichten Blogbeitrag ["Verhaltensblockierung und -eindämmung: Transformieren von Optik in Schutz"](https://www.microsoft.com/security/blog/2020/03/09/behavioral-blocking-and-containment-transforming-optics-into-protection)beschrieben, hat Defender für Endpunkt im Januar 2020 eine Berechtigungseskalierungsaktivität auf einem Gerät in einer Organisation erkannt. Eine Warnung namens "Mögliche Berechtigungseskalation mit NTLM-Relay" wurde ausgelöst.

:::image type="content" source="images/NTLMalertjuicypotato.png" alt-text="NTLM-Warnung für Schadsoftware vom &quot;Juicy&quot;-Schadsoftware":::

Die Bedrohung hat sich als Schadsoftware erwiesen. Es handelte sich um eine neue, noch nicht gesehene Variante eines Hacker-Tools namens Juicy Escalation, das von Angreifern verwendet wird, um eine Rechteeskalation auf einem Gerät zu erhalten. 

Minuten nach dem Auslösen der Warnung wurde die Datei analysiert und als bösartig bestätigt. Der Prozess wurde angehalten und blockiert, wie in der folgenden Abbildung dargestellt:

:::image type="content" source="images/Artifactblockedjuicypotato.png" alt-text="Artefakt blockiert":::

Ein paar Minuten nach der Blockierung des Artefakts wurden mehrere Instanzen derselben Datei auf demselben Gerät blockiert, wodurch verhindert wurde, dass zusätzliche Angreifer oder andere Schadsoftware auf dem Gerät bereitgestellt werden. 

Dieses Beispiel zeigt, dass Bedrohungen bei der Blockierung und Eindämmung von Verhaltensweisen automatisch erkannt, eingedämmt und blockiert werden. 

## <a name="next-steps"></a>Nächste Schritte

- [Weitere Informationen zu Defender für Endpunkt](overview-endpoint-detection-response.md)

- [Konfigurieren der Regeln zur Verringerung der Angriffsfläche](attack-surface-reduction.md)

- [Aktivieren EDR im Blockierungsmodus](edr-in-block-mode.md)

- [Anzeigen der aktuellen globalen Bedrohungsaktivität](https://www.microsoft.com/wdsi/threats)

- [Übersicht über Microsoft 365 Defender](../defender/microsoft-365-defender.md)
