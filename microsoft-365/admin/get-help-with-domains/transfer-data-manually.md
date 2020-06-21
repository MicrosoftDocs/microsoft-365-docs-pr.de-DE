---
title: Manuelles Übertragen von Daten zwischen zwei Konten
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
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
ms.assetid: 7dc5d983-84b2-4802-bef0-602ae1780a42
description: Hier erfahren Sie, wie Sie Daten manuell zwischen zwei Microsoft 365-Konten übertragen, wenn Sie den Plan oder den Firmennamen geändert oder mehrere Abonnements in einem kombiniert haben.
ms.openlocfilehash: 6e64872ad7e145b63eb71d89ea2d69e5d8697eb6
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780169"
---
# <a name="transfer-data-manually-between-two-accounts"></a>Manuelles Übertragen von Daten zwischen zwei Konten

Bereiten Sie das Aufrollen der Ärmel vor und blockieren Sie einen Teil der Zeit in Ihrem Kalender: das Übertragen von Daten zwischen zwei Microsoft 365-Konten ist ein manueller, komplizierter und zeitaufwändiger Prozess. Dies ist kein automatisierter oder unterstützter Prozess. Wir führen Sie an die Arbeit heran.
  
> [!CAUTION]
> Während des Prozesses wird es zu Ausfallzeiten kommen, bei denen e-Mails, Skype for Business und eine auf Microsoft 365 gehostete öffentliche Website nicht funktionieren. Benutzer erhalten neue Benutzernamen und Kennwörter und sie müssen Outlook zurücksetzen.

**Übertragen Sie Daten mithilfe der Anweisungen in diesem Thema nur dann manuell, wenn eine der folgenden Situationen zutrifft:**
  
- Sie müssen zu einem Plan in einer anderen Dienstfamilie wechseln.

- Ihr Firmenname wurde geändert und Sie haben sich entscheiden, ein neues Abonnement zu erstellen und Ihre Daten zu migrieren, da Sie unterschiedliche anfängliche Domänennamen verwenden möchten.

- Sie müssen mehrere Abonnements zu einem neuen einzelnen Abonnement zusammenfassen.

> [!IMPORTANT]
> Wenn Sie [Ihren Abonnementplan ändern müssen](../../commerce/subscriptions/switch-to-a-different-plan.md) und den Assistenten zum Wechseln von Plänen verwenden können, oder wenn Sie zu einem neuen Abonnementplan in derselben Abonnementgruppe wechseln müssen, auch wenn der Assistent zum Wechseln von Plänen nicht funktioniert, müssen Sie Ihre Daten nicht manuell übertragen und es gibt keine Ausfallzeiten.

|**Aufgaben**|**Schritte**|
|:-----|:-----|
|Abonnieren Sie den Plan, in den Sie wechseln möchten.  <br/> |When you sign up, you specify the company name to use in the initial domain names:  *yourcompany*  .onmicrosoft.com,  *yourcompany*  -public.sharepoint.com, and  *yourcompany*  .sharepoint.com. You need to use a different  *yourcompany*  name than you did for any existing subscriptions.  <br/> > [!NOTE]>  Normalerweise dauert es mindestens mehrere Monate nach dem Kündigen eines Abonnements, bis die ursprünglichen Domänennamen von unseren Systemen freigeben werden, die  *ihrefirma*  verwenden. Selbst wenn Sie planen, alle Daten aus Ihrem alten Microsoft 365-Abonnement zu speichern und das Abonnement abzubrechen, ist der alte *yourcompany* -Wert nicht sofort für die Verwendung in einem neuen Abonnement verfügbar.           |
|Entfernen Sie Ihre benutzerdefinierte Domäne aus Ihrem alten Microsoft 365-Abonnement.  <br/> | Befolgen Sie die [erforderlichen Schritte, bevor Sie eine Domäne entfernen](remove-a-domain.md), um den Namen der Domäne aus E-Mail-Adressen von Benutzern sowie DNS-Einträge für E-Mail-Adressen und Lync für die benutzerdefinierte Domäne zu entfernen. Wenn Sie Ihre öffentliche Website auf Microsoft 365 hosten, müssen Sie auch den CNAME-Eintrag entfernen, der auf ihn verweist.  <br/> > [!IMPORTANT]>  After you remove the MX record that routes email to this custom domain, email will stop working until you have added the domain to your new account, set up the new MX record, and set up your users. When you remove the DNS records for Lync, Lync will stop working. And after you remove the CNAME record that points to your public website, it will not be available.           [Remove the domain](remove-a-domain.md) .  <br/> |
|Richten Sie Ihre benutzerdefinierte Domäne für Ihr neues Abonnement sowie Ihre Benutzer ein.  <br/> | Richten Sie Ihr neues Abonnement ein, einschließlich der Erstellung der erforderlichen DNS-Einträge für Ihre benutzerdefinierte Domäne.  <br/>  Erstellen Sie Ihre Benutzer mit E-Mail-Adressen in Ihrer benutzerdefinierten Domäne.  <br/> |
|Übertragen Sie Daten aus dem alten Abonnement in Ihr neues Abonnement.  <br/> | Melden Sie sich in separaten Browserfenstern bei beiden Konten an:  <br/>  Right-click the Internet Explorer icon, and open two InPrivate browser windows. You can use different credentials in the two windows to sign in on both accounts.  <br/> [Übertragen von Verwaltungseinstellungen zwischen Abonnements](#email) <br/> [Übertragen von Teamwebsitestruktur und Daten](#transfer-team-site-structure-and-data) <br/> [Übertragen einer öffentlichen Websites zwischen Abonnements](#transfer-a-public-website-between-subscriptions) <br/> [Übertragen von Verwaltungseinstellungen zwischen Abonnements](#email) <br/> |
|Kündigen Sie das Abonnement für den Plan, mit dem Sie fertig sind, indem Sie den Microsoft-Support für Microsoft 365 anrufen.  <br/> | Stellen Sie sicher, dass Ihr neues Abonnement funktioniert und alle Daten übertragen wurden.  <br/>  [Wenden Sie sich an den Kundendienst](../contact-support-for-business-products.md) , um Ihr altes Abonnement zu kündigen.  <br/> |

## <a name="transfer-administrative-settings-between-subscriptions"></a>Übertragen von Verwaltungseinstellungen zwischen Abonnements

Wechseln Sie in den einzelnen Konten zu den folgenden Seiten, und richten Sie das neue Konto auf Basis der Einstellungen des alten Kontos ein.
  
Wenn Sie Daten von Microsoft 365 an Microsoft 365 mittelständisches Unternehmen oder Microsoft 365 Enterprise übertragen, sind die Administratorseiten unterschiedlich strukturiert. Schauen Sie sich ein [Video an: Einführung in Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365/admin/), und wechseln Sie zu den folgenden Stellen, um die Administratoreinstellungen zu betrachten.
  
Für Microsoft 365 Enterprise und Microsoft 365 mittelständisches Unternehmen:
  
|**Ort**|**Zweck**|
|:-----|:-----|
|**Administrator** \> **Microsoft 365** \> **Diensteinstellungen** <br/> |Wählen Sie jede Registerkarte für Einstellungen für e-Mail, Websites, lync, Benutzer Software, Kennwörter, Community, Rights Management und Mobile aus.  <br/> |
|**Admin** \> **Exchange** <br/> | Exchange Online-Einstellungen  <br/> |
|**Admin** \> **SharePoint** <br/> | SharePoint Online-Einstellungen  <br/> |
|**Administrator** \> **Skype for Business** <br/> |Zusätzliche Skype for Business Einstellungen  <br/> |

Für Microsoft 365 Small Business
  
|**Ort**|**Zweck**|
|:-----|:-----|
|**Admin** \> **Organisationsweite Einstellungen verwalten** <br/> |Verwaltungseinstellungen  <br/> |

## <a name="transfer-a-public-website-between-subscriptions"></a>Übertragen einer öffentlichen Websites zwischen Abonnements

Wenn Sie eine öffentliche Website auf Microsoft 365 gehostet haben, müssen Sie Sie speichern und neu in Ihrem neuen Abonnement erstellen.
  
> [!NOTE]
> If your public website is hosted at a DNS hosting provider, no changes are required. It will not be affected by your transition.
  
Informationen zum Speichern einer Dokumentbibliothek oder von Listeninhalten aus einer SharePoint Online-Umgebung auf Dateifreigaben oder einem lokalen Computer finden Sie unter [Manuelle Migration von SharePoint Online-Inhalten](https://go.microsoft.com/fwlink/p/?LinkId=402910).
  
> [!NOTE]
> Die App für die Migration der öffentlichen Website kann keine Daten in ein anderes Abonnement übertragen.
  
## <a name="transfer-team-site-structure-and-data"></a>Übertragen von Teamwebsitestruktur und Daten

Es gibt mehrere Möglichkeiten zum Speichern oder Übertragen von Teamwebsitedaten:
  
- Sie können die alte Website als Vorlage speichern und die Vorlage in die neue Website importieren.

- Zum Übertragen von Dokumenten müssen Sie zunächst manuell Ihre Hierarchie auf der neuen Website neu erstellen. Sie können dann beide SharePoint-Teamwebsites zur gleichen Zeit öffnen, beide Dokumentbibliotheken mit Windows-Explorer öffnen und die Dokumente kopieren und einfügen. Weitere Informationen finden Sie im [Video: Kopieren oder Verschieben von Bibliotheksdateien mit dem Befehl "Mit Explorer öffnen"](https://support.microsoft.com/office/c7c20284-bc94-47f4-9728-d28e9daf0790).

- Speichern Sie zum Übertragen von Listendaten eine [Listenvorlage](https://support.microsoft.com/office/c3884ad1-bc49-44b8-b3d6-3bc6a01eb393), und verwenden Sie die gespeicherte Vorlage, um die Liste auf der neuen Website neu zu erstellen.

- Informationen zum Speichern einer Dokumentbibliothek oder zum Auflisten von Inhalten aus einer SharePoint Online Umgebung (OneDrive für Unternehmen oder Teamwebsites) in Dateifreigaben oder auf einem lokalen Computer finden Sie unter [Informationen zur manuellen Migration von SharePoint Online Inhalten](https://support.microsoft.com/kb/2783484).

## <a name="transfer-users-data-between-subscriptions"></a>Übertragen von Benutzerdaten zwischen Abonnements

### <a name="email"></a>E-Mail:

Ask users to [move their email, contacts, tasks, and calendar information](https://support.microsoft.com/office/0996ece3-57c6-49bc-977b-0d1892e2aacc) after you set up your new subscription. They can get to their old email by using their initial user name, such as sue@contoso.onmicrosoft.com.
  
### <a name="onedrive-for-business-data"></a>OneDrive for Business-Daten:

Bitten Sie die Benutzer, [OneDrive für Unternehmen Inhalte auf Ihren Computer](https://support.microsoft.com/office/59b1de2b-519e-4d3a-8f45-51647cf291cd)zu kopieren/zu synchronisieren, und fügen Sie Sie dann Ihrem neuen Abonnement wieder hinzu.
