---
title: Importieren eines Ausdruckssatzes mithilfe eines SKOS-basierten Formats
description: Erfahren Sie, wie Sie einen Ausdruckssatz mit einem SKOS-basierten Format importieren
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.service: ''
ms.collection: enabler-strategic
search.appverid: ''
localization_priority: Priority
ms.openlocfilehash: 8a1b61088d0a1594bf1a71542158ade389cce2ab
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288515"
---
# <a name="import-a-term-set-using-a-skos-based-format"></a>Importieren eines Ausdruckssatzes mithilfe eines SKOS-basierten Formats

Sie können einen Ausdruckssatz mit einem SKOS-basierten Format importieren. Ausführliche Informationen zum Format finden Sie unter [SharePoint-Taxonomie SKOS-Format Referenz](skos-format-reference.md). Dieses Feature benötigt eine [SharePoint Syntex](index.md)-Lizenz.

Es wird empfohlen, Ihre Importdateien auf weniger als 20.000 Ausdrücke zu belassen. Größere Dateien können die Zeit für die Überprüfung und den Import verlängern.

1. Erweitern Sie im SharePoint Admin Center **Inhaltsdienste**, und klicken Sie dann auf **Terminologiespeicher**.

2. Wählen Sie die Ausdrucksgruppe aus, in die Sie den Ausdruckssatz importieren möchten.

3. Klicken Sie auf der Befehlsleiste auf **Import Ausdruckssatz**.

4. Wenn Sie eine Beispieldatei herunterladen möchten, die Sie als Vorlage verwenden möchten, klicken Sie auf **sample-metadata.ttl**, um eine Beispieldatei mit dem SKOS-basierten Format abzurufen.

5. Erstellen Sie die Importdatei mit den Ausdruckssätze & Ausdrücke, die Sie importieren möchten.

6. Unter **Dateiformat**, wählen Sie **SKOS (*.ttl)** aus.

7. Klicken Sie auf **Durchsuchen**, navigieren Sie zu Ihrer Importdatei, und fügen Sie sie hinzu.

8. Klicken Sie auf **Importieren**. Schließen Sie den Bereich erst, wenn der Import abgeschlossen ist.

Bei einem erfolgreichen Import der Datei wird eine Erfolgsmeldung angezeigt, und der Terminologiespeicher wird aktualisiert, und Sie können zu den neu erstellten Ausdruckssätzen wechseln.

## <a name="see-also"></a>Weitere Informationen:

[Einführung in verwaltete Metadaten](/sharepoint/managed-metadata)

[Übersicht über das Dokumentenverständnis](document-understanding-overview.md)

[Importieren von Ausdruckssatz (Websiteebene)](https://support.microsoft.com/office/168fbc86-7fce-4288-9a1f-b83fc3921c18)
