---
title: Kontrolle über Ihre Daten in Office 365 mithilfe von Customer Key
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
- SPO_Content
description: Hier erfahren Sie, wie Sie Customer Key für Office 365 für Exchange Online, Skype for Business, SharePoint Online und OneDrive für Unternehmen einrichten. Mit Customer Key können Sie die kryptografischen Schlüssel Ihrer Organisation steuern und dann Office 365 konfigurieren, um Ihre Daten im Ruhezustand in Microsoft-Rechenzentren mithilfe dieser Schlüssel zu verschlüsseln.
ms.openlocfilehash: 500adf03469833784228e13e26d8272716acc56c
ms.sourcegitcommit: 1c962bd0d51dc12419c4e6e393bb734c972b7e38
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "38686182"
---
# <a name="controlling-your-data-in-office-365-using-customer-key"></a>Kontrolle über Ihre Daten in Office 365 mithilfe von Customer Key

Mit Kundenschlüssel können Sie die Verschlüsselungsschlüssel Ihrer Organisation steuern und dann Office 365 konfigurieren, um Ihre Daten im Ruhezustand in Microsoft-Rechenzentren zu verschlüsseln. Mit anderen Worten: Customer Key ermöglicht es Kunden, mit ihren Schlüsseln eine Verschlüsselungsebene hinzuzufügen, die Ihnen gehört. Zu den Daten im Ruhezustand gehören Daten aus Exchange Online und Skype for Business, die in SharePoint Online und OneDrive for Business in Postfächern und Dateien gespeichert sind.

Sie müssen Azure einrichten, bevor Sie Customer Key für Office 365 verwenden können. In diesem themenbezogenen Artikel werden die Schritte beschrieben, die Sie ausführen müssen, um die erforderlichen Azure-Ressourcen zu erstellen und zu konfigurieren, und danach auch die Schritte zum Einrichten von Customer Key in Office 365. Nachdem Sie das Azure-Setup abgeschlossen haben, legen Sie fest, welche Richtlinie und somit auch, welche Schlüssel den Postfächern und Dateien in Ihrer Organisation zugewiesen werden sollen. Für Postfächer und Dateien, denen Sie keine Richtlinie zuweisen, werden Verschlüsselungsrichtlinien verwendet, die von Microsoft gesteuert und verwaltet werden. Weitere Informationen zu Customer Key oder einen allgemeinen Überblick darüber finden Sie unter [Customer Key für Office 365 Häufig gestellte Fragen](service-encryption-with-customer-key-faq.md).
  
> [!IMPORTANT]
> Es wird dringend empfohlen, die in diesem Artikel vorgestellten, bewährten Methoden zu befolgen. Diese werden sind als **TIPP** und **WICHTIG** bezeichnet. Customer Key ermöglicht Ihnen die Kontrolle über die grundlegenden kryptografischen Schlüssel, deren Geltungsbereich so groß wie Ihre gesamte Organisation sein kann. Dies bedeutet, dass Fehler im Zusammenhang mit diesen Schlüsseln einen großen Einfluss haben und zu Dienstunterbrechungen oder unwiderruflichen Datenverlusten führen können.
  
## <a name="before-you-begin-setting-up-customer-key"></a>Bevor Sie mit dem Einrichten von Customer Key beginnen
<a name="Beforeyoustart"> </a>

Bevor Sie beginnen, stellen Sie sicher, dass Sie über die geeignete Lizenzierung für Ihre Organisation verfügen. Customer Key in Office 365 wird in Office 365 E5 oder der Advanced Compliance-SKU bereitgestellt.
  
Wenn Sie die im Rahmen dieses Themas beschriebenen Konzepte und Verfahren verstehen möchten, sollten Sie in der Folge die Dokumentation zu [Azure Key Vault](https://azure.microsoft.com/documentation/services/key-vault/) lesen. Machen Sie sich außerdem mit den in Azure verwendeten Begriffen vertraut, beispielsweise [Mandant](https://msdn.microsoft.com/library/azure/jj573650.aspx#BKMK_WhatIsAnAzureADTenant).
  
Wenn Sie zu Customer Key, einschließlich der Dokumentation, Feedback geben möchten, senden Sie Ihre Ideen, Vorschläge und Einschätzungen an customerkeyfeedback@microsoft.com.
  
## <a name="overview-of-setting-up-customer-key-for-office-365"></a>Überblick zum Einrichten von Customer Key für Office 365
<a name="Overview"> </a>

Um Customer Key einzurichten, müssen Sie folgende Schritte durchführen. Im weiteren Verlauf dieses Artikels finden Sie ausführliche Anweisungen für jeden Schritt, oder Sie erhalten Links, die Sie zu weiteren Informationen zu den einzelnen Verfahrensschritten führen.
  
**In Azure und Microsoft FastTrack:**
  
Für die Durchführung der meisten dieser Schritte müssen Sie eine Remoteverbindung mit Azure PowerShell herstellen. Um optimale Ergebnisse zu erzielen, sollten Sie Version 4.4.0 oder höher von Azure PowerShell verwenden.
  
- [Zwei neue Azure-Abonnements erstellen](controlling-your-data-using-customer-key.md#Create2newsubs)

- [Azure-Abonnements registrieren, um einen obligatorischen Aufbewahrungszeitraum zu nutzen](controlling-your-data-using-customer-key.md#RegisterSubsforMRP)

    Die Registrierung kann ab einem bis zu fünf Arbeitstagen dauern.

- [Senden einer Anforderung zum Aktivieren von Customer Key für Office 365](controlling-your-data-using-customer-key.md#FastTrack)

    Nachdem Sie die beiden neuen Azure-Abonnements erstellt haben, müssen Sie die entsprechende Anforderung für das Customer Key-Angebot übermitteln, indem Sie ein Webformular ausfüllen, das im Microsoft FastTrack-Portal gehostet wird. **Das FastTrack-Team bitte keine Unterstützung für Customer Key. Office nutzt das FastTrack-Portal einfach für die Übermittlung des Formulars und um uns dabei zu helfen, die relevanten Angebote für Customer Key nachzuverfolgen**.
  
Sobald Sie ein Angebot für Customer Key übermittelt haben, überprüft Microsoft Ihre Anforderung und benachrichtigt Sie, sobald Sie mit den restlichen Setupschritten fortfahren können. Dieser Vorgang kann bis zu fünf Arbeitstage dauern.

- [Erstellen eines Premium Azure Key Vault für jedes Abonnement](controlling-your-data-using-customer-key.md#CreateKeyVault)

- [Zuweisen von Berechtigungen für jeden Schlüsseltresor (Key Vault)](controlling-your-data-using-customer-key.md#KeyVaultPerms)

- [Aktivieren und Bestätigen des vorläufigen Löschens in Ihren Schlüsseltresoren](controlling-your-data-using-customer-key.md#SoftDelete)

- [Hinzufügen eines Schlüssels zu jedem Schlüsseltresor durch das Erstellen oder Importieren eines Schlüssels](controlling-your-data-using-customer-key.md#AddKeystoKeyVault)

- [Überprüfen der Wiederherstellungsebene Ihrer Schlüssel](controlling-your-data-using-customer-key.md#CheckKeyRecoveryLevel)

- [Azure Key Vault-Backup](controlling-your-data-using-customer-key.md#BackupAzureKeyVaultkeys)

- [Konfigurationseinstellungen von Azure Key Vault verifizieren](controlling-your-data-using-customer-key.md#Validateconfiguration)

- [Anrufen des URI für jeden Azure Key Vault-Schlüssel](controlling-your-data-using-customer-key.md#GetKeyURI)

**In Office 365:**
  
Exchange Online und Skype for Business:
  
- [Erstellen einer Datenverschlüsselungsrichtlinie (DEP) für die Nutzung von Exchange Online und Skype for Business](controlling-your-data-using-customer-key.md#CreateDEP4EXOSkype)
    
- [Zuweisen einer Datenverschlüsselungsrichtlinie (DEP) zu einem Postfach](controlling-your-data-using-customer-key.md#assignDEPtomailbox)
    
- [Überprüfen einer Postfachverschlüsselung](controlling-your-data-using-customer-key.md#validatemailboxencryption)
    
SharePoint Online und OneDrive for Business:
  
- [Erstellen einer Datenverschlüsselungsrichtlinie (DEP) für jede SharePoint Online- und OneDrive for Business-Geo](controlling-your-data-using-customer-key.md#CreateDEP4SPOODfB)
    
- [Überprüfung der Verschlüsselung von Gruppen-Websites, Team-Websites und OneDrive for Business](controlling-your-data-using-customer-key.md#validateencryptionSPO)
    
## <a name="complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key"></a>Erledigen von Aufgaben in Azure Key Vault und Microsoft FastTrack für Customer Key
<a name="AzureSteps"> </a>

Führen Sie diese Aufgaben in Azure Key Vault aus, um Customer Key für Office 365 einzurichten. Sie müssen diese Schritte ausführen, ungeachtet dessen, ob Sie Customer Key für Exchange Online und Skype for Business oder SharePoint Online und OneDrive for Business oder für alle unterstützten Dienste in Office 365 einrichten möchten.
  
### <a name="create-two-new-azure-subscriptions"></a>Zwei neue Azure-Abonnements erstellen
<a name="Create2newsubs"> </a>

Für Customer Key sind zwei Azure-Abonnements erforderlich. Als bewährte Methode empfiehlt Microsoft, neue Azure-Abonnements für die Verwendung mit Customer Key zu erstellen. Azure Key Vault-Schlüssel können nur für Anwendungen im gleichen Azure Active Directory-Mandanten autorisiert werden. Sie müssen die neuen Abonnements mit demselben Azure Active Directory-Mandanten erstellen, der mit Ihrer Office 365-Organisation verwendet wird, in der die Datenverschlüsselungsrichtlinien zugewiesen werden. Verwenden Sie z. B. Ihr Geschäfts-oder Schulkonto, das über globale Administratorberechtigungen in Ihrer Office 365-Organisation verfügt. Weitere Informationen zu den einzelnen Arbeitsschritten finden Sie unter [Als Unternehmen für Azure registrieren](https://azure.microsoft.com/documentation/articles/sign-up-organization/).
  
> [!IMPORTANT]
> Für Customer Key sind zwei Schlüssel für jede Daten- Verschlüsselungsrichtlinie (DEP) erforderlich. Zu diesem Zweck müssen Sie zwei Azure-Abonnements erstellen. Als bewährte Methode empfiehlt Microsoft, dass separate Mitglieder Ihrer Organisation jeweils einen Schlüssel für jedes Abonnement konfigurieren. Darüber hinaus sollten diese Azure-Abonnements nur zum Verwalten von kryptografischen Schlüsseln für Office 365 verwendet werden. Auf diese Weise ist Ihre Organisation geschützt, falls einer ihrer Betreiber versehentlich, absichtlich oder in böswilliger Absicht die Schlüssel, für die Sie verantwortlich sind, löscht oder auf andere Weise unsachgemäß handhabt. <br/> Es wird empfohlen, dass Sie neue Azure-Abonnements einrichten, die ausschließlich zum Verwalten von Azure Key Vault-Ressourcen für die Verwendung mit Customer Key genutzt werden. Es gibt praktisch keine Beschränkung hinsichtlich der Anzahl von Azure-Abonnements, die Sie für Ihre Organisation erstellen können. Durch die Nutzung dieser bewährten Methoden können Sie die Auswirkungen von menschlichen Fehlern bei der Verwaltung der von Customer Key genutzten Ressourcen minimieren. 
  
### <a name="submit-a-request-to-activate-customer-key-for-office-365"></a>Senden einer Anforderung zum Aktivieren von Customer Key für Office 365
<a name="FastTrack"> </a>

Sobald Sie die Azure-Schritte abgeschlossen haben, müssen Sie im [Microsoft FastTrack-Portal](https://fasttrack.microsoft.com/) eine Angebotsanfrage übermitteln. Sobald Sie eine Anforderung über das FastTrack-Web-Portal übermittelt haben, überprüft Microsoft die von Ihnen bereitgestellten Konfigurationsdaten für den Azure Key Vault und die Kontaktinformationen. Die von Ihnen im Angebotsformular hinsichtlich der autorisierten Mitarbeiter Ihrer Organisation getroffene Auswahl ist wesentlich und für das Abschließen der Registrierung von Customer Key erforderlich. Die Führungskräfte Ihrer Organisation, die Sie im Formular auswählen, werden genutzt, um die Authentizität jeder Anforderung zum Widerrufen und Löschen aller Schlüssel verwendet wird, die mit einer Customer Key Datenverschlüsselungsrichtlinie verwendet werden, sicherzustellen. Sie müssen diesen Schritt einmal ausführen, um Customer Key für Exchange Online und Skype for Business zu aktivieren, und ein zweites Mal, um Customer Key für SharePoint Online und OneDrive for Business zu aktivieren.
  
Führen Sie zur Übermittlung eines Angebots zum Aktivieren von Customer Key die folgenden Schritte aus:
  
1. Wenn Sie ein Geschäfts- oder Schul- bzw. Unikonto verwenden, das über globale Administratorrechte in ihrer Office 365-Organisation verfügt, melden Sie sich am [Microsoft FastTrack-Portal](https://fasttrack.microsoft.com/).
    
2. Sobald Sie angemeldet sind, wechseln Sie zum **Dashboard**.
    
3. Wählen Sie **Angebote** und überprüfen Sie das Verzeichnis der aktuellen Angebote.
    
4. Wählen Sie **Weitere Informationen** zu dem für Sie geltenden Angebot: 
    
  - **Exchange Online und Skype for Business:** Wählen Sie ** Weitere Informationen ** zum Angebot **Customer Key für Exchange**. 
    
  - **SharePoint Online und OneDrive for Business:** Wählen Sie **Weitere Informationen** zum Angebot **Customer Key für SharePoint und OneDrive for Business**. 
    
5. Wählen Sie auf der Seite **Angebotsdetails** **Anforderung erstellen**.
    
6. Tragen Sie alle relevanten Details und erforderlichen Informationen im Angebotsformular ein. Achten Sie besonders auf Ihre Auswahl, welche MitarbeiterInnen Ihrer Organisation Sie autorisieren, die permanente und unwiderrufliche Vernichtung von kryptografischen Schlüsseln und Daten zu genehmigen. Sobald Sie das Formular ausgefüllt haben, wählen Sie **Senden**.
    
    Die Verarbeitung kann bis zu fünf Werktage ab dem Zeitpunkt, zu dem Microsoft Ihre Anforderung mitgeteilt wurde, dauern.
    
7. Fahren Sie bitte mit dem weiter unten aufscheinenden Abschnitt ‚Obligatorischer Aufbewahrungszeitraum‘ fort.
    
### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a>Azure- Abonnements registrieren, um einen obligatorischen Aufbewahrungszeitraum zu nutzen.
<a name="RegisterSubsforMRP"> </a>

Der vorübergehende oder dauerhafte Verlust von kryptografischen Schlüsseln kann für den Betrieb eines Dienstes sehr störend oder sogar katastrophal sein und zu Datenverlust führen. Aus diesem Grund ist für die mit Customer Key verwendeten Ressourcen ein starker Schutz erforderlich. Alle Azure-Ressourcen, die mit Customer Key verwendet werden, bieten Schutzmechanismen, die weit über die Standardkonfiguration hinaus gehen. Azure-Abonnements können derart gekennzeichnet oder registriert werden, dass eine sofortige und unwiderrufliche Kündigung vermieden wird. Dies wird als Registrierung eines obligatorischen Aufbewahrungszeitraums bezeichnet. Die für das Registrieren von Azure-Abonnements für einen obligatorischen Aufbewahrungszeitraum notwendigen Schritte erfordern die Zusammenarbeit mit dem Office 365-Team. Die Registrierung kann ab einen bis fünf Arbeitstage dauern. Bisher wurde diese Funktion zeitweise als „Nicht kündigen" bezeichnet.
  
Bevor Sie sich mit dem Office 365-Team in Verbindung setzen, müssen Sie die folgenden Schritte für jedes Azure-Abonnement ausführen, das Sie mit Customer Key verwenden:
  
1. Melden Sie sich mit Azure PowerShell bei Ihrem Azure-Abonnement an. Anweisungen hierzu finden Sie unter [Anmelden mit Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps?view=azurermps-4.3.1).
    
2. Führen Sie das Cmdlet „Register-AzureRmProviderFeature“ aus, um Ihre Abonnements für die Nutzung eines obligatorischen Aufbewahrungszeitraums zu registrieren.
    
  ```powershell
  Register-AzureRmProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.Resources
  ```

3. Wenden Sie sich an Microsoft, damit der Prozess abgeschlossen wird. Um mit dem SharePoint- und OneDrive for Business-Team in Verbindung zu treten, wenden Sie sich bitte an [spock@microsoft.com](mailto:spock@microsoft.com). Für Exchange Online und Skype for Business wenden Sie sich bitte an [exock@microsoft.com](mailto:exock@microsoft.com). Die Service-Level-Vereinbarung (Service Level Agreement, SLA) für den Abschluss dieses Vorgangs beläuft sich auf fünf Werktage, nachdem Microsoft benachrichtigt wurde (und überprüft hat, dass Sie Ihre Abonnements für die Nutzung eines obligatorischen Aufbewahrungszeitraums registriert haben). Teilen Sie uns in Ihrem E-Mail bitte Folgendes mit:
    
    **Betreff**: Customer Key für \<*Vollständig qualifizierter Domänenname Ihres Mandanten*\> 
    
    **Textkörper**: Abonnements-IDs, für die Sie einen obligatorischen Aufbewahrungszeitraum verbindlich festlegen möchten. 
    
4. Sobald Sie von Microsoft eine Benachrichtigung erhalten, dass die Registrierung abgeschlossen ist, überprüfen Sie bitte den Status Ihrer Registrierung, indem Sie das Cmdlet „Get-AzureRmProviderFeature“ wie folgt ausführen:
    
  ```powershell
  Get-AzureRmProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
  ```

5. Nachdem Sie überprüft haben, dass die Eigenschaft **Registrierungsstatus** vom Cmdlet „Get-AzureRmProviderFeature“ den Wert **Registriert** rückmeldet, führen Sie den folgenden Befehl aus, um den Vorgang abzuschließen:
    
  ```powershell
  Register-AzureRmResourceProvider -ProviderNamespace "Microsoft.KeyVault"
  ```

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a>Erstellen eines Premium Azure Key Vault für jedes Abonnement
<a name="CreateKeyVault"> </a>

Die Schritte zum Erstellen eines Schlüssel Tresors sind in ["erste Schritte mit Azure Key Vault"](https://azure.microsoft.com/documentation/articles/key-vault-get-started/)dokumentiert, das Sie durch das Installieren und Ingangsetzen von Azure PowerShell, das Herstellen einer Verbindung mit Ihrem Azure-Abonnement, das Erstellen einer Ressourcengruppe und das Erstellen eines Schlüsseltresors in dieser Ressourcengruppe führt.
  
Wenn Sie einen Schlüsseltresor erstellen, müssen Sie eine SKU auswählen: entweder Standard oder Premium. Die Standard-SKU ermöglicht das Schützen von Azure Key Vault-Schlüsseln mittels Software – es gibt keinen Schlüsselschutz mittels eines Hardware-Sicherheitsmoduls (HSM) – und die Premium-SKU ermöglicht die Verwendung von Hardware-Sicherheitsmodulen zum Schutz von Key-Vault-Schlüsseln. Customer Key akzeptiert Schlüsseltresore mit jeder SKU, wobei Microsoft dringend empfiehlt, nur die Premium-SKU zu verwenden. Die Betriebskosten mit Schlüsseln eines der beiden Typen sind identisch. Der einzige Unterschied bei den Kosten sind die monatlichen Kosten für jeden HSM-geschützten Schlüsseln. Detailinformationen finden Si unter [Key Vault-Preise](https://azure.microsoft.com/pricing/details/key-vault/). 
  
> [!IMPORTANT]
> Verwenden Sie die Premium-SKU-Schlüsseltresore und HSM-geschützten Schlüssel für Produktionsdaten, und verwenden Sie nur standardmäßige SKU-Schlüsseltresore und Schlüssel für Tests und Überprüfungen. 
  
Erstellen Sie für jeden Office 365-Dienst, für den Sie Customer Key verwenden, einen Schlüsseltresor in jedem der beiden von Ihnen erstellten Azure-Abonnements. Beispielsweise erstellen Sie nur für Exchange Online und Skype for Business oder SharePoint Online und OneDrive for Business lediglich zwei Tresore. Um Customer Key für Exchange Online und SharePoint Online zu aktivieren, erstellen Sie zwei Paar Schlüsseltresore.
  
Verwenden Sie eine Benennungskonvention für Schlüsseltresore, durch welche sich die beabsichtigte Verwendung der Datenverschlüsselungsrichtlinie widerspiegelt, der Sie die Tresore zuordnen möchten. Im nachstehenden Abschnitt „Bewährte Methoden“ finden Sie Empfehlungen zur Benennung.
  
Erstellen Sie für jede Datenverschlüsselungsrichtlinie eine eigene, paarweise angeordnete Tresor-Gruppe. Bei Exchange Online wählen Sie den Geltungsbereich einer Datenverschlüsselungsrichtlinie, wenn Sie die Richtlinie dem Postfach zuweisen. Einem Postfach kann nur eine Richtlinie zugewiesen sein, allerding können Sie bis zu 50 Richtlinien erstellen. Bei SharePoint Online umfasst der Geltungsbereich einer Richtlinie alle Daten innerhalb einer Organisation an einem geografischen Standort oder Geo.
  
Das Erstellen von Schlüsseltresoren setzt außerdem die Erstellung von Azure-Ressourcengruppen voraus, da für Schlüsseltresore Speicherkapazität (wenn auch sehr geringe) erforderlich ist und die Schlüsseltresor-Protokollierung (sofern aktiviert) außerdem gespeicherte Daten generiert. Als bewährte Methode empfiehlt Microsoft die Verwendung eigener Administratoren zum Verwalten jeder Ressourcengruppe, wobei die Verwaltung mit der Gruppe der Administratoren abgestimmt wird, die alle zugehörigen Customer Key-Ressourcen verwalten.
  
> [!IMPORTANT]
> Um die Verfügbarkeit zu maximieren, sollten sich Ihre Schlüsseltresore in Regionen in der Nähe Ihres Office 365-Dienstes befinden. Wenn sich beispielsweise Ihre Exchange Online-Organisation in Nordamerika befindet, sollten Sie Ihre Schlüsseldepots in Nordamerika platzieren. Wenn Ihre Exchange Online-Organisation in Europa ist, sollten Sie Ihre Schlüsseldepots in Europa platzieren.<br/>Verwenden Sie für die Benennung ein gemeinsames Präfix für Schlüsseltresore sowie eine Abkürzung für die Verwendung und den Umfang des Schlüsseltresors und der Schlüssel (so ist z. B. für den Contoso SharePoint-Dienst, in den sich die Tresore in Nordamerika befinden, ein mögliches Namenspaar „Contoso-O365SP-NV-VaultA1“ und „Contoso-O365SP-NV-VaultA2“. In Azure sind Tresornamen global eindeutige Zeichenfolgen, daher müssen Sie möglicherweise Variationen Ihrer gewünschten Namen ausprobieren, falls die gewünschten Namen bereits von anderen Azure-Kunden beansprucht werden. Ab Juli 2017 können Tresornamen nicht mehr geändert werden, daher empfiehlt es sich, einen schriftlichen Setup-Plan zu erstellen und eine zweite Person zu beauftragen, die überprüft, ob der Plan ordnungsgemäß ausgeführt wird.<br/>Erstellen Sie Ihre Depots nach Möglichkeit in nicht-gekoppelten Regionen. Gekoppelte Azure-Regionen bieten eine hohe Verfügbarkeit über Dienstausfall-Domänen hinweg. Dementsprechend können regionale Paare gegenseitig als Backup-Region der jeweils anderen betrachtet werden. Dies bedeutet, dass eine Azure-Ressource, die in einer bestimmten Region platziert ist, durch die gekoppelte Region automatisch an Fehlertoleranz gewinnt. Aus diesem Grund bedeutet die Auswahl von gekoppelten Regionen für zwei Tresore, die in einer Datenverschlüsselungsrichtlinie verwendet werden, dass insgesamt lediglich zwei verfügbare Regionen genutzt verwendet werden. In den meisten geografischen Regionen gibt es nur zwei Regionen, weshalb es noch nicht möglich ist, nicht-gekoppelte Regionen auszuwählen. Sofern möglich, wählen Sie zwei nicht-gekoppelte Regionen für die beiden Tresore aus, die mit einer Datenverschlüsselungsrichtlinie verwendet werden. Dies hat den positiven Effekt, dass insgesamt vier verfügbare Regionen genutzt werden. Weitere Informationen hierzu sowie ein aktuelles Verzeichnis der Regionenpaare finden Sie unter [Geschäftskontinuität und Notfallwiederherstellung (Business continuity and disaster recovery, BCDR): Gekoppelte Regionen in Azure](https://docs.microsoft.com/azure/best-practices-availability-paired-regions). 
  
### <a name="assign-permissions-to-each-key-vault"></a>Zuweisen von Berechtigungen für jeden Schlüsseltresor (Key Vault)
<a name="KeyVaultPerms"> </a>

Sie müssen für jeden Schlüsseltresor entsprechend der von Ihnen gewählten Implementierung drei gesonderte Berechtigungsgruppen für Customer Key definieren. Sie müssen beispielsweise eine Berechtigungsgruppe für jede der folgenden Optionen definieren:
  
- **Schlüsseltresor-Administratoren**, deren Aufgabe das tägliche Verwalten Ihrer Schlüsseltresore für Ihre Organisation ist. Zu diesen Aufgaben gehören Datensicherung sowie Erstellen, Abrufen, Importieren, Auflisten und Wiederherstellen. 
    
    > [!IMPORTANT]
    > Die Berechtigungsgruppe, die Schlüsseltresor-Administratoren zugewiesen ist, beinhaltet keine Berechtigung zum Löschen von Schlüsseln. Dies ist beabsichtigt und eine wichtige Vorgehensweise. Kryptografische Schlüssel werden normalerweise nicht gelöscht, da dadurch Daten dauerhaft vernichtet werden. Eine bewährte Methode besteht darin, den Schlüsseltresor-Administratoren diese Berechtigung nicht standardmäßig zuzuweisen. Behalten Sie stattdessen diese Berechtigung den Schlüsseltresor-Mitwirkenden vor und weisen Sie diese einem Administrator nur kurzfristig und lediglich, sofern die damit verbundenen Folgen klar verstanden wurden, zu. 
  
    Um diese Berechtigungen einem Benutzer in Ihrer Office 365-Organisation zuzuweisen, melden Sie sich bei Ihrem Azure-Abonnement mit Azure PowerShell an. Anweisungen hierzu finden Sie unter [Anmelden mit Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps?view=azurermps-4.3.1).
    
- Führen Sie das Cmdlet „Set-AzureRmKeyVaultAccessPolicy“ aus, um die erforderlichen Berechtigungen zuzuweisen.
    
  ```powershell
  Set-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> 
  -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
  ```

  Beispiel:
    
  ```powershell
  Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
  -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
  ```

- **Schlüsseltresor-Mitwirkenden**, die Berechtigungen für den Azure Key Vault selbst ändern können. Sie müssen diese Berechtigungen ändern, wenn Mitarbeiter Ihr Team verlassen oder Ihrem Team beitreten oder, im äußerst selten eintretenden Fall, dass Schlüsseltresor-Administratoren berechtigterweise die Berechtigung zum Löschen oder Wiederherstellen eines Schlüssels benötigen. Dieser Gruppe von Schlüsseltresor-Mitwirkenden muss die Rolle **Mitwirkender** für Ihren Schlüsseltresor zugewiesen werden. Sie können diese Rolle mithilfe des Azure-Ressourcenmanagers zuweisen. Informationen zu den einzelnen Schritten finden Sie unter [Verwenden der rollenbasierten Zugriffssteuerung zum Verwalten des Zugriffs auf Ihre Azure-Abonnementressourcen](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure). Der Administrator, der ein Abonnement erstellt, verfügt implizit über diesen Zugriff sowie die Möglichkeit, der Rolle des Mitwirkenden weitere Administratoren zuzuweisen.
    
- Wenn Sie beabsichtigen, Customer Key für Exchange Online und Skype for Business zu nutzen, müssen Sie Office 365 die Berechtigung erteilen, den Schlüsseltresor für Exchange Online und Skype for Business zu verwenden. Ebenso müssen Sie, wenn Sie beabsichtigen, Customer Key für SharePoint Online und OneDrive for Business zu nutzen, die Berechtigung für Office 365 hinzufügen, damit dieses den Schlüsseltresor für SharePoint Online und OneDrive for Business verwenden darf. Um Office 365 die Berechtigung zu erteilen, führen Sie das Cmdlet **Set-AzureRmKeyVaultAccessPolicy** mit der folgenden Syntax aus: 
    
  ```powershell
  Set-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
  ```

    Dabei gilt:
    
  - Der *Tresorname* ist der Name des Schlüsseltresors, den Sie erstellt haben. 
    
  - Für Exchange Online und Skype for Business ersetzen Sie bitte die *Office 365 App-ID* durch `00000002-0000-0ff1-ce00-000000000000`
    
  - Für SharePoint Online und OneDrive for Business ersetzen Sie bitte die *Office 365 App-ID* durch `00000003-0000-0ff1-ce00-000000000000`
    
  Beispiel: Festlegen von Berechtigungen für Exchange Online und Skype for Business:
    
  ```powershell
  Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
  -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
  ```

  Beispiel: Festlegen von Berechtigungen für SharePoint Online- und OneDrive for Business

  ```powershell
  Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1 
  -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
  ```

### <a name="enable-and-then-confirm-soft-delete-on-your-key-vaults"></a>Aktivieren und Bestätigen des vorläufigen Löschens in Ihren Schlüsseltresoren
<a name="SoftDelete"> </a>

Wenn Sie Ihre Schlüssel schnell wiederherstellen können, ist ein umfassender Dienstausfalls aufgrund von versehentlich oder in böswilliger Absicht gelöschten Schlüsseln weniger wahrscheinlich. Sie müssen diese Konfiguration, die als „Soft Delete“ (Vorläufiges Löschen) bezeichnet wird, aktivieren, bevor Sie Ihre Schlüssel mit Customer Key verwenden können. Das Aktivieren von Soft Delete ermöglicht Ihnen des Wiederherstellen von Schlüsseln oder Tresoren innerhalb von 90 Tagen nach dem Löschen, ohne diese aus der Datensicherung wiederherstellen zu müssen.
  
Führen Sie die folgenden Schritte aus, um Soft Delete für Ihre Schlüsseltresore zu aktivieren:
  
1. Melden Sie sich mit Windows PowerShell bei Ihrem Azure-Abonnement an. Anweisungen hierzu finden Sie unter [Anmelden mit Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).

2. Führen Sie das Cmdlet [Get-AzureRmKeyVault](https://docs.microsoft.com/powershell/module/azurerm.keyvault/get-azurermkeyvault) aus. In diesem Beispiel ist der *Tresorname* derjenige Name des Schlüsseltresors, den Sie für Soft Delete aktivieren: 

   ```powershell
   $v = Get-AzureRmKeyVault -VaultName <vaultname>
   $r = Get-AzureRmResource -ResourceId $v.ResourceId
   $r.Properties | Add-Member -MemberType NoteProperty -Name enableSoftDelete -Value 'True'
   Set-AzureRmResource -ResourceId $r.ResourceId -Properties $r.Properties
   ```

3. Bestätigen Sie, dass Soft Delete für den Schlüsseltresor konfiguriert ist, indem Sie das Cmdlet **Get-AzureRmKeyVault** ausführen. Wenn „Soft Delete“ für den Schlüsseltresor ordnungsgemäß konfiguriert ist, meldet die Option „Soft Delete aktiviert?“ den Wert **True**: 

   ```powershell
   Get-AzureRmKeyVault -VaultName <vaultname> | fl
   ```

### <a name="add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key"></a>Hinzufügen eines Schlüssels zu jedem Schlüsseltresor durch das Erstellen oder Importieren eines Schlüssels
<a name="AddKeystoKeyVault"> </a>

Es gibt zwei Methoden zum Hinzufügen von Schlüsseln zu einem Azure Key Vault. Sie können entweder direkt im Schlüsseltresor einen Schlüssel erstellen oder aber einen Schlüssel importieren. Das Erstellen eines Schlüssels direkt im Schlüsseltresor ist die einfachere Methode, während der Import eines Schlüssels die vollständige Kontrolle über die Generierung des Schlüssels bietet.
  
Wenn Sie direkt in Ihrem Schlüsseltresor einen Schlüssel erstellen möchten, führen Sie das Cmdlet [Add-AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Add-AzureKeyVaultKey) wie folgt aus: 
  
```powershell
Add-AzureKeyVaultKey -VaultName <vaultname> -Name <keyname> -Destination <HSM|Software> -KeyOps wrapKey,unwrapKey
```

Dabei gilt:
  
- Der *Tresorname* ist der Name des Schlüsseltresors, in dem Sie den Schlüssel erstellen möchten.

- Der *Schlüsselname* ist derjenige Name, den Sie dem neuen Schlüssel geben möchten.

    > [!TIP]
    > Benennen Sie Schlüssel, die eine ähnliche Benennungskonvention verwenden, nach dem oben für Schlüsseltresore beschriebenen Verfahren. Auf diese Weise ist die Zeichenfolge in Tools, die lediglich den Schlüsselnamen anzeigen, selbsterklärend. 
  
- Wenn Sie beabsichtigen, den Schlüssel mit einem HSM zu schützen, sollen Sie sicherstellen, dass Sie das **HSM** als Wert für den _Ziel_-Parameter festlegen. Andernfalls, geben Sie die **Software** an.

Beispiele:
  
```powershell
Add-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination Software -KeyOps wrapKey,unwrapKey
```

Wenn Sie einen Schlüssel direkt in ihren Schlüsseltresor importieren möchten, müssen Sie über ein Thales-nShield-Hardware-Sicherheitsmodul verfügen.
  
Einige Organisationen bevorzugen diese Vorgehensweise, um die Herkunft Ihrer Schlüssel festzulegen. Außerdem bietet diese Methode folgendes Features:
  
- Das für den Import verwendete Toolset beinhaltet die Bescheinigung von Thales, dass der zum Verschlüsseln des von Ihnen generierten Schlüssels genutzte Schlüsselaustauschschlüssel (Key Exchange Key, KEK) nicht exportierbar ist und in einem echten HSM generiert wird, das von Thales hergestellt wurde.

- Das Toolset beinhaltet die Bescheinigung von Thales, dass die Azure Key Vault-Sicherheitsumgebung ebenfalls mit einem echten HSM von Thales generiert wurde. Diese Bescheinigung dient für Sie als Nachweis, dass Microsoft ebenfalls Original-Thales-Hardware verwendet.

Wenden Sie sich an Ihr Sicherheitsteam, um festzustellen, ob die vorstehenden Bescheinigungen erforderlich sind. Detaillierte Anweisungen zum Erstellen eines lokalen Schlüssels und zum Importieren in Ihren Schlüsseltresor finden Sie unter [Generieren und Übertragen von HSM-geschützten Schlüsseln für Azure Key Vault](https://azure.microsoft.com/documentation/articles/key-vault-hsm-protected-keys/). Folgen Sie den Azure-Anweisungen, um in jedem Schlüsseltresor einen Schlüssel zu erstellen.
  
### <a name="check-the-recovery-level-of-your-keys"></a>Überprüfen der Wiederherstellungsebene Ihrer Schlüssel
<a name="CheckKeyRecoveryLevel"> </a>

Office 365 setzt voraus, dass das Azure Key Vault-Abonnement auf „Do Not Cancel“ (Nicht kündigen) gesetzt ist und dass die von Customer Key verwendeten Soft-Delete-Funktion aktiviert ist. Sie können dies sicherstellen, indem Sie die Wiederherstellungsstufe für Ihre Schlüssel überprüfen.
  
Führen Sie zum Überprüfen der Wiederherstellungsebene eines Schlüssels in Azure PowerShell das Cmdlet „Get-AzureKeyVaultKey“ wie folgt aus:
  
```powershell
(Get-AzureKeyVaultKey -VaultName <vaultname> -Name <keyname>).Attributes
```

Wenn die Eigenschaft _Wiederherstellungsebene_ einen anderen Wert als **Recoverable+ProtectedSubscription** (Wiederherstellbar+GeschütztesAbonnement) rückmeldet, müssen Sie diesen Artikel nochmals lesen und sicherstellen, dass Sie alle Schritte befolgt haben, um das Abonnement in das „Nicht-Kündigen-Verzeichnis“  einzutragen   und da Soft Delete für jeden Ihrer Schlüsseltresore aktiviert ist.
  
### <a name="backup-azure-key-vault"></a>Azure Key Vault-Backup
<a name="BackupAzureKeyVaultkeys"> </a>

Unmittelbar nach dem Erstellen oder Ändern eines Schlüssels, dem Durchführen einer Sicherung und dem Speichern von Kopien der Sicherung, sowohl online als auch offline. Offline-Kopien sollten nicht mit einem Netzwerk verbunden sein, d. h. beispielsweise nicht in einem Safe oder in einem gewerblichen Lager aufbewahrt werden. Mindestens eine Kopie der Sicherung sollte an einem Standort gespeichert werden, auf den Sie im Notfall zugreifen können. Die einzelnen Sicherungen sind die einzige Möglichkeit zum Wiederherstellen des Schlüsselmaterials, sollte ein Key-Vault-Schlüssel dauerhaft vernichtet oder auf andere Weise funktionsuntüchtig gemacht worden sein. Schlüssel, die sich außerhalb des Azure Key Vault befinden und in Azure Key Vault importiert wurden, sind als Sicherung nicht geeignet, da die Metadaten, die für die Verwendung des Schlüssels mit Customer Key erforderlich sind, mit dem externen Schlüssel nicht vorhanden sind. Nur eine vom Azure Key Vault erstellte Sicherung kann für Wiederherstellungsvorgänge mit Customer Key verwendet werden. Deshalb ist die Sicherung des Azure Key Vault, sobald ein Schlüssel hochgeladen oder erstellt wurde, von wesentlicher Bedeutung.
  
Für die Sicherung eines Azure Key Vault-Schlüssels führen Sie bitte das Cmdlet [Backup-AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Backup-AzureKeyVaultKey) wie folgt aus:

```powershell
Backup-AzureKeyVaultKey -VaultName <vaultname> -Name <keyname>
-OutputFile <filename .backup>
```

Stellen Sie sicher, dass in der Ausgabedatei das Suffix `.backup` (Sicherung) verwendet wird.
  
Die aus diesem Cmdlet resultierende Ausgabedatei ist verschlüsselt und kann außerhalb von Azure Key Vault nicht verwendet werden. Die Sicherung kann nur für das Azure-Abonnement wiederhergestellt werden, aus dem die Sicherung erstellt wurde.
  
> [!TIP]
> Wählen Sie für die Ausgabedatei eine Kombination aus Ihrem Tresor- und Schlüsselnamen. Dadurch wird der Dateiname selbsterklärend. Außerdem wird sichergestellt, dass die Namen der Sicherungsdateien nicht kollidieren.
  
Beispiel:
  
```powershell
Backup-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -OutputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

### <a name="validate-azure-key-vault-configuration-settings"></a>Konfigurationseinstellungen von Azure Key Vault verifizieren
<a name="Validateconfiguration"> </a>

Das Durchführen der Überprüfung vor der Verwendung von Schlüsseln in einer Datenverschlüsselungsrichtlinie (DEP) ist optional, wird jedoch dringend empfohlen. Insbesondere, wenn Sie andere als die in diesem Artikel beschriebenen Schritte zum Einrichten Ihrer Schlüssel und Tresore verwenden, sollten Sie den Sicherheitsstatus Ihrer Azure Key Vault-Ressourcen überprüfen, bevor Sie Customer Key konfigurieren.
  
Überprüfen, ob für Ihre Schlüssel die Funktionen „Abrufen“, „WrapKey“ und „unWrapKey“ aktiviert sind:
  
Führen Sie das Cmdlet [Get-AzureRmKeyVault](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Get-AzureRmKeyVault) wie folgt aus:
  
```powershell
Get-AzureRMKeyVault -VaultName <vaultname>
```

Suchen Sie in der Ausgabe nach der Zugriffsrichtlinie und, je nach Bedarf, nach der Exchange Online-Identität (GUID) bzw. der SharePoint Online Identity (GUID). Alle drei vorstehenden Berechtigungen müssen unter den Berechtigungen für Schlüssel angezeigt werden.
  
Sollte die Konfiguration der Zugriffsrichtlinien nicht korrekt sein, führen Sie das Cmdlet „Set-AzureRmKeyVaultAccessPolicy“ wie folgt aus:
  
```powershell
Set-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
```

Beispielsweise für Exchange Online und Skype for Business:
  
```powershell
Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
```

Beispielsweise für SharePoint Online und OneDrive for Business:
  
```powershell
Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1 
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName TBD
```

Um Sicherzustellen, dass für Ihre Schlüssel kein Ablaufdatum festgelegt ist, führen Sie das Cmdlet [Get-AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Get-AzureKeyVaultKey) wie folgt aus:
  
```powershell
Get-AzureKeyVaultKey -VaultName <vaultname>
```

Ein abgelaufener Schlüssel kann von Customer Key nicht verwendet werden, und Vorgänge, die mit einem abgelaufenen Schlüssel versucht werden, werden nicht ausgeführt und führen möglicherweise zu einem Dienstausfall. Es wird dringend empfohlen, dass mit Customer Key verwendete Schlüssel kein Ablaufdatum aufweisen. Ein einmal festgelegtes Ablaufdatum kann nicht gelöscht werden, es kann jedoch eine Datumänderung vorgenommen werden. Wenn ein Schlüssel verwendet werden muss, für den ein Ablaufdatum festgelegt ist, ändern Sie bitte das Ablaufdatum auf 31.12.9999. Schlüssel, für die ein anderes Datum als der 31.12.9999 als Ablaufdatum, werden von der Office 365-Überprüfung abgelehnt.
  
Zum Ändern eines Ablaufdatums, für das ein anderer Wert als der 31.12.9999 festgelegt wurde, führen Sie bitte das Cmdlet [Set-AzureKeyVaultKeyAttribute](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Set-AzureKeyVaultKeyAttribute) wie folgt aus:
  
```powershell
Set-AzureKeyVaultKeyAttribute -VaultName <vaultname> -Name <keyname> 
-Expires (Get-Date -Date "12/31/9999")
```

> [!CAUTION]
> Legen Sie keine Ablaufdaten für kryptografische Schlüssel fest, die Sie mit Customer Key verwenden.
  
### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a>Abrufen eines URI für jeden Azure Key Vault-Schlüssel
<a name="GetKeyURI"> </a>

Nachdem Sie alle Schritte zum Einrichten Ihrer Schlüsseltresore in Azure durchgeführt haben und Ihre Schlüssel hinzugefügt haben, führen Sie den folgenden Befehl aus, um den URI für den Schlüssel in jedem Schlüsseltresor abzurufen. Sie müssen diese URI verwenden, wenn Sie in weiterer Folge die einzelnen Datenverschlüsselungsrichtlinien (DEP) erstellen und zuweisen, also speichern Sie diese Informationen an einem sicheren Ort. Denken Sie daran, diesen Befehl jeweils für jeden Schlüsseltresor einmal auszuführen.
  
In Azure PowerShell:
  
```powershell
(Get-AzureKeyVaultKey -VaultName <vaultname>).Id
```

## <a name="office-365-setting-up-customer-key-for-exchange-online-and-skype-for-business"></a>Office 365: Einrichten von Customer Key für Exchange Online und Skype for Business
<a name="AzureSteps"> </a>

Bevor Sie beginnen, stellen Sie sicher, dass Sie die zum Einrichten von Azure Key Vault erforderlichen Aufgaben abgeschlossen haben. Informationen hierzu finden Sie unter [Erledigen von Aufgaben in Azure Key Vault und Microsoft FastTrack für Customer Key](controlling-your-data-using-customer-key.md#AzureSteps). 
  
Um Customer Key für Exchange Online und Skype for Business einzurichten, müssen Sie diese Schritte ausführen, indem Sie mittels Windows PowerShell eine Remoteverbindung mit Exchange Online herstellen.
  
### <a name="create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business"></a>Erstellen einer Datenverschlüsselungsrichtlinie (DEP) zur Nutzung mit Exchange Online und Skype for Business
<a name="CreateDEP4EXOSkype"> </a>

Eine Datenverschlüsselungsrichtlinie (DEP) ist mit einer Reihe von im Azure Key Vault gespeicherten Schlüsseln verknüpft. Sie weisen einem Postfach in Office 365 eine Datenverschlüsselungsrichtlinie (DEP) zu. Office 365 verwendet dann die in der Richtlinie identifizierten Schlüssel zum Verschlüsseln des Postfachs. Zum Erstellen der Datenverschlüsselungsrichtlinie (DEP) benötigen Sie die Key Vault-URI, die Sie zuvor erhalten haben. Anweisungen hierzu finden Sie unter [Abrufen eines URI für jeden Azure Key Vault-Schlüssel](controlling-your-data-using-customer-key.md#GetKeyURI).
  
Nicht vergessen! Beim Erstellen einer Datenverschlüsselungsrichtlinie (DEP) geben Sie zwei Schlüssel an, die sich in zwei verschiedenen Azure Key Vaults befinden. Stellen Sie sicher, dass sich diese Schlüssel in zwei unterschiedlichen Azure-Regionen befinden, um Geo-Redundanz sicherzustellen.
  
Um eine Datenverschlüsselungsrichtlinie (DEP) zu erstellen, führen Sie bitte folgende Schritte aus:
  
1. Stellen Sie auf Ihrem lokalen Computer über ein Geschäfts- oder Schul- bzw. Unikonto, das über globale Administratorberechtigungen in Ihrer Office 365-Organisation verfügt, eine [Verbindung mit Exchange Online PowerShell](https://technet.microsoft.com/library/jj984289%28v=exchg.160%29.aspx)her, indem Sie Windows PowerShell öffnen und den nachfolgenden Befehl ausführen.

   ```powershell
   $UserCredential = Get-Credential
   ```

2. Geben Sie im Dialogfeld für die Eingabe von Anmeldedaten in Windows PowerShell die Kontoinformationen für Ihr Geschäfts-, Schul- oder Unikonto ein, klicken Sie auf **OK** und geben Sie dann den folgenden Befehl ein.

   ```powershell
   $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
   ```

3. Führen Sie den folgenden Befehl aus.

   ```powershell
   Import-PSSession $Session
   ```

4. Um eine Datenverschlüsselungsrichtlinie zu erstellen, verwenden Sie das Cmdlet „New-DataEncryptionPolicy“, indem Sie den folgenden Befehl eingeben.

   ```powershell
   New-DataEncryptionPolicy -Name <PolicyName> -Description "PolicyDescription " -AzureKeyIDs <KeyVaultURI1>, <KeyVaultURI2>
   ```

   Dabei gilt:

   -  Der *PolicyName*ist derjenige Name, den Sie für die Richtlinie verwenden möchten. Namen dürfen keine Leerzeichen enthalten. Beispiel: USA_Postfächer.

   -  Die *PolicyDescription* ist eine benutzerfreundliche Beschreibung der Richtlinie, die Ihnen dabei hilft, sich zu merken, welchen Zweck die Richtlinie hat. In der Beschreibung sind Leerzeichen erlaubt. Beispiel: Root-Key (Hauptschlüssel) für Postfächer in den USA und den dazugehörigen Gebieten.

   -  Der *KeyVaultURI1* ist der URI für den ersten Schlüssel in der Richtlinie. Beispiel: https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01.

   -  Der *KeyVaultURI2* ist der URI für den zweiten Schlüssel in der Richtlinie. Beispiel: https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02. Trennen Sie die beiden URI mittels Komma und Leerzeichen.

   Beispiel:
  
   ```powershell
   New-DataEncryptionPolicy -Name USA_mailboxes -Description "Root key for mailboxes in USA and its territories" -AzureKeyIDs https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01, https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02
   ```

### <a name="assign-a-dep-to-a-mailbox"></a>Zuweisen einer Datenverschlüsselungsrichtlinie (DEP) zu einem Postfach
<a name="assignDEPtomailbox"> </a>

Zuweisen der Datenverschlüsselungsrichtlinie (DEP) zu einem Postfach mithilfe des Cmdlets „Set-Mailbox“. Sobald Sie die Richtlinie zugewiesen haben, kann Office 365 das Postfach mit dem in der Datenverschlüsselungsrichtlinie (DEP) angeführten Schlüssel verschlüsseln.
  
```powershell
Set-Mailbox -Identity <MailboxIdParameter> -DataEncryptionPolicy <PolicyName>
```

Dabei legt der *MailboxIdParameter* ein Postfach fest. Weitere Informationen zum Cmdlet „Set-Mailbox“ finden Sie unter [Set-Mailbox](https://technet.microsoft.com/library/bb123981%28v=exchg.160%29.aspx).
  
### <a name="validate-mailbox-encryption"></a>Überprüfen einer Postfachverschlüsselung
<a name="validatemailboxencryption"> </a>

Das Verschlüsseln eines Postfachs kann einige Zeit in Anspruch nehmen. Bei der erstmaligen Richtlinienzuweisung muss das Postfach den Wechsel von einer Datenbank zu einer anderen durchführen, bevor der Dienst das Postfach verschlüsseln kann. Wir empfehlen, dass Sie 72 Stunden warten, bevor Sie versuchen, die Verschlüsselung nach dem Ändern einer Datenverschlüsselungsrichtlinie (DEP) oder nach dem erstmaligen Zuweisen einer Datenverschlüsselungsrichtlinie (DEP) zu einem Postfach zu überprüfen.
  
Verwenden Sie das Cmdlet „Get-MailboxStatistics“, um festzustellen, ob ein Postfach verschlüsselt ist.
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

Die IsEncrypted-Eigenschaft meldet den Wert **True** (Richtig), wenn das Postfach verschlüsselt ist, und den Wert **False** (Falsch), wenn das Postfach nicht verschlüsselt ist. 

Der Zeitaufwand für das Durchführen von Postfachverschiebungen hängt von der Anzahl der Postfächer ab, denen Sie zum ersten Mal eine Datenverschlüsselungsrichtlinie (DEP) zuweisen, sowie von der Größe der Postfächer. Wenn die Postfächer nach Ablauf einer Woche ab dem Zeitpunkt der Zuweisung der Datenverschlüsselungsrichtlinie (DEP) nicht verschlüsselt wurden, leiten Sie mit dem Cmdlet „New-MoveRequest" eine Postfachverschiebung für die nicht verschlüsselten Postfächer ein.

```powershell
New-MoveRequest <mailbox alias>
```

## <a name="office-365-setting-up-customer-key-for-sharepoint-online-and-onedrive-for-business"></a>Office 365: Einrichten von Customer Key für SharePoint Online und OneDrive for Business
<a name="AzureSteps"> </a>

Bevor Sie beginnen, stellen Sie sicher, dass Sie die zum Einrichten von Azure Key Vault erforderlichen Aufgaben abgeschlossen haben. Informationen hierzu finden Sie unter [Erledigen von Aufgaben in Azure Key Vault und Microsoft FastTrack für Customer Key](controlling-your-data-using-customer-key.md#AzureSteps).
  
Um Customer Key für SharePoint Online und OneDrive for Business einzurichten, müssen Sie diese Schritte ausführen, indem Sie mittels Windows PowerShell eine Remoteverbindung mit SharePoint Online herstellen.
  
### <a name="create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo"></a>Erstellen einer Datenverschlüsselungsrichtlinie (DEP) für jede SharePoint Online- und OneDrive for Business-Geo
<a name="CreateDEP4SPOODfB"> </a>

Eine Datenverschlüsselungsrichtlinie (DEP) ist mit einer Reihe von im Azure Key Vault gespeicherten Schlüsseln verknüpft. Sie wenden eine Datenverschlüsselungsrichtlinie (DEP) auf alle Ihre Daten an einem geografischen Standort an, der auch als Geo bezeichnet wird. Wenn Sie das Multi-Geo-Feature von Office 365 verwenden, können Sie eine Datenverschlüsselungsrichtlinie (DEP) pro Geo erstellen. Wenn Sie das Multi-Geo-Feature nicht verwenden, können Sie eine in Office 365 Datenverschlüsselungsrichtlinie (DEP) zur Verwendung mit SharePoint Online und OneDrive for Business erstellen. Office 365 verwendet dann die in der Richtlinie identifizierten Schlüssel zum Verschlüsseln Ihrer Daten in diesem Geo. Zum Erstellen der Datenverschlüsselungsrichtlinie (DEP) benötigen Sie die Key Vault-URI, die Sie zuvor erhalten haben. Anweisungen hierzu finden Sie unter [Abrufen eines URI für jeden Azure Key Vault-Schlüssel](controlling-your-data-using-customer-key.md#GetKeyURI). 
  
Nicht vergessen! Beim Erstellen einer Datenverschlüsselungsrichtlinie (DEP) geben Sie zwei Schlüssel an, die sich in zwei verschiedenen Azure Key Vaults befinden. Stellen Sie sicher, dass sich diese Schlüssel in zwei unterschiedlichen Azure-Regionen befinden, um Geo-Redundanz sicherzustellen.
  
Um eine Datenverschlüsselungsrichtlinie (DEP) zu erstellen, müssen Sie mithilfe von Windows PowerShell eine Remote-Verbindung zu SharePoint Online herstellen.
  
1. Stellen Sie auf Ihrem lokalen Computer über ein Geschäfts- oder Schul- bzw. Unikonto, das über globale Administratorberechtigungen in Ihrer Office 365-Organisation verfügt, eine [Verbindung mit SharePoint Online PowerShell](https://technet.microsoft.com/library/fp161372.aspx)her.

2. Führen Sie in der Microsoft SharePoint Online Management-Shell das Cmdlet [Register-SPODataEncryptionPolicy](https://technet.microsoft.com/library/mt843950.aspx) wie folgt durch:

   ```powershell
   Register-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -PrimaryKeyVaultName <PrimaryKeyVaultName> -PrimaryKeyName <PrimaryKeyName> -PrimaryKeyVersion <PrimaryKeyVersion> -SecondaryKeyVaultName <SecondaryKeyVaultName> -SecondaryKeyName <SecondaryKeyName> -SecondaryKeyVersion <SecondaryKeyVersion>
   ```

   Sobald Sie die Datenverschlüsselungsrichtlinie (DEP) registrieren, beginnt die Verschlüsselung der Daten im Geo. Dies kann einige Zeit dauern.

### <a name="validate-encryption-of-group-sites-team-sites-and-onedrive-for-business"></a>Überprüfen der Verschlüsselung von Gruppen-Websites, Team-Websites und OneDrive for Business
<a name="validateencryptionSPO"> </a>

Sie können den Verschlüsselungsstatus überprüfen, indem Sie das Cmdlet „Get-SPODataEncryptionPolicy“ wie folgt ausführen:
  
```powershell
Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

Die Ausgabe dieses Cmdlets umfasst Folgendes:
  
- URI des Primärschlüssels.

- URI des Sekundärschlüssels.

- Verschlüsselungsstatus für den Geo. Mögliche weitere Angaben:

  - **Unregistered:** (Nicht registriert) Die Customer Key-Verschlüsselung wurde noch nicht angewendet.

  - **Registering:** (Registrierung läuft) Die Customer Key-Verschlüsselung wurde angewendet wurde und Ihre Dateien werden gegenwärtig gerade verschlüsselt. Wenn Ihr Geo diesen Status hat, werden Ihnen auch Informationen über den Prozentsatz der fertiggestellten Websites in der Geo angezeigt, damit Sie den Verschlüsselungsfortschritt überwachen können.

  - **Registered:** (Registriert) Die Customer Key- Verschlüsselung wurde angewendet, und alle Dateien auf allen Websites wurden verschlüsselt.

  - **Rolling:** Das Erstellen eines sich fortlaufend ändernden, sogenannten Rolling-Codes für den Schlüssel ist in Gang. Wenn Ihr Geo diesen Status hat, werden Ihnen auch Informationen über den Prozentsatz der Websites angezeigt, für die bereits ein Schlüssel erstellt wurde, damit Sie den Fortschritt überwachen können.

## <a name="managing-customer-key-for-office-365"></a>Verwalten von Customer Key für Office 365
<a name="ManageCustomerKey"> </a>

Nachdem Sie Customer Key für Office 365 eingerichtet haben, können Sie diese zusätzlichen Verwaltungsaufgaben ausführen.
  
- [Wiederherstellen von Azure Key Vault-Schlüsseln](controlling-your-data-using-customer-key.md#RestoreAzureKeyVaultKeys)

- [Erstellen eines Rolling-Codes oder eines Rotationscodes für einen Schlüssel in Azure Key Vault, das mit Customer Key genutzt wird](controlling-your-data-using-customer-key.md#RollCKkey)

- [Verwalten von Schlüsseltresor-Berechtigungen](controlling-your-data-using-customer-key.md#Managekeyvaultperms)

- [Ermitteln der Datenverschlüsselungsrichtlinie (DEP), die einem Postfach zugewiesen ist](controlling-your-data-using-customer-key.md#DeterminemailboxDEP)
    
### <a name="restore-azure-key-vault-keys"></a>Wiederherstellen von Azure Key Vault-Schlüsseln
<a name="RestoreAzureKeyVaultKeys"> </a>

Verwenden Sie vor dem Ausführen einer Wiederherstellung die von Soft Delete bereitgestellten Wiederherstellungsfunktionen. Für alle mit Customer Key verwendeten Schlüssel muss Soft Delete aktiviert sein. Soft Delete wirkt wie ein Recycling-Mülleimer und ermöglicht die Wiederherstellung von bis zu 90 Tagen, ohne dass eine Wiederherstellung erforderlich ist. Eine Wiederherstellung sollte nur unter extremen und außergewöhnlichen Umständen erforderlich sein, beispielsweise, wenn ein Schlüssel oder ein Schlüsseltresor verloren geht. Wenn Sie einen Schlüssel zur Verwendung mit Customer Key wiederherstellen müssen, führen Sie in Azure PowerShell das Cmdlet „Restore-AzureKeyVaultKey“ wie folgt aus:
  
```powershell
Restore-AzureKeyVaultKey -VaultName <vaultname> -InputFile <filename>
```

Beispiel:
  
```powershell
Restore-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -InputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

Wenn im Schlüsseltresor bereits ein Schlüssel mit demselben Namen vorhanden ist, schlägt der Wiederherstellungsvorgang fehl. Die Funktion „Restore-AzureKeyVaultKey“ stellt alle Schlüsselversionen und alle Metadaten für den Schlüssel, einschließlich des Schlüsselnamens, wieder her.
  
### <a name="rolling-or-rotating-a-key-in-azure-key-vault-that-you-use-with-customer-key"></a>Erstellen eines Rolling-Codes oder eines Rotationscodes für einen Schlüssel in Azure Key Vault, das mit Customer Key genutzt wird
<a name="RollCKkey"> </a>

Schlüssel mit sich fortlaufend ändernder Kodierung (Rolling-Code) sind weder für Azure Key Vault noch für Customer Key erforderlich. Außerdem sind Schlüssel, die durch ein HSM geschützt sind, praktisch unmöglich zu entschlüsseln. Selbst wenn sich ein Hauptschlüssel im Besitz eines Mitwirkenden mit bösartigen Absichten befinden sollte, gibt es kein praktikables Mittel, um die Daten zu dechiffrieren, da allein der Office 365-Code weiß, wie dieser Hauptschlüssel zu verwenden ist. Allerdings wird die sich fortlaufend ändernde Kodierung von Schlüsseln (Rolling-Code) von Customer Key unterstützt.
  
> [!CAUTION]
> Generieren Sie lediglich dann einen Rolling-Code für einen kryptografischen Schlüssel, den Sie mit Customer Key, wenn ein eindeutiger technischer Grund vorhanden ist oder eine Compliance-Anforderung die Generierung von Rolling-Codes vorschreibt. Löschen Sie darüber hinaus keine Schlüssel, die Richtlinien zugeordnet sind oder waren. Wenn Sie Rolling-Codes für Ihre Schlüssel generieren, wird Inhalt mit den vorhergehenden Schlüsseln verschlüsselt. Werden beispielsweise aktive Postfächer häufig neu verschlüsselt, so werden inaktive, abgeschaltete oder deaktivierte Postfächer möglicherweise weiterhin mit den vorhergehenden Schlüsseln verschlüsselt. SharePoint Online führt Sicherungen von Inhalten durch, um die Verlagerung der Speicherorte dieser sowie deren Wiederherstellung zu ermöglichen, weshalb es durchaus vorkommen kann, dass weiterhin Inhalte archiviert sind, die ältere Schlüssel verwendet. <br/> Um die Sicherheit Ihrer Daten zu gewährleisten, ermöglicht SharePoint Online zeitgleich nicht mehr als einen Generierungsvorgang eines Rolling-Code für einen Schlüssel. Wenn Sie für beide Schlüssel in einem Schlüsseltresor einen Rolling-Code generieren möchten, müssen Sie abwarten, bis der Rolling-Code für den ersten Schlüssel vollständig abgeschlossen ist, bevor der zweite generiert werden kann. Wir empfehlen, die Generierungsvorgänge von Rolling-Codes für Ihre Schlüssel anhand unterschiedlicher Intervallen zu staffeln, damit kein Probleme entstehen.
  
Durch die Generierung eins Rolling-Code für eine Schlüssel, fordern Sie eine neue Version eines vorhandenen Schlüssels an. Um eine neue Version eines vorhandenen Schlüssels anzufordern, verwenden Sie dasselbe Cmdlet [Add-AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Add-AzureKeyVaultKey), mit der gleichen Syntax, die Sie ursprünglich zum Erstellen des Schlüssels verwendet haben.
  
Beispiel:
  
```powershell
Add-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination HSM -KeyOps @('wrapKey','unwrapKey') -NotBefore (Get-Date -Date "12/27/2016 12:01 AM")
```

In diesem Beispiel wird, da bereits ein Schlüssel mit der Bezeichnung **Contoso-O365EX-NA-VaultA1-Key001** im Schlüsseltresor **Contoso-O365EX-NA-VaultA1** vorhanden ist, eine neue Schlüsselversion erstellt. Dieser Vorgang führt dazu, dass eine neue Schlüsselversion hinzugefügt wird. Bei diesem Vorgang werden die bisherigen Schlüsselversionen aus der Versionshistorie des Schlüssels beibehalten, sodass die zuvor mit diesem Schlüssel verschlüsselten Daten weiterhin entschlüsselt werden können. Sobald die Generierung eines Rolling-Code für einen mit einer Datenverschlüsselungsrichtlinie (DEP) gekoppelten Schlüssel abgeschlossen ist, müssen Sie ein zusätzliches Cmdlet durchführen, um sicherzustellen, das Customer Key künftig den neuen Schlüssel nutzt.
  
#### <a name="enable-exchange-online-and-skype-for-business-to-use-a-new-key-after-you-roll-or-rotate-keys-in-azure-key-vault"></a>Aktivieren der Verwendung eines neuen Schlüssels nach der Generierung eines Rolling- oder Rotation-Code für Schlüssel in Azure Key Vault durch Exchange Online und Skype for Business

Wenn Sie für einen der Schlüssel in Azure Key Vault, der mit einer Datenverschlüsselungsrichtlinie (DEP) gekoppelt ist und mit Exchange Online und Skype for Business verwendet wird, einen Rolling-Code generieren, müssen Sie den folgenden Befehl ausführen, um die DEP zu aktualisieren und die Verwendung des neuen Schlüssels durch Office 365 zu aktivieren.
  
Um Customer Key anzuweisen, den neuen Schlüssel für die Verschlüsselung von Postfächern in Office 365 zu verwenden, müssen Sie das Cmdlet „Set-DataEncryptionPolicy“ wie folgt ausführen:
  
```powershell
Set-DataEncryptionPolicy <policyname> -Refresh
```

Innerhalb von 48 Stunden werden die unter Anwendung dieser Richtlinie verschlüsselten, aktiven Postfächer dem aktualisierten Schlüssel zugeordnet. Führen Sie die unter [Ermitteln der einem Postfach zugewiesenen Datenverschlüsselungsrichtlinie (DEP) ](controlling-your-data-using-customer-key.md#DeterminemailboxDEP)angeführten Schritte durch, um den Wert für die DataEncryptionPolicyID-Eigenschaft des Postfachs zu überprüfen. Der Wert für diese Eigenschaft ändert sich entsprechend, sobald der aktualisierte Schlüssel angewendet wurde.
  
#### <a name="enable-sharepoint-online-and-onedrive-for-business-to-use-a-new-key-after-you-roll-or-rotate-keys-in-azure-key-vault"></a>Aktivieren der Verwendung eines neuen Schlüssels nach der Generierung eines Rolling- oder Rotation-Codes für Schlüssel in Azure Key Vault durch SharePoint Online und OneDrive for Business

Wenn Sie für einen der Schlüssel in Azure Key Vault, der mit einer Datenverschlüsselungsrichtlinie (DEP) gekoppelt ist und mit SharePoint Online und OneDrive for Business verwendet wird, einen Rolling-Code generieren, müssen Sie das Cmdlet [Update-SPODataEncryptionPolicy](https://technet.microsoft.com/library/mt843948.aspx) ausführen, um die DEP zu aktualisieren und die Verwendung des neuen Schlüssels durch Office 365 zu aktivieren. 
  
```powershell
Update-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -KeyVaultName <ReplacementKeyVaultName> -KeyName <ReplacementKeyName> -KeyVersion <ReplacementKeyVersion> -KeyType <Primary | Secondary>
```

Dadurch wird der Vorgang zur Generierung eines Rolling-Code für einen Schlüssel, der von SharePoint Online und OneDrive for Business verwendet wird, in Gang gesetzt. Diese Aktion erfolgt nicht sofort. Zum Anzeigen des Fortschritts der Generierung eines Rolling-Code für einen Schlüssel, müssen Sie das Cmdlet „Get-SPODataEncryptionPolicy“ wie folgt ausführen:
  
```powershell
Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

### <a name="manage-key-vault-permissions"></a>Verwalten von Schlüsseltresor-Berechtigungen
<a name="Managekeyvaultperms"> </a>

Mehrere Cmdlets stehen zur Verfügung, mit denen Sie die Schlüsseltresor-Berechtigungen ansehen und, falls erforderlich, entfernen können. Möglicherweise müssen Sie Berechtigungen entfernen, beispielsweise, wenn ein Mitarbeiter das Team verlässt.
  
Führen Sie das Cmdlet „Get-AzureRmKeyVault“ aus, um die Berechtigungen für den Schlüsseltresor ‚Azure Key Vault‘ anzuzeigen:
  
```powershell
Get-AzureRmKeyVault -VaultName <vaultname>
```

Beispiel:
  
```powershell
Get-AzureRmKeyVault -VaultName Contoso-O365EX-NA-VaultA1
```

Führen Sie das Cmdlet „Remove-AzureRmKeyVaultAccessPolicy“ aus, um die Berechtigungen eines Administrators zu entfernen:
  
```powershell
Remove-AzureRmKeyVaultAccessPolicy -VaultName <vaultname>
-UserPrincipalName <UPN of user>
```

Beispiel:
  
```powershell
Remove-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1
-UserPrincipalName alice@contoso.com
```

### <a name="determine-the-dep-assigned-to-a-mailbox"></a>Ermitteln der Datenverschlüsselungsrichtlinie (DEP), die einem Postfach zugewiesen ist
<a name="DeterminemailboxDEP"> </a>

Verwenden Sie das Cmdlet „Get-MailboxStatistics“, um zu ermitteln, welche Datenverschlüsselungsrichtlinie (DEP) einem Postfach zugewiesen ist. Das Cmdlet meldet einen eindeutigen Bezeichner (GUID) zurück.
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl DataEncryptionPolicyID
```

Dabei legt der *GeneralMailboxOrMailUserIdParameter* ein bestimmtes Postfach fest. Weitere Informationen zum Cmdlet „Get-MailboxStatistics“ finden Sie unter [Get-MailboxStatistics](https://technet.microsoft.com/library/bb124612%28v=exchg.160%29.aspx).
  
Verwenden Sie den GUID, um den Anzeigenamen der Datenverschlüsselungsrichtlinie (DEP) zu ermitteln, der das Postfach zugewiesen ist, indem Sie das folgende Cmdlet ausführen.
  
```powershell
Get-DataEncryptionPolicy <GUID>
```

Dabei ist der *GUID* derjenige GUID, der vom Cmdlet „Get-MailboxStatistics“ im vorherigen Schritt zurückgemeldet wurde.
