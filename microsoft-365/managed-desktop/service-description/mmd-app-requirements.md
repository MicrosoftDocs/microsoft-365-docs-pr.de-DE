---
title: Microsoft Managed Desktop-App-Anforderungen
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 01/08/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: de6cc7d77e023a9d41961e5fbcce060f1bb659ae
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32278335"
---
# <a name="microsoft-managed-desktop-app-requirements"></a>Microsoft Managed Desktop-App-Anforderungen

<!--This topic is the target for aka.ms/app-req. This is aka link is used from EA agreeement for MMD. do not delete.-->

<!--Application addendum -->
 
Branchenanwendungen, die Sie auf Microsoft Managed Desktop-Geräten bereitstellen möchten, müssen die Anforderungen in diesem Thema erfüllen. 

## <a name="application-condition"></a>Anwendungs Bedingung

Es ist wichtig, dass sich Anwendungen nicht negativ auf die Microsoft Managed Desktop-Umgebung auswirken. Es folgen die Anforderungen, die eine Anwendung erfüllen muss, damit Microsoft Sie bereitstellen kann. Für eine bestimmte Anwendung oder einen Treiber kann Microsoft auf die hier aufgeführten Anforderungen verzichten. Microsoft kann beschließen, alle Anwendungen oder Treiber zu entfernen, die sich negativ auf die Leistung und Zuverlässigkeit von Microsoft Managed Desktop-Geräten auswirken.

## <a name="deployable-using-microsoft-technologies"></a>Bereitstellen mithilfe von Microsoft-Technologien

Microsoft Managed Desktop verwendet InTune, Microsoft Store und Microsoft Store for Business, um Anwendungen bereitzustellen. Daher müssen Anwendungen so verpackt werden, dass Sie von der jeweils aktuellen Version dieser Dienste bereitgestellt werden können.

## <a name="prohibited-app-classes"></a>Verbotene App-Klassen

Bestimmte Anwendungstypen sind auf verwalteten Desktop Geräten von Microsoft nicht zulässig:
- Antiviren-, Sicherheits-oder Überwachungssoftware von Drittanbietern
- Drittanbieter-Webbrowser
- Versionen von Microsoft Office vor Office 365 pro Plus
- Anwendungen, die andere Drittanbietersoftware installieren oder bündeln

## <a name="restricted-app-behaviors"></a>Eingeschränktes App-Verhalten

Bestimmte Anwendungsverhaltens weisen können eine Beeinträchtigung der Benutzerfreundlichkeit oder ein Sicherheitsrisiko für verwaltete Desktop Geräte von Microsoft darstellen. Anwendungen dürfen nicht die folgenden Verhaltensweisen oder Merkmale aufweisen: 

Benutzererfahrung:
- Installieren von Hintergrunddiensten oder Laichen von lang andauernden Hintergrundprozessen
- Hinzufügen des Windows-Start Pfads

Sicherheit:
- Aufrufen von nicht dokumentierten Windows-oder Office-APIs oder Abhängigkeiten von internen Windows-oder Office-Datenstrukturen
- Fungieren als APP-Speicher oder haben integrierten Erweiterungs-Manager
- Erhöhen der Berechtigungen des Endbenutzers
- Bekannte Sicherheitsrisiken
- Signiert mit einem Zertifikat, das nicht für ein vertrauenswürdiges Stammverzeichnis verwendet wird
- VerSchlüsseln oder Einschränken des Zugriffs auf Endbenutzerdaten
- Ändern des Betriebssystemcodes zur Laufzeit

## <a name="driver-deployment"></a>Treiberbereitstellung

Wenn ein Treiber in Windows Update nicht verfügbar ist oder von Windows Hardware Quality Lab (WHQL) separat signiert wurde, muss Microsoft einen Treiber genehmigen, bevor Microsoft den Treiber für Microsoft Managed Desktop Devices bereitstellt.
