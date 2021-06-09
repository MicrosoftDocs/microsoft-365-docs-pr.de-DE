---
title: Microsoft Defender für Endpunkt– Datenspeicherung und Datenschutz
description: Erfahren Sie, wie Microsoft Defender für Endpunkt den Datenschutz und die gesammelten Daten behandelt.
keywords: Microsoft Defender für Endpunkt, Datenspeicherung und Datenschutz, Speicher, Datenschutz, Lizenzierung, Geolocation, Datenaufbewahrung, Daten
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
ms.openlocfilehash: 0258b2cdbff4a8b20be42e508863985c7402f609
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845510"
---
# <a name="microsoft-defender-for-endpoint-data-storage-and-privacy"></a>Microsoft Defender für Endpunkt– Datenspeicherung und Datenschutz

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Möchten Sie Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

In diesem Abschnitt werden einige der am häufigsten gestellten Fragen zum Datenschutz und zur Datenverarbeitung für Defender für Endpunkt behandelt.
> [!NOTE]
> In diesem Dokument werden die Datenspeicher- und Datenschutzdetails im Zusammenhang mit Defender für Endpunkt erläutert. Weitere Informationen zu Defender für Endpunkt und anderen Produkten und Diensten wie Microsoft Defender Antivirus und Windows 10 finden Sie in den [Datenschutzbestimmungen von Microsoft.](https://go.microsoft.com/fwlink/?linkid=827576) Weitere Informationen finden Sie auch [Windows 10 häufig gestellten Fragen zum Datenschutz.](https://go.microsoft.com/fwlink/?linkid=827577)


## <a name="what-data-does-microsoft-defender-for-endpoint-collect"></a>Welche Daten werden von Microsoft Defender für Endpunkt gesammelt?

Microsoft Defender für Endpunkt sammelt und speichert Informationen von Ihren konfigurierten Geräten in einem kundenspezifischen und getrennten Mandanten speziell für den Dienst zu Verwaltungs-, Nachverfolgungs- und Berichterstellungszwecken. 

Zu den erfassten Informationen gehören Dateidaten (z. B. Dateinamen, Größen und Hashes), Prozessdaten (ausgeführte Prozesse, Hashes), Registrierungsdaten, Netzwerkverbindungsdaten (Host-IPs und Ports) und Gerätedetails (z. B. Geräte-IDs, Namen und die Betriebssystemversion).

Microsoft speichert diese Daten sicher in Microsoft Azure und verwaltet sie gemäß den Microsoft-Datenschutzpraktiken und [Microsoft Trust Center-Richtlinien.](https://go.microsoft.com/fwlink/?linkid=827578)

Diese Daten ermöglichen Defender für Endpunkt Folgendes:
- Proaktive Identifizierung von Angriffsindikatoren (Indicators of Attack, IOAs) in Ihrer Organisation
- Generieren von Warnungen, wenn ein möglicher Angriff erkannt wurde
- Bieten Sie Ihren Sicherheitsvorgängen einen Überblick über Geräte, Dateien und URLs im Zusammenhang mit Bedrohungssignalen aus Ihrem Netzwerk, sodass Sie das Vorhandensein von Sicherheitsbedrohungen im Netzwerk untersuchen und untersuchen können.

Microsoft verwendet Ihre Daten nicht für Werbung.

## <a name="data-protection-and-encryption"></a>Datenschutz und Verschlüsselung
Der Defender für Endpunkt-Dienst nutzt die neuesten Datenschutztechnologien, die auf Microsoft Azure Infrastruktur basieren. 

Es gibt verschiedene Aspekte, die für den Datenschutz relevant sind, um die sich unser Dienst kümmert. Die Verschlüsselung ist eine der wichtigsten Und umfasst datenverschlüsselung im Ruhezustand, Verschlüsselung in Flight und Schlüsselverwaltung mit Key Vault. Weitere Informationen zu anderen Technologien, die vom Defender für Endpunkt-Dienst verwendet werden, finden Sie unter [Übersicht über die Azure-Verschlüsselung.](/azure/security/security-azure-encryption-overview) 

In allen Szenarien werden Daten mindestens mit [](https://en.wikipedia.org/wiki/Advanced_Encryption_Standard) 256-Bit-AES-Verschlüsselung verschlüsselt.


## <a name="data-storage-location"></a>Datenspeicherstandort

Defender für Endpunkt arbeitet in den Microsoft Azure Rechenzentren in der Europäischen Union, im Vereinigten Königreich oder in den Vereinigten Staaten. Kundendaten, die vom Dienst gesammelt werden, können gespeichert werden in: (a) dem geografischen Standort des Mandanten, der während der Bereitstellung identifiziert wurde, oder (b) wenn Defender für Endpunkt einen anderen Microsoft-Onlinedienst zur Verarbeitung dieser Daten verwendet, die Geolocation gemäß den Datenspeicherregeln dieses anderen Onlinediensts.

Kundendaten in pseudonymisierter Form können auch in den zentralen Speicher- und Verarbeitungssystemen in den USA gespeichert werden.

Nach der Konfiguration können Sie den Speicherort Ihrer Daten nicht mehr ändern. Dies bietet eine bequeme Möglichkeit, compliancerisiken zu minimieren, indem Sie aktiv die geografischen Standorte auswählen, an denen sich Ihre Daten befinden. 

## <a name="is-my-data-isolated-from-other-customer-data"></a>Sind meine Daten von anderen Kundendaten isoliert?
Ja, Ihre Daten werden durch Zugriffsauthentifizierung und logische Trennung basierend auf der Kunden-ID isoliert. Jeder Kunde kann nur auf Daten zugreifen, die von seiner eigenen Organisation gesammelt wurden, sowie auf generische Daten, die Microsoft bereitstellt.

## <a name="how-does-microsoft-prevent-malicious-insider-activities-and-abuse-of-high-privilege-roles"></a>Wie verhindert Microsoft böswillige Insideraktivitäten und den Missbrauch von Rollen mit hohen Rechten?

Microsoft-Entwicklern und -Administratoren wurden entwurfsbedingt ausreichende Rechte gewährt, um ihre zugewiesenen Aufgaben zum Betreiben und Weiterentwickeln des Diensts auszuführen. Microsoft stellt Kombinationen aus präventiven, erkennenden und reaktiven Kontrollen bereit, einschließlich der folgenden Mechanismen zum Schutz vor nicht autorisierten Entwickler- und/oder Verwaltungsaktivitäten:

- Strenge Zugriffssteuerung auf vertrauliche Daten
- Kombinationen von Steuerelementen, die die unabhängige Erkennung bösartiger Aktivitäten erheblich verbessern
- Mehrere Ebenen der Überwachung, Protokollierung und Berichterstellung

Darüber hinaus führt Microsoft Hintergrundüberprüfungen für bestimmte Betriebsmitarbeiter durch und schränkt den Zugriff auf Anwendungen, Systeme und Netzwerkinfrastruktur im Verhältnis zum Grad der Hintergrundüberprüfung ein. Betriebsmitarbeiter folgen einem formalen Prozess, wenn sie bei der Erfüllung ihrer Aufgaben auf das Konto eines Kunden oder verwandte Informationen zugreifen müssen.

Der Zugriff auf Daten für Dienste, die in Microsoft Azure Government-Rechenzentren bereitgestellt werden, wird nur betriebsbereiten Mitarbeitern gewährt, die überprüft und genehmigt wurden, um Daten zu verarbeiten, die bestimmten behördlichen Vorschriften und Anforderungen unterliegen, z. B. FedRAMP, NIST 800.171 (DIB), ITAR, IRS 1075, DoD L4 und CJIS.


## <a name="is-data-shared-with-other-customers"></a>Werden Daten für andere Kunden freigegeben?
Nein. Kundendaten sind von anderen Kunden isoliert und werden nicht freigegeben. Erkenntnisse zu den Daten, die sich aus der Microsoft-Verarbeitung ergeben und die keine kundenspezifischen Daten enthalten, können jedoch für andere Kunden freigegeben werden. Jeder Kunde kann nur auf Daten zugreifen, die von seiner eigenen Organisation gesammelt wurden, sowie auf generische Daten, die Microsoft bereitstellt.

## <a name="how-long-will-microsoft-store-my-data-what-is-microsofts-data-retention-policy"></a>Wie lange speichert Microsoft meine Daten? Was ist die Datenaufbewahrungsrichtlinie von Microsoft?
**Beim Onboarding des Diensts**<br>
Standardmäßig werden Die Daten 180 Tage lang aufbewahrt. Sie können jedoch die Datenaufbewahrungsrichtlinie für Ihre Daten angeben. Dadurch wird bestimmt, wie lange Window Defender für Endpunkt Ihre Daten speichert. Es besteht die Flexibilität, zwischen einem Monat und sechs Monaten zu wählen, um die gesetzlichen Complianceanforderungen Ihres Unternehmens zu erfüllen.

**Bei Vertragsbeendigung oder -ablauf**<br>
Ihre Daten werden aufbewahrt und stehen Ihnen zur Verfügung, während sich die Lizenz unter Karenzzeit oder im Angehalten-Modus befindet. Am Ende dieses Zeitraums werden diese Daten aus den Systemen von Microsoft gelöscht, damit sie nicht wiederhergestellt werden können, spätestens 180 Tage nach Vertragsbeendigung oder -ablauf.

**Advanced Hunting-Daten**<br>
Bei der erweiterten Suche handelt es sich um ein abfragebasiertes Tool für die Bedrohungssuche, mit dem Sie Rohdaten von bis zu 30 Tagen erkunden können.


## <a name="can-microsoft-help-us-maintain-regulatory-compliance"></a>Kann Microsoft uns dabei helfen, die Einhaltung gesetzlicher Vorschriften aufrechtzuerhalten?

Microsoft bietet Kunden detaillierte Informationen zu den Sicherheits- und Compliance-Programmen von Microsoft, einschließlich Auditberichten und Compliancepaketen, um Kunden bei der Bewertung von Defender für Endpunkt-Diensten im Hinblick auf ihre eigenen rechtlichen und behördlichen Anforderungen zu unterstützen. Defender für Endpunkt hat eine Reihe von Zertifizierungen wie ISO, SOC, FedRAMP High und PCI erreicht und setzt weitere nationale, regionale und branchenspezifische Zertifizierungen fort.

Durch die Bereitstellung konformer, unabhängig überprüfter Dienste erleichtert Microsoft Kunden die Einhaltung der Infrastruktur und der ausgeführten Anwendungen.

Weitere Informationen zu den Zertifizierungsberichten für Defender für Endpunkt finden Sie im [Microsoft Trust Center.](https://servicetrust.microsoft.com/) 

>Möchten Sie Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-datastorage-belowfoldlink) 
