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
description: Beschreibt, wie Sie die Bereitstellung von Benutzern für Microsoft 365 mithilfe der Verzeichnissynchronisierung und der langfristigen Vorteile dieser Methode vorbereiten.
ms.openlocfilehash: 7f701bf0a8b165323f7fd61b50b41fb5e18268a6
ms.sourcegitcommit: 5a1cb7d95070eef47d401a4693cc137a90550a5e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52259559"
---
# <a name="prepare-for-directory-synchronization-to-microsoft-365"></a>Vorbereiten der Verzeichnissynchronisierung mit Microsoft 365

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Zu den Vorteilen für die Hybrididentität und Verzeichnissynchronisierung in Ihrer Organisation gehören:

- Reduzieren der Administrativen Programme in Ihrer Organisation
- Optional aktivieren des Szenarios für einmaliges Anmelden
- Automatisieren von Kontoänderungen in Microsoft 365

Weitere Informationen zu den Vorteilen der Verzeichnissynchronisierung finden Sie unter [Hybrididentität mit Azure Active Directory (Azure AD)](/azure/active-directory/hybrid/whatis-hybrid-identity) und [Hybrididentität für Microsoft 365](plan-for-directory-synchronization.md).

Die Verzeichnissynchronisierung erfordert jedoch eine Planung und Vorbereitung, um sicherzustellen, dass Ihre Active Directory Domain Services (AD DS) mit dem Azure AD-Mandanten Ihres Microsoft 365-Abonnements synchronisiert werden.

Führen Sie die folgenden Schritte aus, um die besten Ergebnisse zu erzielen.

## <a name="1-directory-cleanup-tasks"></a>1. Verzeichnisbereinigungsaufgaben

Bevor Sie Ad DS mit Ihrem Azure AD-Mandanten synchronisieren, müssen Sie Ad DS bereinigen.

> [!IMPORTANT]
> Wenn Sie vor der Synchronisierung keine AD DS-Bereinigung durchführen, kann dies zu erheblichen negativen Auswirkungen auf den Bereitstellungsprozess führen. Es kann Tage oder sogar Wochen dauern, bis der Zyklus der Verzeichnissynchronisierung, der Identifizierung von Fehlern und der erneuten Synchronisierung durchgehen kann.

Führen Sie in Ihrem AD DS die folgenden Bereinigungsaufgaben für jedes Benutzerkonto aus, dem eine Microsoft 365 zugewiesen wird:

1. Stellen Sie eine gültige und eindeutige E-Mail-Adresse im **proxyAddresses-Attribut** sicher.

2. Entfernen Sie alle doppelten Werte im **proxyAddresses-Attribut.**

3. Stellen Sie nach Möglichkeit einen gültigen und eindeutigen Wert für das **userPrincipalName-Attribut** im **Benutzerobjekt** des Benutzers sicher. Stellen Sie sicher, dass der AD DS UPN dem Azure AD UPN entspricht, um eine optimale Synchronisierung zu gewährleisten. Wenn ein Benutzer keinen Wert für das **userPrincipalName-Attribut** hat, muss das **Benutzerobjekt** einen gültigen und eindeutigen Wert für das **sAMAccountName-Attribut** enthalten. Entfernen Sie alle doppelten Werte im **userPrincipalName-Attribut.**

4. Stellen Sie sicher, dass die Informationen in den folgenden Attributen des AD DS-Benutzerkontos korrekt sind, um die globale Adressliste optimal zu verwenden:

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

## <a name="2-directory-object-and-attribute-preparation"></a>2. Vorbereitung von Verzeichnisobjekten und Attributen

Eine erfolgreiche Verzeichnissynchronisierung zwischen Ad DS und Microsoft 365 erfordert, dass Ihre AD DS-Attribute ordnungsgemäß vorbereitet sind. Sie müssen z. B. sicherstellen, dass bestimmte Zeichen nicht in bestimmten Attributen verwendet werden, die mit der umgebungsspezifischen Microsoft 365 werden. Unerwartete Zeichen führen nicht zu einem Fehler bei der Verzeichnissynchronisierung, aber möglicherweise wird eine Warnung angezeigt. Ungültige Zeichen führen zu einem Fehler bei der Verzeichnissynchronisierung.

Die Verzeichnissynchronisierung kann auch fehlschlagen, wenn einige Ad DS-Benutzer über ein oder mehrere doppelte Attribute verfügen. Jeder Benutzer muss über eindeutige Attribute verfügen.

Die Attribute, die Sie vorbereiten müssen, sind hier aufgeführt:

- **displayName**

  - Wenn das Attribut im Benutzerobjekt vorhanden ist, wird es mit Microsoft 365.
  - Wenn dieses Attribut im Benutzerobjekt vorhanden ist, muss ein Wert dafür vorhanden sein. Das heißt, das Attribut darf nicht leer sein.
  - Maximale Anzahl der Zeichen: 256

- **givenName**

  - Wenn das Attribut im Benutzerobjekt vorhanden ist, wird es mit Microsoft 365 synchronisiert, aber Microsoft 365 erfordert oder verwendet es nicht.
  - Maximale Anzahl der Zeichen: 64

- **mail**

  - Der Attributwert muss innerhalb des Verzeichnisses eindeutig sein.

    > [!NOTE]
    > Wenn doppelte Werte vorhanden sind, wird der erste Benutzer mit dem Wert synchronisiert. Nachfolgende Benutzer werden nicht in Microsoft 365. Sie müssen entweder den Wert in Microsoft 365 oder beide Werte in AD DS ändern, damit beide Benutzer in der Microsoft 365.

- **mailNickname** (Exchange Alias)

  - Der Attributwert kann nicht mit einem Zeitraum (.) beginnen.
  - Der Attributwert muss innerhalb des Verzeichnisses eindeutig sein.

    > [!NOTE]
    > Unterstriche ("_") im synchronisierten Namen gibt an, dass der ursprüngliche Wert dieses Attributs ungültige Zeichen enthält. Weitere Informationen zu diesem Attribut finden Sie unter [Exchange Aliasattribut](/powershell/module/exchange/set-mailbox).
    >

- **proxyAddresses**

  - Attribut mit mehreren Wert
  - Maximale Anzahl von Zeichen pro Wert: 256
  - Der Attributwert darf kein Leerzeichen enthalten.
  - Der Attributwert muss innerhalb des Verzeichnisses eindeutig sein.
  - Ungültige Zeichen: \< \> ( ) ; , [ ] "

    Beachten Sie, dass die ungültigen Zeichen auf die Zeichen angewendet werden, die dem Typtrennzeichen und ":"folgen, so dass SMTP:User@contso.com zulässig ist, SMTP:user:M@contoso.com nicht.

    > [!IMPORTANT]
    > Alle SMTP-Adressen (Simple Mail Transport Protocol) sollten den E-Mail-Messagingstandards entsprechen. Entfernen Sie doppelte oder unerwünschte Adressen, falls vorhanden.

- **sAMAccountName**

  - Maximale Anzahl der Zeichen: 20
  - Der Attributwert muss innerhalb des Verzeichnisses eindeutig sein.
  - Ungültige Zeichen: [ \ " | , / : \< \> + = ; ? \* ']
  - Wenn ein Benutzer über ein ungültiges **sAMAccountName-Attribut** verfügt, aber über ein gültiges **userPrincipalName-Attribut** verfügt, wird das Benutzerkonto in Microsoft 365.
  - Wenn **sowohl sAMAccountName als** auch **userPrincipalName** ungültig sind, muss das AD DS **userPrincipalName-Attribut** aktualisiert werden.

- **sn** (Nachname)

  - Wenn das Attribut im Benutzerobjekt vorhanden ist, wird es mit Microsoft 365 synchronisiert, aber Microsoft 365 erfordert oder verwendet es nicht.

- **targetAddress**

    Es ist erforderlich, dass das **targetAddress-Attribut** (z. B. SMTP:tom@contoso.com), das für den Benutzer aufgefüllt wird, in der Microsoft 365 gal. In Szenarien für die Messagingmigration von Drittanbietern erfordert dies die Microsoft 365 Schemaerweiterung für AD DS. Die Microsoft 365 schemaerweiterung würde auch weitere nützliche Attribute hinzufügen, um Microsoft 365 Objekte zu verwalten, die mithilfe eines Verzeichnissynchronisierungstools aus AD DS aufgefüllt werden. Beispielsweise würde das **attribut msExchHideFromAddressLists** zum Verwalten ausgeblendeter Postfächer oder Verteilergruppen hinzugefügt.

  - Maximale Anzahl der Zeichen: 256
  - Der Attributwert darf kein Leerzeichen enthalten.
  - Der Attributwert muss innerhalb des Verzeichnisses eindeutig sein.
  - Ungültige Zeichen: \ \< \> ( ) ; , [ ] "
  - Alle SMTP-Adressen (Simple Mail Transport Protocol) sollten den E-Mail-Messagingstandards entsprechen.

- **userPrincipalName**

  - Das **userPrincipalName-Attribut** muss im Anmeldeformat im Internetformat vorliegen, in dem auf den Benutzernamen das At-Zeichen (@) und ein Domänenname folgt, z. B. user@contoso.com. Alle SMTP-Adressen (Simple Mail Transport Protocol) sollten den E-Mail-Messagingstandards entsprechen.
  - Die maximale Anzahl von Zeichen für das **userPrincipalName-Attribut** ist 113. Eine bestimmte Anzahl von Zeichen vor und nach dem At-Zeichen (@) ist wie folgt zulässig:
  - Maximale Anzahl von Zeichen für den Benutzernamen vor dem At-Zeichen (@): 64
  - Maximale Anzahl von Zeichen für den Domänennamen nach dem At-Zeichen (@): 48
  - Ungültige Zeichen: \ % &amp; \* + / = ? { } | \< \> ( ) ; : , [ ] "
  - Zulässige Zeichen: A – Z, a - z, 0 – 9, ' . - _ ! # ^ ~
  - Buchstaben mit diakritischen Markierungen, z. B. Umlaute, Akzente und Tildes, sind ungültige Zeichen.
  - Das @-Zeichen ist in jedem **userPrincipalName-Wert** erforderlich.
  - Das @-Zeichen darf nie das erste Zeichen in einem **userPrincipalName**-Wert sein.
  - Der Benutzername kann nicht mit einem Zeitraum (.), einem kaufmännischenSand ( ), einem Leerzeichen oder einem At-Zeichen &amp; (@) enden.
  - Der Benutzername darf keine Leerzeichen enthalten.
  - Routingfähige Domänen müssen verwendet werden. Lokale oder interne Domänen können beispielsweise nicht verwendet werden.
  - Unicode-Zeichen werden in Unterstriche umgewandelt.
  - **userPrincipalName** darf keine doppelten Werte im Verzeichnis enthalten.

## <a name="3-prepare-the-userprincipalname-attribute"></a>3. Vorbereiten des userPrincipalName-Attributs

Active Directory ist so konzipiert, dass die Endbenutzer in Ihrer Organisation sich mit **sAMAccountName** oder **userPrincipalName** bei Ihrem Verzeichnis anmelden können. Auf ähnliche Weise können sich Endbenutzer mit Microsoft 365 benutzerprinzipalnamen (User Principal Name, UPN) ihres Arbeits- oder Schulkontos anmelden. Die Verzeichnissynchronisierung versucht, neue Benutzer in Azure Active Directory mit demselben UPN zu erstellen, der sich in Ihrem AD DS befindet. Der UPN ist wie eine E-Mail-Adresse formatiert.

In Microsoft 365 ist der UPN das Standardattribut, das zum Generieren der E-Mail-Adresse verwendet wird. Es ist einfach, **userPrincipalName** (in AD DS und azure AD) und die primäre E-Mail-Adresse in **proxyAddresses** auf unterschiedliche Werte festgelegt zu erhalten. Wenn sie auf unterschiedliche Werte festgelegt sind, kann es für Administratoren und Endbenutzer zu Verwirrung kommen.

Es ist am besten, diese Attribute auszurichten, um Verwirrung zu vermeiden. Um die Anforderungen für einmaliges Anmelden mit Active Directory Federation Services (AD FS) 2.0 zu erfüllen, müssen Sie sicherstellen, dass die UPNs in Azure Active Directory und Ad DS übereinstimmen und einen gültigen Domänennamespace verwenden.

## <a name="4-add-an-alternative-upn-suffix-to-ad-ds"></a>4. Hinzufügen eines alternativen UPN-Suffixs zu AD DS

Möglicherweise müssen Sie ein alternatives UPN-Suffix hinzufügen, um die Unternehmensanmeldeinformationen des Benutzers der Umgebung Microsoft 365 zuzuordnen. Ein UPN-Suffix ist der Teil eines Benutzerprinzipalnamens, der rechts vom Zeichen @ steht. UPNs, die für einmaliges Anmelden verwendet werden, können Buchstaben, Zahlen, Punkte, Bindestriche und Unterstriche enthalten, aber keine anderen Zeichen.

Weitere Informationen zum Hinzufügen eines alternativen UPN-Suffixes zu Active Directory finden Sie unter [Prepare for directory synchronization]( https://go.microsoft.com/fwlink/p/?LinkId=525430).

## <a name="5-match-the-ad-ds-upn-with-the-microsoft-365-upn"></a>5. Übereinstimmung des AD DS UPN mit dem Microsoft 365 UPN

Wenn Sie die Verzeichnissynchronisierung bereits eingerichtet haben, ist der UPN des Benutzers für Microsoft 365 möglicherweise nicht mit dem ad DS UPN des Benutzers übereinstimmen, der in Ad DS definiert ist. Das kann vorkommen, wenn einem Benutzer vor der Überprüfung der Domäne schon eine Lizenz zugewiesen wurde. Um dies zu beheben, verwenden Sie [PowerShell,](https://go.microsoft.com/fwlink/p/?LinkId=396730) um doppelten UPN zu beheben, um den UPN des Benutzers zu aktualisieren, um sicherzustellen, dass der Microsoft 365-UPN dem Benutzernamen und der Domäne des Unternehmens entspricht. Wenn Sie den UPN im AD DS aktualisieren und ihn mit der Azure Active Directory-Identität synchronisieren möchten, müssen Sie die Lizenz des Benutzers in Microsoft 365 entfernen, bevor Sie die Änderungen in AD DS vornehmen.

Weitere Informationen finden Sie unter Vorbereiten einer nicht routingbaren Domäne (z. B. [lokale Domäne) für die Verzeichnissynchronisierung.](prepare-a-non-routable-domain-for-directory-synchronization.md)

## <a name="next-steps"></a>Nächste Schritte

Wenn Sie die Schritte 1 bis 5 oben ausgeführt haben, lesen Sie [Einrichten der Verzeichnissynchronisierung](set-up-directory-synchronization.md).
