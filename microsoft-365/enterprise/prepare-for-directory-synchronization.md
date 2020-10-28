---
title: Vorbereiten der Verzeichnissynchronisierung mit Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/30/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365p_AddUsersWithDirSync
- O365M_AddUsersWithDirSync
- O365E_HRCSetupAADConnectAboutLM617031
- O365E_AddUsersWithDirSync
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOP150
- MOE150
- MBS150
ms.assetid: 01920974-9e6f-4331-a370-13aea4e82b3e
description: Beschreibt, wie Sie die Bereitstellung von Benutzern auf Microsoft 365 mithilfe der Verzeichnissynchronisierung und die langfristigen Vorteile der Verwendung dieser Methode vorbereiten.
ms.openlocfilehash: b74310b0f444da118699c5ad5fbb68b15519b830
ms.sourcegitcommit: 45c0afcf958069c5c1b31f9b6c762d8dd806e1e9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "48773985"
---
# <a name="prepare-for-directory-synchronization-to-microsoft-365"></a>Vorbereiten der Verzeichnissynchronisierung mit Microsoft 365

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Zu den Vorteilen der Hybriden Identitäts-und Verzeichnissynchronisierung in Ihrer Organisation gehören:

- Reduzieren der Verwaltungsprogramme in Ihrer Organisation
- Optionales Aktivieren des Szenarios für einmaliges Anmelden
- Automatisieren von Kontoänderungen in Microsoft 365

Weitere Informationen zu den Vorteilen der Verwendung der Verzeichnissynchronisierung finden Sie unter [Hybrid Identity with Azure Active Directory (Azure AD)](https://go.microsoft.com/fwlink/p/?LinkId=525398) und [Hybrid Identity for Microsoft 365](plan-for-directory-synchronization.md).

Die Verzeichnissynchronisierung erfordert jedoch die Planung und Vorbereitung, um sicherzustellen, dass Ihre Active Directory-Domänendienste (AD DS) mit dem Azure AD Mandanten Ihres Microsoft 365-Abonnements mit einem Minimum an Fehlern synchronisiert wird.

Führen Sie die folgenden Schritte aus, um die besten Ergebnisse zu erzielen.

## <a name="1-directory-cleanup-tasks"></a>1. Aufgaben zur Verzeichnisbereinigung

Bevor Sie Ihre AD DS mit Ihrem Azure AD-Mandanten synchronisieren, müssen Sie Ihre AD DS bereinigen.

> [!IMPORTANT]
> Wenn Sie AD DS Bereinigung vor der Synchronisierung nicht ausführen, kann dies zu erheblichen negativen Auswirkungen auf den Bereitstellungsprozess führen. Es kann Tage oder sogar Wochen dauern, bis der Zyklus der Verzeichnissynchronisierung durchläuft, Fehler identifiziert und erneut synchronisiert wird.

Führen Sie in Ihrem AD DS die folgenden Bereinigungsaufgaben für jedes Benutzerkonto aus, dem eine Microsoft 365-Lizenz zugewiesen wird:

1. Stellen Sie eine gültige und eindeutige e-Mail-Adresse im **proxyAddresses** -Attribut sicher.

2. Entfernen Sie alle doppelten Werte im **proxyAddresses** -Attribut.

3. Stellen Sie nach Möglichkeit einen gültigen und eindeutigen Wert für das **userPrincipalName** -Attribut im **Benutzer** Objekt des Benutzers sicher. Stellen Sie sicher, dass der AD DS UPN mit dem Azure AD UPN übereinstimmt, um eine optimale Synchronisierung zu erzielen. Wenn ein Benutzer keinen Wert für das **userPrincipalName** -Attribut aufweist, muss das **User** -Objekt einen gültigen und eindeutigen Wert für das **sAMAccountName** -Attribut enthalten. Entfernen Sie alle doppelten Werte im **userPrincipalName** -Attribut.

4. Stellen Sie für eine optimale Verwendung der globalen Adressliste (GAL) sicher, dass die Informationen in den folgenden Attributen des AD DS Benutzerkontos richtig sind:

   - givenName
   - surname
   - displayName
   - Position
   - Abteilung
   - Büro
   - Telefon (geschäftlich)
   - Mobiltelefon
   - Faxnummer
   - Straße
   - Stadt/Ort
   - Bundesland/Kanton
   - PLZ
   - Land oder Region

## <a name="2-directory-object-and-attribute-preparation"></a>2. Verzeichnisobjekt-und Attribut Vorbereitung

Für eine erfolgreiche Verzeichnissynchronisierung zwischen Ihrem AD DS und Microsoft 365 müssen die AD DS-Attribute ordnungsgemäß vorbereitet werden. Beispielsweise müssen Sie sicherstellen, dass bestimmte Zeichen nicht in bestimmten Attributen verwendet werden, die mit der Microsoft 365-Umgebung synchronisiert werden. Unerwartete Zeichen führen nicht dazu, dass die Verzeichnissynchronisierung fehlschlägt, aber möglicherweise wird eine Warnung zurückgegeben. Ungültige Zeichen führen dazu, dass die Verzeichnissynchronisierung fehlschlägt.

Die Verzeichnissynchronisierung schlägt auch fehl, wenn einige Ihrer AD DS Benutzer über ein oder mehrere doppelte Attribute verfügen. Jeder Benutzer muss über eindeutige Attribute verfügen.

Die Attribute, die Sie vorbereiten müssen, sind hier aufgelistet:

- **displayName**

  - Wenn das Attribut im User-Objekt vorhanden ist, wird es mit Microsoft 365 synchronisiert.
  - Wenn dieses Attribut im User-Objekt vorhanden ist, muss es einen Wert dafür geben. Das heißt, das Attribut darf nicht leer sein.
  - Maximale Anzahl der Zeichen: 256

- **givenName**

  - Wenn das Attribut im User-Objekt vorhanden ist, wird es mit Microsoft 365 synchronisiert, aber Microsoft 365 erfordert oder verwendet es nicht.
  - Maximale Anzahl der Zeichen: 64

- **Mail**

  - Der Attributwert muss innerhalb des Verzeichnisses eindeutig sein.

    > [!NOTE]
    > Wenn es doppelte Werte gibt, wird der erste Benutzer mit dem Wert synchronisiert. Nachfolgende Benutzer werden in Microsoft 365 nicht angezeigt. Sie müssen entweder den Wert in Microsoft 365 ändern oder beide Werte in AD DS ändern, damit beide Benutzer in Microsoft 365 angezeigt werden.

- **mailnick Name** (Exchange-Alias)

  - Der Attributwert darf nicht mit einem Punkt (.) beginnen.
  - Der Attributwert muss innerhalb des Verzeichnisses eindeutig sein.

    > [!NOTE]
    > Unterstriche ("_") im synchronisierten Namen gibt an, dass der ursprüngliche Wert dieses Attributs ungültige Zeichen enthält. Weitere Informationen zu diesem Attribut finden Sie unter [Exchange-Alias Attribut](https://docs.microsoft.com/powershell/module/exchange/set-mailbox).
    >

- **proxyAddresses**

  - Mehrwertiges Attribut
  - Maximale Anzahl von Zeichen pro Wert: 256
  - Der Attributwert darf kein Leerzeichen enthalten.
  - Der Attributwert muss innerhalb des Verzeichnisses eindeutig sein.
  - Ungültige Zeichen: \< \> ();, [] "'

    Beachten Sie, dass die ungültigen Zeichen auf die Zeichen nach dem typtrennzeichen und ":" angewendet werden, so dass SMTP:User@contso.com zulässig ist, aber SMTP:User:M@contoso.com nicht ist.

    > [!IMPORTANT]
    > Alle SMTP-Adressen (Simple Mail Transport Protocol) sollten den e-Mail-Messagingstandards entsprechen. Wenn doppelte oder unerwünschte Adressen vorhanden sind, finden Sie im Hilfethema [Entfernen von doppelten und unerwünschten Proxyadressen in Exchange](https://go.microsoft.com/fwlink/?LinkId=293860).

- **sAMAccountName**

  - Maximale Anzahl der Zeichen: 20
  - Der Attributwert muss innerhalb des Verzeichnisses eindeutig sein.
  - Ungültige Zeichen: [\ "|,/: \< \> + =;? \* ']
  - Wenn ein Benutzer ein ungültiges **sAMAccountName** -Attribut aufweist, aber über ein gültiges **userPrincipalName** -Attribut verfügt, wird das Benutzerkonto in Microsoft 365 erstellt.
  - Wenn sowohl **sAMAccountName** als auch **userPrincipalName** ungültig sind, muss das AD DS **userPrincipalName** -Attribut aktualisiert werden.

- **SN** (Nachname)

  - Wenn das Attribut im User-Objekt vorhanden ist, wird es mit Microsoft 365 synchronisiert, aber Microsoft 365 erfordert oder verwendet es nicht.

- **targetAddress**

    Es ist erforderlich, dass das **targetAddress** -Attribut (beispielsweise SMTP:Tom@contoso.com), das für den Benutzer aufgefüllt wird, in der Microsoft 365 GAL angezeigt wird. Bei Messaging Migrationsszenarien von Drittanbietern wäre dies die Microsoft 365-Schemaerweiterung für den AD DS erforderlich. Die Microsoft 365-Schemaerweiterung würde auch weitere nützliche Attribute zum Verwalten von Microsoft 365-Objekten hinzufügen, die mit einem Verzeichnissynchronisierungstool aus AD DS aufgefüllt werden. Beispielsweise würde das **msExchHideFromAddressLists** -Attribut zum Verwalten von ausgeblendeten Postfächern oder Verteilergruppen hinzugefügt werden.

  - Maximale Anzahl der Zeichen: 256
  - Der Attributwert darf kein Leerzeichen enthalten.
  - Der Attributwert muss innerhalb des Verzeichnisses eindeutig sein.
  - Ungültige Zeichen: \ \< \> ();, [] "
  - Alle SMTP-Adressen (Simple Mail Transport Protocol) sollten den e-Mail-Messagingstandards entsprechen.

- **userPrincipalName**

  - Das **userPrincipalName** -Attribut muss das Anmeldeformat im Internet Format aufweisen, dem der Benutzername gefolgt von dem @-Zeichen (@) und einem Domänennamen folgt: beispielsweise user@contoso.com. Alle SMTP-Adressen (Simple Mail Transport Protocol) sollten den e-Mail-Messagingstandards entsprechen.
  - Die maximale Anzahl von Zeichen für das **userPrincipalName** -Attribut lautet 113. Eine bestimmte Anzahl von Zeichen ist vor und nach dem @-Zeichen wie folgt zulässig:
  - Maximale Anzahl von Zeichen für den Benutzernamen vor dem @-Zeichen (@): 64
  - Maximale Anzahl von Zeichen für den Domänennamen nach dem @-Zeichen (@): 48
  - Ungültige Zeichen: \% &amp; \* +/=? { } | \< \> ( ) ; : , [ ] "
  - Zulässige Zeichen: a – z, a-z, 0 – 9, '. - _ ! # ^ ~
  - Buchstaben mit diakritischen Zeichen wie Umlauten, Akzenten und Tilden sind ungültige Zeichen.
  - Das @-Zeichen ist in jedem **userPrincipalName** -Wert erforderlich.
  - Das @-Zeichen darf nie das erste Zeichen in einem **userPrincipalName** -Wert sein.
  - Der Benutzername darf nicht mit einem Punkt (.), einem kaufmännischen und- &amp; Zeichen (), einem Leerzeichen oder einem @-Zeichen enden.
  - Der Benutzername darf keine Leerzeichen enthalten.
  - Routingfähige Domänen müssen verwendet werden; Beispielsweise können keine lokalen oder internen Domänen verwendet werden.
  - Unicode-Zeichen werden in Unterstriche umgewandelt.
  - **userPrincipalName** darf keine doppelten Werte im Verzeichnis enthalten.

## <a name="3-prepare-the-userprincipalname-attribute"></a>3. Vorbereiten des userPrincipalName-Attributs

Active Directory wurde entwickelt, um es den Endbenutzern in Ihrer Organisation zu ermöglichen, sich mit **sAMAccountName** oder **userPrincipalName** bei Ihrem Verzeichnis anzumelden. Auf ähnliche Weise können sich Endbenutzer bei Microsoft 365 mit dem Benutzerprinzipalnamen (User Principal Name, UPN) Ihres Geschäfts-oder Schul Kontos anmelden. Die Verzeichnissynchronisierung versucht, neue Benutzer in Azure Active Directory mithilfe desselben UPN zu erstellen, der in Ihrem AD DS ist. Der UPN ist wie eine e-Mail-Adresse formatiert.

In Microsoft 365 ist der UPN das Standardattribut, das zum Generieren der e-Mail-Adresse verwendet wird. Es ist ganz einfach, **userPrincipalName** (in AD DS und in Azure AD) und die primäre e-Mail-Adresse in **proxyAddresses** auf unterschiedliche Werte festgelegt zu erhalten. Wenn Sie auf unterschiedliche Werte festgelegt sind, kann es zu Verwirrung für Administratoren und Endbenutzer kommen.

Es empfiehlt sich, diese Attribute auszurichten, um Verwirrung zu verringern. Um die Anforderungen des einmaligen Anmeldens mit Active Directory-Verbunddienste (AD FS) 2.0 zu erfüllen, müssen Sie sicherstellen, dass die UPNs in Azure Active Directory und Ihre AD DS übereinstimmen und einen gültigen Domänennamespace verwenden.

## <a name="4-add-an-alternative-upn-suffix-to-ad-ds"></a>4. Hinzufügen eines alternativen UPN-Suffix zu AD DS

Möglicherweise müssen Sie ein alternatives UPN-Suffix hinzufügen, um die Unternehmensanmeldeinformationen des Benutzers der Microsoft 365-Umgebung zuzuordnen. Ein UPN-Suffix ist der Teil eines Benutzerprinzipalnamens, der rechts vom Zeichen @ steht. UPNs, die für einmaliges Anmelden verwendet werden, können Buchstaben, Zahlen, Punkte, Bindestriche und Unterstriche enthalten, aber keine anderen Zeichen.

Weitere Informationen zum Hinzufügen eines alternativen UPN-Suffix zu Active Directory finden Sie unter [Prepare for Directory Synchronization]( https://go.microsoft.com/fwlink/p/?LinkId=525430).

## <a name="5-match-the-ad-ds-upn-with-the-microsoft-365-upn"></a>5. Übereinstimmung mit dem AD DS UPN mit dem Microsoft 365 UPN

Wenn Sie die Verzeichnissynchronisierung bereits eingerichtet haben, stimmt der UPN des Benutzers für Microsoft 365 möglicherweise nicht mit dem AD DS UPN des Benutzers überein, der in Ihrem AD DS definiert ist. Das kann vorkommen, wenn einem Benutzer vor der Überprüfung der Domäne schon eine Lizenz zugewiesen wurde. Um dies zu beheben, verwenden Sie [PowerShell, um doppelten UPN zu beheben](https://go.microsoft.com/fwlink/p/?LinkId=396730) , um den UPN des Benutzers zu aktualisieren, um sicherzustellen, dass der Microsoft 365-UPN dem Benutzernamen und der Domäne des Unternehmens entspricht. Wenn Sie den UPN im AD DS aktualisieren und mit der Azure Active Directory-Identität synchronisieren möchten, müssen Sie die Lizenz des Benutzers in Microsoft 365 entfernen, bevor Sie die Änderungen in AD DS vornehmen.

Weitere Informationen finden Sie unter [Vorgehensweise Vorbereiten einer nicht routingfähigen Domäne (beispielsweise. Local Domain) für die Verzeichnissynchronisierung](prepare-a-non-routable-domain-for-directory-synchronization.md).

## <a name="next-steps"></a>Nächste Schritte

Wenn Sie die Schritte 1 bis 5 oben ausgeführt haben, finden Sie weitere Informationen unter [Einrichten der Verzeichnissynchronisierung](set-up-directory-synchronization.md).
