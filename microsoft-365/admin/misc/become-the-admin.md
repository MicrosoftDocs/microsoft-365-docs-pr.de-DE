---
title: Durchführen einer internen Übernahme durch den Administrator
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b9707ec8-2247-4e25-9bad-f11ddbc686e4
description: Erfahren Sie, wie Sie Ihren E-Mail- und Domänenbesitz überprüfen, um einen nicht verwalteten Mandanten zu übernehmen, der von einer Self-Service-Benutzeranmeldung in Microsoft 365 erstellt wurde.
ms.openlocfilehash: f6378c708e0533c2da2d38bfe5eb8009515423c7
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393847"
---
# <a name="perform-an-internal-admin-takeover"></a>Durchführen einer internen Übernahme durch den Administrator

 **[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.yml)**, wenn Sie nicht finden, wonach Sie suchen. 

Wenn Sie ein Administrator sind und einen nicht verwalteten Mandanten übernehmen möchten, der von einer Self-Service-Benutzeranmeldung erstellt wurde, können Sie dies mit einer internen Administratorübernahme tun.

> [!NOTE]
> Eine Self-Service-Registrierung für jeden Clouddienst, der Azure AD verwendet, fügt den Benutzer einem nicht verwalteten oder "Schatten" Azure AD-Verzeichnis hinzu und erstellt einen nicht verwalteten Mandanten. Ein nicht verwalteter Mandant ist ein Verzeichnis ohne globalen Administrator. Informationen dazu, ob ein Mandant verwaltet oder nicht verwaltet wird, finden Sie unter [Ermitteln des Mandantentyps.](/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type) 
  
## <a name="step-1-verify-your-email-address"></a>Schritt 1: Überprüfen Ihrer E-Mail-Adresse

> [!NOTE]
> Wenn Self-Service in Ihrem Mandanten aktiviert ist, können Benutzer kostenlose Dienste wie Power BI selbst abonnieren. Bei diesen Schritten wird davon ausgegangen, dass ein Self-Service-Benutzerabonnement den nicht verwalteten Mandanten erstellt hat, den Sie als Administrator übernehmen möchten. Im ersten Schritt erstellen Sie einen Benutzerkontext im nicht verwalteten Mandanten mithilfe von Power BI, um den Übernahmepfad des Administrators zu veranschaulichen.

1. To sign up for Power BI, go to the [Power BI site](https://powerbi.com) and select **Start Free** Start  >  **free trial** (in Share with Power BI Pro box). 

2. Registrieren Sie sich mit einem Benutzerkonto, das den Domänennamen Ihrer Organisation verwendet (z. `powerbiadmin@contoso.com` B. ). Wenn Ihr Konto bereits verwendet wird, melden Sie sich mit Ihrem aktuellen Kennwort an.

3. Überprüfen Sie Ihre E-Mail auf den **Überprüfungscode,** und geben Sie den Code ein, um Ihre E-Mail-Adresse zu überprüfen.
    
## <a name="step-2-create-a-new-account"></a>Schritt 2: Erstellen eines neuen Kontos

1. Wenn Sie den Überprüfungscode eingeben, werden Sie zu einer Seite gebracht, auf der Sie ein neues Konto erstellen können. 
    
2. Füllen Sie die Benutzernamen- und Kennwortfelder mit dem Konto aus, das Sie verwenden möchten, und wählen Sie dann **Start** aus. 
    
## <a name="step-3-verify-domain-ownership-and-become-the-admin"></a>Schritt 3: Überprüfen des Domänenbesitzes und Administrator werden

1. Der Assistent **zum Administrator** wird geöffnet. Wenn der Assistent nicht gestartet wird, suchen Sie nach der **Administratorkachel,** und wählen Sie sie aus. 

2. Wählen Sie **"Ja", ich möchte der Administrator sein.**

3. Stellen Sie sicher, dass Sie die Domäne besitzen, die Sie übernehmen möchten, indem Sie Ihrer Domänenregistrierungsstelle einen TXT-Eintrag hinzufügen. Der Assistent gibt Ihnen den hinzuzufügenden TXT-Eintrag sowie einen Link zur Website Ihrer Registrierungsstelle sowie einen Link zu schrittweisen Anweisungen.
    
4. Nachdem Sie den TXT-Eintrag zu Ihrer Registrierungsstellenwebsite hinzugefügt haben, kehren Sie zum Assistenten zurück und wählen **Sie "Okay" aus, ich habe den Datensatz hinzugefügt.**
    
> [!NOTE]
> Die Übernahme des Schattenmandanten wirkt sich nicht auf vorhandene Informationen oder Dienste aus. Wenn sich benutzer in der Domäne jedoch für Dienste angemeldet haben, die eine Lizenz erfordern, werden Sie aufgefordert, lizenzen für sie zu erwerben, als Teil der Übernahme der Administratorrolle. Sie können Lizenzen kaufen oder entfernen, sobald der Administratoreinrichtungsprozess abgeschlossen ist.
  
## <a name="related-content"></a>Verwandte Inhalte

YouTube: [3 Schritte zum Durchführen einer Übernahme durch IT-Administratoren für Power BI und Microsoft 365](https://www.youtube.com/watch?v=xt5EsrQBZZk) (Video)\
[Administratorübernahme in Azure AD](/azure/active-directory/users-groups-roles/domains-admin-takeover) (Artikel)\
[Verwenden der Self-Service-Registrierung in Ihrer Organisation](self-service-sign-up.md) (Artikel)\
[Grundlegendes zur Rolle Power BI Dienstadministrator](/power-bi/service-admin-role) (Artikel)