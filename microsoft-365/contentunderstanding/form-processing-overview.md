---
title: Übersicht über die Formularverarbeitung
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Priority
description: Informationen zur Formularverarbeitung in Microsoft SharePoint Syntex
ms.openlocfilehash: bbdf318b7d0c4a9f58cc79453dfaaf0daf5b9a5c
ms.sourcegitcommit: b06a4f21da247edb03fdf6a01eafb7d4fb387b33
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2020
ms.locfileid: "48333902"
---
# <a name="form-processing-overview"></a>Übersicht über die Formularverarbeitung

 ![AI Builder](../media/content-understanding/ai-builder.png)</br>

Microsoft SharePoint Syntex verwendet die Microsoft PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview) -Formularverarbeitung, um Modelle in SharePoint-Dokumentbibliotheken zu erstellen.

Mithilfe der AI Builder-Formularverarbeitung können Sie KI-Modelle erstellen, die maschinelle Lerntechnologien nutzen, um Schlüsselwertpaare und Tabellendaten aus strukturierten oder teilstrukturierten Dokumenten wie Formularen und Rechnungen zu identifizieren und extrahieren.

Unternehmen erhalten häufig viele Rechnungen aus einer Vielzahl von Quellen, z. B. per Post, Fax, E-Mail usw. Die Verarbeitung dieser Dokumente und die manuelle Eingabe der entsprechenden Daten in eine Datenbank können sehr viel Zeit in Anspruch nehmen. Die Formularverarbeitung automatisiert diesen Vorgang durch den Einsatz von künstlicher Intelligenz zum Extrahieren von Text, Schlüssel-/Wertpaaren und Tabellen aus Ihren Dokumenten. 

> [!NOTE]
> Weitere Informationen zu Beispielszenarien für die Formularverarbeitung finden Sie unter [SharePoint Syntex – Leitfaden für die ersten Schritte](https://docs.microsoft.com/microsoft-365/contentunderstanding/adoption-getstarted#form-processing-scenario-example).

Sie können z. B. ein Formularverarbeitungsmodell erstellen, das alle Auftragsdokumente erkennt, die in die Dokumentbibliothek hochgeladen werden. Aus jedem Auftrag können dann bestimmte für Sie wichtige Daten extrahiert und angezeigt werden, z. B. *Auftragsnummer*, *Datum*oder *Gesamtbetrag*.

![Dokumentbibliotheksansicht](../media/content-understanding/doc-lib-done.png)</br>  

Sie können auch Beispieldateien verwenden, um das Modell zu trainieren und die Informationen zu definieren, die aus dem Formular extrahiert werden sollen. Durch das Trainieren lernt das Modell den Aufbau Ihres Dokuments kennen, und es lernt, Daten aus ähnlichen Stellen in Ihren Formularen zu extrahieren, da diese einen ähnlich strukturierten Aufbau aufweisen. 

Für den Anfang benötigen Sie mindestens fünf Formulare. AI Builder analysiert Ihre Beispieldateien auf Schlüssel-/Wertpaare, und Sie können dann manuell diejenigen ermitteln, die evtl. nicht erkannt wurden.  Im AI Builder können Sie die Genauigkeit Ihres Modells anhand Ihrer Beispieldateien testen.

Nachdem Sie Ihr Modell trainiert und veröffentlicht haben, verwenden Sie es, um einen [Power Automation-Ablauf](https://docs.microsoft.com/power-automate/getting-started) zu erstellen, der nach dem Hochladen einer Datei in die SharePoint-Dokumentbibliothek ausgeführt wird. Anschließend werden die im Modell identifizierten Daten extrahiert. Die extrahierten Daten werden in Spalten in der Dokumentbibliotheksansicht Ihres Modells angezeigt.

Um das Modell zu trainieren und die Informationen zu definieren, die aus dem Formular extrahiert werden sollen, werden Beispieldateien verwendet. Ihr Modell lernt durch das Trainieren den Aufbau Ihres Dokuments kennen. Für den Anfang benötigen Sie nur fünf Formulare. AI Builder analysiert Ihre Beispieldateien auf Schlüssel-/Wertpaare, darüber hinaus können Sie manuell diejenigen ermitteln, die evtl. nicht erkannt wurden.  Im AI Builder können Sie die Genauigkeit Ihres Modells anhand Ihrer Beispieldateien testen.

Nachdem Sie das Modell trainiert und veröffentlicht haben, erstellt das Modell einen [Power Automation-Ablauf](https://docs.microsoft.com/power-automate/getting-started). Der Ablauf wird ausgeführt, wenn eine Datei in die SharePoint-Dokumentbibliothek hochgeladen wird, und extrahiert Daten, die im Modell erkannt wurden. Die extrahierten Daten werden in Spalten in der Dokumentbibliotheksansicht Ihres Modells angezeigt.

Damit Benutzer ein [Formularverarbeitungsmodell erstellen](create-a-form-processing-model.md) können, muss ein Office 365-Administrator die [Formularverarbeitung für die SharePoint-Dokumentbibliothek aktivieren](https://docs.microsoft.com/microsoft-365/contentunderstanding/set-up-content-understanding#to-set-up-content-understanding).



## <a name="see-also"></a>Siehe auch
  
[Power Automate-Dokumentation](https://docs.microsoft.com/power-automate/)

[Erstellen eines Formularverarbeitungsmodells](create-a-form-processing-model.md)

[Übersicht über das Dokumentenverständnis](document-understanding-overview.md)

[Schulungen: Verbessern der Geschäftsergebnisse mit AI Builder](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)
