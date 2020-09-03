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
description: In diesem Artikel finden Sie eine Erläuterung, wie die Mandanten Isolierung die gespeicherten Videos jedes Mandanten in Office 365 Video getrennt hält.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 626a995fc5a3ac971c48cc87bec1017134e87b88
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332244"
---
# <a name="tenant-isolation-in-office-365-video"></a>Mandantenisolation in Office 365 Video

> [!NOTE]
> Office 365 Video wird durch Microsoft Stream ersetzt. Weitere Informationen zum neuen Enterprise-Videodienst, der Informationen zur Video Zusammenarbeit hinzufügt und Informationen zu den Übergangsplänen für aktuelle Microsoft 365-Video Kunden enthält, finden Sie unter [Office 365 Video Transition to Microsoft Stream Overview](https://docs.microsoft.com/stream/migrate-from-office-365).

## <a name="introduction"></a>Einführung

Azure Storage dient zum Speichern von Daten für mehrere Office 365 Dienste, einschließlich Office 365 Video und Sway. Azure Storage umfasst BLOB-Speicher, ein hoch skalierbarer, Rest-basierter Cloud-Objektspeicher, der zum Speichern unstrukturierter Daten verwendet wird. Azure Storage verwendet ein einfaches Zugriffssteuerungsmodell; jedes Azure-Abonnement kann mindestens ein Speicherkonto erstellen. Jedes Speicherkonto verfügt über einen einzelnen geheimen Schlüssel, der verwendet wird, um den Zugriff auf alle Daten in diesem Speicherkonto zu steuern. Dies unterstützt das typische Szenario, in dem Speicher mit Anwendungen verknüpft ist und diese Anwendungen Vollzugriff auf die zugeordneten Daten haben. beispielsweise Sway Speicherung von Inhalten im Azure-Speicher. Alle Kunden Inhalte für Sway werden in freigegebenen Azure-Speicherkonten gespeichert. Die Inhalte jedes Benutzers befinden sich in einer separaten Verzeichnisstruktur von BLOBs im Azure-Speicher.

Die Systeme, die den Zugriff auf Kundenumgebungen (beispielsweise das Azure-Portal, smapi usw.) verwalten, sind in einer Azure-Anwendung isoliert, die von Microsoft betrieben wird. Dadurch wird die Kundenzugriffs Infrastruktur logisch von den Kundenanwendungen und der Speicherschicht getrennt.

## <a name="tenant-isolation-in-office-365-video"></a>Mandantenisolation in Office 365 Video

[Office 365 Video](https://support.office.com/article/Meet-Office-365-Video-ca1cc1a9-a615-46e1-b6a3-40dbd99939a6) ist ein Unternehmensportal, das Organisationen mit einem hochgradig sicheren, organisationsweiten Ziel für das veröffentlichen, freigeben und ermitteln von Videoinhalten bereitstellt. In Office 365 Video werden die Videos jedes Mandanten isoliert und an allen Speicherorten verschlüsselt und stehen nur authentifizierten Benutzern zur Verfügung, die Zugriff und Berechtigungen für die Videos der Organisation besitzen. Office 365 Video verwendet eine Kombination aus Technologien, um dies zu erreichen:

- SharePoint Online wird zum Speichern der Videodatei und der Metadaten (Videotitel, Beschreibung usw.) verwendet. Außerdem werden die Sicherheits-und Kompatibilitätsebene (einschließlich Authentifizierung) und Suchfeatures bereitgestellt.
- Azure Media Services bietet Transcoding, adaptives Streaming, sichere Zustellung (mithilfe der AES-Verschlüsselung) und Miniaturansicht-Features.

[Azure Media Services](https://azure.microsoft.com/services/media-services/) ist ein Plattform-as-a-Service-Angebot für die Aktivierung von End-to-End-Medien Workflows in der Cloud. Die Plattform bietet eine Rest-API für das Hochladen, codieren, verschlüsseln (mit PlayReady) und die Bereitstellung von Medien über Azure-Rechenzentren auf der ganzen Welt.

Alle Uploads für Office 365 Video erfolgen über HTTPS. Wenn eine Videodatei hochgeladen wird, wird Sie in SharePoint Online gespeichert, und eine Kopie der Datei wird über einen verschlüsselten Kanal an Azure Media Services gesendet. Azure Media Services transcodiert das Video in mehrere Formate, die für die Anzeige der Benutzeroberfläche optimiert sind (beispielsweise Mobile, niedrige Bandbreite, hohe Bandbreite usw.). Diese Dateien werden zusammen mit der beim Hochladen erworbenen Originaldatei im Azure-BLOB-Speicher gespeichert. Die Dateien werden mithilfe von AES 128 pro dem MPEG Common Encryption Packaging-Algorithmus (oder einer früheren PlayReady-Version) für die Wiedergabe verschlüsselt und mithilfe der AES 256-Speicherverschlüsselung verschlüsselt, bevor Sie im Azure-BLOB-Speicher gespeichert werden. (Mithilfe des Azure Media Services-Client-SDK können Kunden steuern, welche Verschlüsselung verwendet wird. Beispielsweise könnte ein Kunde die Azure Media Services-Speicherverschlüsselung (AES 256) auf ein hochwertiges Medienobjekt vor dem Hochladen des Azure-BLOB-Speichers anwenden.)

Azure Media Services generiert auch eine Miniaturansicht für das Video, die über einen verschlüsselten Kanal zusammen mit Thumbnail-Metadaten übertragen wird, um SharePoint Online.
