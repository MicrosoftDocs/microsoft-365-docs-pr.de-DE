---
title: Manuelles Übertragen von Daten zwischen zwei Office 365-Konten
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
search.appverid:
- MET150
- MOE150
ms.assetid: 7dc5d983-84b2-4802-bef0-602ae1780a42
description: Hier finden Sie Informationen zum manuellen übertragen von Daten zwischen zwei Office 365 Konten, wenn Sie den Plan oder den Firmennamen geändert oder mehrere Abonnements in einem kombiniert haben.
ms.openlocfilehash: 91f9d7b17a0296931393a89ff95d70628400c61a
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/02/2020
ms.locfileid: "42362150"
---
# <a name="transfer-data-manually-between-two-office-365-accounts"></a>Manuelles Übertragen von Daten zwischen zwei Office 365-Konten

[] Bereiten Sie sich darauf vor, Ihre Ärmel hochzukrempeln, und reservieren Sie einen nicht unerheblichen Zeitabschnitt in Ihrem Kalender: Die Übertragung von Daten zwischen zwei Office 365-Konten ist ein manueller, komplizierter und zeitaufwändiger Vorgang. Dies ist kein automatisierter oder unterstützter Prozess. Wir führen Sie an die Arbeit heran.
  
> [!CAUTION]
> Während des Prozesses wird es zu Ausfallzeiten kommen, bei denen e-Mails, Skype for Business und eine auf Office 365 gehostete öffentliche Website nicht funktionieren. Benutzer erhalten neue Benutzernamen und Kennwörter und sie müssen Outlook zurücksetzen.

**Übertragen Sie Daten mithilfe der Anweisungen in diesem Thema nur dann manuell, wenn eine der folgenden Situationen zutrifft:**
  
- Sie müssen zu einem Plan in einer anderen Dienstfamilie wechseln.

- Ihr Firmenname wurde geändert und Sie haben sich entscheiden, ein neues Abonnement zu erstellen und Ihre Daten zu migrieren, da Sie unterschiedliche anfängliche Domänennamen verwenden möchten.

- Sie müssen mehrere Abonnements zu einem neuen einzelnen Abonnement zusammenfassen.

> [!IMPORTANT]
> Wenn Sie [Ihren Abonnementplan ändern müssen](../../commerce/subscriptions/switch-to-a-different-plan.md) und den Assistenten zum Wechseln von Plänen verwenden können, oder wenn Sie zu einem neuen Abonnementplan in derselben Abonnementgruppe wechseln müssen, auch wenn der Assistent zum Wechseln von Plänen nicht funktioniert, müssen Sie Ihre Daten nicht manuell übertragen und es gibt keine Ausfallzeiten.

|**Aufgaben**|**Schritte**|
|:-----|:-----|
|Abonnieren Sie den Plan, in den Sie wechseln möchten.  <br/> |Wenn Sie sich registrieren, geben Sie den zu verwendenden Firmennamen in den ursprünglichen Domänennamen ein:  *ihrefirma*  .onmicrosoft.com,  *ihrefirma*  -public.sharepoint.com und  *ihrefirma*  .sharepoint.com. Sie müssen einen anderen Namen für  *ihrefirma*  verwenden, als Sie für alle vorhandenen Abonnements verwendet haben.  <br/> > [!NOTE]>  Normalerweise dauert es mindestens mehrere Monate nach dem Kündigen eines Abonnements, bis die ursprünglichen Domänennamen von unseren Systemen freigeben werden, die  *ihrefirma*  verwenden. Auch wenn Sie beabsichtigen, alle Ihre Daten Ihres alten Office 365-Abonnements zu speichern und dann dieses Abonnement kündigen, ist der alte Wert für  *ihrefirma*  nicht sofort für ein neues Abonnement verfügbar.           |
|Entfernen Sie Ihre benutzerdefinierte Domäne aus dem alten Office 365-Abonnement.  <br/> | Befolgen Sie die [erforderlichen Schritte, bevor Sie eine Domäne entfernen](remove-a-domain.md), um den Namen der Domäne aus E-Mail-Adressen von Benutzern sowie DNS-Einträge für E-Mail-Adressen und Lync für die benutzerdefinierte Domäne zu entfernen. Wenn Sie Ihre öffentliche Website auf Office 365 hosten, müssen Sie außerdem den CNAME-Eintrag entfernen, der auf sie verweist.  <br/> > [!IMPORTANT]>  Nachdem Sie den MX-Eintrag entfernt haben, der die E-Mails an diese benutzerdefinierte Domäne weiterleitet, funktioniert die E-Mail-Funktion nicht mehr, bis Sie die Domäne zu Ihrem neuen Konto hinzugefügt, den neuen MX-Eintrag sowie Ihre Benutzer eingerichtet haben. Wenn Sie die DNS-Einträge für Lync entfernen, funktioniert Lync nicht mehr. Und nachdem Sie den CNAME-Eintrag entfernen, der auf Ihre öffentliche Website verweist, ist es nicht mehr verfügbar.           [Entfernen Sie die Domäne](remove-a-domain.md) .  <br/> |
|Richten Sie Ihre benutzerdefinierte Domäne für Ihr neues Abonnement sowie Ihre Benutzer ein.  <br/> | Richten Sie Ihr neues Abonnement ein, einschließlich der Erstellung der erforderlichen DNS-Einträge für Ihre benutzerdefinierte Domäne.  <br/>  Erstellen Sie Ihre Benutzer mit E-Mail-Adressen in Ihrer benutzerdefinierten Domäne.  <br/> |
|Übertragen Sie Daten aus dem alten Abonnement in Ihr neues Abonnement.  <br/> | Melden Sie sich in separaten Browserfenstern bei beiden Konten an:  <br/>  Klicken Sie mit der rechten Maustaste auf das Internet Explorer-Symbols, und öffnen Sie zwei InPrivate-Browserfenster. Sie können in den beiden Fenstern unterschiedliche Anmeldeinformationen verwenden, um sich bei beiden Konten anzumelden.  <br/> [Übertragen von Verwaltungseinstellungen zwischen Abonnements](#email) <br/> [Übertragen von Teamwebsitestruktur und Daten](#transfer-team-site-structure-and-data) <br/> [Übertragen einer öffentlichen Websites zwischen Abonnements](#transfer-a-public-website-between-subscriptions) <br/> [Übertragen von Verwaltungseinstellungen zwischen Abonnements](#email) <br/> |
|Kündigen Sie das Abonnement für den gewünschten Plan, indem Sie den Support von Microsoft für Office 365 anrufen.  <br/> | Stellen Sie sicher, dass Ihr neues Abonnement funktioniert und alle Daten übertragen wurden.  <br/>  [Wenden Sie sich an den Kundendienst](../contact-support-for-business-products.md) , um Ihr altes Abonnement zu kündigen.  <br/> |

## <a name="transfer-administrative-settings-between-subscriptions"></a>Übertragen von Verwaltungseinstellungen zwischen Abonnements

Wechseln Sie in den einzelnen Konten zu den folgenden Seiten, und richten Sie das neue Konto auf Basis der Einstellungen des alten Kontos ein.
  
Wenn Sie Daten von Office 365 zu Office 365 Midsize Business oder Office 365 Enterprise übertragen, sind die Administratorseiten unterschiedlich strukturiert. Anschauen eines [Videos: Einführung in Office 365 Enterprise](https://support.office.com/article/11f7b4a0-1294-4e94-9238-beaae26efa9c.aspx). Wechseln Sie dann zu den folgenden Stellen, um die Administratoreinstellungen zu betrachten.
  
Für Office 365 Enterprise und Office 365 Midsize Business:
  
|**Ort**|**Zweck**|
|:-----|:-----|
|**Admin** \> **Office 365** \> **Diensteinstellungen** <br/> |Wählen Sie jede Registerkarte für Einstellungen für e-Mail, Websites, lync, Benutzer Software, Kennwörter, Community, Rights Management und Mobile aus.  <br/> |
|**Admin** \> **Exchange** <br/> | Exchange Online-Einstellungen  <br/> |
|**Admin** \> **SharePoint** <br/> | SharePoint Online-Einstellungen  <br/> |
|**Administrator** \> **Skype for Business** <br/> |Zusätzliche Skype for Business Einstellungen  <br/> |

In Office 365 Small Business
  
|**Ort**|**Zweck**|
|:-----|:-----|
|**Admin** \> **Organisationsweite Einstellungen verwalten** <br/> |Verwaltungseinstellungen  <br/> |

## <a name="transfer-a-public-website-between-subscriptions"></a>Übertragen einer öffentlichen Websites zwischen Abonnements

Wenn Sie über eine öffentliche Website verfügen, die auf Office 365 gehostet wird, müssen Sie sie speichern und für Ihr neues Abonnement neu erstellen.
  
> [!NOTE]
> Wenn Ihre öffentliche Website bei einem DNS-Hostinganbieter gehostet wird, sind keine Änderungen erforderlich. Sie ist von Ihrem Wechsel nicht betroffen.
  
Informationen zum Speichern einer Dokumentbibliothek oder von Listeninhalten aus einer SharePoint Online-Umgebung auf Dateifreigaben oder einem lokalen Computer finden Sie unter [Manuelle Migration von SharePoint Online-Inhalten](https://go.microsoft.com/fwlink/p/?LinkId=402910).
  
> [!NOTE]
> Die App für die Migration der öffentlichen Website kann keine Daten in ein anderes Abonnement übertragen.
  
## <a name="transfer-team-site-structure-and-data"></a>Übertragen von Teamwebsitestruktur und Daten

Es gibt mehrere Möglichkeiten zum Speichern oder Übertragen von Teamwebsitedaten:
  
- Sie können die alte Website als Vorlage speichern und die Vorlage in die neue Website importieren.

- Zum Übertragen von Dokumenten müssen Sie zunächst manuell Ihre Hierarchie auf der neuen Website neu erstellen. Sie können dann beide SharePoint-Teamwebsites zur gleichen Zeit öffnen, beide Dokumentbibliotheken mit Windows-Explorer öffnen und die Dokumente kopieren und einfügen. Weitere Informationen finden Sie im [Video: Kopieren oder Verschieben von Bibliotheksdateien mit dem Befehl "Mit Explorer öffnen"](https://support.office.com/article/c27bc6f3-7b38-4c29-b947-5d00c7153384.aspx).

- Speichern Sie zum Übertragen von Listendaten eine [Listenvorlage](https://support.office.com/article/c3884ad1-bc49-44b8-b3d6-3bc6a01eb393.aspx), und verwenden Sie die gespeicherte Vorlage, um die Liste auf der neuen Website neu zu erstellen.

- Informationen zum Speichern einer Dokumentbibliothek oder zum Auflisten von Inhalten aus einer SharePoint Online Umgebung (OneDrive für Unternehmen oder Teamwebsites) in Dateifreigaben oder auf einem lokalen Computer finden Sie unter [Informationen zur manuellen Migration von SharePoint Online Inhalten](https://support.microsoft.com/kb/2783484).

## <a name="transfer-users-data-between-subscriptions"></a>Übertragen von Benutzerdaten zwischen Abonnements

### <a name="email"></a>E-Mail:

Bitten Sie die Benutzer, [Ihre E-Mails, Kontakte, Aufgaben und Kalenderdaten zu verschieben](https://support.office.com/article/0996ece3-57c6-49bc-977b-0d1892e2aacc.aspx), nachdem Sie Ihr neues Abonnement eingerichtet haben. Sie können auf ihre alten E-Mails zugreifen, indem sie ihren ursprünglichen Benutzernamen verwenden, z. B. susanne@contoso.onmicrosoft.com.
  
### <a name="onedrive-for-business-data"></a>OneDrive for Business-Daten:

Bitten Sie die Benutzer, [OneDrive für Unternehmen Inhalte auf Ihren Computer](https://support.office.com/article/59b1de2b-519e-4d3a-8f45-51647cf291cd.aspx)zu kopieren/zu synchronisieren, und fügen Sie Sie dann Ihrem neuen Abonnement wieder hinzu.
