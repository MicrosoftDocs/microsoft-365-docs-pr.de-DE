---
title: Einrichten des Kundenschlüssels
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Informationen zum Einrichten des Kundenschlüssels für Microsoft 365.
ms.openlocfilehash: e187c01a355cc9b926e892cb3326b5a527c714a4
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2021
ms.locfileid: "52344674"
---
# <a name="set-up-customer-key"></a>Einrichten des Kundenschlüssels

Mit dem Kundenschlüssel steuern Sie die Verschlüsselungsschlüssel Ihrer Organisation und konfigurieren dann Microsoft 365, um sie zum Verschlüsseln ihrer ruhenen Daten in Den Rechenzentren von Microsoft zu verwenden. Mit anderen Worten: Customer Key ermöglicht es Kunden, mit ihren Schlüsseln eine Verschlüsselungsebene hinzuzufügen, die Ihnen gehört.

Richten Sie Azure ein, bevor Sie den Kundenschlüssel für Office 365. In diesem Artikel werden die Schritte beschrieben, die Sie zum Erstellen und Konfigurieren der erforderlichen Azure-Ressourcen ausführen müssen, und anschließend werden die Schritte zum Einrichten des Kundenschlüssels in Office 365. Nachdem Sie Azure eingerichtet haben, bestimmen Sie, welche Richtlinie und damit welche Schlüssel Sie zuweisen müssen, um Daten über verschiedene Microsoft 365 in Ihrer Organisation zu verschlüsseln. Weitere Informationen zum Kundenschlüssel oder eine allgemeine Übersicht finden Sie unter [Service encryption with Customer Key in Office 365](customer-key-overview.md).
  
> [!IMPORTANT]
> Es wird dringend empfohlen, die bewährten Methoden in diesem Artikel zu befolgen. Diese werden sind als **TIPP** und **WICHTIG** bezeichnet. Customer Key ermöglicht Ihnen die Kontrolle über die grundlegenden kryptografischen Schlüssel, deren Geltungsbereich so groß wie Ihre gesamte Organisation sein kann. Dies bedeutet, dass Fehler im Zusammenhang mit diesen Schlüsseln einen großen Einfluss haben und zu Dienstunterbrechungen oder unwiderruflichen Datenverlusten führen können.
  
## <a name="before-you-set-up-customer-key"></a>Vor dem Einrichten des Kundenschlüssels

Bevor Sie beginnen, stellen Sie sicher, dass Sie über die entsprechenden Azure-Abonnements und -Lizenzierung für Ihre Organisation verfügen. Verwenden Sie kostenpflichtige Azure-Abonnements entweder mithilfe Enterprise Agreement oder eines Clouddienstanbieters. Kreditkartenbasierte Zahlungen werden nicht akzeptiert. Genehmigen und Einrichten der Kontoanforderungen für die Rechnungsstellung. Abonnements, die Sie über kostenlose, Testversionen, Sponsorings, MSDN-Abonnements und unter Legacysupport erhalten haben, sind nicht berechtigt.

Office 365 E5-, Microsoft 365 E5-, Microsoft 365 E5 Compliance- und Microsoft 365 E5 Information Protection & Governance SKUs bieten Kundenschlüssel. Office 365 Advanced Compliance SKU ist nicht mehr für die Beschaffung neuer Lizenzen verfügbar. Vorhandene Office 365 Advanced Compliance werden weiterhin unterstützt.

Informationen zu den Konzepten und Verfahren in diesem Artikel finden Sie in der [Azure Key Vault-Dokumentation.](/azure/key-vault/) Machen Sie sich auch mit den in Azure verwendeten Begriffen vertraut, z. B. [Azure AD-Mandant](/previous-versions/azure/azure-services/jj573650(v=azure.100)#what-is-an-azure-ad-tenant).
  
Wenn Sie über die Dokumentation hinaus mehr Support benötigen, wenden Sie sich an Microsoft Consulting Services (MCS), Premier Field Engineering (PFE) oder einen Microsoft-Partner, um Unterstützung zu erhalten. Um Feedback zum Kundenschlüssel, einschließlich der Dokumentation, zu geben, senden Sie Ihre Ideen, Vorschläge und Perspektiven an customerkeyfeedback@microsoft.com.
  
## <a name="overview-of-steps-to-set-up-customer-key"></a>Übersicht über die Schritte zum Einrichten des Kundenschlüssels

Zum Einrichten des Kundenschlüssels führen Sie diese Aufgaben in der aufgeführten Reihenfolge aus. Der Rest dieses Artikels enthält ausführliche Anweisungen für jede Aufgabe oder links zu weiteren Informationen für jeden Schritt des Prozesses.
  
**In Azure und Microsoft FastTrack:**
  
Sie werden die meisten dieser Aufgaben ausführen, indem Sie eine Remoteverbindung mit Azure PowerShell. Um optimale Ergebnisse zu erzielen, sollten Sie Version 4.4.0 oder höher von Azure PowerShell verwenden.
  
- [Zwei neue Azure-Abonnements erstellen](#create-two-new-azure-subscriptions)

- [Senden einer Anforderung zum Aktivieren von Customer Key für Office 365](#submit-a-request-to-activate-customer-key-for-office-365)
 
- [Azure-Abonnements registrieren, um einen obligatorischen Aufbewahrungszeitraum zu nutzen](#register-azure-subscriptions-to-use-a-mandatory-retention-period)

  Die Registrierung kann ab einem bis zu fünf Arbeitstagen dauern.

- [Erstellen eines Premium Azure Key Vault für jedes Abonnement](#create-a-premium-azure-key-vault-in-each-subscription)

- [Zuweisen von Berechtigungen für jeden Schlüsseltresor (Key Vault)](#assign-permissions-to-each-key-vault)

- [Stellen Sie sicher, dass das soft delete für Ihre Schlüsseltresor aktiviert ist.](#make-sure-soft-delete-is-enabled-on-your-key-vaults)

- [Hinzufügen eines Schlüssels zu jedem Schlüsseltresor durch das Erstellen oder Importieren eines Schlüssels](#add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key)

- [Überprüfen der Wiederherstellungsebene Ihrer Schlüssel](#check-the-recovery-level-of-your-keys)

- [Sichern von Azure Key Vault](#back-up-azure-key-vault)

- [Konfigurationseinstellungen von Azure Key Vault verifizieren](#validate-azure-key-vault-configuration-settings)

- [Anrufen des URI für jeden Azure Key Vault-Schlüssel](#obtain-the-uri-for-each-azure-key-vault-key)
  
## <a name="complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key"></a>Erledigen von Aufgaben in Azure Key Vault und Microsoft FastTrack für Customer Key

Führen Sie diese Aufgaben in Azure Key Vault aus. Sie müssen diese Schritte für alle DEPs ausführen, die Sie mit Customer Key verwenden.
  
### <a name="create-two-new-azure-subscriptions"></a>Zwei neue Azure-Abonnements erstellen

Customer Key erfordert zwei Azure-Abonnements. Als bewährte Methode empfiehlt Microsoft, neue Azure-Abonnements für die Verwendung mit Customer Key zu erstellen. Azure Key Vault keys can only be authorized for applications in the same Azure Active Directory (Microsoft Azure Active Directory) tenant, you must create the new subscriptions using the same Azure AD tenant used with your organization where the DEPs will be assigned. Verwenden Sie beispielsweise Ihr Arbeits- oder Schulkonto, das über globale Administratorrechte in Ihrer Organisation verfügt. Weitere Informationen zu den einzelnen Arbeitsschritten finden Sie unter [Als Unternehmen für Azure registrieren](/azure/active-directory/fundamentals/sign-up-organization).
  
> [!IMPORTANT]
> Für Customer Key sind zwei Schlüssel für jede Daten- Verschlüsselungsrichtlinie (DEP) erforderlich. Zu diesem Zweck müssen Sie zwei Azure-Abonnements erstellen. Als bewährte Methode empfiehlt Microsoft, dass separate Mitglieder Ihrer Organisation jeweils einen Schlüssel für jedes Abonnement konfigurieren. Verwenden Sie diese Azure-Abonnements nur zum Verwalten von Verschlüsselungsschlüsseln für Office 365. Auf diese Weise ist Ihre Organisation geschützt, falls einer ihrer Betreiber versehentlich, absichtlich oder in böswilliger Absicht die Schlüssel, für die Sie verantwortlich sind, löscht oder auf andere Weise unsachgemäß handhabt.

Es gibt praktisch keine Beschränkung hinsichtlich der Anzahl von Azure-Abonnements, die Sie für Ihre Organisation erstellen können. Durch die Nutzung dieser bewährten Methoden können Sie die Auswirkungen von menschlichen Fehlern bei der Verwaltung der von Customer Key genutzten Ressourcen minimieren.
  
### <a name="submit-a-request-to-activate-customer-key-for-office-365"></a>Senden einer Anforderung zum Aktivieren von Customer Key für Office 365

Nachdem Sie die beiden neuen Azure-Abonnements erstellt haben, müssen Sie die entsprechende Kundenschlüsselangebotsanforderung im [Microsoft FastTrack-Portal übermitteln.](https://fasttrack.microsoft.com/) Die Auswahlen, die Sie im Angebotsformular zu den autorisierten Bezeichnungen innerhalb Ihrer Organisation treffen, sind für den Abschluss der Registrierung des Kundenschlüssels wichtig und erforderlich. Die Verantwortlichen in diesen ausgewählten Rollen in Ihrer Organisation stellen die Echtheit aller Anforderungen zum Widerrufen und Zerstören aller Schlüssel sicher, die mit einer Datenverschlüsselungsrichtlinie für Kundenschlüssel verwendet werden. Sie müssen diesen Schritt einmal für jeden Kundenschlüssel-DEP-Typ tun, den Sie für Ihre Organisation verwenden möchten.

**Das FastTrack-Team bietet keine Unterstützung für den Kundenschlüssel. Office 365 verwendet einfach das FastTrack-Portal, um Ihnen das Senden des Formulars zu ermöglichen und uns dabei zu helfen, die relevanten Angebote für Kundenschlüssel nachverfolgt zu werden. Nachdem Sie die FastTrack-Anforderung übermittelt haben, erreichen Sie das entsprechende Customer Key-Onboarding-Team, um den Onboardingvorgang zu starten.**
  
Führen Sie zur Übermittlung eines Angebots zum Aktivieren von Customer Key die folgenden Schritte aus:
  
1. Melden Sie sich mit einem Arbeits- oder Schulkonto mit globalen Administratorberechtigungen in Ihrer Organisation beim [Microsoft FastTrack-Portal an.](https://fasttrack.microsoft.com/)

2. Nachdem Sie angemeldet sind, wählen Sie die entsprechende Domäne aus.

3. Wählen Sie für die ausgewählte Domäne **in** der oberen Navigationsleiste Dienste anfordern aus, und überprüfen Sie die Liste der verfügbaren Angebote.

4. Wählen Sie die Informationskarte für das Angebot aus, das für Sie gilt:

   - **Mehrere Microsoft 365:** Wählen Sie die **Hilfe zum Anfordern des Verschlüsselungsschlüssels für Microsoft 365** aus.

   - **Exchange Online und Skype for Business:** Wählen Sie die **Hilfe zum Anfordern des Verschlüsselungsschlüssels für Exchange** aus.

   - **SharePoint Online-, OneDrive- und Teams Dateien:** Wählen Sie **die Hilfe zum Anfordern von Verschlüsselungsschlüsseln für SharePoint und OneDrive for Business** aus.

5. Nachdem Sie die Angebotsdetails überprüft haben, wählen Sie **Weiter zu Schritt 2 aus.**

6. Tragen Sie alle relevanten Details und erforderlichen Informationen im Angebotsformular ein. Achten Sie besonders auf Ihre Auswahl, welche MitarbeiterInnen Ihrer Organisation Sie autorisieren, die permanente und unwiderrufliche Vernichtung von kryptografischen Schlüsseln und Daten zu genehmigen. Sobald Sie das Formular ausgefüllt haben, wählen Sie **Senden**.

### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a>Azure- Abonnements registrieren, um einen obligatorischen Aufbewahrungszeitraum zu nutzen.

Der temporäre oder dauerhafte Verlust von Stammverschlüsselungsschlüsseln kann für den Dienstbetrieb störend oder sogar katastrophal sein und zu Datenverlusten führen. Aus diesem Grund ist für die mit Customer Key verwendeten Ressourcen ein starker Schutz erforderlich. Alle Azure-Ressourcen, die mit Customer Key verwendet werden, bieten Schutzmechanismen, die weit über die Standardkonfiguration hinaus gehen. Sie können Azure-Abonnements für einen obligatorischen Aufbewahrungszeitraum *kennzeichnen oder registrieren.* Ein obligatorischer Aufbewahrungszeitraum verhindert die sofortige und unwiderrufliche Kündigung Ihres Azure-Abonnements. Die schritte, die zum Registrieren von Azure-Abonnements für einen obligatorischen Aufbewahrungszeitraum erforderlich sind, erfordern die Zusammenarbeit mit dem Microsoft 365 Team. Die Registrierung kann ab einen bis fünf Arbeitstage dauern. Zuvor wurde der obligatorische Aufbewahrungszeitraum manchmal als "Do Not Cancel" bezeichnet.
  
Bevor Sie sich an das Microsoft 365 wenden, müssen Sie die folgenden Schritte für jedes Azure-Abonnement ausführen, das Sie mit Dem Kundenschlüssel verwenden. Stellen Sie sicher, dass das [Azure PowerShell Az-Modul](/powershell/azure/new-azureps-module-az) installiert ist, bevor Sie beginnen.
  
1. Melden Sie sich mit Azure PowerShell. Anweisungen finden Sie unter [Sign in with Azure PowerShell](/powershell/azure/authenticate-azureps).

2. Führen Sie Register-AzProviderFeature cmdlet aus, um Ihre Abonnements für die Verwendung eines obligatorischen Aufbewahrungszeitraums zu registrieren. Führen Sie diese Aktion für jedes Abonnement aus.

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.Resources
   ```

3. Wenden Sie sich an Microsoft, um den Vorgang zu abschließen.

   - Wenden Sie sich zum Aktivieren des Kundenschlüssels zum Zuweisen von DEP zu Exchange Online Postfächern [an exock@microsoft.com](mailto:exock@microsoft.com).

   - Wenn Sie den Kundenschlüssel zum Zuweisen von DEPs zum Verschlüsseln von SharePoint Online- und OneDrive for Business-Inhalten (einschließlich Teams-Dateien) für alle Mandantenbenutzer aktivieren möchten, wenden Sie sich an [spock@microsoft.com](mailto:spock@microsoft.com).

   - Wenden Sie sich an m365-ck@service.microsoft.com, um den Kundenschlüssel zum Zuweisen von DEPs zum Verschlüsseln von Inhalten über mehrere Microsoft 365-Workloads (Exchange Online, Teams, MIP EDM) zu [aktivieren.](mailto:m365-ck@service.microsoft.com)

- Fügen Sie die folgenden Informationen in Ihre E-Mail ein:

   **Betreff**: Kundenschlüssel für \<*Your tenant's fully qualified domain name*\>

   **Textkörper**: Fügen Sie die Abonnement-IDs ein, für die Sie den obligatorischen Aufbewahrungszeitraum und die Ausgabe der Get-AzProviderFeature Abonnements abschließen möchten.

   Die Service-Level-Vereinbarung (Service Level Agreement, SLA) für den Abschluss dieses Vorgangs beläuft sich auf fünf Werktage, nachdem Microsoft benachrichtigt wurde (und überprüft hat, dass Sie Ihre Abonnements für die Nutzung eines obligatorischen Aufbewahrungszeitraums registriert haben).

4. Nachdem Sie von Microsoft eine Benachrichtigung erhalten haben, dass die Registrierung abgeschlossen ist, überprüfen Sie den Status Ihrer Registrierung, indem Sie den befehl Get-AzProviderFeature wie folgt ausführen. Bei Überprüfung gibt der Get-AzProviderFeature den Wert **Registered für** die Registration **State-Eigenschaft** zurück. Führen Sie diesen Schritt für jedes Abonnement aus.

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Get-AzProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
   ```

5. Führen Sie zum Abschließen des Vorgangs den Befehl Register-AzResourceProvider aus. Führen Sie diesen Schritt für jedes Abonnement aus.

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzResourceProvider -ProviderNamespace Microsoft.KeyVault
   ```

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a>Erstellen eines Premium Azure Key Vault für jedes Abonnement

Die Schritte zum Erstellen eines Schlüssel Tresors sind in ["erste Schritte mit Azure Key Vault"](/azure/key-vault/general/overview)dokumentiert, das Sie durch das Installieren und Ingangsetzen von Azure PowerShell, das Herstellen einer Verbindung mit Ihrem Azure-Abonnement, das Erstellen einer Ressourcengruppe und das Erstellen eines Schlüsseltresors in dieser Ressourcengruppe führt.
  
Wenn Sie einen Schlüsseltresor erstellen, müssen Sie eine SKU auswählen: entweder Standard oder Premium. Die Standard-SKU ermöglicht den Schutz von Azure Key Vault-Schlüsseln mit Software - es gibt keinen Hardwaresicherheitsmodul (Hardware Security Module, HSM)-Schlüsselschutz - und die Premium-SKU ermöglicht die Verwendung von HSMs zum Schutz von Schlüsseltresorschlüsseln. Customer Key akzeptiert Schlüsseltresore mit jeder SKU, wobei Microsoft dringend empfiehlt, nur die Premium-SKU zu verwenden. Die Betriebskosten mit Schlüsseln eines der beiden Typen sind identisch. Der einzige Unterschied bei den Kosten sind die monatlichen Kosten für jeden HSM-geschützten Schlüsseln. Detailinformationen finden Si unter [Key Vault-Preise](https://azure.microsoft.com/pricing/details/key-vault/).
  
> [!IMPORTANT]
> Verwenden Sie die Premium-SKU-Schlüsseltresore und HSM-geschützten Schlüssel für Produktionsdaten, und verwenden Sie nur standardmäßige SKU-Schlüsseltresore und Schlüssel für Tests und Überprüfungen.
  
Erstellen Sie für Microsoft 365 Dienst, mit dem Sie den Kundenschlüssel verwenden, einen Schlüsseltresor in jedem der beiden von Ihnen erstellten Azure-Abonnements. Um z. B. den Kundenschlüssel für die Verwendung von DEPs für Exchange Online-, SharePoint Online- und Szenarien mit mehreren Arbeitsauslastungen zu aktivieren, erstellen Sie drei Paare von Schlüsseltresor.
  
Verwenden Sie eine Benennungskonvention für Schlüsseltresore, durch welche sich die beabsichtigte Verwendung der Datenverschlüsselungsrichtlinie widerspiegelt, der Sie die Tresore zuordnen möchten. Im nachstehenden Abschnitt „Bewährte Methoden“ finden Sie Empfehlungen zur Benennung.
  
Erstellen Sie für jede Datenverschlüsselungsrichtlinie eine eigene, paarweise angeordnete Tresor-Gruppe. Bei Exchange Online wählen Sie den Geltungsbereich einer Datenverschlüsselungsrichtlinie, wenn Sie die Richtlinie dem Postfach zuweisen. Einem Postfach kann nur eine Richtlinie zugewiesen werden, und Sie können bis zu 50 Richtlinien erstellen. Der Bereich einer SharePoint Online-Richtlinie umfasst alle Daten innerhalb einer Organisation an einem geografischen Standort oder _geo_. Der Bereich für eine Richtlinie mit mehreren Arbeitsauslastungen umfasst alle Daten in den unterstützten Arbeitsauslastungen für alle Benutzer.

Die Erstellung von Schlüsseltresoren erfordert auch die Erstellung von Azure-Ressourcengruppen, da Schlüsseltresor Speicherkapazität (obwohl klein) benötigen und die Key Vault-Protokollierung, sofern aktiviert, auch gespeicherte Daten generiert. Als bewährte Methode empfiehlt Microsoft, für die Verwaltung jeder Ressourcengruppe separate Administratoren zu verwenden, und die Verwaltung richtet sich an die Administratorengruppe, die alle zugehörigen Customer Key-Ressourcen verwaltet.
  
> [!IMPORTANT]
> Um die Verfügbarkeit zu maximieren, platzieren Sie Ihre Schlüsseltresor in Regionen in der Nähe Ihres Microsoft 365-Diensts. Wenn Sich Ihre Exchange Online-Organisation beispielsweise in Nordamerika befindet, platzieren Sie Ihre Schlüsseltresor in Nordamerika. Wenn Ihre Exchange Online-Organisation in Europa ist, sollten Sie Ihre Schlüsseldepots in Europa platzieren.
>
> Verwenden Sie ein gemeinsames Präfix für Schlüsseltresor und eine Abkürzung für die Verwendung und den Umfang des Schlüsseltresor und der Schlüssel (z. B. für den Contoso SharePoint-Dienst, in dem sich die Tresore in Nordamerika befinden, ist ein mögliches Namenspaar Contoso-CK-SP-NA-VaultA1 und Contoso-CK-SP-NA-VaultA2. In Azure sind Tresornamen global eindeutige Zeichenfolgen, daher müssen Sie möglicherweise Variationen Ihrer gewünschten Namen ausprobieren, falls die gewünschten Namen bereits von anderen Azure-Kunden beansprucht werden. Ab Juli 2017 können Tresornamen nicht mehr geändert werden, daher empfiehlt es sich, einen schriftlichen Setup-Plan zu erstellen und eine zweite Person zu beauftragen, die überprüft, ob der Plan ordnungsgemäß ausgeführt wird.
>
> Erstellen Sie Ihre Depots nach Möglichkeit in nicht-gekoppelten Regionen. Gekoppelte Azure-Regionen bieten eine hohe Verfügbarkeit über Dienstausfall-Domänen hinweg. Dementsprechend können regionale Paare gegenseitig als Backup-Region der jeweils anderen betrachtet werden. Dies bedeutet, dass eine Azure-Ressource, die in einer bestimmten Region platziert ist, durch die gekoppelte Region automatisch an Fehlertoleranz gewinnt. Aus diesem Grund bedeutet die Auswahl von Regionen für zwei Vaults, die in einer Datenverschlüsselungsrichtlinie verwendet werden, in der die Regionen gekoppelt sind, dass nur insgesamt zwei Verfügbarkeitsregionen verwendet werden. In den meisten geografischen Regionen gibt es nur zwei Regionen, weshalb es noch nicht möglich ist, nicht-gekoppelte Regionen auszuwählen. Wählen Sie nach Möglichkeit zwei nicht gekoppelte Bereiche für die beiden mit einer Datenverschlüsselungsrichtlinie verwendeten Tresore aus. Dies hat den positiven Effekt, dass insgesamt vier verfügbare Regionen genutzt werden. Weitere Informationen hierzu sowie ein aktuelles Verzeichnis der Regionenpaare finden Sie unter [Geschäftskontinuität und Notfallwiederherstellung (Business continuity and disaster recovery, BCDR): Gekoppelte Regionen in Azure](/azure/best-practices-availability-paired-regions).
  
### <a name="assign-permissions-to-each-key-vault"></a>Zuweisen von Berechtigungen für jeden Schlüsseltresor (Key Vault)

Sie müssen je nach Implementierung drei separate Berechtigungssätze für jeden Schlüsseltresor definieren. Sie müssen beispielsweise eine Berechtigungsgruppe für jede der folgenden Optionen definieren:
  
- **Schlüsseltresoradministratoren,** die ihre Schlüsseltresorverwaltung für Ihre Organisation täglich verwalten. Zu diesen Aufgaben gehören Datensicherung sowie Erstellen, Abrufen, Importieren, Auflisten und Wiederherstellen.

  > [!IMPORTANT]
  > Die Berechtigungsgruppe, die Schlüsseltresor-Administratoren zugewiesen ist, beinhaltet keine Berechtigung zum Löschen von Schlüsseln. Dies ist beabsichtigt und eine wichtige Vorgehensweise. Kryptografische Schlüssel werden normalerweise nicht gelöscht, da dadurch Daten dauerhaft vernichtet werden. Eine bewährte Methode besteht darin, den Schlüsseltresor-Administratoren diese Berechtigung nicht standardmäßig zuzuweisen. Behalten Sie stattdessen diese Berechtigung den Schlüsseltresor-Mitwirkenden vor und weisen Sie diese einem Administrator nur kurzfristig und lediglich, sofern die damit verbundenen Folgen klar verstanden wurden, zu.
  
  Um diesen Berechtigungen einem Benutzer in Ihrer Organisation zuzuordnen, melden Sie sich bei Ihrem Azure-Abonnement mit Azure PowerShell. Anweisungen finden Sie unter [Sign in with Azure PowerShell](/powershell/azure/authenticate-azureps).

- Führen Sie Set-AzKeyVaultAccessPolicy cmdlet aus, um die erforderlichen Berechtigungen zu erteilen.

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
   ```

   Beispiel:

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-CK-EX-NA-VaultA1 -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
   ```

- **Schlüsseltresor-Mitwirkenden**, die Berechtigungen für den Azure Key Vault selbst ändern können. Sie müssen diese Berechtigungen ändern, wenn Mitarbeiter Ihr Team verlassen oder ihrem Team beitreten. In der seltenen Situation, in der die Schlüsseltresoradministratoren berechtigterweise die Berechtigung zum Löschen oder Wiederherstellen eines Schlüssels benötigen, müssen Sie auch die Berechtigungen ändern. Dieser Gruppe von Schlüsseltresor-Mitwirkenden muss die Rolle **Mitwirkender** für Ihren Schlüsseltresor zugewiesen werden. Sie können diese Rolle mithilfe des Azure-Ressourcenmanagers zuweisen. Informationen zu den einzelnen Schritten finden Sie unter [Verwenden der rollenbasierten Zugriffssteuerung zum Verwalten des Zugriffs auf Ihre Azure-Abonnementressourcen](/azure/active-directory/role-based-access-control-configure). Der Administrator, der ein Abonnement erstellt, verfügt implizit über diesen Zugriff und die Möglichkeit, andere Administratoren der Mitwirkendenrolle zuzuordnen.

- **Berechtigungen zum Microsoft 365** von Anwendungen für jeden Schlüsseltresor, den Sie für Den Kundenschlüssel verwenden, müssen Sie wrapKey, unwrapKey erteilen und Berechtigungen für den entsprechenden Microsoft 365-Dienstprinzipal erhalten. 

Führen Sie zum Erteilen Microsoft 365 Dienstprinzipal das **Cmdlet Set-AzKeyVaultAccessPolicy** mit der folgenden Syntax aus:

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
   ```

   Dabei gilt:

   - *Vaultname* ist der Name des schlüsseltresor, den Sie erstellt haben.
   - Für Exchange Online und Skype for Business ersetzen Sie bitte die *Office 365 App-ID* durch `00000002-0000-0ff1-ce00-000000000000`
   - Für SharePoint Online-, OneDrive for Business- und Teams ersetzen Sie *Office 365 appID* durch`00000003-0000-0ff1-ce00-000000000000`
   - Ersetzen Sie bei Richtlinien mit mehreren Arbeitsauslastungen (Exchange, Teams, MIP EDM), die für alle Mandantenbenutzer gelten, Office 365 *appID* durch`c066d759-24ae-40e7-a56f-027002b5d3e4`

  Beispiel: Festlegen von Berechtigungen für Exchange Online und Skype for Business:

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-CK-EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
   ```

  Beispiel: Festlegen von Berechtigungen für SharePoint Online-, OneDrive for Business- und Teams Dateien:

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-CK-SP-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
   ```

### <a name="make-sure-soft-delete-is-enabled-on-your-key-vaults"></a>Stellen Sie sicher, dass das soft delete für Ihre Schlüsseltresor aktiviert ist.

Wenn Sie Ihre Schlüssel schnell wiederherstellen können, ist ein umfassender Dienstausfalls aufgrund von versehentlich oder in böswilliger Absicht gelöschten Schlüsseln weniger wahrscheinlich. Aktivieren Sie diese Konfiguration, die als Soft Delete bezeichnet wird, bevor Sie Ihre Schlüssel mit dem Kundenschlüssel verwenden können. Das Aktivieren von Soft Delete ermöglicht Ihnen des Wiederherstellen von Schlüsseln oder Tresoren innerhalb von 90 Tagen nach dem Löschen, ohne diese aus der Datensicherung wiederherstellen zu müssen.
  
Führen Sie die folgenden Schritte aus, um Soft Delete für Ihre Schlüsseltresore zu aktivieren:
  
1. Melden Sie sich bei Ihrem Azure-Abonnement mit Windows PowerShell. Anweisungen finden Sie unter [Sign in with Azure PowerShell](/powershell/azure/authenticate-azureps).

2. Führen Sie [das Cmdlet Get-AzKeyVault](/powershell/module/az.keyvault/get-azkeyvault) aus. In diesem Beispiel ist *der Name des* Tresors der Schlüssel, für den Sie das soft delete aktivieren:

   ```powershell
   $v = Get-AzKeyVault -VaultName <vault name>
   $r = Get-AzResource -ResourceId $v.ResourceId
   $r.Properties | Add-Member -MemberType NoteProperty -Name enableSoftDelete -Value 'True'
   Set-AzResource -ResourceId $r.ResourceId -Properties $r.Properties
   ```

3. Bestätigen Sie, dass das soft delete für den Schlüsseltresor konfiguriert ist, indem Sie das **Cmdlet Get-AzKeyVault** ausführen. Wenn das soft delete für den Schlüsseltresor ordnungsgemäß konfiguriert ist, gibt die _Eigenschaft Soft Delete Enabled_ den Wert True **zurück:**

   ```powershell
   Get-AzKeyVault -VaultName <vault name> | fl
   ```

### <a name="add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key"></a>Hinzufügen eines Schlüssels zu jedem Schlüsseltresor durch das Erstellen oder Importieren eines Schlüssels

Es gibt zwei Methoden zum Hinzufügen von Schlüsseln zu einem Azure Key Vault. Sie können entweder direkt im Schlüsseltresor einen Schlüssel erstellen oder aber einen Schlüssel importieren. Das Erstellen eines Schlüssels direkt in Key Vault ist weniger kompliziert, aber das Importieren eines Schlüssels bietet eine totale Kontrolle darüber, wie der Schlüssel generiert wird. Verwenden Sie die RSA-Schlüssel. Azure Key Vault unterstützt das Um- und Auspacken mit elliptischen Kurventasten nicht.
  
Führen Sie das [Cmdlet Add-AzKeyVaultKey](/powershell/module/az.keyvault/add-azkeyvaultkey) wie folgt aus, um einen Schlüssel direkt in Ihrem Schlüsseltresor zu erstellen:
  
```powershell
Add-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Destination <HSM|Software> -KeyOps wrapKey,unwrapKey
```

Dabei gilt:

- *Vaultname* ist der Name des Schlüsseltresor, in dem Sie den Schlüssel erstellen möchten.

- *Schlüsselname* ist der Name, den Sie dem neuen Schlüssel geben möchten.

  > [!TIP]
  > Benennen Sie Schlüssel, die eine ähnliche Benennungskonvention verwenden, nach dem oben für Schlüsseltresore beschriebenen Verfahren. Auf diese Weise ist die Zeichenfolge in Tools, die lediglich den Schlüsselnamen anzeigen, selbsterklärend.
  
Wenn Sie den Schlüssel mit einem HSM schützen möchten, stellen Sie sicher, dass Sie **HSM** als Wert des _Parameters Destination_ angeben, andernfalls Geben Sie **Software an.**

Beispiel:
  
```powershell
Add-AzKeyVaultKey -VaultName Contoso-CK-EX-NA-VaultA1 -Name Contoso-CK-EX-NA-VaultA1-Key001 -Destination HSM -KeyOps wrapKey,unwrapKey
```

Um einen Schlüssel direkt in Ihren Schlüsseltresor zu importieren, benötigen Sie ein nCipher nShield Hardware Security Module.
  
Einige Organisationen bevorzugen diesen Ansatz, um die Provenienz ihrer Schlüssel zu erstellen, und dann stellt diese Methode auch die folgenden Nachweise zur Folge:
  
- Das für den Import verwendete Toolset enthält die Bestätigung von nCipher, dass der Key Exchange Key (KEK), der zum Verschlüsseln des generierten Schlüssels verwendet wird, nicht exportierbar ist und in einem echten HSM generiert wird, das von nCipher hergestellt wurde.

- Das Toolset enthält die Bestätigung von nCipher, dass die Azure Key Vault-Sicherheitswelt auch auf einem echten HSM generiert wurde, das von nCipher hergestellt wurde. Diese Bestätigung belegt, dass Microsoft auch echte nCipher-Hardware verwendet.

Wenden Sie sich an Ihr Sicherheitsteam, um festzustellen, ob die vorstehenden Bescheinigungen erforderlich sind. Detaillierte Anweisungen zum Erstellen eines lokalen Schlüssels und zum Importieren in Ihren Schlüsseltresor finden Sie unter [Generieren und Übertragen von HSM-geschützten Schlüsseln für Azure Key Vault](/azure/key-vault/keys/hsm-protected-keys). Folgen Sie den Azure-Anweisungen, um in jedem Schlüsseltresor einen Schlüssel zu erstellen.
  
### <a name="check-the-recovery-level-of-your-keys"></a>Überprüfen der Wiederherstellungsebene Ihrer Schlüssel

Microsoft 365 erfordert, dass das Azure Key Vault-Abonnement auf Do Not Cancel festgelegt ist und dass für die vom Kundenschlüssel verwendeten Schlüssel das soft delete aktiviert ist. Sie können Die Abonnementeinstellungen bestätigen, indem Sie sich die Wiederherstellungsstufe ihrer Schlüssel anschauen.
  
Führen Sie zum Überprüfen der Wiederherstellungsstufe eines Schlüssels in Azure PowerShell das cmdlet Get-AzKeyVaultKey wie folgt aus:
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes
```

Wenn die _Recovery Level-Eigenschaft_ einen anderen Wert als den Wert **"Recoverable+ProtectedSubscription"** zurückgibt, stellen Sie sicher, dass Sie das Abonnement in die Liste Nicht abbrechen aufgenommen haben und für jeden Schlüsseltresor das soft delete aktiviert haben.
  
### <a name="back-up-azure-key-vault"></a>Sichern von Azure Key Vault

Unmittelbar nach dem Erstellen oder Ändern eines Schlüssels, dem Durchführen einer Sicherung und dem Speichern von Kopien der Sicherung, sowohl online als auch offline. Verbinden Sie keine Offlinekopien mit einem Netzwerk. Speichern Sie sie stattdessen an einem Offlinespeicherort, z. B. in einem physischen sicheren oder kommerziellen Speicher. Mindestens eine Kopie der Sicherung sollte an einem Speicherort gespeichert werden, auf den bei einem Notfall zugegriffen werden kann. Die einzelnen Sicherungen sind die einzige Möglichkeit zum Wiederherstellen des Schlüsselmaterials, sollte ein Key-Vault-Schlüssel dauerhaft vernichtet oder auf andere Weise funktionsuntüchtig gemacht worden sein. Schlüssel, die sich außerhalb von Azure Key Vault befinden und in Azure Key Vault importiert werden, gelten nicht als Sicherung, da die Metadaten, die für die Verwendung des Schlüssels durch den Kundenschlüssel erforderlich sind, nicht mit dem externen Schlüssel vorhanden sind. Nur eine vom Azure Key Vault erstellte Sicherung kann für Wiederherstellungsvorgänge mit Customer Key verwendet werden. Daher müssen Sie eine Sicherung von Azure Key Vault erstellen, nachdem Sie einen Schlüssel hochgeladen oder erstellt haben.
  
Führen Sie zum Erstellen einer Sicherung eines Azure Key Vault-Schlüssels das [Cmdlet Backup-AzKeyVaultKey](/powershell/module/az.keyvault/backup-azkeyvaultkey) wie folgt aus:

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
Backup-AzKeyVaultKey -VaultName Contoso-CK-EX-NA-VaultA1 -Name Contoso-CK-EX-NA-VaultA1-Key001 -OutputFile Contoso-CK-EX-NA-VaultA1-Key001-Backup-20170802.backup
```

### <a name="validate-azure-key-vault-configuration-settings"></a>Konfigurationseinstellungen von Azure Key Vault verifizieren

Das Überprüfen vor der Verwendung von Schlüsseln in einer DEP ist optional, wird jedoch dringend empfohlen. Wenn Sie die in diesem Artikel beschriebenen Schritte zum Einrichten ihrer Schlüssel und Tresore verwenden, überprüfen Sie den Integritätszustand Ihrer Azure Key Vault-Ressourcen, bevor Sie Den Kundenschlüssel konfigurieren.
  
So stellen Sie sicher, dass für Ihre Schlüssel `get` `wrapKey` , und `unwrapKey` -Vorgänge aktiviert sind:
  
Führen Sie [das Cmdlet Get-AzKeyVault](/powershell/module/az.keyvault/get-azkeyvault) wie folgt aus:
  
```powershell
Get-AzKeyVault -VaultName <vault name>
```

Suchen Sie in der Ausgabe nach der Zugriffsrichtlinie und, je nach Bedarf, nach der Exchange Online-Identität (GUID) bzw. der SharePoint Online Identity (GUID). Alle drei vorstehenden Berechtigungen müssen unter den Berechtigungen für Schlüssel angezeigt werden.
  
Wenn die Zugriffsrichtlinienkonfiguration falsch ist, führen Sie das cmdlet Set-AzKeyVaultAccessPolicy wie folgt aus:
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
```

Beispielsweise für Exchange Online und Skype for Business:
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName Contoso-CK-EX-NA-VaultA1 
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
```

Beispielsweise für SharePoint Online und OneDrive for Business:
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName Contoso-CK-SP-NA-VaultA1
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
```

Führen Sie das [Cmdlet Get-AzKeyVaultKey](/powershell/module/az.keyvault/get-azkeyvault) wie folgt aus, um zu überprüfen, ob für Ihre Schlüssel kein Ablaufdatum festgelegt ist:
  
```powershell
Get-AzKeyVaultKey -VaultName <vault name>
```

Der Kundenschlüssel kann keinen abgelaufenen Schlüssel verwenden. Vorgänge, die mit einem abgelaufenen Schlüssel versucht werden, führen zu einem Fehler und führen möglicherweise zu einem Dienstausfall. Es wird dringend empfohlen, dass schlüssel, die mit dem Kundenschlüssel verwendet werden, kein Ablaufdatum haben. Ein einmal festgelegtes Ablaufdatum kann nicht gelöscht werden, es kann jedoch eine Datumänderung vorgenommen werden. Wenn ein Schlüssel verwendet werden muss, für den ein Ablaufdatum festgelegt ist, ändern Sie bitte das Ablaufdatum auf 31.12.9999. Schlüssel mit einem Ablaufdatum, das auf ein anderes Datum als den 31.12.9999 festgelegt ist, bestehen Microsoft 365 Überprüfung.
  
Führen Sie das [Cmdlet Update-AzKeyVaultKey](/powershell/module/az.keyvault/update-azkeyvaultkey) wie folgt aus, um ein Ablaufdatum zu ändern, das auf einen anderen Wert als den 31.12.9999 festgelegt wurde:
  
```powershell
Update-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Expires (Get-Date -Date "12/31/9999")
```

> [!CAUTION]
> Legen Sie keine Ablaufdaten für kryptografische Schlüssel fest, die Sie mit Customer Key verwenden.
  
### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a>Abrufen eines URI für jeden Azure Key Vault-Schlüssel

Nachdem Sie Ihre Schlüsseltresor eingerichtet und Ihre Schlüssel hinzugefügt haben, führen Sie den folgenden Befehl aus, um den URI für den Schlüssel in jedem Schlüsseltresor zu erhalten. Sie verwenden diese URIs, wenn Sie jede DEP später erstellen und zuweisen, speichern Sie diese Informationen also an einem sicheren Ort. Führen Sie diesen Befehl einmal für jeden Schlüsseltresor aus.
  
In Azure PowerShell:
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name>).Id
```

## <a name="next-steps"></a>Nächste Schritte

Nachdem Sie die Schritte in diesem Artikel abgeschlossen haben, können Sie DEPs erstellen und zuweisen. Anweisungen finden Sie unter [Manage Customer Key](customer-key-manage.md).

## <a name="related-articles"></a>Verwandte Artikel

- [Dienstverschlüsselung mit Kundenschlüssel](customer-key-overview.md)

- [Verwalten des Kundenschlüssels](customer-key-manage.md)

- [Rollen oder Drehen eines Kundenschlüssels oder eines Verfügbarkeitsschlüssels](customer-key-availability-key-roll.md)

- [Informationen zum Verfügbarkeitsschlüssel](customer-key-availability-key-understand.md)

- [Dienstverschlüsselung](office-365-service-encryption.md)