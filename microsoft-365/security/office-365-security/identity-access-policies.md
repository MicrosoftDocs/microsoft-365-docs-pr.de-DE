---
title: Allgemeine Identitäts- und Gerätezugriffsrichtlinien – Microsoft 365 Enterprise | Microsoft Docs
description: Beschreibt die empfohlenen allgemeinen Identitäts- und Gerätezugriffsrichtlinien und -konfigurationen.
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: m365-security
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
- m365solution-identitydevice
- m365solution-scenario
ms.technology: mdo
ms.openlocfilehash: 5f1f9d8c5f4e507e62de1b815d2345fc6b70bfea
ms.sourcegitcommit: 8e696c084d097520209c864140af11aa055b979e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2021
ms.locfileid: "50097282"
---
# <a name="common-identity-and-device-access-policies"></a>Allgemeine Identitäts- und Gerätezugriffsrichtlinien

In diesem Artikel werden die allgemeinen empfohlenen Richtlinien zum Sichern des Zugriffs auf Microsoft 365-Clouddienste beschrieben, einschließlich der mit dem Azure Active Directory (Azure AD)-Anwendungsproxy veröffentlichten lokalen Anwendungen.

In diesem Leitfaden wird erläutert, wie die empfohlenen Richtlinien in einer neu bereitgestellten Umgebung bereitgestellt werden. Wenn Sie diese Richtlinien in einer separaten Laborumgebung einrichten, können Sie die empfohlenen Richtlinien verstehen und bewerten, bevor Sie das Rollout in Ihre Präproduktions- und Produktionsumgebungen bereitstellen. Ihre neu bereitgestellte Umgebung kann nur in der Cloud oder hybrid sein, um Ihre Bewertungsanforderungen zu erfüllen.

## <a name="policy-set"></a>Richtliniensatz

Das folgende Diagramm veranschaulicht den empfohlenen Satz von Richtlinien. Sie zeigt, auf welche Schutzebene sich die einzelnen Richtlinien anwenden und ob die Richtlinien für PCs, Smartphones und Tablets oder beide Gerätekategorien gelten. Außerdem wird angegeben, wo Sie diese Richtlinien konfigurieren.

[![Allgemeine Richtlinien zum Konfigurieren des Identitäts- und Gerätezugriffs](../../media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)

[Sehen Sie sich eine größere Version dieses Bilds an.](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)

Hier ist eine einseitige PDF-Zusammenfassung mit Links zu den einzelnen Richtlinien:

[![Miniaturbild für Identitäts- und Geräteschutz für Microsoft 365-Handzettel](../../media/microsoft-365-policies-configurations/MSFT-cloud-architecture-identity-device-protection-handout.png)](../../downloads/MSFT-cloud-architecture-identity-device-protection-handout.pdf) <br> [Als PDF anzeigen](../../downloads/MSFT-cloud-architecture-identity-device-protection-handout.pdf) \| [Als PDF herunterladen](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/MSFT-cloud-architecture-identity-device-protection-handout.pdf)

Im restlichen Teil dieses Artikels wird beschrieben, wie Sie diese Richtlinien konfigurieren.

> [!NOTE]
> Die Verwendung der mehrstufigen Authentifizierung (Multi-Factor Authentication, MFA) wird empfohlen, bevor Sie Geräte in Intune registrieren, um sicherzustellen, dass das Gerät im Besitz des beabsichtigten Benutzers ist. Sie müssen Geräte in Intune registrieren, bevor Sie Richtlinien zur Gerätekonformität erzwingen können.

Um Ihnen Zeit zum Ausführen dieser Aufgaben zu geben, wird empfohlen, die Basisrichtlinien in der in dieser Tabelle aufgeführten Reihenfolge zu implementieren. Die Richtlinien für die MFA für vertrauliche und hochgradig regulierte Schutzebenen können jedoch jederzeit implementiert werden.

|Schutzebene|Richtlinien|Weitere Informationen|
|---|---|---|
|**Basisplan**|[MFA erforderlich, wenn das Anmelderisiko *mittel oder* hoch *ist*](#require-mfa-based-on-sign-in-risk)||
||[Blockieren von Clients, die die moderne Authentifizierung nicht unterstützen](#block-clients-that-dont-support-multi-factor)|Clients, die keine moderne Authentifizierung verwenden, können Richtlinien für bedingten Zugriff umgehen, daher ist es wichtig, diese zu blockieren.|
||[Nutzer mit hohem Risiko müssen das Kennwort ändern](#high-risk-users-must-change-password)|Erzwingt, dass Benutzer ihr Kennwort bei der Anmeldung ändern, wenn für ihr Konto Aktivität mit hohem Risiko erkannt wird.|
||[Anwenden von Richtlinien zum Schutz von App-Daten](#apply-app-data-protection-policies)|Eine Intune App Protection-Richtlinie pro Plattform (Windows, iOS/iPadOS, Android).|
||[Genehmigte Apps und App-Schutz erforderlich](#require-approved-apps-and-app-protection)|Erzwingt den Schutz mobiler Apps für Smartphones und Tablets mit iOS, iPadOS oder Android.|
||[Definieren von Gerätekonformitätsrichtlinien](#define-device-compliance-policies)|Eine Richtlinie für jede Plattform.|
||[Kompatible PCs erforderlich](#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Erzwingt die Verwaltung von PCs mit Windows oder MacOS durch Intune.|
|**Vertraulich**|[MFA erforderlich, wenn das Anmelderisiko *niedrig,* *mittel* oder hoch *ist*](#require-mfa-based-on-sign-in-risk)||
||[Kompatible *PCs* und mobile Geräte erforderlich](#require-compliant-pcs-and-mobile-devices)|Erzwingt die Verwaltung von Intune für PCs (Windows oder MacOS) und Smartphones oder Tablets (iOS, iPadOS oder Android).|
|**Streng geregelt**|[*MFA* immer erforderlich](#require-mfa-based-on-sign-in-risk)|
|

## <a name="assigning-policies-to-groups-and-users"></a>Zuweisen von Richtlinien zu Gruppen und Benutzern

Identifizieren Sie vor dem Konfigurieren von Richtlinien die Azure AD-Gruppen, die Sie für jede Schutzebene verwenden. In der Regel gilt der grundlegende Schutz für alle In der Organisation. Einem Benutzer, der sowohl für den grundlegenden als auch den vertraulichen Schutz einbezogen wird, werden alle Basisrichtlinien sowie die vertraulichen Richtlinien angewendet. Der Schutz ist kumulativ, und die restriktivste Richtlinie wird erzwungen.

Eine empfohlene Vorgehensweise besteht in der Erstellung einer Azure AD-Gruppe für den Ausschluss des bedingten Zugriffs. Fügen Sie diese Gruppe allen Richtlinien für bedingten  Zugriff im Wert **"Ausschließen"** der Einstellung "Benutzer und Gruppen" im Abschnitt **"Zuweisungen"** hinzu. Auf diese Weise erhalten Sie eine Methode, um einem Benutzer während der Behandlung von Zugriffsproblemen Zugriffsrechte zu ermöglichen. Dies wird nur als temporäre Lösung empfohlen. Überwachen Sie diese Gruppe auf Änderungen, und stellen Sie sicher, dass die Ausschlussgruppe nur wie beabsichtigt verwendet wird.

Hier ist ein Beispiel für gruppenzuweisung und Ausschlüsse für MFA erforderlich.

![Beispielgruppenzuweisung und Ausschlüsse für MFA-Richtlinien](../../media/microsoft-365-policies-configurations/identity-access-policies-assignment.png)

Dies sind die Ergebnisse:

- Alle Benutzer müssen MFA verwenden, wenn das Anmelderisiko mittel oder hoch ist.

- Mitglieder der Gruppe "Führungskräfte" müssen MFA verwenden, wenn das Anmelderisiko niedrig, mittel oder hoch ist.

  In diesem Fall entsprechen Die Mitglieder der Gruppe "Führungskräfte" sowohl den Basisrichtlinien als auch den vertraulichen Richtlinien für bedingten Zugriff. Die Zugriffssteuerungen für beide Richtlinien werden kombiniert, was in diesem Fall der vertraulichen Richtlinie für bedingten Zugriff entspricht.

- Mitglieder der Gruppe "Top Secret Project X" müssen immer MFA verwenden.

  In diesem Fall entsprechen Die Mitglieder der Gruppe "Top Secret Project X" sowohl den Basisrichtlinien als auch den streng regulierten Richtlinien für bedingten Zugriff. Die Zugriffssteuerungen für beide Richtlinien werden kombiniert. Da die Zugriffssteuerung für die stark regulierte Richtlinie für bedingten Zugriff restriktiver ist, wird sie verwendet.

Seien Sie vorsichtig, wenn Sie auf Gruppen und Benutzer höhere Schutzebenen anwenden. Beispielsweise müssen Mitglieder der Gruppe "Streng geheimes Projekt X" bei jeder Anmeldung MFA verwenden, auch wenn sie nicht an stark regulierten Inhalten für Project X arbeiten.

Alle Azure AD-Gruppen, die im Rahmen dieser Empfehlungen erstellt wurden, müssen als Microsoft 365-Gruppen erstellt werden. Dies ist wichtig für die Bereitstellung von Vertraulichkeitsbezeichnungen beim Sichern von Dokumenten in Microsoft Teams und SharePoint.

![Bildschirmaufnahme zum Erstellen von Microsoft 365-Gruppen](../../media/microsoft-365-policies-configurations/identity-device-AAD-groups.png)

## <a name="require-mfa-based-on-sign-in-risk"></a>MFA basierend auf dem Anmelderisiko erforderlich

Ihre Benutzer sollten sich vor der Verwendung für MFA registrieren lassen. Wenn Sie über Microsoft 365 E5, Microsoft 365 E3 mit dem Identitäts-& Threat Protection-Add-On, Office 365 mit EMS E5 oder einzelne Azure AD Premium -P2-Lizenzen verfügen, können Sie die Registrierungsrichtlinie für die MFA mit Azure AD Identity Protection verwenden, um zu verlangen, dass sich Benutzer für MFA registrieren. Die [erforderliche Arbeit umfasst](identity-access-prerequisites.md) die Registrierung aller Benutzer mit MFA.

Nachdem Ihre Benutzer registriert wurden, können Sie MFA für die Anmeldung mit einer neuen Richtlinie für bedingten Zugriff verlangen.

1. Navigieren Sie zum [Azure-Portal](https://portal.azure.com), und melden Sie sich mit Ihren Anmeldeinformationen an.
2. Wählen Sie in der Liste der Azure-Dienste **Azure Active Directory aus.**
3. Wählen Sie **in der** Liste "Verwalten" die Option **"Sicherheit"** und dann "Bedingter **Zugriff" aus.**
4. Wählen **Sie "Neue Richtlinie"** aus, und geben Sie den Namen der neuen Richtlinie ein.

In den folgenden Tabellen werden die Richtlinieneinstellungen für bedingten Zugriff beschrieben, um MFA basierend auf dem Anmelderisiko zu erfordern.

Im Abschnitt **"Aufgaben":**

|Setting|Eigenschaften|Werte|Hinweise|
|---|---|---|---|
|Benutzer und Gruppen|Einschließen|**Wählen Sie Benutzer und Gruppen > Benutzer und Gruppen aus:** Wählen Sie bestimmte Gruppen aus, die Zielbenutzerkonten enthalten.|Beginnen Sie mit der Gruppe, die Pilotbenutzerkonten enthält.|
||Ausschließen|**Benutzer und Gruppen:** Wählen Sie Ihre Ausnahmegruppe für bedingten Zugriff aus. Dienstkonten (App-Identitäten).|Die Mitgliedschaft sollte bei Bedarf temporär geändert werden.|
|Cloud-Apps oder -Aktionen|**Cloud apps > Include**|**Wählen Sie Apps** aus: Wählen Sie die Apps aus, auf die diese Richtlinie angewendet werden soll. Wählen Sie beispielsweise Exchange Online aus.||
|Bedingungen|||Konfigurieren Sie Bedingungen, die für Ihre Umgebung und Anforderungen spezifisch sind.|
||Anmelderisiko||Weitere Informationen finden Sie in der folgenden Tabelle.|
|

### <a name="sign-in-risk-condition-settings"></a>Einstellungen für Anmelderisikobedingung

Wenden Sie die Risikoebeneneinstellungen basierend auf der Zielschutzebene an.

|Schutzebene|Benötigte Risikoebenenwerte|Aktion|
|---|---|---|
|Baseline|Hoch, Mmittel|Überprüfen Sie beides.|
|Vertraulich|Hoch, mittel, niedrig|Überprüfen Sie alle drei.|
|Streng geregelt||Lassen Sie alle Optionen deaktiviert, um MFA immer zu erzwingen.|
|

Im Abschnitt **"Access-Steuerelemente":**

|Setting|Eigenschaften|Werte|Aktion|
|---|---|---|---|
|Gewähren|**Grant access**||Auswählen|
|||**Mehrstufige Authentifizierung erforderlich**|Scheck|
||**Alle ausgewählten Steuerelemente erforderlich**||Auswählen|
|

Wählen **Sie "Auswählen"** aus, um die Einstellungen **für die Erteilung zu** speichern.

Wählen Sie schließlich **"Ein"** für **"Richtlinie aktivieren"** und dann **"Erstellen" aus.**

Erwägen Sie auch die Verwendung des [Tools "Was wäre](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) wenn", um die Richtlinie zu testen.

## <a name="block-clients-that-dont-support-multi-factor"></a>Blockieren von Clients, die keine mehrstufigen Clients unterstützen

Verwenden Sie die Einstellungen in diesen Tabellen für eine Richtlinie für bedingten Zugriff, um Clients zu blockieren, die die mehrstufige Authentifizierung nicht unterstützen.

In [diesem Artikel finden](../../enterprise/microsoft-365-client-support-multi-factor-authentication.md) Sie eine Liste der Clients in Microsoft 365, die die mehrstufige Authentifizierung unterstützen.

Im Abschnitt **"Aufgaben":**

|Setting|Eigenschaften|Werte|Hinweise|
|---|---|---|---|
|Benutzer und Gruppen|Einschließen|**Wählen Sie Benutzer und Gruppen > Benutzer und Gruppen** aus: Wählen Sie bestimmte Gruppen aus, die Zielbenutzerkonten enthalten.|Beginnen Sie mit der Gruppe, die Pilotbenutzerkonten enthält.|
||Ausschließen|**Benutzer und Gruppen:** Wählen Sie Ihre Ausnahmegruppe für bedingten Zugriff aus. Dienstkonten (App-Identitäten).|Die Mitgliedschaft sollte bei Bedarf vorübergehend geändert werden.|
|Cloud-Apps oder -Aktionen|**Cloud apps > Include**|**Wählen Sie Apps** aus: Wählen Sie die Apps aus, die den Clients entspricht, die die moderne Authentifizierung nicht unterstützen.||
|Bedingungen|**Client-Apps**|Wählen **Sie "Ja"** für **"Konfigurieren" aus.** <p> Deaktivieren Der Kontrollkästchen für **Browser- und** **mobile Apps und Desktopclients**||
|

Im Abschnitt **"Access-Steuerelemente":**

|Setting|Eigenschaften|Werte|Aktion|
|---|---|---|---|
|Gewähren|**Zugriff blockieren**||Auswählen|
||**Alle ausgewählten Steuerelemente erforderlich**||Auswählen|
|

Wählen **Sie "Auswählen"** aus, um die Einstellungen **für die Erteilung zu** speichern.

Wählen Sie schließlich **"Ein"** für **"Richtlinie aktivieren"** und dann **"Erstellen" aus.**

Erwägen Sie die Verwendung des [Tools "Was wäre](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) wenn", um die Richtlinie zu testen.

Für Exchange Online können Sie Authentifizierungsrichtlinien verwenden, um die [Standardauthentifizierung](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online)zu deaktivieren, wodurch alle Clientzugriffsanforderungen zur Verwendung der modernen Authentifizierung erzwingt werden.

## <a name="high-risk-users-must-change-password"></a>Nutzer mit hohem Risiko müssen das Kennwort ändern

Um sicherzustellen, dass die gefährdeten Konten aller Benutzer mit hohem Risiko bei der Anmeldung zu einer Kennwortänderung gezwungen werden, müssen Sie die folgende Richtlinie anwenden.

Melden Sie sich im [Microsoft Azure-Portal (https://portal.azure.com)](https://portal.azure.com/) mit Ihren Administratoranmeldeinformationen an, und wechseln Sie dann zu **Azure AD Identity Protection > Richtlinie zum Benutzerrisiko**.

Im Abschnitt **"Aufgaben":**

|Typ|Eigenschaften|Werte|Aktion|
|---|---|---|---|
|Users|Einschließen|**Alle Benutzer**|Auswählen|
|Benutzerrisiko|**High**||Auswählen|
|

Im zweiten **Aufgabenabschnitt:**

|Typ|Eigenschaften|Werte|Aktion|
|---|---|---|---|
|Zugriff|**Zugriff zulassen**||Auswählen|
|||**Kennwortänderung erforderlich**|Scheck|
|

Wählen Sie **"Fertig"** aus, um die **Zugriffseinstellungen zu** speichern.

Wählen Sie schließlich **"Ein"** für **"Richtlinie erzwingen"** und dann "Speichern" **aus.**

Erwägen Sie die Verwendung des [Tools "Was wäre](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) wenn", um die Richtlinie zu testen.

Verwenden Sie diese Richtlinie in Verbindung mit dem Konfigurieren des Azure AD-Kennwortschutzes, der bekannte schwache Kennwörter und deren Varianten sowie zusätzliche schwache Begriffe erkennt und blockiert, die für Ihre Organisation spezifisch sind. [](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) Durch die Verwendung des Azure AD-Kennwortschutzes wird sichergestellt, dass geänderte Kennwörter starke Kennwörter sind.

## <a name="apply-app-data-protection-policies"></a>Anwenden von APP-Datenschutzrichtlinien

App Protection Policies (APP) definieren, welche Apps zulässig sind und welche Aktionen sie mit den Daten Ihrer Organisation ausführen können. Die in APP verfügbaren Optionen ermöglichen Es Organisationen, den Schutz an ihre spezifischen Anforderungen anzupassen. Für einige ist es möglicherweise nicht offensichtlich, welche Richtlinieneinstellungen erforderlich sind, um ein vollständiges Szenario zu implementieren. Damit Organisationen die Sicherheit mobiler Clientendpunkte priorisieren können, hat Microsoft taxonomie für das App-Datenschutz-Framework für die Verwaltung mobiler iOS- und Android-Apps eingeführt.

Das Framework für den Schutz von APP-Daten ist in drei verschiedene Konfigurationsebenen geordnet, auf der jede Ebene auf der vorherigen Ebene aufbaut:

- **Der grundlegende Datenschutz in** Unternehmen (Stufe 1) stellt sicher, dass Apps mit einer PIN geschützt und verschlüsselt sind und selektive Zurücklöschvorgänge durchführt. Für Android-Geräte überprüft diese Stufe den Android-Geräte-Nachweis. Dies ist eine Einstiegsebenenkonfiguration, die eine ähnliche Steuerung des Datenschutzes in Exchange Online-Postfachrichtlinien bietet und DIE IT und die Benutzerpopulation in APP einleite.
- **Der erweiterte Datenschutz** in Unternehmen (Stufe 2) führt Mechanismen zur Verhinderung von Datenverlusten und Mindestanforderungen des Betriebssystems ein. Dies ist die Konfiguration, die für die meisten mobilen Benutzer gilt, die auf Arbeits- oder Schuldaten zugreifen.
- **Der hohe Datenschutz** in Unternehmen (Stufe 3) führt erweiterte Datenschutzmechanismen, eine erweiterte PIN-Konfiguration und app-mobile Bedrohungsabwehr ein. Diese Konfiguration ist für Benutzer wünschenswert, die auf Daten mit hohem Risiko zugreifen.

Um die spezifischen Empfehlungen für die einzelnen Konfigurationsebenen und die mindesten zu schützende Apps zu sehen, überprüfen Sie das [Datenschutzframework mithilfe von App-Schutzrichtlinien.](https://docs.microsoft.com/mem/intune/apps/app-protection-framework)

Unter Verwendung der in Identitäts- und [Gerätezugriffskonfigurationen](microsoft-365-policies-configurations.md)beschriebenen Prinzipien sind die Schutzebenen "Basisplan" und "Vertraulich" eng mit den erweiterten Datenschutzeinstellungen der Stufe 2 im Unternehmen verknüpft. Die Schutzebene für hochgradig regulierte Daten ist eng mit den Einstellungen für hohen Datenschutz in Unternehmen der Stufe 3 verknüpft.

|Schutzebene|App-Schutz-Richtlinie|Weitere Informationen|
|---|---|---|
|Baseline|[Erweiterter Datenschutz auf Ebene 2](https://docs.microsoft.com/mem/intune/apps/app-protection-framework#level-2-enterprise-enhanced-data-protection)|Die in Ebene 2 erzwungenen Richtlinieneinstellungen umfassen alle richtlinieneinstellungen, die für Stufe 1 empfohlen werden, und fügen nur die folgenden Richtlinieneinstellungen hinzu oder aktualisieren sie, um mehr Steuerelemente und eine komplexere Konfiguration als Stufe 1 zu implementieren.|
|Vertraulich|[Erweiterter Datenschutz auf Ebene 2](https://docs.microsoft.com/mem/intune/apps/app-protection-framework#level-2-enterprise-enhanced-data-protection)|Die in Ebene 2 erzwungenen Richtlinieneinstellungen umfassen alle richtlinieneinstellungen, die für Stufe 1 empfohlen werden, und fügen nur die folgenden Richtlinieneinstellungen hinzu oder aktualisieren sie, um mehr Steuerelemente und eine komplexere Konfiguration als Stufe 1 zu implementieren.|
|Hochgradig reguliert|[Hoher Datenschutz für Unternehmen der Stufe 3](https://docs.microsoft.com/mem/intune/apps/app-protection-framework#level-3-enterprise-high-data-protection)|Die in Ebene 3 erzwungenen Richtlinieneinstellungen umfassen alle Richtlinieneinstellungen, die für die Ebene 1 und 2 empfohlen werden, und fügen nur die folgenden Richtlinieneinstellungen hinzu oder aktualisieren sie, um mehr Steuerelemente und eine komplexere Konfiguration als Stufe 2 zu implementieren.|
|

Zum Erstellen einer neuen App-Schutzrichtlinie für jede Plattform (iOS und Android) innerhalb von Microsoft Endpoint Manager mithilfe der Datenschutzframeworkeinstellungen können Sie:

1. Erstellen Sie die Richtlinien manuell, indem Sie die Schritte in "Erstellen und Bereitstellen von [App-Schutzrichtlinien mit Microsoft Intune" ausführen.](https://docs.microsoft.com/mem/intune/apps/app-protection-policies)
2. Importieren Sie die [Intune App Protection Policy Configuration Framework-JSON-Beispielvorlagen](https://github.com/microsoft/Intune-Config-Frameworks/tree/master/AppProtectionPolicies) mit den [PowerShell-Skripts von Intune.](https://github.com/microsoftgraph/powershell-intune-samples)

## <a name="require-approved-apps-and-app-protection"></a>Erfordert genehmigte Apps und app-Schutz

Zum Erzwingen der app-Schutzrichtlinien, die Sie in Intune angewendet haben, müssen Sie eine Richtlinie für bedingten Zugriff erstellen, um genehmigte Client-Apps und die Bedingungen, die in den Richtlinien für den App-Schutz festgelegt erforderlich sind.

Das Erzwingen von Richtlinien für den Schutz von Apps erfordert eine Reihe von Richtlinien, die unter "App-Schutzrichtlinie erforderlich" für den [Cloud-App-Zugriff mit bedingten Zugriff beschrieben sind.](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access) Diese Richtlinien sind jeweils in diesem empfohlenen Satz von Identitäts- und Zugriffskonfigurationsrichtlinien enthalten.

Um die Richtlinie für bedingten Zugriff zu erstellen, die genehmigte Apps und den Schutz von APPS erfordert, führen Sie "Schritt 1: Konfigurieren einer Azure AD-Richtlinie für bedingten Zugriff für Microsoft 365" in Szenario [1 aus: Microsoft 365-Apps](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies)benötigen genehmigte Apps mit App-Schutzrichtlinien, die Outlook für iOS und Android ermöglichen, aber die Verbindung von OAuth-fähigen Exchange ActiveSync-Clients mit Exchange Online verhindern.

   > [!NOTE]
   > Diese Richtlinie stellt sicher, dass mobile Benutzer mithilfe der entsprechenden Apps auf alle Office-Endpunkte zugreifen können.

Wenn Sie den mobilen Zugriff auf Exchange Online aktivieren, implementieren Sie [Block ActiveSync-Clients,](secure-email-recommended-policies.md#block-activesync-clients)die Exchange ActiveSync, die die Standardauthentifizierung nutzen, daran hindert, eine Verbindung mit Exchange Online zu herstellen. Diese Richtlinie ist nicht in der Abbildung oben in diesem Artikel dargestellt. Es wird in Richtlinienempfehlungen zum Sichern von E-Mails [beschrieben und abgebildet.](secure-email-recommended-policies.md)

Um die Richtlinie für bedingten Zugriff zu erstellen, die Edge für iOS und Android erfordert, führen Sie "Schritt 2: Konfigurieren einer Azure AD-Richtlinie für bedingten Zugriff für Microsoft 365" in Szenario [2 aus: Browser-Apps](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-2-browser-apps-require-approved-apps-with-app-protection-policies)erfordern genehmigte Apps mit App-Schutzrichtlinien, die Edge für iOS und Android ermöglichen, aber andere Webbrowser für mobile Geräte daran blockieren, eine Verbindung mit Microsoft 365-Endpunkten zu herstellen.

 Diese Richtlinien nutzen die Erteilungssteuerelemente ["Genehmigte Client-App erforderlich"](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-approved-client-app) und ["App-Schutzrichtlinie erforderlich".](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy)

Durch das Blockieren der Legacyauthentifizierung für andere Client-Apps auf iOS- und Android-Geräten wird sichergestellt, dass diese Clients Richtlinien für bedingten Zugriff nicht umgehen können. Wenn Sie den Anweisungen in diesem Artikel folgen, haben Sie bereits Blockclients konfiguriert, die die moderne [Authentifizierung nicht unterstützen.](#block-clients-that-dont-support-multi-factor)

<!---
With Conditional Access, organizations can restrict access to approved (modern authentication capable) iOS and Android client apps with Intune app protection policies applied to them. Several Conditional Access policies are required, with each policy targeting all potential users. Details on creating these policies can be found in [Require app protection policy for cloud app access with Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access).

1. Follow "Step 1: Configure an Azure AD Conditional Access policy for Microsoft 365" in [Scenario 1: Microsoft 365 apps require approved apps with app protection policies](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies), which allows Outlook for iOS and Android, but blocks OAuth capable Exchange ActiveSync clients from connecting to Exchange Online.

   > [!NOTE]
   > This policy ensures mobile users can access all Office endpoints using the applicable apps.

2. If enabling mobile access to Exchange Online, implement [Block ActiveSync clients](secure-email-recommended-policies.md#block-activesync-clients), which prevents Exchange ActiveSync clients leveraging basic authentication from connecting to Exchange Online.

   The above policies leverage the grant controls [Require approved client app](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-approved-client-app) and [Require app protection policy](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy).

3. Disable legacy authentication for other client apps on iOS and Android devices. For more information, see [Block clients that don't support modern authentication](#block-clients-that-dont-support-modern-authentication).
-->

## <a name="define-device-compliance-policies"></a>Definieren von Richtlinien zur Gerätekonformität

Richtlinien zur Gerätekonformität definieren die Anforderungen, die Geräte erfüllen müssen, um als konform festgelegt zu werden. Sie erstellen Intune-Gerätekonformitätsrichtlinien im Microsoft Endpoint Manager Admin Center.

Sie müssen eine Richtlinie für jeden PC, jedes Smartphone oder jede Tablet-Plattform erstellen:

- Administrator für Android-Geräte
- Android Enterprise
- iOS/iPadOS
- macOS
- Windows 8.1 und höher
- Windows 10 und höher

Um Gerätekonformitätsrichtlinien zu erstellen, melden Sie sich mit Ihren Administratoranmeldeinformationen beim [Microsoft Endpoint Manager Admin Center](https://endpoint.microsoft.com) an, und navigieren Sie dann zu Richtlinien zur Gerätekonformität.  \>  \>  Wählen Sie **"Richtlinie erstellen" aus.**

Damit Gerätekonformitätsrichtlinien bereitgestellt werden können, müssen sie Benutzergruppen zugewiesen werden. Sie weisen eine Richtlinie zu, nachdem Sie sie erstellt und gespeichert haben. Wählen Sie im Admin Center die Richtlinie und dann **"Zuordnungen" aus.** Nachdem Sie die Gruppen ausgewählt haben,  die sie erhalten möchten, wählen Sie "Speichern" aus, um diese Gruppenzuweisung zu speichern und die Richtlinie bereitstellen.

Schrittweise Anleitungen zum Erstellen von Compliancerichtlinien in Intune finden Sie unter "Erstellen einer Compliancerichtlinie [in Microsoft Intune"](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy) in der Intune-Dokumentation.

### <a name="recommended-settings-for-windows-10-and-later"></a>Empfohlene Einstellungen für Windows 10 und höher

Die folgenden Einstellungen werden für PCs unter Windows 10 und höher empfohlen, wie in Schritt **2 konfiguriert:** Complianceeinstellungen , des Richtlinienerstellungsprozesses.

Informationen **zu den > des Windows Health Attestation Service** finden Sie in dieser Tabelle.

|Eigenschaften|Wert|Aktion|
|---|---|---|
|BitLocker erforderlich|Erforderlich|Auswählen|
|Aktivieren des sicheren Starts auf dem Gerät erforderlich|Erforderlich|Auswählen|
|Codeintegrität erforderlich|Erforderlich|Auswählen|
|

Geben **Sie für Geräteeigenschaften** geeignete Werte für Betriebssystemversionen basierend auf Ihren IT- und Sicherheitsrichtlinien an.

Wählen **Sie für configuration Manager Compliance** die Option **"Erforderlich" aus.**

Informationen **zur Systemsicherheit** finden Sie in dieser Tabelle.

|Typ|Eigenschaften|Wert|Aktion|
|---|---|---|---|
|Kennwort|Kennwort zum Entsperren mobiler Geräte erforderlich|Erforderlich|Auswählen|
||Einfache Kennwörter|Blockieren|Auswählen|
||Kennworttyp|Geräte standard|Auswählen|
||Minimale Kennwortlänge|6 |Typ|
||Maximale Inaktivität in Minuten, bevor ein Kennwort erforderlich ist|15 |Typ <p> Diese Einstellung wird für Die Versionen 4.0 und höher für Android oder FÜRX 4.0 und höher unterstützt. Für iOS-Geräte wird sie für iOS 8.0 und höher unterstützt.|
||Kennwortablauf (Tage)|41|Typ|
||Anzahl der vorherigen Kennwörter, um die Wiederverwendung zu verhindern|5 |Typ|
||Kennwort erforderlich, wenn das Gerät aus dem Leerlaufzustand zurückkehrt (Mobil und Holographic)|Erforderlich|Verfügbar für Windows 10 und höher|
|Verschlüsselung|Verschlüsselung der Datenspeicherung auf dem Gerät|Erforderlich|Auswählen|
|Gerätesicherheit|Firewall|Erforderlich|Auswählen|
||Antivirus|Erforderlich|Auswählen|
||Antispyware|Erforderlich|Auswählen <p> Für diese Einstellung ist eine Anti-Spyware-Lösung erforderlich, die im Windows Security Center registriert ist.|
|Defender|Microsoft Defender Antimalware|Erforderlich|Auswählen|
||Mindestversion von Microsoft Defender Antimalware||Typ <p> Wird nur für Windows 10-Desktop unterstützt. Microsoft empfiehlt Versionen, die nicht mehr als fünf Weniger als die neueste Version zurück liegen.|
||Microsoft Defender Antimalware-Signatur auf dem neuesten Stand|Erforderlich|Auswählen|
||Echtzeitschutz|Erforderlich|Auswählen <p> Nur für Windows 10-Desktop unterstützt|
|

#### <a name="microsoft-defender-for-endpoint"></a>Microsoft Defender für Endpunkt

|Typ|Eigenschaften|Wert|Aktion|
|---|---|---|---|
|Regeln für Microsoft Defender für Endpunkte|Das Gerät muss sich bei oder unter der Computerrisikopunktzahl besennen|Mittel|Auswählen|
|

## <a name="require-compliant-pcs-but-not-compliant-phones-and-tablets"></a>Kompatible PCs (jedoch keine kompatiblen Telefone und Tablets) erfordern

Bevor Sie eine Richtlinie hinzufügen, um kompatible PCs erforderlich zu machen, müssen Sie Geräte für die Verwaltung bei Intune registrieren. Die Verwendung der mehrstufigen Authentifizierung wird empfohlen, bevor Sie Geräte bei Intune registrieren, um sich zu sicher zu geben, dass das Gerät im Besitz des beabsichtigten Benutzers ist.

So fordern Sie kompatible PCs an:

1. Navigieren Sie zum [Azure-Portal](https://portal.azure.com), und melden Sie sich mit Ihren Anmeldeinformationen an.
2. Wählen Sie in der Liste der Azure-Dienste **Azure Active Directory aus.**
3. Wählen Sie **in der** Liste "Verwalten" die Option **"Sicherheit"** und dann "Bedingter **Zugriff" aus.**
4. Wählen **Sie "Neue Richtlinie"** aus, und geben Sie den Namen der neuen Richtlinie ein.

5. Wählen **Sie unter**"Zuweisungen" **"Benutzer und Gruppen"** aus, und geben Sie an, auf wen die Richtlinie angewendet werden soll. Schließen Sie auch die Ausschlussgruppe für bedingten Zugriff aus.

6. Wählen **Sie unter "Aufgaben"** die **Option "Cloud-Apps oder -Aktionen" aus.**

7. For **Include**, choose **Select apps > Select**, and then select the desired apps from the Cloud **apps** list. Wählen Sie beispielsweise Exchange Online aus. Wählen **Sie "Auswählen"** aus, wenn Sie fertig sind.

8. Wenn Sie kompatible PCs (aber keine kompatiblen Telefone und Tablets) benötigen **möchten,** wählen Sie unter "Aufgaben" die Option "Bedingungen > **Geräteplattformen" aus.** Wählen **Sie "Ja"** für **"Konfigurieren" aus.** Wählen **Sie "Geräteplattformen auswählen",** **"Windows"** und **"macOS"** und dann "Fertig" **aus.**

9. Wählen **Sie unter "Access"-Steuerelemente** **"Gewähren" aus.**

10. Choose **Grant access** and then check Require device to be marked as **compliant**. Wählen Sie für mehrere Steuerelemente die Option **"Alle ausgewählten Steuerelemente erforderlich" aus.** Wählen Sie nach Abschluss des Vorgangs **"Auswählen" aus.**

11. Wählen **Sie "Ein"** **für "Richtlinie aktivieren"** und dann **"Erstellen" aus.**

> [!NOTE]
> Stellen Sie sicher, dass Ihr Gerät kompatibel ist, bevor Sie diese Richtlinie aktivieren. Andernfalls könnten Sie gesperrt werden und können diese Richtlinie erst ändern, wenn Ihr Benutzerkonto der Ausschlussgruppe für bedingten Zugriff hinzugefügt wurde.

## <a name="require-compliant-pcs-and-mobile-devices"></a>Kompatible *PCs* und mobile Geräte erforderlich

So fordern Sie die Kompatibilität für alle Geräte an:

1. Navigieren Sie zum [Azure-Portal](https://portal.azure.com), und melden Sie sich mit Ihren Anmeldeinformationen an.
2. Wählen Sie in der Liste der Azure-Dienste **Azure Active Directory aus.**
3. Wählen Sie **in der** Liste "Verwalten" die Option **"Sicherheit"** und dann "Bedingter **Zugriff" aus.**
4. Wählen **Sie "Neue Richtlinie"** aus, und geben Sie den Namen der neuen Richtlinie ein.

5. Wählen **Sie unter**"Zuweisungen" **"Benutzer und Gruppen"** aus, und geben Sie an, auf wen die Richtlinie angewendet werden soll. Schließen Sie auch die Ausschlussgruppe für bedingten Zugriff aus.

6. Wählen **Sie unter "Aufgaben"** die **Option "Cloud-Apps oder -Aktionen" aus.**

7. For **Include**, choose **Select apps > Select**, and then select the desired apps from the Cloud **apps** list. Wählen Sie beispielsweise Exchange Online aus. Wählen **Sie "Auswählen"** aus, wenn Sie fertig sind.

8. Wählen **Sie unter "Access"-Steuerelemente** **"Gewähren" aus.**

9. Choose **Grant access** and then check Require device to be marked as **compliant**. Wählen Sie für mehrere Steuerelemente die Option **"Alle ausgewählten Steuerelemente erforderlich" aus.** Wählen Sie nach Abschluss des Vorgangs **"Auswählen" aus.**

10. Wählen **Sie "Ein"** **für "Richtlinie aktivieren"** und dann **"Erstellen" aus.**

> [!NOTE]
> Stellen Sie sicher, dass Ihr Gerät kompatibel ist, bevor Sie diese Richtlinie aktivieren. Andernfalls könnten Sie gesperrt werden und können diese Richtlinie erst ändern, wenn Ihr Benutzerkonto der Ausschlussgruppe für bedingten Zugriff hinzugefügt wurde.

## <a name="next-step"></a>Nächster Schritt

[![Schritt 3: Richtlinien für Gastbenutzer und externe Benutzer](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-3.png)](identity-access-policies-guest-access.md)

[Informationen zu Richtlinienempfehlungen für Gastbenutzer und externe Benutzer](identity-access-policies-guest-access.md)
