---
title: Microsoft verwalteter Desktop-app-Anforderungen
description: ''
keywords: Dokumentation Microsoft verwalteter Desktop, Microsoft-365-Dienst
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: 71952a8b073f002890cc95883e717aeb04c0cd68
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2018
ms.locfileid: "26867543"
---
# <a name="microsoft-managed-desktop-app-requirements"></a>Microsoft verwalteter Desktop-app-Anforderungen

<!--This topic is the target for aka.ms/app-req. This is aka link is used from EA agreeement for MMD. do not delete.-->

<!--Application addendum -->
 
Line-of-Business Applications, die Sie an Microsoft verwalteter Desktop Geräte bereitstellen möchten, müssen die Anforderungen in diesem Thema erfüllen. 

## <a name="application-condition"></a>Anwendung Bedingung

Es ist wichtig, dass Anwendungen sich negativ auf die Umgebung Microsoft verwalteten Desktops keine Auswirkung auf die. Im folgenden werden die Anforderungen, dass eine Anwendung, damit Microsoft erfüllen muss bereitzustellen. Für jede Anwendung oder Treiber kann Microsoft jede Anforderung dargelegten verzichten. Microsoft kann beschließen, entfernen Sie alle Anwendung oder Treiber, die sich negativ auf Leistung und Zuverlässigkeit von Microsoft verwalteten Desktops Geräte auswirkt.

## <a name="deployable-using-microsoft-technologies"></a>Bereitstellung von Microsoft-Technologien

Microsoft verwalteter Desktop verwendet Intune, Microsoft Store und Microsoft Store for Business Applications bereitstellen. Aus diesem Grund müssen Applications auf eine Weise, die von der aktuellen Version dieser Dienste bereitgestellt werden können verpackt werden.

## <a name="prohibited-app-classes"></a>Verbotene app-Klassen

Bestimmte Anwendungstypen dürfen nicht auf verwaltete Microsoft-Desktop-Geräten:
- 3. Partei Antivirus, Sicherheit oder Audit-software
- Versionen von Microsoft Office, bevor Sie Office 365 Pro Plus
- Anwendungen, die installieren oder andere 3. Software von Drittanbietern Verpacken

## <a name="restricted-app-behaviors"></a>Eingeschränkte app Verhaltensweisen

Bestimmte Verhaltensweisen Anwendung werden entweder kann so stark beeinträchtigt bei Benutzererlebnis oder an Microsoft verwalteter Desktop Geräte ein Sicherheitsrisiko darstellen. Applikationen darf nicht die folgenden Verhaltensweisen oder Merkmale aufweisen: 
- Installieren Sie Hintergrunddienste oder erzeugen langer Hintergrundprozesse
- Hinzufügen von selbst zu den Windows-Startpfad
- Rufen Sie nicht dokumentierte Windows- oder Office-APIs oder internen Datenstrukturen Windows- oder Office übernehmen Abhängigkeiten
- Fungieren Sie als app-Store oder über die integrierte Erweiterungsmanager
- Der Endbenutzer Berechtigungen ausweiten
- Sicherheitsrisiken haben bezeichnet werden.
- Mit einem Zertifikat die vertrauenswürdige Stammzertifizierungsstelle Rollup nicht signiert
- Verschlüsseln oder Einschränken des Zugriffs auf Endbenutzerdaten
- Ändern der Betriebssystem-Code zur Laufzeit

## <a name="driver-deployment"></a>Treiber-Bereitstellung

Es sei denn, ein Treiber in Windows Update verfügbar ist oder von Windows Hardware Quality Lab (WHQL) getrennt signiert ist, muss Microsoft einen Treiber genehmigen, bevor Microsoft des Treibers an Microsoft verwalteter Desktop-Geräte Deployment.