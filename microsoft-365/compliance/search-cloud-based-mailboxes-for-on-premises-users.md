---
title: Durchsuchen von Cloud-basierten Postfächern für lokale Benutzer
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
localization_priority: Priority
search.appverid:
- MOE150
- MST160
- MET150
ms.assetid: 3f7dde1a-a8ea-4366-86da-8ee6777f357c
description: Verwenden Sie das Tool für die Inhaltssuche im Security & Compliance Center, um Chatdaten von MicrosoftTeams (so genannte 1xN-Chats) für lokale Benutzer in einer Exchange-Hybridbereitstellung zu suchen und zu exportieren.
ms.openlocfilehash: 488a08067a39ff4bab61696d5faf8b7c849b4ab8
ms.sourcegitcommit: 1c90bcc5c56f24895f01c3e0423c3f6b73715c13
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "44214599"
---
# <a name="searching-cloud-based-mailboxes-for-on-premises-users"></a>Durchsuchen von Cloud-basierten Postfächern für lokale Benutzer

Wenn Ihre Organisation über eine Exchange-Hybridbereitstellung verfügt (oder Ihre Organisation eine lokale Exchange-Organisation mit Office 365 synchronisiert) und Microsoft Teams aktiviert hat, können Benutzer die Teams-Chatanwendung für Chatnachrichten verwenden. Bei cloudbasierten Benutzern werden die Chatdaten der Teams (ebenfalls *1xN-Chats* genannt) in ihrem primären cloudbasierten Postfach gespeichert. Wenn ein lokaler Benutzer die Teams-Chatanwendung verwendet, ist das primäre Postfach lokal untergebracht. Um diese Einschränkung zu umgehen, hat Microsoft ein neues Feature veröffentlicht, bei dem ein cloudbasierter Speicherbereich (bezeichnet als cloudbasiertes Postfach für lokale Benutzer) zum Speichern von Teams-Chatdaten für lokale Benutzer erstellt wird. Auf diese Weise können Sie das Tool für die Inhaltssuche im Security & Compliance Center verwenden, um Teams-Chatdaten für lokale Benutzer zu suchen und zu exportieren. 
  
Hier sind die Anforderungen und Einschränkungen für das Einrichten von cloudbasierten Postfächern für lokale Benutzer:
  
- Die Benutzerkonten in Ihrem lokalen Verzeichnisdienst (z. B. Active Directory) müssen mit Azure Active Directory, dem Verzeichnisdienst in Microsoft 365, synchronisiert werden. Dies bedeutet, dass in Microsoft 365 ein E-Mail-Benutzerkonto erstellt wird, das einem Benutzer zugeordnet ist, dessen primäres Postfach sich in der lokalen Organisation befindet.

- Der Benutzer, dessen primäres Postfach in der lokalen Organisation gespeichert ist, muss eine Microsoft Teams-Lizenz und mindestens eine Exchange Online Plan 1-Lizenz zugewiesen haben.

- In den cloudbasierten Postfächer für lokale Benutzer werden nur Teams-Chatdaten gespeichert. Ein lokaler Benutzer kann sich nicht bei dem cloudbasierten Postfach anmelden oder auf irgendeine Weise darauf zugreifen. Es kann nicht dazu verwendet werden, e-Mail-Nachrichten zu senden oder zu empfangen. 

- Sie müssen eine Anfrage an den Microsoft-Support senden, damit Ihre Organisation in den cloudbasierten Postfächern für lokale Benutzer nach Teams-Chatdaten suchen kann. Informationen hierzu finden Sie in diesem Artikel unter [Einreichen einer Anforderung an den Microsoft-Support, dieses Feature zu aktivieren](#filing-a-request-with-microsoft-support-to-enable-this-feature). 

> [!NOTE]
> Unterhaltungen eines Teams-Kanals werden immer in dem cloudbasierten Postfach gespeichert, das dem Team zugeordnet ist. Das bedeutet, dass Sie die Inhaltssuche zum Durchsuchen von Kanal-Unterhaltungen verwenden können, ohne dass Sie eine Supportanfrage einreichen müssen. Weitere Informationen zum Durchsuchen von Unterhaltungen in Teams-Kanälen finden Sie unter [Durchsuchen von Microsoft Teams und Microsoft 365-Gruppen](content-search.md#searching-microsoft-teams-and-microsoft-365-groups).
  
## <a name="how-it-works"></a>Funktionsweise

Wenn ein aktivierter Microsoft Teams-Benutzer über ein lokales Postfach verfügt und dessen Benutzerkonto/Identität in der Cloud synchronisiert wurde, erstellt Microsoft ein cloudbasiertes Postfach zum Sichern der 1xN-Teams-Chatdaten. Nach dem Speichern der Chatdaten von Teams im cloudbasierten Postfach wird dieses für die Suche indiziert. Auf diese Weise können Sie die Inhaltssuche (und mit eDiscovery-Fällen verknüpfte Suchvorgänge) verwenden, um Chatdaten von Teams für lokale Benutzer zu durchsuchen, in der Vorschau anzuzeigen und zu exportieren. Sie können auch **\*ComplianceSearch**-Cmdlets in der Security & Compliance Center PowerShell verwenden, um für lokale Benutzer nach Team-Chatdaten zu suchen. 
  
Die folgende Abbildung zeigt den Workflow, wie Teams-Chatdaten für lokale Benutzer für die Suche, Vorschau und den Export verfügbar sind.
  
![Cloudbasierte Speicherung für lokale Benutzer in Microsoft Teams](../media/EHAMShard1.png)
  
Zusätzlich zu dieser neuen Funktion können Sie die Inhaltssuche weiterhin dazu verwenden, um für lokale Benutzer Teams-Inhalte in der cloudbasierten SharePoint-Website und dem Exchange-Postfach, die mit jedem Microsoft Team und den 1xN-Chatdaten von Teams im Exchange Online-Postfach für cloudbasierte Benutzer verknüpft sind, zu suchen, in der Vorschau anzuzeigen und zu exportieren.

## <a name="filing-a-request-with-microsoft-support-to-enable-this-feature"></a>Einreichen einer Anforderung an den Microsoft-Support, dieses Feature zu aktivieren

Sie müssen eine Anforderung beim Microsoft-Support stellen, damit Ihre Organisation die grafische Benutzeroberfläche im Security & Compliance Center verwenden kann, um in den cloudbasierten Postfächern für lokale Benutzer nach Teams-Chatdaten zu suchen. Dieses Feature ist in der Security & Compliance Center PowerShell verfügbar. Sie müssen keine Supportanforderung für die Verwendung von PowerShell zum Suchen nach Teams-Chatdaten für lokale Benutzer einreichen.
  
Geben Sie die folgenden Informationen an, wenn Sie die Anforderung an den Microsoft-Support senden:
  
- Der Standarddomänenname Ihrer Organisation.

- Der Mandantenname und die Mandanten-ID Ihrer Organisation. Sie finden diese im Azure Active Directory-Portal (unter **Verwalten von ** \> **Eigenschaften**). Lesen Sie [Suchen Ihrer Microsoft 365-Mandanten-ID](https://docs.microsoft.com/onedrive/find-your-office-365-tenant-id).

- Der folgende Titel oder eine Beschreibung des Zwecks der Supportanforderung: "Anwendungs-Inhaltssuche für lokale Benutzer aktivieren". Auf diese Weise kann die Anforderung an das eDiscovery Engineering-Team geleitet werden, das die Anforderung umsetzt.

Wenn die technischen Änderungen vorgenommen wurden, erhalten Sie vom Microsoft-Support ein voraussichtliches Bereitstellungsdatum. Der Bereitstellungsvorgang dauert in der Regel 2 bis 3 Wochen, nachdem Sie die Supportanfrage abgeschickt haben.
  
### <a name="what-happens-after-this-feature-is-enabled"></a>Was geschieht nach der Aktivierung dieses Features?

Nachdem dieses Feature in Ihrer Organisation bereitgestellt wurde, werden die folgenden Änderungen in der Inhaltssuche und in Suchvorgängen, die mit einem eDiscovery-Fall im Security & Compliance Center verknüpft sind, vorgenommen:
  
- Das Kontrollkästchen **Inhalte der Office-App für lokale Benutzer hinzufügen** wird unter **Speicherorte** in der Inhaltssuche hinzugefügt.

    ![Das Kontrollkästchen "Inhalte der Office-App für lokale Benutzer hinzufügen" wird der Benutzeroberfläche der Inhaltssuche hinzugefügt.](../media/599e751e-17bd-408d-a18c-127538de6e85.png)
  
- Lokale Benutzer werden in der Auswahl der Inhaltsspeicherorte angezeigt, in der Sie die zu durchsuchenden Benutzerpostfächer auswählen.

## <a name="searching-for-teams-chat-content-in-cloud-based-mailboxes-for-on-premises-users"></a>Suchen nach Chatinhalten von Teams in cloudbasierten Postfächern für lokale Benutzer

Nachdem das Feature aktiviert wurde, können Sie die Inhaltssuche im Security & Compliance Center verwenden, um in den cloudbasierten Postfächern für lokale Benutzer nach Teams-Chatdaten zu suchen.
  
1. Gehen Sie im Security & Compliance Center auf **Suche** \> **Inhaltssuche**

2. Klicken Sie auf der Seite **Suchen** auf das Symbol ![Hinzufügen](../media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **Neue Suche**.

    Wie bereits erläutert wird das Kontrollkästchen **Inhalte der Office-App für lokale Benutzer hinzufügen** unter **Speicherorte** angezeigt. Es ist standardmäßig aktiviert.

3. Erstellen Sie die Schlüsselwortabfrage und fügen Sie der Suchabfrage Bedingungen hinzu, falls notwendig. Wenn Sie nur nach Team-Chatdaten suchen möchten, können Sie die folgende Abfrage im Feld **Schlüsselwort** hinzufügen:

    ```text
    kind:im
    ```

4. An diesem Punkt können Sie unter **Speicherorte**eine der folgenden Optionen auswählen:

    - **Alle Speicherorte:** Wählen Sie diese Option, um die Postfächer aller Benutzer in Ihrer Organisation zu durchsuchen. Wenn das Kontrollkästchen aktiviert ist, werden auch alle cloudbasierten Postfächer für lokale Benutzer durchsucht.

    - **Bestimmte Speicherorte:** Wählen Sie diese Option aus und klicken Sie dann auf **Modifizieren** \> Wählen Sie Benutzer, Gruppen oder Teams aus, um bestimmte Postfächer zu durchsuchen. Wie zuvor erläutert können Sie mit der Auswahl "Speicherorte" nach lokalen Benutzern suchen.

5. Speichern Sie die Suche und führen Sie sie aus. Alle Suchergebnisse aus den cloudbasierten Postfächern für lokale Benutzer können wie alle anderen Suchergebnisse in der Vorschau angezeigt werden. Sie können die Suchergebnisse (einschließlich aller Chatdaten von Teams) auch in eine PST-Datei exportieren. Weitere Informationen finden Sie unter: 

    - [Erstellen einer Suche](content-search.md#create-a-search)

    - [Anzeigen von Suchergebnissen in der Vorschau](content-search.md#preview-search-results)

    - [Exportieren von Inhaltssuchergebnissen ](export-search-results.md)

## <a name="using-powershell-to-search-for-teams-chat-data-in-cloud-based-mailboxes-for-on-premises-users"></a>PowerShell für die Suche nach Chatdaten von Teams in cloudbasierten Postfächern für lokale Benutzer benutzen

Sie können die Cmdlets **New-ComplianceSearch** und **Set-ComplianceSearch** in der PowerShell des Security & Compliance Centers verwenden, um cloudbasierte Postfächer für lokale Benutzer zu durchsuchen. Wie zuvor erläutert müssen Sie keine Supportanforderung für die Verwendung von PowerShell zum Suchen nach Teams-Chatdaten für lokale Benutzer einreichen. 
  
1. [Stellen Sie eine Verbindung mit der Security & Compliance Center PowerShell her](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).

2. Führen Sie den folgenden PowerShell-Befehl aus, um eine Inhaltssuche zu erstellen, die die cloudbasierten Postfächer für lokale Benutzer durchsucht.

    ```powershell
    New-ComplianceSearch <name of new search> -ContentMatchQuery <search query> -ExchangeLocation <on-premises user> -IncludeUserAppContent $true -AllowNotFoundExchangeLocationsEnabled $true  
    ```

    Der Parameter *IncludeUserAppContent* wird verwendet, um das cloudbasierte Postfach des Benutzers oder der Benutzer festzulegen, die durch den Parameter *ExchangeLocation* angegeben wurden. *AllowNotFoundExchangeLocationsEnabled* ermöglicht cloudbasierte Postfächer für lokale Benutzer. Wenn Sie den Wert `$true` für diesen Parameter verwenden, versucht die Suche nicht, das Vorhandensein des Postfachs vor dem Fortfahren zu überprüfen. Dies ist erforderlich, um die cloudbasierten Postfächer nach lokalen Benutzern zu durchsuchen, da diese Typen von Postfächern nicht als reguläre Postfächer aufgelöst werden.

    Im folgenden Beispiel wird im cloudbasierten Postfach von Sara Davis, die ein lokaler Benutzer der Organisation Contoso ist, nach Teams-Chats (Chatnachrichten) gesucht, die das Stichwort "Redstone" enthalten.
  
    ```powershell
    New-ComplianceSearch "Redstone_Search" -ContentMatchQuery "redstone AND kind:im" -ExchangeLocation sarad@contoso.com -IncludeUserAppContent $true -AllowNotFoundExchangeLocationsEnabled $true  
    ```

   Verwenden Sie nach dem Erstellen einer Suche unbedingt das Cmdlet **Start-ComplianceSearch**, um die Suche auszuführen. 
  
Weitere Informationen über diese Cmdlets finden Sie unter:
  
- [New-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/new-compliancesearch)

- [Set-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/set-compliancesearch)

- [Start-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/start-compliancesearch)

## <a name="known-issues"></a>Bekannte Probleme

- Derzeit können Sie Inhalte in cloudbasierten Postfächern für lokale Benutzer durchsuchen, in der Vorschau anzeigen und exportieren. Außerdem können Sie ein cloudbasiertes Postfach für einen lokalen Benutzer in einem Archiv platzieren, das einem eDiscovery-Fall zugeordnet ist, und eine Aufbewahrungsrichtlinie für Teams-Chats oder Kanalmeldungen an cloudbasierte Postfächer für lokale Benutzer anwenden. Derzeit können Sie jedoch keine Aufbewahrungsrichtlinie für andere Inhaltsspeicherorte (z. B. Exchange-Postfächer und SharePoint-Websites) auf cloudbasierte Postfächer für lokale Benutzer anwenden.

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

 **Wo befinden sich die cloudbasierten Postfächer für lokale Benutzer?**
  
Cloudbasierte Postfächer werden in demselben Rechenzentrum wie Ihre Organisation erstellt und gespeichert.
  
 **Gibt es andere Voraussetzungen als die Einreichung einer Supportanfrage?**
  
 Wie zuvor erläutert müssen die Identitäten von Benutzern mit lokalen Postfächern mit Ihrer cloudbasierten Organisation synchronisiert werden, damit für jedes lokale Benutzerkonto in Office 365 ein entsprechendes E-Mail-Benutzerkonto angelegt wird. Außerdem muss Ihre Organisation ein Office 365 Enterprise-Abonnement haben, wie z. B. ein Office 365 Enterprise E1-, E3- oder E5-Abonnement.
  
 **Besteht das Risiko, dass die Chatdaten der Teams verloren gehen, wenn das lokale Postfach des Benutzers in die Cloud migriert wird?**
  
Nein. Wenn Sie das primäre Postfach eines lokalen Benutzers in die Cloud migrieren, werden die Chatdaten des Teams für diesen Benutzer zum neuen cloudbasierten primären Postfach migriert.
  
 **Kann ich ein eDiscovery-Archiv oder Aufbewahrungsrichtlinien auf lokale Benutzer anwenden?**
  
Ja. Sie können eDiscovery-Archive oder Aufbewahrungsrichtlinien für Teams-Chats und Kanalnachrichten auf cloudbasierte Postfächer für lokale Benutzer anwenden.
  
 **Kann die Inhaltssuche Teams-Chats für lokale Benutzer aus der Zeit finden, bevor meine Organisation die Anforderung zur Aktivierung dieses Features eingereicht hat?**
  
Microsoft hat am 31. Januar 2018 mit der Speicherung der Teams-Chatdaten für lokale Benutzer begonnen. Wenn also die Identität eines Benutzers für lokale Teams seit diesem Datum zwischen Active Directory und Azure Active Directory synchronisiert wurde, werden die Chatdaten ihrer Teams in einem cloudbasierten Postfach gespeichert und können mithilfe der Inhaltssuche durchsucht werden. Außerdem arbeitet Microsoft daran, auch Teams-Chatdaten von vor dem 31. Januar 2018 in den cloudbasierten Postfächern für lokale Benutzer zu speichern. Weitere Informationen hierzu werden bald verfügbar sein.

 **Benötigen lokale Benutzer eine Lizenz, um Teams-Chatdaten in einem cloudbasierten Postfach zu speichern?**
  
Ja. Wenn die Chatdaten von Teams für einen lokalen Benutzer in einem cloudbasierten Postfach gespeichert werden sollen, muss dem Benutzer eine Lizenz für Microsoft Teams und eine für Exchange Online Plan in Office 365 (oder Microsoft 365) zugewiesen werden.
