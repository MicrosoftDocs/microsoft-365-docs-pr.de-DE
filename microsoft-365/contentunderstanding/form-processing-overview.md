---
title: Übersicht über die Formularverarbeitung
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Informationen zur Formularverarbeitung in Microsoft SharePoint Syntex
ms.openlocfilehash: 518bc13017762bbe21420a81726e89c9c327834d
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295176"
---
# <a name="form-processing-overview-preview"></a>Übersicht über die Formularverarbeitung (Vorschau)

Der Inhalt in diesem Artikel ist für die Project Cortex private Preview. [Erfahren Sie mehr über Project Cortex](https://aka.ms/projectcortex).

Project Cortex verwendet Microsoft PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview) -Formularverarbeitung zum Erstellen von Modellen in SharePoint-Dokumentbibliotheken.

Sie können die AI Builder-Formularverarbeitung zum Erstellen von AI-Modellen verwenden, die maschinelle Lerntechnologie zum Identifizieren und Extrahieren von Schlüssel/Wert-Paaren und Tabellendaten aus strukturierten oder semi-strukturierten Dokumenten wie Formularen und Rechnungen verwenden.

Verwenden Sie die AI Builder-Formularverarbeitung, um AI-Modelle zu erstellen, die die maschinelle Lerntechnologie (ml) zum Identifizieren und Extrahieren von Schlüssel/Wert-Paaren und Tabellendaten aus strukturierten oder semi-strukturierten Dokumenten wie Formularen und Rechnungen nutzen.

Organisationen erhalten häufig Rechnungen in großen Mengen aus einer Vielzahl von Quellen wie e-Mail, Fax, e-Mail usw. Die Verarbeitung dieser Dokumente und die manuelle Eingabe in eine Datenbank kann sehr viel Zeit in Anspruch nehmen. Durch die Verwendung von AI zum Extrahieren von Text, Schlüssel/Wert-Paaren und Tabellen aus Ihren Dokumenten automatisiert die Formularverarbeitung diesen Prozess. 

Sie können beispielsweise ein Formular Verarbeitungsmodell erstellen, das alle Bestelldokumente identifiziert, die in die Dokumentbibliothek hochgeladen werden. Aus jeder Bestellung können Sie dann bestimmte Daten extrahieren und anzeigen, die für Sie wichtig sind, beispielsweise *Bestellnummer*, *Datum*oder *Gesamtkosten*.

Sie können auch Beispieldateien verwenden, um Ihr Modell zu trainieren und die Informationen zu definieren, die aus dem Formular extrahiert werden sollen. Das Layout Ihres Dokuments wird durch Schulung Ihres Modells erlernt. Für die ersten Schritte benötigen Sie mindestens fünf Formular Dokumente. AI Building analysiert Ihre Beispieldateien auf Schlüssel-Wert-Paare und identifiziert dann manuell diejenigen, die möglicherweise nicht erkannt wurden.  Mit AI Builder können Sie die Genauigkeit Ihres Modells in ihren Beispieldateien testen.

Nachdem Sie Ihr Modell trainiert und veröffentlicht haben, verwenden Sie es, um einen [Power-Automatisierungs Fluss](https://docs.microsoft.com/power-automate/getting-started) zu erstellen, der ausgeführt wird, nachdem eine Datei in die SharePoint-Dokumentbibliothek hochgeladen wurde. Anschließend werden Daten extrahiert, die im Modell identifiziert wurden. Die extrahierten Daten werden in den Spalten in der Dokumentbibliotheksansicht Ihres Modells angezeigt.

Sie verwenden Beispieldateien, um Ihr Modell zu trainieren und die Informationen zu definieren, die aus dem Formular extrahiert werden sollen. Das Layout Ihres Dokuments wird durch Schulung Ihres Modells erlernt. Für die ersten Schritte benötigen Sie nur fünf Formular Dokumente. AI Builder analysiert Ihre Beispieldateien auf Schlüssel-Wert-Paare, und Sie können auch manuell erkennen, welche möglicherweise nicht erkannt wurden.  Mit AI Builder können Sie die Genauigkeit Ihres Modells in ihren Beispieldateien testen.

Nachdem Sie Ihr Modell trainiert und veröffentlicht haben, erstellen Sie einen Power- [Automatisierungs Fluss](https://docs.microsoft.com/power-automate/getting-started), um ihn zu verwenden. Der Fluss wird ausgeführt, wenn eine Datei in die SharePoint-Dokumentbibliothek hochgeladen wird und Daten extrahiert, die im Modell identifiziert wurden. Die extrahierten Daten werden in den Spalten in der Dokumentbibliotheksansicht Ihres Modells angezeigt.

Ein Office 365 Administrator muss die [Formularverarbeitung](https://docs.microsoft.com/microsoft-365/contentunderstanding/set-up-content-understanding#to-set-up-content-understanding) für die SharePoint-Dokumentbibliothek aktivieren, damit Benutzer [ein Formular Verarbeitungsmodell](create-a-form-processing-model.md) in dieser erstellen können.

## <a name="see-also"></a>Siehe auch
  
[Power Automation-Dokumentation](https://docs.microsoft.com/power-automate/)</br>
[Erstellen eines Formular Verarbeitungsmodells](create-a-form-processing-model.md)</br>
[Dokument Verständnis Übersicht](document-understanding-overview.md)</br>
[Schulung: verbessern der Geschäftsleistung mit AI Builder](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>
