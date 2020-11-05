---
title: Hinzufügen von Suchergebnissen zu einem Prüfdateisatz
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
ms.custom:
- seo-marvel-apr2020
description: In diesem Artikel erfahren Sie, wie Sie Suchergebnisse oder Beispiele dieser Suchergebnisse zu einer erweiterten eDiscovery-Fall Prüfungsgruppe hinzufügen.
ms.openlocfilehash: 25ea5fe076753d4a5685f1224b98a2005d334f5f
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2020
ms.locfileid: "48919977"
---
# <a name="add-search-results-to-a-review-set"></a>Hinzufügen von Suchergebnissen zu einem Prüfdateisatz

Wenn Sie mit den Ergebnissen einer Suche zufrieden sind und Sie diese Suchergebnisse überprüfen und analysieren möchten, können Sie Sie zu einem Überprüfungs in dem Fall hinzufügen. Durch das Kopieren der ursprünglichen Daten in den Überprüfungs wird auch der Überprüfungs-und Analyseprozess erleichtert, indem Ihnen erweiterte Analysetools bereitgestellt werden, beispielsweise die Erkennung von Designs, die Erkennung praktischer Duplikate und die e-Mail-Threadidentifikation. Sie können auch Daten aus nicht-Microsoft 365-Datenquellen zu einem Überprüfungs Satz hinzufügen, damit Sie diese Daten zusätzlich zu den von Microsoft 365 erfassten Daten überprüfen können.

Wenn Sie die Ergebnisse einer Suche zu einem Überprüfungs Satz hinzufügen (die Überprüfungs Sätze werden in einem Fall auf der Registerkarte **Überprüfungs Sätze** aufgeführt), treten die folgenden Dinge auf:

- Die Suche wird erneut ausgeführt. Dies bedeutet, dass die tatsächlichen Suchergebnisse, die in den Überprüfungs Satzes kopiert wurden, sich möglicherweise von den geschätzten Ergebnissen unterscheiden, die bei der letzten Ausführung der Suche zurückgegeben wurden.

- Alle Elemente in den Suchergebnissen werden aus der ursprünglichen Datenquelle in den Live-Diensten kopiert und in einen sicheren Azure-Speicherort in der Microsoft-Cloud kopiert.

- Alle Elemente (einschließlich der Inhalte und Metadaten) werden neu indiziert, sodass alle Daten in der Überprüfungsgruppe während der Überprüfung der Falldaten vollständig durchsuchbar sind. Durch das Neuindizieren der Daten werden gründliche und schnelle Suchvorgänge durchsucht, wenn Sie die Daten im Überprüfungs Satzes während der Fall Ermittlung durchsuchen.

- Eine mit einer Microsoft- [Verschlüsselungstechnologie](encryption.md) verschlüsselte Datei, die an eine e-Mail-Nachricht angehängt wird, die in den Suchergebnissen zurückgegeben wird, wird entschlüsselt, wenn die e-Mail-Nachricht und die angefügte Datei dem Überprüfungs-Ordner hinzu Sie können die entschlüsselte Datei im Überprüfungs Satzes überprüfen und Abfragen. Sie müssen die RMS-Entschlüsselungs Rolle zugewiesen haben, um einem Überprüfungs Satz entschlüsselte e-Mail-Anlagen hinzuzufügen. Weitere Informationen finden Sie unter [Entschlüsselung in Microsoft 365 eDiscovery Tools](ediscovery-decryption.md).

Klicken Sie zum Hinzufügen von Daten zu einem Überprüfungs Satzes auf der Registerkarte **Suchen** auf eine Suche, und klicken Sie dann auf der Flyout-Seite auf **zu überprüfende Ergebnisse hinzufügen** .

Sie können zu einer vorhandenen Überprüfungsgruppe hinzufügen oder einen neuen Überprüfungs erstellen.  Wenn Sie zu einem neuen Überprüfungs Satzes hinzufügen, geben Sie den Namen an, und klicken Sie dann auf **Hinzufügen** , um die Flyout-Seite anzuzeigen.

![Auswählen eines Überprüfungs Satzes und Konfigurieren von Sammlungsoptionen](../media/AeD_AddToReviewSet.png)

Das Hinzufügen von Daten zu einem Prüfdateisatz ist ein langwieriger Prozess. Dieser Prozess umfasst das Sammeln von Elementen aus den ursprünglichen Datenquellen in Microsoft 365 (beispielsweise aus Postfächern und Websites), das Kopieren dieser Elemente in den Azure-Speicherort (dieser Kopiervorgang wird auch als *Einnahme* bezeichnet) und anschließendes Neuindizieren der Elemente. Sie können den Fortschritt auf der Registerkarte **Aufträge** oder auf der Registerkarte **Suchen** überwachen, indem Sie den Status in der Spalte **hinzugefügte Daten zum Überprüfen des Satzes über** wachen. Klicken Sie nach Abschluss der Überarbeitungs Satzverarbeitung in der Anfrage auf die Registerkarte Überprüfungs **Sätze** , und klicken Sie dann auf den Überprüfungs Satz, um das Filtern, überprüfen, markieren und Exportieren von Daten in der Überprüfungsgruppe zu starten.

## <a name="define-options-to-scope-your-collection-for-review"></a>Definieren von Optionen zum Bereich Ihrer Sammlung zur Überprüfung

Wenn Sie den Inhalt einer Suche einem vorhandenen oder neuen Überprüfungs Sätzen hinzufügen, haben Sie die folgenden Optionen zum Erfassen der Inhalte zur Überprüfung:

- **Versionen von SharePoint einbeziehen (Beta)** : Verwenden Sie diese Option, um die Sammlung aller Versionen eines SharePoint-Dokuments pro Versions Limits und Suchparametern der Auflistung zu aktivieren. Durch Auswahl dieser Option wird die Größe der Elemente, die dem Überprüfungs Satzes hinzugefügt werden, erheblich erhöht.

- **Unterhaltungs Abrufoptionen** : Elemente, die dem Überprüfungs Satzes hinzugefügt wurden, sind für Thread gestützte Unterhaltungen aktiviert, um Inhalte im Kontext der hin-und her-Unterhaltung zu überprüfen. Weitere Informationen finden Sie unter [Review Conversations in Advanced eDiscovery](conversation-review-sets.md).

- **Abruf für moderne Anlagen aktivieren** : Verwenden Sie diese Option, um moderne Anlagen oder verknüpfte Dateien in die Sammlung zur weiteren Überprüfung einzubeziehen. Weitere Informationen zu den durchsuchbaren Eigenschaften im Zusammenhang mit modernen Anlagen finden Sie unter [Document Metadata fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).

## <a name="add-a-sample-to-a-review-set"></a>Hinzufügen eines Beispiels zu einem Überprüfungs Satzes

Wenn Sie die Ergebnisse einer Suche gründlicher überprüfen möchten, bevor Sie Sie einer Überprüfungsgruppe hinzufügen, können Sie ein Beispiel der Suchergebnisse zu einer Überprüfungsgruppe hinzufügen, anstatt alles hinzuzufügen.

Wenn Sie einem Überprüfungs Satzes ein Beispiel hinzufügen möchten, klicken Sie auf der Registerkarte **Suchen** auf eine Suche, und klicken Sie auf der Flyout-Seite auf **Sample** . Wählen Sie auf der Seite **Stichproben Parameter** eine der folgenden Optionen aus:

- **Konfidenz Stufe%** und **Konfidenzintervall%** – die der Überprüfungsgruppe hinzugefügten Elemente werden durch die von Ihnen festgelegten statistischen Parameter bestimmt. Wenn Sie normalerweise bei Sampling-Ergebnissen eine Konfidenz Stufe und ein Intervall verwenden, geben Sie diese in den Dropdownfeldern an. Verwenden Sie andernfalls die Standardeinstellungen.

- **Zufalls Beispiel%** – die Elemente, die dem Überprüfungs Satz hinzugefügt wurden, basieren auf einer zufälligen Auswahl des angegebenen Prozentsatzes der Gesamtzahl der Elemente, die von der Suche zurückgegeben wurden.

Nachdem Sie eine der vorherigen Optionen ausgewählt und konfiguriert haben, wählen Sie eine Überprüfungsgruppe aus, der Sie das Beispiel hinzufügen möchten, und klicken Sie dann auf **senden**. Sie können den Fortschritt auch wieder auf der Registerkarte **Aufträge** oder auf der Registerkarte **Suchen** verfolgen, indem Sie den Status in der Spalte **hinzugefügte Daten zum Überprüfen des Satzes über** wachen.

## <a name="optical-character-recognition"></a>Optical Character Recognition (optische Zeichenerkennung)

Wenn Sie Suchergebnisse zu einem Überprüfungs Satz hinzufügen, extrahiert die OCR-Funktion (Optical Character Recognition) in Advanced eDiscovery automatisch Text aus Bildern und enthält den Bildtext mit den Daten, die einem Überprüfungs Satz hinzugefügt wurden. Sie können den extrahierten Text im Text Betrachter der ausgewählten Bilddatei im überprüfungsordner anzeigen. Auf diese Weise können Sie den Text in Bildern genauer überprüfen und analysieren. OCR wird für lose Dateien, E-Mail-Anlagen und eingebettete Bilder unterstützt. Eine Liste der Bilddateiformate, für die OCR unterstützt wird, finden Sie unter [Unterstützte Dateitypen in Advanced eDiscovery](supported-filetypes-ediscovery20.md#image).

Sie müssen die OCR-Funktion für jeden Fall aktivieren, den Sie in Advanced eDiscovery erstellen. Weitere Informationen finden Sie unter [Configure Search and Analytics Settings](configure-search-and-analytics-settings-in-advanced-ediscovery.md#optical-character-recognition-ocr).
