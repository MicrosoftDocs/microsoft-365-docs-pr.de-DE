---
title: Bereitstellen von Microsoft Defender für Endpunkt in Ringen
description: Erfahren Sie, wie Sie Microsoft Defender für Endpunkt in Ringen bereitstellen
keywords: bereitstellen, Ringe, auswerten, Pilot, Insider schnell, Insider langsam, Setup, onboard, Phase, Bereitstellung, bereitstellen, Einführung, Konfigurieren
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-endpointprotect
- m365solution-overview
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 4fffbbb519f9c31b5343e665958bcb47436a2d50
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289343"
---
# <a name="deploy-microsoft-defender-for-endpoint-in-rings"></a>Bereitstellen von Microsoft Defender für Endpunkt in Ringen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Möchten Sie Defender für Endpunkt erfahren? [Registrieren Sie sich für eine kostenlose Testversion](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

Die Bereitstellung von Microsoft Defender für Endpunkt kann mithilfe eines ringbasierten Bereitstellungsansatzes erfolgen. 

Die Bereitstellungsringe können in den folgenden Szenarien angewendet werden:
- [Neue Bereitstellungen](#new-deployments)
- [Vorhandene Bereitstellungen](#existing-deployments)

## <a name="new-deployments"></a>Neue Bereitstellungen

![Abbildung der Bereitstellungsringe](images/deployment-rings.png)


Ein ringbasierter Ansatz ist eine Methode zum Identifizieren einer Gruppe von Zu integrierenden Endpunkten und zum Überprüfen, ob bestimmte Kriterien erfüllt sind, bevor der Dienst auf einer größeren Gruppe von Geräten bereitgestellt wird. Sie können die Beendigungskriterien für jeden Ring definieren und sicherstellen, dass sie erfüllt sind, bevor Sie zum nächsten Ring wechseln.

Die Einführung einer ringbasierten Bereitstellung trägt dazu bei, potenzielle Probleme zu reduzieren, die beim Rollout des Diensts auftreten können. Indem Sie zuerst eine bestimmte Anzahl von Geräten testen, können Sie potenzielle Probleme identifizieren und potenzielle Risiken mindern, die auftreten können. 

Tabelle 1 enthält ein Beispiel für die Bereitstellungsringe, die Sie verwenden können.

**Tabelle 1**

|Bereitstellungsring|Beschreibung
|---|---|
Auswerten | Ring 1: Identifizieren von 50 Systemen für Pilottests
Pilotprojekt | Ring 2: Identifizieren der nächsten 50 bis 100 Endpunkte in der Produktionsumgebung
Vollständige Bereitstellung | Ring 3: Rollout des Diensts für die restliche Umgebung in größeren Schritten

### <a name="exit-criteria"></a>Beendigungskriterien

Eine Beispielgruppe von Beendigungskriterien für diese Ringe kann Folgendes umfassen:

- Geräte werden in der Gerätebestandsliste angezeigt
- Warnungen werden im Dashboard angezeigt
- [Ausführen eines Erkennungstests](run-detection-test.md)
- [Ausführen eines simulierten Angriffs auf ein Gerät](attack-simulations.md)

### <a name="evaluate"></a>Auswerten

Identifizieren Sie eine kleine Anzahl von Testcomputern in Ihrer Umgebung, die in den Dienst integriert werden sollen. Im Idealfall wären diese Computer weniger als 50 Endpunkte.

### <a name="pilot"></a>Pilotprojekt

Microsoft Defender für Endpunkt unterstützt eine Vielzahl von Endpunkten, die Sie in den Dienst integrieren können. Identifizieren Sie in diesem Ring mehrere Geräte, die integriert werden sollen, und entscheiden Sie sich basierend auf den von Ihnen definierten Beendigungskriterien, mit dem nächsten Bereitstellungsring fortzufahren.

In der folgenden Tabelle sind die unterstützten Endpunkte und das entsprechende Tool aufgeführt, mit dem Sie Geräte in den Dienst integrieren können. 

| Endpunkt     | Bereitstellungstool                       |
|--------------|------------------------------------------|
| **Windows**  |  [Lokales Skript (bis zu 10 Geräte)](configure-endpoints-script.md) <br> HINWEIS: Wenn Sie mehr als 10 Geräte in einer Produktionsumgebung bereitstellen möchten, verwenden Sie stattdessen die Gruppenrichtlinienmethode oder die anderen unten aufgeführten unterstützten Tools.<br>  [Gruppenrichtlinie](configure-endpoints-gp.md) <br>  [Microsoft Endpoint Manager/Mobile Device Manager](configure-endpoints-mdm.md) <br>   [Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md) <br> [VDI-Skripts](configure-endpoints-vdi.md)   |
| **macOS**    | [Lokales Skript](mac-install-manually.md) <br> [Microsoft Endpoint Manager](mac-install-with-intune.md) <br> [JAMF-Pro](mac-install-with-jamf.md) <br> [Verwaltung mobiler Geräte - Mobile Device Management](mac-install-with-other-mdm.md) |
| **Linux Server** | [Lokales Skript](linux-install-manually.md) <br> [Puppe](linux-install-with-puppet.md) <br> [Ansible](linux-install-with-ansible.md)|
| **iOS**      | [App-basiert](ios-install.md)                                |
| **Android**  | [Microsoft Endpoint Manager](android-intune.md)               |

### <a name="full-deployment"></a>Vollständige Bereitstellung

In dieser Phase können Sie das [Bereitstellungsmaterial zum Planen](deployment-strategy.md) ihrer Bereitstellung verwenden. 

Verwenden Sie das folgende Material, um die entsprechende Microsoft Defender für Endpunkt-Architektur auszuwählen, die ihre Organisation am besten eignet.

|**Item**|**Beschreibung**|
|:-----|:-----|
|[![Miniaturbild für die Bereitstellungsstrategie von Microsoft Defender für Endpunkt](images/mdatp-deployment-strategy.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)<br/> [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  \| [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) | Das Architekturmaterial hilft Ihnen bei der Planung der Bereitstellung für die folgenden Architekturen: <ul><li> Cloudspezifisch </li><li> Co-Management </li><li> Lokal</li><li>Auswertung und lokales Onboarding</li></ul>

## <a name="existing-deployments"></a>Vorhandene Bereitstellungen

### <a name="windows-endpoints"></a>Windows Endpunkte

Für Windows und/oder Windows Server wählen Sie mehrere Computer aus, die Sie vorab (vor Patch-Dienstag) mithilfe des **SECURITY Update Validation-Programms (DOPPELKLICKP)** testen möchten.

Weitere Informationen finden Sie unter:

- [Was ist das Überprüfungsprogramm für Sicherheitsupdates?](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/what-is-the-security-update-validation-program/ba-p/275767)
- [Software Update Validation Program and Microsoft Center zum Schutz vor Malware Establishment – TwC Interactive Timeline Part 4](https://www.microsoft.com/security/blog/2012/03/28/software-update-validation-program-and-microsoft-malware-protection-center-establishment-twc-interactive-timeline-part-4/)

### <a name="non-windows-endpoints"></a>Nicht Windows Endpunkte

Mit macOS und Linux können Sie einige Systeme verwenden und im Betakanal ausführen.

> [!NOTE]
> Idealerweise mindestens ein Sicherheitsadministrator und ein Entwickler, damit Sie Kompatibilitäts-, Leistungs- und Zuverlässigkeitsprobleme finden können, bevor der Build in den aktuellen Kanal gelangt.

Die Wahl des Kanals bestimmt den Typ und die Häufigkeit von Updates, die auf Ihrem Gerät angeboten werden. Geräte in der Betaversion sind die ersten Geräte, die Updates und neue Features erhalten, gefolgt von der Vorschau und schließlich von Current.

![Abbildung von Insiderringen](images/insider-rings.png)

Um eine Vorschau der neuen Features anzuzeigen und frühzeitigEs Feedback zu geben, empfiehlt es sich, einige Geräte in Ihrem Unternehmen für die Verwendung von Beta oder Vorschau zu konfigurieren.

> [!WARNING]
> Um den Kanal nach der Erstinstallation zu wechseln, muss das Produkt neu installiert werden. Um den Produktkanal zu wechseln: Deinstallieren Sie das vorhandene Paket, konfigurieren Sie Ihr Gerät erneut für die Verwendung des neuen Kanals, und führen Sie die Schritte in diesem Dokument aus, um das Paket vom neuen Speicherort aus zu installieren.
