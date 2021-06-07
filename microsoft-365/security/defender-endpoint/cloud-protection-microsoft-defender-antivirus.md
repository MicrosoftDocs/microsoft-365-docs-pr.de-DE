---
title: Schutz über die Cloud und Microsoft Defender Antivirus
description: Erfahren Sie mehr über den über die Cloud bereitgestellten Schutz und Microsoft Defender Antivirus
keywords: Microsoft Defender Antivirus, Technologien der nächsten Generation, Av der nächsten Generation, maschinelles Lernen, Antischadsoftware, Sicherheit, Defender, Cloud, über die Cloud bereitgestellter Schutz
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.reviewer: shwjha
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 836025b42bbe6142f462ee31f266a636f5101fe9
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/05/2021
ms.locfileid: "52783005"
---
# <a name="cloud-delivered-protection-and-microsoft-defender-antivirus"></a>Schutz über die Cloud und Microsoft Defender Antivirus

**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)
- Microsoft Defender Antivirus

Technologien der nächsten Generation in Microsoft Defender Antivirus nahezu sofortigen automatisierten Schutz vor neuen und neuen Bedrohungen bieten. Um neue Bedrohungen dynamisch zu erkennen, arbeiten Technologien der nächsten Generation mit großen Gruppen von verbundenen Daten in den Microsoft Intelligent Security-Graph und leistungsstarken KI-Systemen (Künstliche Intelligenz), die von fortschrittlichen Machine Learning-Modellen gesteuert werden. Microsoft Defender Antivirus verwendet mehrere Erkennungs- und Verhinderungstechnologien, um präzisen, echtzeitbasierten und intelligenten Schutz zu bieten. 

> [!TIP]
> Möchten Sie mehr erfahren? Weitere Informationen zu den erweiterten Technologien im [Kern des Schutzes der nächsten Generation von Microsoft Defender für Endpunkt](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)finden Sie im Blogbeitrag.

Microsoft Defender Antivirus funktioniert nahtlos mit Microsoft Cloud Services. Diese Cloud-Schutzdienste, auch als Microsoft Advanced Protection Service (MAPS) bezeichnet, verbessern den standardmäßigen Echtzeitschutz und stellen die wohl beste Antivirenschutzlösung bereit. 

> [!NOTE]
> Der Microsoft Defender Antivirus Clouddienst ist ein Mechanismus für die Bereitstellung eines aktualisierten Schutzes für Ihr Netzwerk und Ihre Endpunkte. Als Clouddienst ist es nicht nur Schutz für in der Cloud gespeicherte Dateien; Stattdessen verwendet der Clouddienst verteilte Ressourcen und maschinelles Lernen, um Schutz für Ihre Endpunkte in einer Geschwindigkeit bereitzustellen, die viel schneller als herkömmliche Security Intelligence-Updates ist.

Mit dem über die Cloud bereitgestellten Schutz bieten Technologien der nächsten Generation eine schnelle Identifizierung neuer Bedrohungen, manchmal sogar, bevor ein einzelner Computer infiziert wird. Die folgenden Blogbeiträge veranschaulichen, wie der über die Cloud bereitgestellte Schutz funktioniert:

- [Warum Microsoft Defender Antivirus am häufigsten im Unternehmen bereitgestellt wird](https://www.microsoft.com/security/blog/2018/03/22/why-windows-defender-antivirus-is-the-most-deployed-in-the-enterprise) 
- [Die Verhaltensüberwachung in Kombination mit maschinellem Lernen beeinträchtigt eine massive Coin-Mining-Kampagne](https://www.microsoft.com/security/blog/2018/03/07/behavior-monitoring-combined-with-machine-learning-spoils-a-massive-dofoil-coin-mining-campaign)
- [Wie künstliche Intelligenz einen "Emotet"-Ausbruch stoppte](https://www.microsoft.com/security/blog/2018/02/14/how-artificial-intelligence-stopped-an-emotet-outbreak)
- [Detonieren eines schlechten Diktierens: Microsoft Defender Antivirus und mehrstufige Machine Learning-Abwehr](https://www.microsoft.com/security/blog/2017/12/11/detonating-a-bad-rabbit-windows-defender-antivirus-and-layered-machine-learning-defenses)
- [Microsoft Defender Antivirus Cloudschutzdienst: Erweiterte Echtzeitschutzmaßnahmen gegen noch nie zuvor gesehene Schadsoftware](https://www.microsoft.com/security/blog/2017/07/18/windows-defender-antivirus-cloud-protection-service-advanced-real-time-defense-against-never-before-seen-malware) 
 
## <a name="how-to-get-cloud-delivered-protection"></a>So erhalten Sie über die Cloud bereitgestellten Schutz 

Der über die Cloud bereitgestellte Schutz ist standardmäßig aktiviert. Möglicherweise müssen Sie es jedoch erneut aktivieren, wenn es im Rahmen früherer Organisationsrichtlinien deaktiviert wurde. Weitere Informationen finden Sie unter Aktivieren des über [die Cloud bereitgestellten Schutzes.](enable-cloud-protection-microsoft-defender-antivirus.md)

Organisationen, die Windows 10 E5 ausführen, können auch Dynamische Intelligence-Notfallupdates nutzen, die nahezu in Echtzeit Schutz vor neuen Bedrohungen bieten. Wenn Sie den über die Cloud bereitgestellten Schutz aktivieren, können Korrekturen für Schadsoftwareprobleme innerhalb von Minuten über die Cloud bereitgestellt werden, anstatt auf das nächste Update zu warten. [Konfigurieren Sie Microsoft Defender Antivirus, um automatisch neue Schutzupdates basierend auf Berichten von unserem Clouddienst zu erhalten.](manage-event-based-updates-microsoft-defender-antivirus.md#cloud-report-updates)

> [!TIP]
> Besuchen Sie die Windows Defender Testground-Website unter [demo.wd.microsoft.com,](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) um zu bestätigen, dass das Feature funktioniert, und sehen Sie, wie es funktioniert.

## <a name="next-steps"></a>Nächste Schritte

1. [Aktivieren Sie den über die Cloud bereitgestellten Schutz.](enable-cloud-protection-microsoft-defender-antivirus.md) Sie können den über die Cloud bereitgestellten Schutz mit Microsoft Endpoint Manager (die jetzt Microsoft Endpoint Configuration Manager und Microsoft Intune umfasst), Gruppenrichtlinien oder PowerShell-Cmdlets aktivieren.

2. [Geben Sie die über die Cloud bereitgestellte Schutzebene an.](specify-cloud-protection-level-microsoft-defender-antivirus.md) Sie können das von der Cloud angebotene Schutzniveau mithilfe von Microsoft Endpoint Manager oder Gruppenrichtlinien angeben. Die Schutzebene wirkt sich auf die Menge der informationen aus, die für die Cloud freigegeben wurden, und die Art und Weise, wie aggressiv neue Dateien blockiert werden.

3. Konfigurieren und Überprüfen von [Netzwerkverbindungen für Microsoft Defender Antivirus.](configure-network-connections-microsoft-defender-antivirus.md) Es gibt bestimmte Microsoft-URLs, mit denen Ihr Netzwerk und Ihre Endpunkte eine Verbindung herstellen können müssen, damit der über die Cloud bereitgestellte Schutz effektiv funktioniert. In diesem Artikel werden die URLs aufgeführt, die über Firewall- oder Netzwerkfilterregeln zulässig sein sollten, sowie Anweisungen zur Bestätigung, dass Ihr Netzwerk ordnungsgemäß im über die Cloud bereitgestellten Schutz registriert ist.

4. [Konfigurieren Sie das Feature "Bei erster Anzeige blockieren".](configure-block-at-first-sight-microsoft-defender-antivirus.md) Das Feature "Bei erster Anzeige blockieren" kann neue Schadsoftware innerhalb von Sekunden blockieren, ohne stundenlang auf herkömmliche Security Intelligence warten zu müssen. Sie können sie mithilfe Microsoft Endpoint Manager oder mithilfe von Gruppenrichtlinien aktivieren und konfigurieren.

5. [Konfigurieren Des Cloudblock-Timeoutzeitraums.](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md) Microsoft Defender Antivirus können die Ausführung verdächtiger Dateien blockieren, während sie unseren über die Cloud bereitgestellten Schutzdienst abfragen. Mit Microsoft Endpoint Manager oder Gruppenrichtlinien können Sie konfigurieren, wie viel Zeit die Ausführung der Datei verhindert wird.