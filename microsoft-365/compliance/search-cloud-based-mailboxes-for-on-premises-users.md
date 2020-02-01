---
title: Durchsuchen von Cloud-basierten Postfächern für lokale Benutzer in Office 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MST160
- MET150
ms.assetid: 3f7dde1a-a8ea-4366-86da-8ee6777f357c
description: 'Verwenden Sie das Tool für die Inhaltssuche im Security #a0 Compliance Center zum Suchen und Exportieren von verläuft-Chat Daten (als 1xN-Chats bezeichnet) für lokale Benutzer in einer Exchange-hybridbereitstellung.'
ms.openlocfilehash: d59af2e39d91bf107567016428102a5aba9cb724
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41597572"
---
# <a name="searching-cloud-based-mailboxes-for-on-premises-users-in-office-365"></a>Durchsuchen von Cloud-basierten Postfächern für lokale Benutzer in Office 365

Wenn Ihre Organisation über eine Exchange-hybridbereitstellung verfügt und Microsoft Teams aktiviert hat, können Benutzer die Chat Anwendung "Teams" für Chatnachrichten verwenden. Für den cloudbasierten Benutzer werden die Teamchat Daten (auch als 1xN- *Chats*bezeichnet) in Ihrem primären cloudbasierten Postfach gespeichert. Wenn ein lokaler Benutzer die Team Chat Anwendung verwendet, befindet sich das primäre Postfach lokal. Um diese Einschränkung zu umgehen, hat Microsoft ein neues Feature veröffentlicht, in dem ein Cloud-basierter Speicherbereich (als Cloud-basiertes Postfach für lokale Benutzer bezeichnet) zum Speichern von teamchatdaten für lokale Benutzer erstellt wurde. Auf diese Weise können Sie das Inhalts Such Tool im Security #a0 Compliance Center verwenden, um Microsoft Teams-Chat Daten für lokale Benutzer zu suchen und zu exportieren. 
  
Im folgenden sind die Anforderungen und Einschränkungen für die Einrichtung von Cloud-basierten Postfächern für lokale Benutzer aufgelistet:
  
- Die Benutzerkonten in Ihrem lokalen Verzeichnisdienst (beispielsweise Active Directory) müssen mit Azure Active Directory, dem Verzeichnisdienst in Office 365, synchronisiert werden. Dies bedeutet, dass ein e-Mail-Benutzerkonto in Office 365 erstellt wird und einem Benutzer zugeordnet ist, dessen primäres Postfach sich in der lokalen Organisation befindet.

- Dem Benutzer, dessen primäres Postfach sich in der lokalen Organisation befindet, muss eine Microsoft Teams-Lizenz und mindestens eine Exchange Online Plan 1-Lizenz zugewiesen sein.

- Das Cloud-basierte Postfach für lokale Benutzer wird nur zum Speichern von Team-Chat Daten verwendet. Ein lokaler Benutzer kann sich in keiner Weise beim cloudbasierten Postfach oder Zugriff anmelden. Es kann nicht zum Senden oder empfangen von e-Mail-Nachrichten verwendet werden. 

- Sie müssen eine Anforderung an den Microsoft-Support übermitteln, damit Ihre Organisation in den Cloud-basierten Postfächern für lokale Benutzer nach teamchatdaten suchen kann. Weitere Informationen finden Sie unter [Einreichung einer Anforderung mit dem Microsoft-Support, um dieses Feature](#filing-a-request-with-microsoft-support-to-enable-this-feature) in diesem Artikel zu aktivieren. 

> [!NOTE]
> Microsoft Teams-Kanal Unterhaltungen werden immer in dem cloudbasierten Postfach gespeichert, das dem Team zugeordnet ist. Das bedeutet, dass Sie die Inhaltssuche zum Durchsuchen von Kanal Unterhaltungen verwenden können, ohne eine Supportanfrage einreichen zu müssen. Weitere Informationen zum Durchsuchen von Teams-Kanal Unterhaltungen finden Sie unter durch [Suchen von Microsoft Teams und Office 365 Gruppen](content-search.md#searching-microsoft-teams-and-office-365-groups).
  
## <a name="how-it-works"></a>Funktionsweise

Wenn ein Microsoft Teams-aktivierter Benutzer über ein lokales Postfach verfügt und sein Benutzerkonto/seine Identität mit der Cloud synchronisiert wurde, erstellt Microsoft ein Cloud-basiertes Postfach zum Speichern von 1xN-Chat Daten. Nachdem die Microsoft Teams-Chat Daten im cloudbasierten Postfach gespeichert wurden, wird Sie für die Suche indiziert. Auf diese Weise können Sie die Inhaltssuche (und Suchvorgänge im Zusammenhang mit eDiscovery-Fällen) zum Suchen, anzeigen und Exportieren von teamchatdaten für lokale Benutzer verwenden. Sie können auch ** \*ComplianceSearch** -Cmdlets im Security #a0 Compliance Center PowerShell verwenden, um nach teamchatdaten für lokale Benutzer zu suchen. 
  
Die folgende Grafik zeigt den Workflow, wie Microsoft Teams-Chat Daten für lokale Benutzer für die Suche, Vorschau und den Export zur Verfügung stehen.
  
![Cloud-basierter Speicher für lokale Benutzer in Microsoft Teams](media/895845f8-2ceb-47ed-96c9-5ab7f1aea916.png)
  
Zusätzlich zu dieser neuen Funktion können Sie weiterhin die Inhaltssuche zum Durchsuchen, anzeigen und Exportieren von Microsoft Teams-Inhalten in der cloudbasierten SharePoint-Website und zum Exchange-Postfach verwenden, das den einzelnen Microsoft Teams-und 1xN-Team Chat Daten im Exchange Online Postfach für Cloud-basierte Benutzer.

## <a name="filing-a-request-with-microsoft-support-to-enable-this-feature"></a>Einreichen einer Anforderung mit dem Microsoft-Support, um diese Funktion zu aktivieren

Sie müssen eine Anforderung mit dem Microsoft-Support einreichen, damit Ihre Organisation die grafische Benutzeroberfläche im Security #a0 Compliance Center zum Suchen von teamchatdaten in den cloudbasierten Postfächern für lokale Benutzer verwenden kann. Dieses Feature steht in Security #a0 Compliance Center PowerShell zur Verfügung. Sie müssen keine Supportanfrage übermitteln, um PowerShell zum Suchen von teamchatdaten für lokale Benutzer zu verwenden. 
  
Schließen Sie die folgenden Informationen ein, wenn Sie die Anforderung an den Microsoft-Support übermitteln:
  
- Der Standarddomänenname Ihrer Office 365 Organisation.
    
- Der Mandantenname und die Mandanten-ID Ihrer Office 365 Organisation. Sie finden diese im Azure Active Directory-Portal (unter Eigenschaften **Verwalten** \> ****). Weitere Informationen finden Sie unter [Suchen Ihrer Office 365 Mandanten-ID](https://support.office.com/article/6891b561-a52d-4ade-9f39-b492285e2c9b).
    
- Der folgende Titel oder die Beschreibung des Zwecks der Supportanforderung: "Aktivieren der Anwendungsinhalts Suche für lokale Benutzer". Dadurch wird die Anforderung an das Office 365 eDiscovery-Entwicklungsteam weitergeleitet, das die Anforderung implementiert. 
    
Nachdem die technische Änderung vorgenommen wurde, wird Ihnen der Microsoft-Support ein geschätztes Bereitstellungsdatum senden. Der Bereitstellungsprozess dauert normalerweise 2 bis 3 Wochen, nachdem Sie die Supportanfrage gesendet haben. 
  
### <a name="what-happens-after-this-feature-is-enabled"></a>Was geschieht, nachdem dieses Feature aktiviert wurde?

Nachdem dieses Feature in Ihrer Office 365 Organisation bereitgestellt wurde, werden die folgenden Änderungen an der Inhaltssuche und in Suchvorgängen im Zusammenhang mit einem eDiscovery-Fall im Security #a0 Compliance Center vorgenommen:
  
- Das Kontrollkästchen **Office-App-Inhalt für lokale Benutzer hinzufügen** wird unter **der Suche nach Inhalten** hinzugefügt. 
    
    ![Das Kontrollkästchen "Office-App-Inhalt für lokale Benutzer hinzufügen" wird der Benutzeroberfläche für die Inhaltssuche hinzugefügt.](media/599e751e-17bd-408d-a18c-127538de6e85.png)
  
- Lokale Benutzer werden in der Auswahl für inhaltsspeicherorte angezeigt, die Sie zum Auswählen von zu durchsuchenden Benutzerpostfächern verwenden. 

## <a name="searching-for-teams-chat-content-in-cloud-based-mailboxes-for-on-premises-users"></a>Suchen nach teamchats-Inhalten in cloudbasierten Postfächern für lokale Benutzer

Nachdem das Feature aktiviert wurde, können Sie die Inhaltssuche im Security #a0 Compliance Center verwenden, um nach teamchatdaten in den Cloud-basierten Postfächern für lokale Benutzer zu suchen. 
  
1. Wechseln Sie im Security #a0 Compliance Center zu **Such** \> **Inhaltssuche**
    
2. Klicken Sie **** ![auf der Seite Suche auf Symbol](media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **neue Suche**hinzufügen.
    
    Wie bereits erläutert, wird das Kontrollkästchen **Office-App-Inhalt für lokale Benutzer hinzufügen** unter **Standorte**angezeigt. Sie ist standardmäßig ausgewählt.
    
3. Erstellen Sie die Stichwortabfrage, und fügen Sie bei Bedarf der Suchabfrage Bedingungen hinzu. Um nur nach Team Chats-Daten zu suchen, können Sie die folgende Abfrage im Feld **Schlüsselwörter** hinzufügen: 

    ```text
    kind:im
    ```

4. An dieser Stelle können Sie eine der folgenden Optionen unter **Standorte**auswählen:

    - **Alle Standorte:** Wählen Sie diese Option aus, um die Postfächer aller Benutzer in Ihrer Organisation zu durchsuchen. Wenn das Kontrollkästchen aktiviert ist, werden auch alle Cloud-basierten Postfächer für lokale Benutzer durchsucht. 

    - **Bestimmte Standorte:** Wählen Sie diese Option aus, und klicken Sie dann auf Benutzer, Gruppen oder Teams zum Durchsuchen bestimmter Postfächer **ändern** \> . Wie bereits erläutert, können Sie mit der Speicherorts Auswahl nach lokalen Benutzern suchen. 
    
5. Speichern Sie die Suche, und führen Sie Sie aus. Alle Suchergebnisse aus den cloudbasierten Postfächern für lokale Benutzer können wie andere Suchergebnisse in der Vorschau angezeigt werden. Sie können auch die Suchergebnisse (einschließlich aller teamchats-Daten) in eine PST-Datei exportieren. Weitere Informationen finden Sie unter: 

    - [Create a search](content-search.md#create-a-search)

    - [Preview search results](content-search.md#preview-search-results)

    - [Exportieren von Inhaltssuchergebnissen ](export-search-results.md)

## <a name="using-powershell-to-search-for-teams-chat-data-in-cloud-based-mailboxes-for-on-premises-users"></a>Verwenden von PowerShell zum Suchen von teamchatdaten in Cloud-basierten Postfächern für lokale Benutzer

Sie können die Cmdlets **New-ComplianceSearch** und **ComplianceSearch** in der PowerShell Security #a0 Compliance Center verwenden, um das Cloud-basierte Postfach für lokale Benutzer zu durchsuchen. Wie bereits erläutert, müssen Sie keine Supportanfrage übermitteln, um PowerShell zum Suchen von teamchatdaten für lokale Benutzer zu verwenden. 
  
1. Stellen [Sie eine Verbindung mit Security #a0 Compliance Center PowerShell her](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).

2. Führen Sie den folgenden PowerShell-Befehl aus, um eine Inhaltssuche zu erstellen, die die cloudbasierten Postfächer von lokalen Benutzern durchsucht.

    ```powershell
    New-ComplianceSearch <name of new search> -ContentMatchQuery <search query> -ExchangeLocation <on-premises user> -IncludeUserAppContent $true -AllowNotFoundExchangeLocationsEnabled $true  
    ```

    Der Parameter *IncludeUserAppContent* wird verwendet, um das cloudbasierten Postfach für den Benutzer oder die Benutzer anzugeben, die durch den *ExchangeLocation* -Parameter angegeben werden. Das *AllowNotFoundExchangeLocationsEnabled* ermöglicht Cloud-basierte Postfächer für lokale Benutzer. Wenn Sie den `$true` Wert für diesen Parameter verwenden, versucht die Suche nicht, das vorhanden sein des Postfachs zu überprüfen, bevor es ausgeführt wird. Dies ist erforderlich, um die Cloud-basierten Postfächer für lokale Benutzer zu durchsuchen, da diese Typen von Postfächern nicht als reguläre Postfächer aufgelöst werden. 

    Im folgenden Beispiel wird nach Microsoft Teams-Chats (Sofortnachrichten) gesucht, die das Schlüsselwort "Redstone" im cloudbasierten Postfach von Sara Davis, einem lokalen Benutzer in der Contoso-Organisation, enthalten.
  
    ```powershell
    New-ComplianceSearch "Redstone_Search" -ContentMatchQuery "redstone AND kind:im" -ExchangeLocation sarad@contoso.com -IncludeUserAppContent $true -AllowNotFoundExchangeLocationsEnabled $true  
    ```

   Nachdem Sie eine Suche erstellt haben, müssen Sie das Cmdlet **Start-ComplianceSearch** verwenden, um die Suche auszuführen. 
  
Weitere Informationen zur Verwendung dieser Cmdlets finden Sie unter:
  
- [New-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/new-compliancesearch)

- [Set-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/set-compliancesearch)

- [Start-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/start-compliancesearch)

## <a name="known-issues"></a>Bekannte Probleme

- Derzeit können Sie nur Inhalte in Cloud-basierten Postfächern für lokale Benutzer suchen, anzeigen und exportieren. Das Platzieren eines cloudbasierten Postfachs für einen lokalen Benutzer in einem halten, das einem eDiscovery-Fall zugeordnet ist, oder das Zuweisen dieser zu einer Office 365-Aufbewahrungsrichtlinie wird nicht unterstützt. 

- Die Inhaltsspeicherort-Auswahl für eDiscovery-Haltestatus zeigt lokale Benutzer an und lässt Sie Sie auswählen. Wie bereits erläutert, wird der Aufbewahrungs Status jedoch nicht auf den lokalen Benutzer angewendet.

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

 **Wo befinden sich Cloud-basierte Postfächer für lokale Benutzer?**
  
Cloudbasierten Postfächer werden in demselben Rechenzentrum wie Ihre Office 365 Organisation erstellt und gespeichert. 
  
 **Gibt es andere Anforderungen als das Einreichen einer Supportanfrage?**
  
 Wie bereits erläutert, müssen die Identitäten von Benutzern mit on-Prem-Postfächern mit ihrer cloudbasierten Organisation synchronisiert werden, damit für jedes lokale Benutzerkonto in Office 365 ein entsprechendes e-Mail-Benutzerkonto erstellt wird. Ihre Organisation muss außerdem über ein Office 365 Enterprise-Abonnement verfügen, beispielsweise ein Office 365 Enterprise E1-, E3-oder E5-Abonnement. 
  
 **Besteht das Risiko, dass die Chat Daten des Teams verloren gehen, wenn das lokale Postfach des Benutzers in die Cloud migriert wird?**
  
Nein. Wenn Sie das primäre Postfach eines lokalen Benutzers in die Cloud migrieren, werden die Chat Daten des Teams für diesen Benutzer zu Ihrem neuen cloudbasierten primären Postfach migriert.
  
 **Kann ich eine eDiscovery Hold-oder Office 365-Aufbewahrungsrichtlinie auf lokale Benutzer anwenden?**
  
Nein.
  
 **Kann die Inhaltssuche ältere Microsoft Teams-Chats für lokale Benutzer suchen, bevor meine Organisation die Anforderung zur Aktivierung dieser Funktion übermittelt hat?**
  
Microsoft hat am 31. Januar 2018 begonnen, die Chatdaten der Teams für lokale Benutzer zu speichern. Wenn also die Identität eines lokalen Teams-Benutzers zwischen Active Directory und Azure Active Directory seit diesem Datum synchronisiert wurde, werden Ihre Teams-Chat Daten in einem cloudbasierten Postfach gespeichert und können mithilfe der Inhaltssuche durchsucht werden. Microsoft arbeitet außerdem an der Speicherung von teamchatdaten vor dem 31. Januar 2018 in den Cloud-basierten Postfächern für lokale Benutzer. Weitere Informationen dazu sind in Kürze verfügbar.

 **Benötigen lokale Benutzer eine Lizenz zum Speichern von Microsoft Teams-Chat Daten in einem cloudbasierten Postfach?**
  
Ja. Zum Speichern von teamchatdaten für einen lokalen Benutzer in einem cloudbasierten Postfach muss dem Benutzer eine Microsoft Teams-Lizenz und eine Exchange Online Plan Lizenz in Office 365 (oder Microsoft 365) zugewiesen sein.
