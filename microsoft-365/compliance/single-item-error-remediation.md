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
description: Sie können einen Verarbeitungsfehler in einem Dokument in einem Überprüfungssatz in Advanced eDiscovery, ohne den Massenfehlerbehebungsprozess befolgen zu müssen.
ms.openlocfilehash: 8e5d8d00f507dc5792a1beda018d4c76632b82f7
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/05/2021
ms.locfileid: "49751582"
---
# <a name="single-item-error-remediation-in-advanced-ediscovery"></a>Behebung einzelner Elemente in Advanced eDiscovery

Die Fehlerbehebung Advanced eDiscovery Benutzern die Möglichkeit, Datenprobleme zu beheben, die verhindern, dass Advanced eDiscovery Inhalte ordnungsgemäß verarbeiten. Beispielsweise können kennwortgeschützte Dateien nicht verarbeitet werden, da diese Dateien gesperrt oder verschlüsselt sind. Bisher konnten Sie Fehler nur in Massen beheben, indem Sie diesen [Workflow verwenden.](error-remediation-when-processing-data-in-advanced-ediscovery.md) Manchmal ist es jedoch nicht sinnvoll, Fehler in mehreren Dateien zu beheben, wenn Sie nicht sicher sind, ob eine dieser Dateien auf den fall reagiert, den Sie untersuchen. Es ist möglicherweise auch nicht sinnvoll, Fehler zu beheben, bevor Sie die Dateimetadaten (z. B. Dateispeicherort oder Zugriff) überprüfen können, um Ihnen bei der Entscheidung über die Reaktionsfähigkeit zu helfen. Ein neues  Feature, das als Fehlerbehebung für einzelne Elemente bezeichnet wird, ermöglicht eDiscovery-Managern, die Metadaten von Dateien mit einem Verarbeitungsfehler zu sehen und den Fehler gegebenenfalls direkt im Überprüfungssatz zu beheben. In diesem Artikel wird erläutert, wie Dateien mit Verarbeitungsfehlern in einem Überprüfungssatz identifiziert, ignoriert und behoben werden.

## <a name="identify-documents-with-errors"></a>Identifizieren von Dokumenten mit Fehlern

Dokumente mit Verarbeitungsfehlern in einem Überprüfungssatz werden jetzt identifiziert (mit einem Banner). Sie können den Fehler beheben oder ignorieren. Der folgende Screenshot zeigt das Verarbeitungsfehlerbanner für ein Word-Dokument in einem kennwortgeschützten Überprüfungssatz. Beachten Sie außerdem, dass Sie die Dateimetadaten von Dokumenten mit Verarbeitungsfehlern anzeigen können.

![Banner für Dokument mit Verarbeitungsfehler angezeigt](../media/SIERimage1.png)

Sie können auch nach Dokumenten mit Verarbeitungsfehlern suchen, indem Sie die **Statusbedingung Processing** verwenden, wenn Sie die Dokumente [in einem Überprüfungssatz abfragen.](review-set-search.md)

![Verwenden der Statusbedingung "Verarbeitung", um nach Fehlerdokumenten zu suchen](../media/SIERimage2.png)

### <a name="ignore-errors"></a>Fehler ignorieren

Sie können einen Verarbeitungsfehler ignorieren, indem Sie im Verarbeitungsfehlerbanner auf **Ignorieren** klicken. Wenn Sie einen Fehler ignorieren, wird das Dokument aus dem [Massenfehlerbehebungsworkflow entfernt.](error-remediation-when-processing-data-in-advanced-ediscovery.md) Nachdem ein Fehler ignoriert wurde, ändert das Dokumentbanner die Farbe und gibt an, dass der Verarbeitungsfehler ignoriert wurde. Sie können jederzeit die Entscheidung rückgängig machen, um den Fehler zu ignorieren, indem Sie auf **Wiederherstellen klicken.**

![Klicken Sie auf Ignorieren, um den Verarbeitungsfehler zu ignorieren.](../media/SIERimage3.png)

Sie können auch nach allen Dokumenten suchen, bei denen ein Verarbeitungsfehler aufgetreten ist, der ignoriert wurde, indem Sie die Bedingung *Ignorierte* Verarbeitungsfehler beim Abfragen von Dokumenten in einem Überprüfungssatz verwenden.

![Verwenden der Bedingung Ignorierte Verarbeitungsfehler zum Suchen nach ignorierten Fehlerdokumenten](../media/SIERimage4.png)

## <a name="remediate-a-document-with-errors"></a>Korrigieren eines Dokuments mit Fehlern

Manchmal müssen Sie möglicherweise einen Verarbeitungsfehler in Dokumenten beheben (indem Sie ein Kennwort entfernen, eine verschlüsselte Datei entschlüsseln oder ein beschädigtes Dokument wiederherstellen) und dann das behobene Dokument dem Überprüfungssatz hinzufügen. Auf diese Weise können Sie das Fehlerdokument zusammen mit den anderen Dokumenten im Überprüfungssatz überprüfen und exportieren. 

Führen Sie die folgenden Schritte aus, um ein einzelnes Dokument zu sanieren:

1. Klicken **Sie auf Original** herunterladen, um eine Kopie der Datei auf einen lokalen Computer  >   herunterzuladen.

   ![Herunterladen des Dokuments mit dem Verarbeitungsfehler](../media/SIERimage5.png)

2. Beheben Sie den Fehler in der Datei offline. Für verschlüsselte Dateien, die Entschlüsselungssoftware erfordern würden, um den Kennwortschutz zu entfernen, geben Sie entweder das Kennwort an, und speichern Sie die Datei, oder verwenden Sie einen Kennwortknacker. Nachdem Sie die Datei behoben haben, fahren Sie mit dem nächsten Schritt fort.

3. Wählen Sie im Überprüfungssatz die Datei mit dem von Ihnen behobenen Verarbeitungsfehler aus, und klicken Sie dann auf **Beheben**.

   ![Klicken Sie im Banner des Dokuments mit Einem Verarbeitungsfehler auf Korrektur](../media/SIERimage6.png)


4. Klicken **Sie auf Durchsuchen,** wechseln Sie zum Speicherort der behobenen Datei auf dem lokalen Computer, und wählen Sie dann die Datei aus.

   ![Klicken Sie auf Durchsuchen, und wählen Sie die behobene Datei auf Dem lokalen Computer aus.](../media/SIERimage7.png)

    Nachdem Sie die gelöschte Datei ausgewählt haben, wird sie automatisch in den Überprüfungssatz hochgeladen. Sie können den Verarbeitungsstatus der Datei nachverfolgen.

    ![Der Status des Korrekturvorgangs wird angezeigt.](../media/SIERimage8.png)

   Nach Abschluss der Verarbeitung können Sie das behobene Dokument anzeigen.

    ![Sie können die behobene Datei im systemeigenen Format im Überprüfungssatz anzeigen.](../media/SIERimage9.png)

Weitere Informationen dazu, was geschieht, wenn ein Dokument behoben wird, finden Sie unter Was geschieht, wenn Dateien [behoben werden.](error-remediation-when-processing-data-in-advanced-ediscovery.md#what-happens-when-files-are-remediated)

## <a name="search-for-remediated-documents"></a>Suchen nach behobenen Dokumenten

Sie können nach allen Dokumenten in einem Überprüfungssatz suchen, die mithilfe der **Keywords-Bedingung** behoben wurden, und das folgende Property:Value-Paar angeben: **IsFromErrorRemediation:true**. Diese Eigenschaft ist auch in der Exportladedatei verfügbar, wenn Sie Dokumente aus einem Überprüfungssatz exportieren.
