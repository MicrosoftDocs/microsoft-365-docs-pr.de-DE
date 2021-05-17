---
title: Übersicht über die unbeschränkte Archivierung
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 37cdbb02-a24a-4093-8bdb-2a7f0b3a19ee
description: Erfahren Sie mehr über die automatische Erweiterung der Archivierung, die unbegrenzten Archivspeicher für Exchange Online bietet.
ms.openlocfilehash: d61d3649ed65a93298928cced21180bbeca6aa95
ms.sourcegitcommit: 7b8104015a76e02bc215e1cf08069979c70650ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/31/2021
ms.locfileid: "51476266"
---
# <a name="overview-of-unlimited-archiving"></a>Übersicht über die unbeschränkte Archivierung

In Office 365 bieten Archivpostfächer Benutzern zusätzlichen Postfachspeicherplatz. Nachdem das Archivpostfach eines Benutzers aktiviert wurde, stehen bis zu 100 GB zusätzlicher Speicher zur Verfügung. In der Vergangenheit, als das Speicherkontingent von 100 GB erreicht wurde, mussten Sich Organisationen an Microsoft wenden, um zusätzlichen Speicherplatz für ein Archivpostfach anantragen zu können. Das ist nicht mehr der Fall.

Das unbegrenzte Archivierungsfeature in Microsoft 365 (als *automatisch* erweiternde Archivierung bezeichnet) bietet zusätzlichen Speicher in Archivpostfächern. Wenn das Speicherkontingent im Archivpostfach erreicht ist, erhöht Microsoft 365 automatisch die Größe des Archivs, was bedeutet, dass den Benutzern kein Speicherplatz mehr zur Verfügung steht und Administratoren keinen zusätzlichen Speicher für Archivpostfächer anfordern müssen.

Schrittweise Anweisungen zum Aktivieren der automatischen Erweiterung der Archivierung finden Sie unter [Enable unlimited archiving](enable-unlimited-archiving.md).

> [!NOTE]
> Die Archivierung mit automatischer Erweiterung unterstützt auch freigegebene Postfächer. Zum Aktivieren des Archivs für ein freigegebenes Postfach ist eine Exchange Online Plan 2-Lizenz oder eine Exchange Online Plan 1-Lizenz mit Exchange Online-Archivierung erforderlich.

## <a name="how-auto-expanding-archiving-works"></a>Funktionsweise der automatischen Erweiterung der Archivierung

Wie bereits erläutert, wird zusätzlicher Postfachspeicherplatz erstellt, wenn das Archivpostfach eines Benutzers aktiviert ist. Wenn die Archivierung automatisch erweitert wird, Microsoft 365 die Größe des Archivpostfachs regelmäßig überprüft. Wenn ein Archivpostfach seinen Speichergrenzwert erreicht, Microsoft 365 automatisch zusätzlichen Speicherplatz für das Archiv erstellt. Wenn dem Benutzer dieser zusätzliche Speicherplatz nicht mehr zur Verfügung Microsoft 365 zusätzlichen Speicherplatz zum Archiv des Benutzers hinzu. Dieser Vorgang erfolgt automatisch, d. h. Administratoren müssen keinen zusätzlichen Archivspeicher anfordern oder die automatisch erweiternde Archivierung verwalten.

Hier finden Sie eine kurze Übersicht über den Prozess.

![Übersicht über den Archivierungsprozess mit automatischer Erweiterung](../media/74355385-d990-44fe-8a87-6c3639d1f63f.png)

1. Die Archivierung ist für ein Benutzerpostfach oder ein freigegebenes Postfach aktiviert. Es wird ein Archivpostfach mit 100 GB Speicherplatz erstellt, und das Warnungskontingent für das Archivpostfach ist auf 90 GB festgelegt.

2. Ein Administrator ermöglicht die automatische Erweiterung der Archivierung für das Postfach. Wenn das Archivpostfach (einschließlich des Ordners "Wiederherstellbare Elemente") 90 GB erreicht, wird es in ein automatisch erweiternde Archiv konvertiert, und Microsoft 365 fügt dem Archiv Speicherplatz hinzu. Es kann bis zu 30 Tage dauern, bis der zusätzliche Speicherplatz bereitgestellt wird.

   > [!NOTE]
   > Wenn ein Postfach in der Aufbewahrungsaufbewahrung platziert oder einer Aufbewahrungsrichtlinie zugewiesen wird, wird das Speicherkontingent für das Archivpostfach auf 110 GB erhöht, wenn die archivierungsfähige automatische Erweiterung aktiviert ist. Auf ähnliche Weise wird das Kontingent für Archivwarnungen auf 100 GB erhöht.

3. Microsoft 365 wird bei Bedarf automatisch mehr Speicherplatz hinzugefügt.

> [!IMPORTANT]
> Das Archiv für automatisches Erweitern wird nur für Postfächer unterstützt, die für einzelne Benutzer (oder freigegebene Postfächer) mit einer Zuwachsrate von nicht mehr als 1 GB pro Tag verwendet werden. Das Archivpostfach eines Benutzers ist nur für diesen Benutzer vorgesehen. Das Verwenden von Journaling-, Transportregeln oder automatischen Weiterleitungsregeln zum Kopieren von Nachrichten in ein Archivpostfach ist nicht zulässig. Microsoft behält sich das Recht vor, die unbegrenzte Archivierung in Fällen zu verweigern, in denen das Archivpostfach eines Benutzers zum Speichern von Archivdaten für andere Benutzer oder in anderen Fällen der unangemessenen Verwendung verwendet wird.

## <a name="what-gets-moved-to-the-additional-archive-storage-space"></a>Was wird in den zusätzlichen Archivspeicher verschoben?

Um den automatisch erweiternden Archivspeicher effizient zu nutzen, werden Ordner möglicherweise verschoben. Microsoft 365 bestimmt, welche Ordner verschoben werden, wenn dem Archiv zusätzlicher Speicher hinzugefügt wird. Manchmal werden beim Verschieben eines Ordners automatisch ein oder mehrere Unterordner erstellt, und Elemente aus dem ursprünglichen Ordner werden an diese Ordner verteilt, um den Verschiebensprozess zu erleichtern. Beim Anzeigen des Archivteils der Ordnerliste in Outlook werden diese Unterordner unter dem ursprünglichen Ordner angezeigt.  Die Benennungskonvention, die Microsoft 365 zum Benennen dieser Unterordner verwendet, ist **\<folder name\> _yyyy (Created on mmm dd, yyyy h_mm)**, wobei:

- **yyyy** ist das Jahr, in dem die Nachrichten im Ordner empfangen wurden.

- **mmm dd, yyyy h_m** ist das Datum und die Uhrzeit, zu der der Unterordner von Office 365 im UTC-Format erstellt wurde, basierend auf der Zeitzone des Benutzers und den regionalen Einstellungen in Outlook.

Die folgenden Screenshots zeigen eine Ordnerliste vor und nach dem Verschieben von Nachrichten in ein automatisch erweitertes Archiv.

 **Bevor zusätzlicher Speicher hinzugefügt wird**

![Ordnerliste des Archivpostfachs vor der Bereitstellung des automatischen Erweiterns des Archivs](../media/5d6d6420-e562-4912-aaab-1c111762b3f6.png)

 **Nach dem Hinzufügen von zusätzlichem Speicher**

![Ordnerliste des Archivpostfachs nach der Bereitstellung des automatisch erweiterten Archivs](../media/c03c5f51-23fa-4fc2-b887-7e7e5cce30da.png)

> [!NOTE]
> Wie bereits beschrieben, verschiebt Microsoft 365 Elemente in Unterordner (und bezeichnet sie mithilfe der oben beschriebenen Benennungskonvention), um Inhalte an ein Hilfsarchiv zu verteilen. Das Verschieben von Elementen in Unterordner ist jedoch möglicherweise nicht immer der Fall. Manchmal kann ein ganzer Ordner in ein Hilfsarchiv verschoben werden. In diesem Fall behält der Ordner seinen ursprünglichen Namen bei.  Es wird nicht in der Ordnerliste in Outlook, dass der Ordner in ein Hilfsarchiv verschoben wurde.

## <a name="outlook-requirements-for-accessing-items-in-an-auto-expanded-archive"></a>Outlook Anforderungen für den Zugriff auf Elemente in einem automatisch erweiterten Archiv

Für den Zugriff auf Nachrichten, die in einem automatisch erweiterten Archiv gespeichert sind, müssen Benutzer einen der folgenden Outlook verwenden:

- Outlook 2016 oder Outlook 2019 für Windows

- Outlook im Web

- Outlook 2016 oder Outlook 2019 für Mac

Hier sind einige Dinge, die Sie bei der Verwendung von Outlook oder Outlook im Web berücksichtigen sollten, um auf Nachrichten zu zugreifen, die in einem automatisch erweiterten Archiv gespeichert sind.

- Sie können auf einen beliebigen Ordner in Ihrem Archivpostfach zugreifen, einschließlich der Ordner, die in den automatisch erweiterten Speicherbereich verschoben wurden.

- Die Suche nach automatisch erweiterter Archivierung ist in Outlook für das Web (OWA) verfügbar. Ähnlich wie beim Onlinearchiv können Sie nach Elementen suchen, die in einen zusätzlichen Speicherbereich verschoben wurden. Wenn Archiv als Suchbereich in OWA ausgewählt ist, werden alle Archive (einschließlich automatisch erweiterter Archive) und deren entsprechende Unterordner durchsucht.

- Die automatisch erweiterte Archivsuche ist in Outlook Desktop im aktuellen Kanal (Vorschau) verfügbar. In dieser Vorschau ist der Bereich Aktuelles Postfach verfügbar, sodass Sie das automatisch erweiterte Archiv durchsuchen können. Weitere Informationen zu diesem und anderen Microsoft Search-Supportfeatures finden Sie unter How [Outlook for Windows connected to Exchange Online Microsoft Search](https://techcommunity.microsoft.com/t5/outlook-global-customer-service/how-outlook-for-windows-connected-to-exchange-online-utilizes/ba-p/1715045). 

- Die Anzahl von Outlook und Lese-/Ungelesenen (in Outlook und Outlook im Web) in einem automatisch erweiterten Archiv ist möglicherweise nicht korrekt.

- Sie können Elemente in einem Unterordner löschen, der auf einen automatisch erweiterten Speicherbereich verweist, aber der Ordner selbst kann nicht gelöscht werden.

- Das Feature Gelöschte Elemente wiederherstellen kann nicht zum Wiederherstellen eines Elements verwendet werden, das aus einem automatisch erweiterten Speicherbereich gelöscht wurde.

## <a name="auto-expanding-archiving-and-other-compliance-features"></a>Automatisches Erweitern der Archivierung und anderer Compliancefeatures

In diesem Abschnitt wird die Funktionalität zwischen der automatischen Erweiterung der Archivierung und anderen Compliance- und Data Governance-Features erläutert.

- **eDiscovery:** Wenn Sie ein eDiscovery-Tool wie die Inhaltssuche oder In-Place eDiscovery verwenden, werden auch die zusätzlichen Speicherbereiche in einem automatisch erweiterten Archiv durchsucht.

- **Aufbewahrung:** Wenn Sie ein Postfach mithilfe von Tools wie z. B. dem Aufbewahrungsverfahren in Exchange Online oder eDiscovery-Fallarchiven und Aufbewahrungsrichtlinien im Security and Compliance Center archivieren, werden inhalte, die sich in einem automatisch erweiterten Archiv befinden, ebenfalls in einem Archiv aufbewahrt.

- **Verwaltung von Messagingdatensätzen (Messaging Records Management, MRM):** Wenn Sie MRM-Löschrichtlinien in Exchange Online, um abgelaufene Postfachelemente dauerhaft zu löschen, werden auch abgelaufene Elemente im automatisch erweiterten Archiv gelöscht.

- **Importdienst:** Sie können den Office 365 Importdienst verwenden, um PST-Dateien in das automatisch erweiterte Archiv eines Benutzers zu importieren. Sie können bis zu 100 GB Daten aus PST-Dateien in das Archivpostfach des Benutzers importieren.

## <a name="more-information"></a>Weitere Informationen

Weitere technische Details zur automatischen Erweiterung der Archivierung finden Sie [unter Microsoft 365: Auto-Expanding Archives FAQ](https://techcommunity.microsoft.com/t5/exchange-team-blog/office-365-auto-expanding-archives-faq/ba-p/607784).
