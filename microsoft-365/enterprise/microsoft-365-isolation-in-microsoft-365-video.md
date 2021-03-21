---
title: Mandantenisolation in Office 365 Video
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: In diesem Artikel finden Sie eine Erläuterung, wie die Mandantenisolation die gespeicherten Videos jedes Mandanten in Office 365 Video getrennt hält.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fc67b17aa40b3bca9ce6d73ebb7e18319e780339
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918930"
---
# <a name="tenant-isolation-in-office-365-video"></a>Mandantenisolation in Office 365 Video

> [!NOTE]
> Office 365 Video wird durch Microsoft Stream ersetzt. Weitere Informationen zum neuen Unternehmensvideodienst, der der Videozusammenarbeit Informationen hinzufügt, und Informationen zu den Übergangsplänen für aktuelle Microsoft 365 Video-Kunden finden Sie unter Übersicht über den Übergang von [Office 365 Video](/stream/migrate-from-office-365)zu Microsoft Stream .

## <a name="introduction"></a>Einführung

Azure Storage wird zum Speichern von Daten für mehrere Office 365-Dienste verwendet, einschließlich Office 365 Video und Sway. Azure Storage umfasst Blobspeicher, einen hochgradig skalierbaren, REST-basierten Cloudobjektspeicher, der zum Speichern unstrukturierter Daten verwendet wird. Azure Storage verwendet ein einfaches Zugriffssteuerungsmodell. Jedes Azure-Abonnement kann ein oder mehrere Speicherkonten erstellen. Jedes Speicherkonto verfügt über einen einzelnen geheimen Schlüssel, der zum Steuern des Zugriffs auf alle Daten in diesem Speicherkonto verwendet wird. Dies unterstützt das typische Szenario, in dem Speicher Anwendungen zugeordnet ist und diese Anwendungen voll über die zugehörigen Daten verfügen. Z. B. Sway zum Speichern von Inhalten in Azure Storage. Alle Kundeninhalte für Sway werden in freigegebenen Azure-Speicherkonten gespeichert. Die Inhalte der einzelnen Benutzer befinden sich in einer separaten Verzeichnisstruktur von Blobs im Azure-Speicher.

Die Systeme, die den Zugriff auf Kundenumgebungen verwalten (z. B. das Azure-Portal, SMAPI usw.), sind in einer von Microsoft betriebenen Azure-Anwendung isoliert. Dadurch wird die Infrastruktur für den Kundenzugriff logisch von den Kundenanwendungen und der Speicherebene getrennt.

## <a name="tenant-isolation-in-office-365-video"></a>Mandantenisolation in Office 365 Video

[Office 365 Video](https://support.office.com/article/Meet-Office-365-Video-ca1cc1a9-a615-46e1-b6a3-40dbd99939a6) ist ein Unternehmensportal, das Organisationen ein äußerst sicheres, organisationsweites Ziel für das Veröffentlichen, Freigeben und Entdecken von Videoinhalten bietet. In Office 365 Video werden die Videos jedes Mandanten isoliert und verschlüsselt an allen Speicherorten aufbewahrt und stehen nur authentifizierten Benutzern zur Verfügung, die Über Zugriff und Berechtigungen für die Videos der Organisation haben. Office 365 Video verwendet dazu eine Kombination von Technologien:

- SharePoint Online wird zum Speichern der Videodatei und metadaten (Videotitel, Beschreibung usw.) verwendet. Außerdem bietet es die Sicherheits- und Complianceebene (einschließlich Authentifizierung) und Suchfeatures.
- Azure Media Services bietet Transcoding, adaptives Streaming, sichere Zustellung (mithilfe der AES-Verschlüsselung) und Miniaturansichtsfunktionen.

[Azure Media Services ist](https://azure.microsoft.com/services/media-services/) ein Plattform-as-a-Service-Angebot zum Aktivieren von End-to-End-Medienworkflows in der Cloud. Die Plattform bietet eine REST-API zum Hochladen, Codieren, Verschlüsseln (mit PlayReady) und zum Bereitstellen von Medien über Azure-Rechenzentren auf der ganzen Welt.

Alle Uploads für Office 365 Video erfolgen über HTTPS. Wenn eine Videodatei hochgeladen wird, wird sie in SharePoint Online gespeichert, und eine Kopie der Datei wird über einen verschlüsselten Kanal an Azure Media Services gesendet. Azure Media Services transcodierung das Video in mehrere Formate, die für die Anzeige optimiert sind (z. B. mobile, niedrige Bandbreite, hohe Bandbreite usw.). Diese Dateien werden zusammen mit der originalen Datei, die beim Hochladen erworben wurde, im Azure Blob-Speicher gespeichert. Die Dateien werden mithilfe von AES 128 pro MPEG Common Encryption-Packalgorithmus (oder einer früheren PlayReady-Version) für die Wiedergabe verschlüsselt und mit AES 256-Speicherverschlüsselung verschlüsselt, bevor sie im Azure Blob Storage gespeichert werden. (Mithilfe des Azure Media Services Client SDK können Kunden steuern, welche Verschlüsselung verwendet wird. Beispielsweise könnte ein Kunde die Azure Media Services-Speicherverschlüsselung (AES 256) auf ein hochwertiges Medieninventar anwenden, bevor es azure blob storage hochgeladen wird.)

Azure Media Services generiert auch eine Miniaturansicht für das Video, die zusammen mit Miniaturansichtmetadaten über einen verschlüsselten Kanal an SharePoint Online übermittelt wird.