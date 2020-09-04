---
title: Allgemeine Richtlinien für Identitäts-und Geräte Zugriff – Microsoft 365 für Unternehmen | Microsoft-Dokumente
description: Beschreibt die empfohlenen allgemeinen Richtlinien und Konfigurationen für den Identitäts-und Geräte Zugriff.
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- remotework
ms.openlocfilehash: 4cbc4ceec734587137a284dd800f77b712c0168d
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358018"
---
# <a name="common-identity-and-device-access-policies"></a>Allgemeine Identitäts- und Gerätezugriffsrichtlinien
In diesem Artikel werden die allgemeinen empfohlenen Richtlinien für die Sicherung des Zugriffs auf Cloud-Dienste beschrieben, einschließlich lokaler Anwendungen, die mit Azure Active Directory (Azure AD)-Anwendungs Proxy veröffentlicht werden. 

In diesem Leitfaden wird erläutert, wie die empfohlenen Richtlinien in einer neu bereitgestellten Umgebung bereitgestellt werden. Durch das Einrichten dieser Richtlinien in einer separaten Lab-Umgebung können Sie die empfohlenen Richtlinien vor dem Staging in ihren Vorprodukt-und Produktionsumgebungen verstehen und auswerten. Ihre neu bereitgestellte Umgebung ist möglicherweise nur in der Cloud oder Hybrid.  

## <a name="policy-set"></a>Richtliniengruppe 

Das folgende Diagramm zeigt die empfohlenen Richtlinien. Es wird angezeigt, auf welcher Schutzebene jede Richtlinie angewendet wird und ob die Richtlinien auf PCs oder Telefone und Tablets oder auf beide Gerätekategorien zutreffen. Außerdem wird angegeben, wo Sie diese Richtlinien konfigurieren.

[ ![ Allgemeine Richtlinien für das Konfigurieren von Identitäts-und Geräte Zugriff](../media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png) 
 [Siehe eine größere Version dieses Abbilds](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)

Im Rest dieses Artikels wird beschrieben, wie Sie diese Richtlinien konfigurieren. 

>[!Note]
>Das Erfordernis der Verwendung von mehrstufiger Authentifizierung (MFA) wird empfohlen, bevor Geräte in InTune registriert werden, um sicherzustellen, dass das Gerät im Besitz des beabsichtigten Benutzers ist. Sie müssen Geräte in InTune registrieren, bevor Sie Geräte Konformitätsrichtlinien erzwingen können.
>

Um Ihnen Zeit zum Ausführen dieser Aufgaben zu geben, empfehlen wir, die Basisrichtlinien in der in dieser Tabelle aufgeführten Reihenfolge zu implementieren. Die MFA-Richtlinien für vertrauliche und hochgradig geregelte Schutzniveaus können jedoch jederzeit implementiert werden.

|Schutzebene|Richtlinien|Weitere Informationen|
|:---------------|:-------|:----------------|
|**Basisplan**|[MFA erforderlich, wenn das Anmelde Risiko *Mittel* groß oder *hoch* ist](#require-mfa-based-on-sign-in-risk)| |
|        |[Blockieren von Clients, die die moderne Authentifizierung nicht unterstützen](#block-clients-that-dont-support-modern-authentication)|Clients, die keine moderne Authentifizierung verwenden, können Richtlinien für bedingten Zugriff umgehen, daher ist es wichtig, diese zu blockieren.|
|        |[Nutzer mit hohem Risiko müssen das Kennwort ändern](#high-risk-users-must-change-password)|Zwingt Benutzer, Ihr Kennwort zu ändern, wenn Sie sich anmelden, wenn hochriskante Aktivitäten für Ihr Konto erkannt werden.|
|        |[Anwenden von App-Datenschutzrichtlinien](#apply-app-data-protection-policies)|Eine InTune-App-Schutzrichtlinie pro Plattform (Windows, IOS/iPads, Android).|
|        |[Erfordern von genehmigten apps und App-Schutz](#require-approved-apps-and-app-protection)|Erzwingt Mobile App Schutz für Telefone und Tablets mit IOS, iPads oder Android.|
|        |[Definieren von Geräte Konformitätsrichtlinien](#define-device-compliance-policies)|Eine Richtlinie für jede Plattform.|
|        |[Kompatible PCs erforderlich](#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Erzwingt die Intune-Verwaltung von PCs mithilfe von Windows oder MacOS.|
|**Vertraulich**|[MFA erforderlich, wenn das Anmelde Risiko *niedrig*, *Mittel*oder *hoch* ist](#require-mfa-based-on-sign-in-risk)| |
|         |[Erfordern von kompatiblen PCs *und* mobilen Geräten](#require-compliant-pcs-and-mobile-devices)|Erzwingt die Intune-Verwaltung für PCs (Windows oder MacOS) sowie für Telefone oder Tablets (Ios, iPads oder Android).|
|**Streng geregelt**|[*Immer* MFA erforderlich](#require-mfa-based-on-sign-in-risk)|
| | |

## <a name="assigning-policies-to-groups-and-users"></a>Zuweisen von Richtlinien zu Gruppen und Benutzern

Identifizieren Sie vor dem Konfigurieren von Richtlinien die Azure Ad Gruppen, die Sie für jede Schutzebene verwenden. Normalerweise gilt der Basisplan-Schutz für alle in der Organisation. Für einen Benutzer, der sowohl für den grundlegenden als auch für den vertraulichen Schutz enthalten ist, werden alle grundlegenden Richtlinien sowie die vertraulichen Richtlinien angewendet. Der Schutz ist kumulativ, und die restriktivste Richtlinie wird erzwungen. 

Eine empfohlene Vorgehensweise besteht darin, eine Azure Ad Gruppe für bedingten Zugriffs Ausschluss zu erstellen. Fügen Sie diese Gruppe zu allen bedingten Zugriffsregeln unter "ausschließen" hinzu. Dadurch erhalten Sie eine Methode zum Bereitstellen des Zugriffs auf einen Benutzer, während Sie Zugriffsprobleme beheben. Dies wird nur als temporäre Lösung empfohlen. Überwachen Sie diese Gruppe auf Änderungen, und stellen Sie sicher, dass die Ausschlussgruppe nur wie beabsichtigt verwendet wird. 

Im folgenden finden Sie ein Beispiel für Gruppenzuweisung und-Ausschlüsse für die Notwendigkeit eines MFA.

![Beispiel für Gruppenzuweisung und-Ausschlüsse für MFA-Regeln](../media/microsoft-365-policies-configurations/identity-access-policies-assignment.png)

Hier sind die Ergebnisse:

- Alle Benutzer müssen MFA verwenden, wenn das Anmelde Risiko Mittel oder hoch ist.

- Mitglieder der Gruppe "Führungskräfte" müssen MFA verwenden, wenn das Anmelde Risiko niedrig, Mittel oder hoch ist.

  In diesem Fall entsprechen Mitglieder der Gruppe der Führungskräfte sowohl den grundlegenden als auch den vertraulichen Richtlinien für bedingten Zugriff. Die Zugriffssteuerung für beide Richtlinien wird kombiniert, was in diesem Fall der Richtlinie für vertraulichen bedingten Zugriff entspricht.

- Mitglieder der streng geheimen Project X-Gruppe sind immer für die Verwendung von MFA erforderlich.

  In diesem Fall entsprechen Mitglieder der streng geheimen Projekt X-Gruppe sowohl den grundlegenden als auch streng regulierten Richtlinien für bedingten Zugriff. Die Zugriffssteuerung für beide Richtlinien wird kombiniert. Da die Zugriffssteuerung für die streng geregelte Richtlinie für den bedingten Zugriff restriktiver ist, wird Sie verwendet.

Seien Sie vorsichtig, wenn Sie Gruppen und Benutzern höhere Schutzebenen zuweisen. Mitglieder der streng geheimen Projekt x-Gruppe müssen beispielsweise jedes Mal, wenn Sie sich anmelden, MFA verwenden, auch wenn Sie nicht an hoch regulierten Inhalten für Project x arbeiten.  

Alle Azure Ad Gruppen, die als Teil dieser Empfehlungen erstellt wurden, müssen als Microsoft 365-Gruppen erstellt werden. Dies ist wichtig für die Bereitstellung von Sensitivitäts Bezeichnungen beim Sichern von Dokumenten in Microsoft Teams und SharePoint Online.

![Bildschirmaufnahme zum Erstellen von Microsoft 365-Gruppen](../media/microsoft-365-policies-configurations/identity-device-AAD-groups.png)

## <a name="require-mfa-based-on-sign-in-risk"></a>MFA basierend auf dem Anmelde Risiko erforderlich

Sie sollten Ihre Benutzer für MFA registrieren lassen, bevor Sie Ihre Verwendung benötigen. Wenn Sie Microsoft 365 E5, Microsoft 365 E3 mit dem Identity & Threat Protection-Add-on, Office 365 mit EMS E5 oder einzelnen Azure AD Premium P2-Lizenzen haben, können Sie die MFA-Registrierungsrichtlinie mit Azure AD Identitätsschutz verwenden, um die Registrierung von Benutzern für MFA zu verlangen. Die [erforderliche Arbeit](identity-access-prerequisites.md) umfasst das Registrieren aller Benutzer mit MFA.

Nachdem Ihre Benutzer registriert wurden, können Sie die MFA für die Anmeldung benötigen.

So erstellen Sie eine neue Richtlinie für bedingten Zugriff: 

1. Navigieren Sie zum [Azure-Portal](https://portal.azure.com), und melden Sie sich mit Ihren Anmeldeinformationen an.

2. Wählen Sie in der Liste der Azure-Dienste die Option **Azure Active Directory**aus.

3. Wählen Sie in der Liste **Verwalten** die Option **Sicherheit**aus, und wählen Sie dann **bedingter Zugriff**aus.

4. Wählen Sie **neue Richtlinie** aus, und geben Sie den Namen der neuen Richtlinie ein.

In den folgenden Tabellen werden die Richtlinieneinstellungen für den bedingten Zugriff beschrieben, um MFA basierend auf dem Anmelde Risiko zu erfordern.

Im Abschnitt **Zuweisungen** :

|Einstellung|Eigenschaften|Werte|Hinweise|
|:---|:---------|:-----|:----|
|Benutzer und Gruppen|Einschließen| **Wählen Sie Benutzer und Gruppen > Benutzer und Gruppen**aus: bestimmte Gruppen mit Zielbenutzer Konten auswählen. |Beginnen Sie mit der Gruppe, die Pilotbenutzer Konten enthält.|
||Ausschließen| **Benutzer und Gruppen**: Wählen Sie die Ausnahmegruppe für bedingten Zugriff aus. Dienstkonten (app-Identitäten).|Die Mitgliedschaft sollte auf der Grundlage der erforderlichen, temporären Änderungen geändert werden.|
|Cloud-Apps oder-Aktionen|Include| **Auswählen von apps**: Wählen Sie die Apps aus, auf die diese Regel angewendet werden soll. Wählen Sie beispielsweise Exchange Online aus.||
|Bedingungen| | |Konfigurieren Sie Bedingungen, die für Ihre Umgebung und Ihre Anforderungen spezifisch sind.|
||Anmelderisiko||Lesen Sie den Leitfaden in der folgenden Tabelle.|
|||||

**Einstellungen für die Anmeldungs Risikobedingung**

Wenden Sie die Einstellungen für die Risikostufe basierend auf der Schutzebene an, auf die Sie Zielen.

|Schutzniveau|Erforderliche Risikostufen Werte|Aktion|
|:---------|:-----|:----|
|Baseline|Hoch, Mmittel|Überprüfen Sie beides.|
|Vertraulich|Hoch, Mittel, niedrig|Überprüfen Sie alle drei.|
|Streng geregelt| |Lassen Sie alle Optionen deaktiviert, damit MFA immer erzwungen wird.|
||||

Im Abschnitt **Zugriffssteuerungen** :

|Einstellung|Eigenschaften|Werte|Aktion|
|:---|:---------|:-----|:----|
|Gewähren|**Grant access**| | Auswählen |
|||**Mehrstufige Authentifizierung erforderlich**| Prüfen |
||**Alle ausgewählten Steuerelemente erforderlich** ||Auswählen|
|||||

Wählen **Sie auswählen aus** , um die **Berechtigungs** Einstellungen zu speichern.

Wählen Sie schließlich für **Richtlinie aktivieren** **aus.**

In diesem Fall sollten Sie auch das [What-if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) -Tool zum Testen der Richtlinie verwenden.


## <a name="block-clients-that-dont-support-modern-authentication"></a>Sperrt Clients, die moderne Authentifizierung nicht unterstützen

Verwenden Sie die Einstellungen in diesen Tabellen für eine Richtlinie für den bedingten Zugriff, um Clients zu blockieren, die die moderne Authentifizierung nicht unterstützen.

Im Abschnitt **Zuweisungen** :

|Typ|Eigenschaften|Werte|Hinweise|
|:---|:---------|:-----|:----|
|Benutzer und Gruppen|Einschließen|Wählen Sie Benutzer und Gruppen aus: Wählen Sie eine spezifische Sicherheitsgruppe aus, die Zielbenutzer enthält.|Beginnen Sie mit der Sicherheitsgruppe einschließlich Pilotbenutzer|
||Ausschließen|Ausnahmesicherheitsgruppe, Dienstkonten (App-Identitäten)|Mitgliedschaft, die auf vorübergehender, bedarfsmäßiger Basis geändert wird|
|Cloud-Apps|Einschließen|Wählen Sie die Apps aus, auf die diese Regel angewendet werden soll. Wählen Sie beispielsweise Exchange Online||
|Bedingungen|Konfigurierte|Ja|Konfigurieren von Client-apps|
|Client-Apps|Konfigurierte|Ja|Mobile Apps und Desktop Clients, andere Clients (Wählen Sie beides aus)|

Im Abschnitt **Zugriffssteuerungen** :

|Typ|Eigenschaften|Werte|Hinweise|
|:---|:---------|:-----|:----|
|Gewähren|Zugriff blockieren|True|Ausgewählt|
||MFA erforderlich|Falsch||
||Gerät muss als konform gekennzeichnet werden|Falsch||
||Hybrides Azure AD verbundenes Gerät erforderlich|Falsch||
||Genehmigte Client-App erforderlich|False||
||Alle ausgewählten Steuerelemente erforderlich|True|Ausgewählt|

> [!NOTE]
> Stellen Sie sicher, dass Sie diese Richtlinie aktivieren, indem Sie **auf**auswählen. In diesem Fall sollten Sie auch das [What-if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) -Tool zum Testen der Richtlinie verwenden.



## <a name="high-risk-users-must-change-password"></a>Nutzer mit hohem Risiko müssen das Kennwort ändern
Um sicherzustellen, dass alle gefährdeten Benutzerkonten mit hohem Risiko gezwungen werden, beim Anmelden eine Kennwortänderung durchzuführen, müssen Sie die folgende Richtlinie anwenden.

Melden Sie sich im [Microsoft Azure-Portal (https://portal.azure.com)](https://portal.azure.com/) mit Ihren Administratoranmeldeinformationen an, und wechseln Sie dann zu **Azure AD Identity Protection > Richtlinie zum Benutzerrisiko**.

**Assignments**

|Typ|Eigenschaften|Werte|Hinweise|
|:---|:---------|:-----|:----|
|Users|Einschließen|Alle Benutzer|Ausgewählt|
||Ausschließen|Keine||
|Bedingungen|Benutzerrisiko|Hoch|Ausgewählt|

**Steuerelemente**

| Typ | Eigenschaften | Werte                  | Hinweise |
|:-----|:-----------|:------------------------|:------|
|      | Zugriff     | Zugriff zulassen            | True  |
|      | Zugriff     | Kennwortänderung erforderlich | True  |

**Überprüfung:** nicht zutreffend

> [!NOTE]
> Stellen Sie sicher, dass Sie diese Richtlinie aktivieren, indem Sie **auf**auswählen. Sie sollten auch das [What-if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) -Tool zum Testen der Richtlinie verwenden.

## <a name="apply-app-data-protection-policies"></a>Anwenden von App-Datenschutzrichtlinien
App-Schutzrichtlinien (app) definieren, welche apps zulässig sind und welche Aktionen Sie mit den Daten Ihrer Organisation durchführen können. Mit den in App verfügbaren Auswahlmöglichkeiten können Organisationen den Schutz ihren spezifischen Anforderungen anpassen. Für einige ist es möglicherweise nicht offensichtlich, welche Richtlinieneinstellungen erforderlich sind, um ein vollständiges Szenario zu implementieren. Um Organisationen die Priorisierung mobiler Clientendpunkte zu erleichtern, hat Microsoft die Taxonomie für das App-Datenschutz Framework für IOS-und Android-Mobile App Verwaltung eingeführt. 

Das App Data Protection-Framework ist in drei unterschiedliche Konfigurationsebenen unterteilt, wobei jede Ebene die vorherige Ebene abbaut: 

- **Enterprise Basic Data Protection** (Level 1) stellt sicher, dass apps mit einer PIN geschützt und verschlüsselt und selektive Löschvorgänge ausgeführt werden. Für Android-Geräte überprüft diese Stufe die Beglaubigung von Android-Geräten. Hierbei handelt es sich um eine Einstiegskonfiguration, die eine ähnliche Datenschutz Steuerung in Exchange Online Postfachrichtlinien bereitstellt und die Benutzerpopulation in die APP einführt. 
- **Unter Enterprise Enhanced Data Protection** (Level 2) werden Präventionsmechanismen für App-Daten Leckagen und Mindestanforderungen für BS eingeführt. Dies ist die Konfiguration, die für die meisten mobilen Benutzer gilt, die auf Arbeits-oder Schuldaten zugreifen. 
- **Unter Enterprise High Data Protection** (Stufe 3) werden erweiterte Datenschutzmechanismen, erweiterte Pin-Konfiguration und Verteidigung der mobilen App-Bedrohungen eingeführt. Diese Konfiguration ist für Benutzer, die auf Daten mit hohem Risiko zugreifen, wünschenswert. 

Informationen zu den spezifischen Empfehlungen für jede Konfigurationsebene und zu den minimalen apps, die geschützt werden müssen, finden Sie unter [Data Protection Framework mithilfe von App-Schutzrichtlinien](https://docs.microsoft.com/mem/intune/apps/app-protection-framework). 

Anhand der in den Konfigurationen für den [Identitäts-und Geräte Zugriff](microsoft-365-policies-configurations.md)beschriebenen Prinzipien werden die grundlegenden und sensiblen Schutzebenen eng mit den Einstellungen der Stufe 2 Enterprise Enhanced Data Protection zugeordnet. Die hochregulierte Schutzebene ordnet sich eng mit den Einstellungen der Stufe 3 Enterprise High Data Protection an.

|Schutzebene |App-Schutzrichtlinie  |Weitere Informationen  |
|---------|---------|---------|
|Baseline     | [Stufe 2 erweiterter Datenschutz](https://docs.microsoft.com/mem/intune/apps/app-protection-framework#level-2-enterprise-enhanced-data-protection)        | Die Richtlinieneinstellungen in Ebene 2 enthalten alle Richtlinieneinstellungen, die für Stufe 1 empfohlen werden, und die folgenden Richtlinieneinstellungen werden nur hinzugefügt oder aktualisiert, um weitere Steuerelemente und eine anspruchsvollere Konfiguration als Ebene 1 zu implementieren.         |
|Vertraulich     | [Stufe 2 erweiterter Datenschutz](https://docs.microsoft.com/mem/intune/apps/app-protection-framework#level-2-enterprise-enhanced-data-protection)        | Die Richtlinieneinstellungen in Ebene 2 enthalten alle Richtlinieneinstellungen, die für Stufe 1 empfohlen werden, und die folgenden Richtlinieneinstellungen werden nur hinzugefügt oder aktualisiert, um weitere Steuerelemente und eine anspruchsvollere Konfiguration als Ebene 1 zu implementieren.        |
|Stark reguliert     | [Stufe 3 Enterprise High Data Protection](https://docs.microsoft.com/mem/intune/apps/app-protection-framework#level-3-enterprise-high-data-protection)        | Die Richtlinieneinstellungen in Stufe 3 umfassen alle Richtlinieneinstellungen, die für Stufe 1 und 2 empfohlen werden, und nur die unten aufgeführten Richtlinieneinstellungen hinzugefügt oder aktualisiert, um weitere Steuerelemente und eine anspruchsvollere Konfiguration als Ebene 2 zu implementieren.        |

Um eine neue APP-Schutzrichtlinie für jede Plattform (IOS und Android) in Microsoft Endpoint Manager mithilfe der Data Protection Framework-Einstellungen zu erstellen, können Administratoren Folgendes tun:
1. Erstellen Sie die Richtlinien manuell, indem Sie die Schritte unter [Vorgehensweise erstellen und Bereitstellen von App-Schutzrichtlinien mit Microsoft InTune](https://docs.microsoft.com/mem/intune/apps/app-protection-policies)ausführen. 
2. Importieren Sie die JSON-Vorlagen für das Beispiel [InTune-App-Schutzrichtlinien-Konfigurations Framework](https://github.com/microsoft/Intune-Config-Frameworks/tree/master/AppProtectionPolicies) mit [InTune-PowerShell-Skripts](https://github.com/microsoftgraph/powershell-intune-samples).

## <a name="require-approved-apps-and-app-protection"></a>Erfordern von genehmigten apps und App-Schutz
Zum Erzwingen der APP-Schutzrichtlinien, die Sie in InTune angewendet haben, müssen Sie eine Regel für bedingten Zugriff erstellen, um genehmigte Client-apps und die in den App-Schutzrichtlinien festgelegten Bedingungen zu erfordern. 

Das Erzwingen von App-Schutzrichtlinien erfordert eine Reihe von Richtlinien, die unter in [erfordern von App-Schutzrichtlinien für Cloud-App-Zugriff mit bedingtem Zugriff](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access)beschrieben werden. Diese Richtlinien sind jeweils in dieser empfohlenen Gruppe von Richtlinien für Identitäts-und Zugriffs Konfigurationen enthalten.

Um die Regel für bedingten Zugriff zu erstellen, für die genehmigte apps und App-Schutz erforderlich sind, führen Sie "Schritt 1: Konfigurieren einer Azure AD Richtlinie für den bedingten Zugriff für Microsoft 365" in [Szenario 1: Microsoft 365-apps erfordern genehmigte apps mit App-Schutzrichtlinien](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies), die Outlook für IOS und Android ermöglichen, aber verhindert, dass OAuth-fähige Exchange ActiveSync-Clients eine Verbindung Exchange Online mit

   > [!NOTE]
   > Diese Richtlinie stellt sicher, dass Mobile Benutzer mithilfe der entsprechenden apps auf alle Office-Endpunkte zugreifen können.

Wenn Sie mobilen Zugriff auf Exchange Online ermöglichen, implementieren Sie [Blockieren von ActiveSync-Clients](secure-email-recommended-policies.md#block-activesync-clients), wodurch verhindert wird, dass Exchange ActiveSync-Clients die Standardauthentifizierung für die Verbindung mit Exchange Online nutzen. Diese Richtlinie wird in der Abbildung oben in diesem Artikel nicht abgebildet. Sie wird in [Richtlinien Empfehlungen zum Sichern von e-Mails](secure-email-recommended-policies.md)beschrieben und abgebildet.

 Diese Richtlinien nutzen die Grant-Steuerelemente [erfordern eine genehmigte Client-App](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-approved-client-app) und [erfordern eine APP-Schutzrichtlinie](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy).

Schließlich wird durch das Blockieren der Legacy Authentifizierung für andere Client-apps auf IOS-und Android-Geräten sichergestellt, dass diese Clients keine bedingten Zugriffsregeln umgehen können. Wenn Sie die Anleitungen in diesem Artikel befolgen, haben Sie bereits [Blockierte Clients konfiguriert, die die moderne Authentifizierung nicht unterstützen](#block-clients-that-dont-support-modern-authentication).

<!---
With Conditional Access, organizations can restrict access to approved (modern authentication capable) iOS and Android client apps with Intune app protection policies applied to them. Several Conditional Access policies are required, with each policy targeting all potential users. Details on creating these policies can be found in [Require app protection policy for cloud app access with Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access).

1. Follow "Step 1: Configure an Azure AD Conditional Access policy for Microsoft 365" in [Scenario 1: Microsoft 365 apps require approved apps with app protection policies](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies), which allows Outlook for iOS and Android, but blocks OAuth capable Exchange ActiveSync clients from connecting to Exchange Online.

   > [!NOTE]
   > This policy ensures mobile users can access all Office endpoints using the applicable apps.

2. If enabling mobile access to Exchange Online, implement [Block ActiveSync clients](secure-email-recommended-policies.md#block-activesync-clients), which prevents Exchange ActiveSync clients leveraging basic authentication from connecting to Exchange Online.

   The above policies leverage the grant controls [Require approved client app](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-approved-client-app) and [Require app protection policy](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy).

3. Disable legacy authentication for other client apps on iOS and Android devices. For more information, see [Block clients that don't support modern authentication](#block-clients-that-dont-support-modern-authentication).
-->

## <a name="define-device-compliance-policies"></a>Definieren von Geräte Kompatibilitätsrichtlinien

Geräte Konformitätsrichtlinien definieren die Anforderungen, die Geräte erfüllen müssen, um als konform gekennzeichnet zu sein. Erstellen Sie in Microsoft Endpoint Manager Admin Center InTune-Geräte Konformitätsrichtlinien.

Erstellen Sie eine Richtlinie für jede Plattform:
- Android-Geräteadministrator
- Android Enterprise
- IOS/iPads
- MacOS
- Windows 8.1 und höher
- Windows 10 und höher

Um Geräte Konformitätsrichtlinien zu erstellen, melden Sie sich mit Ihren Administratoranmeldeinformationen beim [Microsoft Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431) an, und navigieren Sie dann zu Richtlinien für **Devices**  >  **Konformitätsrichtlinien**für Geräte  >  **Policies**. Wählen Sie **Richtlinie erstellen**aus.

Damit Geräte Konformitätsrichtlinien bereitgestellt werden, müssen Sie Benutzergruppen zugewiesen werden. Sie weisen eine Richtlinie zu, nachdem Sie Sie erstellt und gespeichert haben. Wählen Sie im Admin Center die Richtlinie aus, und wählen Sie dann **Zuweisungen**aus. Nachdem Sie die Gruppen ausgewählt haben, für die Sie die Richtlinie erhalten möchten, wählen Sie **Speichern** aus, um diese Gruppenzuweisung zu speichern und die Richtlinie bereitzustellen.

Eine Schritt-für-Schritt-Anleitung zum Erstellen von Konformitätsrichtlinien in InTune finden Sie unter [Create a Compliance Policy in Microsoft InTune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy) in der InTune-Dokumentation.

Die folgenden Einstellungen werden für Windows 10 empfohlen.

**Geräte Integrität: Evaluierungsregeln für den Windows-Integritäts Bestätigungs Dienst**

|Eigenschaften|Werte|Hinweise|
|:---------|:-----|:----|
|BitLocker erforderlich|Erforderlich||
|Sicheres Booten muss auf dem Gerät aktiviert sein|Erforderlich||
|Codeintegrität erforderlich|Erforderlich||


**Geräteeigenschaften**

|Typ|Eigenschaften|Werte|Hinweise|
|:---|:---------|:-----|:----|
|Betriebssystemversion|Alle|Nicht konfiguriert||

**Systemsicherheit**

|Typ|Eigenschaften|Werte|Hinweise|
|:---|:---------|:-----|:----|
|Kennwort|Anfordern eines Kennworts zum Entsperren mobiler Geräte|Erforderlich||
||Einfache Kennwörter|Blockieren||
||Kennwort-Typ|Geräte Standard||
||Minimale Kennwortlänge|6 ||
||Maximale Anzahl von Minuten Inaktivität, bevor Kennwort erforderlich ist|15 |Diese Einstellung wird für die Android-Versionen 4,0 und höher oder für Knox 4,0 und höher unterstützt. Für IOS-Geräte wird diese für IOS 8,0 und höher unterstützt.|
||Kennwortablauf (Tage)|41||
||Anzahl der vorherigen Kennwörter zur Verhinderung der Wiederverwendung|5 ||
||Kennwort anfordern, wenn das Gerät vom Leerlaufzustand zurückkehrt (Mobil und holographisch)|Erforderlich|Verfügbar für Windows 10 und höher|
|Verschlüsselung|Verschlüsselung der Datenspeicherung auf dem Gerät|Erforderlich||
|Gerätesicherheit|Firewall|Erforderlich||
||Antivirus|Erforderlich||
||AntiSpyware|Erforderlich|Für diese Einstellung ist eine mit dem Windows Security Center registrierte Anti-Spyware-Lösung erforderlich.|
|Defender|Antischadsoftware für Microsoft Defender|Erforderlich||
||Mindestversion von Microsoft Defender Antischadsoftware||Wird nur für Windows 10-Desktop unterstützt. Microsoft empfiehlt Versionen von nicht mehr als fünf hinter der neuesten Version|
||Microsoft Defender-Antischadsoftware-Signatur auf dem neuesten Stand|Erforderlich||
||Echtzeitschutz|Erforderlich|Wird nur für Windows 10-Desktop unterstützt|

**Microsoft Defender ATP**

|Typ|Eigenschaften|Werte|Hinweise|
|:---|:---------|:-----|:----|
|Microsoft Defender Advanced Threat Protection-Regeln|Erfordern, dass das Gerät auf oder unter dem Computer-Risk-Score liegt|Medium||


## <a name="require-compliant-pcs-but-not-compliant-phones-and-tablets"></a>Erfordern Sie kompatible PCs (aber keine kompatiblen Telefone und Tablets)
Bevor Sie eine Richtlinie hinzufügen, die kompatible PCs erfordert, müssen Sie die Geräte für die Verwaltung in InTune registrieren. Die Verwendung der mehrstufigen Authentifizierung wird empfohlen, bevor Geräte in InTune registriert werden, um sicher zu sein, dass das Gerät im Besitz des beabsichtigten Benutzers ist. 

So benötigen Sie kompatible PCs:

1. Navigieren Sie zum [Azure-Portal](https://portal.azure.com), und melden Sie sich mit Ihren Anmeldeinformationen an. Nachdem Sie sich erfolgreich angemeldet haben, wird das Azure-Dashboard angezeigt.

2. Wählen Sie im linken Menü **Azure Active Directory** aus.

3. Wählen Sie im Abschnitt **Sicherheit** die Option **bedingter Zugriff**aus.

4. Wählen Sie **Neue Richtlinie** aus.

5. Geben Sie einen Richtliniennamen ein, und wählen Sie dann die **Benutzer und Gruppen** aus, auf die Sie die Richtlinie anwenden möchten.

6. Klicken Sie auf **Cloud-Apps**.

7. Wählen **Sie apps auswählen**aus, und wählen Sie in der Liste **Cloud apps** die gewünschten Apps aus. Wählen Sie beispielsweise Exchange Online aus. Wählen **Sie auswählen** und **Fertig**aus.

8. Um kompatible PCs, aber keine kompatiblen Telefone und Tablets zu benötigen, wählen Sie **Bedingungen** und **Geräteplattformen**aus. Wählen **Sie Geräteplattformen auswählen** aus, und wählen Sie **Windows** und **macOS**aus.

9. Wählen Sie im Abschnitt **Zugriffssteuerung** die Option **Erteilen** aus.

10. Wählen Sie **Zugriff gewähren**aus, und wählen Sie **Gerät müssen als konform gekennzeichnet sein**aus. Wählen Sie für mehrere Steuerelemente **die Option alle ausgewählten Steuerelemente anfordern**aus, und wählen Sie dann **auswählen**aus. 

11. Klicken Sie auf **Erstellen**.

Wenn Ihr Ziel darin besteht, kompatible PCs *und* Mobile Geräte zu benötigen, wählen Sie keine Plattformen aus. Dadurch wird die Kompatibilität für alle Geräte erzwungen. 

## <a name="require-compliant-pcs-and-mobile-devices"></a>Erfordern von kompatiblen PCs *und* mobilen Geräten

So erfordern Sie die Kompatibilität für alle Geräte:

1. Navigieren Sie zum [Azure-Portal](https://portal.azure.com), und melden Sie sich mit Ihren Anmeldeinformationen an. Nachdem Sie sich erfolgreich angemeldet haben, wird das Azure-Dashboard angezeigt.

2. Wählen Sie im linken Menü **Azure Active Directory** aus.

3. Wählen Sie im Abschnitt **Sicherheit** die Option **bedingter Zugriff**aus.

4. Wählen Sie **Neue Richtlinie** aus.

5. Geben Sie einen Richtliniennamen ein, und wählen Sie dann die **Benutzer und Gruppen** aus, auf die Sie die Richtlinie anwenden möchten.

6. Klicken Sie auf **Cloud-Apps**.

7. Wählen **Sie apps auswählen**aus, und wählen Sie in der Liste **Cloud apps** die gewünschten Apps aus. Wählen Sie beispielsweise Exchange Online aus. Wählen **Sie auswählen** und **Fertig**aus.

8. Wählen Sie im Abschnitt **Zugriffssteuerung** die Option **Erteilen** aus.

9. Wählen Sie **Zugriff gewähren**aus, und wählen Sie **Gerät müssen als konform gekennzeichnet sein**aus. Wählen Sie für mehrere Steuerelemente **die Option alle ausgewählten Steuerelemente anfordern**aus, und wählen Sie dann **auswählen**aus. 

10. Klicken Sie auf **Erstellen**.

Wählen Sie beim Erstellen dieser Richtlinie keine Plattformen aus. Dadurch werden konforme Geräte erzwungen.


## <a name="next-steps"></a>Nächste Schritte

![Schritt 3: Richtlinien für Gast-und externe Benutzer](../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-3.png)


[Informationen zu Richtlinien Empfehlungen für Gast-und externe Benutzer](identity-access-policies-guest-access.md)
