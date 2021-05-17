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
# <a name="single-item-error-remediation-in-advanced-ediscovery"></a><span data-ttu-id="08dd9-103">Behebung einzelner Elemente in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="08dd9-103">Single item error remediation in Advanced eDiscovery</span></span>

<span data-ttu-id="08dd9-104">Die Fehlerbehebung Advanced eDiscovery Benutzern die Möglichkeit, Datenprobleme zu beheben, die verhindern, dass Advanced eDiscovery Inhalte ordnungsgemäß verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="08dd9-104">Error remediation gives Advanced eDiscovery users the ability to rectify data issues that prevent Advanced eDiscovery from properly processing the content.</span></span> <span data-ttu-id="08dd9-105">Beispielsweise können kennwortgeschützte Dateien nicht verarbeitet werden, da diese Dateien gesperrt oder verschlüsselt sind.</span><span class="sxs-lookup"><span data-stu-id="08dd9-105">For example, files that are password protected can't be processed because those files are locked or encrypted.</span></span> <span data-ttu-id="08dd9-106">Bisher konnten Sie Fehler nur in Massen beheben, indem Sie diesen [Workflow verwenden.](error-remediation-when-processing-data-in-advanced-ediscovery.md)</span><span class="sxs-lookup"><span data-stu-id="08dd9-106">Previously, you could only remediate errors in bulk by using [this workflow](error-remediation-when-processing-data-in-advanced-ediscovery.md).</span></span> <span data-ttu-id="08dd9-107">Manchmal ist es jedoch nicht sinnvoll, Fehler in mehreren Dateien zu beheben, wenn Sie nicht sicher sind, ob eine dieser Dateien auf den fall reagiert, den Sie untersuchen.</span><span class="sxs-lookup"><span data-stu-id="08dd9-107">But sometimes, it doesn't make sense to remediate errors in multiple files when you’re unsure if any of those files are responsive to the case you’re investigating.</span></span> <span data-ttu-id="08dd9-108">Es ist möglicherweise auch nicht sinnvoll, Fehler zu beheben, bevor Sie die Dateimetadaten (z. B. Dateispeicherort oder Zugriff) überprüfen können, um Ihnen bei der Entscheidung über die Reaktionsfähigkeit zu helfen.</span><span class="sxs-lookup"><span data-stu-id="08dd9-108">It also might not make sense to remediate errors before you’ve had a chance to review the file metadata (such as file location or who had access) to help you make up-front decisions about responsiveness.</span></span> <span data-ttu-id="08dd9-109">Ein neues  Feature, das als Fehlerbehebung für einzelne Elemente bezeichnet wird, ermöglicht eDiscovery-Managern, die Metadaten von Dateien mit einem Verarbeitungsfehler zu sehen und den Fehler gegebenenfalls direkt im Überprüfungssatz zu beheben.</span><span class="sxs-lookup"><span data-stu-id="08dd9-109">A new feature called *single item error remediation* gives eDiscovery managers the ability to view the metadata of files with a processing error and if necessary remediate the error directly in the review set.</span></span> <span data-ttu-id="08dd9-110">In diesem Artikel wird erläutert, wie Dateien mit Verarbeitungsfehlern in einem Überprüfungssatz identifiziert, ignoriert und behoben werden.</span><span class="sxs-lookup"><span data-stu-id="08dd9-110">The article discusses how to identify, ignore, and remediate files with processing errors in a review set.</span></span>

## <a name="identify-documents-with-errors"></a><span data-ttu-id="08dd9-111">Identifizieren von Dokumenten mit Fehlern</span><span class="sxs-lookup"><span data-stu-id="08dd9-111">Identify documents with errors</span></span>

<span data-ttu-id="08dd9-112">Dokumente mit Verarbeitungsfehlern in einem Überprüfungssatz werden jetzt identifiziert (mit einem Banner).</span><span class="sxs-lookup"><span data-stu-id="08dd9-112">Documents with processing errors in a review set are now identified (with a banner).</span></span> <span data-ttu-id="08dd9-113">Sie können den Fehler beheben oder ignorieren.</span><span class="sxs-lookup"><span data-stu-id="08dd9-113">You can remediate or ignore the error.</span></span> <span data-ttu-id="08dd9-114">Der folgende Screenshot zeigt das Verarbeitungsfehlerbanner für ein Word-Dokument in einem kennwortgeschützten Überprüfungssatz.</span><span class="sxs-lookup"><span data-stu-id="08dd9-114">The following screenshot shows the processing error banner for a Word document in a review set that is password-protected.</span></span> <span data-ttu-id="08dd9-115">Beachten Sie außerdem, dass Sie die Dateimetadaten von Dokumenten mit Verarbeitungsfehlern anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="08dd9-115">Also notice that you can view the file metadata of documents with processing errors.</span></span>

![Banner für Dokument mit Verarbeitungsfehler angezeigt](../media/SIERimage1.png)

<span data-ttu-id="08dd9-117">Sie können auch nach Dokumenten mit Verarbeitungsfehlern suchen, indem Sie die **Statusbedingung Processing** verwenden, wenn Sie die Dokumente [in einem Überprüfungssatz abfragen.](review-set-search.md)</span><span class="sxs-lookup"><span data-stu-id="08dd9-117">You can also search for documents that have processing errors by using the **Processing status** condition when [querying the documents in a review set](review-set-search.md).</span></span>

![Verwenden der Statusbedingung "Verarbeitung", um nach Fehlerdokumenten zu suchen](../media/SIERimage2.png)

### <a name="ignore-errors"></a><span data-ttu-id="08dd9-119">Fehler ignorieren</span><span class="sxs-lookup"><span data-stu-id="08dd9-119">Ignore errors</span></span>

<span data-ttu-id="08dd9-120">Sie können einen Verarbeitungsfehler ignorieren, indem Sie im Verarbeitungsfehlerbanner auf **Ignorieren** klicken.</span><span class="sxs-lookup"><span data-stu-id="08dd9-120">You can ignore a processing error by clicking **Ignore** in the processing error banner.</span></span> <span data-ttu-id="08dd9-121">Wenn Sie einen Fehler ignorieren, wird das Dokument aus dem [Massenfehlerbehebungsworkflow entfernt.](error-remediation-when-processing-data-in-advanced-ediscovery.md)</span><span class="sxs-lookup"><span data-stu-id="08dd9-121">When you ignore an error, the document is removed from the [bulk error remediation workflow](error-remediation-when-processing-data-in-advanced-ediscovery.md).</span></span> <span data-ttu-id="08dd9-122">Nachdem ein Fehler ignoriert wurde, ändert das Dokumentbanner die Farbe und gibt an, dass der Verarbeitungsfehler ignoriert wurde.</span><span class="sxs-lookup"><span data-stu-id="08dd9-122">After an error is ignored, the document banner changes color and indicates that the processing error was ignored.</span></span> <span data-ttu-id="08dd9-123">Sie können jederzeit die Entscheidung rückgängig machen, um den Fehler zu ignorieren, indem Sie auf **Wiederherstellen klicken.**</span><span class="sxs-lookup"><span data-stu-id="08dd9-123">At any time, you can revert the decision to ignore the error by clicking **Revert**.</span></span>

![Klicken Sie auf Ignorieren, um den Verarbeitungsfehler zu ignorieren.](../media/SIERimage3.png)

<span data-ttu-id="08dd9-125">Sie können auch nach allen Dokumenten suchen, bei denen ein Verarbeitungsfehler aufgetreten ist, der ignoriert wurde, indem Sie die Bedingung *Ignorierte* Verarbeitungsfehler beim Abfragen von Dokumenten in einem Überprüfungssatz verwenden.</span><span class="sxs-lookup"><span data-stu-id="08dd9-125">You can also search for all documents that had a processing error that was ignored by using the *Ignored processing errors* condition when querying documents in a review set.</span></span>

![Verwenden der Bedingung Ignorierte Verarbeitungsfehler zum Suchen nach ignorierten Fehlerdokumenten](../media/SIERimage4.png)

## <a name="remediate-a-document-with-errors"></a><span data-ttu-id="08dd9-127">Korrigieren eines Dokuments mit Fehlern</span><span class="sxs-lookup"><span data-stu-id="08dd9-127">Remediate a document with errors</span></span>

<span data-ttu-id="08dd9-128">Manchmal müssen Sie möglicherweise einen Verarbeitungsfehler in Dokumenten beheben (indem Sie ein Kennwort entfernen, eine verschlüsselte Datei entschlüsseln oder ein beschädigtes Dokument wiederherstellen) und dann das behobene Dokument dem Überprüfungssatz hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="08dd9-128">Sometimes you may be required to remediate a processing error in documents (by removing a password, decrypting an encrypted file, or recovering a corrupted document) and then add the remediated document to the review set.</span></span> <span data-ttu-id="08dd9-129">Auf diese Weise können Sie das Fehlerdokument zusammen mit den anderen Dokumenten im Überprüfungssatz überprüfen und exportieren.</span><span class="sxs-lookup"><span data-stu-id="08dd9-129">This allows you to review and export the error document together with the other documents in the review set.</span></span> 

<span data-ttu-id="08dd9-130">Führen Sie die folgenden Schritte aus, um ein einzelnes Dokument zu sanieren:</span><span class="sxs-lookup"><span data-stu-id="08dd9-130">To remediate a single document, follow these steps:</span></span>

1. <span data-ttu-id="08dd9-131">Klicken **Sie auf Original** herunterladen, um eine Kopie der Datei auf einen lokalen Computer  >   herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="08dd9-131">Click **Download** > **Download original** to download a copy of the file to a local computer.</span></span>

   ![Herunterladen des Dokuments mit dem Verarbeitungsfehler](../media/SIERimage5.png)

2. <span data-ttu-id="08dd9-133">Beheben Sie den Fehler in der Datei offline.</span><span class="sxs-lookup"><span data-stu-id="08dd9-133">Remediate the error in the file offline.</span></span> <span data-ttu-id="08dd9-134">Für verschlüsselte Dateien, die Entschlüsselungssoftware erfordern würden, um den Kennwortschutz zu entfernen, geben Sie entweder das Kennwort an, und speichern Sie die Datei, oder verwenden Sie einen Kennwortknacker.</span><span class="sxs-lookup"><span data-stu-id="08dd9-134">For encrypted files, that would require decryption software, to remove password protection, either provide the password and save the file or use a password cracker.</span></span> <span data-ttu-id="08dd9-135">Nachdem Sie die Datei behoben haben, fahren Sie mit dem nächsten Schritt fort.</span><span class="sxs-lookup"><span data-stu-id="08dd9-135">After you remediate the file, go to the next step.</span></span>

3. <span data-ttu-id="08dd9-136">Wählen Sie im Überprüfungssatz die Datei mit dem von Ihnen behobenen Verarbeitungsfehler aus, und klicken Sie dann auf **Beheben**.</span><span class="sxs-lookup"><span data-stu-id="08dd9-136">In the review set, select the file with the processing error that you remediated, and then  click **Remediation**.</span></span>

   ![Klicken Sie im Banner des Dokuments mit Einem Verarbeitungsfehler auf Korrektur](../media/SIERimage6.png)


4. <span data-ttu-id="08dd9-138">Klicken **Sie auf Durchsuchen,** wechseln Sie zum Speicherort der behobenen Datei auf dem lokalen Computer, und wählen Sie dann die Datei aus.</span><span class="sxs-lookup"><span data-stu-id="08dd9-138">Click **Browse**, go to the location of the remediated file on your local computer, and then select the file.</span></span>

   ![Klicken Sie auf Durchsuchen, und wählen Sie die behobene Datei auf Dem lokalen Computer aus.](../media/SIERimage7.png)

    <span data-ttu-id="08dd9-140">Nachdem Sie die gelöschte Datei ausgewählt haben, wird sie automatisch in den Überprüfungssatz hochgeladen.</span><span class="sxs-lookup"><span data-stu-id="08dd9-140">After selecting the remediated file, it is automatically uploaded to the review set.</span></span> <span data-ttu-id="08dd9-141">Sie können den Verarbeitungsstatus der Datei nachverfolgen.</span><span class="sxs-lookup"><span data-stu-id="08dd9-141">You can track the processing status of the file.</span></span>

    ![Der Status des Korrekturvorgangs wird angezeigt.](../media/SIERimage8.png)

   <span data-ttu-id="08dd9-143">Nach Abschluss der Verarbeitung können Sie das behobene Dokument anzeigen.</span><span class="sxs-lookup"><span data-stu-id="08dd9-143">After processing is completed, you can view the remediated document.</span></span>

    ![Sie können die behobene Datei im systemeigenen Format im Überprüfungssatz anzeigen.](../media/SIERimage9.png)

<span data-ttu-id="08dd9-145">Weitere Informationen dazu, was geschieht, wenn ein Dokument behoben wird, finden Sie unter Was geschieht, wenn Dateien [behoben werden.](error-remediation-when-processing-data-in-advanced-ediscovery.md#what-happens-when-files-are-remediated)</span><span class="sxs-lookup"><span data-stu-id="08dd9-145">For more information about what happens when a document is remediated, see [What happens when files are remediated](error-remediation-when-processing-data-in-advanced-ediscovery.md#what-happens-when-files-are-remediated).</span></span>

## <a name="search-for-remediated-documents"></a><span data-ttu-id="08dd9-146">Suchen nach behobenen Dokumenten</span><span class="sxs-lookup"><span data-stu-id="08dd9-146">Search for remediated documents</span></span>

<span data-ttu-id="08dd9-147">Sie können nach allen Dokumenten in einem Überprüfungssatz suchen, die mithilfe der **Keywords-Bedingung** behoben wurden, und das folgende Property:Value-Paar angeben: **IsFromErrorRemediation:true**.</span><span class="sxs-lookup"><span data-stu-id="08dd9-147">You can search for all documents in a review set that were remediated by using the **Keywords** condition and specifying the following property:value pair: **IsFromErrorRemediation:true**.</span></span> <span data-ttu-id="08dd9-148">Diese Eigenschaft ist auch in der Exportladedatei verfügbar, wenn Sie Dokumente aus einem Überprüfungssatz exportieren.</span><span class="sxs-lookup"><span data-stu-id="08dd9-148">This property is also available in the export load file when you export documents from a review set.</span></span>
