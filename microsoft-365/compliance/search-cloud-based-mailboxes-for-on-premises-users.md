---
title: Suche nach Teams-Chatdaten für lokale Benutzer
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
description: Verwenden Sie das Tool für die Inhaltssuche im Security & Compliance Center, um Chatdaten von Teams für lokale Benutzer in einer Exchange-Hybridbereitstellung zu suchen und zu exportieren.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 23f8ea08de3d7fdbbc36274374d315ef0cb66a84
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/25/2021
ms.locfileid: "49976202"
---
# <a name="search-for-teams-chat-data-for-on-premises-users"></a>Suche nach Teams-Chatdaten für lokale Benutzer

Wenn Ihre Organisation über eine Exchange-Hybridbereitstellung verfügt (oder Ihre Organisation eine lokale Exchange-Organisation mit Office 365 synchronisiert) und Microsoft Teams aktiviert hat, können lokale Benutzer die Teams-Chatanwendung für Chatnachrichten verwenden. Bei cloudbasierten Benutzern werden die Teams-Chatdaten (auch *1:1- oder 1:n-Chats* genannt) in deren primären cloudbasierten Postfächern gespeichert. Wenn ein lokaler Benutzer die Teams-Chatanwendung verwendet, können seine Chatnachrichten nicht in seinem primären, lokalen Postfach gespeichert werden. Um diese Einschränkung zu umgehen, hat Microsoft ein neues Feature veröffentlicht, bei dem ein cloudbasierter Speicherbereich erstellt wird, der eDiscovery-Tools zum Suchen nach und exportieren von Teams-Chatdaten für lokale Benutzer verwendet.
  
Hier sind die Anforderungen und Einschränkungen für das Aktivieren von cloudbasiertem Speicher für lokale Benutzer:
  
- Die Benutzerkonten in Ihrem lokalen Verzeichnisdienst (z. B. Active Directory) müssen mit Azure Active Directory, dem Verzeichnisdienst in Microsoft 365, synchronisiert werden. Dies bedeutet, dass in Microsoft 365 ein E-Mail-Benutzerkonto erstellt wird, das einem Benutzer zugeordnet ist, dessen primäres Postfach sich in der lokalen Organisation befindet.

- Der Benutzer, dessen primäres Postfach in der lokalen Organisation gespeichert ist, muss eine Microsoft Teams-Lizenz und mindestens eine Exchange Online Plan 1-Lizenz zugewiesen haben.

- Wenn Ihre Organisation nicht über eine Exchange-Hybridbereitstellung verfügt, müssen Sie Ihr lokales Exchange-Schema mit Azure Active Directory synchronisieren. Wenn Sie das nicht tun, besteht möglicherweise das Risiko, dass in Exchange Online cloudbasierte Postfächer für Benutzer dupliziert werden, die über ein Postfach in Ihrer lokalen Exchange-Organisation verfügen.

- Im cloudbasierten Speicherbereich werden nur die Teams-Chatdaten im Zusammenhang mit einem lokalen Benutzer gespeichert. Ein lokaler Benutzer kann in keiner Weise auf diesen Speicherbereich zugreifen.

- Sie müssen eine Anfrage an den Microsoft-Support senden, damit Ihre Organisation für lokale Benutzer nach Teams-Chatdaten suchen kann. Informationen hierzu finden Sie in diesem Artikel unter [Einreichen einer Anforderung an den Microsoft-Support, dieses Feature zu aktivieren](#filing-a-request-with-microsoft-support-to-enable-this-feature).

> [!NOTE]
> Unterhaltungen eines Teams-Kanals werden immer in dem cloudbasierten Postfach gespeichert, das dem Team zugeordnet ist. Das bedeutet, dass Sie die Inhaltssuche zum Durchsuchen von Kanal-Unterhaltungen verwenden können, ohne dass Sie eine Supportanfrage einreichen müssen. Weitere Informationen zum Durchsuchen von Unterhaltungen in Teams-Kanälen finden Sie unter [Durchsuchen von Microsoft Teams und Microsoft 365-Gruppen](content-search.md#searching-microsoft-teams-and-microsoft-365-groups).
  
## <a name="how-it-works"></a>Funktionsweise

Wenn ein aktivierter Microsoft Teams-Benutzer über ein lokales Postfach verfügt und dessen Benutzerkonto/Identität mit der Cloud synchronisiert wurde, erstellt Microsoft einen cloudbasierten Speicher, mit dem die 1:n-Teams-Chatdaten des lokalen Benutzers verknüpft werden. Teams-Chatdaten für lokale Benutzer werden für die Suche indiziert. Auf diese Weise können Sie die Inhaltssuche (und mit Core eDiscovery- und Advanced eDiscovery-Fällen verknüpfte Suchvorgänge) verwenden, um Teams-Chatdaten für lokale Benutzer zu durchsuchen, in der Vorschau anzuzeigen und zu exportieren. Sie können auch **\*ComplianceSearch**-Cmdlets in der Security & Compliance Center PowerShell verwenden, um für lokale Benutzer nach Team-Chatdaten zu suchen.
  
Die folgende Abbildung zeigt den Workflow, wie Teams-Chatdaten für lokale Benutzer für die Suche, Vorschau und den Export verfügbar sind.
  
![Cloudbasierte Speicherung für lokale Benutzer in Microsoft Teams](../media/EHAMShard1.png)
  
Zusätzlich zu dieser neuen Funktion können Sie die Inhaltssuche weiterhin dazu verwenden, um für lokale Benutzer Teams-Inhalte in der cloudbasierten SharePoint-Website und dem Exchange-Postfach, die mit jedem Microsoft Team und den 1xN-Chatdaten von Teams im Exchange Online-Postfach für cloudbasierte Benutzer verknüpft sind, zu suchen, in der Vorschau anzuzeigen und zu exportieren.

## <a name="filing-a-request-with-microsoft-support-to-enable-this-feature"></a>Einreichen einer Anforderung an den Microsoft-Support, dieses Feature zu aktivieren

Sie müssen eine Anforderung beim Microsoft-Support stellen, damit Ihre Organisation die grafische Benutzeroberfläche im Security & Compliance Center verwenden kann, um für lokale Benutzer nach Teams-Chatdaten zu suchen. Dieses Feature ist in der Security & Compliance Center PowerShell verfügbar. Sie müssen keine Supportanforderung für die Verwendung von PowerShell zum Suchen nach Teams-Chatdaten für lokale Benutzer einreichen.
  
Geben Sie die folgenden Informationen an, wenn Sie die Anforderung an den Microsoft-Support senden:
  
- Der Standarddomänenname Ihrer Organisation.

- Der Mandantenname und die Mandanten-ID Ihrer Organisation. Sie finden diese im Azure Active Directory-Portal (unter **Verwalten von** \> **Eigenschaften**). Lesen Sie [Suchen Ihrer Microsoft 365-Mandanten-ID](https://docs.microsoft.com/onedrive/find-your-office-365-tenant-id).

- Der folgende Titel oder eine Beschreibung des Zwecks der Supportanforderung: "Anwendungs-Inhaltssuche für lokale Benutzer aktivieren". Auf diese Weise kann die Anforderung an das eDiscovery Engineering-Team geleitet werden, das die Anforderung umsetzt.

Wenn die technischen Änderungen vorgenommen wurden, erhalten Sie vom Microsoft-Support ein voraussichtliches Bereitstellungsdatum. Der Bereitstellungsvorgang dauert in der Regel 2 bis 3 Wochen, nachdem Sie die Supportanfrage abgeschickt haben.
  
### <a name="what-happens-after-this-feature-is-enabled"></a>Was geschieht nach der Aktivierung dieses Features?

Nachdem dieses Feature in Ihrer Organisation bereitgestellt wurde, werden die folgenden Änderungen in der Inhaltssuche und in Suchvorgängen, die mit einem eDiscovery-Fall im Security & Compliance Center verknüpft sind, vorgenommen:
  
- Das Kontrollkästchen **Inhalte der Office-App für lokale Benutzer hinzufügen** wird unter **Speicherorte** in der Inhaltssuche hinzugefügt.

    ![Das Kontrollkästchen "Inhalte der Office-App für lokale Benutzer hinzufügen" wird der Benutzeroberfläche der Inhaltssuche hinzugefügt.](../media/599e751e-17bd-408d-a18c-127538de6e85.png)
  
- Lokale Benutzer werden in der Auswahl der Inhaltsspeicherorte angezeigt, in der Sie die zu durchsuchenden Benutzerpostfächer auswählen.

## <a name="searching-for-teams-chat-content-for-on-premises-users"></a>Suchen nach Teams-Chatinhalten für lokale Benutzer

Nachdem das Feature aktiviert wurde, können Sie die Inhaltssuche im Security & Compliance Center verwenden, um für lokale Benutzer nach Teams-Chatdaten zu suchen.
  
1. Gehen Sie im Security & Compliance Center auf **Suche** \> **Inhaltssuche**

2. Klicken Sie auf der Seite **Suchen** auf das Symbol ![Hinzufügen](../media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **Neue Suche**.

    Wie bereits erläutert wird das Kontrollkästchen **Inhalte der Office-App für lokale Benutzer hinzufügen** unter **Speicherorte** angezeigt. Es ist standardmäßig aktiviert.

3. Erstellen Sie die Schlüsselwortabfrage und fügen Sie der Suchabfrage Bedingungen hinzu, falls notwendig. Wenn Sie nur nach Team-Chatdaten suchen möchten, können Sie die folgende Abfrage im Feld **Schlüsselwort** hinzufügen:

    ```text
    kind:im
    ```

4. An diesem Punkt können Sie unter **Speicherorte** eine der folgenden Optionen auswählen:

    - **Alle Speicherorte:** Wählen Sie diese Option, um die Postfächer aller Benutzer in Ihrer Organisation zu durchsuchen. Wenn das Kontrollkästchen aktiviert ist, werden auch alle cloudbasierten Speicher von Teams-Chatdaten für lokale Benutzer durchsucht.

    - **Bestimmte Speicherorte:** Wählen Sie diese Option aus und klicken Sie dann auf **Modifizieren** \> Wählen Sie Benutzer, Gruppen oder Teams aus, um bestimmte Postfächer zu durchsuchen. Wie zuvor erläutert können Sie mit der Auswahl "Speicherorte" nach Teams-Chatdaten für lokale Benutzer suchen.

5. Speichern Sie die Suche, und führen Sie sie aus. Alle Suchergebnisse für lokale Benutzer können wie alle anderen Suchergebnisse in der Vorschau angezeigt werden. Sie können die Suchergebnisse (einschließlich aller Chatdaten von Teams) auch in eine PST-Datei exportieren. Weitere Informationen finden Sie unter:

    - [Erstellen einer Suche](content-search.md#create-a-search)

    - [Anzeigen von Suchergebnissen in der Vorschau](content-search.md#preview-search-results)

    - [Exportieren von Inhaltssuchergebnissen ](export-search-results.md)

## <a name="using-powershell-to-search-for-teams-chat-data-for-on-premises-users"></a>Verwenden von PowerShell zum Suchen von Teams-Chatdaten für lokale Benutzer

Sie können die Cmdlets **New-ComplianceSearch** und **Set-ComplianceSearch** in der Security and Compliance Center PowerShell verwenden, um nach Teams-Chatdaten für lokale Benutzer zu suchen. Wie zuvor erläutert müssen Sie keine Supportanforderung für die Verwendung von PowerShell zum Suchen nach Teams-Chatdaten für lokale Benutzer einreichen.
  
1. [Stellen Sie eine Verbindung mit der Security & Compliance Center PowerShell her](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).

2. Führen Sie den folgenden PowerShell-Befehl aus, um eine Inhaltssuche zu erstellen, die nach Teams-Chatdaten für lokale Benutzer sucht.

    ```powershell
    New-ComplianceSearch <name of new search> -ContentMatchQuery <search query> -ExchangeLocation <on-premises user> -IncludeUserAppContent $true -AllowNotFoundExchangeLocationsEnabled $true  
    ```

    Der Parameter *IncludeUserAppContent* wird verwendet, um den cloudbasierten Speicher für den bzw. die durch den Parameter *ExchangeLocation* angegebenen Benutzer anzugeben. Mit *AllowNotFoundExchangeLocationsEnabled* können Sie den cloudbasierten Speicher nach lokalen Benutzern durchsuchen. Wenn Sie den Wert `$true` für diesen Parameter verwenden, versucht die Suche nicht, das Vorhandensein des Postfachs vor dem Fortfahren zu überprüfen. Dies ist erforderlich, um den cloudbasierten Speicher nach lokalen Benutzern zu durchsuchen, da dieser cloudbasierte Speicher nicht als reguläres cloudbasiertes Postfach aufgelöst wird.

    Im folgenden Beispiel wird im cloudbasierten Speicher von Sara Davis, die ein lokaler Benutzer der Organisation Contoso ist, nach Teams-Chats (Chatnachrichten) gesucht, die das Stichwort "Redstone" enthalten.
  
    ```powershell
    New-ComplianceSearch "Redstone_Search" -ContentMatchQuery "redstone AND kind:im" -ExchangeLocation sarad@contoso.com -IncludeUserAppContent $true -AllowNotFoundExchangeLocationsEnabled $true  
    ```

   Verwenden Sie nach dem Erstellen einer Suche unbedingt das Cmdlet **Start-ComplianceSearch**, um die Suche auszuführen. 
  
Weitere Informationen über diese Cmdlets finden Sie unter:
  
- [New-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/new-compliancesearch)

- [Set-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/set-compliancesearch)

- [Start-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/start-compliancesearch)

## <a name="known-issues"></a>Bekannte Probleme

- Derzeit können Sie Teams-Chatdaten für lokale Benutzer durchsuchen, in der Vorschau anzeigen und exportieren. Außerdem können Sie die Teams-Chatdaten für einen lokalen Benutzer in einem Archiv platzieren, das einem Core eDiscovery- oder Advanced eDiscovery-Fall zugeordnet ist, und eine Aufbewahrungsrichtlinie für Teams-Chats oder Kanalmeldungen für lokale Benutzer anwenden. Derzeit können Sie jedoch keine Aufbewahrungsrichtlinie für andere Inhaltsspeicherorte (z. B. Exchange-Postfächer und SharePoint-Websites) für lokale Benutzer anwenden.

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

**Wo befindet sich der cloudbasierte Speicher für lokale Benutzer?**
  
Die Chat-Daten von Teams werden im bevorzugten Datenspeicher (PDL) für einen lokalen Benutzer gespeichert. Der PDL wird sowohl in Single-Geo- als auch in Multi-Geo-Umgebungen beachtet. Mehr dazu unter [Microsoft 365 Multi-Geo](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-multi-geo).
  
 **Gibt es andere Voraussetzungen als die Einreichung einer Supportanfrage?**
  
Wie zuvor erläutert müssen die Identitäten von Benutzern mit lokalen Postfächern mit Ihrer cloudbasierten Organisation synchronisiert werden, damit für jedes lokale Benutzerkonto in Office 365 ein entsprechendes E-Mail-Benutzerkonto angelegt wird. Außerdem muss Ihre Organisation ein Office 365 Enterprise-Abonnement haben, wie z. B. ein Office 365 Enterprise E1-, E3- oder E5-Abonnement.
  
 **Besteht das Risiko, dass die Chatdaten der Teams verloren gehen, wenn das lokale Postfach des Benutzers in die Cloud migriert wird?**
  
Nein. Wenn Sie das primäre Postfach eines lokalen Benutzers in die Cloud migrieren, werden die Chatdaten des Teams für diesen Benutzer zum neuen cloudbasierten primären Postfach migriert.
  
 **Kann ich ein eDiscovery-Archiv oder Aufbewahrungsrichtlinien auf lokale Benutzer anwenden?**
  
Ja. Sie können eDiscovery-Archive oder Aufbewahrungsrichtlinien für Teams-Chats und Kanalnachrichten von lokalen Benutzern anwenden.
  
 **Kann die Inhaltssuche Teams-Chatdaten für lokale Benutzer aus der Zeit finden, bevor meine Organisation die Anforderung zur Aktivierung dieses Features eingereicht hat?**
  
Microsoft hat am 31. Januar 2018 mit der Speicherung der Teams-Chatdaten für lokale Benutzer begonnen. Wenn also die Identität eines Benutzers für lokale Teams seit diesem Datum zwischen Active Directory und Azure Active Directory synchronisiert wurde, werden ihre Teams-Chatdaten in der Cloud gespeichert und können mithilfe der Inhaltssuche durchsucht werden. Außerdem arbeitet Microsoft daran, auch Teams-Chatdaten von vor dem 31. Januar 2018 im cloudbasierten Speicher für lokale Benutzer zu speichern. Weitere Informationen hierzu werden bald verfügbar sein.

 **Benötigen lokale Benutzer eine Lizenz, um ihre Teams-Chatdaten in der Cloud zu speichern?**
  
Ja. Wenn die Teams-Chatdaten für einen lokalen Benutzer in einem cloudbasierten Speicher gespeichert werden sollen, muss dem Benutzer eine Lizenz für Microsoft Teams und eine für Exchange Online Plan in Office 365 (oder Microsoft 365) zugewiesen werden.
