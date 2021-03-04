---
title: Ändern der Aufbewahrungsdauer für ein inaktives Postfach
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 8/29/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: bdee24ed-b8cf-4dd0-92ae-b86ec4661e6b
ms.custom:
- seo-marvel-apr2020
description: Nachdem ein Office 365-Postfach inaktiv gemacht wurde, ändern Sie die Aufbewahrungsdauer oder die Office 365-Aufbewahrungsrichtlinie, die dem inaktiven Postfach zugewiesen ist.
ms.openlocfilehash: ec8a4cac7d2ee8e40bd791bd531556d1151c1ad1
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2021
ms.locfileid: "50421634"
---
# <a name="change-the-hold-duration-for-an-inactive-mailbox"></a>Ändern der Aufbewahrungsdauer für ein inaktives Postfach

Ein inaktives Postfach wird verwendet, um die E-Mails eines ehemaligen Mitarbeiters aufzubewahren, nachdem dieser die Organisation verlassen hat. Ein Postfach wird inaktiv, wenn ein In-Place-Speicher, eine Microsoft 365-Aufbewahrungsrichtlinie oder ein Speicher, der einem eDiscovery-Fall zugeordnet ist, für das Postfach platziert wird und das entsprechende Benutzerkonto gelöscht wird. Die Inhalte eines inaktiven Postfachs werden für die Dauer der Archivierung beibehalten, die für das Postfach aktiviert wurde, bevor es inaktiv gemacht wurde. Die Aufbewahrungsdauer definiert die Aufbewahrungsdauer von Elementen im Ordner „Wiederherstellbare Elemente". Wenn die Aufbewahrungsdauer für ein Element im Ordner „Wiederherstellbare Elemente" abläuft, wird das Element dauerhaft aus dem inaktiven Postfach gelöscht. Nachdem ein Postfach inaktiv gemacht wurde, können Sie die Aufbewahrungsdauer oder die Microsoft 365-Aufbewahrungsrichtlinie ändern, die dem inaktiven Postfach zugewiesen ist.
  
> [!IMPORTANT]
> Da wir weiterhin auf unterschiedliche Weise investieren, um Postfachinhalte zu erhalten, wird der In-Place im Exchange Admin Center angekündigt. Das bedeutet, dass Sie die Aufbewahrungsrichtlinien für Rechtsstreitigkeiten und Microsoft 365 verwenden sollten, um ein inaktives Postfach zu erstellen. Ab dem 1. April 2020 können Sie keine neuen In-Place in Exchange Online erstellen. Sie können jedoch weiterhin die Haltedauer eines In-Place inaktiven Postfachs ändern. Ab dem 1. Juli 2020 können Sie die Haltedauer jedoch nicht mehr ändern. Sie können nur ein inaktives Postfach löschen, indem Sie die In-Place entfernen. Vorhandene inaktive Postfächer, die sich im In-Place befinden, bleiben bis zum Entfernen des Haltespeichers erhalten. Weitere Informationen zum Austritt von In-Place finden Sie unter [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md).
  
## <a name="connect-to-powershell"></a>Herstellen einer Verbindung mit PowerShell

- Zum Ändern der Aufbewahrungsdauer für ein Beweissicherungsverfahren für ein aktives Postfach müssen Sie die Exchange Online PowerShell verwenden. Sie können nicht die Exchange-Verwaltungskonsole (EAC) verwenden. Sie können Exchange Online PowerShell oder die Exchange-Verwaltungskonsole jedoch verwenden, um die Aufbewahrungsdauer für einen In-Situ-Speicher zu ändern. Sie können das Security and Compliance Center oder das Security & Compliance Center PowerShell verwenden, um die Aufbewahrungsdauer für eine Microsoft 365-Aufbewahrungsrichtlinie zu ändern.
    
- Informationen zum Herstellen einer Verbindung mit Exchange Online PowerShell oder Security & Compliance Center PowerShell finden Sie in einem der folgenden Themen:
    
  - [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)
    
  - [Herstellen einer Verbindung mit Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)
    
- Für eDiscovery-Fälle zugeordnete Haltedauern sind unendliche Halte, d. h. es gibt keine Haltedauer, die geändert werden kann. Elemente werden dauerhaft aufbewahrt oder bis der Haltebereich entfernt wird und das inaktive Postfach gelöscht wird.
    
- Weitere Informationen zu inaktiven Postfächern finden Sie unter [Inactive mailboxes in Microsoft 365](inactive-mailboxes-in-office-365.md).
    
## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a>Schritt 1: Identifizieren der Haltebereiche für ein inaktives Postfach

Da verschiedene Arten von Aufbewahrungsspeichern oder eine oder mehrere Microsoft 365-Aufbewahrungsrichtlinien für ein inaktives Postfach platziert werden können, besteht der erste Schritt in der Identifizierung der Haltefächer für ein inaktives Postfach.
  
Führen Sie in Exchange Online PowerShell den folgenden Befehl aus, um die Informationen zu Haltebereichen für alle inaktiven Postfächer in Ihrer Organisation anzuzeigen.
  
```powershell
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,LitigationHoldDuration,InPlaceHolds
```

Der Wert **True** für die Eigenschaft **LitigationHoldEnabled** gibt an, dass für das inaktive Postfach ein Beweissicherungsverfahren aktiviert ist. Wenn eine In-Place, eDiscovery-Aufbewahrungsrichtlinie oder Microsoft 365-Aufbewahrungsrichtlinie für ein inaktives Postfach platziert wird, wird eine GUID für die Aufbewahrungs- oder Aufbewahrungsrichtlinie als Wert für die **InPlaceHolds-Eigenschaft** angezeigt. Im folgenden Beispiel werden Ergebnisse für fünf inaktive Postfächer angezeigt. 
  
```text
DisplayName           : Ann Beebe
Name                  : annb
IsInactiveMailbox     : True
LitigationHoldEnabled : True
LitigationHoldDuration: 365.00:00:00
InPlaceHolds          : {}
...
DisplayName           : Pilar Pinilla
Name                  : pilarp
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {c0ba3ce811b6432a8751430937152491}
...
DisplayName           : Mario Necaise
Name                  : marion
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {}
...
DisplayName           : Carol Olson
Name                  : carolo
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {mbxcdbbb86ce60342489bff371876e7f224}
...
DisplayName           : Abraham McMahon
Name                  : abrahamm
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {UniH7d895d48-7e23-4a8d-8346-533c3beac15d}
```

In der folgenden Tabelle sind fünf unterschiedliche Haltebereichstypen aufgeführt, die verwendet wurden, um die einzelnen Postfächer als inaktiv zu markieren.
  
|**Inaktives Postfach**|**Haltebereichstyp**|**Wie Sie den Haltebereich für das inaktive Postfach erkennen**|
|:-----|:-----|:-----|
|Ann Beebe  <br/> |Beweissicherungsverfahren  <br/> |Die  *LitigationHoldEnabled*  -Eigenschaft wird festgelegt auf  `True`.  <br/> |
|Pilar Pinilla  <br/> |Compliance-Archiv  <br/> |Die  *InPlaceHolds*  -Eigenschaft enthält die GUID des In-Situ-Speichers, in dem das inaktive Postfach platziert wird. Sie können erkennen, dass es sich hierbei um einen In-Situ-Speichern handelt, da die ID nicht mit einem Präfix beginnt.  <br/> Sie können den Befehl  `Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL` in Exchange Online PowerShell verwenden, um Informationen zu dem In-Situ-Speicher für das inaktive Postfach zu erhalten.  <br/> |
|Mario Necaise  <br/> |Organisationsweite Microsoft 365-Aufbewahrungsrichtlinie im Security & Compliance Center  <br/> |Die  *InPlaceHolds*  -Eigenschaft ist leer. Dies gibt an, dass eine oder mehrere organisationsweite oder (exchangeweite) Microsoft 365-Aufbewahrungsrichtlinie auf das inaktive Postfach angewendet wird. In diesem Fall können Sie den Befehl in Exchange Online PowerShell ausführen, um eine Liste der GUIDs für organisationsweite  `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` Microsoft 365-Aufbewahrungsrichtlinien zu erhalten. Die GUID für organisationsweite Aufbewahrungsrichtlinien, die auf #A0 angewendet werden, beginnt mit dem  `mbx` Präfix, z. B.  `mbxa3056bb15562480fadb46ce523ff7b02` .  <br/> <br/>Führen Sie zum Identitätsieren der Microsoft 365-Aufbewahrungsrichtlinie, die auf das inaktive Postfach angewendet wird, den folgenden Befehl in Security & Compliance Center PowerShell aus.  <br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/>
|Carol Olson  <br/> |Microsoft 365-Aufbewahrungsrichtlinie im Security & Compliance Center auf bestimmte Postfächer angewendet  <br/> |Die  *InPlaceHolds-Eigenschaft*  enthält die GUID der Microsoft 365-Aufbewahrungsrichtlinie, die auf das inaktive Postfach angewendet wird. Sie können erkennen, dass es sich hierbei um eine Aufbewahrungsrichtlinie handelt, die auf bestimmte Postfächer angewendet wurde, da die GUID mit dem Präfix  `mbx` beginnt. Wenn die GUID der Aufbewahrungsrichtlinie, die auf das inaktive Postfach angewendet wurde, mit dem Präfix gestartet wurde, würde dies darauf hinweisen, dass die Aufbewahrungsrichtlinie auf  `skp` Skype for Business-Unterhaltungen angewendet wird.  <br/><br/> Führen Sie zum Identitätsieren der Microsoft 365-Aufbewahrungsrichtlinie, die auf das inaktive Postfach angewendet wird, den folgenden Befehl in Security & Compliance Center PowerShell aus.<br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name` <br/><br/>Entfernen Sie die Präfix  `mbx` oder  `skp`, wenn Sie diesen Befehl ausführen.  <br/> |
|Abraham McMahon  <br/> |eDiscovery-Fallsicherung im Security & Compliance Center  <br/> |Die  *InPlaceHolds*  -Eigenschaft enthält die GUID des eDiscovery-Falls, in dem das inaktive Postfach platziert wird. Sie können erkennen, dass es sich hierbei um einen eDiscovery-Fall handelt, da die GUID mit dem Präfix  `UniH` beginnt.  <br/> Sie können das Cmdlet in Security & Compliance Center PowerShell verwenden, um Informationen zum eDiscovery-Fall zu erhalten, dem das Archiv für das inaktive Postfach  `Get-CaseHoldPolicy` zugeordnet ist. Sie können beispielsweise den Befehl  `Get-CaseHoldPolicy <hold GUID without prefix> | FL Name` to display the name of the case hold that's on the inactive mailbox. Be sure to remove the  `UniH`, wenn Sie diesen Befehl ausführen.  <br/><br/> Führen Sie die folgenden Befehle aus, um den eDiscovery-Fall zu identifizieren, mit dem der Haltebereich für das inaktive Postfach verknüpft ist.  <br/><br/> `$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>`<br/><br/> `Get-ComplianceCase $CaseHold.CaseId | FL Name`<br/><br/><br/> **Hinweis:** Es wird nicht empfohlen, eDiscovery-Haltefächer für inaktive Postfächer zu verwenden. Grund hierfür ist, dass eDiscovery-Fälle für bestimmte zeitgebundene Fälle im Zusammenhang mit einem rechtlichen Problem vorgesehen sind. Eine Rechtsstreitigkeit endet wahrscheinlich irgendwann, und der mit dem Fall verknüpfte Haltebereich wird entfernt, und der eDiscovery-Fall wird geschlossen (oder gelöscht). Wenn ein Haltebereich für ein inaktives Postfach mit einem eDiscovery-Fall verknüpft ist und der Haltebereich freigegeben oder der eDiscovery-Fall geschlossen oder gelöscht wird, wird das inaktive Postfach dauerhaft gelöscht. 

Weitere Informationen zu Microsoft 365-Aufbewahrungsrichtlinien finden Sie [unter Informationen zu Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen.](retention.md)
  
## <a name="step-2-change-the-hold-duration-for-an-inactive-mailbox"></a>Schritt 2: Ändern der Aufbewahrungsdauer für ein inaktives Postfach

Nachdem Sie ermittelt haben, welche Art von Haltebereich für das inaktive Postfach aktiviert ist (und ob es mehrere Haltebereiche gibt), wird im nächsten Schritt die Dauer des Haltebereichs geändert. 
  
### <a name="change-the-duration-for-a-litigation-hold"></a>Ändern der Dauer für ein Beweissicherungsverfahren

Im Folgenden erfahren Sie, wie Sie die Exchange Online PowerShell zum Ändern der Aufbewahrungsdauer für ein Beweissicherungsverfahren verwenden, das auf einem inaktiven Postfach platziert wird. Sie können nicht die EAC verwenden. Führen Sie zum Ändern der Aufbewahrungsdauer den folgenden Befehl aus. In diesem Beispiel wird die Aufbewahrungsdauer auf unbegrenzt festgelegt.
  
```powershell
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldDuration unlimited
```

Dadurch werden die Elemente im inaktiven Postfach unbegrenzt beibehalten oder bis der Haltebereich entfernt oder die Aufbewahrungsdauer in einen anderen Wert geändert wird.
  
> [!TIP]
> Die beste Methode zum Identifizieren eines inaktiven Postfachs ist die Verwendung des **Distinguished Name** oder des **Exchange GUID** -Werts. Durch Verwenden eines dieser Werte können Sie verhindern, versehentlich das falsche Postfach anzugeben. 
  
### <a name="change-the-duration-for-an-in-place-hold"></a>Ändern der Dauer für einen In-Situ-Speicher

 In-Place Halte halte wurden eingestellt und können nicht mehr geändert werden. Wenn für ein inaktives Postfach ein In-Place angewendet wird, können Sie die Haltedauer nicht ändern. Sie können nur das In-Place entfernen, was zum Löschen des inaktiven Postfachs führt. Weitere Informationen finden Sie unter [Löschen eines inaktiven Postfachs](delete-an-inactive-mailbox.md#remove-in-place-holds).
  
## <a name="more-information"></a>Weitere Informationen

- **Wie wird die Aufbewahrungsdauer für ein Element in einem inaktiven Postfach berechnet?** Die Dauer wird anhand des ursprünglichen Datums berechnet, an dem ein Postfach empfangen oder erstellt wurde. 
    
- **Was geschieht, wenn die Aufbewahrungsdauer abläuft?** Wenn die Aufbewahrungsdauer für ein Postfachelement im Ordner „Wiederherstellbare Elemente" abläuft, wird das Element dauerhaft aus dem inaktiven Postfach gelöscht. Wenn für das inaktive Postfach keine Dauer angegeben ist, werden Elemente im Ordner "Wiederherstellbare Elemente" nie gelöscht (es sei denn, die Haltedauer für das inaktive Postfach wird geändert). 
    
- **Wird eine Exchange-Aufbewahrungsrichtlinie für inaktive Postfächer weiterhin verarbeitet?** Wenn eine Exchange-Aufbewahrungsrichtlinie (Messaging-Datensatzverwaltung, MRM-Funktion inExchange Online) auf ein Postfach angewendet wurde, als es als inaktiv markiert wurde, werden die Löschrichtlinien (hierbei handelt es sich um Aufbewahrungstags mit der Aufbewahrungsaktion **Delete** ) weiterhin auf das inaktive Postfach angewendet. Mit einer Löschrichtlinie markierte Elemente werden demnach in den Ordner „Wiederherstellbare Elemente" verschoben, wenn die Aufbewahrungsrichtlinie abläuft. Diese Elemente werden dann aus dem inaktiven Postfach gelöscht, wenn die Aufbewahrungsdauer für ein Element abläuft. 
    
    Umgekehrt werden einem inaktiven Postfach zugewiesene Archivrichtlinien (mit der Aufbewahrungsaktion **MoveToArchive** konfigurierte Aufbewahrungstags) ignoriert, die in der Aufbewahrungsrichtlinie enthalten sind. Elemente in einem inaktiven Postfach, die mit einer Archivrichtlinie markiert sind, verbleiben demnach im primären Postfach, wenn die Aufbewahrungsdauer abläuft. Sie werden nicht in das Archivpostfach oder in den Ordner „Wiederherstellbare Elemente" im Archivpostfach verschoben. Da sich ein Benutzer nicht an einem inaktiven Postfach anmelden kann, gibt es keinen Grund, Rechenzentrumsressourcen für das Verarbeiten von Archivrichtlinien zu verwenden. 

- **Führen Sie die folgenden Befehle aus, um die neue Haltedauer für ein Prozesssicherungsverfahren zu überprüfen.** 

   ```powershell
    Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | FL LitigationHoldDuration
    ```

- **Wie bei regulären Postfächern verarbeitet der Assistent für verwaltete Ordner auch inaktive Postfächer.** In Exchange Online verarbeitet die MFA Postfächer ungefähr alle sieben Tage. Nachdem Sie die Aufbewahrungsdauer für ein inaktives Postfach geändert haben, können Sie das Cmdlet **Start-ManagedFolderAssistant** verwenden, um die Verarbeitung der neuen Aufbewahrungsdauer für das inaktive Postfach sofort zu starten. Führen Sie den folgenden Befehl aus. 

    ```powershell
    Start-ManagedFolderAssistant -InactiveMailbox <identity of inactive mailbox>
    ```
   
- **Wenn viele Haltefächer für ein inaktives Postfach platziert werden, werden nicht alle Halte-GUIDs angezeigt.** Sie können den folgenden Befehl ausführen, um die GUIDs für alle Haltebereiche (mit Ausnahme von Beweissicherungsverfahren) für ein inaktives Postfach anzuzeigen. 
    
    ```powershell
    Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds
    ```
