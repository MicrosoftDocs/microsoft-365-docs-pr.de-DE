---
title: Korrektur von Fehlern einzelner Elemente
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
description: Sie können einen Verarbeitungsfehler in einem Dokument in einer Überprüfungsgruppe in Advanced eDiscovery beheben, ohne den Prozess der Massen Fehlerkorrektur durchführen zu müssen.
ms.openlocfilehash: c049ce4b5d3f8fc12a015a61ea927b744ae76eb3
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41601492"
---
# <a name="single-item-error-remediation"></a>Korrektur von Fehlern einzelner Elemente

Durch die Fehlerkorrektur können erweiterte eDiscovery-Benutzerdaten Probleme beheben, durch die verhindert wird, dass Advanced eDiscovery die Inhalte ordnungsgemäß verarbeitet. Beispielsweise können Dateien, die kennwortgeschützt sind, nicht verarbeitet werden, da diese Dateien gesperrt oder verschlüsselt sind. Zuvor konnten Sie Fehler in Massen mithilfe [dieses Workflows](error-remediation-when-processing-data-in-advanced-ediscovery.md)nur beheben. Manchmal ist es jedoch nicht sinnvoll, Fehler in mehreren Dateien zu beheben, wenn Sie sich nicht sicher sind, ob eine dieser Dateien auf den Fall reagiert, den Sie untersuchen. Es ist auch möglicherweise nicht sinnvoll, Fehler zu beheben, bevor Sie die Datei Metadaten (beispielsweise den Dateispeicherort oder die Zugriffsberechtigung) überprüfen konnten, damit Sie Vorabentscheidungen zur Reaktionsfähigkeit treffen können. Ein neues Feature namens " *Single Item Error Remediation* " gibt eDiscovery-Managern die Möglichkeit, die Metadaten von Dateien mit einem Verarbeitungsfehler anzuzeigen und den Fehler bei Bedarf direkt in der Überprüfungsgruppe zu beheben. In diesem Artikel wird erläutert, wie Sie Dateien mit Verarbeitungsfehlern in einem Überprüfungs Satz identifizieren, ignorieren und korrigieren.

## <a name="identify-documents-with-errors"></a>Identifizieren von Dokumenten mit Fehlern

Dokumente mit Verarbeitungsfehlern in einem Überprüfungs Satz werden nun identifiziert (mit einem Banner). Sie können den Fehler korrigieren oder ignorieren. Der folgende Screenshot zeigt das Fehler Banner Verarbeitung für ein Word-Dokument in einem Überprüfungs Sätze, die kennwortgeschützt sind. Beachten Sie außerdem, dass Sie die Datei Metadaten von Dokumenten mit Verarbeitungsfehlern anzeigen können.

![Für Dokument mit Verarbeitungsfehler angezeigtes Banner](media/SIERimage1.png)

Sie können auch nach Dokumenten mit Verarbeitungsfehlern suchen, indem Sie die **Verarbeitungsstatus** Bedingung beim [Abfragen der Dokumente in einem Überprüfungs Satz](review-set-search.md)verwenden.

![Verwenden der Bedingung "Verarbeitungsstatus" zum Suchen nach Fehler Dokumenten](media/SIERimage2.png)

### <a name="ignore-errors"></a>Fehler ignorieren

Sie können einen Verarbeitungsfehler ignorieren, indem Sie im Fehler Banner Verarbeitung auf **ignorieren** klicken. Wenn Sie einen Fehler ignorieren, wird das Dokument aus dem [Fehler Behebungs Workflow des Massen Fehlers](error-remediation-when-processing-data-in-advanced-ediscovery.md)entfernt. Nachdem ein Fehler ignoriert wurde, ändert sich die Farbe des Dokument Banners und gibt an, dass der Verarbeitungsfehler ignoriert wurde. Sie können die Entscheidung, den Fehler zu ignorieren, jederzeit rückgängig machen, indem Sie auf **Rückgängig**klicken.

![Klicken Sie auf ignorieren, um den Verarbeitungsfehler zu ignorieren](media/SIERimage3.png)

Sie können auch nach allen Dokumenten suchen, bei denen ein Verarbeitungsfehler aufgetreten ist, der bei der Abfrage von Dokumenten in einem Überprüfungs Satz mit der Bedingung *ignorierte Verarbeitungsfehler* ignoriert wurde.

![Verwenden der Bedingung ignorierte Verarbeitungsfehler zum Suchen nach ignorierten Fehler Dokumenten](media/SIERimage4.png)

## <a name="remediate-a-document-with-errors"></a>Korrigieren eines Dokuments mit Fehlern

In einigen Fällen müssen Sie möglicherweise einen Verarbeitungsfehler in Dokumenten korrigieren (durch Entfernen eines Kennworts, Entschlüsseln einer verschlüsselten Datei oder Wiederherstellung eines beschädigten Dokuments) und dann das korrigierte Dokument dem Überprüfungs-Datensatz hinzufügen. Auf diese Weise können Sie das Fehlerdokument zusammen mit den anderen Dokumenten in der Überprüfungsgruppe überprüfen und exportieren. 

Führen Sie die folgenden Schritte aus, um ein einzelnes Dokument zu korrigieren:

1. Klicken Sie auf Download**Original** herunterladen, um eine Kopie der Datei auf einen lokalen Computer herunterzuladen. **** > 

   ![Herunterladen des Dokuments mit dem Verarbeitungsfehler](media/SIERimage5.png)

2. Beheben Sie den Fehler in der Datei offline. Für verschlüsselte Dateien, für die eine Entschlüsselungssoftware erforderlich ist, müssen Sie entweder das Kennwort angeben und die Datei speichern oder einen Kennwortcracker verwenden, um den Kennwortschutz zu entfernen. Nachdem Sie die Datei behoben haben, fahren Sie mit dem nächsten Schritt fort.

3. Wählen Sie in der Überprüfungsgruppe die Datei mit dem Verarbeitungsfehler aus, den Sie behoben haben, und klicken Sie dann auf **Korrektur**.

   ![Klicken Sie auf Korrektur im Banner des Dokuments mit Verarbeitungsfehler](media/SIERimage6.png)


4. Klicken Sie auf **Durchsuchen**, wechseln Sie zum Speicherort der korrigierten Datei auf Ihrem lokalen Computer, und wählen Sie dann die Datei aus.

   ![Klicken Sie auf Durchsuchen, und wählen Sie die Datei auf Ihrem lokalen Computer aus.](media/SIERimage7.png)

    Nachdem Sie die korrigierte Datei ausgewählt haben, wird Sie automatisch in den Überprüfungs-Datensatz hochgeladen. Sie können den Verarbeitungsstatus der Datei nachverfolgen.

    ![Der Status des Korrekturprozesses wird angezeigt.](media/SIERimage8.png)

   Nach Abschluss der Verarbeitung können Sie das korrigierte Dokument anzeigen.

    ![Sie können die korrigierte Datei im systemeigenen Format des Überprüfungs Satzes anzeigen.](media/SIERimage9.png)

Weitere Informationen dazu, was geschieht, wenn ein Dokument korrigiert wird, finden Sie unter [Was geschieht, wenn Dateien behoben werden](error-remediation.md#what-happens-when-files-are-remediated).

## <a name="search-for-remediated-documents"></a>Suchen nach korrigierten Dokumenten

Sie können nach allen Dokumenten in einem Überprüfungs Satzes suchen, die mithilfe der Bedingung **Schlüsselwörter** korrigiert wurden, und die folgende Eigenschaft: Wert Paar: **IsFromErrorRemediation: true**angeben. Diese Eigenschaft steht auch in der Exportdatei zum Exportieren zur Verfügung, wenn Sie Dokumente aus einem Überprüfungs Sätzen exportieren.
