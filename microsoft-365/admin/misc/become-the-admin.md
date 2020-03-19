---
title: Ausführen einer internen Übernahme durch den Administrator in Office 365
f1.keywords:
- CSH
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b9707ec8-2247-4e25-9bad-f11ddbc686e4
description: Erfahren Sie, wie Sie überprüfen, ob Ihr e-Mail-und Domänenbesitz einen nicht verwalteten Mandanten in Office 365 übernimmt.
ms.openlocfilehash: 0f7932b9ba727db62f81ac15b99a5f5ca276f09f
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2020
ms.locfileid: "42857403"
---
# <a name="perform-an-internal-admin-takeover-in-office-365"></a>Ausführen einer internen Übernahme durch den Administrator in Office 365

 **[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen. 

Wenn Sie ein Administrator sind und einen nicht verwalteten Mandanten übernehmen möchten, der von einer Self-Service-Benutzeranmeldung erstellt wurde, können Sie dies mit einer internen Übernahme durch den Administrator tun.

> [!NOTE]
> Eine Self-Service-Registrierung für einen beliebigen cloudbasierten Dienst, der Azure AD verwendet, fügt den Benutzer einem nicht verwalteten oder "Shadow"-Azure AD Verzeichnis hinzu und erstellt einen nicht verwalteten Mandanten. Ein nicht verwalteter Mandant ist ein Verzeichnis ohne globalen Administrator. Informationen zum ermitteln, ob ein Mandant verwaltet oder nicht verwaltet wird, finden Sie unter [bestimmen des Mandanten Typs](https://docs.microsoft.com/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type). 
  
## <a name="step-1-verify-your-email-address"></a>Schritt 1: Überprüfen Ihrer e-Mail-Adresse

> [!NOTE]
> Wenn Self-Service in Ihrem Mandanten aktiviert ist, können Benutzer kostenlos Dienste wie Power BI selbst abonnieren. Bei diesen Schritten wird davon ausgegangen, dass ein Self-Service-Benutzer Abonnement den nicht verwalteten Mandanten erstellt hat, den Sie als Administrator übernehmen möchten. Im ersten Schritt erstellen Sie einen Benutzerkontext im nicht verwalteten Mandanten, indem Sie Power BI verwenden, um den Übernahme Pfad des Administrators zu illustrieren.

1. Wenn Sie sich für Power BI registrieren möchten, wechseln Sie zur [Power BI-Website](https://powerbi.com) , **und wählen Sie ﻿kostenlose** > **Testversion** starten (in Freigabe mit Power BI pro Box) aus. 

2. Registrieren Sie sich mit einem Benutzerkonto, das den Domänennamen Ihrer Organisation (like `powerbiadmin@contoso.com`) verwendet. Wenn Ihr Konto bereits verwendet wird, melden Sie sich mit Ihrem aktuellen Kennwort an.

3. Überprüfen Sie Ihre e-Mails auf den **Verifizierungscode** , und geben Sie den Code zum Überprüfen Ihrer e-Mail-Adresse ein.
    
## <a name="step-2-create-a-new-account"></a>Schritt 2: Erstellen eines neuen Kontos

1. Wenn Sie den Überprüfungscode eingeben, werden Sie auf eine Seite gebracht, auf der Sie ein neues Konto erstellen können. 
    
2. Geben Sie die Felder Benutzername und Kennwort mit dem Konto ein, das Sie verwenden möchten, und wählen Sie dann **Start**aus. 
    
## <a name="step-3-verify-domain-ownership-and-become-the-admin"></a>Schritt 3: Überprüfen des Domänenbesitzes und als Administrator

1. Der Assistent zum Ausführen **des Administrators** wird geöffnet. Wenn der Assistent nicht gestartet wird, suchen Sie nach der **Administrator** Kachel, und wählen Sie Sie aus. 

2. Wählen Sie **Ja aus, ich möchte der Administrator sein**.

3. Stellen Sie sicher, dass Sie die Domäne besitzen, die Sie übernehmen möchten, indem Sie Ihrer Domänenregistrierungsstelle einen TXT-Eintrag hinzufügen. Der Assistent gibt Ihnen den TXT-Eintrag, der hinzugefügt werden soll, sowie einen Link zur Website Ihrer Registrierungsstelle sowie einen Link zu Schritt-für-Schritt-Anweisungen.
    
4. Nachdem Sie den TXT-Eintrag zur Registrierungsstelle hinzugefügt haben, kehren Sie zum Assistenten zurück, und wählen Sie **OK, ich habe den Eintrag hinzugefügt**.
    
> [!NOTE]
> Die Übernahme des Shadow-Mandanten wirkt sich nicht auf vorhandene Informationen oder Dienste aus. Wenn sich jedoch Benutzer in der Domäne für Dienste angemeldet haben, für die eine Lizenz erforderlich ist, werden Sie aufgefordert, Lizenzen für Sie im Rahmen der Übernahme der Administratorrolle zu erwerben. Sie können Lizenzen hinzufügen oder entfernen, sobald der Administrator-Setup-Vorgang abgeschlossen ist. 
  
## <a name="related-articles"></a>Verwandte Artikel

YouTube: [3 steps to do an IT Admin Takeover for Power BI and Office 365](https://www.youtube.com/watch?v=xt5EsrQBZZk) ("3 Schritte zur Übernahme der IT-Administratorrolle für Power BI und Office 365", in englischer Sprache)

[Übernahme von Administratoren in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/domains-admin-takeover)

[Hilfe zu Office 365-Domänen erhalten](../get-help-with-domains/get-help-with-domains.yml)

[Verwenden von Self-Service-Registrierung in Ihrer Organisation](self-service-sign-up.md)
  
[Grundlegendes zur Rolle des Power BI-Dienstadministrators](https://docs.microsoft.com/power-bi/service-admin-role)

