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
ms.openlocfilehash: 8e5d8d00f507dc5792a1beda018d4c76632b82f7
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/05/2021
ms.locfileid: "49751582"
---
# <a name="single-item-error-remediation-in-advanced-ediscovery"></a><span data-ttu-id="7be7d-103">Fehlerbehebung einzelner Elemente in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="7be7d-103">Single item error remediation in Advanced eDiscovery</span></span>

<span data-ttu-id="7be7d-104">Durch die Fehlerkorrektur können erweiterte eDiscovery-Benutzerdaten Probleme beheben, durch die verhindert wird, dass Advanced eDiscovery die Inhalte ordnungsgemäß verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="7be7d-104">Error remediation gives Advanced eDiscovery users the ability to rectify data issues that prevent Advanced eDiscovery from properly processing the content.</span></span> <span data-ttu-id="7be7d-105">Beispielsweise können Dateien, die kennwortgeschützt sind, nicht verarbeitet werden, da diese Dateien gesperrt oder verschlüsselt sind.</span><span class="sxs-lookup"><span data-stu-id="7be7d-105">For example, files that are password protected can't be processed because those files are locked or encrypted.</span></span> <span data-ttu-id="7be7d-106">Zuvor konnten Sie Fehler in Massen mithilfe [dieses Workflows](error-remediation-when-processing-data-in-advanced-ediscovery.md)nur beheben.</span><span class="sxs-lookup"><span data-stu-id="7be7d-106">Previously, you could only remediate errors in bulk by using [this workflow](error-remediation-when-processing-data-in-advanced-ediscovery.md).</span></span> <span data-ttu-id="7be7d-107">Manchmal ist es jedoch nicht sinnvoll, Fehler in mehreren Dateien zu beheben, wenn Sie sich nicht sicher sind, ob eine dieser Dateien auf den Fall reagiert, den Sie untersuchen.</span><span class="sxs-lookup"><span data-stu-id="7be7d-107">But sometimes, it doesn't make sense to remediate errors in multiple files when you’re unsure if any of those files are responsive to the case you’re investigating.</span></span> <span data-ttu-id="7be7d-108">Es ist auch möglicherweise nicht sinnvoll, Fehler zu beheben, bevor Sie die Datei Metadaten (beispielsweise den Dateispeicherort oder die Zugriffsberechtigung) überprüfen konnten, damit Sie Vorabentscheidungen zur Reaktionsfähigkeit treffen können.</span><span class="sxs-lookup"><span data-stu-id="7be7d-108">It also might not make sense to remediate errors before you’ve had a chance to review the file metadata (such as file location or who had access) to help you make up-front decisions about responsiveness.</span></span> <span data-ttu-id="7be7d-109">Ein neues Feature namens " *Single Item Error Remediation* " gibt eDiscovery-Managern die Möglichkeit, die Metadaten von Dateien mit einem Verarbeitungsfehler anzuzeigen und den Fehler bei Bedarf direkt in der Überprüfungsgruppe zu beheben.</span><span class="sxs-lookup"><span data-stu-id="7be7d-109">A new feature called *single item error remediation* gives eDiscovery managers the ability to view the metadata of files with a processing error and if necessary remediate the error directly in the review set.</span></span> <span data-ttu-id="7be7d-110">In diesem Artikel wird erläutert, wie Sie Dateien mit Verarbeitungsfehlern in einem Überprüfungs Satz identifizieren, ignorieren und korrigieren.</span><span class="sxs-lookup"><span data-stu-id="7be7d-110">The article discusses how to identify, ignore, and remediate files with processing errors in a review set.</span></span>

## <a name="identify-documents-with-errors"></a><span data-ttu-id="7be7d-111">Identifizieren von Dokumenten mit Fehlern</span><span class="sxs-lookup"><span data-stu-id="7be7d-111">Identify documents with errors</span></span>

<span data-ttu-id="7be7d-112">Dokumente mit Verarbeitungsfehlern in einem Überprüfungs Satz werden nun identifiziert (mit einem Banner).</span><span class="sxs-lookup"><span data-stu-id="7be7d-112">Documents with processing errors in a review set are now identified (with a banner).</span></span> <span data-ttu-id="7be7d-113">Sie können den Fehler korrigieren oder ignorieren.</span><span class="sxs-lookup"><span data-stu-id="7be7d-113">You can remediate or ignore the error.</span></span> <span data-ttu-id="7be7d-114">Der folgende Screenshot zeigt das Fehler Banner Verarbeitung für ein Word-Dokument in einem Überprüfungs Sätze, die kennwortgeschützt sind.</span><span class="sxs-lookup"><span data-stu-id="7be7d-114">The following screenshot shows the processing error banner for a Word document in a review set that is password-protected.</span></span> <span data-ttu-id="7be7d-115">Beachten Sie außerdem, dass Sie die Datei Metadaten von Dokumenten mit Verarbeitungsfehlern anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="7be7d-115">Also notice that you can view the file metadata of documents with processing errors.</span></span>

![Für Dokument mit Verarbeitungsfehler angezeigtes Banner](../media/SIERimage1.png)

<span data-ttu-id="7be7d-117">Sie können auch nach Dokumenten mit Verarbeitungsfehlern suchen, indem Sie die **Verarbeitungsstatus** Bedingung beim [Abfragen der Dokumente in einem Überprüfungs Satz](review-set-search.md)verwenden.</span><span class="sxs-lookup"><span data-stu-id="7be7d-117">You can also search for documents that have processing errors by using the **Processing status** condition when [querying the documents in a review set](review-set-search.md).</span></span>

![Verwenden der Bedingung "Verarbeitungsstatus" zum Suchen nach Fehler Dokumenten](../media/SIERimage2.png)

### <a name="ignore-errors"></a><span data-ttu-id="7be7d-119">Fehler ignorieren</span><span class="sxs-lookup"><span data-stu-id="7be7d-119">Ignore errors</span></span>

<span data-ttu-id="7be7d-120">Sie können einen Verarbeitungsfehler ignorieren, indem Sie im Fehler Banner Verarbeitung auf **ignorieren** klicken.</span><span class="sxs-lookup"><span data-stu-id="7be7d-120">You can ignore a processing error by clicking **Ignore** in the processing error banner.</span></span> <span data-ttu-id="7be7d-121">Wenn Sie einen Fehler ignorieren, wird das Dokument aus dem [Fehler Behebungs Workflow des Massen Fehlers](error-remediation-when-processing-data-in-advanced-ediscovery.md)entfernt.</span><span class="sxs-lookup"><span data-stu-id="7be7d-121">When you ignore an error, the document is removed from the [bulk error remediation workflow](error-remediation-when-processing-data-in-advanced-ediscovery.md).</span></span> <span data-ttu-id="7be7d-122">Nachdem ein Fehler ignoriert wurde, ändert sich die Farbe des Dokument Banners und gibt an, dass der Verarbeitungsfehler ignoriert wurde.</span><span class="sxs-lookup"><span data-stu-id="7be7d-122">After an error is ignored, the document banner changes color and indicates that the processing error was ignored.</span></span> <span data-ttu-id="7be7d-123">Sie können die Entscheidung, den Fehler zu ignorieren, jederzeit rückgängig machen, indem Sie auf **Rückgängig** klicken.</span><span class="sxs-lookup"><span data-stu-id="7be7d-123">At any time, you can revert the decision to ignore the error by clicking **Revert**.</span></span>

![Klicken Sie auf ignorieren, um den Verarbeitungsfehler zu ignorieren](../media/SIERimage3.png)

<span data-ttu-id="7be7d-125">Sie können auch nach allen Dokumenten suchen, bei denen ein Verarbeitungsfehler aufgetreten ist, der bei der Abfrage von Dokumenten in einem Überprüfungs Satz mit der Bedingung *ignorierte Verarbeitungsfehler* ignoriert wurde.</span><span class="sxs-lookup"><span data-stu-id="7be7d-125">You can also search for all documents that had a processing error that was ignored by using the *Ignored processing errors* condition when querying documents in a review set.</span></span>

![Verwenden der Bedingung ignorierte Verarbeitungsfehler zum Suchen nach ignorierten Fehler Dokumenten](../media/SIERimage4.png)

## <a name="remediate-a-document-with-errors"></a><span data-ttu-id="7be7d-127">Korrigieren eines Dokuments mit Fehlern</span><span class="sxs-lookup"><span data-stu-id="7be7d-127">Remediate a document with errors</span></span>

<span data-ttu-id="7be7d-128">In einigen Fällen müssen Sie möglicherweise einen Verarbeitungsfehler in Dokumenten korrigieren (durch Entfernen eines Kennworts, Entschlüsseln einer verschlüsselten Datei oder Wiederherstellung eines beschädigten Dokuments) und dann das korrigierte Dokument dem Überprüfungs-Datensatz hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="7be7d-128">Sometimes you may be required to remediate a processing error in documents (by removing a password, decrypting an encrypted file, or recovering a corrupted document) and then add the remediated document to the review set.</span></span> <span data-ttu-id="7be7d-129">Auf diese Weise können Sie das Fehlerdokument zusammen mit den anderen Dokumenten in der Überprüfungsgruppe überprüfen und exportieren.</span><span class="sxs-lookup"><span data-stu-id="7be7d-129">This allows you to review and export the error document together with the other documents in the review set.</span></span> 

<span data-ttu-id="7be7d-130">Führen Sie die folgenden Schritte aus, um ein einzelnes Dokument zu korrigieren:</span><span class="sxs-lookup"><span data-stu-id="7be7d-130">To remediate a single document, follow these steps:</span></span>

1. <span data-ttu-id="7be7d-131">Klicken **Sie** auf Download  >  **Original** herunterladen, um eine Kopie der Datei auf einen lokalen Computer herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="7be7d-131">Click **Download** > **Download original** to download a copy of the file to a local computer.</span></span>

   ![Herunterladen des Dokuments mit dem Verarbeitungsfehler](../media/SIERimage5.png)

2. <span data-ttu-id="7be7d-133">Beheben Sie den Fehler in der Datei offline.</span><span class="sxs-lookup"><span data-stu-id="7be7d-133">Remediate the error in the file offline.</span></span> <span data-ttu-id="7be7d-134">Für verschlüsselte Dateien, für die eine Entschlüsselungssoftware erforderlich ist, müssen Sie entweder das Kennwort angeben und die Datei speichern oder einen Kennwortcracker verwenden, um den Kennwortschutz zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="7be7d-134">For encrypted files, that would require decryption software, to remove password protection, either provide the password and save the file or use a password cracker.</span></span> <span data-ttu-id="7be7d-135">Nachdem Sie die Datei behoben haben, fahren Sie mit dem nächsten Schritt fort.</span><span class="sxs-lookup"><span data-stu-id="7be7d-135">After you remediate the file, go to the next step.</span></span>

3. <span data-ttu-id="7be7d-136">Wählen Sie in der Überprüfungsgruppe die Datei mit dem Verarbeitungsfehler aus, den Sie behoben haben, und klicken Sie dann auf **Korrektur**.</span><span class="sxs-lookup"><span data-stu-id="7be7d-136">In the review set, select the file with the processing error that you remediated, and then  click **Remediation**.</span></span>

   ![Klicken Sie auf Korrektur im Banner des Dokuments mit Verarbeitungsfehler](../media/SIERimage6.png)


4. <span data-ttu-id="7be7d-138">Klicken Sie auf **Durchsuchen**, wechseln Sie zum Speicherort der korrigierten Datei auf Ihrem lokalen Computer, und wählen Sie dann die Datei aus.</span><span class="sxs-lookup"><span data-stu-id="7be7d-138">Click **Browse**, go to the location of the remediated file on your local computer, and then select the file.</span></span>

   ![Klicken Sie auf Durchsuchen, und wählen Sie die Datei auf Ihrem lokalen Computer aus.](../media/SIERimage7.png)

    <span data-ttu-id="7be7d-140">Nachdem Sie die korrigierte Datei ausgewählt haben, wird Sie automatisch in den Überprüfungs-Datensatz hochgeladen.</span><span class="sxs-lookup"><span data-stu-id="7be7d-140">After selecting the remediated file, it is automatically uploaded to the review set.</span></span> <span data-ttu-id="7be7d-141">Sie können den Verarbeitungsstatus der Datei nachverfolgen.</span><span class="sxs-lookup"><span data-stu-id="7be7d-141">You can track the processing status of the file.</span></span>

    ![Der Status des Korrekturprozesses wird angezeigt.](../media/SIERimage8.png)

   <span data-ttu-id="7be7d-143">Nach Abschluss der Verarbeitung können Sie das korrigierte Dokument anzeigen.</span><span class="sxs-lookup"><span data-stu-id="7be7d-143">After processing is completed, you can view the remediated document.</span></span>

    ![Sie können die korrigierte Datei im systemeigenen Format des Überprüfungs Satzes anzeigen.](../media/SIERimage9.png)

<span data-ttu-id="7be7d-145">Weitere Informationen dazu, was geschieht, wenn ein Dokument korrigiert wird, finden Sie unter [Was geschieht, wenn Dateien behoben werden](error-remediation-when-processing-data-in-advanced-ediscovery.md#what-happens-when-files-are-remediated).</span><span class="sxs-lookup"><span data-stu-id="7be7d-145">For more information about what happens when a document is remediated, see [What happens when files are remediated](error-remediation-when-processing-data-in-advanced-ediscovery.md#what-happens-when-files-are-remediated).</span></span>

## <a name="search-for-remediated-documents"></a><span data-ttu-id="7be7d-146">Suchen nach korrigierten Dokumenten</span><span class="sxs-lookup"><span data-stu-id="7be7d-146">Search for remediated documents</span></span>

<span data-ttu-id="7be7d-147">Sie können nach allen Dokumenten in einem Überprüfungs Satzes suchen, die mithilfe der Bedingung **Schlüsselwörter** korrigiert wurden, und die folgende Eigenschaft: Wert Paar: **IsFromErrorRemediation: true** angeben.</span><span class="sxs-lookup"><span data-stu-id="7be7d-147">You can search for all documents in a review set that were remediated by using the **Keywords** condition and specifying the following property:value pair: **IsFromErrorRemediation:true**.</span></span> <span data-ttu-id="7be7d-148">Diese Eigenschaft steht auch in der Exportdatei zum Exportieren zur Verfügung, wenn Sie Dokumente aus einem Überprüfungs Sätzen exportieren.</span><span class="sxs-lookup"><span data-stu-id="7be7d-148">This property is also available in the export load file when you export documents from a review set.</span></span>
