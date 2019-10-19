---
title: Allgemeine Richtlinien für Identitäts-und Geräte Zugriff – Microsoft 365 Enterprise | Microsoft-Dokumente
description: Beschreibt die Richtlinien für Empfehlungen von Microsoft zur Anwendung von Identitäts- und Gerätezugriffsrichtlinien und -konfigurationen
author: BrendaCarter
manager: Laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.author: bcarter
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: 3739f9f0ab7a7faa9c0467b29cc6c401254e8f58
ms.sourcegitcommit: aa878adee65a1cdf87d4cabda41ab35673957f40
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2019
ms.locfileid: "37590499"
---
# <a name="common-identity-and-device-access-policies"></a>Allgemeine Identitäts- und Gerätezugriffsrichtlinien
In diesem Artikel werden die allgemeinen empfohlenen Richtlinien für die Sicherung des Zugriffs auf Cloud-Dienste beschrieben, einschließlich lokaler Anwendungen, die mit Azure AD-Anwendungs Proxy veröffentlicht werden. 

In diesem Leitfaden wird erläutert, wie die empfohlenen Richtlinien in einer neu bereitgestellten Umgebung bereitgestellt werden. Durch das Einrichten dieser Richtlinien in einer separaten Lab-Umgebung können Sie die empfohlenen Richtlinien vor dem Staging in ihren Vorprodukt-und Produktionsumgebungen verstehen und auswerten. Ihre neu bereitgestellte Umgebung ist möglicherweise nur in der Cloud oder Hybrid.  

## <a name="policy-set"></a>Richtliniengruppe 

Das folgende Diagramm zeigt die empfohlenen Richtlinien. Es wird angezeigt, auf welcher Schutzebene jede Richtlinie angewendet wird und ob die Richtlinien auf PCs oder Telefone und Tablets oder auf beide Gerätekategorien zutreffen. Außerdem wird angegeben, wo diese Richtlinien konfiguriert sind.

![Allgemeine Richtlinien für das Konfigurieren des Identitäts-und Gerätezugriffs](../images/Identity_device_access_policies_byplan.png)


Im Rest dieses Artikels wird beschrieben, wie Sie diese Richtlinien konfigurieren. 

Die Verwendung der mehrstufigen Authentifizierung wird empfohlen, bevor Geräte in InTune registriert werden, um sicher zu sein, dass das Gerät im Besitz des beabsichtigten Benutzers ist. Sie müssen auch Geräte in InTune registrieren, bevor Sie Geräte Konformitätsrichtlinien erzwingen.

Um Ihnen Zeit zum Ausführen dieser Aufgaben zu geben, empfehlen wir, die Basisrichtlinien in der in dieser Tabelle aufgeführten Reihenfolge zu implementieren. Die MFA-Richtlinien für vertraulichen und streng reglementierten Schutz können jedoch jederzeit implementiert werden.


|Schutzebene|Richtlinien|Weitere Informationen|
|:---------------|:-------|:----------------|
|**Basisplan**|[MFA erforderlich, wenn das Anmelde Risiko *Mittel* groß oder *hoch* ist](#require-mfa-based-on-sign-in-risk)| |
|        |[Sperrt Clients, die moderne Authentifizierung nicht unterstützen](#block-clients-that-dont-support-modern-authentication)|Clients, die keine moderne Authentifizierung verwenden, können Regeln für bedingten Zugriff umgehen, daher ist es wichtig, diese zu blockieren.|
|        |[Benutzer mit hohem Risiko müssen das Kennwort ändern](#high-risk-users-must-change-password)|Zwingt Benutzer, Ihr Kennwort zu ändern, wenn Sie sich anmelden, wenn risikoreiche Aktivitäten für Ihr Konto erkannt werden|
|        |[Definieren von App-Schutzrichtlinien](#define-app-protection-policies)|Eine Richtlinie pro Plattform (Ios, Android, Windows).|
|        |[Genehmigte apps erfordern](#require-approved-apps)|Erzwingt Mobile App Schutz für Telefone und Tablets|
|        |[Definieren von Geräte Konformitätsrichtlinien](#define-device-compliance-policies)|Eine Richtlinie für jede Plattform|
|        |[Kompatible PCs erforderlich](#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Erzwingt die Intune-Verwaltung von PCs.|
|**Vertraulich**|[MFA erforderlich, wenn das Anmelde Risiko *niedrig*, *Mittel* oder *hoch* ist](#require-mfa-based-on-sign-in-risk)| |
|         |[Erfordern von kompatiblen PCs *und* mobilen Geräten](#require-compliant-pcs-and-mobile-devices)|Erzwingt die Intune-Verwaltung für PCs und Telefon/Tablets.|
|**Streng geregelt**|[*Immer* MFA erforderlich](#require-mfa-based-on-sign-in-risk)|
| | |

## <a name="assigning-policies-to-users"></a>Zuweisen von Richtlinien zu Benutzern
Identifizieren Sie vor dem Konfigurieren von Richtlinien die Azure Ad Gruppen, die Sie für jede Schutzebene verwenden. Normalerweise gilt der Basisplan-Schutz für alle in der Organisation. Für einen Benutzer, der sowohl für den grundlegenden als auch für den vertraulichen Schutz enthalten ist, werden alle grundlegenden Richtlinien sowie die vertraulichen Richtlinien angewendet. Der Schutz ist kumulativ, und die restriktivste Richtlinie wird erzwungen. 

Eine empfohlene Vorgehensweise besteht darin, eine Azure Ad Gruppe für bedingten Zugriffs Ausschluss zu erstellen. Fügen Sie diese Gruppe zu allen bedingten Zugriffsregeln unter "ausschließen" hinzu. Dadurch erhalten Sie eine Methode zum Bereitstellen des Zugriffs auf einen Benutzer, während Sie Zugriffsprobleme beheben. Dies wird nur als temporäre Lösung empfohlen. Überwachen Sie diese Gruppe auf Änderungen, und stellen Sie sicher, dass die Ausschlussgruppe nur wie beabsichtigt verwendet wird. 

Das folgende Diagramm enthält ein Beispiel für Benutzerzuweisungen und-Ausschlüsse.

![Beispiel für eine Benutzerzuweisung und Ausschlüsse für MFA-Regeln](../images/identity-access-policies-assignment.png)

In der Abbildung wird dem "Top Secret Project X-Team" eine Richtlinie für den bedingten Zugriff zugewiesen, für die *immer*MFA erforderlich ist. Achten Sie bei der Anwendung eines höheren Schutzniveaus auf Benutzer mit Bedacht. Mitglieder dieses Projektteams müssen bei jeder Anmeldung zwei Formen der Authentifizierung bereitstellen, auch wenn Sie nicht hochregulierte Inhalte anzeigen.  

Alle Azure Ad Gruppen, die als Teil dieser Empfehlungen erstellt wurden, müssen als Office 365 Gruppen erstellt werden. Dies ist insbesondere für die Bereitstellung von AIP (Azure Information Protection) beim Schützen von Dokumenten in SharePoint Online wichtig.

![Bildschirmaufnahme zum Erstellen von Office 365 Gruppen](../images/identity-device-AAD-groups.png)


## <a name="require-mfa-based-on-sign-in-risk"></a>MFA basierend auf dem Anmelde Risiko erforderlich
Bevor Sie MFA benötigen, müssen Sie zunächst eine MFA-Registrierungsrichtlinie für den Identitätsschutz verwenden, um Benutzer für MFA zu registrieren. Nachdem Benutzer registriert wurden, können Sie MFA für die Anmeldung erzwingen. Die [erforderliche Arbeit](identity-access-prerequisites.md) umfasst das Registrieren aller Benutzer mit MFA.

So erstellen Sie eine neue bedingte Zugriffsrichtlinie: 

1. Navigieren Sie zum [Azure-Portal](https://portal.azure.com), und melden Sie sich mit Ihren Anmeldeinformationen an. Nachdem Sie sich erfolgreich angemeldet haben, wird das Azure-Dashboard angezeigt.

2. Wählen Sie im linken Menü **Azure Active Directory** aus.

3. Klicken Sie im Bereich **Sicherheit** auf **Bedingter Zugriff**.

4. Wählen Sie **Neue Richtlinie** aus.

![Grundlegende Richtlinie für bedingten Zugriff](./media/secure-email/CA-EXO-policy-1.png)

 In den folgenden Tabellen werden die Richtlinieneinstellungen für den bedingten Zugriff beschrieben, die für diese Richtlinie implementiert werden müssen.

**Aufgaben**

|Typ|Eigenschaften|Werte|Hinweise|
|:---|:---------|:-----|:----|
|Benutzer und Gruppen|Einschließen|Wählen Sie Benutzer und Gruppen aus: Wählen Sie eine spezifische Sicherheitsgruppe aus, die Zielbenutzer enthält.|Beginnen Sie mit der Sicherheitsgruppe einschließlich Pilotbenutzer|
||Ausschließen|Ausnahmesicherheitsgruppe, Dienstkonten (App-Identitäten)|Mitgliedschaft auf der Grundlage der erforderlichen temporären Basis geändert|
|Cloud-Apps|Einschließen|Wählen Sie die Apps aus, auf die diese Regel angewendet werden soll. Wählen Sie beispielsweise Office 365 Exchange Online||
|Bedingungen|Konfigurierte|Ja|Konfigurieren Sie speziell für Ihre Umgebung und Anforderungen.|
|Anmelderisiko|Risikostufe||Lesen Sie den Leitfaden in der folgenden Tabelle.|

**Anmelderisiko**

Wenden Sie die Einstellungen basierend auf der Schutzebene an, auf die Sie Zielen.

|Eigenschaft|Schutzniveau|Werte|Hinweise|
|:---|:---------|:-----|:----|
|Risikostufe|Baseline|Hoch, Mmittel|Aktivieren Sie beide|
| |Vertraulich|Hoch, Mittel, niedrig|Alle drei aktivieren|
| |Streng geregelt| |Alle Optionen deaktiviert lassen, um MFA immer zu erzwingen|

**Zugriffssteuerung**

|Typ|Eigenschaften|Werte|Hinweise|
|:---|:---------|:-----|:----|
|Gewähren|Gewähren von Zugriff|Wahr|Ausgewählt|
||MFA erforderlich|True|Check|
||Gerät muss als konform gekennzeichnet werden|False||
||Hybrides Azure AD verbundenes Gerät erforderlich|False||
||Genehmigte Client-App erforderlich|False||
||Alle ausgewählten Steuerelemente erforderlich|True|Ausgewählt|

> [!NOTE]
> Stellen Sie sicher, dass Sie diese Richtlinie aktivieren, indem Sie **auf**auswählen. In diesem Fall sollten Sie auch das [What-if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) -Tool zum Testen der Richtlinie verwenden.



## <a name="block-clients-that-dont-support-modern-authentication"></a>Sperrt Clients, die moderne Authentifizierung nicht unterstützen
1. Navigieren Sie zum [Azure-Portal](https://portal.azure.com), und melden Sie sich mit Ihren Anmeldeinformationen an. Nachdem Sie sich erfolgreich angemeldet haben, wird das Azure-Dashboard angezeigt.

2. Wählen Sie im linken Menü **Azure Active Directory** aus.

3. Klicken Sie im Bereich **Sicherheit** auf **Bedingter Zugriff**.

4. Wählen Sie **Neue Richtlinie** aus.

In den folgenden Tabellen werden die Richtlinieneinstellungen für den bedingten Zugriff beschrieben, die für diese Richtlinie implementiert werden müssen.

**Aufgaben**

|Typ|Eigenschaften|Werte|Hinweise|
|:---|:---------|:-----|:----|
|Benutzer und Gruppen|Include|Wählen Sie Benutzer und Gruppen aus: Wählen Sie eine spezifische Sicherheitsgruppe aus, die Zielbenutzer enthält.|Beginnen Sie mit der Sicherheitsgruppe einschließlich Pilotbenutzer|
||Ausschließen|Ausnahmesicherheitsgruppe, Dienstkonten (App-Identitäten)|Mitgliedschaft, die auf vorübergehender, bedarfsmäßiger Basis geändert wird|
|Cloud-Apps|Include|Wählen Sie die Apps aus, auf die diese Regel angewendet werden soll. Wählen Sie beispielsweise Office 365 Exchange Online||
|Bedingungen|Konfigurierte|Ja|Konfigurieren von Client-apps|
|Client-Apps|Konfigurierte|Ja|Mobile Apps und Desktop Clients, andere Clients (Wählen Sie beides aus)|

**Zugriffssteuerung**

|Typ|Eigenschaften|Werte|Hinweise|
|:---|:---------|:-----|:----|
|Gewähren|Zugriff blockieren|Wahr|Ausgewählt|
||MFA erforderlich|False||
||Gerät muss als konform gekennzeichnet werden|False||
||Hybrides Azure AD verbundenes Gerät erforderlich|False||
||Genehmigte Client-App erforderlich|False||
||Alle ausgewählten Steuerelemente erforderlich|True|Ausgewählt|

> [!NOTE]
> Stellen Sie sicher, dass Sie diese Richtlinie aktivieren, indem Sie **auf**auswählen. In diesem Fall sollten Sie auch das [What-if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) -Tool zum Testen der Richtlinie verwenden.



## <a name="high-risk-users-must-change-password"></a>Benutzer mit hohem Risiko müssen das Kennwort ändern
Um sicherzustellen, dass alle gefährdeten Benutzerkonten mit hohem Risiko gezwungen werden, beim Anmelden eine Kennwortänderung durchzuführen, müssen Sie die folgende Richtlinie anwenden.

Melden Sie sich im [Microsoft Azure-Portal (http://portal.azure.com)](http://portal.azure.com/) mit Ihren Administratoranmeldeinformationen an, und wechseln Sie dann zu **Azure AD Identity Protection > Richtlinie zum Benutzerrisiko**.

**Aufgaben**

|Typ|Eigenschaften|Werte|Hinweise|
|:---|:---------|:-----|:----|
|Users|Einschließen|Alle Benutzer|Ausgewählt|
||Ausschließen|Keine||
|Bedingungen|Benutzerrisiko|Hoch|Ausgewählt|

**Steuerelemente**

| Typ | Eigenschaften | Werte                  | Hinweise |
|:-----|:-----------|:------------------------|:------|
|      | Access     | Zugriff zulassen            | Wahr  |
|      | Access     | Kennwortänderung erforderlich | True  |

**Überprüfung:** nicht zutreffend

> [!NOTE]
> Stellen Sie sicher, dass Sie diese Richtlinie aktivieren, indem Sie **auf**auswählen. Sie sollten auch das [What-if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) -Tool zum Testen der Richtlinie verwenden.

## <a name="define-app-protection-policies"></a>Definieren von App-Schutzrichtlinien
App-Schutzrichtlinien definieren, welche apps zulässig sind und welche Aktionen Sie mit den Daten Ihrer Organisation durchführen können. Erstellen Sie InTune-App-Schutzrichtlinien im Azure-Portal. 

Erstellen Sie eine Richtlinie für jede Plattform:
- iOS
- Android
- Windows 10

Um eine neue APP-Schutzrichtlinie zu erstellen, melden Sie sich mit Ihren Administratoranmeldeinformationen beim Microsoft Azure-Portal an, und navigieren Sie dann zu **Client apps** > -**App-Schutzrichtlinien**. Wählen Sie **Richtlinie erstellen**aus.

Es gibt jedoch geringfügige Unterschiede in den Richtlinienoptionen für App-Schutz zwischen iOS und Android. Die folgende Richtlinie gilt speziell für Android. Verwenden Sie dies als Leitfaden für Ihre anderen Richtlinien.

Die empfohlene Liste von apps umfasst Folgendes:
- PowerPoint
- Excel
- Word
- Microsoft Teams
- Microsoft SharePoint
- Microsoft Visio Viewer
- OneDrive
- OneNote
- Outlook

In den folgenden Tabellen werden die empfohlenen Einstellungen beschrieben:

|Typ|Eigenschaften|Werte|Hinweise|
|:---|:---------|:-----|:----|
|Datenverschiebung|Android-Sicherungen verhindern|Ja|Auf iOS wird dies insbesondere iTunes und iCloud aufrufen.|
||App Übertragung von Daten an andere Apps erlauben|Richtlinienverwaltete Apps||
||Zulassen, dass die App Daten von anderen Apps empfängt|Richtlinienverwaltete Apps||
||"Speichern unter" verhindern|Ja||
||Speicherdienste zum Speichern von Unternehmensdaten auswählen|OneDrive für Unternehmen, SharePoint||
||Ausschneiden, Kopieren und Einfügen mit anderen Apps einschränken|Verwaltete Richtlinien-apps mit Paste in||
||Anzeige von Webinhalten auf den Managed Browser beschränken|Nein||
||App-Daten verschlüsseln|Ja|Wählen Sie bei iOS diese Option aus: Wenn das Gerät gesperrt ist.|
||App-Verschlüsselung deaktivieren, wenn das Gerät aktiviert ist|Ja|Deaktivieren Sie diese Einstellung, um eine Doppel Verschlüsselung zu vermeiden|
||Kontaktsynchronisierung deaktivieren|Nein||
||Drucken deaktivieren|Nein||
|Zugriff|PIN für Zugriff anfordern|Ja||
||Typ auswählen|Numeric||
||Einfache PIN zulassen|Nein||
||PIN-Länge|6||
||Fingerabdruck anstelle von PIN zulassen|Ja||
||App-PIN deaktivieren, wenn die Geräte-PIN verwaltet wird|Ja||
||Anfordern von Unternehmensanmeldeinformationen für den Zugriff|Nein||
||Erneutes Überprüfen der Zugriffsanforderung nach (Minuten)|30||
||Bildschirmaufnahme und Android-Assistenten blockieren|Nein|Bei iOS ist diese Option nicht verfügbar.|
|Anmelde Sicherheitsanforderungen|Max. Pin-Versuche|5|PIN zurücksetzen|
||Offline-Toleranzperiode|720|Zugriff blockieren|
||Offline-Intervall (in Tagen), bevor App-Daten zurückgesetzt werden|90|Daten löschen|
||Jailbroken/verwurzelte Geräte| |Daten löschen|

Wenn Sie fertig sind, wählen Sie "erstellen" aus. Wiederholen Sie die obigen Schritte, und ersetzen Sie die ausgewählte Plattform (Dropdown) durch IOS. Dadurch werden zwei App-Richtlinien erstellt, sodass nach dem Erstellen der Richtlinie Gruppen zur Richtlinie zugewiesen und bereitgestellt werden.

Informationen zum Bearbeiten der Richtlinien und Zuweisen dieser Richtlinien zu Benutzern finden Sie unter [Erstellen und Zuweisen von App-Schutzrichtlinien](https://docs.microsoft.com/intune/app-protection-policies). 

## <a name="require-approved-apps"></a>Genehmigte apps erfordern
So erfordern Sie genehmigte apps:

1. Navigieren Sie zum [Azure-Portal](https://portal.azure.com), und melden Sie sich mit Ihren Anmeldeinformationen an. Nachdem Sie sich erfolgreich angemeldet haben, wird das Azure-Dashboard angezeigt.

2. Wählen Sie im linken Menü **Azure Active Directory** aus.

3. Klicken Sie im Bereich **Sicherheit** auf **Bedingter Zugriff**.

4. Wählen Sie **Neue Richtlinie** aus.

5. Geben Sie einen Richtliniennamen ein, und wählen Sie dann die **Benutzer und Gruppen** aus, auf die Sie die Richtlinie anwenden möchten.

6. Klicken Sie auf **Cloud-Apps**.

7. Wählen **Sie apps auswählen**aus, und wählen Sie in der Liste **Cloud apps** die gewünschten Apps aus. Wählen Sie beispielsweise Office 365 Exchange Online aus. Wählen **Sie auswählen** und **Fertig**aus.

8. Wählen Sie **Bedingungen**aus, wählen Sie **Geräteplattformen**und dann **Konfigurieren** aus.

9. Wählen Sie unter **einschließen**die **Option Geräteplattformen auswählen**, **Android** und **IOS**aus. Klicken Sie erneut auf **Fertig** und **Fertig** .

10. Wählen Sie im Abschnitt **Zugriffssteuerung** die Option **Erteilen** aus.

11. Wählen Sie **Zugriff gewähren**aus, wählen Sie **genehmigte Client-App anfordern**aus. Wählen Sie für mehrere Steuerelemente **die Option ausgewählte Steuerelemente erfordern**aus, und wählen Sie dann **auswählen**aus. 

12. Klicken Sie auf **Erstellen**.

## <a name="define-device-compliance-policies"></a>Definieren von Geräte Kompatibilitätsrichtlinien

Geräte Konformitätsrichtlinien definieren die Anforderungen, die Geräte erfüllen müssen, um als konform gekennzeichnet zu sein. Erstellen von InTune-Geräte Konformitätsrichtlinien im Azure-Portal. 

Erstellen Sie eine Richtlinie für jede Plattform:
- Android
- Android Enterprise
- iOS
- macOS
- Diese Einstellung ist auf den folgenden Gerätetypen verfügbar:
- Windows 8.1 und höher
- Windows 10 und höher

Um Geräte Konformitätsrichtlinien zu erstellen, melden Sie sich mit Ihren Administratoranmeldeinformationen beim Microsoft Azure Portal an, und navigieren Sie dann zu **InTune #a0 Device Compliance**. Wählen Sie **Richtlinie erstellen**aus.

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

Damit die oben aufgeführten Richtlinien als bereitgestellt betrachtet werden, müssen sie für bestimmte Benutzergruppen gelten. Sie können dies tun, indem Sie die Richtlinie (beim Speichern) oder höher erstellen, indem Sie die Option " **Bereitstellung verwalten** " im Abschnitt " **Policy** " auswählen (gleiche Ebene wie "hinzufügen").

**Systemsicherheit**

|Typ|Eigenschaften|Werte|Hinweise|
|:---|:---------|:-----|:----|
|Kennwort|Anfordern eines Kennworts zum Entsperren mobiler Geräte|Erforderlich||
||Einfache Kennwörter|Block||
||Kennwort-Typ|Geräte Standard||
||Minimale Kennwortlänge|6||
||Maximale Anzahl von Minuten Inaktivität, bevor Kennwort erforderlich ist|15|Diese Einstellung wird für die Android-Versionen 4,0 und höher oder für Knox 4,0 und höher unterstützt. Für IOS-Geräte wird diese für IOS 8,0 und höher unterstützt.|
||Kennwortablauf (Tage)|41||
||Anzahl der vorherigen Kennwörter zur Verhinderung der Wiederverwendung|5||
||Kennwort anfordern, wenn das Gerät vom Leerlaufzustand zurückkehrt (Mobil und holographisch)|Erforderlich|Verfügbar für Windows 10 und höher|
|Verschlüsselung|Verschlüsselung der Datenspeicherung auf dem Gerät|Erforderlich||
|Gerätesicherheit|Firewall|Erforderlich||
||Antivirus|Erforderlich||
||AntiSpyware|Erforderlich|Für diese Einstellung ist eine mit dem Windows Security Center registrierte Anti-Spyware-Lösung erforderlich.|
|Defender|Windows Defender Antimalware|Erforderlich||
||Minimale Version von Windows Defender-Antischadsoftware||Wird nur für Windows 10-Desktop unterstützt. Microsoft empfiehlt Versionen von nicht mehr als fünf hinter der neuesten Version|
||Windows Defender-Antischadsoftware-Signatur auf dem neuesten Stand|Erforderlich||
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

3. Klicken Sie im Bereich **Sicherheit** auf **Bedingter Zugriff**.

4. Wählen Sie **Neue Richtlinie** aus.

5. Geben Sie einen Richtliniennamen ein, und wählen Sie dann die **Benutzer und Gruppen** aus, auf die Sie die Richtlinie anwenden möchten.

6. Klicken Sie auf **Cloud-Apps**.

7. Wählen **Sie apps auswählen**aus, und wählen Sie in der Liste **Cloud apps** die gewünschten Apps aus. Wählen Sie beispielsweise Office 365 Exchange Online aus. Wählen **Sie auswählen** und **Fertig**aus.

8. Um kompatible PCs, aber keine kompatiblen Telefone und Tablets zu benötigen, wählen Sie **Bedingungen** und **Geräteplattformen**aus. Wählen **Sie Geräteplattformen auswählen** aus, und wählen Sie **Windows** und **macOS**aus.

9. Wählen Sie im Abschnitt **Zugriffssteuerung** die Option **Erteilen** aus.

10. Wählen Sie **Zugriff gewähren**aus, und wählen Sie **Gerät müssen als konform gekennzeichnet sein**aus. Wählen Sie für mehrere Steuerelemente **die Option alle ausgewählten Steuerelemente anfordern**aus, und wählen Sie dann **auswählen**aus. 

11. Klicken Sie auf **Erstellen**.

Wenn Ihr Ziel darin besteht, kompatible PCs *und* Mobile Geräte zu benötigen, wählen Sie keine Plattformen aus. Dadurch wird die Kompatibilität für alle Geräte erzwungen. 

## <a name="require-compliant-pcs-and-mobile-devices"></a>Erfordern von kompatiblen PCs *und* mobilen Geräten

So erfordern Sie die Kompatibilität für alle Geräte:

1. Navigieren Sie zum [Azure-Portal](https://portal.azure.com), und melden Sie sich mit Ihren Anmeldeinformationen an. Nachdem Sie sich erfolgreich angemeldet haben, wird das Azure-Dashboard angezeigt.

2. Wählen Sie im linken Menü **Azure Active Directory** aus.

3. Klicken Sie im Bereich **Sicherheit** auf **Bedingter Zugriff**.

4. Wählen Sie **Neue Richtlinie** aus.

5. Geben Sie einen Richtliniennamen ein, und wählen Sie dann die **Benutzer und Gruppen** aus, auf die Sie die Richtlinie anwenden möchten.

6. Klicken Sie auf **Cloud-Apps**.

7. Wählen **Sie apps auswählen**aus, und wählen Sie in der Liste **Cloud apps** die gewünschten Apps aus. Wählen Sie beispielsweise Office 365 Exchange Online aus. Wählen **Sie auswählen** und **Fertig**aus.

8. Wählen Sie im Abschnitt **Zugriffssteuerung** die Option **Erteilen** aus.

9. Wählen Sie **Zugriff gewähren**aus, und wählen Sie **Gerät müssen als konform gekennzeichnet sein**aus. Wählen Sie für mehrere Steuerelemente **die Option alle ausgewählten Steuerelemente anfordern**aus, und wählen Sie dann **auswählen**aus. 

10. Klicken Sie auf **Erstellen**.

Wählen Sie beim Erstellen dieser Richtlinie keine Plattformen aus. Dadurch werden konforme Geräte erzwungen.


## <a name="next-steps"></a>Nächste Schritte

[Weitere Informationen zu Richtlinienempfehlungen zum Schutz von E-Mails](secure-email-recommended-policies.md)
