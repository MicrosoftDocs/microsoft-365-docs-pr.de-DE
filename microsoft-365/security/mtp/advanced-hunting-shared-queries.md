---
title: 'Verwenden von freigegebenen Abfragen in Microsoft Bedrohungsschutz: Erweiterte Suche'
description: Beginnen Sie sofort mit der Bedrohungssuche mit vordefinierten und freigegebenen Abfragen. Geben Sie Ihre Abfragen für die Öffentlichkeit oder Ihre Organisation frei.
keywords: Erweiterte Suche, Bedrohungs Suche, Cyber-Bedrohungs Suche, Microsoft Threat Protection, Microsoft 365, MTP, m365, Suche, Abfrage, Telemetrie, benutzerdefinierte Erkennungen, Schema, Kusto, GitHub Repo, meine Abfragen, freigegebene Abfragen
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 7ff46226e2535ed9826a61afa857e38b03c06ce1
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42234674"
---
# <a name="use-shared-queries-in-advanced-hunting"></a>Verwenden von freigegebenen Abfragen bei der erweiterten Suche

**Gilt für:**
- Microsoft-Bedrohungsschutz



[Erweiterte Suche](advanced-hunting-overview.md)-Abfragen können von Benutzern derselben Organisation geteilt werden. Sie können öffentlich freigegebene Abfragen auch auf GitHub finden. Mit diesen Abfragen können Sie bestimmte Bedrohungsszenarien schnell verfolgen, ohne dass Sie Abfragen von Grund auf neu erstellen müssen.

![Abbildung freigegebener Abfragen](../../media/advanced-hunting-shared-queries.png)

## <a name="save-modify-and-share-a-query"></a>Speichern, Ändern und Freigeben einer Abfrage
Sie können eine neue oder vorhandene Abfrage so speichern, dass Sie nur für Sie zugänglich oder für andere Benutzer in Ihrer Organisation freigegeben ist. 

1. Erstellen oder Ändern einer Abfrage. 

2. Klicken Sie auf die Dropdownschaltfläche **Abfrage speichern**, und wählen Sie **Speichern unter**aus.
    
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

## <a name="access-queries-in-the-github-repository"></a>Access-Abfragen im GitHub-Repository  
Microsoft-Sicherheitsexperten Teilen regelmäßig Abfragen zur erweiterten Suche in einem [dazu vorgesehenen öffentlichen Repository auf GitHub](https://github.com/microsoft/MTP-AHQ). Dieses Repository ist für Beiträge geöffnet. Um dazu beizutragen, [treten Sie GitHub kostenlos bei](https://github.com/).

>[!tip]
>Microsoft-Sicherheitsexperten stellen zudem Abfragen zur erweiterten Suche bereit, mit denen Sie Aktivitäten und Indikatoren finden können, die mit neuen Bedrohungen verbunden sind. Diese Abfragen werden als Bestandteil der [Bedrohungsanalyse](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/threat-analytics)-Berichte im Microsoft Defender Security Center bereitgestellt.

## <a name="related-topics"></a>Verwandte Themen
- [Vorbeugende Suche nach Bedrohungen](advanced-hunting-overview.md)
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Suche nach Bedrohungen auf Geräten und in E-Mails](advanced-hunting-query-emails-devices.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-tables.md)
- [Anwenden bewährter Methoden für Abfragen](advanced-hunting-best-practices.md)
