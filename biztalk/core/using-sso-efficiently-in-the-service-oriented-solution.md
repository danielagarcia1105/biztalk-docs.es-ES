---
title: Usar SSO de forma eficaz en el servicio de solución orientada a servicios | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SSO, service solutions
- service solution tutorial, SSO
- SSO, using from code
ms.assetid: 809e0ad3-cc7f-4095-87d1-63031675a47f
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 66dafba56bdeedb8c7b35b4442623f55e70f1305
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22289268"
---
# <a name="using-sso-efficiently-in-the-service-oriented-solution"></a>Usar SSO de forma eficaz en el servicio de solución orientada a servicios
La solución orientada a servicios utiliza el inicio de sesión único (SSO) empresarial tanto para almacenar valores de configuración como para controlar las credenciales de los sistemas servidor. Para reducir latencia, la solución utiliza una caché local para los valores de configuración. La solución actualiza la caché cada cinco minutos.  
  
 En muchas aplicaciones, los adaptadores controlan las operaciones de SSO, como obtener un vale de SSO, canjear el vale y con las credenciales para obtener acceso a la aplicación afiliada. Sin embargo, la versión en línea de la solución orientada a servicios no utiliza adaptadores. Debe utilizar SSO del código.  
  
 En este tema se describe el mecanismo de almacenamiento en caché utilizado por la solución y cómo utiliza SSO del código la versión en línea de la solución.  
  
## <a name="local-caching-of-configuration-values"></a>Almacenar en caché local los valores de configuración  
 La solución orientada a servicios utiliza dos objetos, **ConfigPropertyBag** y **ConfigParameters**, para controlar los valores de configuración. El **ConfigPropertyBag** contiene los valores de clase y se utiliza únicamente por la **ConfigParameters** clase. El **ConfigParameters** clase se utiliza por las otras partes de la solución para recuperar los parámetros de configuración. Ambas clases se encuentran en el **Microsoft.Samples.BizTalk.WoodgroveBank.ConfigHelper** espacio de nombres.  
  
> [!NOTE]
>  La solución orientada a servicios corrige el intervalo de actualización de caché a 300 segundos (5 minutos). No obstante, podría convertir el intervalo de actualización de caché en una propiedad configurable en esta solución. Esto lo puede hacer en la solución Administración de procesos empresariales. Para obtener más información acerca de cómo controla SSO la solución, vea [usar SSO de forma eficaz en la solución de administración de procesos empresariales](../core/using-sso-efficiently-in-the-business-process-management-solution.md). Tenga en cuenta que, en tal caso, los cambios en el intervalo de actualización no se hacen efectivos hasta que se actualiza la caché al final del período del intervalo anterior.  
  
 El **ConfigPropertyBag** tiene los siguientes métodos:  
  
|Método|Description|  
|------------|-----------------|  
|Lectura|Recupera un valor para una propiedad dada.|  
|Escribir|Asigna un valor a una propiedad.|  
  
 La clase utiliza una instancia de .NET **NameValueCollection** para almacenar los valores. Implementan los métodos de acceso del **IPropertyBag** interfaz desde el **Microsoft.BizTalk.SSOClient.Interop** espacio de nombres. El **ConfigPropertyBag** clase es una clase interna y utiliza únicamente por la **ConfigParameters** clase.  
  
> [!NOTE]
>  Los nombres de clave en la bolsa de propiedades no distinguen entre mayúsculas y minúsculas. Subyacente **NameValueCollection** usa algoritmos hash y comparaciones entre mayúsculas y minúsculas.  
  
 La aplicación utiliza el **ConfigParameters** clase para controlar los valores de configuración de SSO. La clase tiene los siguientes métodos y atributos públicos:  
  
|Método o atributo|Description|  
|-------------------------|-----------------|  
|SSOConfigParameter|Enumeración para especificar parámetros de configuración.|  
|GetConfigParameters|Método usado para recuperar un valor para un parámetro dado. Utiliza SSOConfigParameter para indicar el parámetro.|  
  
 El **ConfigParameters** clase usa la clase Timer de .NET y una función de delegado para configurar la actualización de la **ConfigPropertyBag**:  
  
```  
private static Timer cacheRefreshTimer;  
private static ISSOConfigStore ssoConfigStore;  
private static ReaderWriterLock syncLock;  
  
// Cache refresh interval in milliseconds  
private const int CacheRefreshInterval = 5 * 60 * 1000;  
private static ConfigPropertyBag ssoPropBag;  
  
static ConfigParameters()  
{  
    ssoConfigStore = new ISSOConfigStore();  
    ssoPropBag = new ConfigPropertyBag();  
    syncLock = new ReaderWriterLock();  
  
    ssoConfigStore.GetConfigInfo(SSO_CONFIG_APP,  
         SSO_IDENTIFIER_NAME, SSOFlag.SSO_FLAG_RUNTIME,  
         ssoPropBag);  
  
    cacheRefreshTimer = new Timer(  
        new TimerCallback(ConfigParameters.cacheRefreshCallback),  
        null, CacheRefreshInterval, CacheRefreshInterval);  
}  
```  
  
 Observe que el constructor estático inicializa las variables de miembro estático además de habilitar el uso de los métodos de clase sin crear una instancia de la clase. El constructor crea instancias de almacén de configuración de SSO (**ISSOConfigStore**), la bolsa de propiedades de configuración (**ConfigPropertyBag**) y un bloqueo de sincronización ( **ReaderWriterLock**) permiten controlar el acceso a la **ConfigurationPropertyBag** durante las actualizaciones y lecturas. A continuación, utiliza el constructor **GetConfigInfo** para recuperar los valores de configuración de SSO y colocarlos en la bolsa de propiedades. Por último, el constructor crea un **temporizador** objeto que, después del intervalo especificado, llama a la función de delegado, **cacheRefreshCallback**.  
  
 El **temporizador** función de delegado es bastante sencillo:  
  
```  
private static void cacheRefreshCallback(object state)  
{  
    // Disable the timer until we are done loading the cache.  
    cacheRefreshTimer.Change(Timeout.Infinite, CacheRefreshInterval);  
  
    // Put the data from SSO in a new property bag so that  
    // we don't have to lock the property bag and block it from being  
    // used. The SSO call is a remote call and may take a while.  
    ConfigPropertyBag propBag2 = new ConfigPropertyBag();  
    ssoConfigStore.GetConfigInfo(SSO_CONFIG_APP,   
        SSO_IDENTIFIER_NAME, SSOFlag.SSO_FLAG_RUNTIME, propBag2);  
  
    // Get a writer lock before updating the cached values.  
    syncLock.AcquireWriterLock(Timeout.Infinite);  
  
    try  
    {  
        ssoPropBag = propBag2;  
    }  
    finally   
    {  
        syncLock.ReleaseWriterLock();  
    }  
    // Enable the timer.  
    cacheRefreshTimer.Change(CacheRefreshInterval,   
        CacheRefreshInterval);  
}  
```  
  
 Tenga en cuenta que el método de devolución de llamada de actualización de caché deshabilita el temporizador para que el método se pueda ejecutar por completo. Tenga también en cuenta el uso de bloqueos para controlar el acceso a la bolsa de propiedades. El **ReaderWriterLock** es la mejor opción, se diseñó para casos donde hay más lecturas que escrituras. Observe también que el bloqueo, **syncLock**, es estático y declara la clase que todos los subprocesos comparten la misma instancia única del mismo nivel.  
  
## <a name="using-sso-from-code"></a>Usar SSO desde código  
 Cuando se utiliza un inicio de sesión único desde el código, el código debe asumir la función del adaptador: es decir, recuperar el vale de SSO desde el mensaje, canjear el vale para obtener el nombre de usuario y la contraseña para el sistema back-end y, por último, utilice el sistema back-end. La solución orientada a servicios hace esto mediante la **GetPendingTransactionsResponse** método de la **PendingTransactionsCaller** objeto.  
  
 El método se muestra de la siguiente forma:  
  
```  
public static PendingTransactionsResponse GetPendingTransactionsResponse(XLANGMessage requestMsg)  
{  
    try  
    {  
        // Get config parameter values.  
        int ptTimeout = Convert.ToInt32(  
            ConfigParameters.GetConfigParameter(  
                ConfigParameters.  
                    SSOConfigParameter.  
                        PENDING_TRANSACTIONS_INLINE_TIMEOUT  
            )  
        );  
  
        string ptURL = ConfigParameters.GetConfigParameter(  
            ConfigParameters.  
                SSOConfigParameter.  
                    PENDING_TRANSACTIONS_URL  
        );  
        string ssoAffliateApp = ConfigParameters.  
            GetConfigParameter(ConfigParameters.  
                SSOConfigParameter.  
                    PENDING_TRANSACTIONS_SSO_AFFILIATE_APP  
            );  
  
        // Redeem the SSO ticket and get the userid/password to   
        // use to interact with Pending Transaction System.  
  
        // Extract the ticket…  
        string msgTicket = (string)requestMsg.  
            GetPropertyValue(typeof(BTS.SSOTicket));  
  
        // and the user name of the originating user.  
        string originatorSID = (string)requestMsg.  
            GetPropertyValue(  
                typeof(  
                    Microsoft.BizTalk.XLANGs.BTXEngine.OriginatorSID  
                )  
            );  
  
        string pendTransUserName;  
        // Now, redeem the ticket.  
        string[] pendTransCredential =   
            ssoTicket.RedeemTicket(  
                ssoAffliateApp,  
                originatorSID,  
                msgTicket,  
                SSOFlag.SSO_FLAG_NONE,  
                out pendTransUserName  
            );   
  
        PendingTransactionsRequest req =   
            (PendingTransactionsRequest)requestMsg[0].  
                RetrieveAs(  
                    typeof(PendingTransactionsRequest)  
                );  
        PendingTransactionsResponse resp;  
  
        using (PendingTransactionsWebService  
            svc = new PendingTransactionsWebService())  
        {  
            svc.Url = ptURL;  
            svc.Timeout = ptTimeout;  
  
            // The web service uses basic authentication, so we  
            //need to send the user id and password in the request.  
            CredentialCache credCache = new CredentialCache();  
            NetworkCredential credentialToUse =  
                new NetworkCredential(  
                    pendTransUserName, pendTransCredential[0]  
                );  
            credCache.Add(new Uri(svc.Url), "Basic", credentialToUse);  
            svc.Credentials = credCache;  
  
            resp = svc.GetPendingTransactions(req);  
        }  
        return resp;                  
    }  
    catch (System.Net.WebException webEx)  
    {  
        if (webEx.Status == WebExceptionStatus.Timeout)  
        {  
            throw new PendingTransactionsTimeoutException();  
        }  
        else  
        {  
            Trace.WriteLine("Other Net.WebException: "  
                + webEx.ToString()   
                + (null == webEx.InnerException ? "" :  
                     ("Inner Exception: "   
                        + webEx.InnerException.ToString())  
                )  
            );  
            throw;  
        }  
    }  
    catch(System.Exception ex)  
    {  
        Trace.WriteLine("Other Exception: "  
            + ex.ToString()   
            + (null == ex.InnerException ? "" :   
                 ("Inner Exception: "  
                    + ex.InnerException.ToString())  
                  )  
            );  
        throw;  
    }  
}  
```  
  
 El método comienza recuperando la información de configuración, incluida la dirección URL, para el sistema servidor y el nombre de la aplicación servidor (afiliada).  
  
 Para canjear el vale, el método debe extraer el vale y el nombre de usuario original de la solicitud del mensaje. El mensaje contiene el vale como una de las propiedades de contexto de mensaje, **BTS. SSOTicket**. Para obtener más información, consulte **propiedades de contexto de mensaje** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]. El método también extrae el **OriginatorSID** desde las propiedades de contexto de mensaje. Con el vale y el nombre del originador, el método llama al método RedeemTicket en el vale para recuperar las credenciales.  
  
 El resto del código crea la caché NetworkCredential de .NET para las credenciales y llama al servicio Web servidor.  
  
> [!NOTE]
>  Puesto que el nombre de usuario y la contraseña se devuelven desde SSO en forma de texto visible, se recomienda reducir la duración de las variables que contienen dicha información. Tenga en cuenta que el código declara las variables de credencial dentro de un **intente** bloque. En este caso, las variables caducan al salir de la **intente** bloque.  
  
## <a name="see-also"></a>Vea también  
 [Aspectos destacados de la implementación del servicio en la solución orientada a servicios](../core/implementation-highlights-of-the-service-oriented-solution.md)