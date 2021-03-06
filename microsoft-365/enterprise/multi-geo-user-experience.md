---
title: Benutzeroberfläche in einer Multi-Geo-Umgebung
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.collection:
- SPO_Content
- Strat_SP_gtc
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
localization_priority: Normal
description: Mehr zur Benutzeroberfläche von SharePoint, OneDrive und Exchange in einer Multi-Geo-Umgebung für Microsoft 365.
ms.openlocfilehash: 4e752581f4ca692f9fecc5019f8e34543ebf7067
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362378"
---
# <a name="user-experience-in-a-multi-geo-environment"></a>Benutzererfahrung in einer Multi-Geo-Umgebung

Im Folgenden wird erläutert, was Benutzern in einer Multi-Geo-Konfiguration in OneDrive angezeigt wird:

## <a name="exchange-mailbox"></a>Exchange-Postfach

Das Exchange-Postfach eines Benutzers wird an dessen bevorzugten Datenspeicherort bereitgestellt und automatisch verschoben, wenn die PDL-Einstellungen geändert werden. Benutzer können Outlook und Outlook im Web in Multi-Geo-Umgebungen wie gewohnt und ohne Auswirkungen auf die Benutzererfahrung verwenden.

## <a name="hub-sites"></a>Hubwebsites

SharePoint-Hubwebsites verbessern den Discovery- und Engagement-Prozess mit Inhalten für Mitarbeiter und gewährleisten eine vollständige und einheitliche Darstellung von Projekten, Abteilungen oder Regionen. In einer Multi-Geo-Umgebung können Satellitenstandort-Websites ganz einfach mit einer Hubwebsite verknüpft werden, unabhängig vom geografischen Standort der Hubwebsite. Über eine zentrale Suchoberfläche können Benutzer unabhängig vom geografischen Standort der Websites den gesamten Hub durchsuchen und entsprechende Ergebnisse erhalten.

## <a name="microsoft-365-app-launcher"></a>Microsoft 365-App-Startfeld

Mit jeder Kachel wird an den entsprechenden geografischen Standort des Workloads weitergeleitet. Die SharePoint- und OneDrive-Kacheln verweisen auf den Standort, der dem bereitgestellten geografischen Standort des Benutzers entspricht. Dies bedeutet, dass SharePoint-Kacheln im Falle von Benutzern mit einer OneDrive-Umgebung am zentralen Standort auf die SharePoint-Homepage verweisen, während die Gruppenwebsites solcher Benutzer an den als PDL festgelegten Standort bereitgestellt werden. 

## <a name="office-applications"></a>Office-Anwendungen

Office Anwendungen wie Word, Excel und PowerPoint erkennt automatisch den richtigen geografischen Standort OneDrive für jeden Benutzer, wenn er sich anmeldet. Benutzer müssen nicht die für den geografischen OneDrive-oder SharePoint-Standort spezifische URL eingeben.

## <a name="onedrive-sync-app"></a>OneDrive-Synchronisation-App

Die OneDrive-Synchronisation-App (Version 17.3.6943.0625 und höher) erkennt automatisch den richtigen OneDrive geografischen Standort für den Benutzer. Die Unterstützung von Synchronisierungs-Apps umfasst die Möglichkeit, gruppenbasierte Websites unabhängig von ihrem geografischen Standort zu synchronisieren. Beachten Sie, dass der Groove-Synchronisierungsclient nicht für Multi-Geo-Umgebungen unterstützt wird. 

## <a name="onedrive-location"></a>OneDrive Standort

Benutzer erhalten ihre OneDrive an ihrem bevorzugten Datenspeicherort bereitgestellt. Wenn ein Benutzer zu einer OneDrive URL navigiert, die einen falschen geografischen Standort enthält (z. B. ein Lesezeichen von einem vorherigen geografischen Standort), wird er automatisch an den OneDrive am entsprechenden geografischen Standort umgeleitet.

## <a name="onedrive-ios-and-android"></a>OneDrive unter IOS und Android 

In den mobilen OneDrive-Apps für iOS und Android werden Ihre OneDrive-Dateien und für Sie freigegebene Dateien unabhängig vom geografischen Standort angezeigt. Die Suche in den mobilen OneDrive-Apps geben relevante Ergebnisse von allen geografischen Standorten zurück. Laden Sie die neueste Version dieser Apps herunter.

Weitere Informationen finden Sie unter Verwenden von [OneDrive unter iOS](https://support.office.com/article/08d5c5b2-ccc6-40eb-a244-fe3597a3c247) und [OneDrive unter Android](https://support.office.com/article/eee1d31c-792d-41d4-8132-f9621b39eb36).

## <a name="onedrive-mobile-client"></a>OneDrive Mobile-Client 

Der OneDrive Mobile-Client ist Multi-Geo-fähig und zeigt relevante Inhalte und Ergebnisse von allen geografischen Standorten an.

## <a name="search"></a>Suchen

Jeder geografische Standort verfügt über einen eigenen Suchindex und ein Suchcenter. Wenn ein Benutzer sucht, wird die Abfrage an alle geografischen Standorte gesendet, und die zurückgegebenen Ergebnisse werden zusammengeführt und dann bewertet, sodass der Benutzer einheitliche Ergebnisse erhält. Benutzer erhalten Unabhängig von ihrem eigenen geografischen Standort Ergebnisse von allen geografischen Standorten. Einzelheiten finden Sie unter [Konfigurieren der Suche nach OneDrive Multi-Geo.](configure-search-for-multi-geo.md)

Die folgenden Suchclients werden unterstützt:

-   OneDrive

-   Delve

-   SharePoint-Homepage

-   Das Suchcenter

-   Benutzerdefinierte Suchanwendungen, die die SharePoint-Suche-API verwenden

## <a name="sharepoint-home"></a>SharePoint-Homepage 

In SharePoint Multi-Geo wird Ihr SharePoint-Zuhause an dem Speicherort gehostet, an dem sich der Benutzer befindet, wie durch seinen OneDrive Standort bestimmt. Wenn die OneDrive-Umgebung eines Benutzers zum Beispiel über einen europäischen Satellitenstandort gehostet wird, wird dessen SharePoint-Homepage in Europa gerendert. Die SharePoint-Homepage enthält unabhängig von ihrem geografischen Standort alle für den Benutzer relevanten Inhalte. 

**Gefolgte Websites, Neuigkeiten von Websites, Zuletzt geöffnete Websites, Häufig verwendete Websites, und Empfohlene Websites**

All diese Komponenten werden dem Benutzer unabhängig von dem geografischen Standort, an dem die Inhalte gehostet werden, unter der Bedingung angezeigt, dass der Benutzer über entsprechende Berechtigungen verfügt. 

**Wichtige Links**

Administratoren können abhängig vom jeweiligen geografischen Standort wichtige Links auf der SharePoint-Homepage einrichten. So kann der Administrator für Benutzer in jeder Region jeweils wichtige Links auf der SharePoint-Homepage hervorheben. 

## <a name="sharepoint-mobile-client"></a>SharePoint Mobile-Client 

Der SharePoint Mobile-Client ist Multi-Geo-fähig und zeigt relevante Inhalte und Ergebnisse von allen geografischen Standorten an.

## <a name="sharing"></a>Freigabe

Die Personenauswahl-Ansicht zeigt sämtliche Benutzer unabhängig von ihrem geografischen Standort an. Dadurch hat ein Benutzer die Möglichkeit, Inhalte mit anderen Benutzern am selben oder an einem anderen Ihrem Mandanten zugewiesenen geografischen Standort zu teilen. Inhalte von verschiedenen geografischen Standorten werden in der Ansicht **"Für mich freigegeben"** im OneDrive des Benutzers angezeigt und können mit single Sign-On-Umgebung aufgerufen werden, unabhängig davon, in welchem geografischen Standort sie gehostet wird.

## <a name="teams-experience"></a>Teams-Erfahrung

Teams ist ein Multi-Geo-Dienst. OneDrive- und zuletzt angezeigte Dateien werden unabhängig vom geografischen Standort des Benutzers angezeigt. @-Erwähnungen funktionieren mit Benutzern von allen geografischen Standorten.

## <a name="user-profiles"></a>Benutzerprofile

Benutzerprofilinformationen werden an dem geografischen Standort des Benutzers verwaltet. Beim Auswählen eines Benutzers werden Sie an den entsprechenden geografischen Standort des Benutzers weitergeleitet, wo vollständige Profilinformationen angezeigt werden.

Wenn Delve deaktiviert ist, sehen Sie das klassische Profil in SharePoint, welches nicht Multi-Geo-fähig ist.


