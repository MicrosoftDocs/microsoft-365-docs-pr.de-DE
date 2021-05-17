---
title: Bereitstellen von Microsoft Defender for Endpoint in Ringen
description: Informationen zum Bereitstellen von Microsoft Defender for Endpoint in Ringen
keywords: deploy, rings, evaluate, pilot, insider fast, insider slow, setup, onboard, phase, deployment, deploying, adoption, configuring
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
ms.openlocfilehash: 5aeaa51e5ab8974c8ca26453534396dac14b5853
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/10/2021
ms.locfileid: "52297218"
---
# <a name="deploy-microsoft-defender-for-endpoint-in-rings"></a>Bereitstellen von Microsoft Defender for Endpoint in Ringen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

Die Bereitstellung von Microsoft Defender for Endpoint kann mithilfe eines ringbasierten Bereitstellungsansatzes durchgeführt werden. 

Die Bereitstellungsringe können in den folgenden Szenarien angewendet werden:
- [Neue Bereitstellungen](#new-deployments)
- [Vorhandene Bereitstellungen](#existing-deployments)

## <a name="new-deployments"></a>Neue Bereitstellungen

![Abbildung von Bereitstellungsringen](images/deployment-rings.png)


Ein ringbasierter Ansatz ist eine Methode zum Identifizieren einer Gruppe von Endpunkten, die onboardiert werden müssen, und zum Überprüfen, ob bestimmte Kriterien erfüllt sind, bevor der Dienst auf einer größeren Gruppe von Geräten bereitgestellt wird. Sie können die Beendigungskriterien für jeden Ring definieren und sicherstellen, dass sie erfüllt sind, bevor Sie zum nächsten Ring fahren.

Die Einführung einer ringbasierten Bereitstellung trägt dazu bei, potenzielle Probleme zu reduzieren, die beim Einführung des Diensts auftreten können. Indem Sie zuerst eine bestimmte Anzahl von Geräten pilotieren, können Sie potenzielle Probleme identifizieren und potenzielle Risiken mindern, die auftreten können. 


Tabelle 1 enthält ein Beispiel für die Bereitstellungsringe, die Sie verwenden können. 

**Tabelle 1**

|**Bereitstellungsring**|**Beschreibung**|
|:-----|:-----|
Auswerten | Ring 1: Identifizieren von 50 Systemen für Pilottests 
Pilotprojekt | Ring 2: Identifizieren der nächsten 50-100 Endpunkte in der Produktionsumgebung <br>  
Vollständige Bereitstellung | Ring 3: Rollout des Diensts für den Rest der Umgebung in größeren Schritten



### <a name="exit-criteria"></a>Beendigungskriterien
Ein Beispielsatz von Beendigungskriterien für diese Ringe kann Folgendes enthalten:
- Geräte werden in der Geräteinventarliste angezeigt
- Warnungen werden im Dashboard angezeigt
- [Ausführen eines Erkennungstests](run-detection-test.md)
- [Ausführen eines simulierten Angriffs auf einem Gerät](attack-simulations.md)

### <a name="evaluate"></a>Auswerten
Identifizieren Sie eine kleine Anzahl von Testcomputern in Ihrer Umgebung, die für das Onboarding in den Dienst verwendet werden sollen. Idealerweise wären diese Computer weniger als 50 Endpunkte. 


### <a name="pilot"></a>Pilotprojekt
Microsoft Defender for Endpoint unterstützt eine Vielzahl von Endpunkten, die Sie in den Dienst integrieren können. Identifizieren Sie in diesem Ring mehrere Zu integrierende Geräte, und fahren Sie basierend auf den von Ihnen definierten Beendigungskriterien mit dem nächsten Bereitstellungsring fort.

In der folgenden Tabelle sind die unterstützten Endpunkte und das entsprechende Tool aufgeführt, mit dem Sie Geräte in den Dienst integrieren können. 

| Endpunkt     | Bereitstellungstool                       |
|--------------|------------------------------------------|
| **Windows**  |  [Lokales Skript (bis zu 10 Geräte)](configure-endpoints-script.md) <br> HINWEIS: Wenn Sie mehr als 10 Geräte in einer Produktionsumgebung bereitstellen möchten, verwenden Sie stattdessen die Gruppenrichtlinienmethode oder die anderen unten aufgeführten unterstützten Tools.<br>  [Gruppenrichtlinie](configure-endpoints-gp.md) <br>  [Microsoft Endpoint Manager/ Mobile Device Manager](configure-endpoints-mdm.md) <br>   [Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md) <br> [VDI-Skripts](configure-endpoints-vdi.md)   |
| **macOS**    | [Lokales Skript](mac-install-manually.md) <br> [Microsoft Endpoint Manager](mac-install-with-intune.md) <br> [JAMF Pro](mac-install-with-jamf.md) <br> [Verwaltung mobiler Geräte - Mobile Device Management](mac-install-with-other-mdm.md) |
| **Linux Server** | [Lokales Skript](linux-install-manually.md) <br> [100](linux-install-with-puppet.md) <br> [Ansible](linux-install-with-ansible.md)|
| **iOS**      | [App-basiert](ios-install.md)                                |
| **Android**  | [Microsoft Endpoint Manager](android-intune.md)               | 




### <a name="full-deployment"></a>Vollständige Bereitstellung
In dieser Phase können Sie das [Bereitstellungsmaterial planen](deployment-strategy.md) verwenden, um Die Bereitstellung zu planen. 


Verwenden Sie das folgende Material, um die geeignete Microsoft Defender for Endpoint-Architektur auszuwählen, die am besten in Ihrer Organisation verwendet wird.

|**Aspekt**|**Beschreibung**|
|:-----|:-----|
|[![Thumb image for Microsoft Defender for Endpoint deployment strategy](images/mdatp-deployment-strategy.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)<br/> [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  \| [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) | Das Architekturmaterial hilft Ihnen bei der Planung der Bereitstellung für die folgenden Architekturen: <ul><li> Cloudspezifisch </li><li> Co-Management </li><li> Lokal</li><li>Auswertung und lokales Onboarding</li>




## <a name="existing-deployments"></a>Vorhandene Bereitstellungen

### <a name="windows-endpoints"></a>Windows-Endpunkte
Für Windows- und/oder Windows-Server wählen Sie mehrere Computer aus, die Sie mit dem Security **Update Validation Program (SUVP)** im Voraus testen möchten (vor patch Tuesday).

Weitere Informationen finden Sie unter:
- [Was ist das Validierungsprogramm für Sicherheitsupdates?](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/what-is-the-security-update-validation-program/ba-p/275767)
- [Softwareupdatevalidierungsprogramm und Microsoft Center zum Schutz vor Malware Einrichtung – Interaktive TwC-Zeitachse Teil 4](https://www.microsoft.com/security/blog/2012/03/28/software-update-validation-program-and-microsoft-malware-protection-center-establishment-twc-interactive-timeline-part-4/)


### <a name="non-windows-endpoints"></a>Nicht-Windows-Endpunkte
Mit macOS und Linux können Sie einige Systeme verwenden und im Betakanal ausführen.

>[!NOTE]
>Idealerweise mindestens ein Sicherheitsadministrator und ein Entwickler, damit Sie Kompatibilitäts-, Leistungs- und Zuverlässigkeitsprobleme finden können, bevor der Build den Build in den aktuellen Kanal schafft.

Die Auswahl des Kanals bestimmt den Typ und die Häufigkeit der Updates, die auf Ihrem Gerät angeboten werden. Geräte in beta sind die ersten, die Updates und neue Features erhalten, gefolgt von Preview und zuletzt von Current.

![Bild von Insiderringen](images/insider-rings.png)

Um eine Vorschau neuer Features anzuzeigen und frühzeitig Feedback zu geben, wird empfohlen, einige Geräte in Ihrem Unternehmen für die Verwendung von Beta oder Preview zu konfigurieren.

>[!WARNING]
>Wenn Sie den Kanal nach der Erstinstallation wechseln, muss das Produkt neu installiert werden. Um den Produktkanal zu wechseln: Deinstallieren Sie das vorhandene Paket, konfigurieren Sie Ihr Gerät neu, um den neuen Kanal zu verwenden, und führen Sie die Schritte in diesem Dokument aus, um das Paket vom neuen Speicherort aus zu installieren.
