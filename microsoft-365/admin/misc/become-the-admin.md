---
title: Durchführen einer internen Administratorübernahme
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b9707ec8-2247-4e25-9bad-f11ddbc686e4
description: Erfahren Sie, wie Sie Ihren E-Mail- und Domänenbesitz überprüfen, um einen nicht verwalteten Mandanten zu übernehmen, der durch eine Self-Service-Benutzerregistrierung in einem Microsoft 365.
ms.openlocfilehash: c37bf153edf39f53b5c10f020b0cbb8d630eb4a6
ms.sourcegitcommit: b0d3abbccf4dd37e32d69664d3ebc9ab8dea760d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/21/2021
ms.locfileid: "52593933"
---
# <a name="perform-an-internal-admin-takeover"></a>Durchführen einer internen Administratorübernahme

 **[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.yml)**, wenn Sie nicht finden, wonach Sie suchen. 

Wenn Sie ein Administrator sind und einen nicht verwalteten Mandanten übernehmen möchten, der durch eine Self-Service-Benutzer-Anmeldung erstellt wurde, können Sie dies mit einer internen Administratorübernahme tun.

> [!NOTE]
> Eine Self-Service-Anmeldung für jeden Clouddienst, der Azure AD verwendet, fügt den Benutzer einem nicht verwalteten Azure AD-Verzeichnis oder einem "Schatten" hinzu und erstellt einen nicht verwalteten Mandanten. Ein nicht verwalteter Mandant ist ein Verzeichnis ohne globalen Administrator. Informationen dazu, ob ein Mandant verwaltet oder nicht verwaltet wird, finden Sie unter [Determining Tenant Type](/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type). 
  
## <a name="step-1-verify-your-email-address"></a>Schritt 1: Überprüfen Ihrer E-Mail-Adresse

> [!NOTE]
> Wenn self-service in Ihrem Mandanten aktiviert ist, können Benutzer kostenlose Dienste, z. B. Power BI, selbst abonnieren. Bei diesen Schritten wird davon ausgegangen, dass ein Self-Service-Benutzerabonnement den nicht verwalteten Mandanten erstellt hat, den Sie als Administrator übernehmen möchten. Im ersten Schritt erstellen Sie einen Benutzerkontext im nicht verwalteten Mandanten, indem Sie Power BI verwenden, um den Administratorübernahmepfad zu veranschaulichen.

1. Um sich für Power BI zu registrieren, wechseln Sie zur [Power BI-Website,](https://powerbi.com) und wählen Sie **kostenlose** Testversion starten (im Feld Freigeben mit  >   Power BI Pro aus). 

2. Registrieren Sie sich mit einem Benutzerkonto, das den Domänennamen Ihrer Organisation verwendet (z. B. `powerbiadmin@contoso.com` ). Wenn Ihr Konto bereits verwendet wird, melden Sie sich mit Ihrem aktuellen Kennwort an.

3. Überprüfen Sie Ihre E-Mail auf den **Überprüfungscode,** und geben Sie den Code ein, um Ihre E-Mail-Adresse zu überprüfen.
    
## <a name="step-2-create-a-new-account"></a>Schritt 2: Erstellen eines neuen Kontos

1. Wenn Sie den Überprüfungscode eingeben, werden Sie auf eine Seite gebracht, auf der Sie ein neues Konto erstellen können. 
    
2. Füllen Sie die Felder Benutzername und Kennwort mit dem Konto aus, das Sie verwenden möchten, und wählen Sie **dann Start aus.** 
    
## <a name="step-3-verify-domain-ownership-and-become-the-admin"></a>Schritt 3: Überprüfen des Domänenbesitzes und Administrator werden

1. Der **Assistent Zum Administrator werden** wird geöffnet. Wenn der Assistent nicht gestartet wird, suchen Sie nach der **Kachel Administrator,** und wählen Sie sie aus. 

2. Wählen **Sie Ja aus, ich möchte der Administrator sein.**

3. Vergewissern Sie sich, dass Sie derEn Domänen besitzen, die Sie übernehmen möchten, indem Sie Ihrer Domänenregistrierungsstelle einen TXT-Eintrag hinzufügen. Der Assistent gibt Ihnen den hinzuzufügende TXT-Eintrag sowie einen Link zur Website Ihrer Registrierungsstelle sowie einen Link zu schrittweisen Anweisungen.
    
4. Nachdem Sie den TXT-Eintrag zur Registrierungswebsite hinzugefügt haben, kehren Sie zum Assistenten zurück, und wählen Sie **Ok aus, ich habe den Eintrag hinzugefügt.**
    
> [!NOTE]
> Die Übernahme des Schatten-Mandanten wirkt sich nicht auf vorhandene Informationen oder Dienste aus. Wenn sich jedoch Benutzer in der Domäne für Dienste angemeldet haben, für die eine Lizenz erforderlich ist, werden Sie aufgefordert, Lizenzen für sie zu erwerben, wenn Sie die Administratorrolle übernehmen. Sie können Lizenzen erwerben oder entfernen, sobald der Administratoreinrichtungsprozess abgeschlossen ist.
  
## <a name="related-content"></a>Verwandte Inhalte

YouTube: [3 Schritte zum Ausführen einer Übernahme](https://www.youtube.com/watch?v=xt5EsrQBZZk) von IT-Administratoren für Power BI und Microsoft 365 (Video)

[Admin-Übernahme in Azure AD](/azure/active-directory/users-groups-roles/domains-admin-takeover) (Artikel)

[Verwenden der Self-Service-Anmeldung in Ihrer Organisation](self-service-sign-up.md) (Artikel)
  
[Grundlegendes zur Power BI Dienstadministratorrolle](/power-bi/service-admin-role) (Artikel)