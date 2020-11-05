---
title: App Monitoring & Reporting – Security Center
description: Hier erfahren Sie, wie Sie in Ihrer Organisation einen besseren Einblick in die Cloud-App-Nutzung erhalten. Umfasst verschiedene Arten von apps, deren Risikograd und Warnungen.
keywords: Sicherheit, Schadsoftware, Microsoft 365, M365, Sicherheitscenter, Monitor, Bericht, Apps
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f73c6b010677cdc481655d1d5310872fd1a99126
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920514"
---
# <a name="app-monitoring-and-reporting-in-the-microsoft-365-security-center"></a>App-Überwachung und Berichterstellung im Microsoft 365 Security Center

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


Diese Berichte bieten einen besseren Einblick in die Verwendung von Cloud-apps in Ihrer Organisation. Umfasst verschiedene Arten von apps, deren Risikograd und Warnungen.

## <a name="monitor-email-accounts-at-risk"></a>Überwachung von gefährdeten E-Mail-Konten

**E-Mail-Schutz** zeigt e-Mail-Konten gefährdet an. Sie können ein Konto auswählen, das im Microsoft Defender Security Center weiter untersucht werden soll.

![E-Mail-Schutzkarte](../../media/email-protection.png)

## <a name="monitor-app-permissions-granted-by-users"></a>Überwachen der von Benutzern erteilten App-Berechtigungen

**Cloud-App-Sicherheit – OAuth-apps** listet apps auf, die von der Cloud-App-Sicherheit erkannt wurden, denen Benutzerberechtigungen erteilt wurden. Der Risikokatalog von Cloud App Security umfasst über 16.000 apps, die mit über 70 Risikofaktoren bewertet werden.

Die Risikofaktoren beginnen mit allgemeinen Informationen, beispielsweise mit dem App-Herausgeber. Anschließend werden Sicherheitsmaßnahmen und-Steuerelemente verschoben, beispielsweise ob die APP die Verschlüsselung in Rest unterstützt oder ein Überwachungsprotokoll der Benutzeraktivität bereitstellt.

![Cloud App Security OAuth apps Card](../../media/cloud-app-security-oauth-apps.png)

## <a name="monitor-cloud-app-user-accounts"></a>Überwachen von Cloud-App-Benutzerkonten

**Cloud-App-Konten für die Überprüfung** listet Konten auf, die möglicherweise Aufmerksamkeit erfordern.

![Cloud-App-Konten für Überprüfungs Karte](../../media/cloud-app-accounts-for-review.png)

## <a name="understand-which-cloud-apps-are-used"></a>Grundlegendes zu den verwendeten Cloud-apps

**Erkannte Cloud-Apps (Kategorien)** zeigen an, welche Arten von apps in Ihrer Organisation verwendet werden. Sie enthält Links zum Cloud Discovery-Dashboard in der Cloud-App-Sicherheit. Weitere Informationen finden Sie unter [Quick Start: Arbeiten mit entdeckten apps](https://docs.microsoft.com/cloud-app-security/discovered-apps).  

![Entdeckte Cloud Apps-Kategorien Karte](../../media/discovered-cloud-apps-categories.png)

## <a name="monitor-where-users-access-cloud-apps"></a>Überwachen der Benutzer auf Cloud-apps

**Cloud-App-Aktivitäts Speicherorte** zeigen an, wo Benutzer auf Cloud-apps zugreifen.

![Cloud-App-Aktivitäts Speicherkarte](../../media/cloud-app-activity-locations.png)

## <a name="monitor-health-for-infrastructure-workloads"></a>Überwachen der Integrität von Infrastruktur Auslastungen

**Infrastruktur Integrität** zeigt Integritätsstatus Warnungen für Infrastruktur Arbeitslasten in Azure Defender an.

Azure Defender bietet einheitliches Sicherheitsmanagement und Defender für Office 365 über lokale und Cloud-Arbeitslasten hinweg. Sie können Sicherheitsdaten aus unterschiedlichen Quellen, einschließlich Firewalls und anderen Partnerlösungen, sammeln, durchsuchen und analysieren.

Weitere Informationen finden Sie unter [Dokumentation zu Azure Defender](https://docs.microsoft.com/azure/security-center/).

![Infrastruktur-Integritäts Karte](../../media/infrastructure-health.png)
