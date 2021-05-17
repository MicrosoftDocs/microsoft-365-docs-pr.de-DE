---
title: Verwenden freigegebener Abfragen in Microsoft 365 erweiterten Defender-Suche
description: Beginnen Sie sofort mit der Bedrohungssuche mit vordefinierten und freigegebenen Abfragen. Geben Sie Ihre Abfragen für die Öffentlichkeit oder Ihre Organisation frei.
keywords: Erweiterte Suche, Bedrohungssuche, Cyberbedrohungssuche, Microsoft 365 Defender, microsoft 365, m365, Suche, Abfrage, Telemetrie, benutzerdefinierte Erkennungen, Schema, Kusto, Github-Repository, meine Abfragen, freigegebene Abfragen
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 83c78f9df5560c75e40a171d770e994b86049204
ms.sourcegitcommit: 7cc2be0244fcc30049351e35c25369cacaaf4ca9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2021
ms.locfileid: "51952584"
---
# <a name="use-shared-queries-in-advanced-hunting"></a>Verwenden von freigegebenen Abfragen bei der erweiterten Suche

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender
- Microsoft Defender für Endpunkt



[Erweiterte Suche](advanced-hunting-overview.md)-Abfragen können von Benutzern derselben Organisation geteilt werden. Sie können öffentlich freigegebene Abfragen auch auf GitHub finden. Mit diesen Abfragen können Sie bestimmte Bedrohungsszenarien schnell verfolgen, ohne dass Sie Abfragen von Grund auf neu erstellen müssen.

![Abbildung freigegebener Abfragen](../../media/advanced-hunting-shared-queries.png)

## <a name="save-modify-and-share-a-query"></a>Speichern, Ändern und Freigeben einer Abfrage
Sie können eine neue oder vorhandene Abfrage so speichern, dass Sie nur für Sie zugänglich oder für andere Benutzer in Ihrer Organisation freigegeben ist. 

1. Erstellen oder Ändern einer Abfrage. 

2. Klicken Sie auf die Dropdownschaltfläche **Abfrage speichern**, und wählen Sie **Speichern unter** aus.
    
3. Geben Sie einen Namen für die Abfrage ein. 

   ![Abbildung des Speicherns einer Abfrage](../../media/advanced-hunting-save-query.png)

4. Wählen Sie den Ordner aus, in dem Sie die Abfrage speichern möchten.
    - **Freigegebene Abfragen** – für alle Benutzer in Ihrer Organisation freigegeben
    - **Meine Abfragen** – nur für Sie zugänglich
    
5. Klicken Sie auf **Speichern**. 

## <a name="delete-or-rename-a-query"></a>Löschen oder Umbenennen einer Abfrage
1. Klicken Sie mit der rechten Maustaste auf eine Abfrage, die Sie umbenennen oder löschen möchten.

    ![Abbildung des Löschens einer Abfrage](../../media/advanced_hunting_delete_rename.png)

2. Wählen Sie **Löschen** aus, und bestätigen Sie Löschung. Oder wählen Sie **Umbenennen** aus und geben Sie einen neuen Namen für die Abfrage ein.

## <a name="create-a-direct-link-to-a-query"></a>Erstellen eines direkten Links zu einer Abfrage
Um einen Link zu generieren, der Ihre Abfrage direkt im Editor für erweiterte Suchabfragen öffnet, müssen Sie Ihre Abfrage abschließend ausführen und link **freigeben auswählen.**

## <a name="access-queries-in-the-github-repository"></a>Access-Abfragen im GitHub-Repository  
Microsoft-Sicherheitsexperten Teilen regelmäßig Abfragen zur erweiterten Suche in einem [dazu vorgesehenen öffentlichen Repository auf GitHub](https://aka.ms/hunting-queries). Dieses Repository ist für Beiträge geöffnet. Um dazu beizutragen, [treten Sie GitHub kostenlos bei](https://github.com/).

>[!tip]
>Microsoft-Sicherheitsexperten stellen zudem Abfragen zur erweiterten Suche bereit, mit denen Sie Aktivitäten und Indikatoren finden können, die mit neuen Bedrohungen verbunden sind. Diese Abfragen werden als Bestandteil der [Bedrohungsanalyse](/windows/security/threat-protection/microsoft-defender-atp/threat-analytics)-Berichte im Microsoft Defender Security Center bereitgestellt.

>[!NOTE]
>Einige Tabellen in diesem Artikel sind möglicherweise nicht in Microsoft Defender for Endpoint verfügbar. [Aktivieren Sie Microsoft 365 Defender,](m365d-enable.md) um bedrohungen mithilfe von weiteren Datenquellen nach Bedrohungen zu fahnen. Sie können Ihre workflows für die erweiterte Suche von Microsoft Defender for Endpoint zu Microsoft 365 Defender verschieben, indem Sie die Schritte unter [Migrate advanced hunting queries from Microsoft Defender for Endpoint ausführen.](advanced-hunting-migrate-from-mde.md)

## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Arbeiten mit Abfrageergebnissen](advanced-hunting-query-results.md)
- [Suche über Geräte, E-Mails, Apps und Identitäten hinweg](advanced-hunting-query-emails-devices.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-tables.md)
- [Anwenden bewährter Methoden für Abfragen](advanced-hunting-best-practices.md)