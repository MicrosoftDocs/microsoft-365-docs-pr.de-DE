---
title: S/MIME für die Verschlüsselung in Exchange Online – Office 365
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
description: Administratoren können sich über die Verwendung von S/MIME (Secure/Multipurpose Internet Mail Extensions) in Exchange Online informieren, um E-Mails zu verschlüsseln und digital zu signieren.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 35266b4ceefe161b907ddbc955fd234b716792a6
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288573"
---
# <a name="smime-for-message-signing-and-encryption-in-exchange-online"></a>S/MIME für die Nachrichtensignierung und -verschlüsselung in Exchange Online

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


S/MIME (Secure/Multipurpose Internet Mail Extensions) ist eine allgemein akzeptierte Methode (oder genauer gesagt ein Protokoll) zum Senden digital signierter und verschlüsselter Nachrichten. S/MIME ermöglicht Ihnen das Verschlüsseln und digitale Signieren von E-Mails. Wenn Sie S/MIME mit einer E-Mail-Nachricht verwenden, hilft es den Personen, die diese Nachricht erhalten, sicher zu sein, dass das, was sie in ihrem Posteingang sehen, genau die Nachricht ist, die mit dem Absender begonnen hat. Es hilft auch Personen, die Nachrichten empfangen, sicher zu sein, dass die Nachricht vom bestimmten Absender stammt und nicht von jemandem, der vorgibt, der Absender zu sein. Dafür bietet S/MIME kryptografische Sicherheitsdienste, wie Authentifizierung, Nachrichtenintegrität und Ursprungszulassung (anhand von digitalen Signaturen). Es trägt außerdem zur Verbesserung des Datenschutzes und der Datensicherheit (mithilfe der Verschlüsselung) für elektronische Nachrichten bei. Genauere Hintergrundinformationen zur Geschichte und Architektur von S/MIME im Kontext von E-Mails finden Sie unter [Informationen zu S/MIME](https://docs.microsoft.com/previous-versions/tn-archive/aa995740(v=exchg.65)).

Als Exchange Online-Administrator können Sie S/MIME-basierte Sicherheit für die Postfächer in Ihrer Organisation aktivieren. Verwenden Sie zum Einrichten von S/MIME die Anleitungen in den hier mit Exchange Online PowerShell verknüpften Themen. Um S/MIME in unterstützten E-Mail-Clients verwenden zu können, müssen die Benutzer in Ihrer Organisation über Zertifikate verfügen, die zu Signierungs- und Verschlüsselungszwecken ausgestellt wurden, sowie Daten, die in Ihrem lokalen Active Directory Domain Service (AD DS) veröffentlicht wurden. Ihr AD DS muss sich auf Computern an einem physischen Standort befinden, den Sie steuern, und nicht an einer Remoteeinrichtung oder einem cloudbasierten Dienst im Internet. Weitere Informationen zu AD DS finden Sie unter [Active Directory Domain Services Overview](https://docs.microsoft.com/windows-server/identity/ad-ds/get-started/virtual-dc/active-directory-domain-services-overview).

## <a name="supported-scenarios-and-technical-considerations"></a>Unterstützte Szenarien und technische Überlegungen

Sie können S/MIME für alle der folgenden Endpunkte einrichten:

- Outlook 2010 oder höher
- Outlook im Web (früher Outlook Web App)
- Exchange ActiveSync (EAS)

Die Schritte, die Sie zum Einrichten von S/MIME für jeden dieser Endpunkte ausführen, unterscheiden sich geringfügig. Im Allgemeinen müssen Sie die folgenden Schritte ausführen:

1. Installieren Sie eine Windows-basierte Zertifizierungsstelle ,und richten Sie eine Public Key-Infrastruktur ein, um S/MIME-Zertifikate auszustellen. Zertifikate, die von Zertifikatanbietern von Drittanbietern ausgestellt wurden, werden ebenfalls unterstützt. Details finden Sie unter [Active Directory-Zertifikatdienste: Übersicht](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh831740(v=ws.11)).

   **Hinweise**:

   - Zertifikate, die von einer Zertifizierungsstelle eines Drittanbieters ausgestellt wurden, haben den Vorteil, dass sie von allen Clients und Geräten automatisch als vertrauenswürdig eingestuft werden. Zertifikate, die von einer internen, privaten Zertifizierungsstelle ausgestellt werden, werden nicht automatisch von Clients und Geräten als vertrauenswürdig eingestuft, und nicht alle Geräte (z. B. Telefone) können so konfiguriert werden, dass sie privaten Zertifikaten vertrauen.

   - Erwägen Sie die Verwendung eines Zwischenzertifikats anstelle des Stammzertifikats, um Zertifikate für Benutzer auszustellen. Auf diese Weise bleibt das Stammzertifikat erhalten, wenn Sie Zertifikate widerrufen und erneut ausstellen müssen.

2. Veröffentlichen Sie das Benutzerzertifikat in einem lokalen AD DS-Konto in den **Attributen "UserSMIMECertificate"** und/oder **"UserCertificate".**

3. Synchronisieren Sie für Exchange Online-Organisationen die Benutzerzertifikate aus AD DS mit Azure Active Directory, indem Sie eine entsprechende Version von Azure AD Connect verwenden. Diese Zertifikate werden dann aus Azure Active Directory mit dem Exchange Online-Verzeichnis synchronisiert und beim Verschlüsseln einer Nachricht mit einem Empfänger verwendet.

4. Richten Sie eine virtuelle Zertifikatauflistung zum Validieren von S/MIME ein. Diese Informationen verwendet Outlook im Web beim Validieren der Signatur einer E-Mail und stellt sicher, dass sie von einem vertrauenswürdigen Zertifikat signiert wurde.

5. Richten Sie den Outlook- oder EAS-Endpunkt für die Verwendung von S/MIME ein.

> [!NOTE]
> Sie können das S/MIME-Steuerelement in Outlook im Web nicht auf Mac-, iOS-, Android- oder anderen Nicht-Windows-Geräten installieren. Weitere Informationen finden Sie unter Verschlüsseln [von Nachrichten mithilfe von S/MIME in Outlook im Web.](https://support.microsoft.com/office/878c79fc-7088-4b39-966f-14512658f480)

## <a name="set-up-smime-with-outlook-on-the-web"></a>Einrichten von S/MIME mit Outlook im Web

Das Einrichten von S/MIME für Exchange Online mit Outlook im Web umfasst die folgenden wichtigen Schritte:

1. [Konfigurieren von S/MIME-Einstellungen für Outlook im Web](configure-s-mime-settings-for-outlook-web-app.md)
2. [Einrichten einer virtuellen Zertifikatauflistung für die Überprüfung von S/MIME](set-up-virtual-certificate-collection-to-validate-s-mime.md)
3. [Synchronisierung von Benutzerzertifikaten nach Office 365 für S/MIME](sync-user-certificates-to-office-365-for-s-mime.md)

## <a name="related-message-encryption-technologies"></a>Zugehörige Nachrichten-Verschlüsselungstechnologien

Mit zunehmender Bedeutung der Nachrichtensicherheit müssen Administratoren die Prinzipien und Konzepte von sicherem Messaging verstehen. Dieses Verständnis ist besonders wichtig aufgrund der wachsenden Vielfalt an schutzbezogenen Technologien (einschließlich S/MIME), die verfügbar sind. Weitere Informationen zu S/MIME und deren Funktionsweise im Kontext von E-Mails finden Sie unter [Understanding S/MIME](https://docs.microsoft.com/previous-versions/tn-archive/aa995740(v=exchg.65)). Eine Vielzahl von Verschlüsselungstechnologien arbeiten zusammen, um den Schutz von Ruhe- und Übertragungsnachrichten zu gewährleisten. S/MIME kann gleichzeitig mit den folgenden Technologien verwendet werden, ist jedoch nicht von ihnen abhängig:

- **TLS (Transport Layer Security)** verschlüsselt den Tunnel oder die Route zwischen E-Mail-Servern, um Snooping und Lauschangriffe zu verhindern.

- **SSL (Secure Sockets Layer)** verschlüsselt die Verbindung zwischen E-Mail-Clients und Microsoft 365-Servern.

- **BitLocker** verschlüsselt die Daten auf einer Festplatte in einem Datencenter, sodass jemand, der nicht autorisierten Zugriff erhält, diese nicht lesen kann.

### <a name="smime-compared-with-office-365-message-encryption"></a>S/MIME im Vergleich zur Office 365-Nachrichtenverschlüsselung

Für S/MIME ist eine Infrastruktur für Zertifikate und Veröffentlichungen erforderlich, die häufig in B2B(Business-to-Business)- und B2C(Business-to-Customer)-Situationen verwendet wird. Der Benutzer steuert die kryptografischen Schlüssel in S/MIME und kann wählen, ob sie für jede versendete Nachricht verwendet werden sollen. E-Mail-Programme wie Outlook suchen nach dem Ort einer vertrauenswürdigen Stammzertifizierungsstelle, um eine digitale Signatur vorzunehmen und diese Signatur zu überprüfen. Die Office 365-Nachrichtenverschlüsselung ist ein richtlinienbasierter Verschlüsselungsdienst, der von einem Administrator und nicht von einem einzelnen Benutzer zum Verschlüsseln von E-Mails konfiguriert werden kann, die an personen innerhalb oder außerhalb der Organisation gesendet werden. Es ist ein Onlinedienst, der auf Azure Rights Management (RMS) aufgebaut ist und nicht auf einer Public -Key-Infrastruktur angewiesen ist. Die Office 365-Nachrichtenverschlüsselung bietet auch zusätzliche Funktionen, z. B. die Möglichkeit, die E-Mails mit der Marke der Organisation anzupassen. Weitere Informationen zur Office 365-Nachrichtenverschlüsselung finden Sie unter ["Verschlüsselung in Office 365".](../../compliance/encryption.md)

## <a name="more-information"></a>Weitere Informationen

[Outlook im Web](https://docs.microsoft.com/exchange/exchange-admin-center)

[Secure Mail (2000)](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc962043(v=technet.10))
