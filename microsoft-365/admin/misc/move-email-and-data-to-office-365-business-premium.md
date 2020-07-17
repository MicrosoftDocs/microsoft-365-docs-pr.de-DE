---
title: Migrieren von e-Mails und Daten nach Microsoft 365 Business Standard
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- SPO_Content
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1062115d-e312-482a-bb5a-765235990f41
ROBOTS: NOINDEX
description: In diesem Artikel erfahren Sie, wie Sie Daten in Ihre neue Geschäftsidentität umlegen.
ms.openlocfilehash: ebbb680baf36386d7f2dafae61fb262bf0220e69
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780001"
---
# <a name="move-email-and-data-to-microsoft-365-business-standard"></a>Migrieren von e-Mails und Daten nach Microsoft 365 Business Standard

Wenn Sie ein Upgrade auf Microsoft 365 Business Standard durchführen, erhalten Sie eine ganz neue *Geschäftsidentität*. Sie erhalten ein neues E-Mail-Konto und ein separates OneDrive-Konto für Ihre Geschäftsdaten. 
  
Wenn Sie einige Ihrer persönlichen Daten auf die neue Business-Identität verschieben möchten, folgen Sie den nachstehenden Anweisungen.
  
## <a name="onedrive"></a>[OneDrive](#tab/OneDrive)
  
 **Kopieren Ihrer OneDrive-Daten**
1. Erstellen Sie einen temporären Ordner auf Ihrer Festplatte, um die Dateien, die Sie zu Microsoft 365 for Business migrieren möchten, vorübergehend zu speichern.
    
2. Wechseln [https://onedrive.live.com/](https://onedrive.live.com/) Sie zu und melden Sie sich mit dem Microsoft-Konto an, das Sie für den Zugriff auf Ihr Microsoft 365-Familien Abonnement verwenden. 
    
3. Kopieren Sie die Dateien, die Sie mit Microsoft 365 for Business verwenden möchten, in den lokalen Ordner, den Sie in Schritt 1 erstellt haben.
    
 **Importieren von OneDrive-Dateien in Microsoft 365 for Business**
1. Wechseln Sie zu [Admin.Microsoft.com](https://go.microsoft.com/fwlink/?LinkId=816877) , und melden Sie sich mit Ihrem Benutzernamen und Kennwort für Microsoft 365 apps for Business an. 
    
2. Select the **app launcher** icon in the upper-left and then choose **OneDrive**.
  
    > [!TIP]
    > Beim ersten Öffnen von OneDrive for Business müssen Sie OneDrive einrichten. Wenn dies der Fall ist, wählen Sie auf der Seite **Willkommen bei OneDrive für Unternehmen** die Option **weiter**aus. Nachdem OneDrive eingerichtet wurde, wählen Sie **Ihr OneDrive ist Ready**aus. 
  
3. Nun wird ein leere OneDrive-Ordner angezeigt. Wenn Sie Unterordner erstellen möchten, wählen Sie **neuer** \> **Ordner**aus.

4. Wählen Sie **hochladen** aus, um die Dateien von Ihrer Festplatte zu kopieren, auf der Sie die OneDrive-Dateien kopiert haben. 
  
    > [!NOTE]
    >  Sie können einzelne Dateien und Dateigruppen (wie alle Dateien in einem bestimmten Ordner) gleichzeitig hochladen, Sie können jedoch keinen Ordner nach OneDrive for Business kopieren. Stattdessen müssen Sie in OneDrive for Business die gewünschte Ordnerstruktur erstellen. >  Wenn Sie Dateien in einen Ordner kopieren möchten, den Sie in Schritt 4 erstellt haben, öffnen Sie den Ordner, bevor Sie die Dateien hochladen. Andernfalls werden die Dateien in den Stammordner hochgeladen. Sie können die Dateien auch zwischen den Ordnern in OneDrive for Business verschieben, nachdem Sie sie hochgeladen haben. 
  
## <a name="outlookemail"></a>[Outlook/E-Mail](#tab/Outlook)
  
 **Exportieren von Outlook 2013-Daten in eine Outlook-Datendatei**
1. Bevor Sie eine Outlook-Datendatei (PST) erstellen können, muss das Konto, aus dem Sie Outlook-Daten exportieren möchten, bereits in der Desktopversion von Outlook hinzugefügt worden sein. Weitere Informationen zum Hinzufügen eines Kontos in Outlook 2013 oder höher finden Sie unter [Einrichten von E-Mail in Outlook (für Windows](https://support.microsoft.com/office/6e27792a-9267-4aa4-8bb6-c84ef146101b) oder [Einrichten von E-Mail in Outlook für Mac 2011](https://support.microsoft.com/office/de372dc4-9648-4044-a76c-e8a60e178d54).
    
2. Jeden Benutzer muss die Schritte unter [Exportieren oder Sichern von E-Mails, Kontakten und Kalender in einer Outlook-PST-Datei](https://support.microsoft.com/office/14252b52-3075-4e9b-be4e-ff9ef1068f91) ausführen.
    
 **Einrichten Ihres neuen E-Mail-Kontos in Outlook**
1. Jeder Benutzer muss sein neues e-Mail-Konto einrichten, das im Lieferumfang des Microsoft 365 for Business-Abonnements aufgeführt ist. Hierfür benötigt er die Adresse des neuen E-Mail-Kontos. Das e-Mail-Konto jedes Benutzers ist identisch mit dem Benutzernamen, mit dem er sich bei Microsoft 365 for Business anmeldet. Also beispielsweise: laura@onmicrosoft.com oder karl@contoso.com.
    
2. Bitten Sie jeden Benutzer, sein E-Mail-Konto in Outlook hinzuzufügen. Wenn Sie wissen möchten, wie das geht, lesen Sie [Einrichten von E-Mail in Outlook (für Windows)](https://support.microsoft.com/office/6e27792a-9267-4aa4-8bb6-c84ef146101b) oder [Einrichten von E-Mail in Outlook für Mac 2011](https://support.microsoft.com/office/de372dc4-9648-4044-a76c-e8a60e178d54).
    
 **Importieren von -Daten aus einer Outlook-Datendatei**
1. Dadurch werden die e-Mails, Kalender, Aufgaben und Kontakte, die in der PST-Datei gespeichert sind, in Ihr Microsoft 365 for Business-e-Mail-Konto zusammengeführt.
    
2. Wenn Sie die in der PST-Datei gespeicherten Informationen in Ihr Microsoft 365 for Business-e-Mail-Konto importieren möchten, führen Sie die Schritte unter [Importieren von e-Mails, Kontakten und Kalender aus einer Outlook. PST-Datei durch](https://support.microsoft.com/office/431a8e9a-f99f-4d5f-ae48-ded54b3440ac).
    
---

