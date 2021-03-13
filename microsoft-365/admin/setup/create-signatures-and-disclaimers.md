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
- seo-marvel-may2020
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 2d75860f-c527-4352-a7f6-73eba54c0c72
description: Erfahren Sie, wie Sie E-Mail-Signaturen verwalten, einschließlich rechtlicher Haftungsausschlüsse oder Offenlegungserklärungen für alle E-Mail-Nachrichten, die Ihr Unternehmen erreichen oder verlassen.
ms.openlocfilehash: c8d63a11a75b9b53de9cabdf1f4baabc61cc3e42
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926918"
---
# <a name="create-organization-wide-signatures-and-disclaimers"></a>Erstellen von organisationsweiten Signaturen und Haftungsausschlüssen

 Sie können E-Mail-Signaturen verwalten, indem Sie den E-Mail-Nachrichten, die an Ihre Organisation oder von ihr gesendet werden, eine E-Mail-Signatur, einen rechtlichen Haftungsausschluss oder eine Offenlegungserklärung hinzufügen. Das können Sie so einrichten, dass diese Hinzufügung auf alle ein- und ausgehenden Nachrichten angewendet wird, wie unten beschrieben wird. Oder Sie können sie nur auf bestimmte Nachrichten anwenden, z. B. solche, die bestimmte Wörter oder Textmuster enthalten.

 Sehen Sie sich ein kurzes Video über die Erstellung einer unternehmensweiten E-Mail-Signatur an. <br><br>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1IEWf] 

Wenn Sie dieses Video hilfreich fanden, sehen Sie sich bitte die [komplette Schulungsserie für kleine Unternehmen und diejenigen, für die Microsoft 365 neu ist](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816) an.

## <a name="create-a-signature-that-applies-to-all-messages"></a>Erstellen einer Signatur, die auf alle Nachrichten angewendet wird

> [!TIP]
> Organisationsweite Signaturen werden „Haftungsausschlüsse“ genannt, unabhängig davon, was sie einschließen. Sie können zum Beispiel nur eine Unterschrift sein, oder auch Ihre Adresse, einen Haftungsausschluss oder andere gewünschte Informationen enthalten.
    
::: moniker range="o365-worldwide"

Wechseln Sie zum Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.

::: moniker-end

::: moniker range="o365-germany"

Wechseln Sie zum Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.

::: moniker-end

::: moniker range="o365-21vianet"

Wechseln Sie zum Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn/adminportal</a>.

::: moniker-end

1. Wählen Sie den Launcher ![Das App-Startfeld-Symbol](../../media/7502f4ec-3c9a-435d-a7b4-b9cda85189a7.png) und dann **Administrator** aus.
   
    Sie können die gesuchte App nicht finden? Wählen Sie im Launcher **Alle Apps** aus, um eine alphabetische Liste der verfügbaren Apps anzuzeigen. Hier können Sie nach einer bestimmten App suchen. 
    
2. Wählen Sie **Admin Center** aus und dann **Exchange**.
    
3. Wählen Sie unter „E-Mail-Fluss“ die Option **Regeln** aus.
    
4. Wählen Sie das Symbol **+** (Hinzufügen) und dann **Haftungsausschlüsse anwenden** aus.
    
5. Benennen Sie die Regel.
    
6. Wählen Sie unter **Diese Regel anwenden** die Option **[Auf alle Nachrichten anwenden]** aus.
    
    > [!TIP]
    > [Erfahren Sie mehr](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/signatures#Scoping) zum Anwenden von Bedingungen, wenn der Haftungsausschluss nicht auf alle Nachrichten angewendet werden soll. (Dieser Artikel zur Bereichseingrenzung bezieht sich auf Exchange Server, gilt aber auch für Microsoft 365). 
  
7. Lassen Sie unter „Folgendes ausführen“ die Option **Haftungsausschluss anfügen** ausgewählt. 
    
8.  Wählen Sie **Text eingeben** aus, und geben Sie Ihren Haftungsausschluss ein. 
    
    > [!TIP]
    > [Erfahren Sie mehr](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/signatures#FormatDisclaimer) über das Formatieren von Haftungsausschlüssen. (Dieser Artikel zur Formatierung bezieht sich auf Exchange Server, gilt aber auch für Microsoft 365). 

9. Wählen Sie **Einen auswählen** aus, und wählen Sie **Umschlag** als Ausweichaktion aus. Klicken Sie dann auf **OK**. Dies bedeutet: Wenn der Haftungsausschluss wegen Verschlüsselung oder einer anderen E-Mail-Einstellung nicht hinzugefügt werden kann, wird er in einen Nachrichtenumschlag eingeschlossen.
    
10. Lassen Sie **Diese Regel mit Schweregrad überwachen** aktiviert. Wählen Sie dann einen der Werte **Niedrig**, **Mittel** oder **Hoch** aus, der im Nachrichtenprotokoll verwendet werden soll. 
    
11. Wählen Sie **Erzwingen** aus, um den Haftungsausschluss sofort zu aktivieren, wenn Sie ihn nicht zuerst testen möchten. 
    
12. Wählen Sie **Weitere Optionen** aus, um zusätzliche Bedingungen oder Ausnahmen einzubeziehen. 
    
13. Wenn Sie fertig sind, wählen Sie **Speichern** aus. 
    
## <a name="limitations-of-organization-wide-signatures"></a>Einschränkungen von organisationsweiten Signaturen

Folgendes können Sie nicht tun, wenn Sie E-Mail-Signaturen in Microsoft 365 verwalten:
  
- Die Signatur direkt unter der letzten E-Mail-Antwort oder -Weiterleitung einfügen
    
- Anzeigen serverseitiger E-Mail-Signaturen in den Ordnern „Gesendete Objekte“ der Benutzer
    
- Bildern in E-Mail-Signaturen einbetten
    
- Zeilen mit Variablen überspringen, die nicht aktualisiert werden konnten (z. B. weil der Wert für einen Benutzer nicht angegeben wurde)
    
Verwenden Sie ein Drittanbieter-Tool, um diese und andere Funktionen zum Verwalten von E-Mail-Signaturen zu erhalten. Führen Sie bitte eine Internet-Suche nach **E-Mail-Signatur-Software** durch. Eine Anzahl dieser Anbieter sind Microsoft Gold-Partner und deren Software stellt diese Funktionen zur Verfügung. 
  
## <a name="more-resources"></a>Weitere Ressourcen

- Weiter Informationen zur Verwendung von PowerShell finden Sie unter [Organisationsweite Haftungsausschlüsse, Signaturen, Fußzeilen oder Kopfzeilen für Nachrichten in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/disclaimers-signatures-footers-or-headers).