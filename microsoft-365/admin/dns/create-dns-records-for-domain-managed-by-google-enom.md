---
title: Erstellen von DNS-Einträgen, wenn Ihre Domäne von Google verwaltet wird (eNom)
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 3c490fbf-7833-4e43-be34-ed0dc3cce5e3
description: Erfahren Sie, wie Sie über die Google Domains-Seite auf eNom zugreifen und DNS erstellen.
ms.openlocfilehash: 7d79350f163d1b120d3dd45bc7bbb3e57583bf05
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629131"
---
# <a name="create-dns-records-when-your-domain-is-managed-by-google-enom"></a><span data-ttu-id="e6667-103">Erstellen von DNS-Einträgen, wenn Ihre Domäne von Google verwaltet wird (eNom)</span><span class="sxs-lookup"><span data-stu-id="e6667-103">Create DNS records when your domain is managed by Google (eNom)</span></span>

 <span data-ttu-id="e6667-104">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="e6667-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="e6667-105">Zum Migrieren Ihrer e-Mail-Konten zu Microsoft müssen Sie einen DNS-Eintrag bei Ihrer Domänenregistrierungsstelle erstellen.</span><span class="sxs-lookup"><span data-stu-id="e6667-105">To migrate your mail accounts to Microsoft, you need to create a DNS record at your domain registrar.</span></span>
  
<span data-ttu-id="e6667-106">Wenn Sie Ihre Domäne über Google erworben haben, während Sie sich für Ihr **Google Apps for Work** -Konto angemeldet haben, werden Ihre DNS-Einträge von Google verwaltet, aber bei eNom registriert.</span><span class="sxs-lookup"><span data-stu-id="e6667-106">If you purchased your domain through Google while signing up for your **Google Apps for Work** account, your DNS records are managed by Google but registered with eNom.</span></span> 
  
<span data-ttu-id="e6667-107">Sie können über die Seite Google **Domains** auf eNom zugreifen und DNS erstellen.</span><span class="sxs-lookup"><span data-stu-id="e6667-107">You can access eNom, and create DNS, through the Google **Domains** page.</span></span> <span data-ttu-id="e6667-108">Führen Sie dazu die Schritte in diesem Artikel aus.</span><span class="sxs-lookup"><span data-stu-id="e6667-108">Just follow the steps in this article.</span></span> 
  
## <a name="create-the-dns-record"></a><span data-ttu-id="e6667-109">Erstellen des DNS-Eintrags</span><span class="sxs-lookup"><span data-stu-id="e6667-109">Create the DNS record</span></span>

1. <span data-ttu-id="e6667-110">Wählen Sie in der [Google-Verwaltungskonsole](https://www.google.com/work/apps/business) **Anmelden**aus.</span><span class="sxs-lookup"><span data-stu-id="e6667-110">At the [Google Admin console](https://www.google.com/work/apps/business), select **Sign In**.</span></span>
    
    ![Google-Apps-Configure-1-1-0](../../media/37a6e9f6-319e-4c02-aa18-d8d06df7953d.png)
  
2. <span data-ttu-id="e6667-112">Geben Sie Ihren Domänennamen ein, und wählen Sie dann **wechseln**aus.</span><span class="sxs-lookup"><span data-stu-id="e6667-112">Enter your domain name, and then select **Go**.</span></span>
    
    ![Google-Apps-Configure-1-1-1](../../media/2caf8dcb-4d40-4cfa-bc40-d634e454e699.png)
  
3. <span data-ttu-id="e6667-114">Wählen Sie unten auf der Seite **Weitere Steuerelemente**aus.</span><span class="sxs-lookup"><span data-stu-id="e6667-114">At the bottom of the page, select **More controls**.</span></span>
    
    ![Google-Apps-Configure-1-2-0](../../media/1518ff78-035b-423e-85a3-c16d7faa0968.png)
  
4. <span data-ttu-id="e6667-116">Wählen Sie **Domänen** aus.</span><span class="sxs-lookup"><span data-stu-id="e6667-116">Select **Domains**.</span></span>
    
    ![Google-Apps-Configure-1-2-1](../../media/c2972c06-9bca-43bd-9876-2cee63043bf1.png)
  
5. <span data-ttu-id="e6667-118">Wählen Sie auf der Seite **Domänen** die Option **Domänen hinzufügen/entfernen**aus.</span><span class="sxs-lookup"><span data-stu-id="e6667-118">On the **Domains** page, select **Add/remove domains**.</span></span>
    
    ![Google-Apps-Configure-1-2-2](../../media/07b8068f-9a05-40aa-a041-fc495c729a18.png)
  
6. <span data-ttu-id="e6667-120">Wählen Sie auf der Seite **Domänen** die Option **Erweiterte DNS-Einstellungen**aus.</span><span class="sxs-lookup"><span data-stu-id="e6667-120">On the **Domains** page, select **Advanced DNS settings**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e6667-121">Falls Sie während der Registrierung für Ihr **Google Apps for Work** -Konto keinen Domänennamen erworben haben, ist die Option **Erweiterte DNS-Einstellungen** nicht auf Ihrer Seite **Domains** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e6667-121">If you didn't purchase a domain name through Google while signing up for your **Google Apps for Work** account, you won't have **Advanced DNS settings** on your **Domains** page.</span></span> <span data-ttu-id="e6667-122">In diesem Fall müssen Sie direkt zur Website Ihres Domain-Hosts wechseln, um auf Ihre DNS-Einstellungen zuzugreifen, um diesen und die folgenden Schritte auszuführen.</span><span class="sxs-lookup"><span data-stu-id="e6667-122">Instead, you must go directly to your domain host's web site to access your DNS settings and to perform this and the following steps.</span></span> <span data-ttu-id="e6667-123">Weitere Informationen finden Sie unter [Access Your G Suite Domain Settings](https://support.google.com/a/answer/54693?hl=en) .</span><span class="sxs-lookup"><span data-stu-id="e6667-123">See [Access your G Suite domain settings](https://support.google.com/a/answer/54693?hl=en) for more information.</span></span> 
  
    ![Google-Apps-eNom-configure-1-3](../../media/b244b29c-e479-40be-b380-4ffa0f74b421.png)
  
7. <span data-ttu-id="e6667-125">Wählen Sie auf der Seite **Erweiterte DNS-Einstellungen** die Option **Anmelden bei DNS-Konsole**aus.</span><span class="sxs-lookup"><span data-stu-id="e6667-125">On the **Advanced DNS settings** page, select **Sign in to DNS Console**.</span></span> <span data-ttu-id="e6667-126">Notieren Sie Ihre Angaben für **Anmeldename** und **Kennwort**.</span><span class="sxs-lookup"><span data-stu-id="e6667-126">Note the **Sign-in name** and **Password** information.</span></span> <span data-ttu-id="e6667-127">Sie benötigen Sie im nächsten Schritt.</span><span class="sxs-lookup"><span data-stu-id="e6667-127">You'll need it in the next step.</span></span> 
    
    ![Google-Apps-eNom-configure-1-4](../../media/056a2767-462f-4847-acee-d01e3f773add.png)
  
8. <span data-ttu-id="e6667-129">Melden Sie sich mithilfe des **Anmeldenamens** und **Kennworts** von der Seite **Advanced DNS settings** (Erweiterte DNS-Einstellungen) beim **Domain Manager** von Google an.</span><span class="sxs-lookup"><span data-stu-id="e6667-129">Log in to the Google **Domain Manager** using the **Sign-in name** and **Password** from the **Advanced DNS settings** page.</span></span> 
    
    ![Google-Apps-eNom-configure-1-5](../../media/08b74652-8cdb-4560-a5fd-0899f86deee8.png)
  
9. <span data-ttu-id="e6667-131">Wählen Sie auf der Seite ***domain_name*** im Abschnitt **Host Einträge** die Option **Bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="e6667-131">On the ***domain_name*** page, in the **Host Records** section, select **Edit**.</span></span>
    
    ![Google-Apps-eNom-configure-1-6](../../media/d54fec18-b9d1-4796-8397-0393c964eade.png)
  
10. <span data-ttu-id="e6667-133">Wählen Sie im Abschnitt **Host Einträge** die Option **Neues hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="e6667-133">In the **Host Records** section, select **Add New**.</span></span>
    
    ![Google-Apps-eNom-configure-1-7](../../media/3562806a-4328-4e60-a717-0566841204cf.png)
  
11. <span data-ttu-id="e6667-135">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="e6667-135">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="e6667-136">**HOST**</span><span class="sxs-lookup"><span data-stu-id="e6667-136">**HOST**</span></span>|<span data-ttu-id="e6667-137">**TXT VALUE**</span><span class="sxs-lookup"><span data-stu-id="e6667-137">**TXT VALUE**</span></span>|<span data-ttu-id="e6667-138">**Eintragstyp**</span><span class="sxs-lookup"><span data-stu-id="e6667-138">**RECORD TYPE**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> ||<span data-ttu-id="e6667-139">TXT</span><span class="sxs-lookup"><span data-stu-id="e6667-139">TXT</span></span>  <br/> |

    > [!NOTE]
    > <span data-ttu-id="e6667-140">This is an example.</span><span class="sxs-lookup"><span data-stu-id="e6667-140">This is an example.</span></span> <span data-ttu-id="e6667-141">Verwenden Sie hier Ihre spezifischen **Ziel-oder Punkt-zu-Adresse** -Werte aus der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="e6667-141">Use your specific **Destination or Points to Address** value here, from the table.</span></span> 
  
    [<span data-ttu-id="e6667-142">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="e6667-142">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)
  
12. <span data-ttu-id="e6667-143">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="e6667-143">Select **Save**.</span></span>
    
    ![Google-Apps-eNom-configure-1-9](../../media/7a6f7b45-8f79-487b-afe4-05949c2c04e8.png)
  
13. <span data-ttu-id="e6667-145">Wählen Sie **Save Changes**aus.</span><span class="sxs-lookup"><span data-stu-id="e6667-145">Select **Save Changes**.</span></span>
    
    ![Google-Apps-Configure-1-11](../../media/7f321236-33fb-4a7d-9d03-26605e9e558c.png)
  
> [!NOTE]
>  <span data-ttu-id="e6667-p105">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="e6667-p105">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
