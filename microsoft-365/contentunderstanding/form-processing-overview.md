---
title: Übersicht über die Formularverarbeitung
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Informationen zur Formularverarbeitung in Microsoft SharePoint Syntex
ms.openlocfilehash: 84aeb7c4e3fc850e5e4c2336e576ff3bce3ecf4b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928308"
---
# <a name="form-processing-overview"></a>Übersicht über die Formularverarbeitung

 ![AI Builder](../media/content-understanding/ai-builder.png)</br>

Microsoft SharePoint Syntex verwendet die Microsoft PowerApps [AI Builder](/ai-builder/overview) -Formularverarbeitung, um Modelle in SharePoint-Dokumentbibliotheken zu erstellen.

Mithilfe der AI Builder-Formularverarbeitung können Sie KI-Modelle erstellen, die maschinelle Lerntechnologien nutzen, um Schlüsselwertpaare und Tabellendaten aus strukturierten oder teilstrukturierten Dokumenten wie Formularen und Rechnungen zu identifizieren und extrahieren.

Unternehmen erhalten häufig viele Rechnungen aus einer Vielzahl von Quellen, z. B. per Post, Fax, E-Mail usw. Die Verarbeitung dieser Dokumente und die manuelle Eingabe der entsprechenden Daten in eine Datenbank können sehr viel Zeit in Anspruch nehmen. Die Formularverarbeitung automatisiert diesen Vorgang durch den Einsatz von künstlicher Intelligenz zum Extrahieren von Text, Schlüssel-/Wertpaaren und Tabellen aus Ihren Dokumenten. 

> [!NOTE]
> Weitere Informationen zu Beispielszenarien für die Formularverarbeitung finden Sie unter [SharePoint Syntex – Leitfaden für die ersten Schritte](./adoption-getstarted.md#form-processing-scenario-example).

Sie können z. B. ein Formularverarbeitungsmodell erstellen, das alle Auftragsdokumente erkennt, die in die Dokumentbibliothek hochgeladen werden. Aus jedem Auftrag können dann bestimmte für Sie wichtige Daten extrahiert und angezeigt werden, z. B. *Auftragsnummer*, *Datum* oder *Gesamtbetrag*.

![Dokumentbibliotheksansicht](../media/content-understanding/doc-lib-done.png)</br>  

Um das Modell zu trainieren und die Informationen zu definieren, die aus dem Formular extrahiert werden sollen, werden Beispieldateien verwendet. Ihr Modell lernt durch das Trainieren den Aufbau Ihres Dokuments kennen. Für den Anfang benötigen Sie nur fünf Formulare. AI Builder analysiert Ihre Beispieldateien auf Schlüssel-/Wertpaare, darüber hinaus können Sie manuell diejenigen ermitteln, die evtl. nicht erkannt wurden.  Im AI Builder können Sie die Genauigkeit Ihres Modells anhand Ihrer Beispieldateien testen.

Nachdem Sie das Modell trainiert und veröffentlicht haben, erstellt das Modell einen [Power Automation-Ablauf](/power-automate/getting-started). Der Ablauf wird ausgeführt, wenn eine Datei in die SharePoint-Dokumentbibliothek hochgeladen wird, und extrahiert Daten, die im Modell erkannt wurden. Die extrahierten Daten werden in Spalten in der Dokumentbibliotheksansicht Ihres Modells angezeigt.

Damit Benutzer ein [Formularverarbeitungsmodell erstellen](create-a-form-processing-model.md) können, muss ein Office 365-Administrator die [Formularverarbeitung für die SharePoint-Dokumentbibliothek aktivieren](./set-up-content-understanding.md#to-set-up-content-understanding). Sie können die Websites während des Setups oder nach dem Setup in den Verwaltungseinstellungen auswählen.

### <a name="file-limitations"></a>Dateieinschränkungen

Wenn Sie das Formular zur Verarbeitung von Modellen verwenden, stellen Sie sicher, dass die [Anforderungen und die Einschränkungen der Dateinutzung](/ai-builder/form-processing-model-requirements) eingetragen sind.

### <a name="multi-geo-environments"></a>Multi-Geo-Umgebungen

Wenn sie SharePoint Syntex in einer [Microsoft 365 Multi-Geo-Umgebung](../enterprise/microsoft-365-multi-geo.md) aufsetzen, dann können Sie es nur für die Verwendung der Formularverarbeitung am zentralen Speicherort konfigurieren. Wenn Sie die Formularverarbeitung in einem Satellitenstandort verwenden wollen, kontaktieren Sie den Microsoft-Support.






## <a name="see-also"></a>Siehe auch
  
[Power Automate-Dokumentation](/power-automate/)

[Erstellen eines Formularverarbeitungsmodells](create-a-form-processing-model.md)

[Übersicht über das Dokumentenverständnis](document-understanding-overview.md)

[Schulungen: Verbessern der Geschäftsergebnisse mit AI Builder](/learn/paths/improve-business-performance-ai-builder/?source=learn)