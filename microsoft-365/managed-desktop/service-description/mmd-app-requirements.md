---
title: Microsoft Managed Desktop-App-Anforderungen
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 01c580cd671a84ef68c18b114e133f046a3e5b3b
ms.sourcegitcommit: 7930fb8327bbd3594fde52f2dbf91e0f5d92f684
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2020
ms.locfileid: "42328067"
---
# <a name="microsoft-managed-desktop-app-requirements"></a>Microsoft Managed Desktop-App-Anforderungen

<!--This topic is the target for aka.ms/app-req. This is aka link is used from EA agreement for MMD. do not delete.-->

<!--Application addendum -->
 
Um die Leistung, Zuverlässigkeit und Servicefähigkeit von Microsoft Managed Desktop-Geräten zu gewährleisten, dürfen die Branchen-apps eines Kunden keine ernsthaften Auswirkungen auf die Endbenutzererfahrung haben oder die Sicherheitseinstellung ändern. Daher müssen Branchenanwendungen, die Sie auf Microsoft Managed Desktop-Geräten bereitstellen möchten, die Anforderungen in diesem Thema erfüllen.

## <a name="application-condition"></a>Anwendungs Bedingung

Es ist wichtig, dass sich Anwendungen nicht nachteilig auf die von Microsoft verwaltete Desktop Umgebung auswirken. Im folgenden sind die Anforderungen aufgeführt, die eine Anwendung erfüllen muss, damit eine Anwendung bereitgestellt werden kann. Für jede Anwendung oder jeden Treiber verzichtet Microsoft möglicherweise auf die hierin entgegenstehenden Anforderungen. Microsoft kann beschließen, jede Anwendung oder jeden Treiber zu entfernen, die sich negativ auf die Leistung und Zuverlässigkeit von von Microsoft verwalteten Desktop Geräten auswirkt.

## <a name="centrally-managed-apps"></a>Zentral verwaltete apps

Alle auf Microsoft Managed Devices installierten Anwendungen und Treiber müssen über Microsoft InTune, den Microsoft Store oder den Microsoft Store for Business bereitgestellt werden. Wenn verfügbar, werden Treiber auch über den Windows Update-Dienst bereitgestellt. 

## <a name="prohibited-app-classes"></a>Verbotene App-Klassen

Bestimmte Anwendungstypen sind auf Microsoft Managed Desktop-Geräten nicht zulässig:
- Virenschutz-, Sicherheits-oder Überwachungssoftware von Drittanbietern
- Versionen von Microsoft Office vor Office 365 ProPlus
- Anwendungen, die andere Drittanbietersoftware installieren oder bündeln

## <a name="restricted-app-behaviors"></a>Eingeschränktes App-Verhalten

Bestimmte App-Verhaltensweisen können sich negativ auf die Benutzerfreundlichkeit auswirken oder ein Sicherheitsrisiko für von Microsoft verwaltete Desktop Geräte darstellen. Apps mit den folgenden Verhaltensweisen dürfen nicht in der Microsoft Managed Desktop-Umgebung ohne einen bestimmten von Microsoft ausgeführt werden.

Benutzererfahrung:
- Installieren von Hintergrunddiensten
- Selbst zum Start Pfad von Windows hinzufügen
- Von Treibern abhängige Anwendungen
- Drittanbieter-Webbrowser

Sicherheit:
- Erhöhen der Benutzerberechtigungen
- Fungieren als App Store oder verfügen über einen integrierten Erweiterungs-Manager
- Bekannte Sicherheitsrisiken
- Verschlüsseln oder Einschränken des Zugriffs auf Endbenutzerdaten
- Ist nicht signiert oder wird mit einem Zertifikat signiert, das nicht auf einen vertrauenswürdigen Stamm aufrollen kann.


## <a name="driver-deployment"></a>Treiberbereitstellung

Microsoft Managed Desktop unterstützt nur Gerätetreiber, die über Windows Update oder einen installierten Posteingang mit dem von Microsoft verwalteten Gerät zur Verfügung stehen. 

Wenn eine Anwendung einen bestimmten Treiber benötigt, um Sie auszuführen, wird Sie als eingeschränkte Anwendung betrachtet und erfordert eine Ausnahme, bevor Sie in Microsoft Managed Desktop bereitgestellt wird. 

