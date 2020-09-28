---
title: Importieren eines Ausdruckssatzes mithilfe eines SKOS-basierten Formats
description: Informationen zum Importieren eines Ausdruckssatzes mithilfe eines SKOS-basierten Formats
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: aaed88463f690853672780b48a8ee3857a956847
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/28/2020
ms.locfileid: "48296075"
---
# <a name="import-a-term-set-using-a-skos-based-format"></a>Importieren eines Ausdruckssatzes mithilfe eines SKOS-basierten Formats

Sie können einen Ausdruckssätzen mit einem SKOS-basierten Format importieren. Ausführliche Informationen zum Format finden Sie unter [SharePoint Taxonomie SKOS Format Reference](skos-format-reference.md).

Es wird empfohlen, ihre Importdateien auf weniger als 20.000 Begriffe zu halten. Größere Dateien können die für die Überprüfung und den Import entstehende Zeit verlängern.

1. Erweitern Sie im SharePoint Admin Center die Option **Inhaltsdienste**, und klicken Sie dann auf **Terminologiespeicher**.

2. Wählen Sie die Ausdrucksgruppe aus, in die Sie den Ausdruckssätze importieren möchten.

3. Klicken Sie auf der Befehlsleiste auf **Ausdruckssätze importieren**.
 
4.  Wenn Sie eine Beispieldatei herunterladen möchten, die als Vorlage verwendet werden soll, klicken Sie auf **Sample-Metadata. TTL** , um eine Beispieldatei abzurufen, in der das SKOS-basierte Format verwendet wird.
 
5.  Erstellen Sie die Importdatei, die die Ausdruckssätze enthält & Begriffe, die Sie importieren möchten.

6.  Wählen Sie unter **Dateiformat**die Option **SKOS (*. TTL)** aus.

7.  Klicken Sie auf **Durchsuchen** , navigieren Sie zu und fügen Sie die Importdatei hinzu.

8.  Klicken Sie auf **Importieren**. Schließen Sie den Bereich erst, wenn der Import abgeschlossen ist.

Bei einem erfolgreichen Import der Datei wird eine Erfolgsmeldung angezeigt, und der Laufzeitspeicher wird aktualisiert, und Sie können zu den neu erstellten Ausdruckssätzen navigieren.

## <a name="see-also"></a>Siehe auch

[Einführung in verwaltete Metadaten](https://docs.microsoft.com/sharepoint/managed-metadata)

[Dokument Verständnis Übersicht](document-understanding-overview.md)

[Importieren von Ausdruckssätzen (Websiteebene)](https://support.microsoft.com/office/168fbc86-7fce-4288-9a1f-b83fc3921c18)