---
title: Grundlagen von DNS
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
- GEA150
- BSA160
ms.assetid: 854b6b2b-0255-4089-8019-b765cff70377
ROBOTS: NOINDEX
description: Erfahren Sie mehr über Domänen und die zugehörigen DNS-Einträge, um Domänen verwalten zu können.
ms.openlocfilehash: 3a3a03c408d480b5d4678fde25c8830e063b1310
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780181"
---
# <a name="dns-basics"></a>Grundlagen von DNS

 **[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen. 
  
::: moniker range="o365-worldwide"

Domain names, like contoso.com, are managed by using a worldwide system of domain registrars and databases. The Domain Name System (DNS) provides a mapping between human-readable computer hostnames and the IP addresses used by networking equipment. An understanding of DNS and domain registrar basics can help you manage domains.
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/c005f2a4-90ad-46fe-b1ab-90f41f2a9d53?autoplay=false]
  
::: moniker-end

::: moniker range="o365-germany"

Domain names, like contoso.com, are managed by using a worldwide system of domain registrars and databases. The Domain Name System (DNS) provides a mapping between human-readable computer hostnames and the IP addresses used by networking equipment. An understanding of DNS and domain registrar basics can help you manage domains in Office 365.
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/c005f2a4-90ad-46fe-b1ab-90f41f2a9d53?autoplay=false]
  
::: moniker-end

::: moniker range="o365-21vianet"

Domänennamen wie "contoso.com" werden über ein weltweites System aus Domänenregistrierungsstellen und Datenbanken verwaltet. Hierbei sorgt das Domain Name System (Domänennamensystem, DNS) für die Zuordnung von lesbaren Computerhostnamen zu den IP-Adressen, die von Netzwerkgeräten verwendet werden. Ein grundlegendes Verständnis von DNS und Domänenregistrierungsstellen kann Administratoren helfen, Domänen in Office 365, betrieben von 21Vianet, zu verwalten.
  
::: moniker-end

## <a name="what-are-domain-names"></a>Was sind Domänennamen?

Domain names are used in URLs and email addresses, and they have different levels. For example, mail.contoso.com is a domain name with the following three levels:
  
- **.com** ist die Domäne auf oberster Ebene 
    
- **contoso** ist die Domäne auf zweiter Ebene 
    
- **mail** ist die Domäne auf dritter Ebene 
    
Why use a third-level domain? You might want to have different domain names for marketing or a blog. For example, blog.contoso.com. You typically add a second-level domain, like contoso.com, to use with Office 365 but you can also use third-level domains if you like.
  
Weitere Informationen zu den von Domänen gebotenen Möglichkeiten beim jeweiligen Angebotstyp finden Sie unter [Office 365-Dienstbeschreibung für Domänen](https://go.microsoft.com/fwlink/?LinkId=402693).
  
## <a name="understand-dns-record-types"></a>Grundlegendes zu DNS-Eintragstypen

DNS records stored at a DNS host for your domain are used to direct traffic for your domain. The following table describes frequently used DNS records and how they're used with Office 365.
  
|**NS-Eintrag (Namenservereintrag)**|**Gibt die Namenserver an, die als "autoritative Namenserver" für eine Domäne verwendet werden. Wenn Sie die Namenserver für Ihre Domäne ändern, ändern Sie, wo Ihre DNS-Einträge verwaltet werden und wo das DNS-System nach Informationen zu Mailservern usw. sucht. Office 365 verfügt über eigene Namenserver. Sie können aber auch weiterhin die Namenserver verwenden, die bereits für Ihre Domäne eingerichtet sind.**|
|:-----|:-----|
|A-Eintrag (Adresseintrag)  <br/> |Ordnet einem Domänennamen eine IP-Adresse zu.  <br/> |
|CNAME-Eintrag (Alias oder kanonischer Name)  <br/> |Redirects one domain to another in the DNS system. When a name server looks up a domain and finds that it has a CNAME record, the server replaces the first domain name with the CNAME, and then looks up the new name.  <br/> |
|MX-Eintrag (Mail-Exchanger)  <br/> |Points to where your email should be sent. It also has a priority field so that you can send mail to different servers in a priority order.  <br/> |
|SPF-Eintrag (Sender Policy Framework)  <br/> |Ein TXT-Eintrag hilft, E-Mail-Spoofing und -Phishing zu verhindern.  <br/> |
|SRV-Eintrag ("Service", Diensteintrag)  <br/> |Used by Skype for Business Online and Exchange Online to coordinate the flow of information between Office 365 services. For example, the SRV records are required to see presence in Outlook Web App, and to use Skype for Business Online, Skype, or other instant messaging tools with people in other companies.  <br/> |
|TTL ("Time-to-live", Gültigkeitsdauer)  <br/> |Die Zeitdauer, für die ein Namenserver einen DNS-Eintrag beibehält, bevor der Server nach einer aktualisierten Version sucht.  <br/> |
   
## <a name="how-does-dns-work"></a>Wie funktioniert das DNS?

Part of setting up your domain with a cloud service like Office 365 includes changing or adding [DNS records](dns-basics.md) for the domain. These changes are required because of how the Internet works with the DNS, Domain Name System, and domain names, to know where to send or find things, like email and websites. 
  
The Internet is set up to use DNS, or Domain Name System, which lets us use familiar names, like contoso.com, to locate specific Internet locations that are actually, under the covers, labeled with hard-to-remember numbers called IP (Internet Protocol) addresses. IP addresses look something like 70.42.241.42, so you can see it's much easier to use a domain name to identify locations like email hosts and websites.
  
So that's the short answer: DNS records tell the Internet where to send email (like joe@contoso.com) or find websites (like www.contoso.com) that use your domain name. When you put the right information into the right DNS records for your domain, the DNS system routes everything correctly so your email, for example, arrives in Office 365 instead of somewhere else.
  
A domain's DNS records can be helpful in other ways, too. For example, Exchange checks a DNS record that lets Outlook automatically set up a connection to the right Exchange server.
  
### <a name="dns-records-help-the-internet-send-email-to-the-right-place"></a>DNS-Einträge sorgen dafür, dass E-Mails über das Internet an den richtigen Ort gelangen

As you read above, DNS essentially directs traffic around the Internet, mapping friendly domain names to those hard-to-remember IP addresses. One DNS record, called the MX record, is specifically for sending email to the right host.
  
DNS records are like a database of information about your domain. The records and their values are kept in something called a zone file, which includes a list of each record for your domain and what its value is. Domain registrars and other DNS hosting companies provide a UI on their websites so you can edit the records in your domain's zone file. And that's where you update the MX record for your domain, to send email messages to Office 365.
  
 *When you change your email to Office 365, by updating your domain's MX record in the next step, ALL email sent to that domain will start coming to Office 365.*  If other people use your domain for email, you must set up Office 365 mailboxes for each of those people. 
  
Sound complicated? Well, it can be, but we walk you through each step in the Office 365 domain setup.
  
### <a name="dns-tells-the-internet-where-to-look-for-websites-too"></a>Über das DNS erfährt das Internet auch, wo nach Websites gesucht werden soll

When you type in a website address, for example, www.contoso.com, the Internet first checks with one of the DNS servers for something called a name server (NS) record for (in this case) contoso.com. The NS record tells the Internet where it should look for the zone file that has all the other DNS record values for that domain. There are lots of DNS servers, all connected to each other. The servers work together to keep track of all registered domain names, which have to be unique, and where the domain's zone files are.
  
::: moniker range="o365-worldwide"

Let's say that the NS record for contoso.com says "godaddy.com." Now the Internet knows that GoDaddy.com is where to look for the zone file listing all the other DNS records for contoso.com. Those DNS records include the MX record that says where to send emails for contoso.com and other records. If the MX record has a value that says (but in technical terms) "send email to Office 365," that's where all the email messages sent to a contoso.com email address (like joe@contoso.com) will be sent. Then, as long as there's a mailbox called "joe" at that location, the email will be delivered.

::: moniker-end

::: moniker range="o365-germany"

Let's say that the NS record for contoso.com says "godaddy.com." Now the Internet knows that GoDaddy.com is where to look for the zone file listing all the other DNS records for contoso.com. Those DNS records include the MX record that says where to send emails for contoso.com and other records. If the MX record has a value that says (but in technical terms) "send email to Office 365," that's where all the email messages sent to a contoso.com email address (like joe@contoso.com) will be sent. Then, as long as there's a mailbox called "joe" at that location, the email will be delivered.

::: moniker-end

::: moniker range="o365-21vianet"

Einmal angenommen, der Wert des NS-Eintrags für "contoso.com" würde "hichina.com" lauten. Damit weiß das Internet, dass es bei "hichina.com" nach der Zonendatei suchen muss, in der sich alle anderen DNS-Einträge für "contoso.com" befinden. Zu diesen DNS-Einträgen gehören auch der MX-Eintrag, der angibt, wohin E-Mails für "contoso.com" gesendet werden sollen, sowie weitere Einträge. Wenn der MX-Eintrag einen Wert aufweist, der (allerdings in technischen Begriffen) besagt: "E-Mails an Office 365 senden", dann werden alle E-Mail-Nachrichten, die an E-Mail-Adressen bei "contoso.com" gerichtet sind (wie "joe@contoso.com") dorthin gesendet. Anschließend wird die E-Mail an diesen Speicherort übermittelt, sofern es dort ein Postfach mit dem Namen "joe" gibt.

::: moniker-end

The actual values that you must enter for all of this to work with Office 365 are listed for you when you're setting up your domain, in the domain setup steps. If you're doing the set up manually, you copy and paste the values into the correct DNS records (MX record, CNAME records, and so on) at your DNS host, which might be your domain registrar but doesn't have to be.
  
::: moniker range="o365-worldwide"

Why might your domain's zone file be somewhere besides at your domain registrar? Well, you might register your domain name at a domain registrar like GoDaddy, but your DNS records might be managed somewhere else, at a separate DNS hosting company or a web hosting company. The NS records for your domain store that information so all the DNS servers know where to look.

::: moniker-end

::: moniker range="o365-germany"

Why might your domain's zone file be somewhere besides at your domain registrar? Well, you might register your domain name at a domain registrar like GoDaddy, but your DNS records might be managed somewhere else, at a separate DNS hosting company or a web hosting company. The NS records for your domain store that information so all the DNS servers know where to look.

::: moniker-end

::: moniker range="o365-21vianet"

Warum befindet sich die Zonendatei Ihrer Domäne möglicherweise an einer anderen Stelle und nicht bei Ihrer Domänenregistrierungsstelle? Nun, Sie können Ihre Domäne bei einer Domänenregistrierungsstelle wie HiChina registrieren, die DNS-Einträge werden aber möglicherweise von einer anderen Stelle verwaltet, wie einem anderen DNS-Hostinganbieter oder einem Webhostingunternehmen. In den NS-Einträgen für Ihre Domäne werden diese Informationen abgelegt, damit alle DNS-Server wissen, wo sie suchen müssen.

::: moniker-end

> [!NOTE]
> Wenn Sie Ihre Domäne in Office 365 so einrichten, dass [Microsoft Ihre DNS-Einträge einrichtet und verwaltet](../setup/domains-faq.md#how-does-office-365-manage-my-dns-records), dann ändern Sie (als Teil des Setups) die [DNS-Verwaltung in Office 365](../setup/domains-faq.md#change-dns-management-to-office-365). 
 

::: moniker range="o365-worldwide"
## <a name="why-add-a-domain-in-office-365"></a>Warum muss ich in Office 365 eine Domäne hinzufügen?


Adding a custom domain, like fourthcoffee.com, to Office 365 lets you use a shorter, more familiar email address and userID with the service. You're [given a domain to use](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) when you sign up for a Office 365 account, but it includes "onmicrosoft.com." Many people prefer to add their organization or business domain if they plan to use Office 365 for email. 
  
> [!NOTE]
> Wenn Sie nur Microsoft-Apps wie Outlook oder Word herunterladen und verwenden möchten, müssen Sie keine Domäne hinzufügen: [Installieren von Office auf Ihrem PC oder Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658). 
  
Sie können Ihren Domänennamen in Office 365 mit Ihrer E-Mail-, öffentlichen Website- und Sofortnachrichtenadresse verwenden.
  
- **Email:** Your domain name lets you customize your email, so you can use a shorter, easier-to-remember address than [the initial onmicrosoft.com email address](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) that comes with your account. So instead of joe@contoso.onmicrosoft.com, the email address (which is also the work account that you use to sign in to Office 365) could be joe@contoso.com. 
    
- **Website:** Wenn Sie über ein Microsoft 365-Abonnement verfügen, das eine öffentliche SharePoint Online-Website umfasst (nicht mehr erhältlich), weist Ihre öffentliche Website eine ursprüngliche Adresse wie „contoso-public.sharepoint.com“ auf. Wenn Sie Ihre Website für Ihr Unternehmen einrichten, können Sie einen benutzerdefinierten Domänennamen verwenden, um die Websiteadresse umzubenennen, etwa in "www.contoso.com". 
    
- **Chatnachrichten:** Ihre Skype for Business Online-Adresse kann ebenfalls so angepasst werden, dass sie Ihren Domänennamen verwendet, sodass Personen in Ihrer Organisation Verbindungen untereinander in Skype for Business Online mithilfe einer kürzeren, leichter zu merkenden Adresse (wie "joe@contoso.com") herstellen können. 
    
::: moniker-end

::: moniker range="o365-germany"
## <a name="why-add-a-domain-in-office-365"></a>Warum muss ich in Office 365 eine Domäne hinzufügen?


Adding a custom domain, like fourthcoffee.com, to Office 365 lets you use a shorter, more familiar email address and userID with the service. You're [given a domain to use](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) when you sign up for a Office 365 account, but it includes "onmicrosoft.com." Many people prefer to add their organization or business domain if they plan to use Office 365 for email. 
  
> [!NOTE]
> Wenn Sie nur Office 365-Apps wie Outlook oder Word herunterladen und verwenden möchten, müssen Sie keine Domäne hinzufügen: [Installieren von Office auf Ihrem PC oder Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658). 
  
Sie können Ihren Domänennamen in Office 365 mit Ihrer E-Mail-, öffentlichen Website- und Sofortnachrichtenadresse verwenden.
  
- **Email:** Your domain name lets you customize your email, so you can use a shorter, easier-to-remember address than [the initial onmicrosoft.com email address](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) that comes with your account. So instead of joe@contoso.onmicrosoft.com, the email address (which is also the work account that you use to sign in to Office 365) could be joe@contoso.com. 
    
- **Website:** Wenn Sie über ein Abonnement verfügen, das eine öffentliche SharePoint Online-Website umfasst (nicht mehr erhältlich), weist Ihre öffentliche Website eine ursprüngliche Adresse wie „contoso-public.sharepoint.com“ auf. Wenn Sie Ihre Website für Ihr Unternehmen einrichten, können Sie einen benutzerdefinierten Domänennamen verwenden, um die Websiteadresse umzubenennen, etwa in "www.contoso.com". 
    
- **Chatnachrichten:** Ihre Skype for Business Online-Adresse kann ebenfalls so angepasst werden, dass sie Ihren Domänennamen verwendet, sodass Personen in Ihrer Organisation Verbindungen untereinander in Skype for Business Online mithilfe einer kürzeren, leichter zu merkenden Adresse (wie "joe@contoso.com") herstellen können. 
    
::: moniker-end

## <a name="the-dns-records-required-for-office-365"></a>Die für Office 365 erforderlichen DNS-Einträge

There are a number of DNS records required for Office 365 to work with your domain. In addition to setting up your domain's MX record so email will be sent to Office 365, there are records to help with tasks like making sure Outlook can automatically connect to the right Exchange server, setting up instant messaging, and helping to prevent spam email.
  
You can [find a list of values](information-for-dns-records.md) to set up your domain. They're included right in the Microsoft 365 admin center. 
  
Oder, wenn Sie eine Bereitstellung planen, möchten Sie sich vielleicht eine Liste aller für Office 365 erforderlichen DNS-Einträge mit Funktion und Beispielwerten anschauen. Lesen Sie die Informationen unter [Externe DNS-Einträge für Office 365](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records).
  
## <a name="how-can-i-learn-more"></a>Wie kann ich mehr erfahren?

Sehen Sie sich die folgenden Informationen an: 
  
- Sie wissen nicht sicher, wo Ihre Domäne registriert ist? [Hilfe zum Ermitteln Ihrer Domänenregistrierungsstelle anfordern.](find-your-domain-registrar.md)
    
- Erfahren Sie, [warum Sie die Schritte des Assistenten ausführen müssen](../setup/add-domain.md), bevor Sie Ihre Domäne mit Office 365 verwenden können. 
    

