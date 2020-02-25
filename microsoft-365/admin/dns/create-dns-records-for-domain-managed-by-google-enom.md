---
title: Erstellen von DNS-Einträgen, wenn Ihre Domäne von Google verwaltet wird (eNom)
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
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
ms.openlocfilehash: 7a1de0887b96678fb95372633b621d96f7855225
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42241047"
---
# <a name="create-dns-records-when-your-domain-is-managed-by-google-enom"></a>Erstellen von DNS-Einträgen, wenn Ihre Domäne von Google verwaltet wird (eNom)

 **[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen. 
  
Zum Migrieren Ihrer E-Mail-Konten zu Office 365 müssen Sie einen DNS-Eintrag bei Ihrer Domänenregistrierungsstelle erstellen.
  
Wenn Sie Ihre Domäne über Google erworben haben, während Sie sich für Ihr **Google Apps for Work** -Konto angemeldet haben, werden Ihre DNS-Einträge von Google verwaltet, aber bei eNom registriert. 
  
Sie können über die Seite Google **Domains** auf eNom zugreifen und DNS erstellen. Führen Sie dazu die Schritte in diesem Artikel aus. 
  
## <a name="create-the-dns-record"></a>Erstellen des DNS-Eintrags

1. Wählen Sie in der [Google-Verwaltungskonsole](https://www.google.com/work/apps/business) **Anmelden**aus.
    
    ![Google-Apps-Configure-1-1-0](../media/37a6e9f6-319e-4c02-aa18-d8d06df7953d.png)
  
2. Geben Sie Ihren Domänennamen ein, und wählen Sie dann **wechseln**aus.
    
    ![Google-Apps-Configure-1-1-1](../media/2caf8dcb-4d40-4cfa-bc40-d634e454e699.png)
  
3. Wählen Sie unten auf der Seite **Weitere Steuerelemente**aus.
    
    ![Google-Apps-Configure-1-2-0](../media/1518ff78-035b-423e-85a3-c16d7faa0968.png)
  
4. Wählen Sie **Domänen** aus.
    
    ![Google-Apps-Configure-1-2-1](../media/c2972c06-9bca-43bd-9876-2cee63043bf1.png)
  
5. Wählen Sie auf der Seite **Domänen** die Option **Domänen hinzufügen/entfernen**aus.
    
    ![Google-Apps-Configure-1-2-2](../media/07b8068f-9a05-40aa-a041-fc495c729a18.png)
  
6. Wählen Sie auf der Seite **Domänen** die Option **Erweiterte DNS-Einstellungen**aus.
    
    > [!NOTE]
    > Falls Sie während der Registrierung für Ihr **Google Apps for Work** -Konto keinen Domänennamen erworben haben, ist die Option **Erweiterte DNS-Einstellungen** nicht auf Ihrer Seite **Domains** verfügbar. In diesem Fall müssen Sie direkt zur Website Ihres Domain-Hosts wechseln, um auf Ihre DNS-Einstellungen zuzugreifen, um diesen und die folgenden Schritte auszuführen. Weitere Informationen finden Sie unter [Access Your G Suite Domain Settings](https://support.google.com/a/answer/54693?hl=en) . 
  
    ![Google-Apps-eNom-configure-1-3](../media/b244b29c-e479-40be-b380-4ffa0f74b421.png)
  
7. Wählen Sie auf der Seite **Erweiterte DNS-Einstellungen** die Option **Anmelden bei DNS-Konsole**aus. Notieren Sie Ihre Angaben für **Anmeldename** und **Kennwort**. Sie benötigen Sie im nächsten Schritt. 
    
    ![Google-Apps-eNom-configure-1-4](../media/056a2767-462f-4847-acee-d01e3f773add.png)
  
8. Melden Sie sich mithilfe des **Anmeldenamens** und **Kennworts** von der Seite **Advanced DNS settings** (Erweiterte DNS-Einstellungen) beim **Domain Manager** von Google an. 
    
    ![Google-Apps-eNom-configure-1-5](../media/08b74652-8cdb-4560-a5fd-0899f86deee8.png)
  
9. Wählen Sie auf der Seite ***domain_name*** im Abschnitt **Host Einträge** die Option **Bearbeiten**aus.
    
    ![Google-Apps-eNom-configure-1-6](../media/d54fec18-b9d1-4796-8397-0393c964eade.png)
  
10. Wählen Sie im Abschnitt **Host Einträge** die Option **Neues hinzufügen**aus.
    
    ![Google-Apps-eNom-configure-1-7](../media/3562806a-4328-4e60-a717-0566841204cf.png)
  
11. In the boxes for the new record, type or copy and paste the values from the following table.
    
    |**HOST**|**TXT VALUE**|**Eintragstyp**|
    |:-----|:-----|:-----|
    |@  <br/> ||TXT  <br/> |

    > [!NOTE]
    > This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365. 
  
    [Wie finde ich diese Angabe?](../get-help-with-domains/information-for-dns-records.md)
  
12. Klicken Sie auf **Speichern**.
    
    ![Google-Apps-eNom-configure-1-9](../media/7a6f7b45-8f79-487b-afe4-05949c2c04e8.png)
  
13. Wählen Sie **Save Changes**aus.
    
    ![Google-Apps-Configure-1-11](../media/7f321236-33fb-4a7d-9d03-26605e9e558c.png)
  
> [!NOTE]
>  Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md). 
  
