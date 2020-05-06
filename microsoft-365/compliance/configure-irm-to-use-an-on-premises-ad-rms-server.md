---
title: Konfigurieren von IRM für die Verwendung eines lokalen AD RMS-Servers
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/13/2017
audience: End User
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 3ecde857-4b7c-451d-b4aa-9eeffc8a8c61
ms.collection:
- M365-security-compliance
description: In diesem Artikel erfahren Sie, wie Sie die Verwaltung von Informationsrechten (Information Rights Management, IRM) in Exchange Online für die Verwendung eines Active Directory Rights Management Service (AD RMS)-Servers konfigurieren.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 510dc7ea628a46bc5bedfc04ba3b197407d5d67d
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44033695"
---
# <a name="configure-irm-to-use-an-on-premises-ad-rms-server"></a><span data-ttu-id="f378e-103">Konfigurieren von IRM für die Verwendung eines lokalen AD RMS-Servers</span><span class="sxs-lookup"><span data-stu-id="f378e-103">Configure IRM to use an on-premises AD RMS server</span></span>
  
<span data-ttu-id="f378e-104">Für die Verwendung mit lokalen Bereitstellungen verwendet die Verwaltung von Informationsrechten (Information Rights Management, IRM) in Exchange Online Active Directory Rights Management Services (AD RMS), eine Informationsschutztechnologie in Windows Server 2008 und höher.</span><span class="sxs-lookup"><span data-stu-id="f378e-104">For use with on-premises deployments, Information Rights Management (IRM) in Exchange Online uses Active Directory Rights Management Services (AD RMS), an information protection technology in Windows Server 2008 and later.</span></span> <span data-ttu-id="f378e-105">IRM-Schutz wird auf E-Mails angewendet, indem eine AD RMS-Berechtigungsrichtlinienvorlage auf eine E-Mail angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="f378e-105">IRM protection is applied to email by applying an AD RMS rights policy template to an email message.</span></span> <span data-ttu-id="f378e-106">Rechte werden der Nachricht selbst zugeordnet, sodass der Schutz sowohl online und offline als auch innerhalb und außerhalb der Firewall der Organisation stattfindet.</span><span class="sxs-lookup"><span data-stu-id="f378e-106">Rights are attached to the message itself so that protection occurs online and offline and inside and outside of your organization's firewall.</span></span>
  
<span data-ttu-id="f378e-107">Mit diesem Thema wird die Konfiguration von IRM für die Verwendung eines AD RMS-Servers erläutert.</span><span class="sxs-lookup"><span data-stu-id="f378e-107">This topic shows you how to configure IRM to use an AD RMS server.</span></span> <span data-ttu-id="f378e-108">Informationen zum Verwenden der neuen Funktionen für Office 365 Nachrichtenverschlüsselung mit Azure Active Directory und Azure Rights Management finden Sie in der [Office 365 FAQ zur Nachrichtenverschlüsselung](https://support.office.com/article/0432dce9-d9b6-4e73-8a13-4a932eb0081e).</span><span class="sxs-lookup"><span data-stu-id="f378e-108">For information about using the new capabilities for Office 365 Message Encryption with Azure Active Directory and Azure Rights Management, see the [Office 365 Message Encryption FAQ](https://support.office.com/article/0432dce9-d9b6-4e73-8a13-4a932eb0081e).</span></span>
  
<span data-ttu-id="f378e-109">Weitere Informationen zu IRM in Exchange Online finden Sie unter [Verwaltung von Informationsrechten in Exchange Online](information-rights-management-in-exchange-online.md).</span><span class="sxs-lookup"><span data-stu-id="f378e-109">To learn more about IRM in Exchange Online, see [Information Rights Management in Exchange Online](information-rights-management-in-exchange-online.md).</span></span>
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f378e-110">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="f378e-110">What do you need to know before you begin?</span></span>

- <span data-ttu-id="f378e-111">Geschätzte Zeit bis zum Abschließen dieser Aufgabe: 30 Minuten</span><span class="sxs-lookup"><span data-stu-id="f378e-111">Estimated time to complete this task: 30 minutes</span></span>

- <span data-ttu-id="f378e-p103">Bevor Sie diese Verfahren ausführen können, müssen Ihnen die entsprechenden Berechtigungen zugewiesen werden. Informationen zu den von Ihnen benötigten Berechtigungen finden Sie unter "Information Rights Management" im Thema [Messaging policy and compliance permissions](https://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx).</span><span class="sxs-lookup"><span data-stu-id="f378e-p103">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Information Rights Management" entry in the [Messaging policy and compliance permissions](https://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx) topic.</span></span> 

- <span data-ttu-id="f378e-p104">Ein AD RMS-Server mit Windows Server 2008 oder höher. Informationen zum Bereitstellen von AD RMS finden Sie im Thema zum [Installieren eines AD RMS-Clusters](https://go.microsoft.com/fwlink/?LinkId=210873).</span><span class="sxs-lookup"><span data-stu-id="f378e-p104">The AD RMS server must be running Windows Server 2008 or later. For details about how to deploy AD RMS, see [Installing an AD RMS Cluster](https://go.microsoft.com/fwlink/?LinkId=210873).</span></span>

- <span data-ttu-id="f378e-116">Informationen zum Installieren und Konfigurieren von Windows PowerShell sowie zum Herstellen einer Verbindung mit dem Dienst finden Sie unter [Herstellen einer Verbindung mit Exchange Online mithilfe der Remote-PowerShell](https://technet.microsoft.com/library/c8bea338-6c1a-4bdf-8de0-7895d427ee5b.aspx).</span><span class="sxs-lookup"><span data-stu-id="f378e-116">For details about how to install and configure Windows PowerShell and connect to the service, see [Connect to Exchange Online Using Remote PowerShell](https://technet.microsoft.com/library/c8bea338-6c1a-4bdf-8de0-7895d427ee5b.aspx).</span></span>

- <span data-ttu-id="f378e-117">Informationen zu Tastenkombinationen, die möglicherweise für die Verfahren in diesem Thema gelten, finden Sie unter [Tastenkombinationen für das Exchange Admin Center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span><span class="sxs-lookup"><span data-stu-id="f378e-117">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="f378e-118">Liegt ein Problem vor?</span><span class="sxs-lookup"><span data-stu-id="f378e-118">Having problems?</span></span> <span data-ttu-id="f378e-119">Bitten Sie in den Exchange-Foren um Hilfe.</span><span class="sxs-lookup"><span data-stu-id="f378e-119">Ask for help in the Exchange forums.</span></span> <span data-ttu-id="f378e-120">Besuchen Sie die Foren unter [Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612),[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542) oder [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351).</span><span class="sxs-lookup"><span data-stu-id="f378e-120">Visit the forums at [Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612),[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542), or [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351).</span></span> 
  
## <a name="how-do-you-do-this"></a><span data-ttu-id="f378e-121">Wie gehen Sie dazu vor?</span><span class="sxs-lookup"><span data-stu-id="f378e-121">How do you do this?</span></span>
<span data-ttu-id="f378e-122"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="f378e-122"><a name="sectionSection1"> </a></span></span>

### <a name="step-1-use-the-ad-rms-console-to-export-a-trusted-publishing-domain-tpd-from-an-ad-rms-server"></a><span data-ttu-id="f378e-123">Schritt 1: Verwenden der AD RMS-Konsole für den Export einer vertrauenswürdigen Veröffentlichungsdomäne von einem AD RMS-Server</span><span class="sxs-lookup"><span data-stu-id="f378e-123">Step 1: Use the AD RMS console to export a trusted publishing domain (TPD) from an AD RMS server</span></span>

<span data-ttu-id="f378e-p106">Der erste Schritt ist das Exportieren einer vertrauenswürdigen Veröffentlichungsdomäne (TPD) vom lokalen AD RMS-Server in eine XML-Datei. Die vertrauenswürdige Veröffentlichungsdomäne (TPD) beinhaltet die folgenden, für die Verwendung von RMS-Funktionen erforderlichen Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="f378e-p106">The first step is to export a trusted publishing domain (TPD) from the on-premises AD RMS server to an XML file. The TPD contains the following settings needed to use RMS features:</span></span>
  
- <span data-ttu-id="f378e-126">Das lizenzgebende Serverzertifikat (SLC) zum Signieren und Verschlüsseln von Zertifikaten und Lizenzen.</span><span class="sxs-lookup"><span data-stu-id="f378e-126">The server licensor certificate (SLC) used for signing and encrypting certificates and licenses</span></span>

- <span data-ttu-id="f378e-127">Die für Lizenzierung und Veröffentlichung verwendeten URLs.</span><span class="sxs-lookup"><span data-stu-id="f378e-127">The URLs used for licensing and publishing</span></span>

- <span data-ttu-id="f378e-128">Die AD RMS-Rechterichtlinienvorlagen, die mit dem spezifischen lizenzgebenden Serverzertifikat (SLC) für diese TPD erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="f378e-128">The AD RMS rights policy templates that were created with the specific SLC for that TPD</span></span>

<span data-ttu-id="f378e-129">Wenn Sie die TPD importieren, wird sie in Exchange Online gespeichert und geschützt.</span><span class="sxs-lookup"><span data-stu-id="f378e-129">When you import the TPD, it's stored and protected in Exchange Online.</span></span>
  
1. <span data-ttu-id="f378e-130">Öffnen Sie die AD RMS-Konsole, und erweitern Sie dann den AD RMS-Cluster.</span><span class="sxs-lookup"><span data-stu-id="f378e-130">Open the Active Directory Rights Management Services console, and then expand the AD RMS cluster.</span></span>

2. <span data-ttu-id="f378e-131">Erweitern Sie in der Konsolenstruktur den Knoten **Vertrauensrichtlinien**, und klicken Sie dann auf **Vertrauenswürdige Veröffentlichungsdomänen**.</span><span class="sxs-lookup"><span data-stu-id="f378e-131">In the console tree, expand **Trust Policies**, and then click **Trusted Publishing Domains**.</span></span>

3. <span data-ttu-id="f378e-132">Wählen Sie das Zertifikat für die zu exportierende Domäne im Ergebnisbereich aus.</span><span class="sxs-lookup"><span data-stu-id="f378e-132">In the results pane, select the certificate for the domain you want to export.</span></span>

4. <span data-ttu-id="f378e-133">Klicken Sie im Bereich **Aktionen** auf **Vertrauenswürdige Veröffentlichungsdomäne exportieren**.</span><span class="sxs-lookup"><span data-stu-id="f378e-133">In the **Actions** pane, click **Export Trusted Publishing Domain**.</span></span>

5. <span data-ttu-id="f378e-p107">Klicken Sie im Feld **Veröffentlichungsdomänendatei** auf **Speichern unter**, um die Datei an einem bestimmten Speicherort auf dem lokalen Computer zu speichern. Geben Sie einen Dateinamen und die  `.xml`-Dateinamenerweiterung an, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="f378e-p107">In the **Publishing domain file** box, click **Save As** to save the file to a specific location on the local computer. Type a file name, making sure to specify the  `.xml` file name extension, and then click **Save**.</span></span>

6. <span data-ttu-id="f378e-p108">Geben Sie in den Feldern **Kennwort** und **Kennwort bestätigen** ein sicheres Kennwort ein, das zum Verschlüsseln der Datei der vertrauenswürdigen Veröffentlichungsdomäne verwendet wird. Dieses Kennwort muss beim Importieren der TPD in die Cloud-basierte E-Mail-Organisation angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="f378e-p108">In the **Password** and **Confirm Password** boxes, type a strong password that will be used to encrypt the trusted publishing domain file. You will have to specify this password when you import the TPD to your cloud-based email organization.</span></span> 

### <a name="step-2-use-the-exchange-management-shell-to-import-the-tpd-to-exchange-online"></a><span data-ttu-id="f378e-138">Schritt 2: Verwenden der Exchange-Verwaltungsshell zum Importieren der TPD in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="f378e-138">Step 2: Use the Exchange Management Shell to import the TPD to Exchange Online</span></span>

<span data-ttu-id="f378e-p109">Nachdem die TPD in eine XML-Datei exportiert wurde, müssen Sie sie in Exchange Online importieren. Beim Importieren einer TPD werden auch die Vorlagen Ihrer Organisation aus AD RMS importiert. Die erste importierte TPD wird zur Standard-TPD für die Cloud-basierte Organisation. Wenn Sie eine weitere TPD importieren, können Sie diese mithilfe der Option **Default** als die für Benutzer verfügbare Standard-TPD festlegen.</span><span class="sxs-lookup"><span data-stu-id="f378e-p109">After the TPD is exported to an XML file, you have to import it to Exchange Online. When a TPD is imported, your organization's AD RMS templates are also imported. When the first TPD is imported, it becomes the default TPD for your cloud-based organization. If you import another TPD, you can use the **Default** switch to make it the default TPD that is available to users.</span></span> 
  
<span data-ttu-id="f378e-143">Führen Sie zum Importieren der TPD in Windows PowerShell den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="f378e-143">To import the TPD, run the following command in Windows PowerShell:</span></span>
  
```powershell
Import-RMSTrustedPublishingDomain -FileData $([byte[]](Get-Content -Encoding byte -Path <path to exported TPD file> -ReadCount 0)) -Name "<name of TPD>" -ExtranetLicensingUrl <URL> -IntranetLicensingUrl <URL>
```

<span data-ttu-id="f378e-p110">Die Werte für die Parameter  _ExtranetLicensingUrl_ und  _IntranetLicensingUrl_ können Sie in der Konsole der Active Directory-Rechteverwaltungsdienste abrufen. Wählen Sie den AD RMS-Cluster in der Konsolenstruktur aus. Die URLs für die Lizenzierung werden im Ergebnisbereich angezeigt. Diese URLs werden von E-Mail-Clients verwendet, wenn Inhalt entschlüsselt werden muss und wenn Exchange Online die zu verwendende TPD ermitteln muss.</span><span class="sxs-lookup"><span data-stu-id="f378e-p110">You can obtain the values for the  _ExtranetLicensingUrl_ and  _IntranetLicensingUrl_ parameters in the Active Directory Rights Management Services console. Select the AD RMS cluster in the console tree. The licensing URLs are displayed in the results pane. These URLs are used by email clients when content has to be decrypted and when Exchange Online needs to determine which TPD to use.</span></span>
  
<span data-ttu-id="f378e-p111">Beim Ausführen dieses Befehls werden Sie zur Eingabe eines Kennworts aufgefordert. Geben Sie das Kennwort ein, das Sie beim Exportieren der TPD vom AD RMS-Server angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="f378e-p111">When you run this command, you'll be prompted for a password. Enter the password that you specified when you exported the TPD from your AD RMS server.</span></span>
  
<span data-ttu-id="f378e-p112">Beispiel: Durch den folgenden Befehl wird die TPD mit dem Namen "Exported TPD" anhand der vom AD RMS-Server exportierten XML-Datei importiert und auf dem Desktop des Administratorkontos gespeichert. Mit dem Name-Parameter wird ein Name für die TPD angegeben.</span><span class="sxs-lookup"><span data-stu-id="f378e-p112">For example, the following command imports the TPD named Exported TPD using the XML file that you exported from your AD RMS server and saved to the desktop of the Administrator account. The Name parameter is used to specify a name to the TPD.</span></span>
  
```powershell
Import-RMSTrustedPublishingDomain -FileData $([byte[]](Get-Content -Encoding byte -Path C:\Users\Administrator\Desktop\ExportTPD.xml -ReadCount 0)) -Name "Exported TPD" -ExtranetLicensingUrl https://corp.contoso.com/_wmcs/licensing -IntranetLicensingUrl https://rmsserver/_wmcs/licensing
```

<span data-ttu-id="f378e-152">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Import-RMSTrustedPublishingDomain](https://technet.microsoft.com/library/7c5e7a0f-9c9d-4863-bab8-bcc729cc16a6.aspx).</span><span class="sxs-lookup"><span data-stu-id="f378e-152">For detailed syntax and parameter information, see [Import-RMSTrustedPublishingDomain](https://technet.microsoft.com/library/7c5e7a0f-9c9d-4863-bab8-bcc729cc16a6.aspx).</span></span>
  
#### <a name="how-do-you-know-this-step-worked"></a><span data-ttu-id="f378e-153">Woher wissen Sie, dass dieser Schritt erfolgreich war?</span><span class="sxs-lookup"><span data-stu-id="f378e-153">How do you know this step worked?</span></span>

<span data-ttu-id="f378e-p113">Führen Sie zur Überprüfung eines erfolgreichen Imports der TPD das Cmdlet **Get-RMSTrustedPublishingDomain** zum Abruf von TPDs in Ihrer Exchange Online-Organisation auf. Für Einzelheiten finden Sie Beispiele unter [Get-RMSTrustedPublishingDomain](https://technet.microsoft.com/library/69499195-f08f-41bd-b0ed-443688410b12.aspx).</span><span class="sxs-lookup"><span data-stu-id="f378e-p113">To verify that you have successfully imported the TPD, run the **Get-RMSTrustedPublishingDomain** cmdlet to retrieve TPDs in your Exchange Online organization. For details, see the examples in [Get-RMSTrustedPublishingDomain](https://technet.microsoft.com/library/69499195-f08f-41bd-b0ed-443688410b12.aspx).</span></span>
  
### <a name="step-3-use-the-exchange-management-shell-to-distribute-an-ad-rms-rights-policy-template"></a><span data-ttu-id="f378e-156">Schritt 3: Verwenden der Exchange-Verwaltungsshell zur Verteilung einer AD RMS-Rechterichtlinienvorlage</span><span class="sxs-lookup"><span data-stu-id="f378e-156">Step 3: Use the Exchange Management Shell to distribute an AD RMS rights policy template</span></span>

<span data-ttu-id="f378e-157">Nach dem Import der TPD müssen Sie sicherstellen, dass eine AD RMS-Rechterichtlinienvorlage verteilt wird.</span><span class="sxs-lookup"><span data-stu-id="f378e-157">After you import the TPD, you must make sure an AD RMS rights policy template is distributed.</span></span> <span data-ttu-id="f378e-158">Eine verteilte Vorlage ist für Outlook im Internet (früher als Outlook Web App bezeichnet) Benutzer sichtbar, die dann die Vorlagen auf eine e-Mail-Nachricht anwenden können.</span><span class="sxs-lookup"><span data-stu-id="f378e-158">A distributed template is visible to Outlook on the web (formerly known as Outlook Web App) users, who can then apply the templates to an email message.</span></span>
  
<span data-ttu-id="f378e-159">Führen Sie den folgenden Befehl aus, um eine Liste aller Vorlagen in der Standard-TPD anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="f378e-159">To return a list of all templates contained in the default TPD, run the following command:</span></span>
  
```powershell
Get-RMSTemplate -Type All | fl
```

<span data-ttu-id="f378e-160">Wenn der Wert des Parameters  _Type_ `Archived` lautet, ist die Vorlage nicht für Benutzer sichtbar.</span><span class="sxs-lookup"><span data-stu-id="f378e-160">If the value of the  _Type_ parameter is  `Archived`, the template isn't visible to users.</span></span> <span data-ttu-id="f378e-161">Nur verteilte Vorlagen in der Standard-TPD sind in Outlook im Internet verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f378e-161">Only distributed templates in the default TPD are available in Outlook on the web.</span></span>
  
<span data-ttu-id="f378e-162">Führen Sie zum Verteilen einer Vorlage den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="f378e-162">To distribute a template, run the following command:</span></span>
  
```powershell
Set-RMSTemplate -Identity "<name of the template>" -Type Distributed
```

<span data-ttu-id="f378e-163">Beispiel: Durch den folgenden Befehl wird die Vorlage "Company Confidential" importiert:</span><span class="sxs-lookup"><span data-stu-id="f378e-163">For example, the following command imports the Company Confidential template.</span></span>
  
```powershell
Set-RMSTemplate -Identity "Company Confidential" -Type Distributed
```

<span data-ttu-id="f378e-164">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-RMSTemplate](https://technet.microsoft.com/library/4a5066e8-b770-4aa2-b464-0d2190914f71.aspx) und [Set-RMSTemplate](https://technet.microsoft.com/library/4637f6b8-751a-4f5e-8869-428250230382.aspx).</span><span class="sxs-lookup"><span data-stu-id="f378e-164">For detailed syntax and parameter information, see [Get-RMSTemplate](https://technet.microsoft.com/library/4a5066e8-b770-4aa2-b464-0d2190914f71.aspx) and [Set-RMSTemplate](https://technet.microsoft.com/library/4637f6b8-751a-4f5e-8869-428250230382.aspx).</span></span>
  
<span data-ttu-id="f378e-165">**Vorlage "Nicht weiterleiten"**</span><span class="sxs-lookup"><span data-stu-id="f378e-165">**The Do Not Forward template**</span></span>
  
<span data-ttu-id="f378e-p116">Wenn Sie die Standard-TPD aus der lokalen Organisation in Exchange Online importieren, wird eine RMS-Rechterichtlinienvorlage mit der Bezeichnung **Do Not Forward** importiert. Diese Vorlage wird standardmäßig verteilt, wenn Sie die Standard-TPD importieren. Die Vorlage **Do Not Forward** kann nicht mit dem Cmdlet **Set-RMSTemplate** geändert werden.</span><span class="sxs-lookup"><span data-stu-id="f378e-p116">When you import the default TPD from your on-premises organization into Exchange Online, one AD RMS rights policy template named **Do Not Forward** is imported. By default, this template is distributed when you import the default TPD. You can't use the **Set-RMSTemplate** cmdlet to modify the **Do Not Forward** template.</span></span> 
  
<span data-ttu-id="f378e-p117">Wenn die Vorlage **Do Not Forward** auf eine Nachricht angewendet wird, kann die Nachricht nur von Empfängern der Nachricht gelesen werden. Darüber hinaus können Empfänger folgende Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="f378e-p117">When the **Do Not Forward** template is applied to a message, only the recipients addressed in the message can read the message. Additionally, recipients can't do the following:</span></span>
  
- <span data-ttu-id="f378e-171">Weiterleiten der Nachricht an eine andere Person</span><span class="sxs-lookup"><span data-stu-id="f378e-171">Forward the message to another person.</span></span>

- <span data-ttu-id="f378e-172">Kopieren von Inhalt aus der Nachricht</span><span class="sxs-lookup"><span data-stu-id="f378e-172">Copy content from the message.</span></span>

- <span data-ttu-id="f378e-173">Drucken der Nachricht</span><span class="sxs-lookup"><span data-stu-id="f378e-173">Print the message.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f378e-174">Durch die Vorlage **Do Not Forward** kann nicht verhindert werden, dass Informationen in einer Nachricht mit Drittanbieter-Bildschirmaufnahmeprogrammen oder Kameras kopiert oder von Benutzern manuell übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="f378e-174">The **Do Not Forward** template can't prevent information in a message from being copied with third-party screen capture programs, cameras, or users manually transcribing the information</span></span> 
  
<span data-ttu-id="f378e-p118">Sie können zusätzliche AD RMS-Rechterichtlinienvorlagen auf dem AD RMS-Server in der lokalen Organisation erstellen, um Ihre Anforderungen hinsichtlich des IRM-Schutzes zu erfüllen. Wenn Sie zusätzliche AD RMS-Vorlagen erstellen, müssen Sie die TPD erneut vom lokalen AD RMS-Server exportieren und die TPD in der Cloud-basierten E-Mail-Organisation aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="f378e-p118">You can create additional AD RMS rights policy templates on the AD RMS server in your on-premises organization to meet your IRM protection requirements. If you create additional AD RMS rights policy templates, you have to export the TPD from the on-premises AD RMS server again and refresh the TPD in the cloud-based email organization.</span></span>
  
#### <a name="how-do-you-know-this-step-worked"></a><span data-ttu-id="f378e-177">Woher wissen Sie, dass dieser Schritt erfolgreich war?</span><span class="sxs-lookup"><span data-stu-id="f378e-177">How do you know this step worked?</span></span>

<span data-ttu-id="f378e-p119">Führen Sie zur Überprüfung einer erfolgreichen Verteilung einer AD RMS-Rechterichtlinienvorlage das Cmdlet **Get-RMSTemplate** zur Prüfung der Eigenschaften der Vorlage aus. Für Einzelheiten finden Sie Beispiele unter [Get-RMSTemplate](https://technet.microsoft.com/library/4a5066e8-b770-4aa2-b464-0d2190914f71.aspx).</span><span class="sxs-lookup"><span data-stu-id="f378e-p119">To verify that you have successfully distributed and AD RMS rights policy template, run the **Get-RMSTemplate** cmdlet to check the template's properties. For details, see the examples in [Get-RMSTemplate](https://technet.microsoft.com/library/4a5066e8-b770-4aa2-b464-0d2190914f71.aspx).</span></span>
  
### <a name="step-4-use-the-exchange-management-shell-to-enable-irm"></a><span data-ttu-id="f378e-180">Schritt 4: Verwenden der Exchange-Verwaltungsshell zur Aktivierung von IRM</span><span class="sxs-lookup"><span data-stu-id="f378e-180">Step 4: Use the Exchange Management Shell to enable IRM</span></span>

<span data-ttu-id="f378e-181">Führen Sie nach dem Import der TPD und der Verteilung der AD RMS-Rechterichtlinienvorlage den folgenden Befehl zur Aktivierung von IRM für Ihre Cloud-basierte E-Mail-Organisation aus.</span><span class="sxs-lookup"><span data-stu-id="f378e-181">After you import the TPD and distribute an AD RMS rights policy template, run the following command to enable IRM for your cloud-based email organization.</span></span>
  
```powershell
Set-IRMConfiguration -InternalLicensingEnabled $true
```

<span data-ttu-id="f378e-182">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-IRMConfiguration](https://technet.microsoft.com/library/5df0b56a-7bcc-4be2-b4b8-4de16720476c.aspx).</span><span class="sxs-lookup"><span data-stu-id="f378e-182">For detailed syntax and parameter information, see [Set-IRMConfiguration](https://technet.microsoft.com/library/5df0b56a-7bcc-4be2-b4b8-4de16720476c.aspx).</span></span>
  
#### <a name="how-do-you-know-this-step-worked"></a><span data-ttu-id="f378e-183">Woher wissen Sie, dass dieser Schritt erfolgreich war?</span><span class="sxs-lookup"><span data-stu-id="f378e-183">How do you know this step worked?</span></span>

<span data-ttu-id="f378e-184">Zur Überprüfung einer erfolgreichen Aktivierung von IRM führen Sie das Cmdlet [Get-IRMConfiguration](https://technet.microsoft.com/library/e1821219-fe18-4642-a9c2-58eb0aadd61a.aspx) zur Prüfung der IRM-Konfiguration in der Exchange Online-Organisation aus.</span><span class="sxs-lookup"><span data-stu-id="f378e-184">To verify that you have successfully enabled IRM, run the [Get-IRMConfiguration](https://technet.microsoft.com/library/e1821219-fe18-4642-a9c2-58eb0aadd61a.aspx) cmdlet to check IRM configuration in the Exchange Online organization.</span></span>
  
## <a name="how-do-you-know-this-task-worked"></a><span data-ttu-id="f378e-185">Woher wissen Sie, dass diese Aufgabe erfolgreich war?</span><span class="sxs-lookup"><span data-stu-id="f378e-185">How do you know this task worked?</span></span>
<span data-ttu-id="f378e-186"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="f378e-186"><a name="sectionSection2"> </a></span></span>

<span data-ttu-id="f378e-187">Führen Sie zur Überprüfung eines erfolgreichen Imports der TPD und einer erfolgreichen Aktivierung von IRM folgende Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="f378e-187">To verify that you have successfully imported the TPD and enabled IRM, do the following:</span></span>
  
- <span data-ttu-id="f378e-p120">Verwenden Sie das Cmdlet **Test-IRMConfiguration**, um die Funktionalität von IRM zu überprüfen. Details finden Sie in "Beispiel 1" unter [Test-IRMConfiguration](https://technet.microsoft.com/library/a730e7ff-a67f-4360-b5ff-70d171bb5e1d.aspx).</span><span class="sxs-lookup"><span data-stu-id="f378e-p120">Use the **Test-IRMConfiguration** cmdlet to test IRM functionality. For details, see "Example 1" in [Test-IRMConfiguration](https://technet.microsoft.com/library/a730e7ff-a67f-4360-b5ff-70d171bb5e1d.aspx).</span></span>

- <span data-ttu-id="f378e-190">Erstellen Sie eine neue Nachricht in Outlook im Internet und IRM-Protect, indem Sie im erweiterten Menü die Option **Berechtigungen festlegen** auswählen ( ![weitere Optionen](../media/ITPro-EAC-MoreOptionsIcon.gif)).</span><span class="sxs-lookup"><span data-stu-id="f378e-190">Compose a new message in Outlook on the web and IRM-protect it by selecting **Set permissions** option from the extended menu ( ![More Options Icon](../media/ITPro-EAC-MoreOptionsIcon.gif)).</span></span>
