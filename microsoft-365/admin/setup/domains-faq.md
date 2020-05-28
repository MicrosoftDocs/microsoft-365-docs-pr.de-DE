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
description: Erfahren Sie mehr über Domänen, indem Sie Antworten auf Ihre Fragen in FAQ finden.
ms.openlocfilehash: c82d5d01d64ad01f68d0c1ba73860511aa1718aa
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44398906"
---
# <a name="domains-faq"></a>FAQ zu Domänen

::: moniker range="o365-21vianet"

> [!NOTE]
> Das Admin Center wird geändert. Wenn Ihre Erfahrung nicht den hier aufgeführten Details entspricht, lesen Sie [über das neue Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

[] In diesem Artikel finden Sie Antworten auf häufig gestellte Fragen zu Domänen in Office 365.

Wenn Sie keine Antwort auf Ihre Frage finden können, lassen Sie es uns wissen, indem Sie einen Kommentar hinterlassen, den wir der Liste hinzufügen.
    
## <a name="what-is-mx-priority"></a>Was ist MX-Priorität?

E-Mail wird an MX-Server (Mail Exchange) mit der niedrigsten Einstellungsnummer (d. h. der höchsten Priorität) übermittelt. Deshalb muss der MX-Eintrag, den Sie für das Routing von E-Mail nutzen, die niedrigste Einstellungsnummer haben (in der Regel 0 oder die Priorität  *Hoch*  ). 
  
- Wenn Sie einen MX-Eintrag erstellen, verlangen die meisten DNS-Hostinganbieter, dass Sie die Einstellungsnummer festlegen.
    
- Bei einigen heißt das Feld  *Einstellung*  , bei anderen  *Priorität*  . 
    
- Einige verlangen einen Wert und andere die Auswahl von  *Niedrig*  ,  *Mittel*  oder  *Hoch*  . 
    
- Wenn Sie nur über einen MX-Eintrag verfügen, spielt der Wert für "Priorität" oder "Einstellung" keine Rolle.
    
- Wenn Sie über mehrere verfügen, stellen Sie sicher, dass der MX-Eintrag für das E-Mail-Routing eine höhere Priorität als derjenige hat, der zum Überprüfen genutzt wird, ob Ihnen die Domäne gehört.
    
## <a name="how-can-i-validate-spf-records-for-my-domain"></a>Wie kann ich SPF-Einträge für meine Domäne überprüfen?

Es ist wichtig, dass Sie **nur einen TXT-Eintrag für SPF**haben oder erstellen. Wenn Sie bereits einen SPF-Eintrag haben, sollten Sie die neuen Office 365 Werte an ihn anfügen, anstatt einen neuen zu erstellen. Nachdem Sie den SPF-Eintrag für Microsoft e-Mail hinzugefügt oder aktualisiert haben, sollten Sie überprüfen, ob die Syntax für eines dieser Tools richtig ist: 
  
- [SPF Record Testing Tools](http://www.kitterman.com/spf/validate.html)
    
- [SPF Surveyor](https://dmarcian.com/spf-survey/)
    
- [Dig Web Interface](http://digwebinterface.com/)
    
## <a name="how-does-office-365-manage-my-dns-records"></a>Wie verwaltet Office 365 meine DNS-Einträge?

Es gibt zwei Optionen für die DNS-Verwaltung in Office 365:
  
1. Sie ändern ihre Namenservereinträge (NS), und dann kümmert sich Microsoft um alle dienstspezifischen Einträge, wie das Einrichten Ihres MX-Eintrags für e-Mail. **Empfohlen**
    
2. Sie fügen DNS-Einträge für E-Mail und andere Office 365-Dienste bei Ihrem DNS-Host selbst hinzu. **(Nur für Experten)**
    
### <a name="office-365-creates-and-hosts-the-dns-records"></a>Office 365 erstellt und hostet die DNS-Einträge 
**Vorteile** 
- Sie müssen keine Sorge haben, dass Sie bei der Eingabe der Werte in den DNS-Einträgen für Office 365-Dienste Fehler machen.  
- Sie haben mehr Flexibilität bei der Auswahl von Domänenregistrierungsstelle und DNS-Host. 
- Jeder Anbieter, bei dem Sie Ihre Namenservereinträge ändern können, kann verwendet werden, selbst wenn der Anbieter nicht alle erforderlichen Eintragstypen unterstützt.   
- Wenn Office 365 neue DNS-Einträge hinzufügt, müssen Sie keine Aktualisierungen vornehmen.  

#### <a name="disadvantages"></a>Nachteile 
- Sie können Ihre DNS-Einträge nicht ändern, um E-Mails außerhalb von Office 365 zu hosten. 
- Wenn Sie bereits eine öffentliche Website mit Ihrer Domäne als Adresse verwenden, wie etwa "www.fourthcoffee.com", müssen Sie Personen von Office 365 an diese Adresse umleiten. 
- Zum Einrichten der Umleitung ist eine statische IP-Adresse erforderlich, die für öffentliche Websites nicht immer so einfach verfügbar ist. -Wenn Ihre aktuelle Domänenregistrierungsstelle es Ihnen nicht erlaubt, die Namenservereinträge Ihrer Domäne zu ändern, müssen Sie zu einer anderen Registrierungsstelle wechseln, um diese DNS-Verwaltungsoption zu verwenden.  

 ### <a name="you-manage-the-dns-records-yourself"></a>Sie verwalten die DNS-Einträge selbst. 
 #### <a name="advantages"></a>Vorteile
- Sie steuern die DNS-Einträge für Office 365-Dienste.   
- Wenn Sie über eine öffentliche Website mit Ihrer Domäne als Adresse verfügen, wie etwa "www.fourthcoffee.com", müssen Sie sich keine Gedanken um eine Umleitung machen, damit sichergestellt ist, dass Benutzer weiterhin Ihre Website aufrufen können, nachdem Sie Ihre Domäne in Office 365 eingerichtet haben.    
- Sie haben die Flexibilität, E-Mails an einer anderen Stelle zu hosten, beispielsweise auf einem lokalen Exchange-Server.  
 
#### <a name="disadvantages"></a>Nachteile
Sie müssen die DNS-Einträge für Office 365-Dienste selbst einrichten (sofern Sie nicht über eine GoDaddy-Domäne verfügen). 
-  Wenn Ihr aktueller DNS-Host nicht alle erforderlichen Datensatztypen für Microsoft 365 unterstützt, sind einige Funktionen nicht verfügbar, und Sie müssen möglicherweise zu einem anderen DNS-Host wechseln. 
- Wenn Office 365 die Anforderungen für DNS-Einträge ändert oder neue Dienste hinzufügt, müssen Sie die Aktualisierungen bei Ihrem DNS-Host selbst durchführen. 
   
## <a name="what-is-a-domain-name"></a>Was ist ein Domänenname?


Eine Domäne ist ein eindeutiger Name, der in E-Mail-Adressen hinter dem **@** -Zeichen und in Internetadressen hinter **www.** angezeigt wird. Er besteht normalerweise aus dem Namen Ihrer Organisation und einem standardmäßigen Internetsuffix, z. B.  *ihrunternehmen.com*  oder  *musikhochschule.edu*  . 
  
Die Verwendung einer benutzerdefinierten Domäne wie "**Rob \@ contoso.com**" mit Office 365 kann dazu beitragen, Glaubwürdigkeit und Anerkennung für Ihre Marke aufzubauen. 
  
Sie können [eine Domäne in Office 365 erwerben](../get-help-with-domains/buy-a-domain-name.md), die wir dann automatisch einrichten, oder Sie können eine Domäne bei Ihrer Domänenregistrierungsstelle erwerben oder eine dort bereits erworbene Domäne übertragen.
  
## <a name="can-i-transfer-a-domain-i-purchased-from-microsoft-to-another-provider"></a>Kann ich eine von Microsoft erworbene Domäne an einen anderen Anbieter übertragen?

Ja, aber Sie können eine Office 365 Domäne erst nach 60 Tagen, nachdem Sie Sie mit Office 365 erworben haben, an eine andere Registrierungsstelle übertragen.

Beachten Sie, dass eine *Whois* -Abfrage eine Office 365 erworbene Domänenregistrierungsstelle als "Wild West Domains LLC" anzeigen kann. In Bezug auf Ihre Office 365 erworbene Domäne sollten jedoch nur Office 365 kontaktiert werden.
  
Führen Sie die nachstehenden Schritte aus, um den Code bei Office 365 zu erhalten. Wechseln Sie dann zur Website der anderen Domänenregistrierungsstelle, um die Übertragung Ihres Domänennamens an diese Registrierungsstelle einzurichten.

::: moniker range="o365-worldwide"

1. Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.

::: moniker-end

::: moniker range="o365-germany"

1. Wechseln Sie im Admin Center zur Seite **Einstellungen** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domänen</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. Wechseln Sie im Admin Center zur Seite mit den **Einstellungs** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Lizenzen</a> .

::: moniker-end
    
2. Wählen Sie auf der Seite **Domänen** die Office 365 Domäne aus, die Sie an eine andere Domänenregistrierungsstelle übertragen möchten, **und wählen Sie dann Domaintransfer**  >  **enable Domaintransfer**aus.
       
4. Führen Sie die nachstehenden Schritte aus, um die Übertragung Ihrer Domäne vorzubereiten.
    
5. Nachdem Sie den Code erhalten haben, wechseln Sie zur Website der Domänenregistrierungsstelle, bei der Sie Ihren Domänennamen verwalten möchten. Folgen Sie dann den Anweisungen der Registrierungsstelle zur Übertragung einer Domäne (suchen Sie auf deren Website nach Hilfe).
    
6. Wenn Sie den Code erneut sehen müssen, wählen Sie auf der Seite **Domäneneinstellungen** in Office 365 die Option **Autorisierungscode für die Domänen Übertragung anzeigen**aus.
    
7. Nach Abschluss der Übertragung erneuern Sie Ihre Domäne bei der neuen Domänenregistrierungsstelle.
    
8. Um den Vorgang abzuschließen, kehren Sie zur Seite Admin Center- **Domänen** zurück, und wählen Sie **vollständige Domänen Übertragung**aus. 

*Hinweis: Beachten Sie, dass Office 365 erworbenen Domänen nicht für Namen Server Änderungen oder die Übertragung der Domäne zwischen Office 365 Mandanten berechtigt sind.  Wenn eine dieser Anforderungen erforderlich ist, muss die Domänenregistrierung an eine andere Registrierungsstelle übertragen werden.*
    
## <a name="how-do-i-change-how-my-dns-records-are-managed-in-office-365"></a>Wie ändere ich die Verwaltung meiner DNS-Einträge in Office 365?

### <a name="change-dns-management-to-a-dns-host-outside-office-365"></a>Wechseln der DNS-Verwaltung auf einen DNS-Host außerhalb von Office 365
   
1. Melden Sie sich bei der Domänenregistrierungsstelle für Ihre Domäne an.
    
2. Suchen Sie den Bereich auf der Website der Registrierungsstelle, auf der Sie die Namenservereinträge aktualisieren, und aktualisieren Sie die Namenserver so, dass sie auf den DNS-Host Ihrer Domäne verweisen. (Der DNS-Host ist oft die Domänenregistrierungsstelle.)
    
3. Klicken Sie auf einen Link, um zum Setup-Assistenten für Domänen zu wechseln:

::: moniker range="o365-worldwide"

4. Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.

::: moniker-end

::: moniker range="o365-germany"

4. Wechseln Sie im Admin Center zur Seite **Einstellungen** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domänen</a>.

::: moniker-end

::: moniker range="o365-21vianet"

4. Wechseln Sie im Admin Center zur Seite **Einstellungen** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domänen</a>.

::: moniker-end
    
5. Wählen Sie auf der Seite **Domänen** die Domäne aus, die Sie wechseln möchten, und wählen Sie **DNS-Verwaltung**aus.
    
6. Wählen Sie im Setup-Assistenten für Domänen auf der Seite **richten Sie Ihre Onlinedienste** aus die Option **Ich werde meine eigenen DNS-Einträge verwalten**aus, und wählen Sie dann **weiter**aus.
    
7. Fügen Sie der Website der Registrierungsstelle die vom Assistenten vorgeschlagenen DNS-Einträge auf der Seite " **DNS-Einstellungen aktualisieren** " hinzu. 
    
8. Nachdem Sie die Datensätze hinzugefügt haben, kehren Sie zu Office 365 zurück, und wählen Sie **überprüfen**aus.
    

### <a name="change-dns-management-to-office-365"></a>Wechseln der DNS-Verwaltung zu Office 365

::: moniker range="o365-worldwide"

1. Wechseln Sie im Admin Center zur Seite mit den **Einstellungs** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a> ..

::: moniker-end

::: moniker range="o365-germany"

1. Wechseln Sie im Admin Center zur Seite **Einstellungen** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domänen</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. Wechseln Sie im Admin Center zur Seite **Einstellungen** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domänen</a>.

::: moniker-end
    
2. Wählen Sie auf der Seite **Domänen** die Domäne aus, die Sie wechseln möchten, und wählen Sie **DNS-Verwaltung**aus.
    
3. Wählen Sie im Setup-Assistenten für Domänen auf der Seite **richten Sie Ihre Onlinedienste** aus die Option **meine Onlinedienste für mich einrichten aus. (Empfohlen)**, und wählen Sie dann **weiter**aus.
    
4. Wenn Sie die Domäne noch nicht überprüft haben, führen Sie hierzu zuerst die folgenden Schritte aus.
    
5. Auf der Seite **DNS-Einstellungen aktualisieren** werden die Namenserver für Office 365 aufgelistet. Wechseln Sie zur Domänenregistrierungsstelle für Ihre Domäne, und ändern Sie die Namenserver in die Office 365-Namenserver. 
    
4. Nachdem Sie die Namenserver aktualisiert haben, **warten Sie mindestens eine Stunde**. Wählen Sie dann zurück im Assistenten in Office 365 die Option **überprüfen**aus.
    
## <a name="what-happens-if-my-dns-provider-doesnt-support-certain-record-types"></a>Was geschieht, wenn mein DNS-Anbieter bestimmte Eintragstypen nicht unterstützt?

Wenn Sie Ihre eigenen DNS-Einträge verwalten und Ihr DNS-Host nicht alle von Office 365 benötigten DNS-Einträge unterstützt, funktionieren einige der Office 365-Funktionen nicht. Wir empfehlen, in diesem Fall Ihre Domäne zu übertragen, und zwar zu einer Domänenregistrierungsstelle, die alle erforderlichen DNS-Einträge unterstützt.
  
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
    
 **Wenn keine SRV-Einträge unterstützt werden**, stehen die folgenden Office 365-Funktionen nicht zur Verfügung: 
  
- Skype for Business Online-Chat und Integration von Anwesenheitsinformationen in Outlook Web App
    
- Externe Kommunikation (Verbund) mit Skype for Business Online-Benutzern in anderen Organisationen
    
- PIC (Public Internet Connectivity) mit Skype for Business Online-Benutzern, die mit einem Microsoft-Konto (vormals Windows Live ID) angemeldet sind
    
 **Wenn mehrere CNAME-Einträge nicht unterstützt werden,** müssen Sie zwischen den folgenden Features für Skype for Business Online wählen: 
  
- E-Mail-Desktop- und mobile Clients können mit dem AutoErmittlungsdienst automatisch den Exchange Online-Dienst finden, sodass die Benutzer sich anmelden können, ohne den Servernamen eingeben zu müssen.
    
- Skype for Business Online-Desktopclients können mit dem AutoErmittlungsdienst automatisch den Skype for Business Online-Dienst finden, sodass die Benutzer sich anmelden können, ohne den Servernamen eingeben zu müssen.
    
- Mobile Skype for Business Online-Clients können mit dem AutoErmittlungsdienst automatisch den Skype for Business Online-Dienst finden, sodass die Benutzer sich anmelden können, ohne den Servernamen eingeben zu müssen.

- Microsoft Teams-Verbund mit Skype for Business, entweder lokal oder online. Weitere Informationen finden Sie unter [Vorbereiten des Netzwerks Ihrer Organisation für Microsoft Teams](https://docs.microsoft.com/microsoftteams/prepare-network).
    
 **Wenn SPF-/TXT-Einträge nicht unterstützt werden**, sind andere Personen möglicherweise in der Lage, über Ihre Domäne Spam oder andere schädliche E-Mails zu senden. Mithilfe von SPF-Einträgen werden die Server bestimmt, denen es gestattet ist, E-Mails über Ihre Domäne zu senden. 
  
## <a name="how-do-i-set-or-change-the-default-domain-in-office-365"></a>Wie kann ich die Standarddomäne in Office 365 festlegen oder ändern?

Sie müssen über mindestens eine benutzerdefinierte Domäne verfügen, die Sie Office 365 hinzugefügt haben, bevor Sie eine Standarddomäne auswählen können.

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

Sie können den Namen ihrer ursprünglichen *. onmicrosoft.de-* Domäne nicht ändern. 

::: moniker-end

::: moniker range="o365-21vianet"

Sie können den Namen ihrer ursprünglichen *. Partner.onmschina.cn-* Domäne nicht ändern. 

::: moniker-end

## <a name="can-i-add-custom-subdomains-or-multiple-domains-to-office-365"></a>Kann ich in Office 365 benutzerdefinierte Unterdomänen oder mehrere Domänen hinzufügen?

::: moniker range="o365-worldwide"

Ja! Zum Hinzufügen von Unterdomänen müssen Sie Ihre eigenen DNS-Einstellungen auf der Website Ihrer Registrierungsstelle verwalten. Wenn Sie Microsoft Ihre DNS-Einstellungen mit NS-Datensätzen verwalten lassen oder wenn Sie die Domäne von Microsoft erworben haben, können Sie keine Unterdomänen hinzufügen.

::: moniker-end

::: moniker range="o365-germany"

Ja! Zum Hinzufügen von Unterdomänen müssen Sie Ihre eigenen DNS-Einstellungen auf der Website Ihrer Registrierungsstelle verwalten. Wenn Sie Microsoft Ihre DNS-Einstellungen mit NS-Datensätzen verwalten lassen oder wenn Sie die Domäne von Microsoft erworben haben, können Sie keine Unterdomänen hinzufügen.

::: moniker-end

::: moniker range="o365-21vianet"

Ja! Zum Hinzufügen von Unterdomänen müssen Sie Ihre eigenen DNS-Einstellungen auf der Website Ihrer Registrierungsstelle verwalten. Wenn Sie 21Vianet Ihre DNS-Einstellungen mit NS-Datensätzen verwalten lassen, können Sie keine Unterdomänen hinzufügen.

::: moniker-end

Sie können Ihrem Office 365-Abonnement in der Regel bis zu 900 Domänen hinzufügen.
  
Sie können beispielsweise die Domänen "contoso.com" und "contosomarketing.com" und dann die Unterdomänen "www.contoso.com", "www.partner.contoso.com", "www.partner.marketing.contoso.com" usw. hinzufügen.
  
Wenn Sie eine Unterdomäne hinzufügen, wird Sie automatisch basierend auf der überprüften übergeordneten Domäne überprüft.
  
Wenn Sie Office 365 mehrere Domänen hinzufügen, können Sie beliebige dieser Dienste (wie E-Mail) in jeder der von Ihnen hinzugefügten Domäne hosten.  *Wenn Sie Ihr E-Mail-System in Office 365 ändern, indem Sie den MX-Eintrag der Domäne ändern, werden von nun an ALLE an diese Domäne gesendeten E-Mails an Office 365 gesendet.* 
 
::: moniker range="o365-worldwide"

> [!NOTE]
> Wenn Sie bereits eine contoso.com-Domäne zu einem Office 365 Mandanten hinzugefügt haben, können Sie auch die Unterdomäne XYZ.contoso.com zu einem anderen Office 365 Mandanten hinzufügen. Beim Hinzufügen der Unterdomäne werden Sie aufgefordert, einen TXT-Eintrag im DNS-Hostanbieter hinzuzufügen.

## <a name="why-do-i-have-an-onmicrosoftcom-domain"></a>Warum habe ich eine Domäne des Typs "onmicrosoft.com"?

Office 365 erstellt eine Domäne für Sie wie *contoso.onmicrosoft.com*, wenn Sie sich beim Dienst anmelden. Die Benutzer-ID, die Sie bei der Registrierung erstellen, umfasst die Domäne, wie *Alan@contoso.onmicrosoft.com*. 
  
 **Wenn Sie möchten, dass Ihre e-Mails wie *Alan \@ contoso.com*aussehen:** [kaufen Sie die Domäne](../get-help-with-domains/buy-a-domain-name.md) , oder befolgen Sie die Schritte unter [Hinzufügen Ihrer Benutzer und Domäne zu Office 365,](add-domain.md) Wenn Sie bereits Besitzer sind. 
  
- **Sie können die "onmicrosoft.com"-Domäne nach der Registrierung nicht umbenennen**. Wenn Sie beispielsweise "fourthcoffee.onmicrosoft.com" als ursprüngliche Domäne ausgewählt haben, können Sie sie nicht in "fabrikam.onmicrosoft.com" ändern. Um eine andere "onmicrosoft.com"-Domäne verwenden zu können, müssen Sie ein neues Abonnement bei Office 365 einrichten. 
    
- **Die URL der Teamwebsite kann nicht umbenannt werden.** Ihre Teamwebsite-URL basiert auf Ihrem onmicrosoft.com-Domänennamen. Aufgrund der Funktionsweise SharePoint Online Architektur können Sie die Teamwebsite leider nicht umbenennen. 
    
- **Sie können Ihre "onmicrosoft.com"-Domäne nicht entfernen.** Office 365 muss diese Domäne beibehalten, weil sie im Hintergrund für Ihr Abonnement verwendet wird. Sie müssen diese Domäne jedoch nicht verwenden, nachdem Sie eine benutzerdefinierte Domäne hinzugefügt haben. 
    
Sie können die ursprüngliche Domäne "onmicrosoft.com" auch nach Hinzufügen Ihrer Domäne weiterverwenden. Sie funktioniert nämlich weiterhin für E-Mail und andere Dienste. Wählen Sie also selbst.
  
::: moniker-end

::: moniker range="o365-germany"
## <a name="why-do-i-have-an-onmicrosoftde-domain"></a>Warum habe ich eine "onmicrosoft.de"-Domäne?

Office 365 erstellt eine Domäne für Sie wie *contoso.onmicrosoft.de*, wenn Sie sich beim Dienst anmelden. Die Benutzer-ID, die Sie bei der Registrierung erstellen, umfasst die Domäne, wie *Alan@contoso.onmicrosoft.de*. 
  
 **Wenn Sie möchten, dass Ihre e-Mails wie *Alan@contoso.de*aussehen:** [kaufen Sie die Domäne](../get-help-with-domains/buy-a-domain-name.md) , oder befolgen Sie die Schritte unter [Hinzufügen Ihrer Benutzer und Domäne zu Office 365,](add-domain.md) Wenn Sie bereits Besitzer sind. 
  
- **Sie können die "onmicrosoft.com"-Domäne nach der Registrierung nicht umbenennen**. Wenn beispielsweise die anfängliche Domäne, die Sie ausgewählt haben, fourthcoffee.onmicrosoft.de war, können Sie Sie nicht in fabrikam.onmicrosoft.de ändern. Um eine andere onmicrosoft.de-Domäne verwenden zu können, müssen Sie ein neues Abonnement mit Office 365 starten. 
    
- **Die URL der Teamwebsite kann nicht umbenannt werden.** Ihre Teamwebsite-URL basiert auf Ihrem onmicrosoft.de-Domänennamen. Aufgrund der Funktionsweise SharePoint Online Architektur können Sie die Teamwebsite leider nicht umbenennen. 
    
- **Sie können Ihre "onmicrosoft.com"-Domäne nicht entfernen.** Office 365 muss diese Domäne beibehalten, weil sie im Hintergrund für Ihr Abonnement verwendet wird. Sie müssen diese Domäne jedoch nicht verwenden, nachdem Sie eine benutzerdefinierte Domäne hinzugefügt haben. 
    
Sie können die anfängliche onmicrosoft.de-Domäne auch dann weiterhin verwenden, wenn Sie Ihre Domäne hinzugefügt haben. Es funktioniert immer noch für e-Mail und andere Dienste, daher ist es Ihre Wahl.
  
::: moniker-end

## <a name="how-do-i-verify-my-nonprofit-or-education-status"></a>Wie kann ich meinen gemeinnützigen oder Bildungsstatus überprüfen?

1. Wählen Sie im [Admin Center](https://docs.microsoft.com/microsoft-365/admin/admin-home) die Option **Setup** aus, um den Assistenten zu starten. (Achten Sie darauf, dass Sie sich zuerst bei Office 365 anmelden.) 
    
2. Um Administrator für Ihre Schule zu werden, wählen Sie die Option **Administrator werden** in Office 365 aus. 
    
3. Sie werden aufgefordert, einen txt-DNS-Eintrag auf der DNS-Hostwebsite für Ihre Domäne hinzuzufügen. Warum? Da Sie sich auf dem DNS-Host anmelden und einen Eintrag für Ihre Domäne hinzufügen, belegen Sie Office 365, dass Sie der Domänenname besitzen.
    
4. Nachdem Sie den Eintrag hinzugefügt haben, kehren Sie zum Office 365 Portal zurück und bestätigen, dass Sie es hinzugefügt haben, damit Office 365 überprüfen kann.
    
Sie haben eine gemeinnützige Organisation und möchten Office 365 erhalten? [Stellen Sie sicher, dass Ihre Organisation qualifiziert](https://www.microsoft.com/en-us/nonprofits/eligibility) ist, und melden Sie sich für den Dienst an. 
  
Möchten Sie mehr darüber erfahren, wie Sie Administrator für Ihre Schule werden? [Erfahren Sie alles darüber](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
).
  
## <a name="can-i-pilot-office-365-with-just-a-few-email-addresses-from-my-custom-domain"></a>Kann ich Office 365 mit nur wenigen e-Mail-Adressen aus meiner benutzerdefinierten Domäne pilotieren?

Sie können, aber es gibt Einschränkungen:
  
- Ihr aktueller e-Mail-Anbieter muss eine e-Mail weiterleiten.
    
- Sie müssen Ihre Office 365 bezogenen DNS-Einträge bei Ihrem DNS-Hostinganbieter verwalten, anstatt diese Einträge Office 365 verwalten zu müssen. Weitere Informationen dazu finden Sie unter Hinzufügen Ihrer Domäne zu Office 365, wenn Sie Ihre eigenen DNS-Einträge verwalten möchten.
    
- Einige Office 365 Funktionen stehen nicht zur Verfügung:
- Benutzer können keine Frei/Gebucht-Informationen für die Benutzer anzeigen, die sich auf dem anderen e-Mail-Anbieter befinden.
- Administratoren können nicht alle Konten von einem Ort aus verwalten.
- Benutzer können Office 365 Spamfilterung möglicherweise nicht verwenden

### <a name="how-to-set-up-an-office-365-pilot"></a>Einrichten eines Office 365 Pilotprojekts
    
1. Melden Sie sich beim Microsoft 365 Admin Center an.
    
    1. Melden Sie sich mit Ihrem Geschäfts- oder Schulkonto bei Office 365 an.
        
    2. Wechseln Sie zu **Einstellungen** \> **Domänen**. 
    
2. Stellen Sie sicher, dass Sie die Domäne besitzen, die Sie verwenden möchten.
    
    1. Wählen Sie auf der Seite **Domänen** die Option **Domäne hinzufügen**aus. 
        
    2. Geben Sie im Bereich die Domäne in diesem Beispiel cohowinery.com ein, und wählen Sie dann **weiter**aus. 
        
    3. Führen Sie auf der Seite Domäne **überprüfen** die schrittweisen Anleitungen aus. 
        
    4. Wählen Sie in der Dropdownliste Ihren DNS-Hostinganbieter aus, und befolgen Sie die Anweisungen, um anzuzeigen, dass Sie der Besitzer der Domäne sind.
        
    5. Wählen Sie **überprüfen**aus. Es dauert zwischen ein paar Minuten und 72 Stunden, bis DNS-Änderungen wirksam werden. 
        
    6. Wenn die Überprüfung erfolgreich verläuft, werden Sie aufgefordert, Ihre DNS-Einträge zu ändern.
    
3. Markieren der Domäne als freigegeben in Exchange Online
    
    1. Wechseln Sie zum **Exchange Admin Center** (EAC). 
        
    2. Wählen Sie im Abschnitt **Nachrichtenfluss** die Option **akzeptierte Domänen**aus. 
        
    3. Doppelklicken Sie auf die Domäne, die Sie ändern möchten.
        
    4. Wählen Sie im daraufhin geöffneten Fenster **Internes Relay**aus. 
        
    5. Wählen Sie **Speichern**. Diese Einstellung erfordert möglicherweise einige Minuten, um wirksam zu werden. 
    
4. Optional: Aufheben der Blockierung des vorhandenen e-Mail-Servers
    
    1. Office 365 verwendet Exchange Online Protection (EoP) zum Schutz vor Spam. Wenn EoP eine große Menge an Spam erkennt, die von Ihrem aktuellen e-Mail-Server weitergeleitet wird, kann dies dazu führen, dass die Weiterleitung möglicherweise nicht mehr funktioniert. Wenn Sie mit dem Spam Schutz vertraut sind, den Ihr anderer e-Mail-Anbieter verwendet, können Sie den Server in Office 365 Whitelisten. Auf diese Weise können jedoch auch alle Spam-Mails, die über den ursprünglichen Server eingehen, in die Office 365 Postfächer gelangen, und Sie können nicht auswerten, wie gut Office 365 Spam verhindert.
    
    2. Wechseln Sie zu Exchange Admin Center (EAC).
        
    3. Wählen Sie in der Exchange-Verwaltungskonsole **Schutz**aus, und wählen Sie **Verbindungsfilter**aus. 
        
    4. Wählen Sie in der **Liste der zugelassenen IP**- **+** Adressen die IP-Adresse des e-Mail-Servers aus, die Sie von Ihrem aktuellen e-Mail-Anbieter erhalten können. 
    
5. Erstellen von Benutzerkonten und Festlegen der primären Adresse (Reply-to)
    
    1. Gehen Sie zum Microsoft 365 Admin Center.
        
    2. Wählen Sie in der linken Navigationsleiste **Benutzer** \> **aktive Benutzer**aus. 
        
    3. Erstellen Sie die Benutzerkonten.
        
    4. Wählen Sie für jedes Konto Select **+ (New)** aus, und füllen Sie die erforderlichen Informationen aus. 
        
    5. Damit die e-Mail-Adresse des Benutzers unverändert bleibt, sollte das Feld **Benutzername** exakt mit der vorhandenen e-Mail-Adresse des Benutzers identisch sein. 
        
    6. Wählen Sie neben Benutzername Ihren benutzerdefinierten Domänennamen aus der Dropdownliste aus.
        
    7. Wählen **Create** Sie \> **Close**erstellen aus. 
        
6. Aktualisieren von DNS-Einträgen bei Ihrem DNS-Hostanbieter
    
    1. Melden Sie sich bei der Website Ihres DNS-Host Anbieters an, und folgen Sie den DNS- [Einträgen bei einem beliebigen DNS-Hostinganbieter für Office 365 Schritte](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md). **Nehmen Sie die folgenden Ausnahmen vor:**
    
        1. Erstellen Sie keinen neuen MX-Eintrag, oder ändern Sie den vorhandenen MX-Eintrag nicht.
            
        2. Wenn Sie bereits einen SPF-Eintrag (Sender Policy Framework) für Ihren vorherigen e-Mail-Anbieter haben, fügen Sie dem aktuellen TXT-Eintrag einfach "include:SPF. Protection. Outlook. com" hinzu, anstatt einen neuen SPF (txt)-Eintrag für Exchange Online zu erstellen. Beispiel: "v = spf1 MX include:adatum. com include:SPF. Protection. Outlook. com ~ all".
            
        3. Wenn Sie noch keinen SPF-Eintrag haben, ändern Sie den von Office 365 empfohlenen, um die Domäne für Ihren aktuellen e-Mail-Anbieter sowie SPF.Protection.Outlook.com hinzuzufügen. Dadurch werden ausgehende Nachrichten von beiden e-Mail-Systemen autorisiert.
            
7. Einrichten der e-Mail-Weiterleitung bei Ihrem aktuellen Anbieter
    
    1. Richten Sie bei Ihrem aktuellen e-Mail-Anbieter die Weiterleitung für Ihre Benutzer-e-Mail-Konten auf Ihre onmicrosoft.com-Domäne ein:
        
    2. Das Postfach von Benutzer A sollte an UserA@yourcompany.onmicrosoft.com weitergeleitet werden
        
    3. Postfach des Benutzers B sollte an UserB@yourcompany.onmicrosoft.com weitergeleitet werden
        
    4. Wenn Sie diesen Schritt ausführen:
        
    5. Alle e-Mails, die an UserA@yourcompany.com und UserB@yourcompany.com gesendet werden, stehen in Office 365 zur Verfügung.
    
    6. Hinweise:
        
        - Wenden Sie sich an Ihren aktuellen e-Mail-Anbieter, um die genauen Schritte zum Einrichten der Weiterleitung zu erhalten.
            
        - Sie müssen keine Kopie der Nachrichten beim aktuellen e-Mail-Anbieter aufbewahren.
            
        - Die meisten Anbieter senden e-Mails, die die Antwort-an-Adresse des Absenders hinterlassen, intakt, sodass Antworten an den ursprünglichen Absender gesendet werden.
    
8. Testen der Nachrichtenübermittlung
    
    1. Melden Sie sich bei Outlook Web App mit den Anmeldeinformationen von Benutzer A an.
        
    2. Führen Sie die folgenden Tests aus:
        
    3. Testen Sie lokale Microsoft-e-Mails. Senden Sie beispielsweise eine e-Mail an Benutzer B. Diese e-Mail sollte sofort zugestellt werden. In diesem Szenario wird die Nachricht nicht an das Postfach des Benutzers B auf dem ursprünglichen Server weitergeleitet, da Office 365 das Postfach als lokal betrachtet.
        
    4. Testen Sie e-Mails an Personen, die sich im anderen e-Mail-System befinden. Senden Sie beispielsweise eine e-Mail an den Benutzer C. Diese e-Mail sollte an das Postfach des Benutzers C auf dem ursprünglichen e-Mail-Server übermittelt werden.
        
    5. Überprüfen Sie von einem externen Konto oder aus dem e-Mail-Konto eines Mitarbeiters im anderen e-Mail-System, dass die Weiterleitung ordnungsgemäß auf dem anderen e-Mail-System eingerichtet ist. Senden Sie beispielsweise aus dem ursprünglichen Server Konto von Benutzer C oder einem Hotmail-Konto Benutzer eine e-Mail, und stellen Sie sicher, dass Sie im Office 365 Postfach von Benutzer a eintrifft.
        
9. Postfachinhalt migrieren
    
    1. Da sich nur zwei Benutzer bewegen müssen und Benutzer a und Benutzer B beide Outlook bereits verwenden, kann die e-Mail-Nachricht durch Öffnen der alten verschoben werden. PST-Datei im neuen Outlook-Profil und Kopieren der Nachrichten, Kalenderelemente, Kontakte usw. wie unter Importieren von Outlook-Elementen aus einer Outlook-Datendatei (PST) dargestellt. Nachdem die Elemente in den richtigen Speicherorten im Office 365 Postfach organisiert wurden, können alle auf alle Geräte zugegriffen werden, und zwar überall.
        
    2. Wenn mehr Postfächer beteiligt sind oder wenn die Mitarbeiter nicht bereits Outlook verwenden, können Sie die im Exchange Admin Center verfügbaren Migrationstools verwenden. Wechseln Sie zunächst zu Exchange Admin Center, und befolgen Sie die Anweisungen unter Migrieren von e-Mails von einem IMAP-Server zu Exchange Online Postfächern.
    
