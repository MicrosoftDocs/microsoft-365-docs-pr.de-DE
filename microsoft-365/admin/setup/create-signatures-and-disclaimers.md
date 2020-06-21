---
title: Erstellen von organisationsweiten Signaturen und Haftungsausschlüssen
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 2d75860f-c527-4352-a7f6-73eba54c0c72
description: Hier erfahren Sie, wie Sie e-Mail-Signaturen, rechtliche Hinweise oder Offenlegungserklärungen allen e-Mail-Nachrichten hinzufügen, die Ihre Organisation betreten oder verlassen.
ms.openlocfilehash: d7e19c6e3f425f95429aefd769d2b8992fde141e
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/17/2020
ms.locfileid: "44779881"
---
# <a name="create-organization-wide-signatures-and-disclaimers"></a>Erstellen von organisationsweiten Signaturen und Haftungsausschlüssen

 You can add an email signature, legal disclaimer, or disclosure statement to the email messages that enter or leave your organization. You can set it up to apply to all incoming and outgoing messages as shown below. Or you can apply it to certain messages like those containing specific words or text patterns.

 Sehen Sie sich ein kurzes Video über die Erstellung einer unternehmensweiten e-Mail-Signatur an. <br><br>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1IEWf] 

Wenn Sie dieses Video hilfreich fanden, sehen Sie sich bitte die [komplette Schulungsserie für kleine Unternehmen und jene, die neu bei Microsoft 365 sind](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816), an.

## <a name="create-a-signature-that-applies-to-all-messages"></a>Erstellen einer Signatur, die auf alle Nachrichten angewendet wird

> [!TIP]
> Organisationsweite Signaturen werden als "Haftungsausschlüsse" bezeichnet, unabhängig davon, was diese enthalten. Sie können beispielsweise lediglich eine Signatur sein oder auch Ihre Adresse, den rechtlichen Haftungsausschluss oder andere Informationen, die Sie verwenden möchten.
    
::: moniker range="o365-worldwide"

Wechseln Sie zum Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.

::: moniker-end

::: moniker range="o365-germany"

Wechseln Sie zum Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.

::: moniker-end

::: moniker range="o365-21vianet"

Wechseln Sie zum Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn/adminportal</a>.

::: moniker-end

1. Wählen Sie das App- ![ Startfeld aus ](../../media/7502f4ec-3c9a-435d-a7b4-b9cda85189a7.png) , und wählen Sie dann **Admin**aus.
   
    Sie können die gesuchte App nicht finden? Wählen Sie im App-Startfeld **alle apps** aus, um eine alphabetische Liste der apps anzuzeigen, die Ihnen zur Verfügung stehen. Hier können Sie nach einer bestimmten App suchen. 
    
2. Wählen Sie **Admin Center**aus, und wählen Sie dann **Exchange**aus.
    
3. Wählen Sie unter Nachrichtenfluss die Option **Regeln**aus.
    
4. Wählen Sie das **+** Symbol (hinzufügen) aus, und wählen Sie **Haftungsausschlüsse anwenden**aus.
    
5. Benennen Sie die Regel.
    
6. Wählen Sie unter **diese Regel anwenden** **die Option [für alle Nachrichten anwenden]** aus.
    
    > [!TIP]
    > [Erfahren Sie mehr](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/signatures#Scoping) zum Anwenden von Bedingungen, wenn der Haftungsausschluss nicht auf alle Nachrichten angewendet werden soll. (Dieser Bereichs Übersichtsartikel ist für Exchange Server, gilt aber auch für Microsoft 365.) 
  
7. Lassen Sie unter "Folgendes ausführen" die Option **Haftungsausschluss anfügen** ausgewählt. 
    
8.  Wählen Sie **Text eingeben** aus, und geben Sie Ihren Haftungsausschluss ein. 
    
    > [!TIP]
    > [Erfahren Sie mehr](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/signatures#FormatDisclaimer) zum Formatieren von Haftungsausschlüssen. (Dieser Formatierungs Artikel ist für Exchange Server, gilt aber auch für Microsoft 365.) 

9. Wählen Sie **einen auswählen** aus, und wählen Sie **umbrechen** als Fallback Option aus. Klicken Sie dann auf **OK**. Dies bedeutet: Wenn der Haftungsausschluss wegen Verschlüsselung oder einer anderen E-Mail-Einstellung nicht hinzugefügt werden kann, wird er in einen Nachrichtenumschlag eingeschlossen.
    
10. Leave **Audit this rule with severity level** selected. Then choose **Low**, **Medium**, or **High** to be used in the message log. 
    
11. Wählen Sie **Erzwingen** aus, um den Haftungsausschluss sofort zu aktivieren, wenn Sie ihn nicht zuerst testen möchten. 
    
12. Wählen Sie **Weitere Optionen** aus, um zusätzliche Bedingungen oder Ausnahmen einzubeziehen. 
    
13. Wenn Sie fertig sind, wählen Sie **Speichern** aus. 
    
## <a name="limitations-of-organization-wide-signatures"></a>Einschränkungen von organisationsweiten Signaturen

Mit Microsoft 365-Signaturen können Sie Folgendes nicht ausführen:
  
- Einfügen der Signatur direkt unter der letzten e-Mail-Antwort oder Weiterleitung
    
- Anzeigen von serverseitigen e-Mail-Signaturen im Ordner "Gesendete Elemente" der Benutzer
    
- Einbetten von Bildern in e-Mail-Signaturen
    
- Zeilen überspringen, die Variablen enthalten, die nicht aktualisiert werden konnten (beispielsweise, weil der Wert für einen Benutzer nicht angegeben wurde)
    
Um diese und andere Funktionen zu erhalten, verwenden Sie ein Drittanbietertool. Führen Sie eine Internetsuche für die **e-Mail-Signatur Software**aus. Eine Reihe dieser Anbieter sind Microsoft Gold-Partner, deren Software diese Funktionen bereitstellt. 
  
## <a name="more-resources"></a>Weitere Ressourcen

- Informationen zur Verwendung von PowerShell finden Sie unter [organisationsweite Nachrichten Haftungsausschlüsse, Signaturen, Fußzeilen oder Kopfzeilen in Microsoft 365](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/disclaimers-signatures-footers-or-headers) . 
    

