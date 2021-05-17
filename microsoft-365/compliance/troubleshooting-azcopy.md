---
title: Behandeln von AzCopy in Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Behandeln von Fehlern für Azure AzCopy beim Laden nicht Office 365 Daten zur Fehlerbehebung in Advanced eDiscovery.
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: f34b47762601a3cc66b46fd8a2691c0fb87d3354
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919291"
---
# <a name="troubleshoot-azcopy-in-advanced-ediscovery"></a>Behandeln von AzCopy in Advanced eDiscovery

Beim Laden von Nicht-Microsoft 365-Daten oder Dokumenten zur Fehlerbehebung in Advanced eDiscovery stellt die Benutzeroberfläche einen Azure AzCopy-Befehl bereit, der Parameter mit dem Speicherort der Dateien, die Sie hochladen möchten, und dem Azure-Speicherort enthält, in den die Dateien hochgeladen werden. Um Ihre Dokumente hochzuladen, kopieren Sie diesen Befehl und führen ihn dann in einer Eingabeaufforderung auf Dem lokalen Computer aus.  Der folgende Screenshot zeigt ein Beispiel für einen AzCopy-Befehl:

![Hochladen nicht Microsoft 365 Dateien](../media/46ba68f6-af11-4e70-bb91-5fc7973516e3.png)

Normalerweise funktioniert der bereitgestellte Befehl, wenn Sie ihn ausführen. Es kann jedoch Fälle gibt, in denen der angezeigte Befehl nicht erfolgreich ausgeführt wird. Hier sind einige mögliche Gründe.

## <a name="the-supported-version-of-azcopy-isnt-installed-on-the-local-computer"></a>Die unterstützte Version von AzCopy wird nicht auf dem lokalen Computer installiert.

Zu diesem Zeitpunkt müssen Sie AzCopy v8.1 verwenden, um Nicht-Microsoft 365-Daten in Advanced eDiscovery. Der Befehl AzCopy, der auf der Seite **Hochladen** Dateien angezeigt wird, der im vorherigen Screenshot angezeigt wird, gibt einen Fehler zurück, wenn Sie AzCopy v8.1 nicht verwenden. Informationen zur Installation dieser Version finden Sie unter Übertragen von Daten [mit azCopy v8.1 auf Windows](/previous-versions/azure/storage/storage-use-azcopy).

## <a name="azcopy-isnt-installed-on-the-local-computer-or-its-not-installed-in-the-default-location"></a>AzCopy ist nicht auf dem lokalen Computer oder nicht am Standardspeicherort installiert

Wenn AzCopy nicht installiert oder an einem anderen Speicherort als dem Standardinstallationsspeicherort (d. h. ) installiert ist, wird möglicherweise der folgende Fehler angezeigt, wenn Sie den `%ProgramFiles(x86)%` Befehl AzCopy ausführen:

> Das System kann den angegebenen Pfad nicht finden.

Wenn AzCopy nicht auf dem lokalen Computer installiert ist, finden Sie Installationsinformationen unter Übertragen von Daten mit [azCopy v8.1 auf Windows](/previous-versions/azure/storage/storage-use-azcopy). Stellen Sie sicher, dass sie am Standardspeicherort installiert wird.

Wenn AzCopy installiert ist, aber an einem anderen Speicherort als dem Standardspeicherort installiert ist, können Sie den Befehl kopieren, in eine Textdatei einfügen und dann den Pfad zum Speicherort ändern, an dem AzCopy installiert ist. Wenn sich Azcopy beispielsweise in befindet, können Sie den ersten Teil des Befehls in `%ProgramFiles%` `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy.exe` `%ProgramFiles%\Microsoft SDKs\Azure\AzCopy` ändern. Nachdem Sie diese Änderung geändert haben, kopieren Sie sie aus der Textdatei, und führen Sie sie dann als Eingabeaufforderung aus.

> [!TIP]
> Wenn AzCopy an einem anderen Speicherort als dem Standardinstallationsspeicherort installiert ist, sollten Sie es deinstallieren und dann erneut am Standardspeicherort installieren. Dies wird dazu beitragen, dieses Problem in Zukunft zu verhindern.