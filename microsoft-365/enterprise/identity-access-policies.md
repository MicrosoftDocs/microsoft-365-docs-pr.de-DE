---
title: Allgemeine Identitäts-und Gerätezugriffs Richtlinien-Microsoft 365 Enterprise | Microsoft-Dokumente
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
ms.openlocfilehash: 9912b05c07599c5ad0c0ed7fec91ae2572bd2ead
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32289325"
---
# <a name="common-identity-and-device-access-policies"></a>Common identity and device access policies (Allgemeine Identitäts- und Gerätezugriffsrichtlinien)
In diesem Artikel werden die allgemeinen empfohlenen Richtlinien für das Sichern des Zugriffs auf Cloud-Dienste beschrieben, einschließlich der lokalen Anwendungen, die mit Azure AD Application Proxy veröffentlicht werden. 

In diesem Leitfaden wird erläutert, wie Sie die empfohlenen Richtlinien in einer neu geschaffenen Umgebung bereitstellen. Wenn Sie diese Richtlinien in einer separaten Lab-Umgebung einrichten, können Sie die empfohlenen Richtlinien verstehen und bewerten, bevor Sie die Einführung in Ihre Vorproduktions-und Produktionsumgebungen bereitstellen. Ihre neu bereitgestellte Umgebung ist möglicherweise nur Cloud-oder Hybrid.  

## <a name="policy-set"></a>Richtliniensatz 

Das folgende Diagramm veranschaulicht die empfohlenen Richtlinien. Es wird angezeigt, für welche Schutzebene jede Richtlinie gilt und ob die Richtlinien für PCs oder Telefone und Tablets oder für beide Gerätekategorien gelten. Außerdem wird angegeben, wo diese Richtlinien konfiguriert sind.

![Allgemeine Richtlinien für das Konfigurieren des Identitäts-und Gerätezugriffs](../images/Identity_device_access_policies_byplan.png)


In diesem Artikel wird beschrieben, wie Sie diese Richtlinien konfigurieren. 

Die Verwendung der mehrstufigen Authentifizierung wird vor der Registrierung von Geräten in InTune empfohlen, um sicher zu stellen, dass sich das Gerät im Besitz des beabsichtigten Benutzers befindet. Sie müssen auch Geräte in InTune registrieren, bevor Sie Geräte Konformitätsrichtlinien erzwingen.

Damit Sie Zeit zum Ausführen dieser Aufgaben haben, wird empfohlen, die Basisrichtlinien in der in dieser Tabelle aufgeführten Reihenfolge zu implementieren. Die MFA-Richtlinien für den vertraulichen und hochgradig regulierten Schutz können jedoch jederzeit implementiert werden.


|Schutzebene|Richtlinien|Weitere Informationen|
|:---------------|:-------|:----------------|
|**Basisplan**|[MFA erfordern, wenn das Anmelde Risiko *Mittel* oder *hoch* ist](#require-mfa-based-on-sign-in-risk)| |
|        |[Blockieren von Clients, die die moderne Authentifizierung nicht unterstützen](#block-clients-that-dont-support-modern-authentication)|Clients, die keine moderne Authentifizierung verwenden, können Regeln für bedingten Zugriff umgehen, daher ist es wichtig, diese zu blockieren.|
|        |[Benutzer mit hohem Risiko müssen das Kennwort ändern](#high-risk-users-must-change-password)|Zwingt Benutzer dazu, Ihr Kennwort bei der Anmeldung zu ändern, wenn die Aktivität mit hohem Risiko für Ihr Konto erkannt wird.|
|        |[Definieren von App-Schutzrichtlinien](#define-app-protection-policies)|Eine Richtlinie pro Plattform (iOS, Android, Windows).|
|        |[Genehmigte apps anfordern](#require-approved-apps)|Erzwingt den Schutz mobiler Apps für Telefone und Tablets|
|        |[Definieren von Geräte Konformitätsrichtlinien](#define-device-compliance-policies)|Eine Richtlinie für jede Plattform|
|        |[Kompatible PCs erforderlich](#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Erzwingung der InTune-Verwaltung von PCs|
|**Vertraulich**|[MFA erfordern, wenn das Anmelde Risiko *niedrig*, *Mittel* oder *hoch* ist](#require-mfa-based-on-sign-in-risk)| |
|         |[Erfordern kompatibler PCs *und* mobiler Geräte](#require-compliant-pcs-and-mobile-devices)|Erzwingung der InTune-Verwaltung für PCs und Telefon/Tablets|
|**Streng geregelt**|[*Immer* MFA erforderlich](#require-mfa-based-on-sign-in-risk)|
| | |

## <a name="assigning-policies-to-users"></a>Zuweisen von Richtlinien zu Benutzern
Identifizieren Sie vor dem Konfigurieren von Richtlinien die Azure AD-Gruppen, die Sie für jede Schutzebene verwenden. In der Regel gilt der Basisschutz für alle in der Organisation. Für einen Benutzer, der sowohl für die Baseline als auch für den vertraulichen Schutz vorgesehen ist, werden alle Basisrichtlinien sowie die vertraulichen Richtlinien angewendet. Der Schutz ist kumulativ, und die restriktivste Richtlinie wird erzwungen. 

Es wird empfohlen, eine Azure AD-Gruppe für den bedingten Zugriff zu erstellen. Fügen Sie diese Gruppe allen bedingten Zugriffsregeln unter "ausschließen" hinzu. Dadurch erhalten Sie eine Methode zum Zugriff auf einen Benutzer während der Behandlung von Zugriffsproblemen. Dies wird nur als temporäre Lösung empfohlen. Überwachen Sie diese Gruppe auf Änderungen, und stellen Sie sicher, dass die Ausschlussgruppe nur wie beabsichtigt verwendet wird. 

Das folgende Diagramm enthält ein Beispiel für Benutzerzuweisungen und-Ausschlüsse.

![Beispiel für Benutzerzuweisung und Ausschlüsse für MFA-Regeln](../images/identity-access-policies-assignment.png)

In der Abbildung wird dem "Top Secret Project X-Team" eine Richtlinie für den bedingten Zugriff zugewiesen, die *immer*MFA erfordert. Bei der Anwendung höherer Schutzgrade für Benutzer sinnvoll sein. Mitglieder dieses Projektteams müssen bei jeder Anmeldung zwei Arten von Authentifizierung bereitstellen, selbst wenn Sie nicht hochregulierte Inhalte anzeigen.  

Alle Azure AD-Gruppen, die als Teil dieser Empfehlungen erstellt wurden, müssen als Office 365-Gruppen erstellt werden. Dies ist insbesondere für die Bereitstellung von AIP (Azure Information Protection) beim Schützen von Dokumenten in SharePoint Online wichtig.

![Bildschirmaufnahme für die Erstellung von Office 365-Gruppen](../images/identity-device-AAD-groups.png)


## <a name="require-mfa-based-on-sign-in-risk"></a>MFA basiert auf dem Anmelde Risiko erfordern
Bevor Sie MFA benötigen, müssen Sie zunächst eine Identitätsschutz-MFA-Registrierungsrichtlinie verwenden, um Benutzer für MFA zu registrieren. Nachdem Benutzer registriert sind, können Sie MFA für die Anmeldung erzwingen. Zu den [voraus](identity-access-prerequisites.md) setzungen gehört die Registrierung aller Benutzer mit MFA.

So erstellen Sie eine neue bedingte Zugriffsrichtlinie: 

1. Navigieren Sie zum [Azure-Portal](https://portal.azure.com), und melden Sie sich mit Ihren Anmeldeinformationen an. Nachdem Sie sich erfolgreich angemeldet haben, wird das Azure-Dashboard angezeigt.

2. Wählen Sie im linken Menü **Azure Active Directory** aus.

3. Klicken Sie im Bereich **Sicherheit** auf **Bedingter Zugriff**.

4. Wählen Sie **Neue Richtlinie** aus.

![Grundlegende Richtlinie für bedingten Zugriff](./media/secure-email/CA-EXO-policy-1.png)

 In der folgenden Tabelle werden die Richtlinieneinstellungen für den bedingten Zugriff beschrieben, die für diese Richtlinie implementiert werden sollen.

**Aufgaben**

|Typ|Eigenschaften|Werte|Hinweise|
|:---|:---------|:-----|:----|
|Benutzer und Gruppen|Einschließen|Wählen Sie Benutzer und Gruppen aus: Wählen Sie eine spezifische Sicherheitsgruppe aus, die Zielbenutzer enthält.|Beginnen Sie mit der Sicherheitsgruppe einschließlich Pilotbenutzer|
||Ausschließen|Ausnahmesicherheitsgruppe, Dienstkonten (App-Identitäten)|Geänderte Mitgliedschaft bei Bedarf auf temporärer Basis|
|Cloud-Apps|Einschließen|Wählen Sie die Apps aus, auf die diese Regel angewendet werden soll. Wählen Sie beispielsweise Office 365 Exchange Online aus.||
|Bedingungen|Konfigurierte|Ja|Konfigurieren Sie speziell für Ihre Umgebung und Anforderungen.|
|Anmelderisiko|Risikostufe||Lesen Sie die Anweisungen in der folgenden Tabelle.|

**Anmelderisiko**

Wenden Sie die Einstellungen basierend auf der Schutzebene an, die Sie verwenden möchten.

|Eigenschaft|Schutzebene|Werte|Hinweise|
|:---|:---------|:-----|:----|
|Risikostufe|Baseline|Hoch, Mmittel|Aktivieren Sie beide|
| |Vertraulich|Hoch, Mittel, niedrig|Alle drei aktivieren|
| |Streng geregelt| |Alle Optionen deaktiviert lassen, um MFA immer zu erzwingen|

**Zugriffssteuerung**

|Typ|Eigenschaften|Werte|Hinweise|
|:---|:---------|:-----|:----|
|Gewähren|Gewähren von Zugriff|True|Ausgewählt|
||MFA erforderlich|True|Check|
||Gerät als kompatibel markieren|False||
||Erfordert ein hybrides Azure AD-verbundenes Gerät|False||
||Genehmigte Client-App erforderlich|False||
||Alle ausgewählten Steuerelemente erforderlich|True|Ausgewählt|

> [!NOTE]
> Stellen Sie sicher, dass Sie diese Richtlinie aktivieren, indem Sie **auf**auswählen. Sie sollten auch das Tool [What if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) verwenden, um die Richtlinie zu testen.



## <a name="block-clients-that-dont-support-modern-authentication"></a>Blockieren von Clients, die die moderne Authentifizierung nicht unterstützen
1. Navigieren Sie zum [Azure-Portal](https://portal.azure.com), und melden Sie sich mit Ihren Anmeldeinformationen an. Nachdem Sie sich erfolgreich angemeldet haben, wird das Azure-Dashboard angezeigt.

2. Wählen Sie im linken Menü **Azure Active Directory** aus.

3. Klicken Sie im Bereich **Sicherheit** auf **Bedingter Zugriff**.

4. Wählen Sie **Neue Richtlinie** aus.

In der folgenden Tabelle werden die Richtlinieneinstellungen für den bedingten Zugriff beschrieben, die für diese Richtlinie implementiert werden sollen.

**Aufgaben**

|Typ|Eigenschaften|Werte|Hinweise|
|:---|:---------|:-----|:----|
|Benutzer und Gruppen|Include|Wählen Sie Benutzer und Gruppen aus: Wählen Sie eine spezifische Sicherheitsgruppe aus, die Zielbenutzer enthält.|Beginnen Sie mit der Sicherheitsgruppe einschließlich Pilotbenutzer|
||Ausschließen|Ausnahmesicherheitsgruppe, Dienstkonten (App-Identitäten)|Mitgliedschaft, die auf vorübergehender, bedarfsmäßiger Basis geändert wird|
|Cloud-Apps|Include|Wählen Sie die Apps aus, auf die diese Regel angewendet werden soll. Wählen Sie beispielsweise Office 365 Exchange Online aus.||
|Bedingungen|Konfigurierte|Ja|Konfigurieren von Client-apps|
|Client-apps|Konfigurierte|Ja|Mobile Apps und Desktop Clients, andere Clients (beide auswählen)|

**Zugriffssteuerung**

|Typ|Eigenschaften|Werte|Hinweise|
|:---|:---------|:-----|:----|
|Gewähren|Zugriff blockieren|True|Ausgewählt|
||MFA erforderlich|False||
||Gerät als kompatibel markieren|False||
||Erfordert ein hybrides Azure AD-verbundenes Gerät|False||
||Genehmigte Client-App erforderlich|False||
||Alle ausgewählten Steuerelemente erforderlich|True|Ausgewählt|

> [!NOTE]
> Stellen Sie sicher, dass Sie diese Richtlinie aktivieren, indem Sie **auf**auswählen. Sie sollten auch das Tool [What if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) verwenden, um die Richtlinie zu testen.



## <a name="high-risk-users-must-change-password"></a>Benutzer mit hohem Risiko müssen das Kennwort ändern
Um sicherzustellen, dass alle gefährdeten Benutzerkonten mit hohem Risiko gezwungen sind, beim Anmelden eine Kennwortänderung durchzuführen, müssen Sie die folgende Richtlinie anwenden.

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
|      | Access     | Zugriff zulassen            | True  |
|      | Access     | Kennwortänderung erforderlich | True  |

**Review:** nicht zutreffend

> [!NOTE]
> Stellen Sie sicher, dass Sie diese Richtlinie aktivieren, indem Sie **auf**auswählen. Erwägen Sie auch, das Tool [What if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) zum Testen der Richtlinie zu verwenden.

## <a name="define-app-protection-policies"></a>Definieren von App-Schutzrichtlinien
App-Schutzrichtlinien definieren, welche apps zulässig sind und welche Aktionen Sie mit den Daten Ihrer Organisation ausführen können. Erstellen Sie InTune-App-Schutzrichtlinien aus dem Azure-Portal. 

Erstellen Sie eine Richtlinie für jede Plattform:
- iOS
- Android
- Windows 10

Um eine neue APP-Schutzrichtlinie zu erstellen, melden Sie sich mit Ihren Administratoranmeldeinformationen beim Microsoft Azure-Portal an, und navigieren Sie dann zu **>-App-Schutzrichtlinien für Mobile Apps**. Wählen Sie **Richtlinie hinzufügen**aus.

Es gibt jedoch geringfügige Unterschiede in den Richtlinienoptionen für App-Schutz zwischen iOS und Android. Die folgende Richtlinie gilt speziell für Android. Verwenden Sie dies als Leitfaden für Ihre anderen Richtlinien.

Die empfohlene Liste von apps umfasst Folgendes:
- PowerPoint
- Excel
- Word
- Microsoft Teams
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
||Speicherdienste zum Speichern von Unternehmensdaten auswählen|OneDrive for Business, SharePoint||
||Ausschneiden, Kopieren und Einfügen mit anderen Apps einschränken|Richtlinien verwaltete apps mit Paste in||
||Anzeige von Webinhalten auf den Managed Browser beschränken|Nein||
||App-Daten verschlüsseln|Ja|Wählen Sie bei iOS diese Option aus: Wenn das Gerät gesperrt ist.|
||Deaktivieren der APP-Verschlüsselung bei aktiviertem Gerät|Ja|Deaktivieren Sie diese Einstellung, um doppelte Verschlüsselung zu vermeiden|
||Kontaktsynchronisierung deaktivieren|Nein||
||Drucken deaktivieren|Nein||
|Zugriff|PIN für Zugriff anfordern|Ja||
||Typ auswählen|Numerisch||
||Einfache PIN zulassen|Nein||
||PIN-Länge|6||
||Fingerabdruck anstelle von PIN zulassen|Ja||
||App-PIN deaktivieren, wenn die Geräte-PIN verwaltet wird|Ja||
||Unternehmensanmeldeinformationen für Zugriff erforderlich|Nein||
||Erneutes Überprüfen der Zugriffsanforderung nach (Minuten)|30||
||Bildschirmaufnahme und Android-Assistenten blockieren|Nein|Bei iOS ist diese Option nicht verfügbar.|
|Sicherheitsanforderungen für die Anmeldung|Max. PIN-Versuche|5|PIN zurücksetzen|
||Offline-Toleranzperiode|720|Zugriff blockieren|
||Offline-Intervall (in Tagen), bevor App-Daten zurückgesetzt werden|90|Daten löschen|
||Jailbroken/Rooted-Geräte| |Daten löschen|

Wenn Sie fertig sind, wählen Sie "erstellen" aus. Wiederholen Sie die obigen Schritte und ersetzen Sie die ausgewählte Plattform (Dropdown) durch iOS. Dadurch werden zwei App-Richtlinien erstellt, sodass Sie nach der Erstellung der Richtlinie Gruppen der Richtlinie zuweisen und bereitstellen können.

Informationen zum Bearbeiten der Richtlinien und zum Zuweisen dieser Richtlinien zu Benutzern finden Sie unter [Erstellen und Zuweisen von App-Schutzrichtlinien](https://docs.microsoft.com/intune/app-protection-policies). 

## <a name="require-approved-apps"></a>Genehmigte apps anfordern
So müssen Sie genehmigte apps anfordern:

1. Navigieren Sie zum [Azure-Portal](https://portal.azure.com), und melden Sie sich mit Ihren Anmeldeinformationen an. Nachdem Sie sich erfolgreich angemeldet haben, wird das Azure-Dashboard angezeigt.

2. Wählen Sie im linken Menü **Azure Active Directory** aus.

3. Klicken Sie im Bereich **Sicherheit** auf **Bedingter Zugriff**.

4. Wählen Sie **Neue Richtlinie** aus.

5. Geben Sie einen Richtliniennamen ein, und wählen Sie dann die **Benutzer und Gruppen** aus, auf die Sie die Richtlinie anwenden möchten.

6. Klicken Sie auf **Cloud-Apps**.

7. Wählen **Sie apps auswählen**aus, und wählen Sie in der Liste **Cloud apps** die gewünschten Apps aus. Wählen Sie beispielsweise Office 365 Exchange Online aus. Wählen **Sie auswählen** und **Fertig**.

8. Wählen Sie im Abschnitt **Zugriffssteuerung** die Option **Erteilen** aus.

9. Wählen Sie **Zugriff gewähren**aus, wählen Sie **genehmigte Client-App anfordern**aus. Wählen Sie für mehrere Steuerelemente **die Option ausgewählte Steuerelemente anfordern**aus, und wählen Sie dann **auswählen**aus. 

10. Klicken Sie auf **Erstellen**.

## <a name="define-device-compliance-policies"></a>Definieren von Geräte Konformitätsrichtlinien

Geräte Konformitätsrichtlinien definieren die Anforderungen, die von Geräten eingehaltenwerden müssen, damit Sie als kompatibel gekennzeichnet werden. Erstellen Sie InTune-Geräte Konformitätsrichtlinien innerhalb des Azure-Portals. 

Erstellen Sie eine Richtlinie für jede Plattform:
- Android
- Android Enterprise
- iOS
- macOS
- Diese Einstellung ist auf den folgenden Gerätetypen verfügbar:
- Windows 8,1 und höher
- Windows 10 und höher

Um Geräte Konformitätsrichtlinien zu erstellen, melden Sie sich mit Ihren Administratoranmeldeinformationen beim Microsoft Azure-Portal an, und navigieren Sie dann zu **InTune _GT_ Device Compliance**. Wählen Sie **Richtlinie erstellen**aus.

Die folgenden Einstellungen sind für Windows 10 empfehlenswert.

**Geräte Integrität: Evaluierungsregeln für den Windows-Integritäts zertifizierungsDienst**

|Eigenschaften|Werte|Hinweise|
|:---------|:-----|:----|
|BitLocker erforderlich|Erforderlich||
|Für das Gerät muss Secure Boot aktiviert sein|Erforderlich||
|Codeintegrität erforderlich|Erforderlich||


**Geräteeigenschaften**

|Typ|Eigenschaften|Werte|Hinweise|
|:---|:---------|:-----|:----|
|Betriebssystemversion|Alle|Nicht konfiguriert||

Damit die oben aufgeführten Richtlinien als bereitgestellt betrachtet werden, müssen sie für bestimmte Benutzergruppen gelten. Sie können dies tun, indem Sie die Richtlinie (bei speichern) oder höher erstellen, indem Sie im Abschnitt **Richtlinie** die Option **Bereitstellung verwalten** auswählen (Ebene als Add).

**Systemsicherheit**

|Typ|Eigenschaften|Werte|Hinweise|
|:---|:---------|:-----|:----|
|Kennwort|Kennwort zum Entsperren mobiler Geräte anfordern|Erforderlich||
||Einfache Kennwörter|Block||
||Kennworttyp|Geräte Standard||
||Minimale Kennwortlänge|6||
||Maximal Minuten der Inaktivität, bevor Kennwort erforderlich ist|15|Diese Einstellung wird für Android-Versionen 4,0 und höher oder KNOX 4,0 und höher unterstützt. Für iOS-Geräte wird es für iOS 8,0 und höher unterstützt.|
||Kennwortablauf (Tage)|41||
||Anzahl der vorherigen Kennwörter zur Vermeidung der Wiederverwendung|5||
||Kennwort anfordern, wenn das Gerät aus dem Leerlauf wechselt (Mobil und holographisch)|Erforderlich|Verfügbar für Windows 10 und höher|
|Verschlüsselung|Verschlüsselung der Datenspeicherung auf dem Gerät|Erforderlich||
|Gerätesicherheit|Firewall|Erforderlich||
||Antivirus|Erforderlich||
||AntiSpyware|Erforderlich|Für diese Einstellung ist eine mit Windows Security Center registrierte Anti-Spyware-Lösung erforderlich.|
|Defender|Windows Defender-Antischadsoftware|Erforderlich||
||Mindestversion von Windows Defender Antischadsoftware||Wird nur für Windows 10 Desktop unterstützt. Microsoft empfiehlt Versionen nicht mehr als fünf hinter der neuesten Version|
||Windows Defender-Antischadsoftware-Signatur auf dem neuesten Stand|Erforderlich||
||Echtzeitschutz|Erforderlich|Nur für Windows 10 Desktop unterstützt|

**Windows Defender ATP**

|Typ|Eigenschaften|Werte|Hinweise|
|:---|:---------|:-----|:----|
|Windows Defender Advanced Threat Protection-Regeln|Das Gerät muss sich auf oder unter dem Computer-Risikofaktor befinden|Mittel||

## <a name="require-compliant-pcs-but-not-compliant-phones-and-tablets"></a>Erforderliche kompatible PCs (aber nicht kompatible Telefone und Tablets)
Bevor Sie eine Richtlinie für die Einhaltung kompatibler PCs hinzufügen, müssen Sie die Geräte für die Verwaltung in InTune registrieren. Die Verwendung der mehrstufigen Authentifizierung wird vor der Registrierung von Geräten in InTune empfohlen, um sicher zu stellen, dass sich das Gerät im Besitz des beabsichtigten Benutzers befindet. 

So benötigen Sie kompatible PCs:

1. Navigieren Sie zum [Azure-Portal](https://portal.azure.com), und melden Sie sich mit Ihren Anmeldeinformationen an. Nachdem Sie sich erfolgreich angemeldet haben, wird das Azure-Dashboard angezeigt.

2. Wählen Sie im linken Menü **Azure Active Directory** aus.

3. Klicken Sie im Bereich **Sicherheit** auf **Bedingter Zugriff**.

4. Wählen Sie **Neue Richtlinie** aus.

5. Geben Sie einen Richtliniennamen ein, und wählen Sie dann die **Benutzer und Gruppen** aus, auf die Sie die Richtlinie anwenden möchten.

6. Klicken Sie auf **Cloud-Apps**.

7. Wählen **Sie apps auswählen**aus, und wählen Sie in der Liste **Cloud apps** die gewünschten Apps aus. Wählen Sie beispielsweise Office 365 Exchange Online aus. Wählen **Sie auswählen** und **Fertig**.

8. Wählen Sie **Bedingungen** und **gerätePlattformen**aus, um kompatible PCs, aber nicht kompatible Telefone und Tablets, zu verlangen. Wählen **Sie Geräteplattformen** auswählen aus, und wählen Sie **Windows** und **macOS**aus.

9. Wählen Sie im Abschnitt **Zugriffssteuerung** die Option **Erteilen** aus.

10. Wählen Sie **Zugriff gewähren**aus, und wählen Sie **Gerät als kompatibel kennzeichnen**aus. Aktivieren Sie für mehrere Steuerelemente **alle ausgewählten Steuerelemente anfordern**, und wählen Sie dann **auswählen**aus. 

11. Klicken Sie auf **Erstellen**.

Wenn Ihr Ziel darin besteht, kompatible PCs *und* Mobile Geräte zu verlangen, wählen Sie keine Plattformen aus. Dadurch wird die Kompatibilität für alle Geräte erzwungen. 

## <a name="require-compliant-pcs-and-mobile-devices"></a>Erfordern kompatibler PCs *und* mobiler Geräte

So müssen Sie für alle Geräte die Kompatibilität erzwingen:

1. Navigieren Sie zum [Azure-Portal](https://portal.azure.com), und melden Sie sich mit Ihren Anmeldeinformationen an. Nachdem Sie sich erfolgreich angemeldet haben, wird das Azure-Dashboard angezeigt.

2. Wählen Sie im linken Menü **Azure Active Directory** aus.

3. Klicken Sie im Bereich **Sicherheit** auf **Bedingter Zugriff**.

4. Wählen Sie **Neue Richtlinie** aus.

5. Geben Sie einen Richtliniennamen ein, und wählen Sie dann die **Benutzer und Gruppen** aus, auf die Sie die Richtlinie anwenden möchten.

6. Klicken Sie auf **Cloud-Apps**.

7. Wählen **Sie apps auswählen**aus, und wählen Sie in der Liste **Cloud apps** die gewünschten Apps aus. Wählen Sie beispielsweise Office 365 Exchange Online aus. Wählen **Sie auswählen** und **Fertig**.

8. Wählen Sie im Abschnitt **Zugriffssteuerung** die Option **Erteilen** aus.

9. Wählen Sie **Zugriff gewähren**aus, und wählen Sie **Gerät als kompatibel kennzeichnen**aus. Aktivieren Sie für mehrere Steuerelemente **alle ausgewählten Steuerelemente anfordern**, und wählen Sie dann **auswählen**aus. 

10. Klicken Sie auf **Erstellen**.

Wählen Sie beim Erstellen dieser Richtlinie keine Plattformen aus. Dadurch werden kompatible Geräte erzwungen.


## <a name="next-steps"></a>Nächste Schritte

[Weitere Informationen zu Richtlinienempfehlungen zum Schutz von E-Mails](secure-email-recommended-policies.md)
