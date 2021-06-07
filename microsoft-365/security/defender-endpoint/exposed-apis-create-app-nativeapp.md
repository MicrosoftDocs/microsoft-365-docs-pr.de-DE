---
title: Verwenden von Microsoft Defender für Endpunkt-APIs
ms.reviewer: ''
description: Erfahren Sie, wie Sie eine systemeigene Windows-App entwerfen, um programmgesteuerten Zugriff auf Microsoft Defender für Endpunkt ohne Benutzer zu erhalten.
keywords: APIs, Graph-API, unterstützte APIs, Actor, Warnungen, Gerät, Benutzer, Domäne, IP, Datei, erweiterte Suche, Abfrage
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 8f23a0b269986f4caa199ad3744c563fcc6ff6b2
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769101"
---
# <a name="use-microsoft-defender-for-endpoint-apis"></a>Verwenden von Microsoft Defender für Endpunkt-APIs

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)

> Möchten Sie Microsoft Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

Auf dieser Seite wird beschrieben, wie Sie eine Anwendung erstellen, um programmgesteuerten Zugriff auf Defender für Endpunkt im Namen eines Benutzers zu erhalten.

Wenn Sie programmgesteuerten Zugriff auf Microsoft Defender für Endpunkt ohne Einen Benutzer benötigen, lesen Sie [Den Zugriff auf Microsoft Defender für Endpunkt mit Anwendungskontext.](exposed-apis-create-app-webapp.md)

Wenn Sie nicht sicher sind, welchen Zugriff Sie benötigen, lesen Sie die [Einführungsseite.](apis-intro.md)

Microsoft Defender für Endpunkt macht einen Großteil seiner Daten und Aktionen über eine Reihe programmgesteuerter APIs verfügbar. Mit diesen APIs können Sie Arbeitsabläufe automatisieren und Innovationen basierend auf den Microsoft Defender für Endpunkt-Funktionen durchführen. Der API-Zugriff erfordert die OAuth2.0-Authentifizierung. Weitere Informationen finden Sie unter [OAuth 2.0-Autorisierungscode Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).

Im Allgemeinen müssen Sie die folgenden Schritte ausführen, um die APIs zu verwenden:
- Erstellen einer AAD-Anwendung
- Abrufen eines Zugriffstokens mithilfe dieser Anwendung
- Verwenden des Tokens für den Zugriff auf die Defender für Endpunkt-API

Auf dieser Seite wird erläutert, wie Sie eine AAD-Anwendung erstellen, ein Zugriffstoken für Microsoft Defender für Endpunkt abrufen und das Token überprüfen.

>[!NOTE]
> Wenn Sie im Namen eines Benutzers auf die Microsoft Defender für Endpunkt-API zugreifen, benötigen Sie die richtige Anwendungsberechtigung und Benutzerberechtigung.
> Wenn Sie nicht mit Benutzerberechtigungen für Microsoft Defender für Endpunkt vertraut sind, lesen Sie "Verwalten des [Portalzugriffs mithilfe der rollenbasierten Zugriffssteuerung".](rbac.md)

>[!TIP]
> Wenn Sie über die Berechtigung zum Ausführen einer Aktion im Portal verfügen, verfügen Sie über die Berechtigung, die Aktion in der API auszuführen.

## <a name="create-an-app"></a>App erstellen

1. Melden Sie sich bei [Azure](https://portal.azure.com) mit einem Benutzerkonto mit der Rolle **"Globaler Administrator"** an.

2. Navigieren Sie zu **Azure Active Directory**  >  **App-Registrierungen**  >  **Neuregistrierung.** 

   ![Abbildung von Microsoft Azure und Navigation zur Anwendungsregistrierung](images/atp-azure-new-app2.png)

3. Geben Sie auf der daraufhin angezeigten Seite **Anwendung registrieren** die Registrierungsinformationen für Ihre Anwendung ein:

   - **Name**: Geben Sie einen aussagekräftigen Anwendungsnamen ein, der den Benutzern der App angezeigt wird.
   - **Unterstützte Kontotypen**: Wählen Sie aus, welche Konten von Ihrer Anwendung unterstützt werden sollen.

       | Unterstützte Kontotypen | Beschreibung |
       |-------------------------|-------------|
       | **Nur Konten in diesem Organisationsverzeichnis** | Wählen Sie diese Option aus, wenn Sie eine Branchenanwendung erstellen. Falls Sie die Anwendung nicht in einem Verzeichnis registrieren, ist diese Option nicht verfügbar.<br><br>Diese Option ist für reine Azure AD-Apps mit einem einzelnen Mandanten vorgesehen.<br><br>Sofern Sie die App nicht außerhalb eines Verzeichnisses registrieren, ist dies die Standardoption. Wird die App außerhalb eines Verzeichnisses registriert, werden standardmäßig mehrinstanzenfähige Azure AD-Konten und persönliche Microsoft-Konten verwendet. |
       | **Konten in einem beliebigen Organisationsverzeichnis** | Wählen Sie diese Option, wenn Sie alle Kunden aus dem Unternehmens- und Bildungsbereich ansprechen möchten.<br><br>Diese Option ist für reine Azure AD-Apps mit mehreren Mandanten vorgesehen.<br><br>Wenn Sie die App als reine Azure AD-App mit einem einzelnen Mandanten registriert haben, können Sie sie über das Blatt **Authentifizierung** in eine Azure AD-App mit mehreren Mandanten (und wieder zurück in eine App mit einem einzelnen Mandanten) verwandeln. |
       | **Konten in allen Organisationsverzeichnissen und persönliche Microsoft-Konten** | Verwenden Sie diese Option, um die breiteste Kundengruppe anzusprechen.<br><br>Diese Option ist für Azure AD-Apps mit mehreren Mandanten und für persönliche Microsoft-Konten vorgesehen.<br><br>Wenn Sie die App als Azure AD-App mit mehreren Mandanten und für persönliche Microsoft-Konten registriert haben, können Sie dies über die Benutzeroberfläche nicht ändern. In diesem Fall müssen die unterstützten Kontotypen mithilfe des Anwendungsmanifest-Editors geändert werden. |

   - **Umleitungs-URI (optional)**: Wählen Sie die Art der App aus, die Sie erstellen (**Web** oder **Öffentlicher Client (Mobilgerät und Desktop)**), und geben Sie dann den Umleitungs-URI (oder die Antwort-URL) für Ihre Anwendung ein.
       - Geben Sie für Webanwendungen die Basis-URL Ihrer App an. `http://localhost:31544` kann beispielsweise die URL für eine Web-App sein, die auf einem lokalen Computer ausgeführt wird. Benutzer können diese URL nutzen, um sich an einer Webclientanwendung anzumelden.
       - Geben Sie für öffentliche Clientanwendungen den URI an, der von Azure AD zum Zurückgeben von Tokenantworten verwendet wird. Geben Sie einen für Ihre Anwendung spezifischen Wert ein (beispielsweise `myapp://auth`).

     Spezifische Beispiele für Webanwendungen oder native Anwendungen finden Sie in unseren [Schnellstartanleitungen](/azure/active-directory/develop/#quickstarts).

     Wenn Sie so weit sind, klicken Sie auf **Registrieren**.

4. Erlauben Sie Ihrer Anwendung, auf Microsoft Defender für Endpunkt zuzugreifen, und weisen Sie ihr die Berechtigung "Warnungen lesen" zu:

    - Wählen Sie auf der Anwendungsseite **"API-Berechtigungen** Hinzufügen von  >    >  **Berechtigungs-APIs" aus,** die meine Organisation > Typ **"WindowsDefenderATP"** verwendet, und wählen Sie **"WindowsDefenderATP"** aus.

    - **Hinweis:** *WindowsDefenderATP* wird nicht in der ursprünglichen Liste angezeigt. Beginnen Sie damit, den Namen in das Textfeld zu schreiben, damit er angezeigt wird.

      ![Berechtigung hinzufügen](images/add-permission.png)

    - Wählen Sie **"Warnung zu delegierten**  >  **Berechtigungen".>** **"Berechtigungen hinzufügen"** aus.

      ![Anwendungsberechtigungen](images/application-permissions-public-client.png)

    - **Wichtiger Hinweis:** Wählen Sie die entsprechenden Berechtigungen aus. Lesen von Warnungen ist nur ein Beispiel.

      Zum Beispiel

      - Wählen Sie zum [Ausführen erweiterter Abfragen](run-advanced-query-api.md)die Berechtigung "Erweiterte Abfragen ausführen" aus.
      - Wählen Sie zum [Isolieren eines Geräts](isolate-machine.md)die Berechtigung "Computer isolieren" aus.
      - Um zu bestimmen, welche Berechtigung Sie benötigen, zeigen Sie den Abschnitt **"Berechtigungen"** in der API an, die Sie aufrufen möchten.

    - Wählen Sie **"Zustimmung erteilen" aus.**

      **Hinweis:** Jedes Mal, wenn Sie die Berechtigung hinzufügen, müssen Sie **"Zustimmung erteilen"** auswählen, damit die neue Berechtigung wirksam wird.

      ![Abbildung der Berechtigungserteilung](images/grant-consent.png)

6. Notieren Sie Ihre Anwendungs-ID und Ihre Mandanten-ID:

   - Wechseln Sie auf der Anwendungsseite zu **"Übersicht",** und kopieren Sie die folgenden Informationen:

   ![Abbildung der erstellten App-ID](images/app-and-tenant-ids.png)


## <a name="get-an-access-token"></a>Abrufen eines Zugriffstokens

Weitere Informationen zu AAD-Token finden Sie im [Azure AD-Lernprogramm](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)

### <a name="using-c"></a>Verwenden von C #

- Kopieren/Fügen Sie die folgende Klasse in Ihre Anwendung ein.
- Verwenden Sie die **AcquireUserTokenAsync-Methode** mit Ihrer Anwendungs-ID, Mandanten-ID, dem Benutzernamen und dem Kennwort, um ein Token abzurufen.

    ```csharp
    namespace WindowsDefenderATP
    {
        using System.Net.Http;
        using System.Text;
        using System.Threading.Tasks;
        using Newtonsoft.Json.Linq;

        public static class WindowsDefenderATPUtils
        {
            private const string Authority = "https://login.microsoftonline.com";

            private const string WdatpResourceId = "https://api.securitycenter.microsoft.com";

            public static async Task<string> AcquireUserTokenAsync(string username, string password, string appId, string tenantId)
            {
                using (var httpClient = new HttpClient())
                {
                    var urlEncodedBody = $"resource={WdatpResourceId}&client_id={appId}&grant_type=password&username={username}&password={password}";

                    var stringContent = new StringContent(urlEncodedBody, Encoding.UTF8, "application/x-www-form-urlencoded");

                    using (var response = await httpClient.PostAsync($"{Authority}/{tenantId}/oauth2/token", stringContent).ConfigureAwait(false))
                    {
                        response.EnsureSuccessStatusCode();

                        var json = await response.Content.ReadAsStringAsync().ConfigureAwait(false);

                        var jObject = JObject.Parse(json);

                        return jObject["access_token"].Value<string>();
                    }
                }
            }
        }
    }
    ```

## <a name="validate-the-token"></a>Überprüfen des Tokens

Stellen Sie sicher, dass Sie ein korrektes Token erhalten haben:
- Kopieren/Einfügen des Tokens, das Sie im vorherigen Schritt erhalten haben, in [JWT,](https://jwt.ms) um es zu decodieren
- Überprüfen, ob Sie einen "scp"-Anspruch mit den gewünschten App-Berechtigungen erhalten
- Im folgenden Screenshot sehen Sie im Lernprogramm ein decodiertes Token, das von der App erworben wurde:

![Abbildung der Tokenüberprüfung](images/nativeapp-decoded-token.png)

## <a name="use-the-token-to-access-microsoft-defender-for-endpoint-api"></a>Verwenden des Tokens für den Zugriff auf die Microsoft Defender für Endpunkt-API

- Auswählen der API, die Sie verwenden möchten – [Unterstützte Microsoft Defender für Endpunkt-APIs](exposed-apis-list.md)
- Legen Sie den Autorisierungsheader in der HTTP-Anforderung, die Sie senden, auf "Bearer {token}" fest (Bearer ist das Autorisierungsschema)
- Die Ablaufzeit des Tokens beträgt 1 Stunde (Sie können mehr als eine Anforderung mit demselben Token senden)

- Beispiel für das Senden einer Anforderung zum Abrufen einer Liste von Warnungen **mit C#** 

    ```csharp
    var httpClient = new HttpClient();

    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.securitycenter.microsoft.com/api/alerts");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();

    // Do something useful with the response
    ```

## <a name="see-also"></a>Siehe auch
- [Microsoft Defender für Endpunkt-APIs](exposed-apis-list.md)
- [Zugreifen auf Microsoft Defender für Endpunkt mit Anwendungskontext](exposed-apis-create-app-webapp.md)
