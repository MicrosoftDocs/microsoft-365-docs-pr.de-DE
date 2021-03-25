---
title: Unterstützte Microsoft Defender Advanced Threat Protection-Antwort-APIs
description: Erfahren Sie mehr über die spezifischen reaktionsbezogenen Microsoft Defender Advanced Threat Protection-API-Aufrufe.
keywords: Antwort-APIs, Graph-API, unterstützte APIs, Akteur, Warnungen, Gerät, Benutzer, Domäne, IP, Datei
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
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
ms.openlocfilehash: a290c431f6d81b23896ddf77e7c7a47de378de22
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185551"
---
# <a name="supported-microsoft-defender-for-endpoint-query-apis"></a>Unterstützte Microsoft Defender for Endpoint-Abfrage-APIs 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> [!TIP]
> Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-supported-response-apis-abovefoldlink) 

Erfahren Sie mehr über die unterstützten reaktionsbezogenen API-Aufrufe, die Sie ausführen können, sowie Details wie die erforderlichen Anforderungsheader und die erwartete Antwort von den Aufrufen.

## <a name="in-this-section"></a>Inhalt dieses Abschnitts
Thema | Beschreibung
:---|:---
Untersuchungspaket sammeln | Führen Sie diese API aus, um ein Untersuchungspaket von einem Gerät zu erfassen.
Isolieren des Geräts | Führen Sie diese API aus, um ein Gerät vom Netzwerk zu isolieren.
Unisolates Gerät | Entfernen eines Geräts aus der Isolation. 
Einschränken der Codeausführung | Führen Sie diese API aus, um einen Angriff zu enthalten, indem Sie bösartige Prozesse beenden. Sie können auch ein Gerät sperren und verhindern, dass nachfolgende Versuche potenziell schädlicher Programme ausgeführt werden.
Unrestrict code execution | Führen Sie dies aus, um die Einschränkung der Anwendungsrichtlinie rückgängig zu machen, nachdem Sie überprüft haben, ob das gefährdete Gerät behoben wurde.
Ausführen der Antivirenscans | Remoteinitiieren sie eine Antivirenscan, um Schadsoftware zu identifizieren und zu beheben, die möglicherweise auf einem gefährdeten Gerät vorhanden ist.
Datei zum Beenden und Isolieren |  Führen Sie diesen Aufruf aus, um die Ausführung von Prozessen, Quarantänedateien und das Löschen von Persistenz wie Registrierungsschlüsseln zu beenden.
Anforderungsbeispiel | Führen Sie diesen Aufruf aus, um ein Beispiel einer Datei von einem bestimmten Gerät an zu fordern. Die Datei wird vom Gerät gesammelt und in einen sicheren Speicher hochgeladen.
Datei blockieren | Führen Sie diese API aus, um eine weitere Verbreitung eines Angriffs in Ihrer Organisation zu verhindern, indem Sie potenziell schädliche Dateien oder mutmaßliche Schadsoftware verbieten. 
Aufheben der Blockierung der Datei | Zulassen der Ausführung einer Datei in der Organisation mithilfe von Microsoft Defender Antivirus.
Paket-SAS-URI | Führen Sie diese API aus, um einen URI zu erhalten, der das Herunterladen eines Untersuchungspakets ermöglicht.
MachineAction-Objekt erhalten | Führen Sie diese API aus, um das MachineAction-Objekt zu erhalten.
MachineActions-Auflistung erhalten | Führen Sie dies aus, um die MachineAction-Auflistung zu erhalten.
FileActions-Auflistung herunterladen | Führen Sie diese API aus, um die FileActions-Auflistung zu erhalten.
FileMachineAction-Objekt herunterladen | Führen Sie diese API aus, um das FileMachineAction-Objekt zu erhalten.
FileMachineActions-Auflistung herunterladen | Führen Sie diese API aus, um die FileMachineAction-Auflistung zu erhalten.
