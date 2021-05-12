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
description: Verwenden Sie eDiscovery-Tools in Microsoft 365, um nach Teams-Chatdaten für lokale Benutzer in einer hybriden Exchange-Bereitstellung zu suchen und diese zu exportieren.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ab59c179b62903dd5f1ddd9b718f81a1ac78923a
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311801"
---
# <a name="search-for-teams-chat-data-for-on-premises-users"></a>Suche nach Teams-Chatdaten für lokale Benutzer

Wenn Ihre Organisation über eine Exchange-Hybridbereitstellung verfügt (oder Ihre Organisation eine lokale Exchange-Organisation mit Office 365 synchronisiert) und Microsoft Teams aktiviert hat, können lokale Benutzer die Teams-Chatanwendung für Chatnachrichten verwenden. Bei cloudbasierten Benutzern werden die Teams-Chatdaten (auch *1:1- oder 1:n-Chats* genannt) in deren primären cloudbasierten Postfächern gespeichert. Wenn ein lokaler Benutzer die Teams-Chatanwendung verwendet, können seine Chatnachrichten nicht in seinem primären, lokalen Postfach gespeichert werden. Um diese Einschränkung zu umgehen, hat Microsoft ein neues Feature veröffentlicht, bei dem ein cloudbasierter Speicherbereich erstellt wird, der eDiscovery-Tools zum Suchen nach und exportieren von Teams-Chatdaten für lokale Benutzer verwendet.
  
Hier sind die Anforderungen und Einschränkungen für das Aktivieren von cloudbasiertem Speicher für lokale Benutzer:
  
- Die Benutzerkonten in Ihrem lokalen Verzeichnisdienst (z. B. Active Directory) müssen mit Azure Active Directory, dem Verzeichnisdienst in Microsoft 365, synchronisiert werden. Dies bedeutet, dass in Microsoft 365 ein E-Mail-Benutzerkonto erstellt wird, das einem Benutzer zugeordnet ist, dessen primäres Postfach sich in der lokalen Organisation befindet.

- Der Benutzer, dessen primäres Postfach in der lokalen Organisation gespeichert ist, muss eine Microsoft Teams-Lizenz und mindestens eine Exchange Online Plan 1-Lizenz zugewiesen haben.

- Wenn Ihre Organisation nicht über eine Exchange-Hybridbereitstellung verfügt, müssen Sie Ihr lokales Exchange-Schema mit Azure Active Directory synchronisieren. Wenn Sie das nicht tun, besteht möglicherweise das Risiko, dass in Exchange Online cloudbasierte Postfächer für Benutzer dupliziert werden, die über ein Postfach in Ihrer lokalen Exchange-Organisation verfügen.

- Im cloudbasierten Speicherbereich werden nur die Teams-Chatdaten im Zusammenhang mit einem lokalen Benutzer gespeichert. Ein lokaler Benutzer kann in keiner Weise auf diesen Speicherbereich zugreifen.

> [!NOTE]
> Kanalunterhaltungen eines Teams werden immer in dem cloudbasierten Postfach gespeichert, das dem Team zugeordnet ist. Das bedeutet, das Sie nach Kanalunterhaltungen suchen können. Weitere Informationen zum Durchsuchen von Unterhaltungen in Teams-Kanälen finden Sie unter [Durchsuchen von Microsoft Teams und Microsoft 365-Gruppen](content-search-reference.md#searching-microsoft-teams-and-microsoft-365-groups).
  
## <a name="how-it-works"></a>Funktionsweise

Wenn ein aktivierter Microsoft Teams-Benutzer über ein lokales Postfach verfügt und dessen Benutzerkonto/Identität mit der Cloud synchronisiert wurde, erstellt Microsoft einen cloudbasierten Speicher, mit dem die 1:n-Teams-Chatdaten des lokalen Benutzers verknüpft werden. Teams-Chatdaten für lokale Benutzer werden für die Suche indiziert. Auf diese Weise können Sie die Inhaltssuche (und mit Core eDiscovery- und Advanced eDiscovery-Fällen verknüpfte Suchvorgänge) verwenden, um Teams-Chatdaten für lokale Benutzer zu durchsuchen, in der Vorschau anzuzeigen und zu exportieren. Sie können auch **\*ComplianceSearch**-Cmdlets in der Security & Compliance Center PowerShell verwenden, um für lokale Benutzer nach Team-Chatdaten zu suchen.
  
Die folgende Abbildung zeigt den Workflow, wie Teams-Chatdaten für lokale Benutzer für die Suche, Vorschau und den Export verfügbar sind.
  
![Cloudbasierte Speicherung für lokale Benutzer in Microsoft Teams](../media/EHAMShard1.png)
  
Zusätzlich zu dieser Funktion können Sie auch eDiscovery-Tools verwenden, um Teams-Inhalte in der cloudbasierten SharePoint-Site und im Exchange-Postfach, die mit jedem Microsoft Team verbunden sind, zu suchen, in der Vorschau anzuzeigen und zu exportieren, sowie 1xN Teams-Chatdaten im Exchange Online-Postfach für cloudbasierte Benutzer.

### <a name="how-this-feature-is-supported-in-content-search-and-core-ediscovery-search-tools"></a>Wie diese Funktion in der Inhaltssuche und den Core eDiscovery-Suchwerkzeugen unterstützt wird

Die folgenden Benutzeroberflächenelemente in der Inhaltssuche und im Suchwerkzeug, die mit Core eDiscovery-Fällen im Microsoft 365 Compliance Center verbunden sind:
  
- Das Kontrollkästchen **"App-Inhalte für lokale Benutzer hinzufügen"** wird auf der Seite des **Speicherorte**-Assistents im Inhaltssuchtool angezeigt und ist standardmäßig aktiviert. Lassen Sie dieses Kontrollkästchen aktiviert, um den Cloud-basierten Speicher für lokale Benutzer in eine Inhaltssuche einzubeziehen.

    ![Das Kontrollkästchen "Inhalte der Office-App für lokale Benutzer hinzufügen" wird der Benutzeroberfläche der Inhaltssuche hinzugefügt.](../media/EHAMShardCheckBox.png)
  
- Sie können nach lokalen Benutzern suchen, wenn Sie bestimmte Benutzer auswählen, nach denen gesucht werden soll.

## <a name="searching-for-teams-chat-content-for-on-premises-users"></a>Suchen nach Teams-Chatinhalten für lokale Benutzer

Hier erfahren Sie, wie Sie die Inhaltssuche im Microsoft 365 Compliance Center verwenden, um nach Teams-Chatdaten für lokale Benutzer zu suchen.
  
1. Gehen Sie im Microsoft 365 Compliance Center auf **Inhaltssuche**.

2. Klicken Sie auf der Registerkarte **Suchvorgängen** auf **Neue Suche** und geben Sie der neuen Suche einen Namen.

3. Setzen Sie auf der Seite **Speicherorte** den Schalter für Exchange-Postfächer auf **Ein**. Beachten Sie, dass das Kontrollkästchen **App-Inhalte für lokale Benutzer hinzufügen** angezeigt und standardmäßig aktiviert ist.

4. Wenn Sie nach Teams-Inhalten für bestimmte Benutzer suchen möchten, wählen Sie **Benutzer, Gruppen oder Teams auswählen** und dann bestimmte Benutzer aus, die in die Suche einbezogen werden sollen. Andernfalls klicken Sie auf **Weiter**, um nach Teams-Inhalten für alle Benutzer zu suchen, einschließlich lokaler Benutzer

5. Erstellen Sie auf der Seite **Suchbedingungen definieren** eine Schlüsselwortabfrage und fügen Sie der Suchabfrage bei Bedarf Kriterien hinzu. Wenn Sie nur nach Team-Chatdaten suchen möchten, können Sie die folgende Abfrage im Feld **Schlüsselwort** hinzufügen:

    ```text
    kind:im AND kind:microsoftteams
    ```

6. Senden Sie die Suche und führen Sie sie aus. Alle Suchergebnisse für lokale Benutzer können wie alle anderen Suchergebnisse in der Vorschau angezeigt werden. Sie können die Suchergebnisse (einschließlich aller Chatdaten von Teams) auch in eine PST-Datei exportieren. Weitere Informationen finden Sie unter:

    - [Erstellen einer Suche](content-search.md)

    - [Anzeigen von Suchergebnissen in der Vorschau](preview-ediscovery-search-results.md)

    - [Exportieren der Suchergebnisse](export-search-results.md)

## <a name="using-powershell-to-search-for-teams-chat-data-for-on-premises-users"></a>Verwenden von PowerShell zum Suchen von Teams-Chatdaten für lokale Benutzer

Sie können die Cmdlets **New-ComplianceSearch** und **Set-ComplianceSearch** in der Security and Compliance Center PowerShell verwenden, um nach Teams-Chatdaten für lokale Benutzer zu suchen. Wie zuvor erläutert müssen Sie keine Supportanforderung für die Verwendung von PowerShell zum Suchen nach Teams-Chatdaten für lokale Benutzer einreichen.
  
1. [Stellen Sie eine Verbindung mit der Security & Compliance Center PowerShell her](/powershell/exchange/connect-to-scc-powershell).

2. Führen Sie den folgenden PowerShell-Befehl aus, um eine Inhaltssuche zu erstellen, die nach Teams-Chatdaten für lokale Benutzer sucht.

    ```powershell
    New-ComplianceSearch <name of new search> -ContentMatchQuery <search query> -ExchangeLocation <on-premises user> -IncludeUserAppContent $true -AllowNotFoundExchangeLocationsEnabled $true  
    ```

    Der Parameter *IncludeUserAppContent* wird verwendet, um den cloudbasierten Speicher für den bzw. die durch den Parameter *ExchangeLocation* angegebenen Benutzer anzugeben. Mit *AllowNotFoundExchangeLocationsEnabled* können Sie den cloudbasierten Speicher nach lokalen Benutzern durchsuchen. Wenn Sie den Wert `$true` für diesen Parameter verwenden, versucht die Suche nicht, das Vorhandensein des Postfachs vor dem Fortfahren zu überprüfen. Dies ist erforderlich, um den cloudbasierten Speicher nach lokalen Benutzern zu durchsuchen, da dieser cloudbasierte Speicher nicht als reguläres cloudbasiertes Postfach aufgelöst wird.

    Im folgenden Beispiel wird im cloudbasierten Speicher von Sara Davis, die ein lokaler Benutzer der Organisation Contoso ist, nach Teams-Chats gesucht, die das Stichwort "Redstone" enthalten.
  
    ```powershell
    New-ComplianceSearch "Redstone_Search" -ContentMatchQuery "redstone AND (kind:im AND kind:microsoftteams)" -ExchangeLocation sarad@contoso.com -IncludeUserAppContent $true -AllowNotFoundExchangeLocationsEnabled $true  
    ```

   Verwenden Sie nach dem Erstellen einer Suche unbedingt das Cmdlet **Start-ComplianceSearch**, um die Suche auszuführen.
  
Weitere Informationen über diese Cmdlets finden Sie unter:
  
- [New-ComplianceSearch](/powershell/module/exchange/new-compliancesearch)

- [Set-ComplianceSearch](/powershell/module/exchange/set-compliancesearch)

- [Start-ComplianceSearch](/powershell/module/exchange/start-compliancesearch)

## <a name="known-issues"></a>Bekannte Probleme

- Derzeit können Sie Teams-Chatdaten für lokale Benutzer durchsuchen, in der Vorschau anzeigen und exportieren. Außerdem können Sie die Teams-Chatdaten für einen lokalen Benutzer in einem Archiv platzieren, das einem Core eDiscovery- oder Advanced eDiscovery-Fall zugeordnet ist, und eine Aufbewahrungsrichtlinie für Teams-Chats oder Kanalmeldungen für lokale Benutzer anwenden. Derzeit können Sie jedoch keine Aufbewahrungsrichtlinie für andere Inhaltsspeicherorte (z. B. Exchange-Postfächer und SharePoint-Websites) für lokale Benutzer anwenden.

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

**Muss ich eine Support-Anfrage stellen, um nach Chat-Nachrichten für lokale Benutzer zu suchen?**

Nein. Diese Funktion ist standardmäßig für alle Organisationen aktiviert. Früher mussten Sie sich an den Microsoft-Support wenden, aber das ist nicht mehr der Fall.
  
 **Können eDiscovery-Tools ältere Teams-Chatdaten für lokale Benutzer finden, bevor diese Funktion standardmäßig für alle Unternehmen aktiviert wurde?**
  
Microsoft hat am 31. Januar 2018 mit der Speicherung der Teams-Chatdaten für lokale Benutzer begonnen. Wenn also die Identität eines lokalen Teams-Benutzers seit diesem Datum zwischen Ihrem lokalen Active Directory und dem Azure Active Directory in Microsoft 365 synchronisiert wurde, dann werden deren Teams-Chatdaten in der Cloud gespeichert und sind mit eDiscovery-Tools durchsuchbar.

 **Benötigen lokale Benutzer eine Lizenz, um ihre Teams-Chatdaten in der Cloud zu speichern?**
  
Ja. Wenn die Teams-Chatdaten für einen lokalen Benutzer in einem cloudbasierten Speicher gespeichert werden sollen, muss dem Benutzer eine Lizenz für Microsoft Teams und eine für Exchange Online Plan in Office 365 (oder Microsoft 365) zugewiesen werden.

**Wo befindet sich der cloudbasierte Speicher für lokale Benutzer?**
  
Die Chat-Daten von Teams werden im bevorzugten Datenspeicher (PDL) für einen lokalen Benutzer gespeichert. Der PDL wird sowohl in Single-Geo- als auch in Multi-Geo-Umgebungen beachtet. Mehr dazu unter [Microsoft 365 Multi-Geo](../enterprise/microsoft-365-multi-geo.md).

**Besteht das Risiko, dass die Chatdaten der Teams verloren gehen, wenn das lokale Postfach des Benutzers in die Cloud migriert wird?**
  
Nein. Wenn Sie das primäre Postfach eines lokalen Benutzers in die Cloud migrieren, werden die Chatdaten des Teams für diesen Benutzer zum neuen cloudbasierten primären Postfach migriert.
  
 **Kann ich ein eDiscovery-Archiv oder Aufbewahrungsrichtlinien auf lokale Benutzer anwenden?**
  
Ja. Sie können eDiscovery-Archive oder Aufbewahrungsrichtlinien für Teams-Chats und Kanalnachrichten von lokalen Benutzern anwenden. Um jedoch den Inhalt von Teams für lokale Benutzer zu erhalten oder zu bewahren, muss einem lokalen Benutzer eine Exchange Online Plan 2-Lizenz zugewiesen werden.
