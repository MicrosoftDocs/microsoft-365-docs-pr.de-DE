---
title: Grundlagen von DNS
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
search.appverid:
- MET150
- MOE150
- GEA150
- BSA160
ms.assetid: 854b6b2b-0255-4089-8019-b765cff70377
ROBOTS: NOINDEX
description: Das Domain Name System (DNS) ordnet Computerhostnamen IP-Adressen zu. Ein grundlegendes Verständnis von DNS und Domänenregistrierungsstellen hilft Ihnen dabei, Domänen zu verwalten.
ms.openlocfilehash: 68b9b82d52e9bb2c4105237f0a29e8137623138e
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393907"
---
# <a name="dns-basics"></a>Grundlagen von DNS

 **[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.yml)**, wenn Sie nicht finden, wonach Sie suchen. 
  
::: moniker range="o365-worldwide"

Domänennamen wie „contoso.com“ werden über ein weltweites System aus Domänenregistrierungsstellen und Datenbanken verwaltet. Hierbei sorgt das Domain Name System (Domänennamensystem, DNS) für die Zuordnung von lesbaren Computerhostnamen zu den IP-Adressen, die von Netzwerkgeräten verwendet werden. Ein grundlegendes Verständnis von DNS und Domänenregistrierungsstellen kann Ihnen helfen, Domänen zu verwalten.

## <a name="watch-domains--dns-an-overview"></a>Ansehen: Domänen und DNS: Ein Überblick
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/c005f2a4-90ad-46fe-b1ab-90f41f2a9d53?autoplay=false]
  
::: moniker-end

::: moniker range="o365-germany"

Domänennamen wie „contoso.com“ werden über ein weltweites System aus Domänenregistrierungsstellen und Datenbanken verwaltet. Hierbei sorgt das Domain Name System (Domänennamensystem, DNS) für die Zuordnung von lesbaren Computerhostnamen zu den IP-Adressen, die von Netzwerkgeräten verwendet werden. Ein grundlegendes Verständnis von DNS und Domänenregistrierungsstellen kann Ihnen helfen, Domänen zu verwalten.

## <a name="watch-domains--dns-an-overview"></a>Ansehen: Domänen und DNS: Ein Überblick
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/c005f2a4-90ad-46fe-b1ab-90f41f2a9d53?autoplay=false]
  
::: moniker-end

::: moniker range="o365-21vianet"

Domänennamen wie „contoso.com“ werden über ein weltweites System aus Domänenregistrierungsstellen und Datenbanken verwaltet. Hierbei sorgt das Domain Name System (Domänennamensystem, DNS) für die Zuordnung von lesbaren Computerhostnamen zu den IP-Adressen, die von Netzwerkgeräten verwendet werden. Ein grundlegendes Verständnis von DNS und Domänenregistrierungsstellen hilft Administratoren dabei, Domänen zu verwalten.
  
::: moniker-end

## <a name="what-are-domain-names"></a>Was sind Domänennamen?

Domänennamen werden in URLs und E-Mail-Adressen verwendet und weisen unterschiedliche Ebenen auf. So ist mail.contoso.com beispielsweise ein Domänenname mit den folgenden drei Ebenen:
  
- **.com** ist die Domäne auf oberster Ebene 
    
- **contoso** ist die Domäne auf zweiter Ebene 
    
- **mail** ist die Domäne auf dritter Ebene 
    
Warum wird eine Domäne auf dritter Ebene verwendet? Möglicherweise möchten Sie für die Marketingabteilung oder einen Blog unterschiedliche Domänennamen verwenden, z. B. blog.contoso.com. Normalerweise fügen Sie eine Domäne auf zweiter Ebene, beispielsweise "contoso.com", für die Verwendung mit Microsoft hinzu, Sie können auf Wunsch aber auch Domänen auf dritter Ebene verwenden.
  
Weitere Informationen zu den von Domänen gebotenen Möglichkeiten beim jeweiligen Angebotstyp finden Sie unter [Beschreibung der Microsoft 365- und Office 365-Plattformdienste](/office365/servicedescriptions/office-365-platform-service-description/domains).
  
## <a name="understand-dns-record-types"></a>Grundlegendes zu DNS-Eintragstypen

DNS-Einträge, die auf einem DNS-Host für Ihre Domäne gespeichert sind, werden zum Lenken des Datenverkehrs für Ihre Domäne verwendet. In der folgenden Tabelle sind häufig verwendete DNS-Einträge und deren Verwendung beschrieben.
  
|**NS-Eintrag (Namenservereintrag)**|**Gibt die Namenserver an, die als "autoritative Namenserver" für eine Domäne verwendet werden. Wenn Sie die Namenserver für Ihre Domäne ändern, ändern Sie, wo Ihre DNS-Einträge verwaltet werden und wo das DNS-System nach Informationen zu Mailservern usw. sucht. Microsoft verfügt über eigene Namenserver. Sie können aber auch weiterhin die Namenserver verwenden, die bereits für Ihre Domäne eingerichtet sind.**|
|:-----|:-----|
|A-Eintrag (Adresseintrag)  <br/> |Ordnet einem Domänennamen eine IP-Adresse zu.  <br/> |
|CNAME-Eintrag (Alias oder kanonischer Name)  <br/> |Leitet im DNS-System eine Domäne auf eine um. Wenn ein Namenserver nach einer Domäne sucht und einen CNAME-Eintrag findet, ersetzt er den ersten Domänennamen durch den CNAME und sucht dann nach einem neuen Namen.  <br/> |
|MX-Eintrag (Mail-Exchanger)  <br/> |Verweist auf den Server, an den E-Mails geleitet werden sollen. Der Eintrag enthält auch ein Prioritätsfeld, sodass E-Mail-Nachrichten in der Reihenfolge der Priorität an unterschiedliche Server geleitet werden können.  <br/> |
|SPF-Eintrag (Sender Policy Framework)  <br/> |Ein TXT-Eintrag hilft, E-Mail-Spoofing und -Phishing zu verhindern.  <br/> |
|SRV-Eintrag ("Service", Diensteintrag)  <br/> |Wird von Skype for Business Online und Exchange Online zum Koordinieren des Informationsflusses zwischen Microsoft-Diensten verwendet So sind die SRV-Einträge beispielsweise erforderlich, um den Anwesenheitsstatus in Outlook Web App anzuzeigen und um mit Skype for Business Online, Skype oder anderen Chatnachrichtensystemen Nachrichten mit Personen in anderen Unternehmen auszutauschen.  <br/> |
|TTL ("Time-to-live", Gültigkeitsdauer)  <br/> |Die Zeitdauer, für die ein Namenserver einen DNS-Eintrag beibehält, bevor der Server nach einer aktualisierten Version sucht.  <br/> |
   
## <a name="how-does-dns-work"></a>Wie funktioniert das DNS?

Zur Einrichtung Ihrer Domäne bei einem Clouddienst wie Microsoft 365 gehört das Ändern oder Hinzufügen von [DNS-Einträgen](dns-basics.md) für Ihre Domäne. Diese Änderungen sind aufgrund der Art und Weise erforderlich, wie das Internet das DNS, das Domain Name System, und Domänennamen verwendet, um festzustellen, wohin Elemente wie E-Mails gesendet werden sollen oder wo Elemente wie Websites gefunden werden können. 
  
Das Internet ist für die Verwendung des DNS eingerichtet, was dafür sorgt, dass wir vertraute Namen wie "contoso.com" verwenden können, um bestimmte Internetspeicherorte zu finden, die hinter den Kulissen eigentlich mit schwer zu merkenden Zahlen, den so genannten IP-Adressen (Internet Protocol) bezeichnet werden. IP-Adressen sehen ähnlich wie 70.42.241.42 aus, und wie Sie sehen, ist es wesentlich einfacher, einen Domänennamen für die Identifikation von Speicherorten wie E-Mail-Hosts und Websites zu verwenden.
  
Kurz gesagt: Das DNS teilt dem Internet mit, wohin eine E-Mail (wie "jonas@contoso.com") gesendet werden soll oder wo sich eine Website (wie "www.contoso.com") befindet, die Ihren Domänennamen verwendet. Wenn Sie die korrekten Informationen in die korrekten DNS-Einträge für Ihre Domäne eingeben, leitet das DNS alles ordnungsgemäß weiter, d. h. Ihre E-Mails kommen in Microsoft 365 und nicht irgendwo anders an.
  
Die DNS-Einträge einer Domäne können aber auch in anderer Weise hilfreich sein. So prüft Exchange beispielsweise einen DNS-Eintrag, der dafür sorgt, dass Outlook automatisch eine Verbindung zum richtigen Exchange-Server herstellt.
  
### <a name="dns-records-help-the-internet-send-email-to-the-right-place"></a>DNS-Einträge sorgen dafür, dass E-Mails über das Internet an den richtigen Ort gelangen

Wie vorstehend bereits erwähnt, leitet das DNS den Datenverkehr durch das Internet, indem aussagekräftige Domänennamen den schwer zu merkenden IP-Adressen zugeordnet werden. Ein DNS-Eintrag, der so genannte MX-Eintrag, dient speziell zum Senden von E-Mails an den richtigen Host. 
  
DNS-Einträge sind wie eine Datenbank mit Informationen über Ihre Domäne. Die Einträge und deren Werte werden in einer sogenannten Zonendatei gespeichert, die eine Liste mit allen Einträgen für Ihre Domäne und deren Werte enthält. Domänenregistrierungsstellen und andere DNS-Hostinganbieter stellen auf ihren Websites eine Benutzeroberfläche bereit, auf der Sie die Einträge in der Zonendatei Ihrer Domäne bearbeiten können. Dies ist auch die Datei, in der Sie den MX-Eintrag für Ihre Domäne aktualisieren, damit E-Mail-Nachrichten an Microsoft 365 gesendet werden.
  
 *Wenn Sie Ihr E-Mail-System auf Microsoft 365 ändern, indem Sie im nächsten Schritt den MX-Eintrag der Domäne ändern, werden von nun an alle an diese Domäne gesendeten E-Mails an Microsoft 365 gesendet.*  Wenn andere Personen Ihre Domäne für E-Mails verwenden, müssen Sie Microsoft 365-Postfächer für jede dieser Person einrichten. 
  
Klingt kompliziert? Nun ja, möglicherweise, aber keine Sorge, wir führen Sie durch jeden Schritt zur Einrichtung Ihrer Domäne in Microsoft.
  
### <a name="dns-tells-the-internet-where-to-look-for-websites-too"></a>Über das DNS erfährt das Internet auch, wo nach Websites gesucht werden soll

Wenn Sie eine Websiteadresse wie "www.contoso.com" eingeben, prüft das Internet zuerst auf einem der DNS-Server, ob es einen NS-Eintrag (Namenserver) für (in diesem Fall) "contoso.com" gibt. Der NS-Eintrag teilt dem Internet mit, wo nach der Zonendatei gesucht werden soll, in der sich alle anderen Werte für die DNS-Einträge dieser Domäne befinden. Es gibt eine Menge DNS-Server, die alle miteinander verbunden sind. Die Server arbeiten zusammen, um alle registrierten Domänennamen (die eindeutig sein müssen) und die Position der Zonendateien der Domänen nachzuverfolgen.
  
::: moniker range="o365-worldwide"

Einmal angenommen, der Wert des NS-Eintrags für "contoso.com" würde "godaddy.com" lauten. Damit weiß das Internet, dass es bei "GoDaddy.com" nach der Zonendatei suchen muss, in der sich alle anderen DNS-Einträge für "contoso.com" befinden. Zu diesen DNS-Einträgen gehören auch der MX-Eintrag, der angibt, wohin E-Mails für "contoso.com" gesendet werden sollen, sowie weitere Einträge. Wenn der MX-Eintrag einen Wert aufweist, der (allerdings in technischen Begriffen) besagt: "E-Mails an Microsoft 365 senden", dann werden alle E-Mail-Nachrichten, die an E-Mail-Adressen bei "contoso.com" gerichtet sind (wie "joe@contoso.com") dorthin gesendet. Anschließend wird die E-Mail an diesen Speicherort übermittelt, sofern es dort ein Postfach mit dem Namen "joe" gibt.

::: moniker-end

::: moniker range="o365-germany"

Einmal angenommen, der Wert des NS-Eintrags für "contoso.com" würde "godaddy.com" lauten. Damit weiß das Internet, dass es bei "GoDaddy.com" nach der Zonendatei suchen muss, in der sich alle anderen DNS-Einträge für "contoso.com" befinden. Zu diesen DNS-Einträgen gehören auch der MX-Eintrag, der angibt, wohin E-Mails für "contoso.com" gesendet werden sollen, sowie weitere Einträge. Wenn der MX-Eintrag einen Wert aufweist, der (allerdings in technischen Begriffen) besagt: "E-Mails an Microsoft 365 senden", dann werden alle E-Mail-Nachrichten, die an E-Mail-Adressen bei "contoso.com" gerichtet sind (wie "joe@contoso.com") dorthin gesendet. Anschließend wird die E-Mail an diesen Speicherort übermittelt, sofern es dort ein Postfach mit dem Namen "joe" gibt.

::: moniker-end

::: moniker range="o365-21vianet"

Einmal angenommen, der Wert des NS-Eintrags für „contoso.com“ würde „hichina.com“ lauten. Damit weiß das Internet, dass es bei „hichina.com“ nach der Zonendatei suchen muss, in der sich alle anderen DNS-Einträge für „contoso.com“ befinden. Zu diesen DNS-Einträgen gehören auch der MX-Eintrag, der angibt, wohin E-Mails für „contoso.com“ gesendet werden sollen, sowie weitere Einträge. Wenn der MX-Eintrag einen Wert aufweist, der (allerdings in technischen Begriffen) besagt: „E-Mails an Microsoft 365 senden“, dann werden alle E-Mail-Nachrichten, die an E-Mail-Adressen bei „contoso.com“ gerichtet sind (wie „joe@contoso.com“) dorthin gesendet. Anschließend wird die E-Mail an diesen Speicherort übermittelt, sofern es dort ein Postfach mit dem Namen „joe“ gibt.

::: moniker-end

Die eigentlichen Werte, die Sie eingeben müssen, damit all das mit Microsoft 365 funktioniert, werden in den Schritten zum Einrichten der Domäne aufgeführt, wenn Sie Ihre Domäne einrichten. Wenn Sie das Setup manuell vornehmen, kopieren Sie die Werte und fügen sie bei Ihrem DNS-Hostinganbieter in die zugehörigen DNS-Einträge (MX-Eintrag, CNAME-Einträge usw.) ein. Der DNS-Hostinganbieter kann, muss aber nicht zwangsläufig, Ihre Domänenregistrierungsstelle sein.
  
::: moniker range="o365-worldwide"

Warum befindet sich die Zonendatei Ihrer Domäne möglicherweise an einer anderen Stelle und nicht bei Ihrer Domänenregistrierungsstelle? Nun, Sie können Ihre Domäne bei einer Domänenregistrierungsstelle wie GoDaddy registrieren, die DNS-Einträge werden aber möglicherweise von einer anderen Stelle verwaltet, wie einem anderen DNS-Hostinganbieter oder einem Webhostingunternehmen. Diese Informationen sind in den NS-Einträgen für Ihre Domäne gespeichert, daher wissen alle DNS-Server, wo sie danach suchen müssen.

::: moniker-end

::: moniker range="o365-germany"

Warum befindet sich die Zonendatei Ihrer Domäne möglicherweise an einer anderen Stelle und nicht bei Ihrer Domänenregistrierungsstelle? Nun, Sie können Ihre Domäne bei einer Domänenregistrierungsstelle wie GoDaddy registrieren, die DNS-Einträge werden aber möglicherweise von einer anderen Stelle verwaltet, wie einem anderen DNS-Hostinganbieter oder einem Webhostingunternehmen. Diese Informationen sind in den NS-Einträgen für Ihre Domäne gespeichert, daher wissen alle DNS-Server, wo sie danach suchen müssen.

::: moniker-end

::: moniker range="o365-21vianet"

Warum befindet sich die Zonendatei Ihrer Domäne möglicherweise an einer anderen Stelle und nicht bei Ihrer Domänenregistrierungsstelle? Nun, Sie können Ihre Domäne bei einer Domänenregistrierungsstelle wie HiChina registrieren, die DNS-Einträge werden aber möglicherweise von einer anderen Stelle verwaltet, wie einem anderen DNS-Hostinganbieter oder einem Webhostingunternehmen. Diese Informationen sind in den NS-Einträgen für Ihre Domäne gespeichert, daher wissen alle DNS-Server, wo sie danach suchen müssen.

::: moniker-end

::: moniker range="o365-worldwide"
## <a name="why-add-a-domain-in-microsoft-365"></a>Warum muss ich in Microsoft 365 eine Domäne hinzufügen?


Indem Sie eine benutzerdefinierte Domäne, z. B. "fourthcoffee.com" zu Microsoft 365 hinzufügen, können Sie eine kürzere, vertrautere E-Mail-Adresse und Benutzer-ID mit dem Dienst verwenden. Wenn Sie sich für ein Microsoft 365-Konto registrieren, [erhalten Sie eine Domäne, die Sie verwenden können](../setup/domains-faq.yml). Diese enthält jedoch "onmicrosoft.com" im Namen. Viele Benutzer möchten lieber die Domäne ihrer Organisation oder ihres Unternehmens hinzufügen, wenn sie die Verwendung von Microsoft 365 für E-Mail planen. 
  
> [!NOTE]
> Wenn Sie nur Microsoft-Apps wie Outlook oder Word herunterladen und verwenden möchten, müssen Sie keine Domäne hinzufügen: [Installieren von Office auf Ihrem PC oder Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658). 
  
Sie können Ihren Domänennamen in Microsoft 365 mit Ihrer E-Mail-, öffentlichen Website- und Sofortnachrichtenadresse verwenden.
  
- **E-Mail:** Sie können Ihre E-Mail mithilfe Ihres Domänennamens anpassen, sodass Sie eine kürzere, leichter zu merkende Adresse als die [ursprüngliche "onmicrosoft.com"-E-Mail-Adresse](../setup/domains-faq.yml), die Ihrem Konto zugeordnet ist, verwenden können. Also könnte anstelle von "joe@contoso.onmicrosoft.com" die E-Mail-Adresse (die auch das Firmenkonto darstellt, das Sie für die Anmeldung bei Microsoft 365 verwenden) "joe@contoso.com" lauten. 
    
- **Website:** Wenn Sie über ein Microsoft 365-Abonnement verfügen, das eine öffentliche SharePoint Online-Website umfasst (nicht mehr zum Kauf erhältlich), weist Ihre öffentliche Website eine ursprüngliche Adresse wie "contoso-public.sharepoint.com" auf. Wenn Sie Ihre Website für Ihr Unternehmen einrichten, können Sie einen benutzerdefinierten Domänennamen verwenden, um die Websiteadresse umzubenennen, etwa in "www.contoso.com". 
    
- **Chatnachrichten:** Ihre Skype for Business Online-Adresse kann ebenfalls so angepasst werden, dass sie Ihren Domänennamen verwendet, sodass Personen in Ihrer Organisation Verbindungen untereinander in Skype for Business Online mithilfe einer kürzeren, leichter zu merkenden Adresse (wie "joe@contoso.com") herstellen können. 
    
::: moniker-end

::: moniker range="o365-germany"
## <a name="why-add-a-domain-in-microsoft-365"></a>Warum muss ich in Microsoft 365 eine Domäne hinzufügen?


Indem Sie eine benutzerdefinierte Domäne, z. B. "fourthcoffee.com" zu Microsoft 365 hinzufügen, können Sie eine kürzere, vertrautere E-Mail-Adresse und Benutzer-ID mit dem Dienst verwenden. Wenn Sie sich für ein Microsoft 365-Konto registrieren, [erhalten Sie eine Domäne, die Sie verwenden können](../setup/domains-faq.yml). Diese enthält jedoch "onmicrosoft.com" im Namen. Viele Benutzer möchten lieber die Domäne ihrer Organisation oder ihres Unternehmens hinzufügen, wenn sie die Verwendung von Microsoft 365 für E-Mail planen. 
  
> [!NOTE]
> Wenn Sie nur Microsoft 365-Apps wie Outlook oder Word herunterladen und verwenden möchten, müssen Sie keine Domäne hinzufügen: [Installieren von Office auf Ihrem PC oder Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658). 
  
Sie können Ihren Domänennamen in Microsoft 365 mit Ihrer E-Mail-, öffentlichen Website- und Sofortnachrichtenadresse verwenden.
  
- **E-Mail:** Sie können Ihre E-Mail mithilfe Ihres Domänennamens anpassen, sodass Sie eine kürzere, leichter zu merkende Adresse als die [ursprüngliche "onmicrosoft.com"-E-Mail-Adresse](../setup/domains-faq.yml), die Ihrem Konto zugeordnet ist, verwenden können. Also könnte anstelle von "joe@contoso.onmicrosoft.com" die E-Mail-Adresse (die auch das Firmenkonto darstellt, das Sie für die Anmeldung bei Microsoft 365 verwenden) "joe@contoso.com" lauten. 
    
- **Website:** Wenn Sie über ein Abonnement verfügen, das eine öffentliche SharePoint Online-Website umfasst (nicht mehr zum Kauf erhältlich), weist Ihre öffentliche Website eine ursprüngliche Adresse wie "contoso-public.sharepoint.com" auf. Wenn Sie Ihre Website für Ihr Unternehmen einrichten, können Sie einen benutzerdefinierten Domänennamen verwenden, um die Websiteadresse umzubenennen, etwa in "www.contoso.com". 
    
- **Chatnachrichten:** Ihre Skype for Business Online-Adresse kann ebenfalls so angepasst werden, dass sie Ihren Domänennamen verwendet, sodass Personen in Ihrer Organisation Verbindungen untereinander in Skype for Business Online mithilfe einer kürzeren, leichter zu merkenden Adresse (wie "joe@contoso.com") herstellen können. 
    
::: moniker-end

## <a name="the-dns-records-required-for-microsoft-365"></a>Die für Microsoft 365 erforderlichen DNS-Einträge

In Microsoft 365 werden mehrere DNS-Einträge benötigt, damit der Dienst mit Ihrer Domäne zusammenarbeitet. Neben dem MX-Eintrag für Ihre Domäne, der benötigt wird, damit E-Mail-Nachrichten an Microsoft 365 gesendet werden, gibt es weitere Einträge, die dafür sorgen, dass Outlook automatisch die Verbindung zu dem richtigen Exchange-Server aufnimmt, dass Sofortnachrichten ordnungsgemäß eingerichtet werden und dass Spam-E-Mails abgewehrt werden.
  
Hier [finden Sie eine Liste mit Werten](information-for-dns-records.md) zum Einrichten Ihrer Domäne. Sie sind direkt im Microsoft 365 Admin Center enthalten. 
  
Oder, wenn Sie eine Bereitstellung planen, möchten Sie sich vielleicht eine Liste aller für Microsoft 365 erforderlichen DNS-Einträge mit Funktion und Beispielwerten anschauen. Lesen Sie dazu die Informationen unter [Externe DNS-Einträge für Microsoft 365](../../enterprise/external-domain-name-system-records.md).
  
## <a name="next-steps"></a>Nächste Schritte

Sehen Sie sich die folgenden Informationen an: 
  
- Sie wissen nicht sicher, wo Ihre Domäne registriert ist? [Hilfe zum Ermitteln Ihrer Domänenregistrierungsstelle anfordern.](find-your-domain-registrar.md)
- Erfahren Sie, [warum Sie die Schritte des Assistenten ausführen müssen](../setup/add-domain.md), bevor Sie Ihre Domäne mit Microsoft 365 verwenden können.

## <a name="related-content"></a>Verwandte Inhalte

[Häufig gestellte Fragen zu Domänen](../setup/domains-faq.yml) (Artikel)\
[Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge hinzugefügt wurden](find-and-fix-issues.md) (Artikel)\
[Domänen verwalten](index.yml) (Linkseite)