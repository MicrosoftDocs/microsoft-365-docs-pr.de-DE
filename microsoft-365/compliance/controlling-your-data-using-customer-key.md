---
title: Kontrolle über Daten in Office 365 mithilfe von Kundenschlüsseln
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 8/1/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f2cd475a-e592-46cf-80a3-1bfb0fa17697
ms.collection:
- M365-security-compliance
description: Hier erfahren Sie, wie Sie den Kundenschlüssel für Office 365 für Exchange Online, Skype for Business, SharePoint Online und OneDrive für Unternehmen einrichten. Mit dem Kundenschlüssel steuern Sie die Verschlüsselungsschlüssel Ihrer Organisation und konfigurieren dann Office 365, damit Sie Ihre Daten im Ruhezustand in den Microsoft-Rechenzentren verschlüsseln können.
ms.openlocfilehash: 839d0b56b3748e2ab4ccecc30a084447f22131aa
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37080992"
---
# <a name="controlling-your-data-in-office-365-using-customer-key"></a>Kontrolle über Daten in Office 365 mithilfe von Kundenschlüsseln

Mit Kundenschlüssel können Sie die Verschlüsselungsschlüssel Ihrer Organisation steuern und dann Office 365 konfigurieren, um Ihre Daten im Ruhezustand in Microsoft-Rechenzentren zu verschlüsseln. Mit anderen Worten: mit dem Kundenschlüssel können Kunden eine Verschlüsselungsebene hinzufügen, die Ihnen gehört, mit ihren Schlüsseln. Zu den Daten im Ruhezustand gehören Daten aus Exchange Online und Skype for Business, die in SharePoint Online und OneDrive for Business in Postfächern und Dateien gespeichert sind.
  
Sie müssen Azure einrichten, bevor Sie den Kundenschlüssel für Office 365 verwenden können. In diesem Thema werden die Schritte beschrieben, die Sie ausführen müssen, um die erforderlichen Azure-Ressourcen zu erstellen und zu konfigurieren, und dann die Schritte zum Einrichten des Kunden Schlüssels in Office 365 bereitgestellt. Nachdem Sie Azure Setup abgeschlossen haben, legen Sie fest, welche Richtlinie und daher welche Schlüssel zu Postfächern und Dateien in Ihrer Organisation zugewiesen werden sollen. Für Postfächer und Dateien, für die Sie keine Richtlinie zuweisen, werden Verschlüsselungsrichtlinien verwendet, die von Microsoft gesteuert und verwaltet werden. Weitere Informationen zum Kundenschlüssel oder eine allgemeine Übersicht finden Sie im [Kundenschlüssel für Office 365 FAQ](service-encryption-with-customer-key-faq.md).
  
> [!IMPORTANT]
> Es wird dringend empfohlen, dass Sie die bewährten Methoden in diesem Thema befolgten. Diese werden als **Trinkgeld** und **wichtig**bezeichnet. Mit dem Kundenschlüssel können Sie die Stamm Verschlüsselungsschlüssel steuern, deren Bereich so groß wie Ihre gesamte Organisation sein kann. Dies bedeutet, dass Fehler, die mit diesen Schlüsseln vorgenommen werden, weit reichende Auswirkungen haben und möglicherweise zu Dienstunterbrechungen oder unwiderruflichem Verlust Ihrer Daten führen. 
  
## <a name="before-you-begin-setting-up-customer-key"></a>Bevor Sie mit dem Einrichten des Kunden Schlüssels beginnen
<a name="Beforeyoustart"> </a>

Stellen Sie vor dem ersten Start sicher, dass Sie über die entsprechende Lizenzierung für Ihre Organisation verfügen. Kundenschlüssel in Office 365 wird in Office 365 E5 oder Advanced Compliance SKU angeboten.
  
Um die Konzepte und Verfahren in diesem Thema zu verstehen, sollten Sie die [Azure Key Vault](https://azure.microsoft.com/en-us/documentation/services/key-vault/) -Dokumentation lesen. Machen Sie sich darüber hinaus mit den in Azure verwendeten Ausdrücken vertraut, beispielsweise [Mandant](https://msdn.microsoft.com/library/azure/jj573650.aspx#BKMK_WhatIsAnAzureADTenant).
  
Um Feedback zum Kundenschlüssel bereitzustellen, einschließlich der Dokumentation, senden Sie Ihre Ideen, Vorschläge und Perspektiven an customerkeyfeedback@Microsoft.com.
  
## <a name="overview-of-setting-up-customer-key-for-office-365"></a>Übersicht über das Einrichten des Kunden Schlüssels für Office 365
<a name="Overview"> </a>

Um den Kundenschlüssel einzurichten, werden diese Aufgaben ausgeführt. Der Rest dieses Themas enthält detaillierte Anweisungen zu den einzelnen Aufgaben oder Links zu weiteren Informationen zu den einzelnen Schritten des Prozesses.
  
**In Azure und Microsoft:**
  
Die meisten dieser Aufgaben werden durch eine Remoteverbindung mit Azure PowerShell abgeschlossen. Um optimale Ergebnisse zu erzielen, verwenden Sie die Version 4.4.0 oder höher von Azure PowerShell.
  
- [Erstellen von zwei neuen Azure-Abonnements](controlling-your-data-using-customer-key.md#Create2newsubs)
    
- [Registrieren von Azure-Abonnements für die Verwendung eines obligatorischen Aufbewahrungszeitraums](controlling-your-data-using-customer-key.md#RegisterSubsforMRP)
    
    Die Registrierung kann von einem bis zu fünf Werktagen dauern.
    
- [Senden einer Anforderung zum Aktivieren des Kunden Schlüssels für Office 365](controlling-your-data-using-customer-key.md#FastTrack)
    
    Nachdem Sie die beiden neuen Azure-Abonnements erstellt haben, müssen Sie die entsprechende Kundenschlüssel Angebotsanforderung übermitteln, indem Sie ein Webformular ausfüllen, das im Microsoft-Portal für die Online-Bereitstellung gehostet wird. **Das Team des Teams bietet keine Unterstützung für den Kundenschlüssel. Office verwendet einfach das rasche Portal, damit Sie das Formular übermitteln und uns helfen können, die relevanten Angebote für den Kundenschlüssel nachzuverfolgen**.
  
Nachdem Sie ein Kundenschlüssel Angebot übermittelt haben, überprüft Microsoft Ihre Anfrage und benachrichtigt Sie, wenn Sie mit den restlichen Setupaufgaben fortfahren können. Dieser Vorgang kann bis zu fünf Geschäftstage dauern.
    
- [Erstellen eines Premium Azure-Schlüssel Tresors in jedem Abonnement](controlling-your-data-using-customer-key.md#CreateKeyVault)
    
- [Zuweisen von Berechtigungen zu jedem schlüsseltresor](controlling-your-data-using-customer-key.md#KeyVaultPerms)
    
- [Aktivieren und bestätigen Sie dann die Option "Soft Delete" in Ihren Schlüssel Tresoren](controlling-your-data-using-customer-key.md#SoftDelete)
    
- [Hinzufügen eines Schlüssels zu jedem schlüsseltresor, indem Sie entweder einen Schlüssel erstellen oder importieren](controlling-your-data-using-customer-key.md#AddKeystoKeyVault)
    
- [Überprüfen der Wiederherstellungsebene Ihrer Schlüssel](controlling-your-data-using-customer-key.md#CheckKeyRecoveryLevel)
    
- [Azure-schlüsseltresor sichern](controlling-your-data-using-customer-key.md#BackupAzureKeyVaultkeys)
    
- [Überprüfen der Konfigurationseinstellungen für Azure Key Vault](controlling-your-data-using-customer-key.md#Validateconfiguration)
    
- [Abrufen des URIs für jeden Schlüssel des Azure Key-Tresors](controlling-your-data-using-customer-key.md#GetKeyURI)
    
**In Office 365:**
  
Exchange Online und Skype for Business:
  
- [Erstellen einer Daten Verschlüsselungsrichtlinie (Data Encryption Policy, DEP) für die Verwendung mit Exchange Online und Skype for Business](controlling-your-data-using-customer-key.md#CreateDEP4EXOSkype)
    
- [Zuweisen einer Datenausführungsverhinderung zu einem Postfach](controlling-your-data-using-customer-key.md#assignDEPtomailbox)
    
- [Überprüfen der Postfachverschlüsselung](controlling-your-data-using-customer-key.md#validatemailboxencryption)
    
SharePoint Online und OneDrive für Unternehmen:
  
- [Erstellen einer Daten Verschlüsselungsrichtlinie für jede SharePoint Online und OneDrive für Unternehmen Geo](controlling-your-data-using-customer-key.md#CreateDEP4SPOODfB)
    
- [Überprüfen der Verschlüsselung von Gruppen Websites, Team Websites und OneDrive für Unternehmen](controlling-your-data-using-customer-key.md#validateencryptionSPO)
    
## <a name="complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key"></a>Ausführen von Aufgaben in Azure Key Vault und Microsoft kurzkunde für den Kundenschlüssel
<a name="AzureSteps"> </a>

Führen Sie diese Aufgaben in Azure Key Vault aus, um den Kundenschlüssel für Office 365 einzurichten. Sie müssen diese Schritte ausführen, unabhängig davon, ob Sie den Kundenschlüssel für Exchange Online und Skype for Business oder SharePoint Online und OneDrive für Unternehmen oder für alle unterstützten Dienste in Office 365 einrichten möchten.
  
### <a name="create-two-new-azure-subscriptions"></a>Erstellen von zwei neuen Azure-Abonnements
<a name="Create2newsubs"> </a>

Für den Kundenschlüssel sind zwei Azure-Abonnements erforderlich. Als bewährte Methode empfiehlt Microsoft, dass Sie neue Azure-Abonnements für die Verwendung mit dem Kundenschlüssel erstellen. Azure Key-Tresorschlüssel können nur für Anwendungen in demselben Azure-Active Directory (AAD)-Mandanten autorisiert werden, Sie müssen die neuen Abonnements mit demselben Azure AD Mandanten erstellen, der mit Ihrer Office 365 Organisation verwendet wird, in der die DEPs zugewiesen wird. Verwenden Sie beispielsweise Ihr Arbeits-oder Schulkonto, das über globale Administratorrechte in Ihrer Office 365 Organisation verfügt. Ausführliche Anweisungen finden Sie unter [registrieren für Azure als Organisation](https://azure.microsoft.com/en-us/documentation/articles/sign-up-organization/).
  
> [!IMPORTANT]
> Der Kundenschlüssel erfordert zwei Schlüssel für jede Daten Verschlüsselungsrichtlinie (Data Encryption Policy, DEP). Um dies zu erreichen, müssen Sie zwei Azure-Abonnements erstellen. Als bewährte Methode empfiehlt Microsoft, dass Sie getrennte Mitglieder Ihrer Organisation einen Schlüssel in jedem Abonnement konfigurieren müssen. Darüber hinaus sollten diese Azure-Abonnements nur zum Verwalten von Verschlüsselungsschlüsseln für Office 365 verwendet werden. Dadurch wird Ihre Organisation geschützt, falls einer ihrer Operatoren die für Sie Verantwortlichen Schlüssel versehentlich absichtlich oder böswillig löscht oder anderweitig missbräuchlich verwaltet. <br/> Es wird empfohlen, neue Azure-Abonnements einzurichten, die ausschließlich für die Verwaltung von Azure Key Vault-Ressourcen für die Verwendung mit dem Kundenschlüssel verwendet werden. Es gibt keine praktische Begrenzung für die Anzahl der Azure-Abonnements, die Sie für Ihre Organisation erstellen können. Wenn Sie diese bewährten Methoden verwenden, wird die Auswirkung des menschlichen Fehlers minimiert und gleichzeitig das Verwalten der vom Kundenschlüssel verwendeten Ressourcen unterstützt. 
  
### <a name="submit-a-request-to-activate-customer-key-for-office-365"></a>Senden einer Anforderung zum Aktivieren des Kunden Schlüssels für Office 365
<a name="FastTrack"> </a>

Nachdem Sie die Azure-Schritte abgeschlossen haben, müssen Sie eine Angebotsanfrage im [Microsoft-Portal](https://fasttrack.microsoft.com/)für die kurzfrage einreichen. Nachdem Sie eine Anforderung über das kurznetz-Webportal übermittelt haben, überprüft Microsoft die Azure Key Vault-Konfigurationsdaten und Kontaktinformationen, die Sie angegeben haben. Die Auswahl, die Sie im Angebotsformular für die autorisierten Officers Ihrer Organisation treffen, ist für die Fertigstellung der Kundenschlüssel Registrierung wichtig und erforderlich. Die Officers Ihrer Organisation, die Sie im Formular auswählen, werden verwendet, um sicherzustellen, dass alle Anforderungen, die mit einer Kundenschlüssel-Daten Verschlüsselungsrichtlinie verwendet werden, alle Schlüssel widerrufen und zerstören. Sie müssen diesen Schritt einmal ausführen, um den Kundenschlüssel für Exchange Online und Skype for Business Abdeckung zu aktivieren, und ein zweites Mal, um den Kundenschlüssel für SharePoint Online und OneDrive für Unternehmen zu aktivieren.
  
Führen Sie die folgenden Schritte aus, um ein Angebot zum Aktivieren des Kunden Schlüssels zu übermitteln:
  
1. Melden Sie sich bei einem Arbeits-oder Schulkonto mit globalen Administratorberechtigungen in Ihrer Office 365 Organisation beim [Microsoft-Portal](https://fasttrack.microsoft.com/)an.
    
2. Nachdem Sie sich angemeldet haben, navigieren Sie zum **Dashboard**.
    
3. Wählen Sie **Angebote**aus, und überprüfen Sie die Liste der aktuellen Angebote.
    
4. Wählen Sie weitere **Informationen** für das Angebot aus, das für Sie gilt: 
    
  - **Exchange Online und Skype for Business:** Wählen Sie weitere **Informationen** im **Kundenschlüssel für Exchange** -Angebot aus. 
    
  - **SharePoint Online und OneDrive für Unternehmen:** Wählen **Sie weitere Informationen** zum **Kundenschlüssel für SharePoint und OneDrive für Unternehmen Angebot aus** . 
    
5. Wählen Sie auf der Seite **Angebotsdetails** die Option **Anforderung erstellen**aus.
    
6. Füllen Sie alle anwendbaren Details und angeforderte Informationen im Angebotsformular aus. Achten Sie besonders auf Ihre Auswahl, für welche Officers Ihrer Organisation Sie autorisieren möchten, um die permanente und irreversible Vernichtung von Verschlüsselungsschlüsseln und Daten zu genehmigen. Nachdem Sie das Formular abgeschlossen haben, wählen Sie **Submit**aus.
    
    Dieser Vorgang kann bis zu fünf Werktage dauern, nachdem Microsoft Ihre Anfrage benachrichtigt hat.
    
7. Fahren Sie mit dem Abschnitt obligatorischer Aufbewahrungszeitraum weiter unten fort.
    
### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a>Registrieren von Azure-Abonnements für die Verwendung eines obligatorischen Aufbewahrungszeitraums
<a name="RegisterSubsforMRP"> </a>

Der vorübergehende oder dauerhafte Verlust von Stamm Verschlüsselungsschlüsseln kann sehr störend oder sogar katastrophal für den Dienstbetrieb sein und zu Datenverlusten führen. Aus diesem Grund benötigen die mit dem Kundenschlüssel verwendeten Ressourcen einen starken Schutz. Alle Azure-Ressourcen, die mit dem Kundenschlüssel verwendet werden, bieten Schutzmechanismen jenseits der Standardkonfiguration an. Azure-Abonnements können gekennzeichnet oder so registriert werden, dass eine sofortige und unwiderrufliche Stornierung verhindert wird. Dies wird als Registrierung für einen obligatorischen Aufbewahrungszeitraum bezeichnet. Die erforderlichen Schritte zum Registrieren von Azure-Abonnements für einen obligatorischen Aufbewahrungszeitraum erfordern die Zusammenarbeit mit dem Office 365 Team. Dieser Vorgang kann eine bis fünf Werktage dauern. Früher wurde dies auch als "nicht abbrechen" bezeichnet.
  
Bevor Sie mit dem Office 365-Team Kontakt aufnehmen, müssen Sie für jedes Azure-Abonnement, das Sie mit dem Kundenschlüssel verwenden, die folgenden Schritte ausführen:
  
1. Melden Sie sich bei Ihrem Azure-Abonnement mit Azure PowerShell an. Anweisungen finden Sie unter [Anmelden bei Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps?view=azurermps-4.3.1).
    
2. Führen Sie das Cmdlet Register-AzureRmProviderFeature aus, um Ihre Abonnements für die Verwendung eines obligatorischen Aufbewahrungszeitraums zu registrieren.
    
  ```
  Register-AzureRmProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.Resources
  ```

3. Wenden Sie sich an Microsoft, um den Prozess abzuschließen. Wenden Sie sich für das SharePoint-und OneDrive für Unternehmen-Team an [Spock@Microsoft.com](mailto:spock@microsoft.com). Wenden Sie sich für Exchange Online und Skype for Business an [exock@Microsoft.com](mailto:exock@microsoft.com). Die Vereinbarung zum Service Level (SLA) für den Abschluss dieses Prozesses beträgt fünf Werktage, nachdem Microsoft benachrichtigt (und überprüft) wurde, dass Sie Ihre Abonnements für die Verwendung eines obligatorischen Aufbewahrungszeitraums registriert haben. Fügen Sie in Ihre e-Mail Folgendes ein:
    
    **Betreff**: Kundenschlüssel für \< *den vollqualifizierten Domänennamen des Mandanten*\> 
    
    **Body**: Abonnement-IDs, für die die obligatorische Beibehaltungsdauer abgeschlossen werden soll. 
    
4. Nachdem Sie eine Benachrichtigung von Microsoft erhalten haben, dass die Registrierung abgeschlossen ist, überprüfen Sie den Status Ihrer Registrierung, indem Sie das Cmdlet Get-AzureRmProviderFeature wie folgt ausführen:
    
  ```
  Get-AzureRmProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
  ```

5. Nachdem Sie überprüft haben, dass die **Registrierungsstatus** Eigenschaft aus dem Cmdlet Get-AzureRmProviderFeature den Wert **registriert**zurückgibt, führen Sie den folgenden Befehl aus, um den Vorgang abzuschließen:
    
  ```
  Register-AzureRmResourceProvider -ProviderNamespace "Microsoft.KeyVault"
  ```

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a>Erstellen eines Premium Azure-Schlüssel Tresors in jedem Abonnement
<a name="CreateKeyVault"> </a>

Die Schritte zum Erstellen eines Schlüssel Tresors sind in [Erste Schritte mit Azure Key Vault](https://azure.microsoft.com/documentation/articles/key-vault-get-started/)dokumentiert, das Sie durch das Installieren und starten von Azure PowerShell, das Herstellen einer Verbindung mit Ihrem Azure-Abonnement, das Erstellen einer Ressourcengruppe und das Erstellen eines Schlüssel Tresors in diesem Dokument führt. Ressourcengruppe.
  
Wenn Sie einen schlüsseltresor erstellen, müssen Sie eine SKU auswählen: entweder Standard oder Premium. Mit der Standard-SKU können Azure Key Vault-Schlüssel mit Software geschützt werden – es gibt keinen Hardware Security Module (HSM)-Schlüsselschutz – und die Premium-SKU ermöglicht die Verwendung von HSMs zum Schutz wichtiger Tresorschlüssel. Kundenschlüssel akzeptiert Schlüssel Tresore, die entweder SKU verwenden, obwohl Microsoft dringend empfiehlt, nur die Premium-SKU zu verwenden. Die Kosten von Vorgängen mit Schlüsseln beider Typen sind identisch, daher ist der einzige Kostenunterschied die Kosten pro Monat für jeden HSM-geschützten Schlüssel. Details finden Sie unter [Key Vault Pricing](https://azure.microsoft.com/pricing/details/key-vault/) . 
  
> [!IMPORTANT]
> Verwenden Sie die Premium-SKU-Schlüssel Tresore und HSM-geschützte Schlüssel für Produktionsdaten, und verwenden Sie nur Standard mäßige SKU-Schlüssel Tresore und-Schlüssel zu Test-und Validierungszwecken. 
  
Erstellen Sie für jeden Office 365 Dienst, mit dem Sie den Kundenschlüssel verwenden, in jedem der beiden Azure-Abonnements, die Sie erstellt haben, einen schlüsseltresor. Wenn Sie beispielsweise nur Exchange Online und nur Skype for Business oder nur SharePoint Online und OneDrive für Unternehmen erstellen möchten, erstellen Sie nur ein paar Tresore. Um den Kundenschlüssel sowohl für Exchange Online als auch für SharePoint Online zu aktivieren, erstellen Sie zwei schlüsseltresor Paare.
  
Verwenden Sie eine Benennungskonvention für Schlüssel Tresore, die die vorgesehene Verwendung der Datenausführungsverhinderung widerspiegelt, mit dem Sie die Tresore assoziieren werden. Weitere Informationen finden Sie im Abschnitt bewährte Methoden für Benennungs Konventions Empfehlungen.
  
Erstellen Sie für jede Daten Verschlüsselungsrichtlinie eine separate, gekoppelte Gruppe von Tresoren. Für Exchange Online wird der Bereich einer Daten Verschlüsselungsrichtlinie von Ihnen ausgewählt, wenn Sie die Richtlinie dem Postfach zuweisen. Einem Postfach kann nur eine Richtlinie zugewiesen sein, und Sie können bis zu 50-Richtlinien erstellen. Für SharePoint Online der Bereich einer Richtlinie alle Daten innerhalb einer Organisation an einem geografischen Standort oder Geo.
  
Die Erstellung von Schlüssel Tresoren erfordert auch die Erstellung von Azure-Ressourcengruppen, da Schlüssel Tresore Speicherkapazität (wenn auch sehr klein) benötigen und die schlüsseltresor Protokollierung bei Aktivierung ebenfalls gespeicherte Daten generiert. Als bewährte Methode empfiehlt Microsoft die Verwendung von separaten Administratoren zum Verwalten der einzelnen Ressourcengruppen, wobei die Verwaltung mit der Gruppe von Administratoren abgeglichen wird, die alle zugehörigen Kundenschlüssel Ressourcen verwalten wird.
  
> [!IMPORTANT]
> Um die Verfügbarkeit zu maximieren, sollten sich Ihre Schlüssel Tresore in Regionen befinden, die sich in der Nähe Ihres Office 365 Dienstes befinden. Wenn sich Ihre Exchange Online Organisation beispielsweise in Nordamerika befindet, müssen Sie Ihre Schlüsseldepots in Nordamerika platzieren. Wenn sich Ihre Exchange Online Organisation in Europa befindet, platzieren Sie Ihre Schlüssel Tresore in Europa.<br/>Verwenden Sie ein gemeinsames Präfix für Schlüssel Tresore, und schließen Sie eine Abkürzung für die Verwendung und den Bereich des Schlüssel Tresors und der Schlüssel ein (beispielsweise für den Contoso SharePoint-Dienst, in dem sich die Tresore in Nordamerika befinden, eine mögliche Namenskombination ist contoso-O365SP-na-VaultA1 und Contoso-O365SP-na-VaultA2. Vault-Namen sind global eindeutige Zeichenfolgen in Azure, daher müssen Sie möglicherweise Variationen Ihrer gewünschten Namen ausprobieren, falls die gewünschten Namen bereits von anderen Azure-Kunden beansprucht werden. Ab Juli 2017 können Tresor Namen nicht geändert werden, daher empfiehlt es sich, einen schriftlichen Plan für das Setup zu haben und eine zweite Person zu verwenden, um zu überprüfen, ob der Plan ordnungsgemäß ausgeführt wird.<br/>Erstellen Sie nach Möglichkeit Ihre Tresore in nicht gepaarten Regionen. Gekoppelte Azure-Regionen bieten hohe Verfügbarkeit über Dienstfehler Domänen hinweg. Daher können regionale Paare als Sicherungs Region der jeweils anderen Person betrachtet werden. Dies bedeutet, dass eine Azure-Ressource, die in einer Region positioniert wird, automatisch eine Fehlertoleranz durch den gepaarten Bereich erhält. Aus diesem Grund bedeutet das Auswählen von Regionen für zwei Tresore, die in einer Datenausführungsverhinderung verwendet werden, in der die Regionen gekoppelt sind, dass nur insgesamt zwei Verfügbarkeits Regionen verwendet werden. Die meisten Geographen weisen nur zwei Regionen auf, daher ist es noch nicht möglich, nicht gepaarte Regionen auszuwählen. Wenn möglich, wählen Sie zwei nicht gepaarte Bereiche für die beiden Vaults, die mit einem DEP verwendet werden. Dies profitiert von insgesamt vier Verfügbarkeits Regionen. Weitere Informationen finden Sie unter [Business Continuity and Disaster Recovery (BCDR): Azure gepaart Regionen](https://docs.microsoft.com/azure/best-practices-availability-paired-regions) für eine aktuelle Liste der regionalen Paare. 
  
### <a name="assign-permissions-to-each-key-vault"></a>Zuweisen von Berechtigungen zu jedem schlüsseltresor
<a name="KeyVaultPerms"> </a>

Für jeden schlüsseltresor müssen Sie je nach Implementierung drei separate Berechtigungssätze für den Kundenschlüssel definieren. Sie müssen beispielsweise eine Gruppe von Berechtigungen für jede der folgenden definieren:
  
- **Wichtige Vault-Administratoren** , die die tägliche Verwaltung Ihres Schlüssel Tresors für Ihre Organisation durchführen werden. Zu diesen Aufgaben gehören das sichern, erstellen, abrufen, importieren, auflisten und wiederherstellen. 
    
    > [!IMPORTANT]
    > Die Berechtigungsgruppe, die Key Vault-Administratoren zugewiesen ist, enthält nicht die Berechtigung zum Löschen von Schlüsseln. Dies ist beabsichtigt und eine wichtige Praxis. Das Löschen von Verschlüsselungsschlüsseln erfolgt normalerweise nicht, da Daten dadurch dauerhaft gelöscht werden. Als bewährte Methode sollten Sie diese Berechtigung nicht standardmäßig schlüsseltresor-Administratoren erteilen. Reservieren Sie dies stattdessen für die Mitwirkenden von Key Vault, und weisen Sie es nur kurzfristig einem Administrator zu, sobald ein klares Verständnis der Konsequenzen verstanden wird. 
  
    Um diese Berechtigungen einem Benutzer in Ihrer Office 365 Organisation zuzuweisen, melden Sie sich bei Ihrem Azure-Abonnement mit Azure PowerShell an. Anweisungen finden Sie unter [Anmelden bei Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps?view=azurermps-4.3.1).
    
- Führen Sie das Cmdlet "Cmdlet festlegen-AzureRmKeyVaultAccessPolicy" aus, um die erforderlichen Berechtigungen zuzuweisen.
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> 
  -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
  ```

  Beispiel:
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
  -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
  ```

- **Key Vault mitwirk** Ende, die Berechtigungen für den Azure Key Vault selbst ändern können. Sie müssen diese Berechtigungen ändern, wenn Mitarbeiter ihr Team verlassen oder Ihrem Team beitreten, oder in der äußerst seltenen Situation, dass die Key Vault-Administratoren berechtigterweise die Berechtigung zum Löschen oder Wiederherstellen eines Schlüssels benötigen. Dieser Gruppe von wichtigen Vault-Mitwirkenden muss die Rolle " **Contributor** " in Ihrem schlüsseltresor gewährt werden. Sie können diese Rolle mithilfe von Azure Resource Manager zuweisen. Ausführliche Anweisungen finden Sie unter [Verwenden der rollenbasierten Zugriffssteuerung zum Verwalten des Zugriffs auf Ihre Azure-Abonnement Ressourcen](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure). Der Administrator, der ein Abonnement erstellt, hat diesen Zugriff implizit sowie die Möglichkeit, anderen Administratoren der Rolle "Contributor" zuzuweisen.
    
- Wenn Sie den Kundenschlüssel mit Exchange Online und Skype for Business verwenden möchten, müssen Sie Office 365 die Berechtigung erteilen, den schlüsseltresor im Namen von Exchange Online und Skype for Business zu verwenden. Wenn Sie den Kundenschlüssel mit SharePoint Online und OneDrive für Unternehmen verwenden möchten, müssen Sie ebenfalls die Berechtigung für den Office 365 hinzufügen, um den schlüsseltresor im Namen von SharePoint Online und OneDrive für Unternehmen zu verwenden. Führen Sie das Cmdlet " **AzureRmKeyVaultAccessPolicy** " mit der folgenden Syntax aus, um die Berechtigung für Office 365 zu erteilen: 
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
  ```

    Wobei Folgendes gilt:
    
  - *vaultname* ist der Name des Schlüssel Tresors, den Sie erstellt haben. 
    
  - Ersetzen Sie *Office 365* -ID für Exchange Online und Skype for Business durch`00000002-0000-0ff1-ce00-000000000000`
    
  - Ersetzen Sie *Office 365* -ID für SharePoint Online und OneDrive für Unternehmen durch`00000003-0000-0ff1-ce00-000000000000`
    
  Beispiel: Festlegen von Berechtigungen für Exchange Online und Skype for Business:
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
  -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
  ```

  Beispiel: Festlegen von Berechtigungen für SharePoint Online und OneDrive für Unternehmen
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1 
  -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
  ```

### <a name="enable-and-then-confirm-soft-delete-on-your-key-vaults"></a>Aktivieren und bestätigen Sie dann die Option "Soft Delete" in Ihren Schlüssel Tresoren
<a name="SoftDelete"> </a>

Wenn Sie Ihre Schlüssel schnell wiederherstellen können, wird aufgrund versehentlicher oder in böswilliger Absicht gelöschter Schlüssel ein längerer Dienstausfall möglicherweise nicht mehr auftreten. Sie müssen diese Konfiguration aktivieren, die als "Soft Delete" bezeichnet wird, bevor Sie Ihre Schlüssel mit dem Kundenschlüssel verwenden können. Durch die Aktivierung von Soft Delete können Sie Schlüssel oder Tresore innerhalb von 90 Tagen nach dem Löschen wiederherstellen, ohne Sie aus der Sicherung wiederherstellen zu müssen.
  
Führen Sie die folgenden Schritte aus, um das weiche löschen in Ihren Schlüssel Tresoren zu aktivieren:
  
1. Melden Sie sich mit Windows PowerShell bei Ihrem Azure-Abonnement an. Anweisungen finden Sie unter [Anmelden bei Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).
    
2. Führen Sie das Cmdlet [Get-AzureRmKeyVault](https://docs.microsoft.com/powershell/module/azurerm.keyvault/get-azurermkeyvault) aus. In diesem Beispiel ist *vaultname* der Name des Schlüssel Tresors, für den Sie Soft Delete aktivieren: 
    
   ```
   $v = Get-AzureRmKeyVault -VaultName <vaultname>
   $r = Get-AzureRmResource -ResourceId $v.ResourceId
   $r.Properties | Add-Member -MemberType NoteProperty -Name enableSoftDelete -Value 'True'
   Set-AzureRmResource -ResourceId $r.ResourceId -Properties $r.Properties
   ``` 
    
3. Bestätigen Sie, dass Soft Delete für den schlüsseltresor konfiguriert ist, indem Sie das Cmdlet **Get-AzureRmKeyVault** ausführen. Wenn Soft Delete ordnungsgemäß für den schlüsseltresor konfiguriert wurde, ist die Option "Soft Delete" aktiviert? Eigenschaft gibt den Wert **true**zurück: 
    
   ```
   Get-AzureRmKeyVault -VaultName <vaultname> | fl
   ```

   
    
### <a name="add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key"></a>Hinzufügen eines Schlüssels zu jedem schlüsseltresor, indem Sie entweder einen Schlüssel erstellen oder importieren
<a name="AddKeystoKeyVault"> </a>

Es gibt zwei Möglichkeiten zum Hinzufügen von Schlüsseln zu einem Azure-schlüsseltresor. Sie können einen Schlüssel direkt in Key Vault erstellen, oder Sie können einen Schlüssel importieren. Das Erstellen eines Schlüssels direkt in Key Vault ist die unkompliziertere Methode, während das Importieren eines Schlüssels eine vollständige Kontrolle darüber bietet, wie der Schlüssel generiert wird.
  
Um einen Schlüssel direkt in Ihrem schlüsseltresor zu erstellen, führen [Sie das Add-AzureKeyVaultKey-](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Add-AzureKeyVaultKey) Cmdlet wie folgt aus: 
  
```
Add-AzureKeyVaultKey -VaultName <vaultname> -Name <keyname> -Destination <HSM|Software> -KeyOps wrapKey,unwrapKey
```

Wobei Folgendes gilt:
  
-  *vaultname* ist der Name des Schlüssel Tresors, in dem Sie den Schlüssel erstellen möchten. 
    
-  *keyName* ist der Name, den Sie dem neuen Schlüssel zuweisen möchten. 
    
    > [!TIP]
    > Namensschlüssel mit einer ähnlichen Benennungskonvention wie oben für Schlüssel Tresore beschrieben. Auf diese Weise wird in Tools, die nur den Schlüsselnamen anzeigen, die Zeichenfolge selbsterklärend. 
  
- Wenn Sie den Schlüssel mit einem HSM schützen möchten, stellen Sie sicher, dass Sie **HSM** als Wert des Parameters _Destination_ angeben, andernfalls geben Sie **Software**an.
    
For example,
  
```
Add-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination Software -KeyOps wrapKey,unwrapKey
```

Wenn Sie einen Schlüssel direkt in ihren schlüsseltresor importieren möchten, benötigen Sie ein Thales nShield-Hardware Sicherheitsmodul.
  
Einige Organisationen bevorzugen diesen Ansatz, um die Herkunft Ihrer Schlüssel festzulegen, und die diese Methode bietet auch Folgendes:
  
- Das für den Import verwendete Toolset schließt die Beglaubigung von Thales ein, dass der Schlüsselaustauschschlüssel (KEK), der zum Verschlüsseln des von Ihnen generierten Schlüssels verwendet wird, nicht exportierbar ist und in einem echten HSM generiert wird, das von Thales hergestellt wurde.
    
- Das Toolset umfasst die Beglaubigung von Thales, dass die Azure Key Vault Security-Welt auch auf einem echten HSM von Thales generiert wurde. Diese Bestätigung beweist, dass Microsoft auch echte Thales-Hardware verwendet.
    
Wenden Sie sich an Ihre Sicherheitsgruppe, um festzustellen, ob die oben genannten Bescheinigungen erforderlich sind. Ausführliche Schritte zum Erstellen eines lokalen Schlüssels und zum Importieren in den Schlüsselspeicher finden Sie unter [generieren und übertragen von HSM-geschützten Schlüsseln für Azure Key Vault](https://azure.microsoft.com/documentation/articles/key-vault-hsm-protected-keys/). Verwenden Sie die Azure-Anweisungen, um einen Schlüssel in jedem schlüsseltresor zu erstellen.
  
### <a name="check-the-recovery-level-of-your-keys"></a>Überprüfen der Wiederherstellungsebene Ihrer Schlüssel
<a name="CheckKeyRecoveryLevel"> </a>

Office 365 erfordert, dass das Azure Key Vault-Abonnement auf nicht abbrechen festgelegt ist und dass für die Schlüssel, die von Kunden Schlüsseln verwendet werden, Soft Delete aktiviert ist. Sie können dies überprüfen, indem Sie die Wiederherstellungsebene auf ihren Schlüsseln betrachten.
  
Um die Wiederherstellungsebene eines Schlüssels zu überprüfen, führen Sie in Azure PowerShell das Cmdlet Get-AzureKeyVaultKey wie folgt aus:
  
```
(Get-AzureKeyVaultKey -VaultName <vaultname> -Name <keyname>).Attributes 
```

Wenn die _Wiederherstellungsebene_ etwas anderes als den Wert " **refundable + ProtectedSubscription**" zurückgibt, müssen Sie dieses Thema lesen und sicherstellen, dass Sie alle Schritte zum Setzen des Abonnements in der Liste "nicht abbrechen" und , dass für jeden schlüsseltresor ein Soft Delete aktiviert ist.
  
### <a name="backup-azure-key-vault"></a>Azure-schlüsseltresor sichern
<a name="BackupAzureKeyVaultkeys"> </a>

Führen Sie unmittelbar nach dem Erstellen oder Ändern eines Schlüssels eine Sicherung aus, und speichern Sie Kopien der Sicherung sowohl online als auch offline. Offline Kopien sollten nicht mit einem Netzwerk verbunden sein, beispielsweise in einer physischen sicheren oder kommerziellen Speichereinrichtung. Mindestens eine Kopie der Sicherung sollte an einem Speicherort gespeichert sein, auf den im Fall eines Notfalls zugegriffen werden kann. Die Sicherungs-BLOBs sind das einzige Mittel zum Wiederherstellen von Schlüsselmaterial, wenn ein schlüsseltresor Schlüssel dauerhaft zerstört oder anderweitig nicht funktionsfähig gemacht wird. Schlüssel, die sich außerhalb von Azure Key Vault befinden und in Azure Key Vault importiert wurden, qualifizieren sich nicht als Sicherung, da die Metadaten, die für die Verwendung des Schlüssels für den Kundenschlüssel erforderlich sind, nicht mit dem externen Schlüssel vorhanden sind. Für Wiederherstellungsvorgänge mit dem Kundenschlüssel kann nur eine Sicherung verwendet werden, die aus dem Azure Key Vault entnommen wurde. Daher ist es wichtig, dass eine Sicherung von Azure Key Vault durchgeführt wird, nachdem ein Schlüssel hochgeladen oder erstellt wurde.
  
Um eine Sicherung eines Azure Key-Tresor Schlüssels zu erstellen, führen Sie das Cmdlet [Backup-AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Backup-AzureKeyVaultKey) wie folgt aus:
```
Backup-AzureKeyVaultKey -VaultName <vaultname> -Name <keyname> 
-OutputFile <filename .backup>

```

Stellen Sie sicher, dass Ihre Ausgabedatei `.backup`das Suffix verwendet.
  
Die Ausgabedatei, die sich aus diesem Cmdlet ergibt, ist verschlüsselt und kann nicht außerhalb des Azure Key Vault verwendet werden. Die Sicherung kann nur für das Azure-Abonnement wiederhergestellt werden, von dem die Sicherung ausgeführt wurde.
  
> [!TIP]
> Wählen Sie für die Ausgabedatei eine Kombination aus Ihrem Tresor Namen und dem Schlüsselnamen aus. Dadurch wird der Dateiname selbsterklärend. Außerdem wird sichergestellt, dass die Namen der Sicherungsdateien nicht kollidieren. 
  
Beispiel:
  
```
Backup-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -OutputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

### <a name="validate-azure-key-vault-configuration-settings"></a>Überprüfen der Konfigurationseinstellungen für Azure Key Vault
<a name="Validateconfiguration"> </a>

Das Durchführen einer Überprüfung vor der Verwendung von Schlüsseln in einer DEP ist optional, wird jedoch dringend empfohlen. Wenn Sie beispielsweise die in diesem Thema beschriebenen Schritte zum Einrichten von Schlüsseln und Tresoren verwenden, sollten Sie vor dem Konfigurieren des Kunden Schlüssels die Integrität ihrer Azure Key-Vault-Ressourcen überprüfen.
  
So stellen Sie sicher, dass für die Schlüssel die Befehle Get, wrapKey und unwrapKey aktiviert sind:
  
Führen Sie das Cmdlet [Get-AzureRmKeyVault](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Get-AzureRmKeyVault) wie folgt aus: 
  
```
Get-AzureRMKeyVault -VaultName <vaultname>
```

Suchen Sie in der Ausgabe nach der Zugriffsrichtlinie und nach der Exchange Online Identität (GUID) oder der SharePoint Online Identität (GUID), je nach Bedarf. Alle drei der oben genannten Berechtigungen müssen unter Berechtigungen für Keys angezeigt werden.
  
Wenn die Konfiguration der Zugriffsrichtlinie falsch ist, führen Sie das Cmdlet "AzureRmKeyVaultAccessPolicy" wie folgt aus:
  
```
Set-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
```

Beispielsweise für Exchange Online und Skype for Business:
  
```
Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
```

Beispielsweise für SharePoint Online und OneDrive für Unternehmen:
  
```
Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1 
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName TBD
```

Um zu überprüfen, ob für Ihre Schlüssel ein Ablaufdatum festgelegt wurde, führen Sie das Cmdlet [Get-AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Get-AzureKeyVaultKey) wie folgt aus: 
  
```
Get-AzureKeyVaultKey -VaultName <vaultname> 
```

Ein abgelaufener Schlüssel kann nicht vom Kundenschlüssel verwendet werden, und Vorgänge, die mit einem abgelaufenen Schlüssel versucht werden, schlagen fehl und führen möglicherweise zu einem Dienstausfall. Es wird dringend empfohlen, dass Schlüssel, die mit dem Kundenschlüssel verwendet werden, kein Ablaufdatum aufweisen. Ein Ablaufdatum, das einmal festgelegt wurde, kann nicht entfernt werden, kann aber in ein anderes Datum geändert werden. Wenn ein Schlüssel verwendet werden muss, für den ein Ablaufdatum festgelegt wurde, ändern Sie den Ablaufwert in 12/31/9999. Schlüssel mit einem Ablaufdatum, das auf ein anderes Datum als 12/31/9999 festgelegt ist, werden Office 365 Überprüfung nicht übergeben.
  
Um ein Ablaufdatum zu ändern, das auf einen anderen Wert als 12/31/9999 festgelegt wurde, führen Sie das Cmdlet " [AzureKeyVaultKeyAttribute](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Set-AzureKeyVaultKeyAttribute) " wie folgt aus: 
  
```
Set-AzureKeyVaultKeyAttribute -VaultName <vaultname> -Name <keyname> 
-Expires (Get-Date -Date "12/31/9999")
```

> [!CAUTION]
> Legen Sie keine Ablaufdaten für Verschlüsselungsschlüssel fest, die Sie mit dem Kundenschlüssel verwenden. 
  
### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a>Abrufen des URIs für jeden Schlüssel des Azure Key-Tresors
<a name="GetKeyURI"> </a>

Nachdem Sie alle Schritte in Azure abgeschlossen haben, um die Schlüsseldepots einzurichten und die Schlüssel hinzugefügt haben, führen Sie den folgenden Befehl aus, um den URI für den Schlüssel in jedem schlüsseltresor abzurufen. Sie müssen diese URIs verwenden, wenn Sie die Datenausführungsverhinderung später erstellen und zuweisen, damit diese Informationen an einem sicheren Ort gespeichert werden. Denken Sie daran, diesen Befehl einmal für jeden schlüsseltresor auszuführen.
  
In Azure PowerShell:
  
```
(Get-AzureKeyVaultKey -VaultName <vaultname>).Id
```

## <a name="office-365-setting-up-customer-key-for-exchange-online-and-skype-for-business"></a>Office 365: Einrichten des Kunden Schlüssels für Exchange Online und Skype for Business
<a name="AzureSteps"> </a>

Bevor Sie beginnen, stellen Sie sicher, dass Sie die erforderlichen Aufgaben zum Einrichten von Azure Key Vault abgeschlossen haben. Weitere Informationen finden Sie unter [Complete Tasks in Azure Key Vault und Microsoft kurzkunde für den Kundenschlüssel](controlling-your-data-using-customer-key.md#AzureSteps) . 
  
Um den Kundenschlüssel für Exchange Online und Skype for Business einzurichten, müssen Sie diese Schritte durch eine Remoteverbindung mit Exchange Online mit Windows PowerShell ausführen.
  
### <a name="create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business"></a>Erstellen einer Daten Verschlüsselungsrichtlinie (Data Encryption Policy, DEP) für die Verwendung mit Exchange Online und Skype for Business
<a name="CreateDEP4EXOSkype"> </a>

Eine DEP ist einer Reihe von Schlüsseln zugeordnet, die in Azure Key Vault gespeichert sind. Sie weisen einer Datenausführungsverhinderung einem Postfach in Office 365 zu. Office 365 verwendet dann die Schlüssel, die in der Richtlinie zum Verschlüsseln des Postfachs angegeben sind. Zum Erstellen der DEP benötigen Sie die wichtigsten Vault-URIs, die Sie zuvor abgerufen haben. Anweisungen finden Sie unter [Abrufen des URI für jeden Azure Key Vault-Schlüssel](controlling-your-data-using-customer-key.md#GetKeyURI) . 
  
Denken Sie daran! Wenn Sie eine Datenausführungsverhinderung erstellen, geben Sie zwei Schlüssel an, die sich in zwei verschiedenen Azure-Schlüssel Tresoren befinden. Stellen Sie sicher, dass sich diese Schlüssel in zwei separaten Azure-Regionen befinden, um die Geo-Redundanz sicherzustellen.
  
Führen Sie die folgenden Schritte aus, um die DEP zu erstellen:
  
1. Stellen Sie auf Ihrem lokalen Computer mithilfe eines Arbeits-oder Schul Kontos, das über globale Administratorberechtigungen in Ihrer Office 365 Organisation verfügt, [eine Verbindung mit Exchange Online PowerShell her](https://technet.microsoft.com/en-us/library/jj984289%28v=exchg.160%29.aspx) , indem Sie Windows PowerShell öffnen und den folgenden Befehl ausführen. 
    
   ```
   $UserCredential = Get-Credential
   ```

2. Geben Sie im Dialogfeld Anmeldeinformationen für Windows PowerShell ihre Arbeit oder Ihr Schulkonto ein, klicken Sie auf **OK**, und geben Sie dann den folgenden Befehl ein. 
    
   ```
   $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
   ```

3. Führen Sie den folgenden Befehl aus.
    
   ```
   Import-PSSession $Session
   ```

4. Verwenden Sie zum Erstellen einer Datenausführungsverhinderung das Cmdlet New-DataEncryptionPolicy, indem Sie den folgenden Befehl eingeben.
    
   ```
   New-DataEncryptionPolicy -Name <PolicyName> -Description "PolicyDescription " -AzureKeyIDs <KeyVaultURI1>, <KeyVaultURI2>
   ```

   Wobei Folgendes gilt:
    
   -  *PolicyName* ist der Name, den Sie für die Richtlinie verwenden möchten. Namen dürfen keine Leerzeichen enthalten. Beispiel: USA_mailboxes. 
    
   -  *PolicyDescription* ist eine benutzerfreundliche Beschreibung der Richtlinie, mit der Sie sich daran erinnern können, wofür die Richtlinie verwendet wird. Sie können Leerzeichen in die Beschreibung einschließen. Beispiel: Stammschlüssel für Postfächer in USA und seinen Territorien. 
    
   -  *KeyVaultURI1* ist der URI für den ersten Schlüssel in der Richtlinie. Beispiel: https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01. 
    
   -  *KeyVaultURI2* ist der URI für den zweiten Schlüssel in der Richtlinie. Beispiel: https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02. Trennen Sie die beiden URIs durch ein Komma und ein Leerzeichen. 
    
   Beispiel:
  
   ```
   New-DataEncryptionPolicy -Name USA_mailboxes -Description "Root key for mailboxes in USA and its territories" -AzureKeyIDs https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01, https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02
   ```

### <a name="assign-a-dep-to-a-mailbox"></a>Zuweisen einer Datenausführungsverhinderung zu einem Postfach
<a name="assignDEPtomailbox"> </a>

Weisen Sie die Datenausführungsverhinderung einem Postfach mithilfe des Cmdlets "Cmdlet festlegen" zu. Nachdem Sie die Richtlinie zugewiesen haben, können Office 365 das Postfach mit dem in der DEP festgelegten Schlüssel verschlüsseln.
  
```
Set-Mailbox -Identity <MailboxIdParameter> -DataEncryptionPolicy <PolicyName>
```

Wobei *MailboxIdParameter* ein Postfach angibt. Weitere Informationen zum Cmdlet "Set-Mailbox" finden Sie unter [Sets-Mailbox](https://technet.microsoft.com/library/bb123981%28v=exchg.160%29.aspx).
  
### <a name="validate-mailbox-encryption"></a>Überprüfen der Postfachverschlüsselung
<a name="validatemailboxencryption"> </a>

Das Verschlüsseln eines Postfachs kann einige Zeit in Anspruch nehmen. Bei der erstmaligen Richtlinienzuweisung muss das Postfach auch den Wechsel von einer Datenbank zu einer anderen durchführen, bevor der Dienst das Postfach verschlüsseln kann. Es wird empfohlen, dass Sie 72 Stunden warten, bevor Sie versuchen, die Verschlüsselung zu überprüfen, nachdem Sie eine Datenausführungsverhinderung geändert haben oder wenn Sie eine DEP zum ersten Mal einem Postfach zuweisen.
  
Verwenden Sie das Cmdlet Get-MailboxStatistics, um zu ermitteln, ob ein Postfach verschlüsselt ist.
  
```
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

Die IsEncrypted-Eigenschaft gibt den Wert **true** zurück, wenn das Postfach verschlüsselt ist, und den Wert **false** , wenn das Postfach nicht verschlüsselt ist. 

Die Zeit bis zum Abschließen der Postfachverschiebungen hängt von der Anzahl der Postfächer ab, denen Sie erstmalig eine DEP zuweisen, sowie von der Größe der Postfächer. Wenn die Postfächer nach einer Woche ab dem Zeitpunkt, an dem Sie die Datenausführungsverhinderung zugewiesen haben, nicht verschlüsselt wurden, initiieren Sie mithilfe des Cmdlets New-MoveRequest eine Post Fach Verlagerung für die nicht verschlüsselten Postfächer.

```
New-MoveRequest <mailbox alias>
``` 

## <a name="office-365-setting-up-customer-key-for-sharepoint-online-and-onedrive-for-business"></a>Office 365: Einrichten des Kunden Schlüssels für SharePoint Online und OneDrive für Unternehmen
<a name="AzureSteps"> </a>

Bevor Sie beginnen, stellen Sie sicher, dass Sie die erforderlichen Aufgaben zum Einrichten von Azure Key Vault abgeschlossen haben. Weitere Informationen finden Sie unter [Complete Tasks in Azure Key Vault und Microsoft kurzkunde für den Kundenschlüssel](controlling-your-data-using-customer-key.md#AzureSteps) . 
  
Um den Kundenschlüssel für SharePoint Online und OneDrive für Unternehmen einzurichten, müssen Sie diese Schritte durch eine Remoteverbindung mit SharePoint Online mit Windows PowerShell ausführen.
  
### <a name="create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo"></a>Erstellen einer Daten Verschlüsselungsrichtlinie für jede SharePoint Online und OneDrive für Unternehmen Geo
<a name="CreateDEP4SPOODfB"> </a>

Eine DEP ist einer Reihe von Schlüsseln zugeordnet, die in Azure Key Vault gespeichert sind. Sie wenden einen DEP auf alle Ihre Daten an einem geografischen Standort an, der auch als Geo bezeichnet wird. Wenn Sie das Multi-Geo-Feature von Office 365 (derzeit in der Vorschau) verwenden, können Sie eine DEP pro Geo erstellen. Wenn Sie keine Multi-Geo-Daten verwenden, können Sie eine DEP in Office 365 für die Verwendung mit SharePoint Online und OneDrive für Unternehmen erstellen. Office 365 verwendet dann die in der DEP identifizierten Schlüssel, um Ihre Daten in diesem Geo zu verschlüsseln. Zum Erstellen der DEP benötigen Sie die wichtigsten Vault-URIs, die Sie zuvor abgerufen haben. Anweisungen finden Sie unter [Abrufen des URI für jeden Azure Key Vault-Schlüssel](controlling-your-data-using-customer-key.md#GetKeyURI) . 
  
Denken Sie daran! Wenn Sie eine Datenausführungsverhinderung erstellen, geben Sie zwei Schlüssel an, die sich in zwei verschiedenen Azure-Schlüssel Tresoren befinden. Stellen Sie sicher, dass sich diese Schlüssel in zwei separaten Azure-Regionen befinden, um die Geo-Redundanz sicherzustellen.
  
Um eine Datenausführungsverhinderung zu erstellen, müssen Sie mithilfe von Windows PowerShell eine Remoteverbindung mit SharePoint Online herstellen.
  
1. Stellen Sie auf Ihrem lokalen Computer mithilfe eines Arbeits-oder Schul Kontos, das über globale Administratorberechtigungen in Ihrer Office 365 Organisation verfügt, eine [Verbindung mit SharePoint Online PowerShell her](https://technet.microsoft.com/library/fp161372.aspx).
    
2. Führen Sie in der Microsoft SharePoint Online Verwaltungsshell das Cmdlet [Register-SPODataEncryptionPolicy](https://technet.microsoft.com/library/mt843950.aspx) wie folgt aus: 
    
   ```
   Register-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -PrimaryKeyVaultName <PrimaryKeyVaultName> -PrimaryKeyName <PrimaryKeyName> -PrimaryKeyVersion <PrimaryKeyVersion> -SecondaryKeyVaultName <SecondaryKeyVaultName> -SecondaryKeyName <SecondaryKeyName> -SecondaryKeyVersion <SecondaryKeyVersion>
   ```

   Wenn Sie die DEP registrieren, beginnt die Verschlüsselung mit den Daten im Geo. Dies kann einige Zeit in Anspruch nehmen.
    
### <a name="validate-encryption-of-group-sites-team-sites-and-onedrive-for-business"></a>Überprüfen der Verschlüsselung von Gruppen Websites, Team Websites und OneDrive für Unternehmen
<a name="validateencryptionSPO"> </a>

Sie können den Status der Verschlüsselung überprüfen, indem Sie das Cmdlet Get-SPODataEncryptionPolicy wie folgt ausführen:
  
```
Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

Die Ausgabe dieses Cmdlets umfasst Folgendes:
  
- Der URI des Primärschlüssels.
    
- Der URI des sekundären Schlüssels.
    
- Der Verschlüsselungsstatus für den Geo. Zu den möglichen Zuständen gehören:
    
  - Nicht **registriert:** Die Kundenschlüssel Verschlüsselung wurde noch nicht angewendet. 
    
  - **Registrieren:** Die Verschlüsselung mit dem Kundenschlüssel wurde angewendet, und Ihre Dateien werden gerade verschlüsselt. Wenn sich Ihr Geo in diesem Zustand befindet, werden Ihnen auch Informationen darüber angezeigt, wie viel Prozent der Websites in der Geo abgeschlossen sind, damit Sie den Verschlüsselungs Fortschritt überwachen können. 
    
  - **Registriert:** Die Verschlüsselung mit dem Kundenschlüssel wurde angewendet, und alle Dateien an allen Standorten wurden verschlüsselt. 
    
  - **Rollen:** Eine Schlüsselrolle wird gerade ausgeführt. Wenn sich Ihr Geo in diesem Zustand befindet, werden Ihnen auch Informationen darüber angezeigt, wie viel Prozent der Websites den Schlüsselrollen Vorgang abgeschlossen haben, damit Sie den Fortschritt überwachen können. 
    
## <a name="managing-customer-key-for-office-365"></a>Verwalten des Kunden Schlüssels für Office 365
<a name="ManageCustomerKey"> </a>

Nachdem Sie den Kundenschlüssel für Office 365 eingerichtet haben, können Sie diese zusätzlichen Verwaltungsaufgaben durchführen.
  
- [Wiederherstellen von Azure Key-Tresor Schlüsseln](controlling-your-data-using-customer-key.md#RestoreAzureKeyVaultKeys)
    
- [Rollen oder Drehen eines Schlüssels im Azure-schlüsseltresor, den Sie mit dem Kundenschlüssel verwenden](controlling-your-data-using-customer-key.md#RollCKkey)
    
- [Verwalten von schlüsseltresor-Berechtigungen](controlling-your-data-using-customer-key.md#Managekeyvaultperms)
    
- [Bestimmen der einem Postfach zugewiesenen Datenausführungsverhinderung](controlling-your-data-using-customer-key.md#DeterminemailboxDEP)
    
### <a name="restore-azure-key-vault-keys"></a>Wiederherstellen von Azure Key-Tresor Schlüsseln
<a name="RestoreAzureKeyVaultKeys"> </a>

Verwenden Sie vor dem Ausführen einer Wiederherstellung die von Soft Delete bereitgestellten Wiederherstellungsfunktionen. Für alle Schlüssel, die mit dem Kundenschlüssel verwendet werden, ist die Aktivierung von Soft Delete erforderlich. Soft Delete fungiert wie ein Papierkorb und ermöglicht die Wiederherstellung für bis zu 90 Tage, ohne dass eine Wiederherstellung erforderlich ist. Die Wiederherstellung sollte nur unter extremen oder ungewöhnlichen Umständen erforderlich sein, beispielsweise wenn der Schlüssel oder schlüsseltresor verloren geht. Wenn Sie einen Schlüssel für die Verwendung mit dem Kundenschlüssel wiederherstellen müssen, führen Sie in Azure PowerShell das Cmdlet Restore-AzureKeyVaultKey wie folgt aus:
  
```
Restore-AzureKeyVaultKey -VaultName <vaultname> -InputFile <filename>
```

Beispiel:
  
```
Restore-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -InputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

Wenn bereits ein Schlüssel mit dem gleichen Namen im schlüsseltresor vorhanden ist, tritt beim Wiederherstellungsvorgang ein Fehler auf. Restore-AzureKeyVaultKey stellt alle Schlüssel Versionen und alle Metadaten für den Schlüssel einschließlich des Schlüssel namens wieder her.
  
### <a name="rolling-or-rotating-a-key-in-azure-key-vault-that-you-use-with-customer-key"></a>Rollen oder Drehen eines Schlüssels im Azure-schlüsseltresor, den Sie mit dem Kundenschlüssel verwenden
<a name="RollCKkey"> </a>

Rollende Schlüssel sind weder für Azure Key Vault noch für den Kundenschlüssel erforderlich. Darüber hinaus sind Tasten, die mit einem HSM geschützt sind, praktisch unmöglich zu gefährden. Selbst wenn ein Hauptschlüssel im Besitz eines böswilligen Akteurs war, gibt es keine praktikablen Mittel zur Verwendung zum Entschlüsseln von Daten, da nur Office 365 Code diese verwenden kann. Das Rollen eines Schlüssels wird jedoch vom Kundenschlüssel unterstützt.
  
> [!CAUTION]
> Rollen Sie nur einen Verschlüsselungsschlüssel, den Sie mit dem Kundenschlüssel verwenden, wenn ein klarer technischer Grund vorliegt oder eine Compliance-Anforderung vorschreibt, dass Sie den Schlüsselrollen müssen. Löschen Sie außerdem keine Schlüssel, die Richtlinien zugeordnet sind oder wurden. Wenn Sie Ihre Schlüsselrollen, wird der Inhalt mit den vorherigen Schlüsseln verschlüsselt. Wenn beispielsweise aktive Postfächer häufig erneut verschlüsselt werden, werden inaktive, getrennte und deaktivierte Postfächer möglicherweise weiterhin mit den vorherigen Schlüsseln verschlüsselt. SharePoint Online führt eine Sicherung der Inhalte für Wiederherstellungs-und Wiederherstellungszwecke aus, sodass es möglicherweise weiterhin archivierte Inhalte mit älteren Schlüsseln gibt. <br/> Um die Sicherheit Ihrer Daten sicherzustellen, können SharePoint Online nicht mehr als einen Schlüsselrollen Vorgang gleichzeitig durchführen. Wenn Sie beide Schlüssel in einem schlüsseltresor Rollen möchten, müssen Sie warten, bis der erste Schlüsselrollen Vorgang vollständig abgeschlossen ist. Unsere Empfehlung besteht darin, ihre Schlüsselrollen Vorgänge in unterschiedlichen Intervallen zu staffeln, sodass dies kein Problem darstellt. 
  
Wenn Sie einen Schlüssel ausrollen, fordern Sie eine neue Version eines vorhandenen Schlüssels an. Um eine neue Version eines vorhandenen Schlüssels anzufordern, verwenden Sie dasselbe Cmdlet, [Add-AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Add-AzureKeyVaultKey), mit der gleichen Syntax, die Sie zum Erstellen des Schlüssels in erster Linie verwendet haben.
  
Beispiel:
  
```
Add-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination HSM -KeyOps @('wrapKey','unwrapKey') -NotBefore (Get-Date -Date "12/27/2016 12:01 AM")
```

In diesem Beispiel wird, da ein Schlüssel namens " **contoso-O365EX-na-VaultA1-Key001** " bereits im Tresor " **contoso-O365EX-na-VaultA1** " vorhanden ist, eine neue Schlüssel Version erstellt. Durch den Vorgang wird eine neue Schlüssel Version hinzugefügt. Bei diesem Vorgang werden die vorherigen Schlüssel Versionen im Versionsverlauf des Schlüssels beibehalten, sodass die zuvor mit diesem Schlüssel verschlüsselten Daten weiterhin entschlüsselt werden können. Nachdem Sie alle einem DEP zugeordneten Schlüssel ausgeführt haben, müssen Sie ein zusätzliches Cmdlet ausführen, um sicherzustellen, dass der Kundenschlüssel mit dem neuen Schlüssel beginnt. 
  
#### <a name="enable-exchange-online-and-skype-for-business-to-use-a-new-key-after-you-roll-or-rotate-keys-in-azure-key-vault"></a>Aktivieren Sie Exchange Online und Skype for Business, um einen neuen Schlüssel zu verwenden, nachdem Sie Keys im Azure Key Vault gerollt oder gedreht haben.

Wenn Sie eine der Azure Key Vault-Schlüsselrollen, die einer DEP zugeordnet sind, die mit Exchange Online und Skype for Business verwendet wird, müssen Sie den folgenden Befehl ausführen, um die DEP zu aktualisieren und Office 365 zu aktivieren, um mit dem neuen Schlüssel zu beginnen.
  
Führen Sie das Cmdlet "DataEncryptionPolicy" wie folgt aus, um den Kundenschlüssel für die Verwendung des neuen Schlüssels zum Verschlüsseln von Postfächern in Office 365 zu instruieren:
  
```
Set-DataEncryptionPolicy <policyname> -Refresh 
```

Innerhalb von 48 Stunden werden die mit dieser Richtlinie verschlüsselten aktiven Postfächer dem aktualisierten Schlüssel zugeordnet. Verwenden Sie die Schritte in [bestimmen der einem Postfach zugewiesenen DEP](controlling-your-data-using-customer-key.md#DeterminemailboxDEP) , um den Wert für die DataEncryptionPolicyID-Eigenschaft für das Postfach zu überprüfen. Der Wert für diese Eigenschaft ändert sich, sobald der aktualisierte Schlüssel angewendet wurde. 
  
#### <a name="enable-sharepoint-online-and-onedrive-for-business-to-use-a-new-key-after-you-roll-or-rotate-keys-in-azure-key-vault"></a>Aktivieren Sie SharePoint Online und OneDrive für Unternehmen, um einen neuen Schlüssel zu verwenden, nachdem Sie Keys im Azure Key Vault gerollt oder gedreht haben.

Wenn Sie eine der Azure Key Vault-Schlüsselrollen, die einer DEP zugeordnet sind, die mit SharePoint Online und OneDrive für Unternehmen verwendet wird, müssen Sie das Cmdlet [Update-SPODataEncryptionPolicy](https://technet.microsoft.com/library/mt843948.aspx) ausführen, um die Datenausführungsverhinderung zu aktualisieren und Office 365 zu verwenden, um mit dem neuen Schlüssel zu beginnen. 
  
```
Update-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -KeyVaultName <ReplacementKeyVaultName> -KeyName <ReplacementKeyName> -KeyVersion <ReplacementKeyVersion> -KeyType <Primary | Secondary>
```

Damit wird der Schlüsselrollen Vorgang für SharePoint Online und OneDrive für Unternehmen gestartet. Diese Aktion ist nicht direkt. Führen Sie das Cmdlet Get-SPODataEncryptionPolicy wie folgt aus, um den Fortschritt der Schlüsselrollen Operation anzuzeigen:
  
```
Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

### <a name="manage-key-vault-permissions"></a>Verwalten von schlüsseltresor-Berechtigungen
<a name="Managekeyvaultperms"> </a>

Es stehen mehrere Cmdlets zur Verfügung, mit denen Sie die schlüsseltresor-Berechtigungen anzeigen und gegebenenfalls entfernen können. Möglicherweise müssen Sie Berechtigungen entfernen, beispielsweise, wenn ein Mitarbeiter das Team verlässt.
  
Führen Sie das Cmdlet Get-AzureRmKeyVault aus, um die schlüsseltresor-Berechtigungen anzuzeigen:
  
```
Get-AzureRmKeyVault -VaultName <vaultname>
```

Beispiel:
  
```
Get-AzureRmKeyVault -VaultName Contoso-O365EX-NA-VaultA1
```

Um die Berechtigungen eines Administrators zu entfernen, führen Sie das Cmdlet Remove-AzureRmKeyVaultAccessPolicy aus:
  
```
Remove-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> 
-UserPrincipalName <UPN of user>
```

Beispiel:
  
```
Remove-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
-UserPrincipalName alice@contoso.com
```

### <a name="determine-the-dep-assigned-to-a-mailbox"></a>Bestimmen der einem Postfach zugewiesenen Datenausführungsverhinderung
<a name="DeterminemailboxDEP"> </a>

Verwenden Sie das Cmdlet Get-MailboxStatistics, um die einem Postfach zugewiesene Datenausführungsverhinderung zu ermitteln. Das Cmdlet gibt einen eindeutigen Bezeichner (GUID) zurück.
  
```
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl DataEncryptionPolicyID
```

Wobei *GeneralMailboxOrMailUserIdParameter* ein Postfach angibt. Weitere Informationen zum Get-MailboxStatistics-Cmdlet finden Sie unter [Get-MailboxStatistics](https://technet.microsoft.com/library/bb124612%28v=exchg.160%29.aspx).
  
Ermitteln Sie mithilfe der GUID den Anzeigenamen der DEP, der das Postfach zugewiesen ist, indem Sie das folgende Cmdlet ausführen.
  
```
Get-DataEncryptionPolicy <GUID>
```

Dabei ist *GUID* die vom Cmdlet Get-MailboxStatistics im vorherigen Schritt zurückgegebene GUID. 
  

