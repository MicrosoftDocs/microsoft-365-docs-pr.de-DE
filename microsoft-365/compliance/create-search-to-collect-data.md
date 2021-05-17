---
title: Erstellen einer Suche
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Informationen zum Erstellen, Definieren und Auswählen von Verwahrern und Verwahrstellen für eine Suche in einem Advanced eDiscovery Fall.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 1d9051824ff3f28484d0750b982edd70334a9b88
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035767"
---
# <a name="create-a-search"></a>Erstellen einer Suche

Auf der **Registerkarte Suchen** in Ihrem Fall können Sie eine neue Suche erstellen, indem Sie auf **Neue** Suche klicken und dem Assistenten folgen.

![Der Suchassistent in einem Advanced eDiscovery Fall](../media/AeDSearch1.png)

## <a name="name-the-search-and-give-it-a-description"></a>Benennen Sie die Suche, und geben Sie ihr eine Beschreibung.

Jede Suche mit einem Fall sollte einen eindeutigen Namen haben. Sie können optional eine Beschreibung für Ihre Suche bereitstellen. 

## <a name="choose-the-custodians-and-custodial-locations-to-search"></a>Wählen Sie die zu durchsuchenden Verwahrer und Verwahrer aus.

Wählen Sie Speicherorte für verwahrerische Inhalte aus, um zu suchen, indem Sie angeben, welche Verwahrer Sie dem Fall hinzugefügt haben. Wenn Sie einen Verwahrer auswählen, führen Sie die Suche nach allen Datenquellen aus, die dem Custodian zugeordnet sind. Sie haben auch die Möglichkeit, die Suche für jeden Custodian auf ausgewählte Datenquellen zu verenten. Weitere Informationen zum Hinzufügen von Custodians und zum Verwalten ihrer Datenquellen finden Sie unter [Arbeiten mit Verwahrern](managing-custodians.md).

## <a name="choose-non-custodial-locations"></a>Wählen Sie nicht verwahrungsfreie Speicherorte aus

In einigen Fällen können Sie Datenquellen durchsuchen, die keinem Verwahrer zugeordnet sind. In diesem Fall können Sie die Speicherorte angeben, die Sie durchsuchen möchten, oder alle Inhaltsspeicherorte nach einem bestimmten Microsoft-Dienst durchsuchen (z. B. alle Exchange-Postfächer oder alle SharePoint-Websites und OneDrive-Konten).

## <a name="define-the-search-query-and-conditions"></a>Definieren der Suchabfrage und -bedingungen

Sie können die Schlüsselwörterabfrage und alle Bedingungen für die Suche mithilfe der vordefinierten Bedingungskarten oder mithilfe von Keyword Query Language (KQL) definieren. Weitere Informationen finden Sie unter [Erstellen von Suchabfragen](building-search-queries.md).
