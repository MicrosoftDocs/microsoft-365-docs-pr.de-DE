---
title: Microsoft Managed Desktop-App-Anforderungen
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 01/08/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 07e4719d87cb11910a90665ce9beb95edf6641a4
ms.sourcegitcommit: e15cf5d0d8ff3dfdc457b469992d72ac802e6434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/29/2019
ms.locfileid: "33467743"
---
# <a name="microsoft-managed-desktop-app-requirements"></a>Microsoft Managed Desktop-App-Anforderungen

<!--This topic is the target for aka.ms/app-req. This is aka link is used from EA agreeement for MMD. do not delete.-->

<!--Application addendum -->
 
Um die Leistung, Zuverlässigkeit und Wartbarkeit von Microsoft Managed Desktop-Geräten zu gewährleisten, dürfen die Branchen-apps eines Kunden keine gravierenden Auswirkungen auf die Endbenutzererfahrung haben oder die Sicherheitseinstellung ändern. Daher müssen Branchenanwendungen, die Sie auf Microsoft Managed Desktop-Geräten bereitstellen möchten, die Anforderungen in diesem Thema erfüllen.

## <a name="application-condition"></a>Anwendungs Bedingung

Es ist wichtig, dass sich Anwendungen nicht negativ auf die Microsoft Managed Desktop-Umgebung auswirken. Die folgenden Anforderungen müssen erfüllt sein, damit eine Anwendung bereitgestellt werden kann. Für eine bestimmte Anwendung oder einen Treiber kann Microsoft auf die hier aufgeführten Anforderungen verzichten. Microsoft kann beschließen, alle Anwendungen oder Treiber zu entfernen, die sich negativ auf die Leistung und Zuverlässigkeit von Microsoft Managed Desktop-Geräten auswirken.

## <a name="centrally-managed-apps"></a>Zentral verwaltete apps

Alle Anwendungen und Treiber, die auf verwalteten Microsoft-Geräten installiert sind, müssen über InTune, den Microsoft Store oder den Microsoft Store for Business bereitgestellt werden. Falls verfügbar, werden auch Treiber über den Windows Update-Dienst bereitgestellt. 

## <a name="prohibited-app-classes"></a>Verbotene App-Klassen

Bestimmte Anwendungstypen sind auf verwalteten Desktop Geräten von Microsoft nicht zulässig:
- Antiviren-, Sicherheits-oder Überwachungssoftware von Drittanbietern
- Versionen von Microsoft Office vor Office 365 pro Plus
- Anwendungen, die andere Drittanbietersoftware installieren oder bündeln

## <a name="restricted-app-behaviors"></a>Eingeschränktes App-Verhalten

Bestimmte App-Verhaltensweisen können sich negativ auf die Benutzererfahrung auswirken oder können ein Sicherheitsrisiko für verwaltete Desktop Geräte von Microsoft darstellen. Apps mit den folgenden Verhaltensweisen sind nicht zulässig, in der Microsoft Managed Desktop-Umgebung ohne eine bestimmte Ausnahme von Microsoft ausgeführt werden.

Benutzererfahrung:
- Installieren von Hintergrunddiensten
- Hinzufügen des Windows-Start Pfads
- Von Treibern abhängige Anwendungen
- Drittanbieter-Webbrowser

Sicherheit:
- Erhöhen der Berechtigungen des Endbenutzers
- Fungieren als APP-Speicher oder verfügen über einen integrierten Erweiterungs-Manager
- Bekannte Sicherheitsrisiken
- VerSchlüsseln oder Einschränken des Zugriffs auf Endbenutzerdaten
- Ist nicht signiert oder wird mit einem Zertifikat signiert, das nicht für ein vertrauenswürdiges Stammverzeichnis verwendet wird


## <a name="driver-deployment"></a>Treiberbereitstellung

Microsoft Managed Desktop unterstützt nur Gerätetreiber, die über Windows Update oder den installierten Posteingang mit dem verwalteten Microsoft-Gerät zur Verfügung stehen. 

Wenn eine Anwendung einen bestimmten Treiber benötigt, um Sie auszuführen, wird Sie als eingeschränkte Anwendung angesehen, und es ist eine Ausnahmegenehmigung für Microsoft Managed Desktop erforderlich. 

