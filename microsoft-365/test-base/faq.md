---
title: Häufig gestellte Fragen zur Testbasis
description: Häufig gestellte Fragen überprüfen
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: troubleshooting
ms.date: 07/06/2021
ms.service: virtual-desktop
localization_priority: Normal
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: 9d24ecb807e60733471be60353d12789f19be1b4
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322926"
---
# <a name="test-base-faq"></a>Häufig gestellte Fragen zur Testbasis

**F: Wie übermitteln wir unsere Pakete an das Testbasisteam?**

**A:** Übermitteln Sie Ihre Pakete direkt an die Testbasisumgebung über unser Self-Serve-Portal.

Um Ihr Anwendungspaket zu übermitteln, navigieren Sie zum [Azure-Portal,](https://www.aka.ms/testbaseportal "Homepage der Testbasis") und laden Sie einen gezippten Ordner mit den Binärdateien, Abhängigkeiten und Testskripts Ihrer Anwendung über das Dashboard des Self-Serve-Testbasisportals hoch. 

Weitere Informationen finden Sie im Onboarding-Benutzerhandbuch, oder wenden Sie sich an unser Team, um Unterstützung und weitere Informationen zu <testbasepreview@microsoft.com> erhalten.

**F: Was sind Out-of-Box (OOB)-Tests?**

**A:** Out-of-Box (OOB)-Tests sind standardisiert, Standardtestläufe, bei denen Anwendungspakete installiert, gestartet und 30 Mal geschlossen und dann deinstalliert werden. 

Die für Test Base erstellten Pakete verfügen über die folgenden Testskripts: Installieren, Starten, Schließen und optional das Deinstallationsskript. 

Die Out-of-Box (OOB)-Tests bieten Ihnen standardisierte Telemetriedaten für Ihre Anwendung, die sie in Windows Builds vergleichen können.

**F: Können tests außerhalb der Out-of-Box-Tests (Installieren, Starten, Schließen, Deinstallieren von Testskripts) eingereicht werden?**

**A:** Ja, Kunden können Anwendungspakete für **Funktionstests** auch über das Dashboard des Self-Serve-Portals hochladen.
**Funktionstests** sind Tests, mit denen Kunden ihre Skripts ausführen können, um benutzerdefinierte Funktionen für ihre Anwendung auszuführen.


## <a name="testing"></a>Testen

**F: Unterstützen Sie Funktionstests?**

**A:** Ja, Test Base unterstützt Funktionstests. Funktionstests sind Tests, die es unseren Kunden ermöglichen, ihre Skripts auszuführen, um benutzerdefinierte Funktionen für ihre Anwendung auszuführen. 

Um Ihr Anwendungspaket für Funktionstests zu übermitteln, laden Sie einfach den gezippten Ordner mit den Binärdateien, Abhängigkeiten und Testskripts Ihrer Anwendung über unser Self-Serve-Portaldashboard hoch. 

Weitere Informationen finden Sie im Onboarding-Benutzerhandbuch, oder wenden Sie sich an unser Team, um Unterstützung und weitere Informationen zu <testbasepreview@microsoft.com> erhalten.

**F: Wie behandelt test Base unsere Testdaten?**

**A:** Test Base sammelt und verwaltet Ihre Testdaten sicher in der Azure-Umgebung. 

**F: Kann die Testbasis unsere automatisierten Tests unterstützen?**

Ja, Test Base unterstützt automatisierte Tests, aber aufgrund von Dienstfunktionen unterstützen wir derzeit keine manuellen Tests.

**F: Welche Sprachen und Frameworks automatisierter Tests werden unterstützt?**

**A:** Wir unterstützen alle Sprachen und Frameworks. Wir rufen alle Skripts über PowerShell auf. 

Sie müssen auch die abhängigen Binärdateien des erforderlichen Frameworks bereitstellen (hochladen).

**F: Wie bald liefert Testbasis Testergebnisse?**

**A:** Für jeden Test, den wir für die Vorabversionen ausführen, stellen wir innerhalb von 48 Stunden Ergebnisse auf Ihrem [Azure Portal-Dashboard](https://www.aka.ms/testbaseportal "Homepage der Testbasis") bereit.

**F: Können Sie nach der Installation neu starten?**

**A:** Ja, unser Prozess unterstützt den Neustart nach der Installation. Achten Sie darauf, diese Option in der Dropdownliste "Optionale Einstellungen" auszuwählen, wenn Sie Ihre **Aufgaben** im Onboardingportal festlegen.

Für Out-of-Box (OOB)-Tests können Sie angeben, ob für das Installationsskript ein Neustart erforderlich _ist._

![Bild "Neustart"](Media/reboot.png)

Bei Funktionstests können Sie angeben, ob für jedes hinzugefügte Skript ein Neustart erforderlich ist.

![Auswählen von Funktionstests](Media/functionalreboot.png)

**F: Welche Windows Versionen unterstützen Sie?**

**A:** Derzeit unterstützen wir Windows 10 Clients, Windows Server 2016, Windows Server 2016 Core-Version, Windows Server 2019 und Windows Server 2019 Core-Version.

**F: Was ist der Unterschied zwischen Sicherheitsupdatetests und Funktionsupdatetests?**

**A:** Bei Sicherheitsupdatetests testen wir die **<ins>monatlichen Pre-Release-Sicherheitsupdates</ins>** auf Windows, die darauf ausgerichtet sind, unsere Benutzer immer sicher und geschützt zu halten. Für die Featureupdatetests testen wir die **<ins>zweijährlichen Vorabversionsfeatureupdates,</ins>** mit denen neue Features und Funktionen für Windows eingeführt werden.

## <a name="debugging-options"></a>Debugoptionen

**F: Erhalten wir Zugriff auf die virtuellen Computer (VMs) bei Fehlern? Was teilt testbasis?**

**A:** Damit der Dienst kompatibel ist und die Vorabversionsupdates sicher sind, hat nur Microsoft Zugriff auf die virtuellen Computer. Kunden können jedoch Testergebnisse und andere Testmetriken auf ihrem Portal-Dashboard anzeigen, einschließlich Crash- und Hang-Signalen, Zuverlässigkeitsmetriken, Arbeitsspeicher- und CPU-Auslastung usw. Außerdem generieren und stellen wir Protokolle von Testläufen auf dem Dashboard zum Herunterladen und zur weiteren Analyse bereit. 

Wir können bei Bedarf auch Speicherabbilder für das Absturzdebugging bereitstellen.

**F: Was sind die nächsten Schritte, um diese Probleme zu beheben, wenn während der Tests Probleme gefunden werden?**

**A:** Das Testbasisteam führt einen anfänglichen Selektierungsprozess durch, um die Ursache des Fehlers zu ermitteln. Je nach unseren Ergebnissen werden wir dann zum Debuggen an den Kunden oder interne Teams in Microsoft weitergeleitet. 

Wir arbeiten bei der gemeinsamen Behebung von Problemen immer eng mit unseren Kunden zusammen. 

**F: Hält Microsoft die Veröffentlichung des Sicherheitspatches bereit, bis das Problem behoben ist? Welche alternativen Auflösungen sind verfügbar?**

**A:** Das Ziel von Test Base besteht darin, sicherzustellen, dass unsere gemeinsamen Endbenutzer keine Probleme haben. Wir werden hart mit Softwareanbietern zusammenarbeiten, um Probleme vor der Veröffentlichung zu beheben, aber für den Fall, dass die Korrektur nicht machbar ist, haben wir andere Lösungen wie Shims und Blöcke.

## <a name="miscellaneous"></a>Sonstiges

**F: Wie funktioniert der Dienst mit einem lokalen Server?**

**A:** Wir bieten derzeit keine Unterstützung für lokale Server. Wenn der Server jedoch den HTTP-Endpunkt verfügbar macht, können wir eine Verbindung über das Internet herstellen.

**F: Wer hostet die virtuellen Computer?**

**A:** Microsoft stellt den virtuellen Computer für diesen Dienst bereit und übernimmt dabei die Last des Kunden.

**F: Unterstützt dieser Dienst Web-, Mobil- oder Desktopanwendungen?**

**A:** Derzeit liegt unser Fokus auf Desktopanwendungen, wir haben jedoch pläne, Webanwendungen in der Zukunft zu integrieren, aber wir unterstützen derzeit keine mobilen Anwendungen.

**F: Was ist der Unterschied zwischen Test Base und INTUNEP?**

**A:** Der größte Unterschied zwischen Test Base und WILLP besteht darin, dass unsere Partner ihre Anwendungen in die Testbasis-Azure-Umgebung integrieren, um die Überprüfung anhand von Vorabversionsupdates durchzuführen, anstatt die Tests selbst durchzuführen. 

Zusätzlich zum Testen von Sicherheitsupdates vor der Veröffentlichung unterstützen wir Tests von Vorabversionsfeatureupdates auf unserer Plattform. Wir haben viele andere Arten von Updates und Betriebssystemtests auf unserer Roadmap.

**F: Gibt es Kosten, die mit dem Dienst verbunden sind?**

**A:** Der Testbasisdienst steht Benutzern bis zur allgemeinen Verfügbarkeit (Ga) kostenlos zur Verfügung. Zu diesem Zeitpunkt werden wir eine Kostenstruktur ankündigen, die für alle Kunden wirksam wird. 

**F: Wie kann ich Feedback zur Testbasis geben?**

**A:** Um Ihr Feedback zur Testbasis zu teilen, wählen Sie das **Feedbacksymbol** unten links im Portal aus. Fügen Sie einen Screenshot in Ihre Übermittlung ein, damit Microsoft Ihr Feedback besser verstehen kann. 

Sie können auch Produktvorschläge übermitteln und andere Ideen auf der Website <testbasepreview@microsoft.com> aufrufen.
