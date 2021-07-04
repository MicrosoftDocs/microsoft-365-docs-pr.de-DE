---
title: 'Identifizieren von Inhalten für Empfehlungen im Hinblick auf die Datengovernance '
f1.keywords:
- NOCSH
ms.author: brendonb
author: cabailey
manager: laurawi
ms.date: 1/15/2019
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
ms.collection:
- SPO_Content
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ROBOTS: NOINDEX, NOFOLLOW
description: Das Microsoft 365 Security und Microsoft 365 Compliance Center bieten Empfehlungen für Datengovernance basierend auf dem aktuellen Setup Ihrer Organisation; mit nur wenigen Klicks können Sie alles einrichten. Einige dieser Empfehlungen erkennen spezifische Inhalte in Ihrer Organisation und bieten dann empfohlene Schritte zum Verwalten dieser Inhalte an. Eine Empfehlung könnte beispielsweise Elemente mit unternehmenswichtigen Inhalten erkennen (z. B. Anwaltsgeheimnisse oder Geheimhaltungsvereinbarungen). Sie können dann automatisch eine Aufbewahrungsbezeichnung auf diese Elemente anwenden, um sicherzustellen, dass sie bei Bedarf mit einer Geheimhaltungsklassifizierung versehen und aufbewahrt werden. In diesem Thema sind die Datengovernance-Empfehlungen aufgeführt, die möglicherweise angezeigt werden, und es wird beschrieben, welche Inhalte erkannt werden, damit die einzelnen Empfehlungen ausgelöst werden.
ms.openlocfilehash: 42956e72bf377a02adde3e4253bd9221bb84ff3e
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288527"
---
# <a name="how-content-is-identified-for-data-governance-recommendations"></a>Identifizieren von Inhalten für Empfehlungen im Hinblick auf die Datengovernance 

Das Microsoft 365 Security und Microsoft 365 Compliance Center bieten Empfehlungen für Datengovernance basierend auf dem aktuellen Setup Ihrer Organisation; mit nur wenigen Klicks können Sie alles einrichten. Einige dieser Empfehlungen erkennen spezifische Inhalte in Ihrer Organisation und bieten dann empfohlene Schritte zum Verwalten dieser Inhalte an. Eine Empfehlung könnte beispielsweise Elemente mit unternehmenswichtigen Inhalten erkennen (z. B. Anwaltsgeheimnisse oder Geheimhaltungsvereinbarungen). Sie können dann automatisch eine Aufbewahrungsbezeichnung auf diese Elemente anwenden, um sicherzustellen, dass sie bei Bedarf mit einer Geheimhaltungsklassifzierung versehen und aufbewahrt werden.

In diesem Thema sind die Datengovernance-Empfehlungen aufgeführt, die möglicherweise angezeigt werden, und es wird beschrieben, welche Inhalte erkannt werden, damit die einzelnen Empfehlungen ausgelöst werden.

## <a name="clean-up-voicemail"></a>Voicemail bereinigen

Diese Empfehlung wird angezeigt, wenn E-Mail-Nachrichten, die mit dem Nachrichtentyp „Voicemail“ identifiziert wurden, in den Postfächern von Benutzern erkannt werden. Erfahren Sie mehr zu [Nachrichteneigenschaften in Exchange](/exchange/policy-and-compliance/ediscovery/message-properties-and-search-operators#searchable-properties-in-exchange).

## <a name="label-attorney-client-privilege-content"></a>Inhalte mit Anwaltsgeheimnissen kennzeichnen

Diese Empfehlung wird angezeigt wird, wenn eine der folgenden Bedingungen erfüllt ist.

- Eine beliebige Kombination der folgenden Schlüsselwörter wird im Textkörper einer E-Mail-Nachricht erkannt:
  - AG
  - Anwaltsgeheimnis
  - Anwalts-Geheimnis
  - Anwaltsgeheimnisse

- Eine beliebige Kombination der folgenden Schlüsselwörter wird in SharePoint- oder OneDrive-Dateien erkannt:
  - AG
  - Anwaltsgeheimnis*
  - Anwalts-Geheimnis

## <a name="retain-audio-files"></a>Audiodateien beibehalten

Diese Empfehlung wird angezeigt wird, wenn einer der folgenden Dateitypen in SharePoint oder OneDrive erkannt wird:

- .MP3
- .WMA
- .WAV
- .RA
- .RAM
- .RM
- .MID
- .OGG
- .AIFF
- .PCM
- .AAC
- .FLAC
- .ALAC

## <a name="retain-cad-files"></a>CAD-Dateien beibehalten

Diese Empfehlung wird angezeigt wird, wenn einer der folgenden Dateitypen in SharePoint oder OneDrive erkannt wird:

- .3DXML
- .ACIS
- .ARC
- .ASM
- .CAT*
- .CGR
- .DW*
- .DX*
- .EDRW
- .IAM
- .IGES
- .IGS
- .IPT
- .JT
- .MF1
- .NEU
- .PAR
- .PKG
- .PRC
- .PRT
- .PSM
- .PWD
- .SLD*
- .STEP
- .STL
- .STP
- .U3D
- .UNV
- .VRML
- .WRL
- .X_*
- .XAS
- .XMT*
- .XPR

## <a name="retain-image-files"></a>Bilddateien beibehalten

Diese Empfehlung wird angezeigt wird, wenn einer der folgenden Dateitypen in SharePoint oder OneDrive erkannt wird:

- .JPEG
- .GIF
- .TIF*
- .BMP
- .PNG
- .RAW
- .PSD
- .PSP
- .JPG
- .EXIF
- .PPM
- .PGM
- .PBM
- .PNM
- .WEBP

## <a name="retain-nda-content"></a>Retain NDA content

Diese Empfehlung wird angezeigt wird, wenn eine der folgenden Bedingungen erfüllt ist.

- Eine beliebige Kombination der folgenden Schlüsselwörter wird im Textkörper einer E-Mail-Nachricht erkannt:
  - NDA
  - „Geheimhaltungsvereinbarung“
  - „Geheimhaltungsvereinbarung“

- Eine beliebige Kombination der folgenden Schlüsselwörter wird in PDF- oder DOC-Dateien in SharePoint oder OneDrive erkannt:
  - NDA
  - Geheimhaltungsvereinbarung

## <a name="retain-software-development-files"></a>Softwaredateien beibehalten

Diese Empfehlung wird angezeigt wird, wenn einer der folgenden Dateitypen in SharePoint oder OneDrive erkannt wird:

- .ASAX
- .ASM
- .ASP*
- .BAT
- .CONFIG
- .CS
- .CSS
- .DISCO
- .HTM*
- .INC
- .JAD
- .JAVA
- .JS*
- .LIB
- .O
- .PHP
- .RC
- .RESX
- .RPT
- .RSS
- .SCPT
- .SRC
- .VB*
- .WSF
- .XCODEPROJ
- .XML
- .XSD
- .XSL*

## <a name="retain-video-files"></a>Videodateien beibehalten

Diese Empfehlung wird angezeigt wird, wenn einer der folgenden Dateitypen in SharePoint oder OneDrive erkannt wird:

- .AVCHD
- .AVI
- .FLV
- .MOV
- .MP2V
- .MP4
- .MP4V
- .MPE
- .MPEG
- .MPEG1
- .MPEG2
- .MPEG4
- .MPG
- .MPG2
- .MPG4
- .WMV
- .XMV
