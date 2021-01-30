---
title: Einrichten des Kundenschlüssels auf Anwendungsebene
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
description: 'Erfahren Sie, wie Sie Customer Key für Microsoft 365 für Exchange Online-, Skype for Business-, SharePoint Online-, OneDrive for Business- und #A0 einrichten.'
ms.openlocfilehash: 057f20005e64a15ef18d076206394159d2690818
ms.sourcegitcommit: 50f10d83fa21db8572adab90784146e5231e3321
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2021
ms.locfileid: "50058478"
---
# <a name="set-up-customer-key-at-the-application-level"></a>Einrichten des Kundenschlüssels auf Anwendungsebene

Mit Customer Key steuern Sie die Verschlüsselungsschlüssel Ihrer Organisation und konfigurieren Dann Microsoft 365 so, dass diese zum Verschlüsseln Ihrer ruhen daten in den Rechenzentren von Microsoft verwendet werden. Mit anderen Worten: Customer Key ermöglicht es Kunden, mit ihren Schlüsseln eine Verschlüsselungsebene hinzuzufügen, die Ihnen gehört. Zu den Daten im Ruhezustand gehören Daten aus Exchange Online und Skype for Business, die in SharePoint Online und OneDrive for Business in Postfächern und Dateien gespeichert sind.

Sie müssen Azure einrichten, bevor Sie Customer Key für Office 365 verwenden können. In diesem Artikel werden die Schritte beschrieben, die Sie ausführen müssen, um die erforderlichen Azure-Ressourcen zu erstellen und zu konfigurieren. Anschließend werden die Schritte zum Einrichten von Customer Key in Office 365 beschrieben. Nachdem Sie das Azure-Setup abgeschlossen haben, legen Sie fest, welche Richtlinie und somit auch, welche Schlüssel den Postfächern und Dateien in Ihrer Organisation zugewiesen werden sollen. Für Postfächer und Dateien, denen Sie keine Richtlinie zuweisen, werden Verschlüsselungsrichtlinien verwendet, die von Microsoft gesteuert und verwaltet werden. Weitere Informationen zu Customer Key oder eine allgemeine Übersicht finden Sie unter [Dienstverschlüsselung mit Customer Key in Office 365](customer-key-overview.md).
  
> [!IMPORTANT]
> Es wird dringend empfohlen, die bewährten Methoden in diesem Artikel zu befolgen. Diese werden sind als **TIPP** und **WICHTIG** bezeichnet. Customer Key ermöglicht Ihnen die Kontrolle über die grundlegenden kryptografischen Schlüssel, deren Geltungsbereich so groß wie Ihre gesamte Organisation sein kann. Dies bedeutet, dass Fehler im Zusammenhang mit diesen Schlüsseln einen großen Einfluss haben und zu Dienstunterbrechungen oder unwiderruflichen Datenverlusten führen können.
  
## <a name="before-you-set-up-customer-key"></a>Vor dem Einrichten von Customer Key

Bevor Sie beginnen, stellen Sie sicher, dass Sie über die entsprechende Lizenzierung für Ihre Organisation verfügen. Verwenden Sie ein kostenpflichtiges, in Rechnung gestelltes Azure-Abonnement, indem Sie Konzernvertrag oder einen Clouddienstanbieter verwenden. Azure Subscriptions purchased using Pay As You Go plans or using a credit card aren't supported for Customer Key. Ab dem 1. April 2020 wird Customer Key in Office 365 in Office 365 E5, M365 E5, M365 E5 Compliance und M365 E5 Information Protection & Governance SKUs angeboten. Office 365 Advanced Compliance SKU ist nicht mehr für die Beschaffung neuer Lizenzen verfügbar. Vorhandene Office 365 Advanced Compliance-Lizenzen werden weiterhin unterstützt.

Informationen zu den Konzepten und Verfahren in diesem Artikel finden Sie in der [Azure Key Vault-Dokumentation.](https://docs.microsoft.com/azure/key-vault/) Machen Sie sich außerdem mit den in Azure verwendeten Begriffen vertraut, z. B. [Azure AD-Mandant.](https://docs.microsoft.com/previous-versions/azure/azure-services/jj573650(v=azure.100)#what-is-an-azure-ad-tenant)

FastTrack wird nur verwendet, um die erforderlichen Mandanten- und Dienstkonfigurationsinformationen zu erfassen, die für die Registrierung für Customer Key verwendet werden. Die Kundenschlüsselangebote werden über FastTrack veröffentlicht, sodass es für Sie und unsere Partner praktisch ist, die erforderlichen Informationen mithilfe derselben Methode zu übermitteln. FastTrack erleichtert auch das Archivieren der Daten, die Sie im Angebot bereitstellen.
  
Wenn Sie über die Dokumentation hinaus weiteren Support benötigen, wenden Sie sich an Microsoft Consulting Services (MCS), Premier Field Engineering (PFE) oder einen Microsoft-Partner, um Unterstützung zu erhalten. Um Feedback zu Customer Key, einschließlich der Dokumentation, zu geben, senden Sie Ihre Ideen, Vorschläge und Perspektiven an customerkeyfeedback@microsoft.com.
  
## <a name="overview-of-steps-to-set-up-customer-key"></a>Übersicht über die Schritte zum Einrichten von Customer Key

Führen Sie zum Einrichten von Customer Key diese Aufgaben in der angegebenen Bestellung aus. Der Rest dieses Artikels enthält ausführliche Anweisungen für jede Aufgabe oder links zu weiteren Informationen zu jedem Schritt des Prozesses.
  
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

- [Überprüfen der Dateiverschlüsselung für SharePoint Online-, OneDrive for Business- und #A0](#validate-file-encryption)

## <a name="complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key"></a>Erledigen von Aufgaben in Azure Key Vault und Microsoft FastTrack für Customer Key

Führen Sie diese Aufgaben in Azure Key Vault aus. Sie müssen diese Schritte unabhängig davon ausführen, ob Sie Customer Key für Exchange Online und Skype for Business oder für SharePoint Online-, OneDrive for Business- und #A0 oder für alle unterstützten Dienste in Office 365 einrichten möchten.
  
### <a name="create-two-new-azure-subscriptions"></a>Zwei neue Azure-Abonnements erstellen

Customer Key erfordert zwei Azure-Abonnements. Als bewährte Methode empfiehlt Microsoft, neue Azure-Abonnements für die Verwendung mit Customer Key zu erstellen. Azure Key Vault-Schlüssel können nur für Anwendungen im selben Azure Active Directory (Microsoft Azure Active Directory)-Mandanten autorisiert werden. Sie müssen die neuen Abonnements mit demselben Azure AD-Mandanten erstellen, der mit Ihrer Organisation verwendet wird, in dem die DEPs zugewiesen werden. Verwenden Sie beispielsweise Ihr Arbeits- oder Schulkonto, das über globale Administratorrechte in Ihrer Organisation verfügt. Weitere Informationen zu den einzelnen Arbeitsschritten finden Sie unter [Als Unternehmen für Azure registrieren](https://azure.microsoft.com/documentation/articles/sign-up-organization/).
  
> [!IMPORTANT]
> Für Customer Key sind zwei Schlüssel für jede Daten- Verschlüsselungsrichtlinie (DEP) erforderlich. Zu diesem Zweck müssen Sie zwei Azure-Abonnements erstellen. Als bewährte Methode empfiehlt Microsoft, dass separate Mitglieder Ihrer Organisation jeweils einen Schlüssel für jedes Abonnement konfigurieren. Sie sollten diese Azure-Abonnements nur zum Verwalten von Verschlüsselungsschlüsseln für Office 365 verwenden. Auf diese Weise ist Ihre Organisation geschützt, falls einer ihrer Betreiber versehentlich, absichtlich oder in böswilliger Absicht die Schlüssel, für die Sie verantwortlich sind, löscht oder auf andere Weise unsachgemäß handhabt.
>

Es gibt praktisch keine Beschränkung hinsichtlich der Anzahl von Azure-Abonnements, die Sie für Ihre Organisation erstellen können. Durch die Nutzung dieser bewährten Methoden können Sie die Auswirkungen von menschlichen Fehlern bei der Verwaltung der von Customer Key genutzten Ressourcen minimieren.
  
### <a name="submit-a-request-to-activate-customer-key-for-office-365"></a>Senden einer Anforderung zum Aktivieren von Customer Key für Office 365

Sobald Sie die Azure-Schritte abgeschlossen haben, müssen Sie im [Microsoft FastTrack-Portal](https://fasttrack.microsoft.com/) eine Angebotsanfrage übermitteln. Nachdem Sie eine Anforderung über das FastTrack-Webportal übermittelt haben, überprüft Microsoft die Azure Key Vault-Konfigurationsdaten und Kontaktinformationen, die Sie bereitgestellt haben. Die Auswahl, die Sie im Angebotsformular über die autorisierten Mitarbeiter Ihrer Organisation treffen, ist wichtig und für den Abschluss der Registrierung des Kundenschlüssels erforderlich. Die Mitarbeiter Ihrer Organisation stellen die Echtheit aller Anforderungen zum Widerrufen und Zerstören aller Schlüssel sicher, die mit einer Datenverschlüsselungsrichtlinie für Kundenschlüssel verwendet werden. Sie müssen diesen Schritt einmal ausführen, um Customer Key für Exchange Online und Skype for Business zu aktivieren, und ein zweites Mal, um Customer Key für SharePoint Online und OneDrive for Business zu aktivieren.
  
Führen Sie zur Übermittlung eines Angebots zum Aktivieren von Customer Key die folgenden Schritte aus:
  
1. Melden Sie sich mit einem Arbeits- oder Schulkonto, das über globale Administratorberechtigungen in Ihrer Organisation verfügt, beim [Microsoft FastTrack-Portal an.](https://fasttrack.microsoft.com/)

2. Sobald Sie angemeldet sind, wechseln Sie zum **Dashboard**.

3. Wählen **Sie "Bereitstellen"** in der Navigationsleiste **oder** **"Alle** Bereitstellungsressourcen auf der Informationskarte bereitstellen" aus, und überprüfen Sie die Liste der aktuellen Angebote. 

4. Wählen Sie die Informationskarte für das Angebot aus, das für Sie gilt:

   - **Exchange Online und Skype for Business:** Wählen Sie die **Hilfe zum Anfordern des Verschlüsselungsschlüssels für das Exchange-Onlineangebot** aus.

   - **SharePoint Online-, OneDrive- und Teams-Dateien:** Wählen Sie die **Hilfe zum Anfordern des Verschlüsselungsschlüssels für Sharepoint und OneDrive** aus.

5. Nachdem Sie die Angebotsdetails überprüft haben, wählen Sie **"Weiter zu Schritt 2" aus.**

6. Tragen Sie alle relevanten Details und erforderlichen Informationen im Angebotsformular ein. Achten Sie besonders auf Ihre Auswahl, welche MitarbeiterInnen Ihrer Organisation Sie autorisieren, die permanente und unwiderrufliche Vernichtung von kryptografischen Schlüsseln und Daten zu genehmigen. Sobald Sie das Formular ausgefüllt haben, wählen Sie **Senden**.

### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a>Azure- Abonnements registrieren, um einen obligatorischen Aufbewahrungszeitraum zu nutzen.

Der vorübergehende oder dauerhafte Verlust von Stammverschlüsselungsschlüsseln kann störend oder sogar katastrophal für den Dienstbetrieb sein und zu Datenverlusten führen. Aus diesem Grund ist für die mit Customer Key verwendeten Ressourcen ein starker Schutz erforderlich. Alle Azure-Ressourcen, die mit Customer Key verwendet werden, bieten Schutzmechanismen, die weit über die Standardkonfiguration hinaus gehen. Sie können Azure-Abonnements für einen obligatorischen *Aufbewahrungszeitraum kennzeichnen oder registrieren.* Ein obligatorischer Aufbewahrungszeitraum verhindert die sofortige und unwiderrufliche Kündigung Ihres Azure-Abonnements. Die erforderlichen Schritte zum Registrieren von Azure-Abonnements für einen obligatorischen Aufbewahrungszeitraum erfordern die Zusammenarbeit mit dem Microsoft 365-Team. Die Registrierung kann ab einen bis fünf Arbeitstage dauern. Früher wurde der obligatorische Aufbewahrungszeitraum manchmal als "Nicht abbrechen" bezeichnet.
  
Bevor Sie das Microsoft 365-Team kontaktieren, müssen Sie die folgenden Schritte für jedes Azure-Abonnement ausführen, das Sie mit Customer Key verwenden. Stellen Sie sicher, dass Sie das [Azure PowerShell Az-Modul](https://docs.microsoft.com/powershell/azure/new-azureps-module-az) installiert haben, bevor Sie beginnen.
  
1. Melden Sie sich mit Azure PowerShell an. Anweisungen finden Sie unter ["Anmelden mit Azure PowerShell".](https://docs.microsoft.com/powershell/azure/authenticate-azureps)

2. Führen Sie Register-AzProviderFeature Cmdlet aus, um Ihre Abonnements für die Verwendung eines obligatorischen Aufbewahrungszeitraums zu registrieren. Führen Sie diese Aktion für jedes Abonnement aus.

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.Resources
   ```

3. Wenden Sie sich an Microsoft, um den Vorgang abschließen zu können. Um mit dem SharePoint- und OneDrive for Business-Team in Verbindung zu treten, wenden Sie sich bitte an [spock@microsoft.com](mailto:spock@microsoft.com). Für Exchange Online und Skype for Business wenden Sie sich bitte an [exock@microsoft.com](mailto:exock@microsoft.com). Fügen Sie die folgenden Informationen in Ihre E-Mail ein:

   **Betreff:** Kundenschlüssel für \<*Your tenant's fully qualified domain name*\>

   **Text:** Schließen Sie die Abonnement-IDs ein, für die Sie den obligatorischen Aufbewahrungszeitraum abschließen möchten, und die Ausgabe Get-AzProviderFeature Abonnement.

   Die Service-Level-Vereinbarung (Service Level Agreement, SLA) für den Abschluss dieses Vorgangs beläuft sich auf fünf Werktage, nachdem Microsoft benachrichtigt wurde (und überprüft hat, dass Sie Ihre Abonnements für die Nutzung eines obligatorischen Aufbewahrungszeitraums registriert haben).

4. Sobald Sie von Microsoft benachrichtigt werden, dass die Registrierung abgeschlossen ist, überprüfen Sie den Status Ihrer Registrierung, indem Sie den Get-AzProviderFeature wie folgt ausführen. Bei Überprüfung gibt der Get-AzProviderFeature den Wert **"Registered" für** die **Eigenschaft "Registration State"** zurück. Führen Sie diesen Schritt für jedes Abonnement aus.

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Get-AzProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
   ```

5. Führen Sie zum Abschließen des Vorgangs den befehl Register-AzResourceProvider aus. Führen Sie diesen Schritt für jedes Abonnement aus.

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzResourceProvider -ProviderNamespace Microsoft.KeyVault
   ```

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a>Erstellen eines Premium Azure Key Vault für jedes Abonnement

Die Schritte zum Erstellen eines Schlüssel Tresors sind in ["erste Schritte mit Azure Key Vault"](https://azure.microsoft.com/documentation/articles/key-vault-get-started/)dokumentiert, das Sie durch das Installieren und Ingangsetzen von Azure PowerShell, das Herstellen einer Verbindung mit Ihrem Azure-Abonnement, das Erstellen einer Ressourcengruppe und das Erstellen eines Schlüsseltresors in dieser Ressourcengruppe führt.
  
Wenn Sie einen Schlüsseltresor erstellen, müssen Sie eine SKU auswählen: entweder Standard oder Premium. Die Standard-SKU ermöglicht den Schutz von Azure Key Vault-Schlüsseln durch Software – es gibt keinen Schlüsselschutz für Das Hardwaresicherheitsmodul (HSM) – und die Premium-SKU ermöglicht die Verwendung von HSMs zum Schutz von Key Vault-Schlüsseln. Customer Key akzeptiert Schlüsseltresore mit jeder SKU, wobei Microsoft dringend empfiehlt, nur die Premium-SKU zu verwenden. Die Betriebskosten mit Schlüsseln eines der beiden Typen sind identisch. Der einzige Unterschied bei den Kosten sind die monatlichen Kosten für jeden HSM-geschützten Schlüsseln. Detailinformationen finden Si unter [Key Vault-Preise](https://azure.microsoft.com/pricing/details/key-vault/).
  
> [!IMPORTANT]
> Verwenden Sie die Premium-SKU-Schlüsseltresore und HSM-geschützten Schlüssel für Produktionsdaten, und verwenden Sie nur standardmäßige SKU-Schlüsseltresore und Schlüssel für Tests und Überprüfungen.
  
Erstellen Sie für jeden Microsoft 365-Dienst, mit dem Sie Customer Key verwenden, einen Schlüsseltresor in jedem der beiden von Ihnen erstellten Azure-Abonnements. For example, for Exchange Online and Skype for Business only or SharePoint Online and OneDrive for Business only, you'll create only one pair of vaults. Um Customer Key für Exchange Online und SharePoint Online zu aktivieren, erstellen Sie zwei Paar Schlüsseltresore.
  
Verwenden Sie eine Benennungskonvention für Schlüsseltresore, durch welche sich die beabsichtigte Verwendung der Datenverschlüsselungsrichtlinie widerspiegelt, der Sie die Tresore zuordnen möchten. Im nachstehenden Abschnitt „Bewährte Methoden“ finden Sie Empfehlungen zur Benennung.
  
Erstellen Sie für jede Datenverschlüsselungsrichtlinie eine eigene, paarweise angeordnete Tresor-Gruppe. Bei Exchange Online wählen Sie den Geltungsbereich einer Datenverschlüsselungsrichtlinie, wenn Sie die Richtlinie dem Postfach zuweisen. Einem Postfach kann nur eine Richtlinie zugewiesen werden, und Sie können bis zu 50 Richtlinien erstellen. Der Gültigkeitsbereich einer SharePoint Online-Richtlinie umfasst alle Daten innerhalb einer Organisation an einem geografischen Standort oder an einem _geografischen Standort._

Die Erstellung von Key Vaults erfordert auch die Erstellung von Azure-Ressourcengruppen, da Schlüsseltresor Speicherkapazität (wenn auch klein) benötigen und die Key Vault-Protokollierung, falls aktiviert, auch gespeicherte Daten generiert. Als bewährte Methode empfiehlt Microsoft, für die Verwaltung jeder Ressourcengruppe separate Administratoren zu verwenden. Dabei wird die Verwaltung an die Administratorengruppe angepasst, die alle zugehörigen Customer Key-Ressourcen verwaltet.
  
> [!IMPORTANT]
> Um die Verfügbarkeit zu maximieren, sollten sich Ihre Schlüsseltresor in Regionen in der Nähe Ihres Microsoft 365-Diensts befinden. Wenn sich beispielsweise Ihre Exchange Online-Organisation in Nordamerika befindet, sollten Sie Ihre Schlüsseldepots in Nordamerika platzieren. Wenn Ihre Exchange Online-Organisation in Europa ist, sollten Sie Ihre Schlüsseldepots in Europa platzieren.
> 
> Verwenden Sie für die Benennung ein gemeinsames Präfix für Schlüsseltresore sowie eine Abkürzung für die Verwendung und den Umfang des Schlüsseltresors und der Schlüssel (so ist z. B. für den Contoso SharePoint-Dienst, in den sich die Tresore in Nordamerika befinden, ein mögliches Namenspaar „Contoso-O365SP-NV-VaultA1“ und „Contoso-O365SP-NV-VaultA2“. In Azure sind Tresornamen global eindeutige Zeichenfolgen, daher müssen Sie möglicherweise Variationen Ihrer gewünschten Namen ausprobieren, falls die gewünschten Namen bereits von anderen Azure-Kunden beansprucht werden. Ab Juli 2017 können Tresornamen nicht mehr geändert werden, daher empfiehlt es sich, einen schriftlichen Setup-Plan zu erstellen und eine zweite Person zu beauftragen, die überprüft, ob der Plan ordnungsgemäß ausgeführt wird.
> 
> Erstellen Sie Ihre Depots nach Möglichkeit in nicht-gekoppelten Regionen. Gekoppelte Azure-Regionen bieten eine hohe Verfügbarkeit über Dienstausfall-Domänen hinweg. Dementsprechend können regionale Paare gegenseitig als Backup-Region der jeweils anderen betrachtet werden. Dies bedeutet, dass eine Azure-Ressource, die in einer bestimmten Region platziert ist, durch die gekoppelte Region automatisch an Fehlertoleranz gewinnt. Aus diesem Grund bedeutet die Auswahl von Regionen für zwei Tresore, die in einer Datenverschlüsselungsrichtlinie verwendet werden, bei der die Regionen gekoppelt sind, dass nur insgesamt zwei Verfügbarkeitsregionen verwendet werden. In den meisten geografischen Regionen gibt es nur zwei Regionen, weshalb es noch nicht möglich ist, nicht-gekoppelte Regionen auszuwählen. Wählen Sie nach Möglichkeit zwei nicht gekoppelte Regionen für die beiden Tresore aus, die mit einer Datenverschlüsselungsrichtlinie verwendet werden. Dies hat den positiven Effekt, dass insgesamt vier verfügbare Regionen genutzt werden. Weitere Informationen hierzu sowie ein aktuelles Verzeichnis der Regionenpaare finden Sie unter [Geschäftskontinuität und Notfallwiederherstellung (Business continuity and disaster recovery, BCDR): Gekoppelte Regionen in Azure](https://docs.microsoft.com/azure/best-practices-availability-paired-regions).
  
### <a name="assign-permissions-to-each-key-vault"></a>Zuweisen von Berechtigungen für jeden Schlüsseltresor (Key Vault)

Je nach Implementierung müssen Sie drei separate Berechtigungssätze für jeden Schlüsseltresor definieren. Sie müssen beispielsweise eine Berechtigungsgruppe für jede der folgenden Optionen definieren:
  
- **Key Vault-Administratoren,** die ihre Schlüsseltresor täglich für Ihre Organisation verwalten. Zu diesen Aufgaben gehören Datensicherung sowie Erstellen, Abrufen, Importieren, Auflisten und Wiederherstellen.

  > [!IMPORTANT]
  > Die Berechtigungsgruppe, die Schlüsseltresor-Administratoren zugewiesen ist, beinhaltet keine Berechtigung zum Löschen von Schlüsseln. Dies ist beabsichtigt und eine wichtige Vorgehensweise. Kryptografische Schlüssel werden normalerweise nicht gelöscht, da dadurch Daten dauerhaft vernichtet werden. Eine bewährte Methode besteht darin, den Schlüsseltresor-Administratoren diese Berechtigung nicht standardmäßig zuzuweisen. Behalten Sie stattdessen diese Berechtigung den Schlüsseltresor-Mitwirkenden vor und weisen Sie diese einem Administrator nur kurzfristig und lediglich, sofern die damit verbundenen Folgen klar verstanden wurden, zu.
  
  Um diese Berechtigungen einem Benutzer in Ihrer Organisation zuzuordnen, melden Sie sich mit Azure PowerShell bei Ihrem Azure-Abonnement an. Anweisungen finden Sie unter ["Anmelden mit Azure PowerShell".](https://docs.microsoft.com/powershell/azure/authenticate-azureps)

- Führen Sie Set-AzKeyVaultAccessPolicy cmdlet aus, um die erforderlichen Berechtigungen zu erteilen.

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
   ```

   Beispiel:

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
   ```

- **Schlüsseltresor-Mitwirkenden**, die Berechtigungen für den Azure Key Vault selbst ändern können. Sie müssen diese Berechtigungen ändern, wenn Mitarbeiter Ihr Team verlassen oder ihrem Team beitreten. In der seltenen Situation, dass die Schlüsseltresoradministratoren berechtigterweise die Berechtigung zum Löschen oder Wiederherstellen eines Schlüssels benötigen, müssen Sie auch die Berechtigungen ändern. Dieser Gruppe von Schlüsseltresor-Mitwirkenden muss die Rolle **Mitwirkender** für Ihren Schlüsseltresor zugewiesen werden. Sie können diese Rolle mithilfe des Azure-Ressourcenmanagers zuweisen. Informationen zu den einzelnen Schritten finden Sie unter [Verwenden der rollenbasierten Zugriffssteuerung zum Verwalten des Zugriffs auf Ihre Azure-Abonnementressourcen](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure). Der Administrator, der ein Abonnement erstellt, verfügt implizit über diesen Zugriff und kann der Rolle "Mitwirkender" andere Administratoren zuweisen.

- Wenn Sie beabsichtigen, Customer Key mit Exchange Online und Skype for Business zu verwenden, müssen Sie Microsoft 365 die Berechtigung erteilen, den Schlüsseltresor im Auftrag von Exchange Online und Skype for Business zu verwenden. Ebenso müssen Sie, wenn Sie Customer Key mit SharePoint Online und OneDrive for Business verwenden möchten, die Berechtigung für Microsoft 365 hinzufügen, um den Schlüsseltresor im Auftrag von SharePoint Online und OneDrive for Business zu verwenden. Führen Sie das Cmdlet **"Set-AzKeyVaultAccessPolicy"** mit der folgenden Syntax aus, um Microsoft 365 die Berechtigung zu erteilen:

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
   ```

   Dabei gilt Folgendes:

    - *Der Name des* Tresors ist der Name des Schlüsseltresor, den Sie erstellt haben.

    - Für Exchange Online und Skype for Business ersetzen Sie bitte die *Office 365 App-ID* durch `00000002-0000-0ff1-ce00-000000000000`

    - Ersetzen Sie für SharePoint Online-, OneDrive for Business- und #A0  *Office 365 appID* durch `00000003-0000-0ff1-ce00-000000000000`

  Beispiel: Festlegen von Berechtigungen für Exchange Online und Skype for Business:

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
   ```

  Beispiel: Festlegen von Berechtigungen für SharePoint Online-, OneDrive for Business- und Teams-Dateien:

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
   ```

### <a name="enable-and-then-confirm-soft-delete-on-your-key-vaults"></a>Aktivieren und Bestätigen des vorläufigen Löschens in Ihren Schlüsseltresoren

Wenn Sie Ihre Schlüssel schnell wiederherstellen können, ist ein umfassender Dienstausfalls aufgrund von versehentlich oder in böswilliger Absicht gelöschten Schlüsseln weniger wahrscheinlich. Sie müssen diese Konfiguration, die als „Soft Delete“ (Vorläufiges Löschen) bezeichnet wird, aktivieren, bevor Sie Ihre Schlüssel mit Customer Key verwenden können. Das Aktivieren von Soft Delete ermöglicht Ihnen des Wiederherstellen von Schlüsseln oder Tresoren innerhalb von 90 Tagen nach dem Löschen, ohne diese aus der Datensicherung wiederherstellen zu müssen.
  
Führen Sie die folgenden Schritte aus, um Soft Delete für Ihre Schlüsseltresore zu aktivieren:
  
1. Melden Sie sich bei Ihrem Azure-Abonnement mit Windows PowerShell. Anweisungen finden Sie unter ["Anmelden mit Azure PowerShell".](https://docs.microsoft.com/powershell/azure/authenticate-azureps)

2. Führen Sie [das Cmdlet "Get-AzKeyVault"](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) aus. In diesem Beispiel ist *der Name des* Tresors der Name des Schlüsseltresor, für den Sie soft delete aktivieren:

   ```powershell
   $v = Get-AzKeyVault -VaultName <vault name>
   $r = Get-AzResource -ResourceId $v.ResourceId
   $r.Properties | Add-Member -MemberType NoteProperty -Name enableSoftDelete -Value 'True'
   Set-AzResource -ResourceId $r.ResourceId -Properties $r.Properties
   ```

3. Bestätigen Sie, dass soft delete für den Schlüsseltresor konfiguriert ist, indem Sie das **Cmdlet "Get-AzKeyVault"** ausführen. Wenn soft delete ordnungsgemäß für den Schlüsseltresor konfiguriert ist, gibt die _Eigenschaft Soft Delete Enabled_ den Wert True **zurück:**

   ```powershell
   Get-AzKeyVault -VaultName <vault name> | fl
   ```

### <a name="add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key"></a>Hinzufügen eines Schlüssels zu jedem Schlüsseltresor durch das Erstellen oder Importieren eines Schlüssels

Es gibt zwei Methoden zum Hinzufügen von Schlüsseln zu einem Azure Key Vault. Sie können entweder direkt im Schlüsseltresor einen Schlüssel erstellen oder aber einen Schlüssel importieren. Das Erstellen eines Schlüssels direkt im Schlüsseltresor ist die einfachere Methode, während der Import eines Schlüssels die vollständige Kontrolle über die Generierung des Schlüssels bietet. Verwenden Sie die RSA-Schlüssel. Azure Key Vault unterstützt das Umbrechen und Entwrapping mit ellipsenlinientasten nicht.
  
Führen Sie das Cmdlet ["Add-AzKeyVaultKey"](https://docs.microsoft.com/powershell/module/az.keyvault/add-azkeyvaultkey) wie folgt aus, um einen Schlüssel direkt in Ihrem Schlüsseltresor zu erstellen:
  
```powershell
Add-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Destination <HSM|Software> -KeyOps wrapKey,unwrapKey
```

Dabei gilt Folgendes:

- *Der Name des* Tresors ist der Name des Schlüsseltresor, in dem Sie den Schlüssel erstellen möchten.

- *Schlüsselname* ist der Name, den Sie dem neuen Schlüssel geben möchten.

  > [!TIP]
  > Benennen Sie Schlüssel, die eine ähnliche Benennungskonvention verwenden, nach dem oben für Schlüsseltresore beschriebenen Verfahren. Auf diese Weise ist die Zeichenfolge in Tools, die lediglich den Schlüsselnamen anzeigen, selbsterklärend.
  
Wenn Sie den Schlüssel mit einem HSM schützen möchten, stellen Sie sicher, dass Sie **HSM** als Wert für den Parameter _"Destination"_ angeben. Andernfalls geben Sie **Software an.**

Beispiel:
  
```powershell
Add-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination HSM -KeyOps wrapKey,unwrapKey
```

Um einen Schlüssel direkt in Ihren Schlüsseltresor zu importieren, benötigen Sie ein nCipher nShield Hardware Security Module.
  
Einige Organisationen bevorzugen diesen Ansatz, um die Herkunft ihrer Schlüssel zu erstellen, und dann bietet diese Methode auch die folgenden Nachweise:
  
- Das für den Import verwendete Toolset enthält den Nachweis von nCipher, dass der Schlüsselaustauschschlüssel (Key Exchange Key, KEK), der zum Verschlüsseln des generierten Schlüssels verwendet wird, nicht exportierbar ist und in einem originalen HSM generiert wird, das von nCipher hergestellt wurde.

- Das Toolset enthält den Nachweis von nCipher, dass die Azure Key Vault-Sicherheitswelt auch auf einem echten HSM von nCipher generiert wurde. Dieser Nachweis belegt Ihnen, dass Microsoft auch originale nCipher-Hardware verwendet.

Wenden Sie sich an Ihr Sicherheitsteam, um festzustellen, ob die vorstehenden Bescheinigungen erforderlich sind. Detaillierte Anweisungen zum Erstellen eines lokalen Schlüssels und zum Importieren in Ihren Schlüsseltresor finden Sie unter [Generieren und Übertragen von HSM-geschützten Schlüsseln für Azure Key Vault](https://azure.microsoft.com/documentation/articles/key-vault-hsm-protected-keys/). Folgen Sie den Azure-Anweisungen, um in jedem Schlüsseltresor einen Schlüssel zu erstellen.
  
### <a name="check-the-recovery-level-of-your-keys"></a>Überprüfen der Wiederherstellungsebene Ihrer Schlüssel

Microsoft 365 erfordert, dass das Azure Key Vault-Abonnement auf "Nicht kündigen" festgelegt ist und dass für die von Customer Key verwendeten Schlüssel soft delete aktiviert ist. Sie können Die Abonnementeinstellungen bestätigen, indem Sie die Wiederherstellungsstufe für Ihre Schlüssel überprüfen.
  
Führen Sie zum Überprüfen der Wiederherstellungsstufe eines Schlüssels in Azure PowerShell das Get-AzKeyVaultKey Wiederherstellungs-Cmdlet aus:
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes
```

Wenn  die Eigenschaft "Wiederherstellungsebene" einen anderen Wert als den Wert **"Recoverable+ProtectedSubscription"** zurückgibt, stellen Sie sicher, dass Sie das Abonnement in die Liste "Nicht kündigen" aufgenommen haben und dass für jeden Schlüsseltresor soft delete aktiviert ist.
  
### <a name="back-up-azure-key-vault"></a>Sichern von Azure Key Vault

Unmittelbar nach dem Erstellen oder Ändern eines Schlüssels, dem Durchführen einer Sicherung und dem Speichern von Kopien der Sicherung, sowohl online als auch offline. Offline-Kopien sollten nicht mit einem Netzwerk verbunden sein, d. h. beispielsweise nicht in einem Safe oder in einem gewerblichen Lager aufbewahrt werden. Mindestens eine Kopie der Sicherung sollte an einem Standort gespeichert werden, auf den Sie im Notfall zugreifen können. Die einzelnen Sicherungen sind die einzige Möglichkeit zum Wiederherstellen des Schlüsselmaterials, sollte ein Key-Vault-Schlüssel dauerhaft vernichtet oder auf andere Weise funktionsuntüchtig gemacht worden sein. Schlüssel, die sich außerhalb des Azure Key Vault befinden und in Azure Key Vault importiert wurden, sind als Sicherung nicht geeignet, da die Metadaten, die für die Verwendung des Schlüssels mit Customer Key erforderlich sind, mit dem externen Schlüssel nicht vorhanden sind. Nur eine vom Azure Key Vault erstellte Sicherung kann für Wiederherstellungsvorgänge mit Customer Key verwendet werden. Daher müssen Sie eine Sicherung von Azure Key Vault erstellen, nachdem Sie einen Schlüssel hochgeladen oder erstellt haben.
  
Führen Sie zum Erstellen einer Sicherung eines Azure Key Vault-Schlüssels das [Cmdlet "Backup-AzKeyVaultKey"](https://docs.microsoft.com/powershell/module/az.keyvault/backup-azkeyvaultkey) wie folgt aus:

```powershell
Backup-AzKeyVaultKey -VaultName <vault name> -Name <key name>
-OutputFile <filename.backup>
```

Stellen Sie sicher, dass die Ausgabedatei das Suffix `.backup` verwendet.
  
Die aus diesem Cmdlet resultierende Ausgabedatei ist verschlüsselt und kann außerhalb von Azure Key Vault nicht verwendet werden. Die Sicherung kann nur für das Azure-Abonnement wiederhergestellt werden, aus dem die Sicherung erstellt wurde.
  
> [!TIP]
> Wählen Sie für die Ausgabedatei eine Kombination aus Ihrem Tresor- und Schlüsselnamen. Dadurch wird der Dateiname selbsterklärend. Außerdem wird sichergestellt, dass die Namen der Sicherungsdateien nicht kollidieren.
  
Beispiel:
  
```powershell
Backup-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -OutputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

### <a name="validate-azure-key-vault-configuration-settings"></a>Konfigurationseinstellungen von Azure Key Vault verifizieren

Die Validierung vor der Verwendung von Schlüsseln in einer DEP ist optional, wird jedoch dringend empfohlen. Wenn Sie die Schritte zum Einrichten Ihrer Schlüssel und Tresore verwenden, die nicht die in diesem Artikel beschriebenen sind, überprüfen Sie den Zustand Ihrer Azure Key Vault-Ressourcen, bevor Sie Customer Key konfigurieren.
  
So stellen Sie sicher, dass die `get` Schlüssel und Vorgänge aktiviert `wrapKey` `unwrapKey` sind:
  
Führen Sie [das Cmdlet "Get-AzKeyVault"](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) wie folgt aus:
  
```powershell
Get-AzKeyVault -VaultName <vault name>
```

Suchen Sie in der Ausgabe nach der Zugriffsrichtlinie und, je nach Bedarf, nach der Exchange Online-Identität (GUID) bzw. der SharePoint Online Identity (GUID). Alle drei vorstehenden Berechtigungen müssen unter den Berechtigungen für Schlüssel angezeigt werden.
  
Wenn die Konfiguration der Zugriffsrichtlinie falsch ist, führen Sie das Set-AzKeyVaultAccessPolicy wie folgt aus:
  
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
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
```

Führen Sie das Cmdlet ["Get-AzKeyVaultKey"](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) wie folgt aus, um zu überprüfen, ob für Ihre Schlüssel kein Ablaufdatum festgelegt ist:
  
```powershell
Get-AzKeyVaultKey -VaultName <vault name>
```

Der Kundenschlüssel kann keinen abgelaufenen Schlüssel verwenden. Vorgänge, die mit einem abgelaufenen Schlüssel versucht werden, führen möglicherweise zu einem Dienstausfall. Es wird dringend empfohlen, dass mit Customer Key verwendete Schlüssel kein Ablaufdatum aufweisen. Ein einmal festgelegtes Ablaufdatum kann nicht gelöscht werden, es kann jedoch eine Datumänderung vorgenommen werden. Wenn ein Schlüssel verwendet werden muss, für den ein Ablaufdatum festgelegt ist, ändern Sie bitte das Ablaufdatum auf 31.12.9999. Schlüssel, deren Ablaufdatum auf ein anderes Datum als den 31.12.9999 festgelegt ist, bestehen die Microsoft 365-Überprüfung nicht.
  
Führen Sie zum Ändern eines Ablaufdatums, das auf einen anderen Wert als den 31.12.9999 festgelegt wurde, das [Cmdlet "Update-AzKeyVaultKey"](https://docs.microsoft.com/powershell/module/az.keyvault/update-azkeyvaultkey) wie folgt aus:
  
```powershell
Update-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Expires (Get-Date -Date "12/31/9999")
```

> [!CAUTION]
> Legen Sie keine Ablaufdaten für kryptografische Schlüssel fest, die Sie mit Customer Key verwenden.
  
### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a>Abrufen eines URI für jeden Azure Key Vault-Schlüssel

Nachdem Sie Ihre Schlüsseltresor eingerichtet und Ihre Schlüssel hinzugefügt haben, führen Sie den folgenden Befehl aus, um den URI für den Schlüssel in jedem Schlüsseltresor zu erhalten. Sie müssen diese URIs verwenden, wenn Sie später jede DEP erstellen und zuweisen. Speichern Sie diese Informationen daher an einem sicheren Ort. Führen Sie diesen Befehl einmal für jeden Schlüsseltresor aus.
  
In Azure PowerShell:
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name>).Id
```

## <a name="office-365-setting-up-customer-key-for-exchange-online-and-skype-for-business"></a>Office 365: Einrichten von Customer Key für Exchange Online und Skype for Business

Bevor Sie beginnen, stellen Sie sicher, dass Sie die erforderlichen Aufgaben zum Einrichten von Azure Key Vault abgeschlossen haben. Informationen hierzu finden Sie unter [Erledigen von Aufgaben in Azure Key Vault und Microsoft FastTrack für Customer Key](#complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key).
  
Zum Einrichten von Customer Key für Exchange Online und Skype for Business führen Sie diese Schritte aus, indem Sie eine Remoteverbindung mit Exchange Online mit Windows PowerShell.
  
### <a name="create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business"></a>Erstellen einer Datenverschlüsselungsrichtlinie (DEP) zur Nutzung mit Exchange Online und Skype for Business

Eine Datenverschlüsselungsrichtlinie (DEP) ist mit einer Reihe von im Azure Key Vault gespeicherten Schlüsseln verknüpft. Sie weisen einem Postfach in Microsoft 365 eine DEP zu. Microsoft 365 verwendet dann die in der Richtlinie identifizierten Schlüssel, um das Postfach zu verschlüsseln. Zum Erstellen der Datenverschlüsselungsrichtlinie (DEP) benötigen Sie die Key Vault-URI, die Sie zuvor erhalten haben. Anweisungen hierzu finden Sie unter [Abrufen eines URI für jeden Azure Key Vault-Schlüssel](#obtain-the-uri-for-each-azure-key-vault-key).
  
Nicht vergessen! Wenn Sie eine DEP erstellen, geben Sie zwei Schlüssel in zwei verschiedenen Azure Key Vaults an. Erstellen Sie diese Schlüssel in zwei separaten Azure-Regionen, um die Georedundanz sicherzustellen.
  
Um eine Datenverschlüsselungsrichtlinie (DEP) zu erstellen, führen Sie bitte folgende Schritte aus:
  
1. Stellen Sie auf Ihrem lokalen Computer mithilfe eines Arbeits- oder Schulkontos, das über globale Administratorberechtigungen in Ihrer Organisation verfügt, eine Verbindung mit [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) in einem Windows PowerShell herstellen.

2. Um eine Datenverschlüsselungsrichtlinie zu erstellen, verwenden Sie das Cmdlet „New-DataEncryptionPolicy“, indem Sie den folgenden Befehl eingeben.

   ```powershell
   New-DataEncryptionPolicy -Name <PolicyName> -Description "Policy Description" -AzureKeyIDs <KeyVaultURI1>, <KeyVaultURI2>
   ```

   Dabei gilt:

   - *PolicyName* ist der Name, den Sie für die Richtlinie verwenden möchten. Namen dürfen keine Leerzeichen enthalten. Beispiel: USA_Postfächer.

   - *Die Richtlinienbeschreibung* ist eine benutzerfreundliche Beschreibung der Richtlinie, die Ihnen dabei hilft, sich zu merken, wofür die Richtlinie steht. In der Beschreibung sind Leerzeichen erlaubt. Beispiel: "Stammschlüssel für Postfächer in den USA und deren Gebiet".

   - *KeyVaultURI1* ist der URI für den ersten Schlüssel in der Richtlinie. Beispiel: <https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01>.

   - *KeyVaultURI2* ist der URI für den zweiten Schlüssel in der Richtlinie. Beispiel: <https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02>. Trennen Sie die beiden URI mittels Komma und Leerzeichen.

   Beispiel:
  
   ```powershell
   New-DataEncryptionPolicy -Name USA_mailboxes -Description "Root key for mailboxes in USA and its territories" -AzureKeyIDs https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01, https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02
   ```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-DataEncryptionPolicy](https://docs.microsoft.com/powershell/module/exchange/new-data-encryptionpolicy).

### <a name="assign-a-dep-to-a-mailbox"></a>Zuweisen einer Datenverschlüsselungsrichtlinie (DEP) zu einem Postfach

Zuweisen der Datenverschlüsselungsrichtlinie (DEP) zu einem Postfach mithilfe des Cmdlets „Set-Mailbox“. Nachdem Sie die Richtlinie zugewiesen haben, kann Microsoft 365 das Postfach mit dem in der DEP identifizierten Schlüssel verschlüsseln.
  
```powershell
Set-Mailbox -Identity <MailboxIdParameter> -DataEncryptionPolicy <PolicyName>
```

Dabei *gibt MailboxIdParameter* ein Benutzerpostfach an. Weitere Informationen zum Cmdlet „Set-Mailbox“ finden Sie unter [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/set-mailbox).

In Hybridumgebungen können Sie den lokalen Postfachdaten, die mit Ihrem Exchange -Mandanten synchronisiert werden, eine DEP zuweisen. Um diesen synchronisierten Postfachdaten eine DEP zuzuordnen, verwenden Sie das Set-MailUser Cmdlet. Weitere Informationen zu Postfachdaten in der Hybridumgebung finden Sie in lokalen Postfächern, die [Outlook für iOS](https://docs.microsoft.com/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth)und Android mit moderner Hybridauthentifizierung verwenden.

```powershell
Set-MailUser -Identity <MailUserIdParameter> -DataEncryptionPolicy <PolicyName>
```

Dabei *gibt MailUserIdParameter* einen E-Mail-Benutzer an (auch als E-Mail-aktivierter Benutzer bezeichnet). Weitere Informationen zum cmdlet Set-MailUser finden Sie unter [Set-MailUser](https://docs.microsoft.com/powershell/module/exchange/set-mailuser).
  
### <a name="validate-mailbox-encryption"></a>Überprüfen einer Postfachverschlüsselung

Das Verschlüsseln eines Postfachs kann einige Zeit in Anspruch nehmen. Bei der ersten Richtlinienzuweisung muss das Postfach auch vollständig von einer Datenbank in eine andere verschoben werden, bevor der Dienst das Postfach verschlüsseln kann. Wir empfehlen, dass Sie 72 Stunden warten, bevor Sie versuchen, die Verschlüsselung nach dem Ändern einer Datenverschlüsselungsrichtlinie (DEP) oder nach dem erstmaligen Zuweisen einer Datenverschlüsselungsrichtlinie (DEP) zu einem Postfach zu überprüfen.
  
Verwenden Sie das Cmdlet „Get-MailboxStatistics“, um festzustellen, ob ein Postfach verschlüsselt ist.
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

Die Eigenschaft "IsEncrypted" gibt den Wert **"true"** zurück, wenn das Postfach verschlüsselt ist, und den Wert **"false",** wenn das Postfach nicht verschlüsselt ist. Die Zeit bis zum Abschließen des Verschiebens von Postfächern hängt von der Anzahl der Postfächer, denen Sie zum ersten Mal eine DEP zuweisen, und der Größe der Postfächer ab. Wenn die Postfächer nach einer Woche nach dem Zugewiesenen der DEP nicht verschlüsselt wurden, wenden Sie sich an Microsoft.

## <a name="office-365-setting-up-customer-key-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>Office 365: Einrichten von Customer Key für SharePoint Online-, OneDrive for Business- und #A0

Bevor Sie beginnen, stellen Sie sicher, dass Sie die erforderlichen Aufgaben zum Einrichten von Azure Key Vault abgeschlossen haben. Informationen hierzu finden Sie unter [Erledigen von Aufgaben in Azure Key Vault und Microsoft FastTrack für Customer Key](#complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key).
  
Zum Einrichten von Customer Key für SharePoint Online-, OneDrive for Business- und #A0 führen Sie diese Schritte aus, indem Sie eine Remoteverbindung mit SharePoint Online mit Windows PowerShell.
  
### <a name="create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo"></a>Erstellen einer Datenverschlüsselungsrichtlinie (DEP) für jede SharePoint Online- und OneDrive for Business-Geo

Sie ordnen eine DEP einem Satz von Schlüsseln zu, die in Azure Key Vault gespeichert sind. Sie wenden eine Datenverschlüsselungsrichtlinie (DEP) auf alle Ihre Daten an einem geografischen Standort an, der auch als Geo bezeichnet wird. Wenn Sie das Multi-Geo-Feature von Office 365 verwenden, können Sie eine DEP pro Geografischem erstellen, mit der Möglichkeit, unterschiedliche Schlüssel pro Geografischem zu verwenden. Wenn Sie multi-geo nicht verwenden, können Sie eine DEP in Ihrer Organisation für die Verwendung mit SharePoint Online-, OneDrive for Business- und #A0 erstellen. Microsoft 365 verwendet die in der DEP identifizierten Schlüssel, um Ihre Daten in diesem Geografischen zu verschlüsseln. Zum Erstellen der Datenverschlüsselungsrichtlinie (DEP) benötigen Sie die Key Vault-URI, die Sie zuvor erhalten haben. Anweisungen hierzu finden Sie unter [Abrufen eines URI für jeden Azure Key Vault-Schlüssel](#obtain-the-uri-for-each-azure-key-vault-key).
  
Nicht vergessen! Wenn Sie eine DEP erstellen, geben Sie zwei Schlüssel in zwei verschiedenen Azure Key Vaults an. Erstellen Sie diese Schlüssel in zwei separaten Azure-Regionen, um die Georedundanz sicherzustellen.
  
Um eine Datenverschlüsselungsrichtlinie (DEP) zu erstellen, müssen Sie mithilfe von Windows PowerShell eine Remote-Verbindung zu SharePoint Online herstellen.
  
1. Stellen Sie auf Ihrem lokalen Computer mithilfe eines Arbeits- oder Schulkontos, das über globale Administratorberechtigungen in Ihrer Organisation verfügt, [eine Verbindung mit SharePoint Online PowerShell sicher.](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps&preserve-view=true)

2. Führen Sie in der Microsoft SharePoint Online Management-Shell das Cmdlet Register-SPODataEncryptionPolicy wie folgt durch:

   ```powershell
   Register-SPODataEncryptionPolicy -Identity <adminSiteCollectionURL> -PrimaryKeyVaultName <PrimaryKeyVaultName> -PrimaryKeyName <PrimaryKeyName> -PrimaryKeyVersion <PrimaryKeyVersion> -SecondaryKeyVaultName <SecondaryKeyVaultName> -SecondaryKeyName <SecondaryKeyName> -SecondaryKeyVersion <SecondaryKeyVersion>
   ```

   Beispiel:
  
   ```powershell
   Register-SPODataEncryptionPolicy -Identity https://contoso.sharepoint.com -PrimaryKeyVaultName 'stageRG3vault' -PrimaryKeyName 'SPKey3' -PrimaryKeyVersion 'f635a23bd4a44b9996ff6aadd88d42ba' -SecondaryKeyVaultName 'stageRG5vault' -SecondaryKeyName 'SPKey5' -SecondaryKeyVersion '2b3e8f1d754f438dacdec1f0945f251a’
   ```

   Sobald Sie die Datenverschlüsselungsrichtlinie (DEP) registrieren, beginnt die Verschlüsselung der Daten im Geo. Die Verschlüsselung kann einige Zeit dauern. Weitere Informationen zur Verwendung dieses Parameters finden Sie unter [Register-SPODataEncryptionPolicy](https://docs.microsoft.com/powershell/module/sharepoint-online/register-spodataencryptionpolicy?view=sharepoint-ps&preserve-view=true).

### <a name="validate-file-encryption"></a>Überprüfen der Dateiverschlüsselung

 Um die Verschlüsselung von SharePoint Online-, OneDrive for Business- und Get-SPODataEncryptionPolicy zu überprüfen, stellen Sie eine Verbindung mit [SharePoint Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)auf, und verwenden Sie dann das cmdlet Get-SPODataEncryptionPolicy, um den Status Ihres Mandanten zu überprüfen. Die _Eigenschaft "State"_ gibt den Wert **"registriert"** zurück, wenn die Kundenschlüsselverschlüsselung aktiviert ist und alle Dateien auf allen Websites verschlüsselt wurden. Wenn die Verschlüsselung noch ausgeführt wird, gibt dieses Cmdlet den Wert der **Registrierung zurück.**

## <a name="related-articles"></a>Verwandte Artikel

- [Dienstverschlüsselung mit Kundenschlüssel](customer-key-overview.md)

- [Verwalten von Kundenschlüsseln](customer-key-manage.md)

- [Rollen oder Drehen eines Kundenschlüssels oder eines Verfügbarkeitsschlüssels](customer-key-availability-key-roll.md)

- [Informationen zum Verfügbarkeitsschlüssel](customer-key-availability-key-understand.md)

- [Dienstverschlüsselung](office-365-service-encryption.md)
