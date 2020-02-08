---
title: DSGVO für Project Server
description: Erfahren Sie, wie Sie mit DSGVO-Anforderungen in lokalen Project Server-Installationen umgehen.
f1.keywords:
- NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
titleSuffix: Microsoft GDPR
ms.openlocfilehash: a9fff9f085fd42f28801a82c3f83d6bdd1f74ff6
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41596412"
---
# <a name="gdpr-for-project-server"></a>DSGVO für Project Server

Project Server verwendet benutzerdefinierte Skripts zum Exportieren und Bearbeiten von Benutzerdaten in Project Web App. Die grundlegende Vorgehensweise sieht folgendermaßen aus:

1.  Suchen Sie die Project Web App-Websites in Ihrer Farm.

2.  Suchen Sie auf jeder Website die Projekte, die den Benutzer enthalten.

3.  Exportieren und überprüfen Sie die Arten von Daten, die Sie überprüfen möchten.

4.  Bearbeiten Sie die Daten bei Bedarf.

In den folgenden Artikeln werden diese Schritte ausführlich beschrieben:

- [Exportieren von Benutzerdaten aus Project Server](/Project/export-user-data-from-project-server?toc=/Office365/Enterprise/toc.json)

- [Löschen von Benutzerdaten aus Project Server](/Project/delete-user-data-from-project-server?toc=/Office365/Enterprise/toc.json)


Beachten Sie, dass Project Server auf SharePoint Server aufbaut und Ereignisse in SharePoint-ULS-Protokollen und in der Verwendungsdatenbank protokolliert. Weitere Informationen finden Sie unter [DSGVO für SharePoint Server](gdpr-for-sharepoint-server.md).
