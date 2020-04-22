---
title: Einrichten des Kunden Schlüssels
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 02/05/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: In diesem Artikel erfahren Sie, wie Sie den Kundenschlüssel für Microsoft 365 für Exchange Online-, Skype for Business-, SharePoint Online-, OneDrive für Unternehmen-und Microsoft Teams-Dateien einrichten.
ms.openlocfilehash: c9c02f697e04a5cd01ddce1546b6712091712025
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43634197"
---
# <a name="set-up-customer-key"></a>Einrichten des Kunden Schlüssels

Mit dem Kundenschlüssel können Sie die Verschlüsselungsschlüssel Ihrer Organisation steuern und dann Microsoft 365 so konfigurieren, dass Sie Sie zum Verschlüsseln von Daten im Ruhezustand in Microsoft-Rechenzentren verwenden. Mit anderen Worten: Customer Key ermöglicht es Kunden, mit ihren Schlüsseln eine Verschlüsselungsebene hinzuzufügen, die Ihnen gehört. Zu den Daten im Ruhezustand gehören Daten aus Exchange Online und Skype for Business, die in SharePoint Online und OneDrive for Business in Postfächern und Dateien gespeichert sind.

Sie müssen Azure einrichten, bevor Sie Customer Key für Office 365 verwenden können. In diesem themenbezogenen Artikel werden die Schritte beschrieben, die Sie ausführen müssen, um die erforderlichen Azure-Ressourcen zu erstellen und zu konfigurieren, und danach auch die Schritte zum Einrichten von Customer Key in Office 365. Nachdem Sie das Azure-Setup abgeschlossen haben, legen Sie fest, welche Richtlinie und somit auch, welche Schlüssel den Postfächern und Dateien in Ihrer Organisation zugewiesen werden sollen. Für Postfächer und Dateien, denen Sie keine Richtlinie zuweisen, werden Verschlüsselungsrichtlinien verwendet, die von Microsoft gesteuert und verwaltet werden. Weitere Informationen zum Kundenschlüssel oder eine allgemeine Übersicht finden Sie unter [Dienst Verschlüsselung mit Kundenschlüssel in Office 365](customer-key-overview.md).
  
> [!IMPORTANT]
> Es wird dringend empfohlen, die in diesem Artikel vorgestellten, bewährten Methoden zu befolgen. Diese werden sind als **TIPP** und **WICHTIG** bezeichnet. Customer Key ermöglicht Ihnen die Kontrolle über die grundlegenden kryptografischen Schlüssel, deren Geltungsbereich so groß wie Ihre gesamte Organisation sein kann. Dies bedeutet, dass Fehler im Zusammenhang mit diesen Schlüsseln einen großen Einfluss haben und zu Dienstunterbrechungen oder unwiderruflichen Datenverlusten führen können.
  
## <a name="before-you-set-up-customer-key"></a>Vor dem Einrichten des Kunden Schlüssels

Stellen Sie vor dem ersten Start sicher, dass Sie über die entsprechende Lizenzierung für Ihre Organisation verfügen. Kundenschlüssel in Microsoft 365 wird in Office 365 E5 oder Advanced Compliance SKU angeboten. Um die Konzepte und Verfahren in diesem Thema zu verstehen, lesen Sie die [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/) -Dokumentation. Machen Sie sich außerdem mit den in Azure verwendeten Begriffen vertraut, beispielsweise [Mandant](https://docs.microsoft.com/previous-versions/azure/azure-services/jj573650(v=azure.100)).

Der kurzstand wird nur zum Erfassen der erforderlichen Mandanten-und Dienstkonfigurationsinformationen verwendet, die für die Registrierung für den Kundenschlüssel verwendet werden. Die Kundenschlüssel Angebote werden über die Kurzarbeits Veröffentlichung veröffentlicht, sodass Sie und unsere Partner die erforderlichen Informationen bequem mit derselben Methode übermitteln können. Mit dem schnelleren Archivieren von Daten, die Sie im Angebot bereitgestellt haben, können Sie auch einfach archivieren.
  
Wenn Sie weitere Unterstützung über die Dokumentation hinaus benötigen, wenden Sie sich an Microsoft Consulting Services (MCS), Premier Field Engineering (pfe) oder an einen Microsoft-Partner, um Hilfe zu erhalten. Um Feedback zum Kundenschlüssel bereitzustellen, einschließlich der Dokumentation, senden Sie Ihre Ideen, Vorschläge und Perspektiven an customerkeyfeedback@Microsoft.com.
  
## <a name="overview-of-steps-to-set-up-customer-key"></a>Übersicht über die Schritte zum Einrichten des Kunden Schlüssels

Um den Kundenschlüssel einzurichten, führen Sie diese Aufgaben in der angegebenen Reihenfolge aus. Der Rest dieses Artikels enthält detaillierte Anweisungen zu den einzelnen Aufgaben oder Links zu weiteren Informationen zu den einzelnen Schritten des Prozesses.
  
**In Azure und Microsoft FastTrack:**
  
Für die Durchführung der meisten dieser Schritte müssen Sie eine Remoteverbindung mit Azure PowerShell herstellen. Um optimale Ergebnisse zu erzielen, sollten Sie Version 4.4.0 oder höher von Azure PowerShell verwenden.
  
- [Zwei neue Azure-Abonnements erstellen](#create-two-new-azure-subscriptions)

- [Azure-Abonnements registrieren, um einen obligatorischen Aufbewahrungszeitraum zu nutzen](#register-azure-subscriptions-to-use-a-mandatory-retention-period)

  Die Registrierung kann ab einem bis zu fünf Arbeitstagen dauern.

- [Senden einer Anforderung zum Aktivieren von Customer Key für Office 365](#submit-a-request-to-activate-customer-key-for-office-365)

Nachdem Sie die beiden neuen Azure-Abonnements erstellt haben, müssen Sie die entsprechende Anforderung für das Customer Key-Angebot übermitteln, indem Sie ein Webformular ausfüllen, das im Microsoft FastTrack-Portal gehostet wird. **Das FastTrack-Team bitte keine Unterstützung für Customer Key. Office nutzt das FastTrack-Portal einfach für die Übermittlung des Formulars und um uns dabei zu helfen, die relevanten Angebote für Customer Key nachzuverfolgen**.

- [Erstellen eines Premium Azure Key Vault für jedes Abonnement](#create-a-premium-azure-key-vault-in-each-subscription)

- [Zuweisen von Berechtigungen für jeden Schlüsseltresor (Key Vault)](#assign-permissions-to-each-key-vault)

- [Aktivieren und Bestätigen des vorläufigen Löschens in Ihren Schlüsseltresoren](#enable-and-then-confirm-soft-delete-on-your-key-vaults)

- [Hinzufügen eines Schlüssels zu jedem Schlüsseltresor durch das Erstellen oder Importieren eines Schlüssels](#add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key)

- [Überprüfen der Wiederherstellungsebene Ihrer Schlüssel](#check-the-recovery-level-of-your-keys)

- [Sichern von Azure Key Vault](#back-up-azure-key-vault)

- [Konfigurationseinstellungen von Azure Key Vault verifizieren](#validate-azure-key-vault-configuration-settings)

- [Anrufen des URI für jeden Azure Key Vault-Schlüssel](#obtain-the-uri-for-each-azure-key-vault-key)

**In Office 365:**
  
Exchange Online und Skype for Business:
  
- [Erstellen einer Datenverschlüsselungsrichtlinie (DEP) für die Nutzung von Exchange Online und Skype for Business](#create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business)

- [Zuweisen einer Datenverschlüsselungsrichtlinie (DEP) zu einem Postfach](#assign-a-dep-to-a-mailbox)

- [Überprüfen einer Postfachverschlüsselung](#validate-mailbox-encryption)

SharePoint Online und OneDrive for Business:
  
- [Erstellen einer Datenverschlüsselungsrichtlinie (DEP) für jede SharePoint Online- und OneDrive for Business-Geo](#create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo)

- [Überprüfen der Dateiverschlüsselung für SharePoint Online-, OneDrive für Unternehmen-und Microsoft Teams-Dateien](#validate-file-encryption)

## <a name="complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key"></a>Erledigen von Aufgaben in Azure Key Vault und Microsoft FastTrack für Customer Key

Führen Sie diese Aufgaben in Azure Key Vault aus. Sie müssen diese Schritte ausführen, unabhängig davon, ob Sie den Kundenschlüssel für Exchange Online und Skype for Business oder für SharePoint Online-, OneDrive für Unternehmen-und Microsoft Teams-Dateien oder für alle unterstützten Dienste in Office 365 einrichten möchten.
  
### <a name="create-two-new-azure-subscriptions"></a>Zwei neue Azure-Abonnements erstellen

Kundenschlüssel erfordert zwei Azure-Abonnements. Als bewährte Methode empfiehlt Microsoft, neue Azure-Abonnements für die Verwendung mit Customer Key zu erstellen. Azure Key-Tresorschlüssel können nur für Anwendungen in demselben Azure-Active Directory (AAD)-Mandanten autorisiert werden, Sie müssen die neuen Abonnements mit demselben Azure AD Mandanten erstellen, der in Ihrer Organisation verwendet wird, in der das DEPs zugewiesen wird. Verwenden Sie beispielsweise Ihr Arbeits-oder Schulkonto, das über globale Administratorrechte in Ihrer Organisation verfügt. Weitere Informationen zu den einzelnen Arbeitsschritten finden Sie unter [Als Unternehmen für Azure registrieren](https://azure.microsoft.com/documentation/articles/sign-up-organization/).
  
> [!IMPORTANT]
> Für Customer Key sind zwei Schlüssel für jede Daten- Verschlüsselungsrichtlinie (DEP) erforderlich. Zu diesem Zweck müssen Sie zwei Azure-Abonnements erstellen. Als bewährte Methode empfiehlt Microsoft, dass separate Mitglieder Ihrer Organisation jeweils einen Schlüssel für jedes Abonnement konfigurieren. Darüber hinaus sollten diese Azure-Abonnements nur zum Verwalten von kryptografischen Schlüsseln für Office 365 verwendet werden. Auf diese Weise ist Ihre Organisation geschützt, falls einer ihrer Betreiber versehentlich, absichtlich oder in böswilliger Absicht die Schlüssel, für die Sie verantwortlich sind, löscht oder auf andere Weise unsachgemäß handhabt. <br/> Es wird empfohlen, dass Sie neue Azure-Abonnements einrichten, die ausschließlich zum Verwalten von Azure Key Vault-Ressourcen für die Verwendung mit Customer Key genutzt werden. Es gibt praktisch keine Beschränkung hinsichtlich der Anzahl von Azure-Abonnements, die Sie für Ihre Organisation erstellen können. Durch die Nutzung dieser bewährten Methoden können Sie die Auswirkungen von menschlichen Fehlern bei der Verwaltung der von Customer Key genutzten Ressourcen minimieren.
  
### <a name="submit-a-request-to-activate-customer-key-for-office-365"></a>Senden einer Anforderung zum Aktivieren von Customer Key für Office 365

Sobald Sie die Azure-Schritte abgeschlossen haben, müssen Sie im [Microsoft FastTrack-Portal](https://fasttrack.microsoft.com/) eine Angebotsanfrage übermitteln. Sobald Sie eine Anforderung über das FastTrack-Web-Portal übermittelt haben, überprüft Microsoft die von Ihnen bereitgestellten Konfigurationsdaten für den Azure Key Vault und die Kontaktinformationen. Die von Ihnen im Angebotsformular hinsichtlich der autorisierten Mitarbeiter Ihrer Organisation getroffene Auswahl ist wesentlich und für das Abschließen der Registrierung von Customer Key erforderlich. Die Führungskräfte Ihrer Organisation, die Sie im Formular auswählen, werden genutzt, um die Authentizität jeder Anforderung zum Widerrufen und Löschen aller Schlüssel verwendet wird, die mit einer Customer Key Datenverschlüsselungsrichtlinie verwendet werden, sicherzustellen. Sie müssen diesen Schritt einmal ausführen, um Customer Key für Exchange Online und Skype for Business zu aktivieren, und ein zweites Mal, um Customer Key für SharePoint Online und OneDrive for Business zu aktivieren.
  
Führen Sie zur Übermittlung eines Angebots zum Aktivieren von Customer Key die folgenden Schritte aus:
  
1. Melden Sie sich mit einem Arbeits-oder Schulkonto, das über globale Administratorberechtigungen in Ihrer Organisation verfügt, beim [Microsoft-Portal](https://fasttrack.microsoft.com/)an.

2. Sobald Sie angemeldet sind, wechseln Sie zum **Dashboard**.

3. Wählen Sie **Angebote** und überprüfen Sie das Verzeichnis der aktuellen Angebote.

4. Wählen Sie **Weitere Informationen** zu dem für Sie geltenden Angebot:

   - **Exchange Online und Skype for Business:** Wählen Sie ** Weitere Informationen ** zum Angebot **Customer Key für Exchange**.

   - **SharePoint Online-, OneDrive für Unternehmen-und Microsoft Teams-Dateien:** Wählen Sie weitere **Informationen** im **Kundenschlüssel für SharePoint und OneDrive für Unternehmen** Angebot.

5. Wählen Sie auf der Seite **Angebotsdetails** **Anforderung erstellen**.

6. Tragen Sie alle relevanten Details und erforderlichen Informationen im Angebotsformular ein. Achten Sie besonders auf Ihre Auswahl, welche MitarbeiterInnen Ihrer Organisation Sie autorisieren, die permanente und unwiderrufliche Vernichtung von kryptografischen Schlüsseln und Daten zu genehmigen. Sobald Sie das Formular ausgefüllt haben, wählen Sie **Senden**.

### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a>Azure- Abonnements registrieren, um einen obligatorischen Aufbewahrungszeitraum zu nutzen.

Der vorübergehende oder dauerhafte Verlust von kryptografischen Schlüsseln kann für den Betrieb eines Dienstes sehr störend oder sogar katastrophal sein und zu Datenverlust führen. Aus diesem Grund ist für die mit Customer Key verwendeten Ressourcen ein starker Schutz erforderlich. Alle Azure-Ressourcen, die mit Customer Key verwendet werden, bieten Schutzmechanismen, die weit über die Standardkonfiguration hinaus gehen. Azure-Abonnements können derart gekennzeichnet oder registriert werden, dass eine sofortige und unwiderrufliche Kündigung vermieden wird. Dies wird als Registrierung eines obligatorischen Aufbewahrungszeitraums bezeichnet. Die erforderlichen Schritte zum Registrieren von Azure-Abonnements für einen obligatorischen Aufbewahrungszeitraum erfordern die Zusammenarbeit mit dem Microsoft 365-Team. Die Registrierung kann ab einen bis fünf Arbeitstage dauern. Bisher wurde diese Funktion zeitweise als „Nicht kündigen" bezeichnet.
  
Bevor Sie sich an das Microsoft 365-Team wenden, müssen Sie für jedes Azure-Abonnement, das Sie mit dem Kundenschlüssel verwenden, die folgenden Schritte ausführen. Stellen Sie sicher, dass das [Azure PowerShell AZ](https://docs.microsoft.com/powershell/azure/new-azureps-module-az) -Modul installiert ist, bevor Sie beginnen.
  
1. Melden Sie sich mit Azure PowerShell an. Anweisungen finden Sie unter [Anmelden mit Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).

2. Führen Sie das Cmdlet Register-AzProviderFeature aus, um Ihre Abonnements für die Verwendung eines obligatorischen Aufbewahrungszeitraums zu registrieren. Führen Sie diese Aktion für jedes Abonnement aus.

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.KeyVault
   ```

3. Wenden Sie sich an Microsoft, damit der Prozess abgeschlossen wird. Um mit dem SharePoint- und OneDrive for Business-Team in Verbindung zu treten, wenden Sie sich bitte an [spock@microsoft.com](mailto:spock@microsoft.com). Für Exchange Online und Skype for Business wenden Sie sich bitte an [exock@microsoft.com](mailto:exock@microsoft.com). Teilen Sie uns in Ihrem E-Mail bitte Folgendes mit:

   **Betreff**: Customer Key für \<*Vollständig qualifizierter Domänenname Ihres Mandanten*\>

   **Textkörper**: Abonnements-IDs, für die Sie einen obligatorischen Aufbewahrungszeitraum verbindlich festlegen möchten.
   Die Ausgabe von Get-AzProviderFeature für jedes Abonnement.

   Die Service-Level-Vereinbarung (Service Level Agreement, SLA) für den Abschluss dieses Vorgangs beläuft sich auf fünf Werktage, nachdem Microsoft benachrichtigt wurde (und überprüft hat, dass Sie Ihre Abonnements für die Nutzung eines obligatorischen Aufbewahrungszeitraums registriert haben).

4. Nachdem Sie eine Benachrichtigung von Microsoft erhalten haben, dass die Registrierung abgeschlossen ist, überprüfen Sie den Status Ihrer Registrierung, indem Sie den Befehl Get-AzProviderFeature wie folgt ausführen. Wenn überprüft, gibt der Befehl Get-AzProviderFeature den Wert **registered** für die **Registrierungsstatus** Eigenschaft zurück. Führen Sie diese Aktion für jedes Abonnement aus.

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Get-AzProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
   ```

5. Führen Sie den Befehl Register-AzResourceProvider aus, um den Vorgang abzuschließen. Führen Sie diese Aktion für jedes Abonnement aus.

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzResourceProvider -ProviderNamespace Microsoft.KeyVault
   ```

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a>Erstellen eines Premium Azure Key Vault für jedes Abonnement

Die Schritte zum Erstellen eines Schlüssel Tresors sind in ["erste Schritte mit Azure Key Vault"](https://azure.microsoft.com/documentation/articles/key-vault-get-started/)dokumentiert, das Sie durch das Installieren und Ingangsetzen von Azure PowerShell, das Herstellen einer Verbindung mit Ihrem Azure-Abonnement, das Erstellen einer Ressourcengruppe und das Erstellen eines Schlüsseltresors in dieser Ressourcengruppe führt.
  
Wenn Sie einen Schlüsseltresor erstellen, müssen Sie eine SKU auswählen: entweder Standard oder Premium. Die Standard-SKU ermöglicht das Schützen von Azure Key Vault-Schlüsseln mittels Software – es gibt keinen Schlüsselschutz mittels eines Hardware-Sicherheitsmoduls (HSM) – und die Premium-SKU ermöglicht die Verwendung von Hardware-Sicherheitsmodulen zum Schutz von Key-Vault-Schlüsseln. Customer Key akzeptiert Schlüsseltresore mit jeder SKU, wobei Microsoft dringend empfiehlt, nur die Premium-SKU zu verwenden. Die Betriebskosten mit Schlüsseln eines der beiden Typen sind identisch. Der einzige Unterschied bei den Kosten sind die monatlichen Kosten für jeden HSM-geschützten Schlüsseln. Detailinformationen finden Si unter [Key Vault-Preise](https://azure.microsoft.com/pricing/details/key-vault/).
  
> [!IMPORTANT]
> Verwenden Sie die Premium-SKU-Schlüsseltresore und HSM-geschützten Schlüssel für Produktionsdaten, und verwenden Sie nur standardmäßige SKU-Schlüsseltresore und Schlüssel für Tests und Überprüfungen.
  
Erstellen Sie für jeden Microsoft 365-Dienst, mit dem Sie den Kundenschlüssel verwenden, in jedem der beiden Azure-Abonnements, die Sie erstellt haben, einen schlüsseltresor. Beispielsweise erstellen Sie nur für Exchange Online und Skype for Business oder SharePoint Online und OneDrive for Business lediglich zwei Tresore. Um Customer Key für Exchange Online und SharePoint Online zu aktivieren, erstellen Sie zwei Paar Schlüsseltresore.
  
Verwenden Sie eine Benennungskonvention für Schlüssel Tresore, die die vorgesehene Verwendung der Daten Verschlüsselungsrichtlinie wiedergibt, mit der Sie die Tresore verknüpfen. Im nachstehenden Abschnitt „Bewährte Methoden“ finden Sie Empfehlungen zur Benennung.
  
Erstellen Sie für jede Datenverschlüsselungsrichtlinie eine eigene, paarweise angeordnete Tresor-Gruppe. Bei Exchange Online wählen Sie den Geltungsbereich einer Datenverschlüsselungsrichtlinie, wenn Sie die Richtlinie dem Postfach zuweisen. Einem Postfach kann nur eine Richtlinie zugewiesen sein, allerding können Sie bis zu 50 Richtlinien erstellen. Für SharePoint Online der Bereich einer Richtlinie alle Daten innerhalb einer Organisation an einem geografischen Standort oder _Geo_.

Das Erstellen von Schlüsseltresoren setzt außerdem die Erstellung von Azure-Ressourcengruppen voraus, da für Schlüsseltresore Speicherkapazität (wenn auch sehr geringe) erforderlich ist und die Schlüsseltresor-Protokollierung (sofern aktiviert) außerdem gespeicherte Daten generiert. Als bewährte Methode empfiehlt Microsoft die Verwendung eigener Administratoren zum Verwalten jeder Ressourcengruppe, wobei die Verwaltung mit der Gruppe der Administratoren abgestimmt wird, die alle zugehörigen Customer Key-Ressourcen verwalten.
  
> [!IMPORTANT]
> Um die Verfügbarkeit zu maximieren, sollten sich Ihre Schlüssel Tresore in Regionen befinden, die sich in der Nähe Ihres Microsoft 365-Diensts befinden. Wenn sich beispielsweise Ihre Exchange Online-Organisation in Nordamerika befindet, sollten Sie Ihre Schlüsseldepots in Nordamerika platzieren. Wenn Ihre Exchange Online-Organisation in Europa ist, sollten Sie Ihre Schlüsseldepots in Europa platzieren.<br/>Verwenden Sie für die Benennung ein gemeinsames Präfix für Schlüsseltresore sowie eine Abkürzung für die Verwendung und den Umfang des Schlüsseltresors und der Schlüssel (so ist z. B. für den Contoso SharePoint-Dienst, in den sich die Tresore in Nordamerika befinden, ein mögliches Namenspaar „Contoso-O365SP-NV-VaultA1“ und „Contoso-O365SP-NV-VaultA2“. In Azure sind Tresornamen global eindeutige Zeichenfolgen, daher müssen Sie möglicherweise Variationen Ihrer gewünschten Namen ausprobieren, falls die gewünschten Namen bereits von anderen Azure-Kunden beansprucht werden. Ab Juli 2017 können Tresornamen nicht mehr geändert werden, daher empfiehlt es sich, einen schriftlichen Setup-Plan zu erstellen und eine zweite Person zu beauftragen, die überprüft, ob der Plan ordnungsgemäß ausgeführt wird.<br/>Erstellen Sie Ihre Depots nach Möglichkeit in nicht-gekoppelten Regionen. Gekoppelte Azure-Regionen bieten eine hohe Verfügbarkeit über Dienstausfall-Domänen hinweg. Dementsprechend können regionale Paare gegenseitig als Backup-Region der jeweils anderen betrachtet werden. Dies bedeutet, dass eine Azure-Ressource, die in einer bestimmten Region platziert ist, durch die gekoppelte Region automatisch an Fehlertoleranz gewinnt. Aus diesem Grund bedeutet das Auswählen von Regionen für zwei Tresore, die in einer Daten Verschlüsselungsrichtlinie verwendet werden, in der die Regionen gekoppelt sind, dass nur insgesamt zwei Verfügbarkeits Regionen verwendet werden. In den meisten geografischen Regionen gibt es nur zwei Regionen, weshalb es noch nicht möglich ist, nicht-gekoppelte Regionen auszuwählen. Wählen Sie nach Möglichkeit zwei nicht gepaarte Bereiche für die beiden Tresore aus, die mit einer Daten Verschlüsselungsrichtlinie verwendet werden. Dies hat den positiven Effekt, dass insgesamt vier verfügbare Regionen genutzt werden. Weitere Informationen hierzu sowie ein aktuelles Verzeichnis der Regionenpaare finden Sie unter [Geschäftskontinuität und Notfallwiederherstellung (Business continuity and disaster recovery, BCDR): Gekoppelte Regionen in Azure](https://docs.microsoft.com/azure/best-practices-availability-paired-regions).
  
### <a name="assign-permissions-to-each-key-vault"></a>Zuweisen von Berechtigungen für jeden Schlüsseltresor (Key Vault)

Sie müssen für jeden Schlüsseltresor entsprechend der von Ihnen gewählten Implementierung drei gesonderte Berechtigungsgruppen für Customer Key definieren. Sie müssen beispielsweise eine Berechtigungsgruppe für jede der folgenden Optionen definieren:
  
- **Schlüsseltresor-Administratoren**, deren Aufgabe das tägliche Verwalten Ihrer Schlüsseltresore für Ihre Organisation ist. Zu diesen Aufgaben gehören Datensicherung sowie Erstellen, Abrufen, Importieren, Auflisten und Wiederherstellen.

  > [!IMPORTANT]
  > Die Berechtigungsgruppe, die Schlüsseltresor-Administratoren zugewiesen ist, beinhaltet keine Berechtigung zum Löschen von Schlüsseln. Dies ist beabsichtigt und eine wichtige Vorgehensweise. Kryptografische Schlüssel werden normalerweise nicht gelöscht, da dadurch Daten dauerhaft vernichtet werden. Eine bewährte Methode besteht darin, den Schlüsseltresor-Administratoren diese Berechtigung nicht standardmäßig zuzuweisen. Behalten Sie stattdessen diese Berechtigung den Schlüsseltresor-Mitwirkenden vor und weisen Sie diese einem Administrator nur kurzfristig und lediglich, sofern die damit verbundenen Folgen klar verstanden wurden, zu.
  
  Um diese Berechtigungen einem Benutzer in Ihrer Organisation zuzuweisen, melden Sie sich bei Ihrem Azure-Abonnement mit Azure PowerShell an. Anweisungen finden Sie unter [Anmelden mit Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).

- Führen Sie das Cmdlet "Cmdlet festlegen-AzKeyVaultAccessPolicy" aus, um die erforderlichen Berechtigungen zuzuweisen.

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
   ```

   Beispiel:

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
   ```

- **Schlüsseltresor-Mitwirkenden**, die Berechtigungen für den Azure Key Vault selbst ändern können. Sie müssen diese Berechtigungen ändern, wenn Mitarbeiter Ihr Team verlassen oder Ihrem Team beitreten oder, im äußerst selten eintretenden Fall, dass Schlüsseltresor-Administratoren berechtigterweise die Berechtigung zum Löschen oder Wiederherstellen eines Schlüssels benötigen. Dieser Gruppe von Schlüsseltresor-Mitwirkenden muss die Rolle **Mitwirkender** für Ihren Schlüsseltresor zugewiesen werden. Sie können diese Rolle mithilfe des Azure-Ressourcenmanagers zuweisen. Informationen zu den einzelnen Schritten finden Sie unter [Verwenden der rollenbasierten Zugriffssteuerung zum Verwalten des Zugriffs auf Ihre Azure-Abonnementressourcen](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure). Der Administrator, der ein Abonnement erstellt, verfügt implizit über diesen Zugriff sowie die Möglichkeit, der Rolle des Mitwirkenden weitere Administratoren zuzuweisen.

- Wenn Sie den Kundenschlüssel mit Exchange Online und Skype for Business verwenden möchten, müssen Sie Microsoft 365 die Berechtigung erteilen, das Schlüsseldepot im Namen von Exchange Online und Skype for Business zu verwenden. Wenn Sie den Kundenschlüssel mit SharePoint Online und OneDrive für Unternehmen verwenden möchten, müssen Sie ebenfalls die Berechtigung für den Microsoft 365 hinzufügen, um den schlüsseltresor im Namen von SharePoint Online und OneDrive für Unternehmen zu verwenden. Führen Sie das Cmdlet " **AzKeyVaultAccessPolicy** " mit der folgenden Syntax aus, um die Berechtigung für Microsoft 365 zu erteilen: 

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
   ```

   Dabei gilt:

    - *Vault Name* ist der Name des Schlüssel Tresors, den Sie erstellt haben.

    - Für Exchange Online und Skype for Business ersetzen Sie bitte die *Office 365 App-ID* durch `00000002-0000-0ff1-ce00-000000000000`

    - Ersetzen Sie für SharePoint Online-, OneDrive für Unternehmen-und Microsoft Teams-Dateien *Office 365* -ID durch`00000003-0000-0ff1-ce00-000000000000`

  Beispiel: Festlegen von Berechtigungen für Exchange Online und Skype for Business:

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
   ```

  Beispiel: Festlegen von Berechtigungen für SharePoint Online-, OneDrive für Unternehmen-und Microsoft Teams-Dateien:

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
   ```

### <a name="enable-and-then-confirm-soft-delete-on-your-key-vaults"></a>Aktivieren und Bestätigen des vorläufigen Löschens in Ihren Schlüsseltresoren

Wenn Sie Ihre Schlüssel schnell wiederherstellen können, ist ein umfassender Dienstausfalls aufgrund von versehentlich oder in böswilliger Absicht gelöschten Schlüsseln weniger wahrscheinlich. Sie müssen diese Konfiguration, die als „Soft Delete“ (Vorläufiges Löschen) bezeichnet wird, aktivieren, bevor Sie Ihre Schlüssel mit Customer Key verwenden können. Das Aktivieren von Soft Delete ermöglicht Ihnen des Wiederherstellen von Schlüsseln oder Tresoren innerhalb von 90 Tagen nach dem Löschen, ohne diese aus der Datensicherung wiederherstellen zu müssen.
  
Führen Sie die folgenden Schritte aus, um Soft Delete für Ihre Schlüsseltresore zu aktivieren:
  
1. Melden Sie sich mit Windows PowerShell bei Ihrem Azure-Abonnement an. Anweisungen finden Sie unter [Anmelden mit Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).

2. Führen Sie das Cmdlet [Get-AzKeyVault](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) aus. In diesem Beispiel ist *Vault Name* der Name des Schlüssel Tresors, für den Sie Soft Delete aktivieren:

   ```powershell
   $v = Get-AzKeyVault -VaultName <vault name>
   $r = Get-AzResource -ResourceId $v.ResourceId
   $r.Properties | Add-Member -MemberType NoteProperty -Name enableSoftDelete -Value 'True'
   Set-AzResource -ResourceId $r.ResourceId -Properties $r.Properties
   ```

3. Bestätigen Sie, dass Soft Delete für den schlüsseltresor konfiguriert ist, indem Sie das Cmdlet **Get-AzKeyVault** ausführen. Wenn Soft Delete ordnungsgemäß für den schlüsseltresor konfiguriert ist, gibt die _Soft Delete Enabled_ -Eigenschaft den Wert " **true**" zurück:

   ```powershell
   Get-AzKeyVault -VaultName <vault name> | fl
   ```

### <a name="add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key"></a>Hinzufügen eines Schlüssels zu jedem Schlüsseltresor durch das Erstellen oder Importieren eines Schlüssels

Es gibt zwei Methoden zum Hinzufügen von Schlüsseln zu einem Azure Key Vault. Sie können entweder direkt im Schlüsseltresor einen Schlüssel erstellen oder aber einen Schlüssel importieren. Das Erstellen eines Schlüssels direkt im Schlüsseltresor ist die einfachere Methode, während der Import eines Schlüssels die vollständige Kontrolle über die Generierung des Schlüssels bietet.
  
Um einen Schlüssel direkt in Ihrem schlüsseltresor zu erstellen, führen [Sie das Add-AzKeyVaultKey-](https://docs.microsoft.com/powershell/module/az.keyvault/add-azkeyvaultkey) Cmdlet wie folgt aus:
  
```powershell
Add-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Destination <HSM|Software> -KeyOps wrapKey,unwrapKey
```

Dabei gilt:

- *Vault Name* ist der Name des Schlüssel Tresors, in dem Sie den Schlüssel erstellen möchten.

- *Key Name* ist der Name, den Sie dem neuen Schlüssel zuweisen möchten.

  > [!TIP]
  > Benennen Sie Schlüssel, die eine ähnliche Benennungskonvention verwenden, nach dem oben für Schlüsseltresore beschriebenen Verfahren. Auf diese Weise ist die Zeichenfolge in Tools, die lediglich den Schlüsselnamen anzeigen, selbsterklärend.
  
- Wenn Sie den Schlüssel mit einem HSM schützen möchten, stellen Sie sicher, dass Sie **HSM** als Wert des Parameters _Destination_ angeben, andernfalls geben Sie **Software**an.

Beispiele:
  
```powershell
Add-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination Software -KeyOps wrapKey,unwrapKey
```

Wenn Sie einen Schlüssel direkt in ihren Schlüsseltresor importieren möchten, müssen Sie über ein Thales-nShield-Hardware-Sicherheitsmodul verfügen.
  
Einige Organisationen bevorzugen diese Vorgehensweise, um die Herkunft Ihrer Schlüssel festzulegen. Außerdem bietet diese Methode folgendes Features:
  
- Der für den Import verwendete Werkzeugsatz umfasst die Beglaubigung von Thales, dass der Schlüsselaustauschschlüssel (KEK), der zum Verschlüsseln des von Ihnen generierten Schlüssels verwendet wird, nicht exportierbar ist und in einem echten HSM generiert wird, das von Thales hergestellt wurde.

- Das Toolset umfasst die Bestätigung von Thales, dass die Azure Key Vault Security-Welt auch auf einem echten HSM von Thales generiert wurde. Diese Bescheinigung dient für Sie als Nachweis, dass Microsoft ebenfalls Original-Thales-Hardware verwendet.

Wenden Sie sich an Ihr Sicherheitsteam, um festzustellen, ob die vorstehenden Bescheinigungen erforderlich sind. Detaillierte Anweisungen zum Erstellen eines lokalen Schlüssels und zum Importieren in Ihren Schlüsseltresor finden Sie unter [Generieren und Übertragen von HSM-geschützten Schlüsseln für Azure Key Vault](https://azure.microsoft.com/documentation/articles/key-vault-hsm-protected-keys/). Folgen Sie den Azure-Anweisungen, um in jedem Schlüsseltresor einen Schlüssel zu erstellen.
  
### <a name="check-the-recovery-level-of-your-keys"></a>Überprüfen der Wiederherstellungsebene Ihrer Schlüssel

Microsoft 365 erfordert, dass das Azure Key Vault-Abonnement auf nicht abbrechen festgelegt ist und dass für die Schlüssel, die von Kunden Schlüsseln verwendet werden, Soft Delete aktiviert ist. Sie können dies sicherstellen, indem Sie die Wiederherstellungsstufe für Ihre Schlüssel überprüfen.
  
Um die Wiederherstellungsebene eines Schlüssels zu überprüfen, führen Sie in Azure PowerShell das Cmdlet Get-AzKeyVaultKey wie folgt aus:
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes
```

Wenn die _Wiederherstellungsebene_ einen anderen Wert als "wieder **herstellbare + ProtectedSubscription**" zurückgibt, müssen Sie dieses Thema durchlesen und sicherstellen, dass Sie alle Schritte zum Platzieren des Abonnements in der Liste "nicht abbrechen" und "Soft Delete" für jeden schlüsseltresor aktiviert haben.
  
### <a name="back-up-azure-key-vault"></a>Sichern von Azure Key Vault

Unmittelbar nach dem Erstellen oder Ändern eines Schlüssels, dem Durchführen einer Sicherung und dem Speichern von Kopien der Sicherung, sowohl online als auch offline. Offline-Kopien sollten nicht mit einem Netzwerk verbunden sein, d. h. beispielsweise nicht in einem Safe oder in einem gewerblichen Lager aufbewahrt werden. Mindestens eine Kopie der Sicherung sollte an einem Standort gespeichert werden, auf den Sie im Notfall zugreifen können. Die einzelnen Sicherungen sind die einzige Möglichkeit zum Wiederherstellen des Schlüsselmaterials, sollte ein Key-Vault-Schlüssel dauerhaft vernichtet oder auf andere Weise funktionsuntüchtig gemacht worden sein. Schlüssel, die sich außerhalb des Azure Key Vault befinden und in Azure Key Vault importiert wurden, sind als Sicherung nicht geeignet, da die Metadaten, die für die Verwendung des Schlüssels mit Customer Key erforderlich sind, mit dem externen Schlüssel nicht vorhanden sind. Nur eine vom Azure Key Vault erstellte Sicherung kann für Wiederherstellungsvorgänge mit Customer Key verwendet werden. Deshalb ist die Sicherung des Azure Key Vault, sobald ein Schlüssel hochgeladen oder erstellt wurde, von wesentlicher Bedeutung.
  
Um eine Sicherung eines Azure Key-Tresor Schlüssels zu erstellen, führen Sie das Cmdlet [Backup-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/backup-azkeyvaultkey) wie folgt aus:

```powershell
Backup-AzKeyVaultKey -VaultName <vault name> -Name <key name>
-OutputFile <filename.backup>
```

Stellen Sie sicher, dass Ihre Ausgabedatei `.backup`das Suffix verwendet.
  
Die aus diesem Cmdlet resultierende Ausgabedatei ist verschlüsselt und kann außerhalb von Azure Key Vault nicht verwendet werden. Die Sicherung kann nur für das Azure-Abonnement wiederhergestellt werden, aus dem die Sicherung erstellt wurde.
  
> [!TIP]
> Wählen Sie für die Ausgabedatei eine Kombination aus Ihrem Tresor- und Schlüsselnamen. Dadurch wird der Dateiname selbsterklärend. Außerdem wird sichergestellt, dass die Namen der Sicherungsdateien nicht kollidieren.
  
Beispiel:
  
```powershell
Backup-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -OutputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

### <a name="validate-azure-key-vault-configuration-settings"></a>Konfigurationseinstellungen von Azure Key Vault verifizieren

Das Durchführen der Überprüfung vor der Verwendung von Schlüsseln in einer Datenverschlüsselungsrichtlinie (DEP) ist optional, wird jedoch dringend empfohlen. Insbesondere, wenn Sie andere als die in diesem Artikel beschriebenen Schritte zum Einrichten Ihrer Schlüssel und Tresore verwenden, sollten Sie den Sicherheitsstatus Ihrer Azure Key Vault-Ressourcen überprüfen, bevor Sie Customer Key konfigurieren.
  
Überprüfen, ob für Ihre Schlüssel die Funktionen „Abrufen“, „WrapKey“ und „unWrapKey“ aktiviert sind:
  
Führen Sie das Cmdlet [Get-AzKeyVault](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) wie folgt aus:
  
```powershell
Get-AzKeyVault -VaultName <vault name>
```

Suchen Sie in der Ausgabe nach der Zugriffsrichtlinie und, je nach Bedarf, nach der Exchange Online-Identität (GUID) bzw. der SharePoint Online Identity (GUID). Alle drei vorstehenden Berechtigungen müssen unter den Berechtigungen für Schlüssel angezeigt werden.
  
Wenn die Konfiguration der Zugriffsrichtlinie falsch ist, führen Sie das Cmdlet "AzKeyVaultAccessPolicy" wie folgt aus:
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
```

Beispielsweise für Exchange Online und Skype for Business:
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
```

Beispielsweise für SharePoint Online und OneDrive for Business:
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName TBD
```

Um zu überprüfen, ob für Ihre Schlüssel ein Ablaufdatum festgelegt wurde, führen Sie das Cmdlet [Get-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) wie folgt aus:
  
```powershell
Get-AzKeyVaultKey -VaultName <vault name>
```

Ein abgelaufener Schlüssel kann von Customer Key nicht verwendet werden, und Vorgänge, die mit einem abgelaufenen Schlüssel versucht werden, werden nicht ausgeführt und führen möglicherweise zu einem Dienstausfall. Es wird dringend empfohlen, dass mit Customer Key verwendete Schlüssel kein Ablaufdatum aufweisen. Ein einmal festgelegtes Ablaufdatum kann nicht gelöscht werden, es kann jedoch eine Datumänderung vorgenommen werden. Wenn ein Schlüssel verwendet werden muss, für den ein Ablaufdatum festgelegt ist, ändern Sie bitte das Ablaufdatum auf 31.12.9999. Schlüssel mit einem Ablaufdatum, das auf ein anderes Datum als 12/31/9999 festgelegt ist, werden nicht von der Microsoft 365-Validierung übergeben.
  
Um ein Ablaufdatum zu ändern, das auf einen anderen Wert als 12/31/9999 festgelegt wurde, führen Sie das Cmdlet [Update-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/update-azkeyvaultkey) wie folgt aus:
  
```powershell
Update-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Expires (Get-Date -Date "12/31/9999")
```

> [!CAUTION]
> Legen Sie keine Ablaufdaten für kryptografische Schlüssel fest, die Sie mit Customer Key verwenden.
  
### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a>Abrufen eines URI für jeden Azure Key Vault-Schlüssel

Nachdem Sie alle Schritte in Azure abgeschlossen haben, um die Schlüsseldepots einzurichten und die Schlüssel hinzugefügt haben, führen Sie den folgenden Befehl aus, um den URI für den Schlüssel in jedem schlüsseltresor abzurufen. Sie müssen diese URI verwenden, wenn Sie in weiterer Folge die einzelnen Datenverschlüsselungsrichtlinien (DEP) erstellen und zuweisen, also speichern Sie diese Informationen an einem sicheren Ort. Denken Sie daran, diesen Befehl jeweils für jeden Schlüsseltresor einmal auszuführen.
  
In Azure PowerShell:
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name>).Id
```

## <a name="office-365-setting-up-customer-key-for-exchange-online-and-skype-for-business"></a>Office 365: Einrichten von Customer Key für Exchange Online und Skype for Business

Bevor Sie beginnen, stellen Sie sicher, dass Sie die zum Einrichten von Azure Key Vault erforderlichen Aufgaben abgeschlossen haben. Informationen hierzu finden Sie unter [Erledigen von Aufgaben in Azure Key Vault und Microsoft FastTrack für Customer Key](#complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key).
  
Um Customer Key für Exchange Online und Skype for Business einzurichten, müssen Sie diese Schritte ausführen, indem Sie mittels Windows PowerShell eine Remoteverbindung mit Exchange Online herstellen.
  
### <a name="create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business"></a>Erstellen einer Datenverschlüsselungsrichtlinie (DEP) zur Nutzung mit Exchange Online und Skype for Business

Eine Datenverschlüsselungsrichtlinie (DEP) ist mit einer Reihe von im Azure Key Vault gespeicherten Schlüsseln verknüpft. Sie weisen einer Datenausführungsverhinderung einem Postfach in Microsoft 365 zu. Microsoft 365 verwendet dann die Schlüssel, die in der Richtlinie zum Verschlüsseln des Postfachs angegeben sind. Zum Erstellen der Datenverschlüsselungsrichtlinie (DEP) benötigen Sie die Key Vault-URI, die Sie zuvor erhalten haben. Anweisungen hierzu finden Sie unter [Abrufen eines URI für jeden Azure Key Vault-Schlüssel](#obtain-the-uri-for-each-azure-key-vault-key).
  
Nicht vergessen! Beim Erstellen einer Datenverschlüsselungsrichtlinie (DEP) geben Sie zwei Schlüssel an, die sich in zwei verschiedenen Azure Key Vaults befinden. Stellen Sie sicher, dass sich diese Schlüssel in zwei unterschiedlichen Azure-Regionen befinden, um Geo-Redundanz sicherzustellen.
  
Um eine Datenverschlüsselungsrichtlinie (DEP) zu erstellen, führen Sie bitte folgende Schritte aus:
  
1. Stellen Sie auf Ihrem lokalen Computer mithilfe eines Arbeits-oder Schul Kontos, das über globale Administratorberechtigungen in Ihrer Organisation verfügt, [eine Verbindung mit Exchange Online PowerShell her](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps) , indem Sie Windows PowerShell öffnen und den folgenden Befehl ausführen.

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
   New-DataEncryptionPolicy -Name <PolicyName> -Description "Policy Description" -AzureKeyIDs <KeyVaultURI1>, <KeyVaultURI2>
   ```

   Dabei gilt:

   - *PolicyName* ist der Name, den Sie für die Richtlinie verwenden möchten. Namen dürfen keine Leerzeichen enthalten. Beispiel: USA_Postfächer.

   - *Richtlinienbeschreibung* ist eine benutzerfreundliche Beschreibung der Richtlinie, mit der Sie sich daran erinnern können, wofür die Richtlinie verwendet wird. In der Beschreibung sind Leerzeichen erlaubt. Beispiel: "Stammschlüssel für Postfächer in USA und seinen Territorien".

   - *KeyVaultURI1* ist der URI für den ersten Schlüssel in der Richtlinie. Beispiel: https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01.

   - *KeyVaultURI2* ist der URI für den zweiten Schlüssel in der Richtlinie. Beispiel: https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02. Trennen Sie die beiden URI mittels Komma und Leerzeichen.

   Beispiel:
  
   ```powershell
   New-DataEncryptionPolicy -Name USA_mailboxes -Description "Root key for mailboxes in USA and its territories" -AzureKeyIDs https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01, https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02
   ```

### <a name="assign-a-dep-to-a-mailbox"></a>Zuweisen einer Datenverschlüsselungsrichtlinie (DEP) zu einem Postfach

Zuweisen der Datenverschlüsselungsrichtlinie (DEP) zu einem Postfach mithilfe des Cmdlets „Set-Mailbox“. Nachdem Sie die Richtlinie zugewiesen haben, kann Microsoft 365 das Postfach mit dem in der DEP festgelegten Schlüssel verschlüsseln.
  
```powershell
Set-Mailbox -Identity <MailboxIdParameter> -DataEncryptionPolicy <PolicyName>
```

Dabei legt der *MailboxIdParameter* ein Postfach fest. Weitere Informationen zum Cmdlet „Set-Mailbox“ finden Sie unter [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox?view=exchange-ps).
  
### <a name="validate-mailbox-encryption"></a>Überprüfen einer Postfachverschlüsselung

Das Verschlüsseln eines Postfachs kann einige Zeit in Anspruch nehmen. Bei der erstmaligen Richtlinienzuweisung muss das Postfach auch vollständig von einer Datenbank zu einer anderen verschoben werden, bevor der Dienst das Postfach verschlüsseln kann. Wir empfehlen, dass Sie 72 Stunden warten, bevor Sie versuchen, die Verschlüsselung nach dem Ändern einer Datenverschlüsselungsrichtlinie (DEP) oder nach dem erstmaligen Zuweisen einer Datenverschlüsselungsrichtlinie (DEP) zu einem Postfach zu überprüfen.
  
Verwenden Sie das Cmdlet „Get-MailboxStatistics“, um festzustellen, ob ein Postfach verschlüsselt ist.
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

Die IsEncrypted-Eigenschaft meldet den Wert **True** (Richtig), wenn das Postfach verschlüsselt ist, und den Wert **False** (Falsch), wenn das Postfach nicht verschlüsselt ist.

Der Zeitaufwand für das Durchführen von Postfachverschiebungen hängt von der Anzahl der Postfächer ab, denen Sie zum ersten Mal eine Datenverschlüsselungsrichtlinie (DEP) zuweisen, sowie von der Größe der Postfächer. Wenn die Postfächer nach einer Woche ab dem Zeitpunkt, zu dem Sie die Datenausführungsverhinderung zugewiesen haben, nicht verschlüsselt wurden, wenden Sie sich an Microsoft.

## <a name="office-365-setting-up-customer-key-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>Office 365: Einrichten des Kunden Schlüssels für SharePoint Online-, OneDrive für Unternehmen-und Microsoft Teams-Dateien

Bevor Sie beginnen, stellen Sie sicher, dass Sie die zum Einrichten von Azure Key Vault erforderlichen Aufgaben abgeschlossen haben. Informationen hierzu finden Sie unter [Erledigen von Aufgaben in Azure Key Vault und Microsoft FastTrack für Customer Key](#complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key).
  
Um den Kundenschlüssel für SharePoint Online-, OneDrive für Unternehmen-und Microsoft Teams-Dateien einzurichten, müssen Sie diese Schritte durch eine Remoteverbindung mit SharePoint Online mit Windows PowerShell ausführen.
  
### <a name="create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo"></a>Erstellen einer Datenverschlüsselungsrichtlinie (DEP) für jede SharePoint Online- und OneDrive for Business-Geo

Sie ordnen eine DEP einer Gruppe von Schlüsseln zu, die in Azure Key Vault gespeichert sind. Sie wenden eine Datenverschlüsselungsrichtlinie (DEP) auf alle Ihre Daten an einem geografischen Standort an, der auch als Geo bezeichnet wird. Wenn Sie das Multi-Geo-Feature von Office 365 verwenden, können Sie eine Datenausführungsverhinderung pro Geo erstellen, mit der Möglichkeit, verschiedene Schlüssel pro Geo zu verwenden. Wenn Sie keine Multi-Geo-Daten verwenden, können Sie eine DEP in Ihrer Organisation für die Verwendung mit SharePoint Online-, OneDrive für Unternehmen-und Microsoft Teams-Dateien erstellen. Microsoft 365 verwendet die in der DEP identifizierten Schlüssel, um Ihre Daten in diesem Geo zu verschlüsseln. Zum Erstellen der Datenverschlüsselungsrichtlinie (DEP) benötigen Sie die Key Vault-URI, die Sie zuvor erhalten haben. Anweisungen hierzu finden Sie unter [Abrufen eines URI für jeden Azure Key Vault-Schlüssel](#obtain-the-uri-for-each-azure-key-vault-key).
  
Nicht vergessen! Beim Erstellen einer Datenverschlüsselungsrichtlinie (DEP) geben Sie zwei Schlüssel an, die sich in zwei verschiedenen Azure Key Vaults befinden. Stellen Sie sicher, dass sich diese Schlüssel in zwei unterschiedlichen Azure-Regionen befinden, um Geo-Redundanz sicherzustellen.
  
Um eine Datenverschlüsselungsrichtlinie (DEP) zu erstellen, müssen Sie mithilfe von Windows PowerShell eine Remote-Verbindung zu SharePoint Online herstellen.
  
1. Stellen Sie auf Ihrem lokalen Computer mithilfe eines Arbeits-oder Schul Kontos, das über globale Administratorberechtigungen in Ihrer Organisation verfügt, [eine Verbindung mit SharePoint Online PowerShell her](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).

2. Führen Sie in der Microsoft SharePoint Online Management-Shell das Cmdlet Register-SPODataEncryptionPolicy wie folgt durch:

   ```powershell
   Register-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -PrimaryKeyVaultName <PrimaryKeyVaultName> -PrimaryKeyName <PrimaryKeyName> -PrimaryKeyVersion <PrimaryKeyVersion> -SecondaryKeyVaultName <SecondaryKeyVaultName> -SecondaryKeyName <SecondaryKeyName> -SecondaryKeyVersion <SecondaryKeyVersion>
   ```

   Sobald Sie die Datenverschlüsselungsrichtlinie (DEP) registrieren, beginnt die Verschlüsselung der Daten im Geo. Dies kann einige Zeit dauern.

### <a name="validate-file-encryption"></a>Überprüfen der Dateiverschlüsselung

 Um die Verschlüsselung von SharePoint Online-, OneDrive für Unternehmen-und Microsoft Teams-Dateien zu überprüfen, stellen Sie [eine Verbindung mit SharePoint Online PowerShell her](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps), und verwenden Sie dann das Cmdlet Get-SPODataEncryptionPolicy, um den Status Ihres Mandanten zu überprüfen. Die _State_ -Eigenschaft gibt den Wert **registriert** zurück, wenn die Verschlüsselung von Kunden Schlüsseln aktiviert ist und alle Dateien an allen Standorten verschlüsselt wurden. Wenn die Verschlüsselung noch ausgeführt wird, bietet dieses Cmdlet Informationen darüber, welcher Prozentsatz der Websites abgeschlossen ist.

## <a name="related-articles"></a>Verwandte Artikel

- [Dienst Verschlüsselung mit Kundenschlüssel](customer-key-overview.md)

- [Verwalten des Kunden Schlüssels](customer-key-manage.md)

- [Rollen oder Drehen eines Kundenschlüssels oder eines Verfügbarkeitsschlüssels](customer-key-availability-key-roll.md)

- [Informationen zum Verfügbarkeits Schlüssel](customer-key-availability-key-understand.md)

- [Dienst Verschlüsselung](office-365-service-encryption.md)
