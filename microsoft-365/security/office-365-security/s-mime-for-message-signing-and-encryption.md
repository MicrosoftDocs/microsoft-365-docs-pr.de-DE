---
title: S/MIME für die Verschlüsselung in Exchange Online - Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 887c710b-0ec6-4ff0-8065-5f05f74afef3
description: Administratoren können mehr über die Verwendung von S/MIME (Secure/Multipurpose Internet Mail Extensions) in Exchange Online E-Mails verschlüsseln und digital signieren.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d189bf7f52dd6f9fb11dc360c17d5fe15729c9fa
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205687"
---
# <a name="smime-for-message-signing-and-encryption-in-exchange-online"></a>S/MIME für die Nachrichtensignatur und -verschlüsselung in Exchange Online

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


S/MIME (Secure/Multipurpose Internet Mail Extensions) ist eine allgemein akzeptierte Methode (oder genauer gesagt ein Protokoll) zum Senden von digital signierten und verschlüsselten Nachrichten. S/MIME ermöglicht Ihnen das Verschlüsseln und digitale Signieren von E-Mails. Wenn Sie S/MIME mit einer E-Mail-Nachricht verwenden, hilft es den Personen, die diese Nachricht empfangen, sicher zu sein, dass das, was sie in ihrem Posteingang sehen, die genaue Nachricht ist, die mit dem Absender begonnen hat. Es hilft auch Personen, die Nachrichten empfangen, sicher zu sein, dass die Nachricht vom bestimmten Absender stammt und nicht von jemandem, der vorgibt, der Absender zu sein. Dafür bietet S/MIME kryptografische Sicherheitsdienste, wie Authentifizierung, Nachrichtenintegrität und Ursprungszulassung (anhand von digitalen Signaturen). Darüber hinaus trägt sie dazu bei, den Datenschutz und die Datensicherheit (mithilfe von Verschlüsselung) für elektronische Nachrichten zu verbessern. Genauere Hintergrundinformationen zur Geschichte und Architektur von S/MIME im Kontext von E-Mails finden Sie unter [Informationen zu S/MIME](/previous-versions/tn-archive/aa995740(v=exchg.65)).

Als Exchange Online können Sie die S/MIME-basierte Sicherheit für die Postfächer in Ihrer Organisation aktivieren. Verwenden Sie die Anleitungen in den hier verknüpften Themen und Exchange Online PowerShell zum Einrichten von S/MIME. Für die Verwendung von S/MIME in unterstützten E-Mail-Clients müssen die Benutzer in Ihrer Organisation über Zertifikate verfügen, die zu Signatur- und Verschlüsselungszwecken ausgestellt wurden, sowie Daten, die in Ihrem lokalen Active Directory Domain Service (AD DS) veröffentlicht werden. Ihr AD DS muss sich auf Computern an einem physischen Standort befinden, den Sie steuern, und nicht an einer Remoteeinrichtung oder einem cloudbasierten Dienst irgendwo im Internet. Weitere Informationen zu AD DS finden Sie unter [Active Directory Domain Services Overview](/windows-server/identity/ad-ds/get-started/virtual-dc/active-directory-domain-services-overview).

## <a name="supported-scenarios-and-technical-considerations"></a>Unterstützte Szenarien und technische Überlegungen

Sie können S/MIME für alle der folgenden Endpunkte einrichten:

- Outlook 2010 oder höher
- Outlook im Web (früher Outlook Web App)
- Exchange ActiveSync (EAS)

Die Schritte, die Sie zum Einrichten von S/MIME mit jedem dieser Endpunkte ausführen, unterscheiden sich geringfügig. Im Allgemeinen müssen Sie die folgenden Schritte ausführen:

1. Installieren Sie Windows zertifizierungsstelle (Ca) und richten Sie eine Infrastruktur für öffentliche Schlüssel ein, um S/MIME-Zertifikate auszustellen. Zertifikate von Zertifikatanbietern von Drittanbietern werden ebenfalls unterstützt. Details finden Sie unter [Active Directory-Zertifikatdienste: Übersicht](/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh831740(v=ws.11)).

   **Hinweise**:

   - Von einer Zertifizierungsstelle eines Drittanbieters ausgestellte Zertifikate haben den Vorteil, dass sie von allen Clients und Geräten automatisch als vertrauenswürdig eingestuft werden. Zertifikate, die von einer internen, privaten Zertifizierungsstelle ausgestellt werden, werden nicht automatisch von Clients und Geräten als vertrauenswürdig eingestuft, und nicht alle Geräte (z. B. Telefone) können so konfiguriert werden, dass privaten Zertifikaten vertraut wird.

   - Erwägen Sie die Verwendung eines Zwischenzertifikats anstelle des Stammzertifikats zum Ausstellen von Zertifikaten für Benutzer. Auf diese Weise ist das Stammzertifikat weiterhin intakt, wenn Sie Zertifikate widerrufen und erneut ausstellen müssen.

2. Veröffentlichen Sie das Benutzerzertifikat in einem lokalen AD DS-Konto in den **Attributen UserSMIMECertificate** und/oder **UserCertificate.**

3. Synchronisieren Exchange Online Organisationen die Benutzerzertifikate von AD DS mit Azure Active Directory mithilfe einer geeigneten Version von Azure AD Verbinden. Diese Zertifikate werden dann von Azure Active Directory zu Exchange Online synchronisiert und beim Verschlüsseln einer Nachricht an einen Empfänger verwendet.

4. Richten Sie eine virtuelle Zertifikatauflistung zum Validieren von S/MIME ein. Diese Informationen verwendet Outlook im Web beim Validieren der Signatur einer E-Mail und stellt sicher, dass sie von einem vertrauenswürdigen Zertifikat signiert wurde.

5. Richten Sie den Outlook- oder EAS-Endpunkt für die Verwendung von S/MIME ein.

> [!NOTE]
> Sie können das S/MIME-Steuerelement nicht im Outlook auf Mac, iOS, Android oder anderen nicht Windows installieren. Weitere Informationen finden Sie unter [Verschlüsseln von Nachrichten mithilfe von S/MIME in Outlook im Web](https://support.microsoft.com/office/878c79fc-7088-4b39-966f-14512658f480).

## <a name="set-up-smime-with-outlook-on-the-web"></a>Einrichten von S/MIME mit Outlook im Web

Das Einrichten von S/MIME für Exchange Online mit Outlook im Web umfasst die folgenden wichtigen Schritte:

1. [Konfigurieren von S/MIME-Einstellungen für Outlook im Web](configure-s-mime-settings-for-outlook-web-app.md)
2. [Einrichten einer virtuellen Zertifikatauflistung für die Überprüfung von S/MIME](set-up-virtual-certificate-collection-to-validate-s-mime.md)
3. [Synchronisierung von Benutzerzertifikaten nach Office 365 für S/MIME](sync-user-certificates-to-office-365-for-s-mime.md)

## <a name="related-message-encryption-technologies"></a>Zugehörige Nachrichten-Verschlüsselungstechnologien

Wenn die Nachrichtensicherheit wichtiger wird, müssen Administratoren die Prinzipien und Konzepte von sicherem Messaging verstehen. Dieses Verständnis ist besonders wichtig, da immer mehr schutzbezogene Technologien (einschließlich S/MIME) verfügbar sind. Weitere Informationen zu S/MIME und deren Funktionsweise im Kontext von E-Mails finden Sie unter [Understanding S/MIME](/previous-versions/tn-archive/aa995740(v=exchg.65)). Eine Vielzahl von Verschlüsselungstechnologien arbeiten zusammen, um Schutz für Ruhe- und Transitnachrichten zu bieten. S/MIME kann gleichzeitig mit den folgenden Technologien verwendet werden, ist jedoch nicht von ihnen abhängig:

- **Transport Layer Security (TLS)** verschlüsselt den Tunnel oder die Route zwischen E-Mail-Servern, um Schnüffeln und Lauschangriffe zu verhindern.

- **Ssl (Secure Sockets Layer)** verschlüsselt die Verbindung zwischen E-Mail-Clients und Microsoft 365 Server.

- **BitLocker** verschlüsselt die Daten auf einer Festplatte in einem Datencenter, sodass jemand, der nicht autorisierten Zugriff erhält, diese nicht lesen kann.

### <a name="smime-compared-with-office-365-message-encryption"></a>S/MIME im Vergleich zu Office 365-Nachrichtenverschlüsselung

Für S/MIME ist eine Infrastruktur für Zertifikate und Veröffentlichungen erforderlich, die häufig in B2B(Business-to-Business)- und B2C(Business-to-Customer)-Situationen verwendet wird. Der Benutzer steuert die kryptografischen Schlüssel in S/MIME und kann wählen, ob sie für jede versendete Nachricht verwendet werden sollen. E-Mail-Programme wie Outlook suchen nach dem Ort einer vertrauenswürdigen Stammzertifizierungsstelle, um eine digitale Signatur vorzunehmen und diese Signatur zu überprüfen. Office 365-Nachrichtenverschlüsselung ist ein richtlinienbasierter Verschlüsselungsdienst, der von einem Administrator und nicht von einem einzelnen Benutzer zum Verschlüsseln von E-Mails konfiguriert werden kann, die an personen innerhalb oder außerhalb der Organisation gesendet werden. Es ist ein Onlinedienst, der auf Azure Rights Management (RMS) baut und nicht auf einer Infrastruktur für öffentliche Schlüssel angewiesen ist. Office 365-Nachrichtenverschlüsselung bietet auch zusätzliche Funktionen, z. B. die Möglichkeit, die E-Mails mit der Marke der Organisation anzupassen. Weitere Informationen zu Office 365-Nachrichtenverschlüsselung finden Sie unter [Verschlüsselung in Office 365](../../compliance/encryption.md).

## <a name="more-information"></a>Weitere Informationen

[Outlook im Web](/exchange/exchange-admin-center)

[Secure Mail (2000)](/previous-versions/windows/it-pro/windows-2000-server/cc962043(v=technet.10))