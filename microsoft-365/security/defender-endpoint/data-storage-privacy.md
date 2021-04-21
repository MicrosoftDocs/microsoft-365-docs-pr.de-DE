---
title: Datenspeicherung und Datenschutz von Microsoft Defender for Endpoint
description: Erfahren Sie, wie Microsoft Defender for Endpoint den Datenschutz und die erfassten Daten verarbeitet.
keywords: Microsoft Defender for Endpoint, Microsoft Defender for Endpoint, Datenspeicherung und Datenschutz, Speicher, Datenschutz, Lizenzierung, Geolocation, Datenspeicherung, Daten
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: dfdfcdcfb8d76f95e3b866f5f95af7efd94ed59e
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2021
ms.locfileid: "51904128"
---
# <a name="microsoft-defender-for-endpoint-data-storage-and-privacy"></a>Datenspeicherung und Datenschutz von Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

Dieser Abschnitt behandelt einige der am häufigsten gestellten Fragen zum Datenschutz und zur Datenverarbeitung für Defender for Endpoint.
> [!NOTE]
> In diesem Dokument werden die Datenspeicherungs- und Datenschutzdetails im Zusammenhang mit Defender for Endpoint erläutert. Weitere Informationen zu Defender for Endpoint und anderen Produkten und Diensten wie Microsoft Defender Antivirus und Windows 10 finden Sie unter [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=827576). Weitere Informationen finden Sie unter Häufig gestellte Fragen zu [Windows 10-Datenschutz.](https://go.microsoft.com/fwlink/?linkid=827577)


## <a name="what-data-does-microsoft-defender-for-endpoint-collect"></a>Welche Daten werden von Microsoft Defender for Endpoint gesammelt?

Microsoft Defender for Endpoint sammelt und speichern Informationen von Ihren konfigurierten Geräten in einem kundenspezifischen und getrennten Mandanten, der für den Dienst für Verwaltungs-, Nachverfolgungs- und Berichterstellungszwecke spezifisch ist. 

Zu den erfassten Informationen gehören Dateidaten (z. B. Dateinamen, Größen und Hashes), Prozessdaten (laufende Prozesse, Hashes), Registrierungsdaten, Netzwerkverbindungsdaten (Host-IPs und Ports) und Gerätedetails (z. B. Gerätebezeichner, Namen und die Betriebssystemversion).

Microsoft speichert diese Daten sicher in Microsoft Azure und verwaltet sie in Übereinstimmung mit den Datenschutzpraktiken von Microsoft und [den Microsoft Trust Center-Richtlinien.](https://go.microsoft.com/fwlink/?linkid=827578)

Diese Daten ermöglichen Defender for Endpoint:
- Proaktive Identifizierung von Angriffsindikatoren (IoAs) in Ihrer Organisation
- Generieren von Warnungen, wenn ein möglicher Angriff erkannt wurde
- Bieten Sie Ihren Sicherheitsvorgängen einen Einblick in Geräte, Dateien und URLs im Zusammenhang mit Bedrohungssignalen aus Ihrem Netzwerk, sodass Sie das Vorhandensein von Sicherheitsbedrohungen im Netzwerk untersuchen und untersuchen können.

Microsoft verwendet Ihre Daten nicht für Werbung.

## <a name="data-protection-and-encryption"></a>Datenschutz und Verschlüsselung
Der Defender for Endpoint-Dienst verwendet moderne Datenschutztechnologien, die auf der Microsoft Azure-Infrastruktur basieren. 

Es gibt verschiedene Aspekte, die für den Datenschutz relevant sind, die unser Dienst übernimmt. Die Verschlüsselung ist eine der wichtigsten Und umfasst die Datenverschlüsselung im Ruhebetrieb, die Verschlüsselung im Flight und die Schlüsselverwaltung mit Key Vault. Weitere Informationen zu anderen Technologien, die vom Defender for Endpoint-Dienst verwendet werden, finden Sie unter [Azure encryption overview](https://docs.microsoft.com/azure/security/security-azure-encryption-overview). 

In allen Szenarien werden Daten mindestens mit [](https://en.wikipedia.org/wiki/Advanced_Encryption_Standard) 256-Bit-AES-Verschlüsselung verschlüsselt.


## <a name="data-storage-location"></a>Datenspeicherstandort

Defender for Endpoint ist in den Microsoft Azure-Rechenzentren in der Europäischen Union, im Vereinigten Königreich oder in den Vereinigten Staaten tätig. Vom Dienst erfasste Kundendaten können gespeichert werden in: (a) dem geografischen Standort des Mandanten, der während der Bereitstellung identifiziert wurde, oder (b) wenn Defender for Endpoint einen anderen Microsoft Onlinedienst verwendet, um solche Daten zu verarbeiten, die Geolocation gemäß den Datenspeicherregeln dieses anderen Onlinediensts.

Kundendaten in pseudonymisierter Form können auch in den zentralen Speicher- und Verarbeitungssystemen in den USA gespeichert werden.

Nach der Konfiguration können Sie den Speicherort ihrer Daten nicht mehr ändern. Auf diese Weise können Sie das Compliancerisiko minimieren, indem Sie aktiv die geografischen Standorte auswählen, an denen sich Ihre Daten befinden. 

## <a name="is-my-data-isolated-from-other-customer-data"></a>Sind meine Daten von anderen Kundendaten isoliert?
Ja, Ihre Daten werden durch Zugriffsauthentifizierung und logische Trennung basierend auf der Kunden-ID isoliert. Jeder Kunde kann nur auf Daten zugreifen, die von seiner eigenen Organisation und generischen Daten von Microsoft erfasst werden.

## <a name="how-does-microsoft-prevent-malicious-insider-activities-and-abuse-of-high-privilege-roles"></a>Wie verhindert Microsoft böswillige Insideraktivitäten und missbraucht Rollen mit hohen Rechten?

Microsoft-Entwicklern und -Administratoren wurden entwurfsweise ausreichende Rechte zur Ausführung ihrer zugewiesenen Aufgaben zum Betrieb und zur Weiterentwicklung des Diensts zugewiesen. Microsoft stellt Kombinationen aus vorbeugenden, detektivischen und reaktiven Steuerelementen einschließlich der folgenden Mechanismen zum Schutz vor nicht autorisierten Entwickler- und/oder Verwaltungsaktivitäten zur Verfügung:

- Strenge Zugriffssteuerung auf vertrauliche Daten
- Kombinationen von Steuerelementen, die die unabhängige Erkennung bösartiger Aktivitäten erheblich verbessern
- Mehrere Überwachungs-, Protokollierungs- und Berichtsebenen

Darüber hinaus führt Microsoft Hintergrundüberprüfungen für bestimmte Betriebsmitarbeiter durch und beschränkt den Zugriff auf Anwendungen, Systeme und Netzwerkinfrastruktur im Verhältnis zur Hintergrundüberprüfungsstufe. Das Betriebspersonal folgt einem formalen Prozess, wenn er bei der Aufgabenerführung auf das Konto oder die zugehörigen Informationen eines Kunden zugreifen muss.

Der Zugriff auf Daten für In Microsoft Azure Government-Rechenzentren bereitgestellte Dienste wird nur Betriebspersonal gewährt, das geprüft und genehmigt wurde, um Daten zu verarbeiten, die bestimmten gesetzlichen Bestimmungen und Anforderungen unterliegen, z. B. FedRAMP, NIST 800.171 (DIB), ITAR, IRS 1075, DoD L4 und CJIS.


## <a name="is-data-shared-with-other-customers"></a>Werden Daten für andere Kunden freigegeben?
Nein. Kundendaten werden von anderen Kunden isoliert und nicht freigegeben. Einblicke in die Daten, die sich aus der Microsoft-Verarbeitung ergeben und keine kundenspezifischen Daten enthalten, können jedoch an andere Kunden weitergegeben werden. Jeder Kunde kann nur auf Daten zugreifen, die von seiner eigenen Organisation und generischen Daten von Microsoft erfasst werden.

## <a name="how-long-will-microsoft-store-my-data-what-is-microsofts-data-retention-policy"></a>Wie lange werden meine Daten von Microsoft gespeichert? Was ist die Datenaufbewahrungsrichtlinie von Microsoft?
**Beim Onboarding des Diensts**<br>
Standardmäßig werden Daten 180 Tage lang aufbewahrt. Sie können jedoch die Datenaufbewahrungsrichtlinie für Ihre Daten angeben. Dies bestimmt, wie lange Window Defender for Endpoint Ihre Daten speichern wird. Es gibt eine Flexibilität bei der Auswahl zwischen einem Monat und sechs Monaten, um die Gesetzlichen Complianceanforderungen Ihres Unternehmens zu erfüllen.

**Bei Beendigung oder Ablauf des Vertrags**<br>
Ihre Daten werden aufbewahrt und stehen Ihnen zur Verfügung, während sich die Lizenz im Kulanzzeitraum oder angehaltenen Modus befindet. Am Ende dieses Zeitraums werden diese Daten aus den Systemen von Microsoft gelöscht, damit sie nicht mehr als 180 Tage nach Beendigung oder Ablauf des Vertrags wiederherstellbar sind.

**Erweiterte Suchesdaten**<br>
Bei der erweiterten Suche handelt es sich um ein abfragebasiertes Tool für die Bedrohungssuche, mit dem Sie Rohdaten von bis zu 30 Tagen erkunden können.


## <a name="can-microsoft-help-us-maintain-regulatory-compliance"></a>Kann Microsoft uns bei der Einhaltung gesetzlicher Vorschriften unterstützen?

Microsoft stellt Kunden detaillierte Informationen zu Microsofts Sicherheits- und Complianceprogrammen, einschließlich Überwachungsberichten und Compliancepaketen, zur Verfügung, um Kunden bei der Bewertung von Defender for Endpoint-Diensten mit ihren eigenen gesetzlichen und behördlichen Anforderungen zu unterstützen. Defender for Endpoint hat eine Reihe von Zertifizierungen wie ISO, SOC, FedRAMP High und PCI erreicht und verfolgt weiterhin zusätzliche nationale, regionale und branchenspezifische Zertifizierungen.

Durch die Bereitstellung von kompatiblen, unabhängig überprüften Diensten erleichtert Microsoft Kunden die Einhaltung der von ihnen ausgeführten Infrastruktur und Anwendungen.

Weitere Informationen zu den Defender for Endpoint-Zertifizierungsberichten finden Sie unter [Microsoft Trust Center](https://servicetrust.microsoft.com/). 

>Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-datastorage-belowfoldlink) 
