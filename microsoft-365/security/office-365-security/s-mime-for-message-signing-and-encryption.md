---
title: S/MIME für die Verschlüsselung in Exchange Online-Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 887c710b-0ec6-4ff0-8065-5f05f74afef3
description: Administratoren können sich über die Verwendung von S/MIME (Secure/Multipurpose Internet Mail Extensions) in Exchange Online informieren, um e-Mails zu verschlüsseln und Digital zu signieren.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 01de52bb1d8e946ead0d8b39e34b13e34741259e
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/06/2021
ms.locfileid: "49760554"
---
# <a name="smime-for-message-signing-and-encryption-in-exchange-online"></a>S/MIME für die Nachrichtensignierung und-Verschlüsselung in Exchange Online

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


S/MIME (Secure/Multipurpose Internet Mail Extensions) ist eine allgemein akzeptierte Methode (oder genauer gesagt ein Protokoll) zum Senden von digital signierten und verschlüsselten Nachrichten. S/MIME ermöglicht Ihnen das Verschlüsseln und digitale Signieren von E-Mails. Wenn Sie S/MIME mit einer e-Mail-Nachricht verwenden, hilft es den Personen, die diese Nachricht erhalten, sicherzustellen, dass das, was Sie in Ihrem Posteingang sehen, die exakte Nachricht ist, die mit dem Absender gestartet wurde. Außerdem können Benutzer, die Nachrichten empfangen, sicher sein, dass die Nachricht vom jeweiligen Absender stammt und nicht von einer Person, die vorgibt, der Absender zu sein. Dafür bietet S/MIME kryptografische Sicherheitsdienste, wie Authentifizierung, Nachrichtenintegrität und Ursprungszulassung (anhand von digitalen Signaturen). Es hilft auch, die Datenschutz-und Datensicherheit (mithilfe von Verschlüsselung) für elektronisches Messaging zu verbessern. Genauere Hintergrundinformationen zur Geschichte und Architektur von S/MIME im Kontext von E-Mails finden Sie unter [Informationen zu S/MIME](https://docs.microsoft.com/previous-versions/tn-archive/aa995740(v=exchg.65)).

Als Exchange Online Administrator können Sie die S/MIME-basierte Sicherheit für die Postfächer in Ihrer Organisation aktivieren. Verwenden Sie die Anleitungen in den hier verknüpften Themen zusammen mit Exchange Online PowerShell, um S/MIME einzurichten. Um S/MIME in unterstützten e-Mail-Clients verwenden zu können, müssen die Benutzer in Ihrer Organisation über Zertifikate verfügen, die zu Signier-und Verschlüsselungs Zwecken ausgestellt wurden, sowie Daten, die in Ihrem lokalen Active Directory Domänendienst (AD DS) veröffentlicht wurden. Ihre AD DS müssen sich auf Computern an einem physischen Standort befinden, den Sie steuern, und nicht an einem Remotestandort oder Cloud-basierten Dienst irgendwo im Internet. Weitere Informationen zu AD DS finden Sie unter [Active Directory-Domänendienste Overview](https://docs.microsoft.com/windows-server/identity/ad-ds/get-started/virtual-dc/active-directory-domain-services-overview).

## <a name="supported-scenarios-and-technical-considerations"></a>Unterstützte Szenarien und technische Überlegungen

Sie können S/MIME für alle der folgenden Endpunkte einrichten:

- Outlook 2010 oder höher
- Outlook im Web (früher Outlook Web App)
- Exchange ActiveSync (EAS)

Die Schritte, die Sie zum Einrichten von S/MIME mit jedem dieser Endpunkte durchführen, unterscheiden sich geringfügig. Im Allgemeinen müssen Sie die folgenden Schritte ausführen:

1. Installieren Sie eine Windows-basierte Zertifizierungsstelle (Certification Authority, ca), und richten Sie eine Public Key-Infrastruktur zum Ausgeben von S/MIME-Zertifikaten ein. Zertifikate, die von Drittanbieter-Zertifikatanbietern ausgestellt werden, werden ebenfalls unterstützt. Details finden Sie unter [Active Directory-Zertifikatdienste: Übersicht](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh831740(v=ws.11)).

   **Hinweise**:

   - Von einer Drittanbieter-Zertifizierungsstelle ausgestellte Zertifikate haben den Vorteil, dass Sie von allen Clients und Geräten automatisch als vertrauenswürdig eingestuft werden. Zertifikate, die von einer internen, privaten Zertifizierungsstelle ausgestellt werden, werden nicht automatisch von Clients und Geräten als vertrauenswürdig eingestuft, und nicht alle Geräte (beispielsweise Telefone) können so konfiguriert werden, dass Sie privaten Zertifikaten vertrauen.

   - Verwenden Sie ein Zwischenzertifikat anstelle des Stammzertifikats, um Benutzern Zertifikate auszustellen. Auf diese Weise ist das Stammzertifikat immer noch intakt, wenn Sie Zertifikate widerrufen und erneut ausstellen müssen.

2. Veröffentlichen Sie das Benutzerzertifikat in einem lokalen AD DS-Konto in den Attributen **UserSMIMECertificate** und/oder **userCertificate** .

3. Synchronisieren Sie für Exchange Online Organisationen die Benutzerzertifikate von AD DS auf Azure Active Directory, indem Sie eine geeignete Version von Azure AD Connect verwenden. Diese Zertifikate werden dann von Azure Active Directory auf Exchange Online Verzeichnis synchronisiert und verwendet, wenn eine Nachricht an einen Empfänger verschlüsselt wird.

4. Richten Sie eine virtuelle Zertifikatauflistung zum Validieren von S/MIME ein. Diese Informationen verwendet Outlook im Web beim Validieren der Signatur einer E-Mail und stellt sicher, dass sie von einem vertrauenswürdigen Zertifikat signiert wurde.

5. Richten Sie den Outlook- oder EAS-Endpunkt für die Verwendung von S/MIME ein.

> [!NOTE]
> Das S/MIME-Steuerelement kann nicht in Outlook im Internet unter Mac, Ios, Android oder anderen nicht-Windows-Geräten installiert werden. Weitere Informationen finden Sie unter [Verschlüsseln von Nachrichten mithilfe von S/MIME in Outlook im Internet](https://support.microsoft.com/office/878c79fc-7088-4b39-966f-14512658f480).

## <a name="set-up-smime-with-outlook-on-the-web"></a>Einrichten von S/MIME mit Outlook im Web

Das Einrichten von S/MIME für Exchange Online mit Outlook im Internet umfasst die folgenden wichtigen Schritte:

1. [Konfigurieren von S/MIME-Einstellungen für Outlook im Web](configure-s-mime-settings-for-outlook-web-app.md)
2. [Einrichten einer virtuellen Zertifikatauflistung für die Überprüfung von S/MIME](set-up-virtual-certificate-collection-to-validate-s-mime.md)
3. [Synchronisierung von Benutzerzertifikaten nach Office 365 für S/MIME](sync-user-certificates-to-office-365-for-s-mime.md)

## <a name="related-message-encryption-technologies"></a>Zugehörige Nachrichten-Verschlüsselungstechnologien

Da die Nachrichtensicherheit wichtiger wird, müssen Administratoren die Grundsätze und Konzepte von Secure Messaging verstehen. Dieses Verständnis ist aufgrund der wachsenden Vielfalt von schutzbezogenen Technologien (einschließlich S/MIME), die verfügbar sind, besonders wichtig. Wenn Sie mehr über s/MIME und deren Funktionsweise im Kontext von e-Mails erfahren möchten, lesen Sie [Understanding s/MIME](https://docs.microsoft.com/previous-versions/tn-archive/aa995740(v=exchg.65)). Eine Vielzahl von Verschlüsselungstechnologien arbeiten zusammen, um den Schutz von Nachrichten im Rest und in der Übertragung bereitzustellen. S/MIME kann gleichzeitig mit den folgenden Technologien arbeiten, ist jedoch nicht von diesen abhängig:

- **Transport Layer Security (TLS)** verschlüsselt den Tunnel oder die Route zwischen e-Mail-Servern, um das Snooping und abhören zu verhindern.

- **Secure Sockets Layer (SSL)** verschlüsselt die Verbindung zwischen e-Mail-Clients und Microsoft 365-Servern.

- **BitLocker** verschlüsselt die Daten auf einer Festplatte in einem Rechenzentrum, sodass Sie nicht gelesen werden können, wenn jemand nicht autorisierten Zugriff erhält.

### <a name="smime-compared-with-office-365-message-encryption"></a>S/MIME im Vergleich zu Office 365 Nachrichtenverschlüsselung

Für S/MIME ist eine Infrastruktur für Zertifikate und Veröffentlichungen erforderlich, die häufig in B2B(Business-to-Business)- und B2C(Business-to-Customer)-Situationen verwendet wird. Der Benutzer steuert die kryptografischen Schlüssel in S/MIME und kann wählen, ob sie für jede versendete Nachricht verwendet werden sollen. E-Mail-Programme wie Outlook suchen nach dem Ort einer vertrauenswürdigen Stammzertifizierungsstelle, um eine digitale Signatur vorzunehmen und diese Signatur zu überprüfen. Office 365 Nachrichtenverschlüsselung ist ein richtlinienbasierter Verschlüsselungsdienst, der von einem Administrator und nicht von einem einzelnen Benutzer konfiguriert werden kann, um e-Mails zu verschlüsseln, die an Personen innerhalb oder außerhalb der Organisation gesendet werden. Es handelt sich um einen Onlinedienst, der auf Azure Rights Management (RMS) aufbaut und nicht auf einer Public Key-Infrastruktur basiert. Office 365 Nachrichtenverschlüsselung bietet auch zusätzliche Funktionen, beispielsweise die Möglichkeit, die e-Mail mit der Marke der Organisation anzupassen. Weitere Informationen zur Office 365 Nachrichtenverschlüsselung finden Sie unter [Encryption in Office 365](https://docs.microsoft.com/microsoft-365/compliance/encryption).

## <a name="more-information"></a>Weitere Informationen

[Outlook im Web](https://docs.microsoft.com/exchange/exchange-admin-center)

[Secure Mail (2000)](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc962043(v=technet.10))
