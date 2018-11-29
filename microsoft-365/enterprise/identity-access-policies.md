---
title: Allgemeine Identität und Gerät Zugriffsrichtlinien - Microsoft 365 Enterprise | Microsoft-Dokumente
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
ms.openlocfilehash: 72a957222ed3bba449e1576873bfc87a614c075b
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868194"
---
# <a name="common-identity-and-device-access-policies"></a>Allgemeine Identitäts- und Gerätezugriffsrichtlinien
Dieser Artikel beschreibt die allgemeine empfohlene Richtlinien für den sicheren Zugriff, um cloud-Dienste, einschließlich lokalen Applikationen mit Azure AD-Anwendungsproxy veröffentlicht. 

In dieser Anleitung wird erläutert, wie Sie die empfohlenen Richtlinien in einer neu bereitgestellten Umgebung bereitstellen. Das Einrichten dieser Richtlinien in einer eigenen Laborumgebung ermöglicht Ihnen, die empfohlenen Richtlinien vor dem Bereitstellen des Rollouts in Ihren Präproduktions- und Produktionsumgebungen zu verstehen und auszuwerten. Die neu bereitgestellte Umgebung kann eine Nur-Cloud- oder eine Hybridumgebung sein.  

## <a name="policy-set"></a>Richtlinie festlegen 

Das folgende Diagramm veranschaulicht den empfohlenen Satz von Richtlinien. Es zeigt, welche Tier Schutzebenen jede Richtlinie gilt für und gibt an, ob die Richtlinien gelten für PCs, Telefone und Tablets oder beiden Kategorien von Geräten. Es gibt an, wobei diese Richtlinien konfiguriert sind.

![Allgemeine Richtlinien zum Konfigurieren des Zugriffs von Identität und Geräte](../images/Identity_device_access_policies_byplan.png)


Der Rest dieses Artikels wird beschrieben, wie diese Richtlinien konfigurieren. 

Verwenden die mehrstufige Authentifizierung wird empfohlen, vor der Geräte in Intune registrieren Assurance, die das Gerät im Besitz des gewünschten Benutzers ist. Und Sie müssen Geräte in Intune registrieren, bevor Kompatibilitätsrichtlinien Gerät erzwungen.

So übergeben Sie die Zeit für diese Aufgaben, es wird empfohlen, die in dieser Tabelle aufgeführten Implementieren der Baseline-Richtlinien in der Reihenfolge. Mehrstufiger Authentifizierung das Richtlinien zum Schutz von vertraulichen und hochgradig regulierten können jedoch jederzeit implementiert werden.


|Schutzebene|Policies|Weitere Informationen|
|:---------------|:-------|:----------------|
|**Baseline**|[Erfordern Sie mehrstufiger Authentifizierung das, bei der Anmeldung Risiko *Mittel* oder *Hoch* ist](#require-mfa-based-on-sign-in-risk)| |
|        |[Blockierung von Clients, die moderne Authentifizierung nicht unterstützen](#block-clients-that-dont-support-modern-authentication)|Clients, die nicht modernen Authentifizierung verwenden können bedingte Zugriffsregeln, umgehen, daher es wichtig ist, diese zu blockieren.|
|        |[Hoch riskante Benutzer müssen Kennwort ändern.](#high-risk-users-must-change-password)|Erzwingt, dass Benutzer ihr Kennwort ändern, bei der Anmeldung Wenn hoch riskante Aktivität für ihr Konto erkannt wird.|
|        |[Definieren von Richtlinien für die app-Schutz](#define-app-protection-policies)|Eine Richtlinie pro Plattform (iOS, Android, Windows).|
|        |[Genehmigte apps erfordern](#require-approved-apps)|Erzwingt die mobile app Schutz für Mobiltelefone und tablets|
|        |[Gerät Compliance-Richtlinien definieren](#define-device-compliance-policies)|Eine Richtlinie für jede Plattform.|
|        |[Kompatible PCs erfordern](#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Erzwingt Intune Verwaltung von PCs|
|**Vertraulich**|[Erfordern Sie mehrstufiger Authentifizierung das, bei der Anmeldung Risiko *Niedrig*, *Mittel* oder *Hoch* ist](#require-mfa-based-on-sign-in-risk)| |
|         |[Erfordern Sie kompatible PCs *und* mobile Geräten](#require-compliant-pcs-and-mobile-devices)|Erzwingt Intune Management für PCs und Telefon-Tablets.|
|**Streng geregelt**|[*Immer* erfordern mehrstufiger Authentifizierung das](#require-mfa-based-on-sign-in-risk)|
| | |

## <a name="assigning-policies-to-users"></a>Zuweisen von Richtlinien für Benutzer
Identifizieren Sie vor dem Konfigurieren von Richtlinien, die Azure AD-Gruppen, die Sie für die einzelnen Ebenen des Schutzes verwenden. In der Regel gilt Baseline Schutz für alle Benutzer in der Organisation. Ein Benutzer, der für geplante und vertrauliche Protection enthalten ist müssen alle angewendeten geplante Richtlinien plus die vertraulichen Richtlinien. Schutz ist kumulativ und die restriktivste Richtlinie erzwungen wird. 

Zum Erstellen einer Azure Active Directory-Gruppe für bedingten Zugriff Ausschluss wird eine empfohlen. Um alle Zugriffsregeln zur bedingten unter "Ausschließen" dieser Gruppe hinzuzufügen. Dadurch können Sie eine Methode, um den Zugriff für einen Benutzer bereitstellen, während Sie Access-Probleme zu beheben. Dies wird als eine Zwischenlösung nur empfohlen. Überwachen Sie diese Gruppe aus, damit die Änderungen, und achten Sie darauf, dass die Ausschlussgruppe nur wie vorgesehen verwendet wird. 

Die folgende Abbildung enthält ein Beispiel von Benutzerrechten und Ausschlüsse.

![Beispiel von Benutzerrechten und Ausschlüssen für mehrstufiger Authentifizierung das Regeln](../images/identity-access-policies-assignment.png)

In der Abbildung ist das "oberen geheimen X Projektteam" eine bedingte Zugriffsrichtlinie zugewiesen, mehrstufiger Authentifizierung das *immer*müssen. Werden Sie zielgerichtete beim Anwenden von höherer Schutz auf Benutzer. Mitglieder dieser Projektteams müssen Sie zwei Arten der Authentifizierung jedes Mal, wenn sie Anmelden bereitstellen, auch wenn sie nicht hochgradig regulierten Inhalte anzeigen.  

 Alle Azure AD-Gruppen, die als Teil des diesen Empfehlungen erstellte müssen als Office 365-Gruppen erstellt werden. Dies ist insbesondere wichtig für die Bereitstellung von Azure Informationen Schutz (per), bei der Sicherung von Dokumenten in SharePoint Online.

![Zum Erstellen von Gruppen für Office 365-Bildschirmaufnahme](../images/identity-device-AAD-groups.png)




## <a name="require-mfa-based-on-sign-in-risk"></a>Mehrstufiger Authentifizierung das basierend auf Risiko-Anmeldung erforderlich
Mehrstufiger Authentifizierung das werden müssen, zunächst mit dem eine Identität Protection mehrstufiger Authentifizierung das Registrierung Richtlinie Benutzer für mehrstufiger Authentifizierung das registrieren. Nachdem der Benutzer registriert sind, können Sie mehrstufiger Authentifizierung das für die Anmeldung erzwingen. Die [erforderliche Arbeit](identity-access-prerequisites.md) enthält, allen Benutzern mit mehrstufiger Authentifizierung das registrieren.

So erstellen Sie eine neue bedingte Zugriffsrichtlinie: 

1. Navigieren Sie zum [Azure-Portal](https://portal.azure.com), und melden Sie sich mit Ihren Anmeldeinformationen an. Sobald Sie erfolgreich angemeldet sind, wird das Azure-Dashboard angezeigt.

2. Wählen Sie im linken Menü **Azure Active Directory** aus.

3. Klicken Sie im Bereich **Sicherheit** auf **Bedingter Zugriff**.

4. Wählen Sie **neue Richtlinie** aus, wie im folgenden Screenshot dargestellt:

![Grundlegende Richtlinie für bedingten Zugriff](./media/secure-email/CA-EXO-policy-1.png)

 In den folgenden Tabellen werden die bedingten Zugriff Richtlinieneinstellungen für diese Richtlinie implementieren beschrieben.

**Zuweisungen**

|Typ|Eigenschaften|Werte|Hinweise|
|:---|:---------|:-----|:----|
|Benutzer und Gruppen|Einschließen|Wählen Sie Benutzer und Gruppen aus: Wählen Sie eine spezifische Sicherheitsgruppe aus, die Zielbenutzer enthält.|Beginnen Sie mit der Sicherheitsgruppe, die Pilotbenutzer enthält.|
||Ausschließen|Ausnahmesicherheitsgruppe, Dienstkonten (App-Identitäten)|Mitgliedschaft, die auf vorübergehender, bedarfsmäßiger Basis geändert wird|
|Cloud-Apps|Einschließen|Wählen Sie die apps, die diese Regel angewendet werden soll. Wählen Sie zum Beispiel auf Office 365 Exchange Online||
|Bedingungen|Konfigurierte|Ja|Konfigurieren Sie speziell für Ihre Umgebung und Anforderungen.|
|Anmelderisiko|Risikostufe||Finden Sie unter der Anleitung in der folgenden Tabelle|

**Anmelderisiko**

Wenden Sie die Einstellungen, die basierend auf der Mail-Schutzstufe, den Sie verwenden möchten.

|Eigenschaft|Schutzebene|Werte|Hinweise|
|:---|:---------|:-----|:----|
|Risikostufe|Baseline|Hoch, Mmittel|Aktivieren Sie beide|
| |Vertraulich|Hoch, Mittel, Niedrig|Alle drei aktivieren|
| |Streng geregelt| |Lassen Sie alle Optionen deaktiviert, um immer mehrstufiger Authentifizierung das erzwingen|

**Zugriffssteuerung**

|Typ|Eigenschaften|Werte|Hinweise|
|:---|:---------|:-----|:----|
|Gewähren|Gewähren von Zugriff|True|Ausgewählt|
||MFA erforderlich|True|Check|
||Müssen Sie Gerät als kompatibel markiert werden|False||
||Erfordern Sie verknüpften Hybrid Azure AD-Gerät|False||
||Genehmigte Client-app erforderlich|False||
||Alle ausgewählten Steuerelemente erforderlich|True|Ausgewählt|

> [!NOTE]
> Achten Sie darauf, dass Sie diese Richtlinie aktivieren, indem Sie **auf**. Berücksichtigen Sie auch mit dem Tool [Was passiert, wenn](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) die Richtlinie testen



## <a name="block-clients-that-dont-support-modern-authentication"></a>Blockierung von Clients, die moderne Authentifizierung nicht unterstützen
1. Navigieren Sie zum [Azure-Portal](https://portal.azure.com), und melden Sie sich mit Ihren Anmeldeinformationen an. Sobald Sie erfolgreich angemeldet sind, wird das Azure-Dashboard angezeigt.

2. Wählen Sie im linken Menü **Azure Active Directory** aus.

3. Klicken Sie im Bereich **Sicherheit** auf **Bedingter Zugriff**.

4. Wählen Sie **Neue Richtlinie** aus.

In den folgenden Tabellen werden die bedingten Zugriff Richtlinieneinstellungen für diese Richtlinie implementieren beschrieben.

**Zuweisungen**

|Typ|Eigenschaften|Werte|Hinweise|
|:---|:---------|:-----|:----|
|Benutzer und Gruppen|Einschließen|Wählen Sie Benutzer und Gruppen aus: Wählen Sie eine spezifische Sicherheitsgruppe aus, die Zielbenutzer enthält.|Beginnen Sie mit der Sicherheitsgruppe, die Pilotbenutzer enthält.|
||Ausschließen|Ausnahmesicherheitsgruppe, Dienstkonten (App-Identitäten)|Mitgliedschaft, die auf vorübergehender, bedarfsmäßiger Basis geändert wird|
|Cloud-Apps|Einschließen|Wählen Sie die apps, die diese Regel angewendet werden soll. Wählen Sie zum Beispiel auf Office 365 Exchange Online||
|Bedingungen|Konfigurierte|Ja|Konfigurieren von Client-apps|
|Client-apps|Konfigurierte|Ja|Mobile apps und Desktopclients, andere Clients (Wählen Sie beide)|

**Zugriffssteuerung**

|Typ|Eigenschaften|Werte|Hinweise|
|:---|:---------|:-----|:----|
|Gewähren|Zugriff blockieren|True|Ausgewählt|
||MFA erforderlich|False||
||Müssen Sie Gerät als kompatibel markiert werden|False||
||Erfordern Sie verknüpften Hybrid Azure AD-Gerät|False||
||Genehmigte Client-app erforderlich|False||
||Alle ausgewählten Steuerelemente erforderlich|True|Ausgewählt|

> [!NOTE]
> Achten Sie darauf, dass Sie diese Richtlinie aktivieren, indem Sie **auf**. Berücksichtigen Sie auch mit dem Tool [Was passiert, wenn](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) die Richtlinie testen



## <a name="high-risk-users-must-change-password"></a>Hoch riskante Benutzer müssen Kennwort ändern.
Stellen Sie sicher, dass alle Benutzer mit hohem Risiko für gefährdete Konten eine Kennwortänderung bei der Anmeldung durchführen müssen, indem Sie die folgende Richtlinie anwenden.

Melden Sie sich bei der [Microsoft Azure-Portal (http://portal.azure.com) ](http://portal.azure.com/) mit Ihren Administratoranmeldeinformationen, und navigieren Sie zu **Azure AD-Schutz > Risiko Benutzerrichtlinie**.

**Zuweisungen**

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

**Überprüfen:** nicht zutreffend

> [!NOTE]
> Achten Sie darauf, dass Sie diese Richtlinie aktivieren, indem Sie **auf**. Berücksichtigen Sie auch mit dem Tool [Was passiert, wenn](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) die Richtlinie testen

## <a name="define-app-protection-policies"></a>Definieren von Richtlinien für die app-Schutz
App-Richtlinien definieren, welche apps zulässig sind, und die Aktionen, die sie mit Ihrer Organisationsdaten ausführen können. Erstellen Sie Intune app Protection-Richtlinien aus der Azure-Portal. 

Erstellen Sie eine Richtlinie für jede Plattform:
- iOS
- Android
- Windows 10

Um eine neue app-Schutz-Richtlinie zu erstellen, melden Sie sich an das Microsoft Azure-Portal mit Ihren Anmeldeinformationen verwalten, und navigieren Sie zu **mobiler apps > Richtlinien für die App Protection**. Klicken Sie auf **eine Richtlinie hinzufügen**.

Es gibt leichte Unterschiede in der app-Schutz Richtlinienoptionen zwischen iOS und Android. Die unter Richtlinie bezieht sich speziell auf Android. Verwenden Sie dies als Leitfaden für die anderen Richtlinien.

Die empfohlene Liste apps umfasst Folgendes:
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
||Ausschneiden, Kopieren und Einfügen mit anderen Apps einschränken|Richtlinie verwaltet apps mit Einfügen in||
||Anzeige von Webinhalten auf den Managed Browser beschränken|Nein||
||App-Daten verschlüsseln|Ja|Wählen Sie bei iOS diese Option aus: Wenn das Gerät gesperrt ist.|
||Deaktivieren der app-Verschlüsselung beim Gerät aktiviert ist|Ja|Deaktivieren Sie diese Einstellung, um doppelte Verschlüsselung zu vermeiden.|
||Kontaktsynchronisierung deaktivieren|Nein||
||Deaktivieren von ausdrucken|Nein||
|Zugriff|PIN für Zugriff anfordern|Ja||
||Wählen Sie|Numerische||
||Einfache PIN zulassen|Nein||
||PIN-Länge|6 ||
||Fingerabdruck anstelle von PIN zulassen|Ja||
||Deaktivieren der app PIN, Geräte-ID verwaltet wird|Ja||
||Erfordern des Unternehmensanmeldeinformationen für access|Nein||
||Erneutes Überprüfen der Zugriffsanforderung nach (Minuten)|30||
||Bildschirmaufnahme und Android-Assistenten blockieren|Nein|Bei iOS ist diese Option nicht verfügbar.|
|Anmeldung sicherheitsanforderungen|Max-PIN versucht|5 |Pin zurücksetzen|
||Offline-Toleranzperiode|720|Zugriff blockieren|
||Offline-Intervall (in Tagen), bevor App-Daten zurückgesetzt werden|90|Daten löschen|
||Jailbroken/Stamm Geräte| |Daten löschen|

Vergessen Sie nach Abschluss des Vorgangs nicht, auf „Erstellen“ zu klicken. Wiederholen Sie die oben genannten Schritte, und ersetzen Sie die ausgewählte Plattform (Dropdownliste) durch iOS. Dadurch werden zwei App-Richtlinien erstellt. Erstellen Sie also zunächst die Richtlinie, weisen Sie ihr dann Gruppen zu, und stellen Sie sie anschließend bereit.

Zum Bearbeiten der Richtlinien und diese Richtlinien Benutzern zuweisen, finden Sie unter [Erstellen und Zuweisen von Richtlinien für die app Schutz](https://docs.microsoft.com/intune/app-protection-policies). 

## <a name="require-approved-apps"></a>Genehmigte apps erfordern
Genehmigte apps erforderlich ist:

1. Navigieren Sie zum [Azure-Portal](https://portal.azure.com), und melden Sie sich mit Ihren Anmeldeinformationen an. Sobald Sie erfolgreich angemeldet sind, wird das Azure-Dashboard angezeigt.

2. Wählen Sie im linken Menü **Azure Active Directory** aus.

3. Klicken Sie im Bereich **Sicherheit** auf **Bedingter Zugriff**.

4. Wählen Sie **Neue Richtlinie** aus.

5. Geben Sie einen Richtliniennamen ein, und wählen Sie dann die **Benutzer und Gruppen** aus, auf die Sie die Richtlinie anwenden möchten.

6. Klicken Sie auf **Cloud-Apps**.

7. Wählen Sie **apps auswählen**, wählen Sie die gewünschten apps aus der Liste der **Cloud-apps** . Wählen Sie beispielsweise Office 365 Exchange Online. Klicken Sie auf **auswählen** und **Fertig**.

8. Wählen Sie im Abschnitt **Zugriffssteuerung** die Option **Erteilen** aus.

9. Wählen Sie **Zugriff gewähren**, wählen Sie **Client-app genehmigt erforderlich**.  Wählen Sie für mehrere Steuerelemente **die ausgewählten Steuerelemente erforderlich**, und klicken Sie dann **auf auswählen**. 

10. Klicken Sie auf **Erstellen**.

## <a name="define-device-compliance-policies"></a>Gerät Compliance-Richtlinien definieren

Gerät Kompatibilitätsrichtlinien definieren die Anforderungen, denen Geräte einhalten müssen, um als kompatibel markiert werden. Erstellen Sie Intune Gerät Kompatibilitätsrichtlinien im Azure-Portal aus. 

Erstellen Sie eine Richtlinie für jede Plattform:
- Android
- Android enterprise
- iOS
- Mac OS
- Windows Phone 8.1
- Windows 8.1 und höher
- Windows 10 und höher

Um Gerät Kompatibilitätsrichtlinien erstellen, melden Sie sich an das Microsoft Azure-Portal mit Ihren Anmeldeinformationen verwalten, und navigieren Sie zu **Intune > Gerät Compliance**. Klicken Sie auf **Richtlinie erstellen**.

Die folgenden Einstellungen sind für Windows 10 empfohlen.

**Device-Status: Windows Health Bescheinigung Service-Regeln**

|Eigenschaften|Werte|Hinweise|
|:---------|:-----|:----|
|BitLocker erfordern|Erforderlich||
|Erfordern Sie Secure Boot auf dem Gerät aktiviert werden soll|Erforderlich||
|Benötigen Sie die Integrität des Codes|Erforderlich||


**Geräteeigenschaften**

|Typ|Eigenschaften|Werte|Hinweise|
|:---|:---------|:-----|:----|
|Betriebssystemversion|Alle|Nicht konfiguriert||

Damit die oben aufgeführten Richtlinien als bereitgestellt betrachtet werden, müssen sie für bestimmte Benutzergruppen gelten. Erstellen Sie hierzu die Richtlinie (unter „Speichern“), oder wählen Sie später im Abschnitt „Richtlinie“ die Option „Bereitstellung verwalten“ aus (auf derselben Ebene wie „Hinzufügen“).

**Systemsicherheit**

|Typ|Eigenschaften|Werte|Hinweise|
|:---|:---------|:-----|:----|
|Password|Anfordern eines Kennworts zum Entsperren von mobiler Geräten|Erforderlich||
||Einfache Kennwörter|Blockieren||
||Kennworttyp|Gerät Standard||
||Minimale Kennwortlänge|6 ||
||Maximale Minuten Inaktivität bevor Kennwort erforderlich ist.|15 |Diese Einstellung wird für Android Versionen 4.0 und höher unterstützt oder KNOX 4.0 und höher. Für iOS-Geräte wird es für iOS 8.0 und höher unterstützt.|
||Kennwortablauf (Tage)|41||
||Anzahl der vorherigen Kennwörter, Wiederverwendung zu verhindern.|5 ||
||Kennwort ist erforderlich, wenn Gerät aus Leerlauf (Mobile und Holographic) zurückgibt|Erforderlich|Für Windows 10 und höher verfügbar.|
|Verschlüsselung|Verschlüsselung von Datenspeicher auf Gerät|Erforderlich||
|Sicherheit von Geräten|Firewall|Erforderlich||
||Antivirus|Erforderlich||
||AntiSpyware|Erforderlich|Diese Einstellung erfordert eine Anti-Schutz-Lösung mit dem Windows-Sicherheitscenter registriert.|
|Defender|Windows-Defender-Modul|Erforderlich||
||Windows Defender Modul Mindestversion||Nur unterstützt für Windows 10 Desktop. Microsoft empfiehlt Versionen nicht mehr als fünf hinter aus der aktuellsten Version.|
||Windows Defender Modul Signatur auf dem aktuellen Stand|Erforderlich||
||„Echtzeitschutz“|Erforderlich|Nur unterstützt für Windows 10 Desktop.|

**Windows Defender ATP**

|Typ|Eigenschaften|Werte|Hinweise|
|:---|:---------|:-----|:----|
|Windows Defender erweiterte Bedrohung-Schutzregeln|Erfordern Sie das Gerät an oder unter der Computer Risiko Score möglicherweise|Mittel||





## <a name="require-compliant-pcs-but-not-compliant-phones-and-tablets"></a>Erfordern Sie kompatible PCs (aber nicht kompatible Telefonen und Tablets)
Bevor Sie kompatible PCs erforderlich, um eine Richtlinie hinzufügen, unbedingt Geräte für die Verwaltung in Intune registrieren. Verwenden die mehrstufige Authentifizierung wird empfohlen, vor der Geräte in Intune registrieren Assurance, die das Gerät im Besitz des gewünschten Benutzers ist. 

Kompatible PCs erforderlich ist:

1. Navigieren Sie zum [Azure-Portal](https://portal.azure.com), und melden Sie sich mit Ihren Anmeldeinformationen an. Sobald Sie erfolgreich angemeldet sind, wird das Azure-Dashboard angezeigt.

2. Wählen Sie im linken Menü **Azure Active Directory** aus.

3. Klicken Sie im Bereich **Sicherheit** auf **Bedingter Zugriff**.

4. Wählen Sie **Neue Richtlinie** aus.

5. Geben Sie einen Richtliniennamen ein, und wählen Sie dann die **Benutzer und Gruppen** aus, auf die Sie die Richtlinie anwenden möchten.

6. Klicken Sie auf **Cloud-Apps**.

7. Wählen Sie **apps auswählen**, wählen Sie die gewünschten apps aus der Liste der **Cloud-apps** . Wählen Sie beispielsweise Office 365 Exchange Online. Klicken Sie auf **auswählen** und **Fertig**.

8. Wählen kompatible erforderlich, um PCs, aber nicht kompatible Telefonen und Tablets, **Bedingungen** und **Geräteplattformen**. Wählen Sie "Select Geräteplattformen", und wählen Sie **Windows** und **Mac OS**.

9. Wählen Sie im Abschnitt **Zugriffssteuerung** die Option **Erteilen** aus.

10. Wählen Sie **Zugriff gewähren**, wählen Sie **erforderlich Gerät als kompatibel markiert werden**.  Wählen Sie für mehrere Steuerelemente **alle ausgewählten Steuerelemente erforderlich**, und klicken Sie dann **auf auswählen**. 

11. Klicken Sie auf **Erstellen**.

Wenn Ihr Ziel ist es, kompatible PCs *und* mobilen Geräten müssen, wählen Sie Plattformen nicht. Dies erzwingt für alle Geräte kompatibel. 




## <a name="require-compliant-pcs-and-mobile-devices"></a>Erfordern Sie kompatible PCs *und* mobile Geräten

So erzwingen Sie Compliance für alle Geräte:

1. Navigieren Sie zum [Azure-Portal](https://portal.azure.com), und melden Sie sich mit Ihren Anmeldeinformationen an. Sobald Sie erfolgreich angemeldet sind, wird das Azure-Dashboard angezeigt.

2. Wählen Sie im linken Menü **Azure Active Directory** aus.

3. Klicken Sie im Bereich **Sicherheit** auf **Bedingter Zugriff**.

4. Wählen Sie **Neue Richtlinie** aus.

5. Geben Sie einen Richtliniennamen ein, und wählen Sie dann die **Benutzer und Gruppen** aus, auf die Sie die Richtlinie anwenden möchten.

6. Klicken Sie auf **Cloud-Apps**.

7. Wählen Sie **apps auswählen**, wählen Sie die gewünschten apps aus der Liste der **Cloud-apps** . Wählen Sie beispielsweise Office 365 Exchange Online. Klicken Sie auf **auswählen** und **Fertig**.

8. Wählen Sie im Abschnitt **Zugriffssteuerung** die Option **Erteilen** aus.

9. Wählen Sie **Zugriff gewähren**, wählen Sie **erforderlich Gerät als kompatibel markiert werden**. Wählen Sie für mehrere Steuerelemente **alle ausgewählten Steuerelemente erforderlich**, und klicken Sie dann **auf auswählen**. 

10. Klicken Sie auf **Erstellen**.

Wenn Sie diese Richtlinie zu erstellen, wählen Sie Plattformen nicht. Dies erzwingt kompatible Geräte.















<!---
#### Data loss prevention
The goal for your device and app management policies is to protect data loss in the event of a lost or stolen device. You can do this by ensuring that access to data is protected by a PIN, that the data is encrypted on the device, and that the device is not compromised.

|Policy recommendation|Description|
|:--------------------|:----------|
|**Require user PC management**|Require users to join their Windows PCs to an Active Directory Domain or enroll their PCs into management with Microsoft Intune or System Center Configuration Manager.|
|**Apply security settings via group policy objects (GPO) or Configuration Manager policies for domain joined PCs**|Deploy policies that configure managed PCs to enable BitLocker, enable anti-virus, and enable firewall.|
|**Require user mobile device management**|Require that user devices used to access email are managed by Intune **or** company email is accessed only through mobile email apps protected by Intune App Protection policies such as Outlook for iOS or Android.|
|**Apply an Intune Device Compliance Policy on managed devices**|Apply an Intune Device Compliance Policy for managed corporate mobile devices and Intune-managed PCs that requires: a PIN with minimum length 6, device encryption, a healthy device (is not jailbroken, rooted; passes health attestation), and, if available, require devices that are **low** risk as determined by a third-party MTP like Lookout or SkyCure.|
|**Apply an Intune App Protection Policy for managed apps running on unmanaged devices**|Apply an Intune App Protection Policy for managed apps running on unmanaged, personal mobile devices to require: a PIN with minimum length 6, device encryption, and that the device is healthy (is not jailbroken, rooted; passes health attestation).|

### User impact

For most organizations, it is important to be able to set user expectations around when and for which conditions they will be expected to sign into Office 365 to access their email.  

Users typically benefit from single sign-on (SSO) except during the following situations:
* When requesting authentication tokens for Exchange Online:
  * Users may be asked to MFA whenever a **medium or above** sign-in risk is detected and users has not yet performed MFA in their current sessions.  
  * Users will be required to either use email apps that support the Intune App Protection SDK or access emails from Intune compliant or AD domain-joined devices.
* When users at risk sign-in, and successfully complete MFA, they will be asked to change their password.

## Sensitive
This section describes the recommendations for the sensitive tier of data, identity, and device protection. These recommendations are for customers who have a subset of data that must be protected at higher levels or require all data to be protected at these higher levels.

You can apply increased protection to all or specific data sets in your Office 365 environment. For example, you can apply policies to ensure sensitive data is only shared between protected apps to prevent data loss. We recommend protecting identities and devices that access sensitive data with comparable levels of security.

### Conditional access policy settings
#### Identity protection

You can give users single sign-on (SSO) experience as described in earlier sections. You only need to intervene when necessary based on [risk events](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-risk-events).   

* Require MFA on **low or above** risk sessions
* Require secure password change for high risk users

>[!IMPORTANT]
>[Password synchronization](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization) and [self-service password reset](https://docs.microsoft.com/azure/active-directory/active-directory-passwords) are required for this policy recommendation.
>

#### Data loss prevention

The goal for these device and app management policies is to protect data loss in the event of a lost or stolen device. You can do this by ensuring that access to data is protected by a PIN, that the data is encrypted on the device, and that the device is not compromised.

|Policy recommendation|Description|
|:--------------------|:----------|
|**Require user PC management**|Require users to join their PCs to an Active Directory Domain or enroll their PCs into management with Intune or Configuration Manager and ensure those devices are compliant with policies before allowing email access.|
|**Apply security settings via group policy objects (GPO) or Configuration Manager policies for domain joined PCs**|Deploy policies that configure managed PCs to enable BitLocker, enable anti-virus, and enable firewall.|
|**Require user mobile device management**|Require that user devices used to access email are managed by Intune **or** company email is accessed only through mobile email apps protected by Intune App Protection policies such as Outlook for iOS or Android.|
|**Apply an Intune Device Compliance Policy on managed devices**|Apply an Intune Device Compliance Policy for managed corporate mobile devices and Intune-managed PCs that requires: a PIN with minimum length 6, device encryption, a healthy device (is not jailbroken, rooted; passes health attestation), and if available, require devices that are **low** risk as determined by a third-party MTP like Lookout or SkyCure.|
|**Apply an Intune App Protection Policy for managed apps running on unmanaged devices**|Apply an Intune App Protection Policy for managed apps running on unmanaged, personal mobile devices to require: a PIN with minimum length 6, device encryption, and that the device is healthy (is not jailbroken, rooted; passes health attestation).|

### User impact
For most organizations, it is important to be able to set expectations for users specific to when and under what conditions they will be expected to sign into Office 365 email.

Users typically benefit from single sign-on (SSO) except under the following situations:
* When requesting authentication tokens for Exchange Online:
  * Users will be asked to MFA whenever a **low or above** sign-in risk is detected and users has not yet performed MFA in their current sessions.  
  * Users will be required to either use email apps that support the Intune App Protection SDK or access emails from Intune compliant or AD domain-joined devices.
* When users at risk sign-in, and successfully complete MFA, they will be asked to change their password.

## Highly regulated
This section describes the recommendations for the highly regulated tier of data, identity, and device protection. These recommendations are for customers who may have a very small amount of data that is highly classified, trade secret, or regulated data. Microsoft provides capabilities to help organizations meet these requirements, including added protection for identities and devices.

### Conditional access policy settings
#### Identity protection

For the highly regulated tier Microsoft recommends enforcing MFA for all new sessions.
* Require MFA for all new sessions
* Require secure password change for **high** risk users

>[!IMPORTANT]
>[Password synchronization](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization) and [self-service password reset](https://docs.microsoft.com/azure/active-directory/active-directory-passwords) are required for this policy recommendation.
>

#### Data Loss Prevention
The goal for these device and app management policies is to prevent data loss in the event of a lost or stolen device. This is done by ensuring that access to data is protected by a PIN, that the data is encrypted on the device, and that the device is not compromised.

For the highly regulated tier, we recommend requiring apps that support Intune App Protection policy running only on Intune compliant or domain-joined devices.

|Policy recommendation|Description|
|:--------------------|:----------|
|**Require user PC management**|Require users to join their Windows PCs to an Active Directory Domain, **or** enroll their PCs into management with Intune or Configuration Manager and ensure those devices are compliant with policies before allowing email access.|
|**Apply security settings via group policy objects (GPO) or Configuration Manager policies for domain joined PCs**|Deploy policies that configure managed PCs to enable BitLocker, enable anti-virus, and enable firewall.|
|**Require user mobile device management**|Require that devices used to access Office 365 email and files are managed by Intune or company email is accessed only through mobile email apps protected by Intune App Protection policies such as Outlook for iOS or Android.|
|**Apply an Intune Device Compliance Policy on managed devices**|Apply an Intune Device Compliance Policy for managed corporate mobile devices and Intune-managed PCs that requires: a PIN with minimum length 6, device encryption, a healthy device (is not jailbroken, rooted; passes health attestation), and, if available, require devices that are Low risk as determined by a third-party MTP like Lookout or SkyCure.|

### User impact
For most organizations, it is important to be able to set expectations for users specific to when and under what conditions they will be expected to sign into Office 365 files.

* Users configured as highly regulated will be required to re-authenticate with MFA after their session expires.
* When users at risk sign-in they will be asked to change their password after completing MFA.
* When requesting authentication tokens for Exchange Online:
  * Users will be asked to perform MFA whenever they begin a new session.  
  * Users will be required to use email apps that support the Intune App Protection SDK
  * Users will be required to access emails from Intune compliant or AD domain-joined devices.
--->
## <a name="next-steps"></a>Nächste Schritte

[Weitere Informationen zu Richtlinienempfehlungen zum Schutz von E-Mails](secure-email-recommended-policies.md)
