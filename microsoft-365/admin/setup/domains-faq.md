---
title: Häufig gestellte Fragen (FAQ) zu Domänen
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
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 1272bad0-4bd4-4796-8005-67d6fb3afc5a
description: Erfahren Sie mehr über Domänen, indem Sie Antworten auf Ihre häufig gestellten Fragen finden.
ms.openlocfilehash: fe602c45059be1b273b7ebe3a11cd91adf89a479
ms.sourcegitcommit: 260bbb93bbda62db9e88c021ccccfa75ac39a32e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2020
ms.locfileid: "46845844"
---
# <a name="domains-faq"></a>FAQ zu Domänen

::: moniker range="o365-21vianet"

> [!NOTE]
> Das Admin Center wird geändert. Wenn Ihre Erfahrung nicht den hier aufgeführten Details entspricht, lesen Sie [über das neue Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

Dieser Artikel enthält Antworten auf häufig gestellte Fragen zu Domänen in Microsoft 365.

Wenn Sie keine Antwort auf Ihre Frage finden können, lassen Sie es uns wissen, indem Sie einen Kommentar hinterlassen, den wir der Liste hinzufügen.

Inhalt dieses Artikels

- [Was ist MX-Priorität?](#what-is-mx-priority)
- [Wie kann ich SPF-Einträge für meine Domäne überprüfen?](#how-can-i-validate-spf-records-for-my-domain)
- [Was ist ein Domänenname?](#what-is-a-domain-name)
- [Was geschieht, wenn mein DNS-Anbieter bestimmte Eintragstypen nicht unterstützt?](#what-happens-if-my-dns-provider-doesnt-support-certain-record-types)
- [Wie kann ich die Standarddomäne in Microsoft 365 festlegen oder ändern?](#how-do-i-set-or-change-the-default-domain-in-microsoft-365)
- [Kann ich Microsoft 365 benutzerdefinierte Unterdomänen oder mehrere Domänen hinzufügen?](#can-i-add-custom-subdomains-or-multiple-domains-to-microsoft-365)
- [Wie übertrage ich eine Domäne von Microsoft 365 auf einen anderen Host?](#how-do-i-transfer-a-domain-from-microsoft-365-to-another-host)
- [Warum habe ich eine Domäne des Typs "onmicrosoft.com"?](#why-do-i-have-an-onmicrosoftcom-domain)
- [Warum habe ich eine "onmicrosoft.de"-Domäne?](#why-do-i-have-an-onmicrosoftde-domain)
- [Wie kann ich meinen gemeinnützigen oder Bildungsstatus überprüfen?](#how-do-i-verify-my-nonprofit-or-education-status)
    
## <a name="what-is-mx-priority"></a>Was ist MX-Priorität?

E-Mail wird an MX-Server (Mail Exchange) mit der niedrigsten Einstellungsnummer (d. h. der höchsten Priorität) übermittelt. Deshalb muss der MX-Eintrag, den Sie für das Routing von E-Mail nutzen, die niedrigste Einstellungsnummer haben (in der Regel 0 oder die Priorität  *Hoch*  ). 
  
- Wenn Sie einen MX-Eintrag erstellen, verlangen die meisten DNS-Hostinganbieter, dass Sie die Einstellungsnummer festlegen.
    
- Bei einigen heißt das Feld  *Einstellung*  , bei anderen  *Priorität*  . 
    
- Einige verlangen einen Wert und andere die Auswahl von  *Niedrig*  ,  *Mittel*  oder  *Hoch*  . 
    
- Wenn Sie nur über einen MX-Eintrag verfügen, spielt der Wert für "Priorität" oder "Einstellung" keine Rolle.
    
- Wenn Sie über mehrere verfügen, stellen Sie sicher, dass der MX-Eintrag für das E-Mail-Routing eine höhere Priorität als derjenige hat, der zum Überprüfen genutzt wird, ob Ihnen die Domäne gehört.
    
## <a name="how-can-i-validate-spf-records-for-my-domain"></a>Wie kann ich SPF-Einträge für meine Domäne überprüfen?

Es ist wichtig, dass Sie  **nur einen TXT-Eintrag für SPF**haben oder erstellen. Wenn Sie bereits einen SPF-Eintrag haben, sollten Sie die neuen Microsoft 365-Werte an diese anfügen, anstatt eine neue zu erstellen. Nachdem Sie den SPF-Eintrag für Microsoft e-Mail hinzugefügt oder aktualisiert haben, sollten Sie überprüfen, ob die Syntax für eines dieser Tools richtig ist: 
  
- [SPF Record Testing Tools](http://www.kitterman.com/spf/validate.html)
    
- [SPF Surveyor](https://dmarcian.com/spf-survey/)
    
- [Dig Web Interface](http://digwebinterface.com/)

## <a name="what-is-a-domain-name"></a>Was ist ein Domänenname?

Eine Domäne ist ein eindeutiger Name, der in E-Mail-Adressen hinter dem **@** -Zeichen und in Internetadressen hinter **www.** angezeigt wird. Er besteht normalerweise aus dem Namen Ihrer Organisation und einem standardmäßigen Internetsuffix, z. B.  *ihrunternehmen.com*  oder  *musikhochschule.edu*  . 
  
Die Verwendung einer benutzerdefinierten Domäne wie "**Rob \@ contoso.com**" mit Microsoft 365 kann dazu beitragen, Glaubwürdigkeit und Anerkennung für Ihre Marke zu schaffen. 
  
Sie können [eine Domäne in Microsoft 365 kaufen, und wir werden Sie automatisch](../get-help-with-domains/buy-a-domain-name.md)einrichten, oder Sie können eine ihrer Besitzer aus einer Domänenregistrierungsstelle kaufen oder holen.
    
## <a name="what-happens-if-my-dns-provider-doesnt-support-certain-record-types"></a>Was geschieht, wenn mein DNS-Anbieter bestimmte Eintragstypen nicht unterstützt?

Wenn Sie Ihre eigenen DNS-Einträge verwalten und Ihr DNS-Host nicht alle DNS-Einträge unterstützt, die von Microsoft 365 benötigt werden, funktionieren einige Features von Microsoft 365 nicht. Wir empfehlen, in diesem Fall Ihre Domäne zu übertragen, und zwar zu einer Domänenregistrierungsstelle, die alle erforderlichen DNS-Einträge unterstützt.
  
Anbieter, die alle erforderlichen DNS-Einträge unterstützen:
  
- Dynadot
    
- eNomCentral
    
- Europe Registry
    
- GoDaddy
    
- Hover
    
- MyHosting.com
    
- Name.com
    
- Nearly Free Speech
    
- Nettica
    
- Network Information Center (NIC)
    
- Network Solutions
    
- Register.com
  
## <a name="how-do-i-set-or-change-the-default-domain-in-microsoft-365"></a>Wie kann ich die Standarddomäne in Microsoft 365 festlegen oder ändern?

Sie müssen über mindestens eine benutzerdefinierte Domäne verfügen, die Sie zu Microsoft 365 hinzugefügt haben, bevor Sie eine Standarddomäne auswählen können.

::: moniker range="o365-worldwide"

1. Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.

::: moniker-end

::: moniker range="o365-germany"

1. Wechseln Sie im Admin Center zur Seite **Einstellungen** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domänen</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. Wechseln Sie im Admin Center zur Seite **Einstellungen** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domänen</a>.

::: moniker-end
    
2. Wählen Sie auf der Seite **Domänen** die Domäne aus, die Sie als Standard für neue e-Mail-Adressen festlegen möchten. 
    
3. Wählen Sie **Als Standard festlegen** aus.
    
::: moniker range="o365-worldwide"

Sie können den Namen der ursprünglichen Domäne  *.onmicrosoft.com*  nicht ändern. 

::: moniker-end

::: moniker range="o365-germany"

Sie können den Namen ihrer ursprünglichen  *. onmicrosoft.de-*  Domäne nicht ändern. 

::: moniker-end

::: moniker range="o365-21vianet"

Sie können den Namen ihrer ursprünglichen  *. Partner.onmschina.cn-*  Domäne nicht ändern. 

::: moniker-end

## <a name="can-i-add-custom-subdomains-or-multiple-domains-to-microsoft-365"></a>Kann ich Microsoft 365 benutzerdefinierte Unterdomänen oder mehrere Domänen hinzufügen?

::: moniker range="o365-worldwide"

Ja. Zum Hinzufügen von Unterdomänen müssen Sie Ihre eigenen DNS-Einstellungen auf der Website Ihrer Registrierungsstelle verwalten. Wenn Sie Microsoft Ihre DNS-Einstellungen mit NS-Datensätzen verwalten lassen oder wenn Sie die Domäne von Microsoft erworben haben, können Sie keine Unterdomänen hinzufügen.

::: moniker-end

::: moniker range="o365-germany"

Ja! Zum Hinzufügen von Unterdomänen müssen Sie Ihre eigenen DNS-Einstellungen auf der Website Ihrer Registrierungsstelle verwalten. Wenn Sie Microsoft Ihre DNS-Einstellungen mit NS-Datensätzen verwalten lassen oder wenn Sie die Domäne von Microsoft erworben haben, können Sie keine Unterdomänen hinzufügen.

::: moniker-end

::: moniker range="o365-21vianet"

Ja! Zum Hinzufügen von Unterdomänen müssen Sie Ihre eigenen DNS-Einstellungen auf der Website Ihrer Registrierungsstelle verwalten. Wenn Sie 21Vianet Ihre DNS-Einstellungen mit NS-Datensätzen verwalten lassen, können Sie keine Unterdomänen hinzufügen.

::: moniker-end

In der Regel können Sie Ihrem Microsoft 365-Abonnement bis zu 900 Domänen hinzufügen.
  
Sie können beispielsweise die Domänen "contoso.com" und "contosomarketing.com" und dann die Unterdomänen "www.contoso.com", "www.partner.contoso.com", "www.partner.marketing.contoso.com" usw. hinzufügen.
  
Wenn Sie eine Unterdomäne hinzufügen, wird Sie automatisch basierend auf der überprüften übergeordneten Domäne überprüft.
  
Wenn Sie Microsoft 365 mehrere Domänen hinzufügen, können Sie alle Dienste (wie e-Mail) in allen Domänen hosten, die Sie hinzugefügt haben.  *Wenn Sie Ihre e-Mail an Microsoft 365 ändern, indem Sie den MX-Eintrag einer Domäne aktualisieren, werden alle e-Mails, die an diese Domäne gesendet werden, mit Microsoft 365 gestartet.* 
 
::: moniker range="o365-worldwide"

> [!NOTE]
> Wenn Sie eine contoso.com-Domäne zu einem Microsoft 365-Abonnement hinzugefügt haben, können Sie auch die Unterdomäne XYZ.contoso.com zu einer anderen Microsoft 365-Organisation hinzufügen. Beim Hinzufügen der Unterdomäne werden Sie aufgefordert, einen TXT-Eintrag im DNS-Hostanbieter hinzuzufügen.

## <a name="how-do-i-transfer-a-domain-from-microsoft-365-to-another-host"></a>Wie übertrage ich eine Domäne von Microsoft 365 auf einen anderen Host?

Informationen zum Verfahren zum Übertragen einer Domäne finden Sie unter [übertragen einer Domäne von Microsoft auf einen anderen Host](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/transfer-a-domain-from-microsoft-to-another-host).

## <a name="pilot-microsoft-365-from-my-custom-domain"></a>Microsoft 365-Pilot aus benutzerdefinierter Domäne

Das Verfahren zum pilotieren von Microsoft 365-e-Mail-Funktionen von einer benutzerdefinierten Domäne zu einem Microsoft 365-Postfach finden Sie unter [Pilot Microsoft 365 aus meiner benutzerdefinierten Domäne](https://docs.microsoft.com/microsoft-365/admin/misc/pilot-microsoft-365-from-my-custom-domain).

## <a name="why-do-i-have-an-onmicrosoftcom-domain"></a>Warum habe ich eine Domäne des Typs "onmicrosoft.com"?

Microsoft 365 erstellt eine Domäne für Sie wie *contoso.onmicrosoft.com*, wenn Sie sich beim Dienst anmelden. Die Benutzer-ID, die Sie bei der Registrierung erstellen, umfasst die Domäne, wie *Alan@contoso.onmicrosoft.com*. 
  
 **Wenn Sie möchten, dass Ihre e-Mails wie *Alan \@ contoso.com*aussehen:** [kaufen Sie die Domäne](../get-help-with-domains/buy-a-domain-name.md) , oder befolgen Sie einfach die Schritte unter [Hinzufügen Ihrer Benutzer und Domäne zu Microsoft 365,](add-domain.md) Wenn Sie bereits Besitzer sind. 
  
- **Sie können die "onmicrosoft.com"-Domäne nach der Registrierung nicht umbenennen**. Wenn Sie beispielsweise "fourthcoffee.onmicrosoft.com" als ursprüngliche Domäne ausgewählt haben, können Sie sie nicht in "fabrikam.onmicrosoft.com" ändern. Um eine andere onmicrosoft.com-Domäne verwenden zu können, müssen Sie ein neues Abonnement mit Microsoft 365 starten. 
    
- **Die URL der Teamwebsite kann nicht umbenannt werden.** Ihre Teamwebsite-URL basiert auf Ihrem onmicrosoft.com-Domänennamen. Aufgrund der Funktionsweise SharePoint Online Architektur können Sie die Teamwebsite leider nicht umbenennen. 
    
- **Sie können Ihre "onmicrosoft.com"-Domäne nicht entfernen.** Microsoft 365 muss ihn beibehalten, da es hinter den Kulissen für Ihr Abonnement verwendet wird. Sie müssen diese Domäne jedoch nicht verwenden, nachdem Sie eine benutzerdefinierte Domäne hinzugefügt haben. 
    
Sie können die ursprüngliche Domäne "onmicrosoft.com" auch nach Hinzufügen Ihrer Domäne weiterverwenden. Sie funktioniert nämlich weiterhin für E-Mail und andere Dienste. Wählen Sie also selbst.
  
::: moniker-end

::: moniker range="o365-germany"
## <a name="why-do-i-have-an-onmicrosoftde-domain"></a>Warum habe ich eine "onmicrosoft.de"-Domäne?

Microsoft 365 erstellt eine Domäne für Sie wie *contoso.onmicrosoft.de*, wenn Sie sich beim Dienst anmelden. Die Benutzer-ID, die Sie bei der Registrierung erstellen, umfasst die Domäne, wie *Alan@contoso.onmicrosoft.de*. 
  
 **Wenn Sie möchten, dass Ihre e-Mails wie *Alan@contoso.de*aussehen:** [kaufen Sie die Domäne](../get-help-with-domains/buy-a-domain-name.md) , oder befolgen Sie einfach die Schritte unter [Hinzufügen Ihrer Benutzer und Domäne zu Microsoft 365,](add-domain.md) Wenn Sie bereits Besitzer sind. 
  
- **Sie können die "onmicrosoft.com"-Domäne nach der Registrierung nicht umbenennen**. Wenn beispielsweise die anfängliche Domäne, die Sie ausgewählt haben, fourthcoffee.onmicrosoft.de war, können Sie Sie nicht in fabrikam.onmicrosoft.de ändern. Um eine andere onmicrosoft.de-Domäne verwenden zu können, müssen Sie ein neues Abonnement mit Microsoft 365 starten. 
    
- **Die URL der Teamwebsite kann nicht umbenannt werden.** Ihre Teamwebsite-URL basiert auf Ihrem onmicrosoft.de-Domänennamen. Aufgrund der Funktionsweise SharePoint Online Architektur können Sie die Teamwebsite leider nicht umbenennen. 
    
- **Sie können Ihre "onmicrosoft.com"-Domäne nicht entfernen.** Microsoft 365 muss ihn beibehalten, da es hinter den Kulissen für Ihr Abonnement verwendet wird. Sie müssen diese Domäne jedoch nicht verwenden, nachdem Sie eine benutzerdefinierte Domäne hinzugefügt haben. 
    
Sie können die anfängliche onmicrosoft.de-Domäne auch dann weiterhin verwenden, wenn Sie Ihre Domäne hinzugefügt haben. Es funktioniert immer noch für e-Mail und andere Dienste, daher ist es Ihre Wahl.
  
::: moniker-end

## <a name="how-do-i-verify-my-nonprofit-or-education-status"></a>Wie kann ich meinen gemeinnützigen oder Bildungsstatus überprüfen?

1. Wählen Sie im [Admin Center](https://docs.microsoft.com/microsoft-365/admin/admin-home) die Option **Setup** aus, um den Assistenten zu starten. (Achten Sie darauf, sich zuerst bei Microsoft 365 anzumelden.) 
    
2. Um Administrator für Ihre Schule zu werden, wählen Sie die Option  **Administrator werden** in Microsoft 365 aus. 
    
3. Sie werden aufgefordert, einen txt-DNS-Eintrag auf der DNS-Hostwebsite für Ihre Domäne hinzuzufügen. Warum? Da Sie sich auf dem DNS-Host anmelden und einen Eintrag für Ihre Domäne hinzufügen, beweisen Sie Microsoft 365, dass Sie der Domänenname besitzen.
    
4. Nachdem Sie den Eintrag hinzugefügt haben, kehren Sie zum Microsoft 365-Portal zurück und bestätigen, dass Sie es hinzugefügt haben, damit Microsoft 365 überprüfen kann.
    
Sie haben eine gemeinnützige Organisation und möchten Microsoft 365 erhalten? [Stellen Sie sicher, dass Ihre Organisation qualifiziert](https://www.microsoft.com/en-us/nonprofits/eligibility) ist, und melden Sie sich für den Dienst an. 
  
Möchten Sie mehr darüber erfahren, wie Sie Administrator für Ihre Schule werden? [Erfahren Sie alles darüber](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
).