---
title: Nachrichtenverschlüsselung
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 02/07/2020
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.assetid: f87cb016-7876-4317-ae3c-9169b311ff8a
ms.custom:
- seo-marvel-apr2020
description: Erfahren Sie, wie Sie verschlüsselte E-Mail-Nachrichten zwischen Personen innerhalb und außerhalb Ihrer Organisation senden und empfangen.
ms.openlocfilehash: 504fa9918636cd596cde0d242083ccb7b9817e69
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927713"
---
# <a name="message-encryption"></a>Nachrichtenverschlüsselung

Häufig werden vertrauliche Informationen wie Finanzdaten, Verträge, vertrauliche Produktinformationen, Verkaufsberichte und -prognosen oder Patienten-, Kunden- und Mitarbeiterdaten per E-Mail ausgetauscht. Postfächer können daher zu Repositories großer Mengen potenziell vertraulicher Informationen werden, und Informationsverluste können eine ernstzunehmende Bedrohung für die Organisation darstellen.

Mit der Office 365-Nachrichtenverschlüsselung kann Ihre Organisation verschlüsselte E-Mail-Nachrichten von bzw. zwischen Personen innerhalb und außerhalb Ihrer Organisation senden und empfangen. Die Office 365-Nachrichtenverschlüsselung funktioniert mit Outlook.com, Yahoo!, Gmail und anderen E-Mail-Diensten. Die E-Mail-Nachrichtenverschlüsselung sorgt dafür, dass nur vorgesehene Empfänger verschlüsselte Nachrichten ansehen können.

## <a name="how-office-365-message-encryption-works"></a>Funktionsweise der Office 365-Nachrichtenverschlüsselung

Der Rest dieses Artikels bezieht sich auf die neuen OME-Funktionen.

Die Office 365-Nachrichtenverschlüsselung ist ein Onlinedienst, der auf Microsoft Azure Rights Management (Azure RMS) baut, das Teil von Azure Information Protection ist. Dieser Dienst umfasst Verschlüsselungs-, Identitäts- und Autorisierungsrichtlinien, um Ihre E-Mails zu schützen. Sie können Nachrichten mithilfe von Vorlagen für die Rechteverwaltung, der [Option Nicht](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)weiterleiten und der Option nur verschlüsseln [.](/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)

Benutzer können dann E-Mail-Nachrichten und verschiedene Anlagen mithilfe dieser Optionen verschlüsseln. Eine vollständige Liste der unterstützten Anlagentypen finden Sie unter "Dateitypen, die von IRM-Richtlinien abgedeckt werden, wenn sie an Nachrichten angefügt [werden" unter Einführung in IRM für E-Mail-Nachrichten](https://support.office.com/article/bb643d33-4a3f-4ac7-9770-fd50d95f58dc#FileTypesforIRM).

Als Administrator können Sie auch Nachrichtenflussregeln definieren, um diesen Schutz anzuwenden. Sie können beispielsweise eine Regel erstellen, die die Verschlüsselung aller nachrichten erfordert, die an einen bestimmten Empfänger adressiert sind, oder die bestimmte Wörter in der Betreffzeile enthält, und außerdem angeben, dass Empfänger den Inhalt der Nachricht nicht kopieren oder drucken können.

Im Gegensatz zur vorherigen Version von OME bieten die neuen Funktionen eine einheitliche Absendererfahrung, unabhängig davon, ob Sie E-Mails innerhalb Ihrer Organisation oder an Empfänger außerhalb von Microsoft 365 senden. Darüber hinaus müssen Empfänger, die eine geschützte E-Mail-Nachricht erhalten, die an ein Microsoft 365-Konto in Outlook 2016 oder Outlook im Web gesendet wird, keine andere Aktion zum Anzeigen der Nachricht ergreifen. Es funktioniert nahtlos. Empfänger, die andere E-Mail-Clients und E-Mail-Dienstanbieter verwenden, haben ebenfalls eine verbesserte Erfahrung. Weitere Informationen finden Sie unter Informationen zu geschützten Nachrichten [in Office 365](https://support.office.com/article/Learn-about-protected-messages-in-Office-365-2baf3ac7-12db-40a4-8af7-1852204b4b67) und Wie öffne [ich eine geschützte Nachricht](https://support.office.com/article/How-do-I-open-a-protected-message-1157a286-8ecc-4b1e-ac43-2a608fbf3098).

Eine detaillierte Liste der Unterschiede zwischen der vorherigen Version von OME und den neuen OME-Funktionen finden Sie [unter Vergleichen von Versionen von OME](ome-version-comparison.md).

Wenn jemand eine E-Mail-Nachricht sendet, die einer Verschlüsselungs-E-Mail-Flussregel entspricht, wird die Nachricht verschlüsselt, bevor sie gesendet wird. Alle Microsoft 365-Endbenutzer, die Outlook-Clients zum Lesen von E-Mails verwenden, erhalten native, erstklassige Leseerfahrungen für verschlüsselte und rechtegeschützte E-Mails, auch wenn sie nicht in derselben Organisation wie der Absender sind. Unterstützte Outlook-Clients sind Outlook Desktop, Outlook Mac, Outlook mobile unter iOS und Android und Outlook im Web (früher als Outlook Web App bekannt).

Empfänger verschlüsselter Nachrichten, die verschlüsselte oder rechtegeschützte E-Mails empfangen, die an ihre Outlook.com-, Gmail- und Yahoo-Konten gesendet werden, erhalten eine Wrapper-E-Mail, die sie an das OME-Portal weiter leitet, wo sie sich problemlos mit einem Microsoft-Konto, Gmail oder Yahoo-Anmeldeinformationen authentifizieren können.

Endbenutzer, die verschlüsselte oder rechtegeschützte E-Mails auf anderen Clients als Outlook lesen, verwenden auch das OME-Portal, um verschlüsselte und rechtegeschützte Nachrichten, die sie empfangen, anzeigen zu können.

Wenn sich der Absender der geschützten E-Mail in GCC High befindet und sich der Empfänger außerhalb von GCC High befindet, einschließlich kommerzieller Benutzer, Outlook.com-Benutzer und Benutzer anderer E-Mail-Anbieter wie Gmail, empfängt der Empfänger eine Wrapper-E-Mail. Die Wrapper-E-Mail leitet den Empfänger an das OME-Portal weiter, in dem der Empfänger die Nachricht lesen und beantworten kann. Andernfalls erhalten Empfänger, die Outlook-Clients zum Lesen von E-Mails verwenden, systemeigene, erstklassige Leseerfahrungen für verschlüsselte und rechtegeschützte E-Mails, wenn sich Absender und Empfänger beide in der GCC High-Umgebung befinden, auch wenn sie sich nicht in derselben Organisation befinden. Weitere Informationen zur unterschiedlichen Erfahrung in GCC High finden Sie [unter Compare versions of OME](ome-version-comparison.md).

Weitere Informationen zu Größenbeschränkungen für Nachrichten und Anlagen, die Sie mit OME verschlüsseln können, finden Sie unter [Exchange Online Limits](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits).

## <a name="how-office-365-advanced-message-encryption-works-on-top-of-ome"></a>Funktionsweise der erweiterten Office 365-Nachrichtenverschlüsselung über OME

Mit der erweiterten Nachrichtenverschlüsselung von Office 365 können Sie mehrere Brandingvorlagen erstellen, sodass Sie die Steuerung von Empfänger-E-Mails optimieren und benutzerdefinierte Brandingerfahrungen erstellen können, um eine unterschiedliche Organisationsstruktur zu unterstützen.

Die erweiterte Nachrichtenverschlüsselung in Microsoft 365 hilft Ihnen bei der Erfüllung von Complianceverpflichtungen, die eine flexiblere Kontrolle über den Zugriff externer Empfänger auf verschlüsselte E-Mails erfordern. Mit der erweiterten Nachrichtenverschlüsselung in Office 365 können Sie als Administrator vertrauliche E-Mails steuern, die außerhalb der Organisation freigegeben wurden, mit automatischen Richtlinien, die Typen vertraulicher Informationen erkennen (z. B. PII-, Finanz- oder Integritäts-IDs), oder Schlüsselwörter, um den Schutz zu verbessern, indem Sie den Zugriff über ein sicheres Webportal auf verschlüsselte E-Mails ablaufen lassen. Als Administrator können Sie verschlüsselte E-Mails, auf die über ein Microsoft 365-Webportal zugegriffen wird, weiter steuern, indem Sie den Zugriff auf eine E-Mail jederzeit widerrufen.

Nachrichtensperrung und -ablauf funktionieren nur für E-Mails, die Ihre Benutzer an Empfänger außerhalb Ihrer Organisation senden. Darüber hinaus müssen die Empfänger über das Webportal auf die E-Mail zugreifen. Um sicherzustellen, dass der Empfänger das Portal zum Empfangen von E-Mails verwendet, richten Sie eine benutzerdefinierte Brandingvorlage ein, die den Wrapper verwendet. Anschließend wenden Sie die Brandingvorlage in einer Nachrichtenflussregel an. Weitere Informationen zur erweiterten Nachrichtenverschlüsselung finden Sie unter [Office 365 Advanced Message Encryption](ome-advanced-message-encryption.md).

## <a name="defining-rules-for-office-365-message-encryption"></a>Definieren von Regeln für die Office 365-Nachrichtenverschlüsselung

Eine Möglichkeit, die neuen Funktionen für die Office 365-Nachrichtenverschlüsselung zu aktivieren, besteht in der Definition von Nachrichtenflussregeln durch Exchange Online- und Exchange Online Protection-Administratoren. Diese Regeln bestimmen, unter welchen Bedingungen E-Mail-Nachrichten verschlüsselt werden sollen. Wenn eine Verschlüsselungsaktion für eine Regel festgelegt wird, werden alle Nachrichten, die den Regelbedingungen entsprechen, verschlüsselt, bevor sie gesendet werden.

Nachrichtenflussregeln sind flexibel, sodass Sie Bedingungen kombinieren können, damit Sie bestimmte Sicherheitsanforderungen in einer einzigen Regel erfüllen können. Sie können beispielsweise eine Regel zum Verschlüsseln aller Nachrichten definieren, die bestimmte Schlüsselwörter enthalten und an externe Empfänger adressiert sind. Die neuen Funktionen für die Office 365-Nachrichtenverschlüsselung verschlüsseln auch Antworten von Empfängern verschlüsselter E-Mails.

Weitere Informationen zum Erstellen von Nachrichtenflussregeln zur Nutzung der neuen OME-Funktionen finden Sie unter [Define Rules for Office 365 Message Encryption](define-mail-flow-rules-to-encrypt-email.md).

## <a name="get-started-with-the-new-ome-capabilities"></a>Erste Schritte mit den neuen OME-Funktionen

Wenn Sie bereit sind, mit den neuen OME-Funktionen in Ihrer Organisation zu beginnen, lesen Sie Einrichten neuer [Office 365-Nachrichtenverschlüsselungsfunktionen](set-up-new-message-encryption-capabilities.md).

## <a name="sending-viewing-and-replying-to-encrypted-email-messages"></a>Senden, Anzeigen und Beantworten von verschlüsselten E-Mail-Nachrichten

Mit der Office 365-Nachrichtenverschlüsselung können Benutzer verschlüsselte E-Mails von Outlook und Outlook im Web senden. Darüber hinaus können Administratoren Nachrichtenflussregeln in Microsoft 365 einrichten, um E-Mails basierend auf dem Stichwortabgleich oder anderen Bedingungen automatisch zu verschlüsseln.

Empfänger verschlüsselter Nachrichten, die sich in Organisationen befinden, können diese Nachrichten nahtlos in jeder Outlook-Version lesen, einschließlich Outlook für PC, Outlook für Mac, Outlook im Web, Outlook für iOS und Outlook für Android. Benutzer, die verschlüsselte Nachrichten auf anderen E-Mail-Clients empfangen, können die Nachrichten im OME-Portal anzeigen.

Ausführliche Anleitungen zum Senden und Anzeigen verschlüsselter Nachrichten finden Sie in diesen Artikeln.

|Lesen Sie diesen Artikel...|Wenn Sie...|
|:-----|:-----|
|[Informationen zu geschützten Nachrichten in Office 365](https://support.office.com/article/2baf3ac7-12db-40a4-8af7-1852204b4b67.aspx)|Ein Endbenutzer, der mehr über die Funktionsweise verschlüsselter Nachrichten und die verfügbaren Optionen erfahren möchte.|
|[Wie öffne ich eine geschützte Nachricht?](https://support.office.com/article/1157a286-8ecc-4b1e-ac43-2a608fbf3098.aspx)|Ein Endbenutzer, der eine geschützte Nachricht lesen möchte, die an Sie gesendet wurde. Dieser Artikel enthält Informationen zum Lesen von Nachrichten in mehreren Versionen von Outlook und von verschiedenen E-Mail-Konten, einschließlich dieser Konten außerhalb von Microsoft 365 wie gmail und Yahoo! Konten.|
|[Senden, Anzeigen und Antworten auf verschlüsselte Nachrichten in Outlook](https://support.microsoft.com/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)|Ein Endbenutzer, der eine verschlüsselte Nachricht von Outlook senden, anzeigen oder beantworten möchte. Auch wenn Sie kein Mitglied einer Organisation sind, erhalten Sie weiterhin Benachrichtigungen über verschlüsselte Nachrichten, die an Sie in Outlook gesendet werden. In diesem Artikel finden Sie Anweisungen zum Anzeigen und Antworten auf verschlüsselte Nachrichten, die von Office 365 gesendet werden.|
|[Senden einer digital signierten oder verschlüsselten Nachricht](https://support.microsoft.com/office/send-a-digitally-signed-or-encrypted-message-a18ecf7f-a7ac-4edd-b02e-687b05eff547)|Ein Endbenutzer, der verschlüsselte Nachrichten mit Outlook für Mac senden, anzeigen oder beantworten möchte. In diesem Artikel wird auch die Verwendung anderer Verschlüsselungsmethoden als OME behandelt, z. B. S/MIME.|
|[Anzeigen verschlüsselter Nachrichten auf Ihrem Android-Gerät](https://support.office.com/article/83d60f17-2305-407a-a762-7d518401fdeb)|Als Endbenutzer, der eine mit office 365-Nachrichtenverschlüsselung verschlüsselte Nachricht auf Ihrem Android-Gerät empfangen hat, können Sie die kostenlose OME-Viewer-App verwenden, um die Nachricht zu sehen und eine verschlüsselte Antwort zu senden. In diesem Artikel wird dies erläutert.|
|[Anzeigen verschlüsselter Nachrichten auf Ihrem iPhone oder iPad](https://support.microsoft.com/office/view-protected-messages-on-your-iphone-or-ipad-4d631321-0d26-4bcc-a483-d294dd0b1caf)|Als Endbenutzer, der eine mit Office 365-Nachrichtenverschlüsselung verschlüsselte Nachricht auf Ihrem iPhone oder iPad empfangen hat, können Sie die kostenlose OME-Viewer-App verwenden, um die Nachricht ein- und zu senden und eine verschlüsselte Antwort zu senden. In diesem Artikel wird dies erläutert.|
||