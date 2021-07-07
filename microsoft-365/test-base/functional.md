---
title: Funktionstests auf der Testbasis
description: Details zum Testen Ihrer Anwendung mit Ihren vorhandenen automatisierten Funktionstests
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: how-to
ms.date: 07/06/2021
ms.service: virtual-desktop
localization_priority: Normal
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: 7b5cb907756ec0fb746d303b3ab629e912bf9c96
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322848"
---
# <a name="functional-testing"></a>Funktionstests

Als Softwareanbieter können Sie jetzt benutzerdefinierte Funktionstests mithilfe des Testframeworks Ihrer Wahl durchführen – über das Self-Serve Test Base für M365-Portal. 

Als wir den Dienst zum ersten Mal gestartet haben, haben wir die Out-of-Box-Tests angeboten, bei denen es sich um eine vordefinierte Gruppe von Tests handelt, die durch standardisierte Skripts gesteuert werden. Dies konnte jedoch für viele unabhängige Softwareanbieter (Independent Software Vendors, ISVs) keine vollständige Testabdeckung erzielen. 

Daher bieten wir als Reaktion auf Ihr Feedback unseren ISVs die Möglichkeit, automatisierte Funktionstests hochzuladen.

Führen Sie die folgenden Schritte aus, um dieses Feature zu verwenden:

1. Hochladen Sie Ihre Dateien (Binärdateien, Abhängigkeiten und Skripts) als einzelnes .zip-Paket.
2. Wählen Sie aus, ob Sie die virtuellen Testcomputer (VMs) an verschiedenen Ausführungspunkten neu starten möchten.
3. Verwalten sie die verfügbaren Optionen für Ihre Skripts.
4. Wählen Sie aus, wann das Windows Update während der Ausführung auf dem virtuellen Computer angewendet werden soll.

Detaillierte Beschreibungen der obigen Schritte sind unten hervorgehoben:

**Hochladen eines Funktionstestpakets**

To get started, navigate to the Hochladen page, select Hochladen new application under Application catalog on the left-side navigation menu of the Test Base for M365 portal in Azure. Von dort aus:

Registerkarte 1– Geben Sie grundlegende Informationen ein. Geben Sie den Namen und die Version Ihrer Anwendung an. Wählen Sie in der Testoption Typ die Option ```Functional tests``` aus. 

*Beachten Sie, dass die Out-of-Box (OOB)-Option standardmäßig erforderlich ist.*


![Wählen Sie die Registerkarte "Funktionale Tests" aus.](Media/functional_testing_tab1.png)

Registerkarte 2 – Hochladen die Komponenten Ihres Pakets, indem Sie eine ZIP-Datei mit Ihrem gesamten Test hochladen (Binärdateien, Abhängigkeiten, Skripts usw.). 

Weitere Informationen finden Sie unter aka.ms/usl-package-outline. (Hinweis: Sowohl die out-of-Box-Testskripts als auch die Funktionalen Testinhalte sollten in derselben ZIP-Datei platziert werden.) Derzeit ist die Dateigröße auf 2 GB beschränkt.

Registerkarte 3 – Konfigurieren sie die out-of-Box- und funktionalen Testaufgaben. Wählen Sie hier die Pfade zu den PowerShell-Skripts aus, die Ihre Anwendung (für Out-of-Box) installieren, starten, schließen und deinstallieren, sowie die Pfade zu allen benutzerdefinierten Skripts, um Ihren Funktionstest durchzuführen. **(Hinweis: Ein Skript zum Deinstallieren Der Anwendung ist optional).**

Derzeit können Sie zwischen 1 und 8 Skripts für Ihre Funktionstests hochladen. (Kommentieren Sie diesen Beitrag bitte, wenn Sie weitere Skripts benötigen!)

![Hochladen bis zu 8 Skripts mit Funktionstests](Media/functional_testing_tab3.png)

(Optional) Konfigurieren Sie einen Neustart nach der Installation. Einige Anwendungen erfordern einen Neustart nach der Installation. 

Wählen Sie ```Reboot After Execution``` auf der Registerkarte "Aufgaben" das spezifische Skript aus, wenn nach der Ausführung dieses Skripts ein Neustart durchgeführt werden soll.

Registerkarte 4 – Wählen Sie aus, wann das Windows Update installiert wird: Die Anwendung des Windows Updatepatches wird vor einem beliebigen Skript Ihrer Wahl ausgeführt. Es wird empfohlen, nach der Installation der Anwendung ein Windows Update zu installieren, um ihre anwendungsbezogenen Anwendungsszenarien imitieren zu können.

![Das Windows Update kann nach einem bestimmten Skript installiert werden.](Media/functional_testing_tab4.png)

Registerkarte 5 – Überprüfen und erstellen Sie das Paket. Nachdem Sie die oben aufgeführten Schritte ausgeführt haben, wählen Sie ```Create``` aus, um den Uploadvorgang abzuschließen.

Nachdem Das Paket erstellt wurde, können Sie den Überprüfungsstatus Ihres Pakets überprüfen.

Wir führen einen ersten Test aus, um Ihre Anwendung zu installieren, zu starten, zu schließen und zu deinstallieren. Dadurch können wir überprüfen, ob Ihr Paket fehlerfrei auf unserem Dienst installiert werden kann.

Der Überprüfungsprozess kann bis zu 24 Stunden dauern. Sobald die Überprüfung abgeschlossen ist, können Sie den Status im ```Manage packages``` Menü sehen. Dies wäre einer von zwei Einträgen:

1. Die Überprüfung ist erfolgreich: Das Paket wird automatisch mit Vorabversionen Windows Updates für die ausgewählten Betriebssystembuilds getestet.
oder
2. Überprüfung schlägt fehl: Sie müssen die Gründe für den Fehler untersuchen, das Problem beheben und Ihr Paket erneut hochladen.

Sie werden auch über das Benachrichtigungssymbol im Azure-Portal über beide Ergebnisse benachrichtigt.
