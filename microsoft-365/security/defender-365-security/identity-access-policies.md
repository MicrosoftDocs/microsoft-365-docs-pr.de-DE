---
title: Allgemeine Identitäts- und Gerätezugriffsrichtlinien – Microsoft 365 for Enterprise | Microsoft Docs
description: Beschreibt die empfohlenen allgemeinen Identitäts- und Gerätezugriffsrichtlinien und -konfigurationen.
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: m365-security
ms.topic: article
audience: Admin
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
- m365solution-identitydevice
- m365solution-scenario
ms.technology: mdo
ms.openlocfilehash: 7ade29259a5552bc9bbaac4b143842c69d05f917
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51065295"
---
# <a name="common-identity-and-device-access-policies"></a>Allgemeine Identitäts- und Gerätezugriffsrichtlinien

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- Azure

In diesem Artikel werden die allgemeinen empfohlenen Richtlinien zum Sichern des Zugriffs auf Microsoft 365-Clouddienste beschrieben, einschließlich der lokalen Anwendungen, die mit dem Azure Active Directory (Azure AD)-Anwendungsproxy veröffentlicht wurden.

In diesem Leitfaden wird erläutert, wie die empfohlenen Richtlinien in einer neu bereitgestellten Umgebung bereitgestellt werden. Wenn Sie diese Richtlinien in einer separaten Laborumgebung einrichten, können Sie die empfohlenen Richtlinien verstehen und bewerten, bevor Sie das Rollout in Ihre Präproduktions- und Produktionsumgebungen bereitstellen. Ihre neu bereitgestellte Umgebung kann nur cloud- oder hybrid sein, um Ihre Bewertungsanforderungen zu erfüllen.

## <a name="policy-set"></a>Richtliniensatz

Das folgende Diagramm veranschaulicht den empfohlenen Satz von Richtlinien. Sie zeigt, auf welche Schutzebene die einzelnen Richtlinien angewendet werden und ob die Richtlinien für PCs, Smartphones und Tablets oder beide Gerätekategorien gelten. Außerdem wird angegeben, wo Sie diese Richtlinien konfigurieren.

[![Allgemeine Richtlinien zum Konfigurieren des Identitäts- und Gerätezugriffs](../../media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)

Im Folgenden finden Sie eine einseitige PDF-Zusammenfassung mit Links zu den einzelnen Richtlinien:

[![Fingerabdruckbild für Identitäts- und Geräteschutz für Microsoft 365-Handzettel](../../media/microsoft-365-policies-configurations/MSFT-cloud-architecture-identity-device-protection-handout.png)](../../downloads/MSFT-cloud-architecture-identity-device-protection-handout.pdf) <br> [Anzeigen als PDF](../../downloads/MSFT-cloud-architecture-identity-device-protection-handout.pdf) \| [Als PDF herunterladen](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/MSFT-cloud-architecture-identity-device-protection-handout.pdf)

Der Rest dieses Artikels beschreibt, wie Diese Richtlinien konfiguriert werden.

> [!NOTE]
> Die Verwendung der mehrstufigen Authentifizierung (MFA) wird empfohlen, bevor Sie Geräte in Intune registrieren, um sicherzustellen, dass das Gerät im Besitz des beabsichtigten Benutzers ist. Sie müssen Geräte in Intune registrieren, bevor Sie Richtlinien zur Gerätekonformität erzwingen können.

Um Ihnen Zeit zum Ausführen dieser Aufgaben zu geben, empfehlen wir die Implementierung der Basisrichtlinien in der in dieser Tabelle aufgeführten Reihenfolge. Die MFA-Richtlinien für vertrauliche und streng regulierte Schutzebenen können jedoch jederzeit implementiert werden.

|Schutzebene|Richtlinien|Weitere Informationen|
|---|---|---|
|**Basisplan**|[MFA erforderlich, wenn das Anmelderisiko *mittel oder* hoch *ist*](#require-mfa-based-on-sign-in-risk)||
||[Blockieren von Clients, die die moderne Authentifizierung nicht unterstützen](#block-clients-that-dont-support-multi-factor)|Clients, die keine moderne Authentifizierung verwenden, können Richtlinien für bedingten Zugriff umgehen, daher ist es wichtig, diese zu blockieren.|
||[Nutzer mit hohem Risiko müssen das Kennwort ändern](#high-risk-users-must-change-password)|Zwingt Benutzer, ihr Kennwort bei der Anmeldung zu ändern, wenn für ihr Konto Aktivitäten mit hohem Risiko erkannt werden.|
||[Anwenden von Datenschutzrichtlinien für Apps](#apply-app-data-protection-policies)|Eine Intune App Protection-Richtlinie pro Plattform (Windows, iOS/iPadOS, Android).|
||[Erforderlicher genehmigter Apps und App-Schutz](#require-approved-apps-and-app-protection)|Erzwingt mobilen App-Schutz für Smartphones und Tablets mit iOS, iPadOS oder Android.|
||[Definieren von Richtlinien zur Gerätekonformität](#define-device-compliance-policies)|Eine Richtlinie für jede Plattform.|
||[Kompatible PCs erforderlich](#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Erzwingt die Intune-Verwaltung von PCs mithilfe von Windows oder MacOS.|
|**Vertraulich**|[MFA erforderlich, wenn das Anmelderisiko *niedrig,* *mittel* oder hoch *ist*](#require-mfa-based-on-sign-in-risk)||
||[Erfordern kompatibler PCs *und* mobiler Geräte](#require-compliant-pcs-and-mobile-devices)|Erzwingt die Intune-Verwaltung für PCs (Windows oder MacOS) und Smartphones oder Tablets (iOS, iPadOS oder Android).|
|**Streng geregelt**|[*MFA* immer erforderlich](#require-mfa-based-on-sign-in-risk)|
|

## <a name="assigning-policies-to-groups-and-users"></a>Zuweisen von Richtlinien zu Gruppen und Benutzern

Identifizieren Sie vor dem Konfigurieren von Richtlinien die Azure AD-Gruppen, die Sie für jede Schutzebene verwenden. In der Regel gilt der Basisschutz für alle in der Organisation. Für einen Benutzer, der sowohl für den Basis- als auch für den vertraulichen Schutz einbezogen ist, werden alle Basisrichtlinien sowie die vertraulichen Richtlinien angewendet. Der Schutz ist kumulativ, und die restriktivste Richtlinie wird erzwungen.

Es wird empfohlen, eine Azure AD-Gruppe für den Ausschluss von bedingten Zugriffen zu erstellen. Fügen Sie diese Gruppe allen Richtlinien für bedingten Zugriff im **Exclude-Wert** der Einstellung **Benutzer** und Gruppen im Abschnitt **Zuweisungen** hinzu. Dadurch erhalten Sie eine Methode zum Bereitstellen des Zugriffs für einen Benutzer, während Sie Probleme mit dem Zugriff behandeln. Dies wird nur als temporäre Lösung empfohlen. Überwachen Sie diese Gruppe auf Änderungen, und stellen Sie sicher, dass die Ausschlussgruppe nur wie beabsichtigt verwendet wird.

Im Folgenden finden Sie ein Beispiel für Gruppenzuweisungen und Ausschlüsse für die Anforderung von MFA.

![Beispiel für Gruppenzuweisungen und Ausschlüsse für MFA-Richtlinien](../../media/microsoft-365-policies-configurations/identity-access-policies-assignment.png)

Hier sind die Ergebnisse:

- Alle Benutzer müssen MFA verwenden, wenn das Anmelderisiko mittel oder hoch ist.

- Mitglieder der Gruppe "Executive Staff" müssen MFA verwenden, wenn das Anmelderisiko niedrig, mittel oder hoch ist.

  In diesem Fall entsprechen Mitglieder der Gruppe "Executive Staff" sowohl den Basisrichtlinien als auch den vertraulichen Richtlinien für bedingten Zugriff. Die Zugriffssteuerelemente für beide Richtlinien werden kombiniert, was in diesem Fall der vertraulichen Richtlinie für bedingten Zugriff entspricht.

- Mitglieder der Gruppe "Top Secret Project X" müssen MFA immer verwenden

  In diesem Fall entsprechen Mitglieder der Gruppe "Top Secret Project X" sowohl den Basisrichtlinien als auch den streng regulierten Richtlinien für bedingten Zugriff. Die Zugriffssteuerelemente für beide Richtlinien werden kombiniert. Da die Zugriffssteuerung für die streng regulierte Richtlinie für bedingten Zugriff restriktiver ist, wird sie verwendet.

Seien Sie vorsichtig, wenn Sie auf Gruppen und Benutzer höhere Schutzebenen anwenden. Beispielsweise müssen Mitglieder der Gruppe "Top Secret Project X" bei jeder Anmeldung MFA verwenden, auch wenn sie nicht an den streng regulierten Inhalten für Project X arbeiten.

Alle Azure AD-Gruppen, die im Rahmen dieser Empfehlungen erstellt wurden, müssen als Microsoft 365-Gruppen erstellt werden. Dies ist wichtig für die Bereitstellung von Vertraulichkeitsbezeichnungen beim Sichern von Dokumenten in Microsoft Teams und SharePoint.

![Bildschirmaufnahme zum Erstellen von Microsoft 365-Gruppen](../../media/microsoft-365-policies-configurations/identity-device-AAD-groups.png)

## <a name="require-mfa-based-on-sign-in-risk"></a>MFA basierend auf dem Anmelderisiko erfordern

Ihre Benutzer sollten sich vor der Verwendung für MFA registrieren lassen. Wenn Sie über Microsoft 365 E5, Microsoft 365 E3 mit dem Identity & Threat Protection-Add-On, Office 365 mit EMS E5 oder einzelnen Azure AD Premium P2-Lizenzen verfügen, können Sie die MFA-Registrierungsrichtlinie mit Azure AD Identity Protection verwenden, um zu verlangen, dass sich Benutzer für MFA registrieren. Die [erforderliche Arbeit umfasst](identity-access-prerequisites.md) die Registrierung aller Benutzer mit MFA.

Nachdem Ihre Benutzer registriert wurden, können Sie MFA für die Anmeldung mit einer neuen Richtlinie für bedingten Zugriff benötigen.

1. Navigieren Sie zum [Azure-Portal](https://portal.azure.com), und melden Sie sich mit Ihren Anmeldeinformationen an.
2. Wählen Sie in der Liste der Azure-Dienste **Azure Active Directory aus.**
3. Wählen Sie **in der** Liste Verwalten die **Option Sicherheit** aus, und wählen Sie dann **bedingten Zugriff aus.**
4. Wählen **Sie Neue Richtlinie** aus, und geben Sie den Namen der neuen Richtlinie ein.

In den folgenden Tabellen werden die Richtlinieneinstellungen für bedingten Zugriff beschrieben, um MFA basierend auf dem Anmelderisiko zu erfordern.

Im Abschnitt **Zuordnungen:**

|Setting|Eigenschaften|Werte|Hinweise|
|---|---|---|---|
|Benutzer und Gruppen|Einschließen|**Wählen Sie Benutzer und Gruppen > Benutzer und Gruppen** aus: Wählen Sie bestimmte Gruppen aus, die zielgerichtete Benutzerkonten enthalten.|Beginnen Sie mit der Gruppe, die Pilotbenutzerkonten enthält.|
||Ausschließen|**Benutzer und Gruppen**: Wählen Sie Ihre Ausnahmegruppe für bedingten Zugriff aus. Dienstkonten (App-Identitäten).|Die Mitgliedschaft sollte bei Bedarf vorübergehend geändert werden.|
|Cloud-Apps oder -Aktionen|**Cloud-Apps > Include**|**Apps auswählen:** Wählen Sie die Apps aus, auf die diese Richtlinie angewendet werden soll. Wählen Sie beispielsweise Exchange Online aus.||
|Bedingungen|||Konfigurieren Von Bedingungen, die für Ihre Umgebung und Ihre Anforderungen spezifisch sind.|
||Anmelderisiko||Weitere Informationen finden Sie in der folgenden Tabelle.|
|

### <a name="sign-in-risk-condition-settings"></a>Anmelderisikobedingungseinstellungen

Wenden Sie die Risikoebeneneinstellungen basierend auf der zielorientierten Schutzebene an.

|Schutzniveau|Benötigte Risikoebenenwerte|Aktion|
|---|---|---|
|Baseline|Hoch, Mmittel|Überprüfen Sie beides.|
|Vertraulich|Hoch, mittel, niedrig|Überprüfen Sie alle drei.|
|Streng geregelt||Lassen Sie alle Optionen deaktiviert, um MFA immer zu erzwingen.|
|

Im Abschnitt **Zugriffssteuerelemente:**

|Setting|Eigenschaften|Werte|Aktion|
|---|---|---|---|
|Gewähren|**Grant access**||Auswählen|
|||**Mehrstufige Authentifizierung erforderlich**|Scheck|
||**Alle ausgewählten Steuerelemente erforderlich**||Auswählen|
|

Wählen **Sie Auswählen** aus, um die **Grant-Einstellungen zu** speichern.

Wählen Sie schließlich **Ein** für **Richtlinie aktivieren** aus, und wählen Sie dann **Erstellen aus.**

Erwägen Sie außerdem die Verwendung des [Tools Was wäre,](/azure/active-directory/active-directory-conditional-access-whatif) um die Richtlinie zu testen.

## <a name="block-clients-that-dont-support-multi-factor"></a>Blockieren von Clients, die keine mehrstufigen Clients unterstützen

Verwenden Sie die Einstellungen in diesen Tabellen für eine Richtlinie für bedingten Zugriff, um Clients zu blockieren, die keine mehrstufige Authentifizierung unterstützen.

In [diesem Artikel finden](../../enterprise/microsoft-365-client-support-multi-factor-authentication.md) Sie eine Liste der Clients in Microsoft 365, die die mehrstufige Authentifizierung unterstützen.

Im Abschnitt **Zuordnungen:**

|Setting|Eigenschaften|Werte|Hinweise|
|---|---|---|---|
|Benutzer und Gruppen|Einschließen|**Wählen Sie Benutzer und Gruppen > Benutzer und Gruppen** aus: Wählen Sie bestimmte Gruppen aus, die zielgerichtete Benutzerkonten enthalten.|Beginnen Sie mit der Gruppe, die Pilotbenutzerkonten enthält.|
||Ausschließen|**Benutzer und Gruppen**: Wählen Sie Ihre Ausnahmegruppe für bedingten Zugriff aus. Dienstkonten (App-Identitäten).|Die Mitgliedschaft sollte bei Bedarf vorübergehend geändert werden.|
|Cloud-Apps oder -Aktionen|**Cloud-Apps > Include**|**Apps auswählen:** Wählen Sie die Apps aus, die den Clients entspricht, die keine moderne Authentifizierung unterstützen.||
|Bedingungen|**Client-Apps**|Wählen **Sie Ja** für Konfigurieren **aus.** <p> Deaktivieren der Kontrollkästchen für **Browser-** und **Mobile-Apps und Desktopclients**||
|

Im Abschnitt **Zugriffssteuerelemente:**

|Setting|Eigenschaften|Werte|Aktion|
|---|---|---|---|
|Gewähren|**Zugriff blockieren**||Auswählen|
||**Alle ausgewählten Steuerelemente erforderlich**||Auswählen|
|

Wählen **Sie Auswählen** aus, um die **Grant-Einstellungen zu** speichern.

Wählen Sie schließlich **Ein** für **Richtlinie aktivieren** aus, und wählen Sie dann **Erstellen aus.**

Erwägen Sie die Verwendung des [Tools Was wäre,](/azure/active-directory/active-directory-conditional-access-whatif) um die Richtlinie zu testen.

Für Exchange Online können Sie Authentifizierungsrichtlinien verwenden, um die [Standardauthentifizierung](/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online)zu deaktivieren, wodurch alle Clientzugriffsanforderungen die moderne Authentifizierung verwenden müssen.

## <a name="high-risk-users-must-change-password"></a>Nutzer mit hohem Risiko müssen das Kennwort ändern

Um sicherzustellen, dass die gefährdeten Konten aller benutzergefährdten Benutzer bei der Anmeldung eine Kennwortänderung durchführen müssen, müssen Sie die folgende Richtlinie anwenden.

Melden Sie sich im [Microsoft Azure-Portal (https://portal.azure.com)](https://portal.azure.com/) mit Ihren Administratoranmeldeinformationen an, und wechseln Sie dann zu **Azure AD Identity Protection > Richtlinie zum Benutzerrisiko**.

Im Abschnitt **Zuordnungen:**

|Typ|Eigenschaften|Werte|Aktion|
|---|---|---|---|
|Users|Einschließen|**Alle Benutzer**|Auswählen|
|Benutzerrisiko|**High**||Auswählen|
|

Im zweiten **Abschnitt Zuordnungen:**

|Typ|Eigenschaften|Werte|Aktion|
|---|---|---|---|
|Access|**Zugriff zulassen**||Auswählen|
|||**Kennwortänderung erforderlich**|Scheck|
|

Wählen **Sie Fertig** aus, um die **Zugriffseinstellungen zu** speichern.

Wählen Sie schließlich **Ein** für **Richtlinie erzwingen** aus, und wählen Sie dann **Speichern aus.**

Erwägen Sie die Verwendung des [Tools Was wäre,](/azure/active-directory/active-directory-conditional-access-whatif) um die Richtlinie zu testen.

Verwenden Sie diese Richtlinie in Verbindung mit [Configure Azure AD password protection](/azure/active-directory/authentication/concept-password-ban-bad), der bekannte schwache Kennwörter und deren Varianten sowie zusätzliche schwache Begriffe erkennt und blockiert, die spezifisch für Ihre Organisation sind. Die Verwendung des Azure AD-Kennwortschutzes stellt sicher, dass geänderte Kennwörter starke Kennwörter sind.

## <a name="apply-app-data-protection-policies"></a>Anwenden von APP-Datenschutzrichtlinien

App Protection Policies (APP) definieren, welche Apps zulässig sind und welche Aktionen sie mit den Daten Ihrer Organisation ausführen können. Die in APP verfügbaren Optionen ermöglichen Es Organisationen, den Schutz an ihre spezifischen Anforderungen anzupassen. Für einige ist es möglicherweise nicht offensichtlich, welche Richtlinieneinstellungen erforderlich sind, um ein vollständiges Szenario zu implementieren. Um Organisationen dabei zu helfen, die Sicherheit mobiler Clientendpunkte zu priorisieren, hat Microsoft die Taxonomie für das APP-Datenschutzframework für die Verwaltung mobiler iOS- und Android-Apps eingeführt.

Das APP-Datenschutzframework ist in drei verschiedene Konfigurationsebenen organisiert, auf der jede Ebene von der vorherigen Ebene abhing:

- **Enterprise Basic Data Protection** (Ebene 1) stellt sicher, dass Apps mit einer PIN geschützt und verschlüsselt sind und selektive Löschvorgänge ausführt. Für Android-Geräte überprüft diese Stufe die Android-Gerätebescheinigung. Dies ist eine Einstiegsebenenkonfiguration, die ähnliche Datenschutzkontrollen in Exchange Online-Postfachrichtlinien bietet und DIE IT und die Benutzerpopulation in APP einleite.
- **Der erweiterte Datenschutz** in Unternehmen (Ebene 2) führt Mechanismen zur Verhinderung von Datenlecks und Mindestanforderungen an das Betriebssystem ein. Dies ist die Konfiguration, die für die meisten mobilen Benutzer gilt, die auf Arbeits- oder Schuldaten zugreifen.
- **Der hohe Datenschutz** in Unternehmen (Ebene 3) führt erweiterte Datenschutzmechanismen, eine erweiterte PIN-Konfiguration und app Mobile Threat Defense ein. Diese Konfiguration ist für Benutzer wünschenswert, die auf Daten mit hohem Risiko zugreifen.

Informationen zu den spezifischen Empfehlungen für die einzelnen Konfigurationsebenen und zu den zu schützende Apps finden Sie unter [Data protection framework using app protection policies](/mem/intune/apps/app-protection-framework).

Unter Verwendung der in [Identitäts-](microsoft-365-policies-configurations.md)und Gerätezugriffskonfigurationen beschriebenen Prinzipien werden die Ebenen Baseline und Sensitive Protection eng mit den erweiterten Datenschutzeinstellungen auf Ebene 2 des Unternehmens verknüpft. Die Stufe "Streng regulierter Schutz" ist eng mit den Einstellungen für hohen Datenschutz auf Ebene 3 des Unternehmens verknüpft.

|Schutzebene|App Protection Policy|Weitere Informationen|
|---|---|---|
|Baseline|[Erweiterter Datenschutz auf Ebene 2](/mem/intune/apps/app-protection-framework#level-2-enterprise-enhanced-data-protection)|Die in Ebene 2 erzwungenen Richtlinieneinstellungen umfassen alle richtlinieneinstellungen, die für Ebene 1 empfohlen werden, und fügen nur die folgenden Richtlinieneinstellungen hinzu, um mehr Steuerelemente und eine komplexere Konfiguration als Stufe 1 zu implementieren.|
|Vertraulich|[Erweiterter Datenschutz auf Ebene 2](/mem/intune/apps/app-protection-framework#level-2-enterprise-enhanced-data-protection)|Die in Ebene 2 erzwungenen Richtlinieneinstellungen umfassen alle richtlinieneinstellungen, die für Ebene 1 empfohlen werden, und fügen nur die folgenden Richtlinieneinstellungen hinzu, um mehr Steuerelemente und eine komplexere Konfiguration als Stufe 1 zu implementieren.|
|Streng reguliert|[Hoher Datenschutz für Unternehmen auf Ebene 3](/mem/intune/apps/app-protection-framework#level-3-enterprise-high-data-protection)|Die in Ebene 3 erzwungenen Richtlinieneinstellungen umfassen alle richtlinieneinstellungen, die für die Ebene 1 und 2 empfohlen werden, und fügen nur die folgenden Richtlinieneinstellungen hinzu oder aktualisieren sie, um mehr Steuerelemente und eine komplexere Konfiguration als Stufe 2 zu implementieren.|
|

Zum Erstellen einer neuen App-Schutzrichtlinie für jede Plattform (iOS und Android) in Microsoft Endpoint Manager mithilfe der Datenschutzframeworkeinstellungen können Sie:

1. Erstellen Sie die Richtlinien manuell, indem Sie die Schritte unter Erstellen und Bereitstellen von App-Schutzrichtlinien [mit Microsoft Intune ausführen.](/mem/intune/apps/app-protection-policies)
2. Importieren Sie die [Intune App Protection Policy Configuration Framework-JSON-Beispielvorlagen](https://github.com/microsoft/Intune-Config-Frameworks/tree/master/AppProtectionPolicies) mit den [PowerShell-Skripts](https://github.com/microsoftgraph/powershell-intune-samples)von Intune.

## <a name="require-approved-apps-and-app-protection"></a>Benötigen genehmigter Apps und APP-Schutz

Zum Erzwingen der app-Schutzrichtlinien, die Sie in Intune angewendet haben, müssen Sie eine Richtlinie für bedingten Zugriff erstellen, um genehmigte Client-Apps und die in den APP-Schutzrichtlinien festgelegten Bedingungen zu benötigen.

Das Erzwingen von APP-Schutzrichtlinien erfordert eine Reihe von Richtlinien, die unter [Require app protection policy for cloud app access with Conditional Access beschrieben werden.](/azure/active-directory/conditional-access/app-protection-based-conditional-access) Diese Richtlinien sind jeweils in diesem empfohlenen Satz von Identitäts- und Zugriffskonfigurationsrichtlinien enthalten.

Um die Richtlinie für bedingten Zugriff zu erstellen, die genehmigte Apps und APP-Schutz erfordert, folgen Sie "Schritt 1: Konfigurieren einer Azure AD-Richtlinie für bedingten Zugriff für Microsoft 365" in [Szenario 1: Microsoft 365-Apps](/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies)erfordern genehmigte Apps mit App-Schutzrichtlinien, die Outlook für iOS und Android zulässt, aber OAuth-fähige Exchange ActiveSync-Clients daran blockiert, eine Verbindung mit Exchange Online zu herstellen.

   > [!NOTE]
   > Diese Richtlinie stellt sicher, dass mobile Benutzer über die entsprechenden Apps auf alle Office-Endpunkte zugreifen können.

Wenn Sie den mobilen Zugriff auf Exchange Online aktivieren, implementieren Sie [Block ActiveSync-Clients,](secure-email-recommended-policies.md#block-activesync-clients)wodurch verhindert wird, dass Exchange ActiveSync Standardauthentifizierung eine Verbindung mit Exchange Online herstellen. Diese Richtlinie ist in der Abbildung oben in diesem Artikel nicht dargestellt. Sie wird in Richtlinienempfehlungen zum Sichern von [E-Mails beschrieben und abgebildet.](secure-email-recommended-policies.md)

Um die Richtlinie für bedingten Zugriff zu erstellen, die Edge für iOS und Android erfordert, folgen Sie "Schritt 2: Konfigurieren einer Azure AD-Richtlinie für bedingten Zugriff für Microsoft 365" in [Szenario 2: Browser-Apps](/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-2-browser-apps-require-approved-apps-with-app-protection-policies)benötigen genehmigte Apps mit App-Schutzrichtlinien, die Edge für iOS und Android ermöglichen, aber andere Webbrowser für mobile Geräte daran blockieren, eine Verbindung mit Microsoft 365-Endpunkten zu herstellen.

 Diese Richtlinien nutzen die Berechtigungssteuerelemente [Genehmigte Client-App und](/azure/active-directory/conditional-access/concept-conditional-access-grant#require-approved-client-app) [App-Schutzrichtlinie erfordern.](/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy)

Schließlich stellt das Blockieren der Legacyauthentifizierung für andere Client-Apps auf iOS- und Android-Geräten sicher, dass diese Clients Richtlinien für bedingten Zugriff nicht umgehen können. Wenn Sie den Anweisungen in diesem Artikel folgen, haben Sie bereits Blockclients konfiguriert, die keine [moderne Authentifizierung unterstützen.](#block-clients-that-dont-support-multi-factor)

<!---
With Conditional Access, organizations can restrict access to approved (modern authentication capable) iOS and Android client apps with Intune app protection policies applied to them. Several Conditional Access policies are required, with each policy targeting all potential users. Details on creating these policies can be found in [Require app protection policy for cloud app access with Conditional Access](/azure/active-directory/conditional-access/app-protection-based-conditional-access).

1. Follow "Step 1: Configure an Azure AD Conditional Access policy for Microsoft 365" in [Scenario 1: Microsoft 365 apps require approved apps with app protection policies](/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies), which allows Outlook for iOS and Android, but blocks OAuth capable Exchange ActiveSync clients from connecting to Exchange Online.

   > [!NOTE]
   > This policy ensures mobile users can access all Office endpoints using the applicable apps.

2. If enabling mobile access to Exchange Online, implement [Block ActiveSync clients](secure-email-recommended-policies.md#block-activesync-clients), which prevents Exchange ActiveSync clients leveraging basic authentication from connecting to Exchange Online.

   The above policies leverage the grant controls [Require approved client app](/azure/active-directory/conditional-access/concept-conditional-access-grant#require-approved-client-app) and [Require app protection policy](/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy).

3. Disable legacy authentication for other client apps on iOS and Android devices. For more information, see [Block clients that don't support modern authentication](#block-clients-that-dont-support-modern-authentication).
-->

## <a name="define-device-compliance-policies"></a>Definieren von Richtlinien zur Gerätekonformität

Richtlinien zur Gerätekonformität definieren die Anforderungen, die Geräte erfüllen müssen, um als kompatibel festgelegt zu werden. Sie erstellen Intune-Gerätekonformitätsrichtlinien im Microsoft Endpoint Manager Admin Center.

Sie müssen eine Richtlinie für jeden PC, jedes Smartphone oder jede Tablet-Plattform erstellen:

- Android-Geräteadministrator
- Android Enterprise
- iOS/iPadOS
- macOS
- Windows 8.1 und höher
- Windows 10 und höher

Melden Sie sich zum Erstellen von Gerätekonformitätsrichtlinien beim [Microsoft Endpoint Manager Admin Center](https://endpoint.microsoft.com) mit Ihren Administratoranmeldeinformationen an, und navigieren Sie dann zu **Richtlinien** für \>  \> **Gerätekonformität.** Wählen **Sie Richtlinie erstellen aus.**

Damit Richtlinien zur Gerätekonformität bereitgestellt werden können, müssen sie Benutzergruppen zugewiesen werden. Sie weisen eine Richtlinie zu, nachdem Sie sie erstellt und gespeichert haben. Wählen Sie im Admin Center die Richtlinie aus, und wählen Sie dann **Zuordnungen aus.** Nachdem Sie die Gruppen ausgewählt haben, die Sie die Richtlinie erhalten möchten, wählen Sie **Speichern** aus, um diese Gruppenzuweisung zu speichern und die Richtlinie zu bereitstellen.

Schrittweise Anleitungen zum Erstellen von Compliancerichtlinien in Intune finden Sie unter [Create a compliance policy in Microsoft Intune in](/mem/intune/protect/create-compliance-policy) der Intune-Dokumentation.

### <a name="recommended-settings-for-windows-10-and-later"></a>Empfohlene Einstellungen für Windows 10 und höher

Die folgenden Einstellungen werden für PCs mit Windows 10 und höher empfohlen, wie in **Schritt 2: Complianceeinstellungen** des Richtlinienerstellungsprozesses konfiguriert.

Informationen **zur > von Windows Health Attestation Service** finden Sie in dieser Tabelle.

|Eigenschaften|Wert|Aktion|
|---|---|---|
|BitLocker erforderlich|Erforderlich|Auswählen|
|Aktivieren des sicheren Starts auf dem Gerät erforderlich|Erforderlich|Auswählen|
|Codeintegrität erfordern|Erforderlich|Auswählen|
|

Geben **Sie für** Geräteeigenschaften basierend auf Ihren IT- und Sicherheitsrichtlinien geeignete Werte für Betriebssystemversionen an.

Wählen **Sie für Configuration Manager Compliance** die Option Erforderlich **aus.**

Informationen **zur Systemsicherheit** finden Sie in dieser Tabelle.

|Typ|Eigenschaften|Wert|Aktion|
|---|---|---|---|
|Kennwort|Kennwort zum Entsperren mobiler Geräte benötigen|Erforderlich|Auswählen|
||Einfache Kennwörter|Blockieren|Auswählen|
||Kennworttyp|Geräteeinstellung|Auswählen|
||Minimale Kennwortlänge|6 |Typ|
||Maximale Inaktivitätsminuten, bevor ein Kennwort erforderlich ist|15 |Typ <p> Diese Einstellung wird für Android-Versionen 4.0 und höher oder KNOX 4.0 und höher unterstützt. Für iOS-Geräte wird es für iOS 8.0 und höher unterstützt.|
||Kennwortablauf (Tage)|41|Typ|
||Anzahl der vorherigen Kennwörter, um die Wiederverwendung zu verhindern|5 |Typ|
||Kennwort erforderlich, wenn das Gerät aus dem Leerlaufzustand zurückkehrt (Mobile und Holographic)|Erforderlich|Verfügbar für Windows 10 und höher|
|Verschlüsselung|Verschlüsselung der Datenspeicherung auf dem Gerät|Erforderlich|Auswählen|
|Gerätesicherheit|Firewall|Erforderlich|Auswählen|
||Antivirus|Erforderlich|Auswählen|
||Ansyware|Erforderlich|Auswählen <p> Für diese Einstellung ist eine Anti-Spyware-Lösung erforderlich, die beim Windows Security Center registriert ist.|
|Defender|Microsoft Defender Anmalware|Erforderlich|Auswählen|
||Microsoft Defender Anmalware-Mindestversion||Typ <p> Nur für Windows 10-Desktop unterstützt. Microsoft empfiehlt Versionen, die nicht mehr als fünf Weniger als die neueste Version haben.|
||Microsoft Defender Antischalwaresignatur auf dem neuesten Stand|Erforderlich|Auswählen|
||Echtzeitschutz|Erforderlich|Auswählen <p> Nur für Windows 10-Desktop unterstützt|
|

#### <a name="microsoft-defender-for-endpoint"></a>Microsoft Defender für Endpunkt

|Typ|Eigenschaften|Wert|Aktion|
|---|---|---|---|
|Regeln für Microsoft Defender für Endpunkte|Fordern Sie an, dass sich das Gerät bei oder unter der Bewertung des Computerrisikos|Mittel|Auswählen|
|

## <a name="require-compliant-pcs-but-not-compliant-phones-and-tablets"></a>Erfordern kompatibler PCs (aber nicht kompatible Telefone und Tablets)

Bevor Sie eine Richtlinie hinzufügen, um kompatible PCs zu erfordern, müssen Sie geräte für die Verwaltung bei Intune registrieren. Die Verwendung der mehrstufigen Authentifizierung wird empfohlen, bevor Sie Geräte bei Intune registrieren, um sicher zu sein, dass sich das Gerät im Besitz des beabsichtigten Benutzers befindet.

So fordern Sie kompatible PCs an:

1. Navigieren Sie zum [Azure-Portal](https://portal.azure.com), und melden Sie sich mit Ihren Anmeldeinformationen an.
2. Wählen Sie in der Liste der Azure-Dienste **Azure Active Directory aus.**
3. Wählen Sie **in der** Liste Verwalten die **Option Sicherheit** aus, und wählen Sie dann **bedingten Zugriff aus.**
4. Wählen **Sie Neue Richtlinie** aus, und geben Sie den Namen der neuen Richtlinie ein.

5. Wählen **Sie unter Zuordnungen** **Benutzer und Gruppen** aus, und geben Sie an, auf wen die Richtlinie angewendet werden soll. Schließen Sie auch Ihre Ausschlussgruppe für bedingten Zugriff aus.

6. Wählen **Sie unter Zuweisungen** **die Option Cloud-Apps oder -Aktionen aus.**

7. Wählen **Sie für** Include die Option Apps auswählen > **Auswählen** aus, und wählen Sie dann die gewünschten Apps aus der **Liste Cloud-Apps** aus. Wählen Sie beispielsweise Exchange Online aus. Wählen **Sie Auswählen** aus, wenn sie fertig ist.

8. Wenn Sie kompatible PCs (aber keine kompatiblen Telefone und Tablets) benötigen möchten, wählen Sie unter **Zuweisungen** die Option Bedingungen **> Geräteplattformen aus.** Wählen **Sie Ja** für Konfigurieren **aus.** Wählen **Sie Geräteplattformen auswählen** aus, wählen Sie **Windows** und **macOS** aus, und wählen Sie dann **Fertig aus.**

9. Wählen **Sie unter Zugriffssteuerelemente** die Option **Gewähren aus.**

10. Wählen **Sie Zugriff gewähren** aus, und klicken Sie dann auf Gerät als kompatibel **festlegen.** Wählen Sie für mehrere Steuerelemente **alle ausgewählten Steuerelemente erforderlich aus.** Wählen Sie nach Abschluss des Vorgangs **Auswählen aus.**

11. Wählen **Sie Ein** für Richtlinie **aktivieren** aus, und wählen Sie dann **Erstellen aus.**

> [!NOTE]
> Stellen Sie sicher, dass Ihr Gerät kompatibel ist, bevor Sie diese Richtlinie aktivieren. Andernfalls könnten Sie gesperrt werden und diese Richtlinie erst ändern, wenn Ihr Benutzerkonto der Ausschlussgruppe bedingter Zugriff hinzugefügt wurde.

## <a name="require-compliant-pcs-and-mobile-devices"></a>Erfordern kompatibler PCs *und* mobiler Geräte

So fordern Sie die Compliance für alle Geräte an:

1. Navigieren Sie zum [Azure-Portal](https://portal.azure.com), und melden Sie sich mit Ihren Anmeldeinformationen an.
2. Wählen Sie in der Liste der Azure-Dienste **Azure Active Directory aus.**
3. Wählen Sie **in der** Liste Verwalten die **Option Sicherheit** aus, und wählen Sie dann **bedingten Zugriff aus.**
4. Wählen **Sie Neue Richtlinie** aus, und geben Sie den Namen der neuen Richtlinie ein.

5. Wählen **Sie unter Zuordnungen** **Benutzer und Gruppen** aus, und geben Sie an, auf wen die Richtlinie angewendet werden soll. Schließen Sie auch Ihre Ausschlussgruppe für bedingten Zugriff aus.

6. Wählen **Sie unter Zuweisungen** **die Option Cloud-Apps oder -Aktionen aus.**

7. Wählen **Sie für** Include die Option Apps auswählen > **Auswählen** aus, und wählen Sie dann die gewünschten Apps aus der **Liste Cloud-Apps** aus. Wählen Sie beispielsweise Exchange Online aus. Wählen **Sie Auswählen** aus, wenn sie fertig ist.

8. Wählen **Sie unter Zugriffssteuerelemente** die Option **Gewähren aus.**

9. Wählen **Sie Zugriff gewähren** aus, und klicken Sie dann auf Gerät als kompatibel **festlegen.** Wählen Sie für mehrere Steuerelemente **alle ausgewählten Steuerelemente erforderlich aus.** Wählen Sie nach Abschluss des Vorgangs **Auswählen aus.**

10. Wählen **Sie Ein** für Richtlinie **aktivieren** aus, und wählen Sie dann **Erstellen aus.**

> [!NOTE]
> Stellen Sie sicher, dass Ihr Gerät kompatibel ist, bevor Sie diese Richtlinie aktivieren. Andernfalls könnten Sie gesperrt werden und diese Richtlinie erst ändern, wenn Ihr Benutzerkonto der Ausschlussgruppe bedingter Zugriff hinzugefügt wurde.

## <a name="next-step"></a>Nächster Schritt

[![Schritt 3: Richtlinien für Gastbenutzer und externe Benutzer](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-3.png)](identity-access-policies-guest-access.md)

[Informationen zu Richtlinienempfehlungen für Gastbenutzer und externe Benutzer](identity-access-policies-guest-access.md)