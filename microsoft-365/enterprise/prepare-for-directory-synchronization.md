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
ms.openlocfilehash: ee6cfe9adfe029e620d2465f08a3fbe1e9290503
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229767"
---
# <a name="prepare-for-directory-synchronization-to-microsoft-365"></a>Vorbereiten der Verzeichnissynchronisierung mit Microsoft 365

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Die Vorteile der Hybrididentitäts- und Verzeichnissynchronisierung In Ihrer Organisation sind:

- Reduzieren der Administrativen Programme in Ihrer Organisation
- Aktivieren des Szenarios für einmaliges Anmelden (Single Sign-On) optional
- Automatisieren von Kontoänderungen in Microsoft 365

Weitere Informationen zu den Vorteilen der Verzeichnissynchronisierung finden Sie unter [Hybrididentität mit Azure Active Directory (Azure AD)](/azure/active-directory/hybrid/whatis-hybrid-identity) und [Hybrididentität für Microsoft 365.](plan-for-directory-synchronization.md)

Die Verzeichnissynchronisierung erfordert jedoch Planung und Vorbereitung, um sicherzustellen, dass Ihre Active Directory Domain Services (AD DS) mit dem Azure AD-Mandanten Ihres Microsoft 365-Abonnements mit einem Minimum an Fehlern synchronisiert wird.

Führen Sie die folgenden Schritte aus, um die besten Ergebnisse zu erzielen.

## <a name="1-directory-cleanup-tasks"></a>1. Verzeichnisbereinigungsaufgaben

Bevor Sie Ihren AD DS mit Ihrem Azure AD-Mandanten synchronisieren, müssen Sie Ad DS bereinigen.

> [!IMPORTANT]
> Wenn Sie vor der Synchronisierung keine AD DS-Bereinigung durchführen, kann dies zu erheblichen negativen Auswirkungen auf den Bereitstellungsprozess führen. Es kann Tage oder sogar Wochen dauern, bis der Zyklus der Verzeichnissynchronisierung, die Identifizierung von Fehlern und die erneute Synchronisierung durchlaufen wird.

Führen Sie in Ihrem AD DS die folgenden Bereinigungsaufgaben für jedes Benutzerkonto aus, dem eine Microsoft 365-Lizenz zugewiesen wird:

1. Stellen Sie eine gültige und eindeutige E-Mail-Adresse im **proxyAddresses-Attribut** sicher.

2. Entfernen Sie alle doppelten Werte im **proxyAddresses -Attribut.**

3. Stellen Sie nach Möglichkeit einen gültigen und eindeutigen Wert für das **attribut userPrincipalName** im **Benutzerobjekt** des Benutzers sicher. Stellen Sie für eine optimale Synchronisierung sicher, dass der AD DS UPN dem Azure AD UPN entspricht. Wenn ein Benutzer keinen Wert für das **UserPrincipalName-Attribut** hat, muss das **Benutzerobjekt** einen gültigen und eindeutigen Wert für das **sAMAccountName-Attribut** enthalten. Entfernen Sie alle doppelten Werte im **userPrincipalName-Attribut.**

4. Um die globale Adressliste (GAL) optimal zu verwenden, stellen Sie sicher, dass die Informationen in den folgenden Attributen des AD DS-Benutzerkontos korrekt sind:

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

## <a name="2-directory-object-and-attribute-preparation"></a>2. Verzeichnisobjekt- und Attributvorbereitung

Eine erfolgreiche Verzeichnissynchronisierung zwischen AD DS und Microsoft 365 erfordert, dass Ihre AD DS-Attribute ordnungsgemäß vorbereitet sind. Sie müssen beispielsweise sicherstellen, dass bestimmte Zeichen nicht in bestimmten Attributen verwendet werden, die mit der Microsoft 365-Umgebung synchronisiert werden. Unerwartete Zeichen führen nicht dazu, dass die Verzeichnissynchronisierung fehlschlägt, aber möglicherweise wird eine Warnung zurückgegeben. Ungültige Zeichen führen dazu, dass die Verzeichnissynchronisierung fehlschlägt.

Die Verzeichnissynchronisierung schlägt auch fehl, wenn einige Ad DS-Benutzer über mindestens ein doppeltes Attribut verfügen. Jeder Benutzer muss über eindeutige Attribute verfügen.

Die Attribute, die Sie vorbereiten müssen, sind hier aufgeführt:

- **displayName**

  - Wenn das Attribut im Benutzerobjekt vorhanden ist, wird es mit Microsoft 365 synchronisiert.
  - Wenn dieses Attribut im Benutzerobjekt vorhanden ist, muss ein Wert dafür vorhanden sein. Das heißt, das Attribut darf nicht leer sein.
  - Maximale Anzahl der Zeichen: 256

- **givenName**

  - Wenn das Attribut im Benutzerobjekt vorhanden ist, wird es mit Microsoft 365 synchronisiert, Microsoft 365 es jedoch nicht benötigt oder verwendet.
  - Maximale Anzahl der Zeichen: 64

- **Mail**

  - Der Attributwert muss innerhalb des Verzeichnisses eindeutig sein.

    > [!NOTE]
    > Wenn doppelte Werte vorhanden sind, wird der erste Benutzer mit dem Wert synchronisiert. Nachfolgende Benutzer werden in Microsoft 365 nicht angezeigt. Sie müssen entweder den Wert in Microsoft 365 oder beide Werte in AD DS ändern, damit beide Benutzer in Microsoft 365 angezeigt werden.

- **mailNickname** (Exchange Alias)

  - Der Attributwert kann nicht mit einem Punkt (.) beginnen.
  - Der Attributwert muss innerhalb des Verzeichnisses eindeutig sein.

    > [!NOTE]
    > Unterstriche ("_") im synchronisierten Namen geben an, dass der ursprüngliche Wert dieses Attributs ungültige Zeichen enthält. Weitere Informationen zu diesem Attribut finden Sie unter [Exchange Aliasattribut.](/powershell/module/exchange/set-mailbox)
    >

- **proxyAddresses**

  - Attribut mit mehreren Werten
  - Maximale Anzahl von Zeichen pro Wert: 256
  - Der Attributwert darf kein Leerzeichen enthalten.
  - Der Attributwert muss innerhalb des Verzeichnisses eindeutig sein.
  - Ungültige Zeichen: \< \> ( ) ; , [ ] "

    Beachten Sie, dass die ungültigen Zeichen auf die Zeichen angewendet werden, die auf das Typtrennzeichen und ":" folgen, sodass SMTP:User@contso.com zulässig ist, SMTP:user:M@contoso.com jedoch nicht.

    > [!IMPORTANT]
    > Alle SMTP-Adressen (Simple Mail Transport Protocol) sollten den E-Mail-Nachrichtenstandards entsprechen. Entfernen Sie doppelte oder unerwünschte Adressen, falls vorhanden.

- **Samaccountname**

  - Maximale Anzahl der Zeichen: 20
  - Der Attributwert muss innerhalb des Verzeichnisses eindeutig sein.
  - Ungültige Zeichen: [ \ " | , / : \< \> + = ; ? \* ']
  - Wenn ein Benutzer über ein ungültiges **sAMAccountName-Attribut** verfügt, aber über ein gültiges **userPrincipalName-Attribut** verfügt, wird das Benutzerkonto in Microsoft 365 erstellt.
  - Wenn **sAMAccountName** und **userPrincipalName** ungültig sind, muss das AD DS **userPrincipalName-Attribut** aktualisiert werden.

- **sn** (Nachname)

  - Wenn das Attribut im Benutzerobjekt vorhanden ist, wird es mit Microsoft 365 synchronisiert, Microsoft 365 es jedoch nicht benötigt oder verwendet.

- **Targetaddress**

    Es ist erforderlich, dass das **targetAddress-Attribut** (z. B. SMTP:tom@contoso.com), das für den Benutzer ausgefüllt ist, in der Microsoft 365 GAL angezeigt werden muss. In Szenarien für die Messagingmigration von Drittanbietern würde dies die Microsoft 365 Schemaerweiterung für AD DS erfordern. Die Microsoft 365 Schemaerweiterung würde auch weitere nützliche Attribute hinzufügen, um Microsoft 365 Objekte zu verwalten, die mithilfe eines Verzeichnissynchronisierungstools aus AD DS aufgefüllt werden. Beispielsweise würde das **MsExchHideFromAddressLists-Attribut** zum Verwalten ausgeblendeter Postfächer oder Verteilergruppen hinzugefügt.

  - Maximale Anzahl der Zeichen: 256
  - Der Attributwert darf kein Leerzeichen enthalten.
  - Der Attributwert muss innerhalb des Verzeichnisses eindeutig sein.
  - Ungültige Zeichen: \ \< \> ( ) ; , [ ] "
  - Alle SMTP-Adressen (Simple Mail Transport Protocol) sollten den E-Mail-Nachrichtenstandards entsprechen.

- **userPrincipalName**

  - Das **UserPrincipalName-Attribut** muss im Anmeldeformat im Internetformat vorliegen, wobei auf den Benutzernamen das At-Zeichen (@) und ein Domänenname folgt, z. B. user@contoso.com. Alle SMTP-Adressen (Simple Mail Transport Protocol) sollten den E-Mail-Nachrichtenstandards entsprechen.
  - Die maximale Anzahl von Zeichen für das **userPrincipalName-Attribut** ist 113. Eine bestimmte Anzahl von Zeichen ist vor und nach dem At-Zeichen (@) wie folgt zulässig:
  - Maximale Anzahl von Zeichen für den Benutzernamen, der sich vor dem At-Zeichen (@) befindet: 64
  - Maximale Anzahl von Zeichen für den Domänennamen nach dem At-Zeichen (@): 48
  - Ungültige Zeichen: \ % &amp; \* + / = ? { } | \< \> ( ) ; : , [ ] "
  - Zulässige Zeichen: A – Z, a - z, 0 – 9, ' . - _ ! # ^ ~
  - Buchstaben mit diakritischen Zeichen, z. B. Umlaute, Akzente und Tilden, sind ungültige Zeichen.
  - Das @-Zeichen ist in jedem **userPrincipalName-Wert** erforderlich.
  - Das @-Zeichen darf nie das erste Zeichen in einem **userPrincipalName**-Wert sein.
  - Der Benutzername kann nicht mit einem Punkt (.), einem kaufmännischen Und-Zeichen ( &amp; ), einem Leerzeichen oder einem At-Zeichen (@) enden.
  - Der Benutzername darf keine Leerzeichen enthalten.
  - Routingfähige Domänen müssen verwendet werden. Beispielsweise können lokale oder interne Domänen nicht verwendet werden.
  - Unicode-Zeichen werden in Unterstriche umgewandelt.
  - **userPrincipalName** darf keine doppelten Werte im Verzeichnis enthalten.

## <a name="3-prepare-the-userprincipalname-attribute"></a>3. Vorbereiten des userPrincipalName-Attributs

Active Directory ist so konzipiert, dass endbenutzer in Ihrer Organisation sich mithilfe von **sAMAccountName** oder **userPrincipalName** bei Ihrem Verzeichnis anmelden können. Auf ähnliche Weise können sich Endbenutzer mithilfe des Benutzerprinzipalnamens (UPN) ihres Geschäfts-, Schul- oder Unikontos bei Microsoft 365 anmelden. Die Verzeichnissynchronisierung versucht, neue Benutzer in Azure Active Directory mit demselben UPN zu erstellen, der sich in Ihrem AD DS befindet. Der UPN ist wie eine E-Mail-Adresse formatiert.

In Microsoft 365 ist der UPN das Standardattribut, das zum Generieren der E-Mail-Adresse verwendet wird. Es ist einfach, **userPrincipalName** (in AD DS und in Azure AD) und die primäre E-Mail-Adresse in **proxyAddresses** abzurufen, die auf unterschiedliche Werte festgelegt sind. Wenn sie auf unterschiedliche Werte festgelegt sind, kann es für Administratoren und Endbenutzer verwirrungen.

Es empfiehlt sich, diese Attribute auszurichten, um Verwirrung zu vermeiden. Um die Anforderungen des einmaligen Anmeldens mit Active Directory-Verbunddiensten (AD FS) 2.0 zu erfüllen, müssen Sie sicherstellen, dass die UPNs in Azure Active Directory und Ihre AD DS übereinstimmen und einen gültigen Domänennamespace verwenden.

## <a name="4-add-an-alternative-upn-suffix-to-ad-ds"></a>4. Hinzufügen eines alternativen UPN-Suffix zu AD DS

Möglicherweise müssen Sie ein alternatives UPN-Suffix hinzufügen, um die Unternehmensanmeldeinformationen des Benutzers der Microsoft 365 Umgebung zuzuordnen. Ein UPN-Suffix ist der Teil eines Benutzerprinzipalnamens, der rechts vom Zeichen @ steht. UPNs, die für einmaliges Anmelden verwendet werden, können Buchstaben, Zahlen, Punkte, Bindestriche und Unterstriche enthalten, aber keine anderen Zeichen.

Weitere Informationen zum Hinzufügen eines alternativen UPN-Suffix zu Active Directory finden Sie unter [Vorbereiten der Verzeichnissynchronisierung.](https://go.microsoft.com/fwlink/p/?LinkId=525430)

## <a name="5-match-the-ad-ds-upn-with-the-microsoft-365-upn"></a>5. Abgleichen des AD DS UPN mit dem Microsoft 365 UPN

Wenn Sie die Verzeichnissynchronisierung bereits eingerichtet haben, stimmt der UPN des Benutzers für Microsoft 365 möglicherweise nicht mit dem AD DS-UPN des Benutzers überein, der in Ihrem AD DS definiert ist. Das kann vorkommen, wenn einem Benutzer vor der Überprüfung der Domäne schon eine Lizenz zugewiesen wurde. Um dies zu beheben, verwenden Sie [PowerShell, um den doppelten UPN zu beheben,](https://go.microsoft.com/fwlink/p/?LinkId=396730) um den UPN des Benutzers zu aktualisieren, um sicherzustellen, dass der Microsoft 365 UPN dem Benutzernamen und der Domäne des Unternehmens entspricht. Wenn Sie den UPN im AD DS aktualisieren und ihn mit der Azure Active Directory Identität synchronisieren möchten, müssen Sie die Lizenz des Benutzers in Microsoft 365 entfernen, bevor Sie die Änderungen in AD DS vornehmen.

Weitere Informationen finden Sie unter [Vorbereiten einer nicht routingfähigen Domäne (z. B. .local domain) für die Verzeichnissynchronisierung.](prepare-a-non-routable-domain-for-directory-synchronization.md)

## <a name="next-steps"></a>Nächste Schritte

Wenn Sie die Schritte 1 bis 5 oben ausgeführt haben, finden Sie weitere Informationen unter Einrichten der [Verzeichnissynchronisierung.](set-up-directory-synchronization.md)
