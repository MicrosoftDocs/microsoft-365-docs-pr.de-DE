---
title: Erkennen und Behebung von unerlaubten Zustimmungsermings
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.collection:
- o365_security_incident_response
- M365-security-compliance
localization_priority: Normal
search.appverid:
- MET150
description: Erfahren Sie, wie Sie den angriffswilligen Zustimmungsermungsangriff in Microsoft Office 365 erkennen und besennen.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a1c724bb3b201e0ddf1edea4794606c7083605e8
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165439"
---
# <a name="detect-and-remediate-illicit-consent-grants"></a>Erkennen und Behebung von unerlaubten Zustimmungsermings

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**Zusammenfassung**  Erfahren Sie, wie Sie den angriffswilligen Zustimmungsermungsangriff in Office 365 erkennen und besennen.

## <a name="what-is-the-illicit-consent-grant-attack-in-office-365"></a>Was ist der Angriff auf die erteilungswillige Zustimmung in Office 365?

Bei einem Angriff auf eine unrechtmäßige Genehmigung erstellt der Angreifer eine in Azure registrierte Anwendung, die Zugriff auf Daten wie Kontaktinformationen, E-Mails oder Dokumente anfordert. Der Angreifer trickst dann einen Endbenutzer dazu, dieser Anwendung die Zustimmung zu erteilen, entweder über einen Phishingangriff auf ihre Daten zugreift, oder indem er unzulässigen Code in eine vertrauenswürdige Website einfing. Nachdem der unrechtmäßigen Anwendung die Zustimmung erteilt wurde, hat sie Zugriff auf Daten auf Kontoebene, ohne dass ein Organisationskonto benötigt wird. Normale Korrekturschritte, z. B. das Zurücksetzen von Kennwörtern für gesperrte Konten oder das Erfordern der mehrstufigen Authentifizierung (Multi-Factor Authentication, MFA) für Konten, sind bei dieser Art von Angriffen nicht effektiv, da es sich um Anwendungen von Drittanbietern handelt und sich außerhalb der Organisation befinden.

Diese Angriffe nutzen ein Interaktionsmodell, bei dem davon ausgegangen wird, dass es sich bei der Entität, die die Informationen aufruft, um Automatisierung und nicht um einen Menschen handelt.

> [!IMPORTANT]
> Verdächtigen Sie, dass Sie derzeit Probleme mit unerlaubten Zustimmungsermächtigungen von einer App haben? Microsoft Cloud App Security (MCAS) verfügt über Tools zum Erkennen, Untersuchen und Beheern Ihrer OAuth-Apps. Dieser MCAS-Artikel enthält ein Lernprogramm, in dem die Untersuchung [riskanter OAuth-Apps erläutert wird.](https://docs.microsoft.com/cloud-app-security/investigate-risky-oauth) Sie können auch [OAuth-App-Richtlinien](https://docs.microsoft.com/cloud-app-security/app-permission-policy) festlegen, um von der App angeforderte Berechtigungen zu untersuchen, welche Benutzer diese Apps autorisieren, und diese Berechtigungsanforderungen allgemein genehmigen oder verbieten.

## <a name="what-does-an-illicit-consent-grant-attack-look-like-in-office-365"></a>Wie sieht ein angriffswilliger Zustimmungserteilungsangriff in Office 365 aus?

Sie müssen das **Überwachungsprotokoll** durchsuchen, um Nachzeichen zu finden, die auch als Indicators of Compromise (IOC) für diesen Angriff bezeichnet werden. Für Organisationen mit vielen in Azure registrierten Anwendungen und einer großen Benutzerbasis besteht die bewährte Methode in der wöchentlichen Überprüfung der Zustimmungsermung Ihrer Organisation.

### <a name="steps-for-finding-signs-of-this-attack"></a>Schritte zum Auffinden von Anzeichen für diesen Angriff

1. Öffnen Sie **das Security & Compliance Center unter** <https://protection.office.com> .

2. Navigieren Sie zu **"Suchen",** und wählen **Sie "Überwachungsprotokollsuche" aus.**

3. Suchen Sie (alle Aktivitäten und alle Benutzer), geben Sie bei Bedarf das Start- und Enddatum ein, und klicken Sie dann auf **"Suchen".**

4. Klicken **Sie auf "Ergebnisse filtern",** und geben Sie "Zustimmung zur Anwendung" in das Feld **"Aktivität"** ein.

5. Klicken Sie auf das Ergebnis, um die Details der Aktivität anzuzeigen. Klicken **Sie auf "Weitere Informationen",** um Details zu der Aktivität zu erhalten. Überprüfen Sie, ob IsAdminContent auf "True" festgelegt ist.

> [!NOTE]
>
> Es kann zwischen 30 Minuten und 24 Stunden dauern, bis der entsprechende Überwachungsprotokolleintrag in den Suchergebnissen angezeigt wird, nachdem ein Ereignis eintritt.
>
> Die Dauer, für die ein Überwachungsdatensatz aufbewahrt und im Überwachungsprotokoll durchsuchbar ist, hängt von Ihrem Microsoft 365-Abonnement und insbesondere vom Lizenztyp ab, der einem bestimmten Benutzer zugewiesen ist. Weitere Informationen finden Sie im [Überwachungsprotokoll.](../../compliance/search-the-audit-log-in-security-and-compliance.md)
>
> Wenn dieser Wert "true" ist, weist dies darauf hin, dass eine Person mit zugriff auf globaler Administrator möglicherweise einen umfassenden Zugriff auf Daten gewährt hat. Wenn dies unerwartet ist, führen Sie Schritte aus, um [einen Angriff zu bestätigen.](#how-to-confirm-an-attack)

## <a name="how-to-confirm-an-attack"></a>So bestätigen Sie einen Angriff

Wenn Sie eine oder mehrere Instanzen der oben aufgeführten IOCs haben, müssen Sie weitere Untersuchungen unternehmen, um zu bestätigen, dass der Angriff aufgetreten ist. Sie können eine dieser drei Methoden verwenden, um den Angriff zu bestätigen:

- Inventarisierung von Anwendungen und deren Berechtigungen mithilfe des Azure Active Directory-Portals. Diese Methode ist sorgfältig, Aber Sie können nur einen Benutzer gleichzeitig überprüfen, was sehr zeitaufwändig sein kann, wenn Sie viele Benutzer zu überprüfen haben.

- Inventarisierung von Anwendungen und deren Berechtigungen mithilfe von PowerShell. Dies ist die schnellste und gründlichste Methode mit dem geringsten Aufwand.

- Lassen Sie Ihre Benutzer ihre Apps und Berechtigungen einzeln überprüfen und die Ergebnisse zur Problembehebung an die Administratoren zurücksenennen.

## <a name="inventory-apps-with-access-in-your-organization"></a>Inventarisierung von Apps mit Zugriff in Ihrer Organisation

Sie können dies für Ihre Benutzer entweder über das Azure Active Directory-Portal oder PowerShell tun oder ihre Benutzer einzeln ihren Anwendungszugriff aufzählen lassen.

### <a name="steps-for-using-the-azure-active-directory-portal"></a>Schritte für die Verwendung des Azure Active Directory-Portals

Sie können die Anwendungen nachschauen, für die jeder einzelne Benutzer Berechtigungen erteilt hat, indem Sie das [Azure Active Directory Portal verwenden.](https://portal.azure.com/)

1. Melden Sie sich beim Azure Portal mit Administratorrechten an.

2. Wählen Sie das Blatt Azure Active Directory aus.

3. Wählen Sie **Benutzer** aus.

4. Wählen Sie den Benutzer aus, den Sie überprüfen möchten.

5. Wählen Sie **Anwendungen aus.**

Dadurch werden die Apps angezeigt, die dem Benutzer zugewiesen sind, und welche Berechtigungen die Anwendungen besitzen.

### <a name="steps-for-having-your-users-enumerate-their-application-access"></a>Schritte zum Aufzählen des Anwendungszugriffs durch die Benutzer

Lassen Sie Ihre Benutzer dort https://myapps.microsoft.com ihre eigenen Anwendungszugriffe überprüfen. Sie sollten in der Lage sein, alle Apps mit Zugriff anzuzeigen, Details zu ihnen anzuzeigen (einschließlich des Zugriffsumfangs), und in der Lage sein, Berechtigungen für verdächtige oder unzulässige Apps zu widerrufen.

### <a name="steps-for-doing-this-with-powershell"></a>Schritte dazu mit PowerShell

Die einfachste Möglichkeit zum Überprüfen des Angriffs auf die gewährungswillige Zustimmung besteht in der Ausführung von [Get-AzureADPSPermissions.ps1, ](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09)wodurch alle OAuth-Zustimmungserteilungen und -OAuth-Apps für alle Benutzer in Ihrem Mandanz in einer CSV-Datei gespeichert werden.

#### <a name="pre-requisites"></a>Voraussetzungen

- Die Installierte Azure AD PowerShell-Bibliothek.

- Globale Administratorrechte für den Mandanten, für den das Skript ausgeführt wird.

- Lokaler Administrator auf dem Computer, auf dem die Skripts ausgeführt werden.

> [!IMPORTANT]
> Es ***wird dringend empfohlen,*** dass Sie eine mehrstufige Authentifizierung für Ihr Administratorkonto benötigen. Dieses Skript unterstützt die MFA-Authentifizierung.

1. Melden Sie sich bei dem Computer an, auf dem Sie das Skript mit lokalen Administratorrechten ausführen.

2. Laden Sie das Skript [Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09) von GitHub in einen Ordner herunter, aus dem Sie das Skript ausführen. Dies ist derselbe Ordner, in den die Ausgabedatei "permissions.csv" geschrieben wird.

3. Öffnen Sie eine PowerShell-Instanz als Administrator, und öffnen Sie den Ordner, in dem Sie das Skript gespeichert haben.

4. Stellen Sie mithilfe des [Connect-AzureAD-Cmdlets](https://docs.microsoft.com/powershell/module/azuread/connect-azuread) eine Verbindung mit Ihrem Verzeichnis herzustellen.

5. Führen Sie diesen PowerShell-Befehl aus:

   ```powershell
   Get-AzureADPSPermissions.ps1 | Export-csv -Path "Permissions.csv" -NoTypeInformation
   ```

Das Skript erzeugt eine Datei namens Permissions.csv. Führen Sie die folgenden Schritte aus, um nach unzulässigen Anwendungsberechtigungen zu suchen:

1. Suchen Sie in der Spalte "ConsentType" (Spalte G) nach dem Wert "AllPrinciples". Mit der Berechtigung "AllPrincipals" kann die Clientanwendung auf alle Inhalte im Mandanten zugreifen. Systemeigene Microsoft 365-Anwendungen benötigen diese Berechtigung, um ordnungsgemäß zu funktionieren. Jede Nicht-Microsoft-Anwendung mit dieser Berechtigung sollte sorgfältig überprüft werden.

2. Überprüfen Sie in der Spalte "Berechtigung" (Spalte F) die Berechtigungen, die jede delegierte Anwendung für Inhalte hat. Suchen Sie nach der Berechtigung "Lesen" und "Schreiben" oder "*". Alle"-Berechtigungen, und überprüfen Sie diese sorgfältig, da sie möglicherweise nicht geeignet sind.

3. Überprüfen Sie die spezifischen Benutzer, deren Zustimmung erteilt wurde. Wenn Benutzern mit hoher Profil- oder hoher Auswirkung unangemessene Zustimmungen erteilt wurden, sollten Sie dies weiter untersuchen.

4. Suchen Sie in der Spalte "ClientDisplayName" (Spalte C) nach Apps, die verdächtig erscheinen. Apps mit falsch geschriebenen Namen, Super-Bland-Namen oder Hackernamen sollten sorgfältig überprüft werden.

## <a name="determine-the-scope-of-the-attack"></a>Bestimmen des Umfangs des Angriffs

Nachdem Sie die Bestandsaufnahme des Anwendungszugriffs abgeschlossen haben, überprüfen Sie das **Überwachungsprotokoll,** um den vollständigen Umfang der Verletzung zu ermitteln. Suchen Sie nach den betroffenen Benutzern, den Zeitrahmen, auf die die verbotene Anwendung Zugriff auf Ihre Organisation hatte, und den Berechtigungen, die die App hatte. Sie können das **Überwachungsprotokoll im** [Microsoft 365 Security and Compliance Center durchsuchen.](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)

> [!IMPORTANT]
> [Postfachüberwachung](https://docs.microsoft.com/microsoft-365/compliance/enable-mailbox-auditing) und [Aktivitätsüberwachung für](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off) Administratoren und Benutzer müssen vor dem Angriff aktiviert worden sein, damit Sie diese Informationen erhalten können.

## <a name="how-to-stop-and-remediate-an-illicit-consent-grant-attack"></a>Beenden und Behebung eines Angriffs auf eine unrechtmäßige Zustimmungserteilung

Nachdem Sie eine Anwendung mit unzulässigen Berechtigungen identifiziert haben, haben Sie mehrere Möglichkeiten, diesen Zugriff zu entfernen.

- Sie können die Berechtigung der Anwendung im Azure Active Directory Portal widerrufen, indem Sie:

  - Navigieren Sie im Blatt **"Azure Active Directory-Benutzer"** zu dem betroffenen Benutzer.

  - Wählen Sie **Anwendungen aus.**

  - Wählen Sie die unzulässige Anwendung aus.

  - Klicken **Sie im** Drilldown auf "Entfernen".

- Sie können die OAuth-Zustimmungserteilung mit PowerShell widerrufen, indem Sie die Schritte in ["Remove-AzureADOAuth2PermissionGrant" ausführen.](https://docs.microsoft.com/powershell/module/azuread/Remove-AzureADOAuth2PermissionGrant)

- Sie können die Dienst-App-Rollenzuweisung mit PowerShell widerrufen, indem Sie die Schritte in ["Remove-AzureADServiceAppRoleAssignment" ausführen.](https://docs.microsoft.com/powershell/module/azuread/Remove-AzureADServiceAppRoleAssignment)

- Sie können die Anmeldung für das betroffene Konto auch vollständig deaktivieren, wodurch wiederum der Zugriff der App auf Daten in diesem Konto deaktiviert wird. Dies ist natürlich nicht ideal für die Produktivität des Endbenutzers, aber wenn Sie daran arbeiten, die Auswirkungen schnell zu begrenzen, kann dies eine kurzfristige Korrektur sein.

- Sie können integrierte Anwendungen für Ihren Mandanz deaktivieren. Dies ist ein drastischer Schritt, der die Möglichkeit für Endbenutzer deaktiviert, die Zustimmung auf mandantenweitem Basis zu erteilen. Dadurch wird verhindert, dass Ihre Benutzer versehentlich Zugriff auf eine schädliche Anwendung gewähren. Dies wird nicht dringend empfohlen, da die Fähigkeit ihrer Benutzer, mit Anwendungen von Drittanbietern produktiv zu sein, stark beeinträchtigt wird. Dazu können Sie die Schritte unter "Aktivieren oder Deaktivieren von integrierten [Apps" ausführen.](https://docs.microsoft.com/microsoft-365/admin/misc/integrated-apps)

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a>Sichern von Microsoft 365 wie ein Profi für Internetsicherheit

Ihr Microsoft 365-Abonnement bietet eine Reihe von leistungsfähigen Funktionen für Sicherheit, die Sie zum Schutz Ihrer Daten und Ihrer Benutzer verwenden können. Verwenden Sie die [Microsoft 365-Sicherheits-Roadmap: Top-Prioritäten für die ersten 30 Tage, 90 Tage und darüber hinaus](security-roadmap.md) zum Implementieren von empfohlenen Microsoft-Best-Practices für den Schutz Ihres Microsoft 365-Mandanten.

- Aufgaben, die in den ersten 30 Tagen ausgeführt werden sollten. Diese sind unmittelbar gültig und haben nur geringe Auswirkungen für die Benutzer.

- Aufgaben, die innerhalb von 90 Tagen ausgeführt werden sollten. Diese erfordern etwas mehr Zeit für Planung und Implementierung, stärken die Sicherheit Ihres Unternehmens jedoch erheblich.

- Über 90 Tage hinaus. Diese Verbesserungen werden in den ersten 90 Tagen Ihrer Arbeit umgesetzt.

## <a name="see-also"></a>Siehe auch:

- [Eine unerwartete Anwendung in meiner Anwendungsliste](https://docs.microsoft.com/azure/active-directory/application-access-unexpected-application) führt Administratoren durch verschiedene Aktionen, die sie möglicherweise ausführen möchten, nachdem sie sich über unerwartete Anwendungen mit Zugriff auf Daten geärärt haben.

- [Das Integrieren von Anwendungen in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-apps-permissions-consent) ist eine übersicht über Zustimmung und Berechtigungen auf hoher Ebene.

- [Probleme bei der Entwicklung meiner Anwendung](https://docs.microsoft.com/azure/active-directory/active-directory-application-dev-development-content-map) bieten Links zu verschiedenen Artikeln im Zusammenhang mit der Zustimmung.

- [Anwendungs- und Dienstprinzipalobjekte in Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/develop/active-directory-application-objects) bieten eine Übersicht über die Anwendungs- und Dienstprinzipalobjekte, die kern des Anwendungsmodells sind.

- [Die Verwaltung des Zugriffs auf Apps](https://docs.microsoft.com/azure/active-directory/active-directory-managing-access-to-apps) ist eine Übersicht über die Funktionen, die Administratoren zum Verwalten des Benutzerzugriffs auf Apps haben.
