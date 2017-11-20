---
title: "Usar SSO de forma eficaz en el servicio de solución orientada a servicios | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SSO, service solutions
- service solution tutorial, SSO
- SSO, using from code
ms.assetid: 809e0ad3-cc7f-4095-87d1-63031675a47f
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 66dafba56bdeedb8c7b35b4442623f55e70f1305
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="using-sso-efficiently-in-the-service-oriented-solution"></a><span data-ttu-id="b3efa-102">Usar SSO de forma eficaz en el servicio de solución orientada a servicios</span><span class="sxs-lookup"><span data-stu-id="b3efa-102">Using SSO Efficiently in the Service Oriented Solution</span></span>
<span data-ttu-id="b3efa-103">La solución orientada a servicios utiliza el inicio de sesión único (SSO) empresarial tanto para almacenar valores de configuración como para controlar las credenciales de los sistemas servidor.</span><span class="sxs-lookup"><span data-stu-id="b3efa-103">The service oriented solution uses Enterprise Single Sign-On (SSO) both to store configuration values and to handle credentials for the back-end systems.</span></span> <span data-ttu-id="b3efa-104">Para reducir latencia, la solución utiliza una caché local para los valores de configuración.</span><span class="sxs-lookup"><span data-stu-id="b3efa-104">To reduce latency, the solution uses a local cache for the configuration values.</span></span> <span data-ttu-id="b3efa-105">La solución actualiza la caché cada cinco minutos.</span><span class="sxs-lookup"><span data-stu-id="b3efa-105">The solution refreshes the cache every five minutes.</span></span>  
  
 <span data-ttu-id="b3efa-106">En muchas aplicaciones, los adaptadores controlan las operaciones de SSO, como obtener un vale de SSO, canjear el vale y con las credenciales para obtener acceso a la aplicación afiliada.</span><span class="sxs-lookup"><span data-stu-id="b3efa-106">In many applications, the adapters handle the SSO operations—including getting an SSO ticket, redeeming the ticket, and using the credentials to gain access to the affiliate application.</span></span> <span data-ttu-id="b3efa-107">Sin embargo, la versión en línea de la solución orientada a servicios no utiliza adaptadores.</span><span class="sxs-lookup"><span data-stu-id="b3efa-107">However, the inline version of the service oriented solution does not use adapters.</span></span> <span data-ttu-id="b3efa-108">Debe utilizar SSO del código.</span><span class="sxs-lookup"><span data-stu-id="b3efa-108">It must use SSO from code.</span></span>  
  
 <span data-ttu-id="b3efa-109">En este tema se describe el mecanismo de almacenamiento en caché utilizado por la solución y cómo utiliza SSO del código la versión en línea de la solución.</span><span class="sxs-lookup"><span data-stu-id="b3efa-109">This topic describes the caching mechanism used by the solution, as well as how the inline version of the solution uses SSO from code.</span></span>  
  
## <a name="local-caching-of-configuration-values"></a><span data-ttu-id="b3efa-110">Almacenar en caché local los valores de configuración</span><span class="sxs-lookup"><span data-stu-id="b3efa-110">Local Caching of Configuration Values</span></span>  
 <span data-ttu-id="b3efa-111">La solución orientada a servicios utiliza dos objetos, **ConfigPropertyBag** y **ConfigParameters**, para controlar los valores de configuración.</span><span class="sxs-lookup"><span data-stu-id="b3efa-111">The service oriented solution uses two objects, **ConfigPropertyBag** and **ConfigParameters**, to handle the configuration values.</span></span> <span data-ttu-id="b3efa-112">El **ConfigPropertyBag** contiene los valores de clase y se utiliza únicamente por la **ConfigParameters** clase.</span><span class="sxs-lookup"><span data-stu-id="b3efa-112">The **ConfigPropertyBag** class holds the values and is used only by the **ConfigParameters** class.</span></span> <span data-ttu-id="b3efa-113">El **ConfigParameters** clase se utiliza por las otras partes de la solución para recuperar los parámetros de configuración.</span><span class="sxs-lookup"><span data-stu-id="b3efa-113">The **ConfigParameters** class is used by the other parts of the solution to retrieve the configuration parameters.</span></span> <span data-ttu-id="b3efa-114">Ambas clases se encuentran en el **Microsoft.Samples.BizTalk.WoodgroveBank.ConfigHelper** espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="b3efa-114">Both classes are in the **Microsoft.Samples.BizTalk.WoodgroveBank.ConfigHelper** namespace.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b3efa-115">La solución orientada a servicios corrige el intervalo de actualización de caché a 300 segundos (5 minutos).</span><span class="sxs-lookup"><span data-stu-id="b3efa-115">The Service Oriented solution fixes the cache refresh interval at 300 seconds (5 minutes).</span></span> <span data-ttu-id="b3efa-116">No obstante, podría convertir el intervalo de actualización de caché en una propiedad configurable en esta solución.</span><span class="sxs-lookup"><span data-stu-id="b3efa-116">You may, instead, want to make the cache refresh interval itself  a configurable property in this solution.</span></span> <span data-ttu-id="b3efa-117">Esto lo puede hacer en la solución Administración de procesos empresariales.</span><span class="sxs-lookup"><span data-stu-id="b3efa-117">This is done in the Business Process Management solution.</span></span> <span data-ttu-id="b3efa-118">Para obtener más información acerca de cómo controla SSO la solución, vea [usar SSO de forma eficaz en la solución de administración de procesos empresariales](../core/using-sso-efficiently-in-the-business-process-management-solution.md).</span><span class="sxs-lookup"><span data-stu-id="b3efa-118">For more information about how that solution handles SSO, see [Using SSO Efficiently in the Business Process Management Solution](../core/using-sso-efficiently-in-the-business-process-management-solution.md).</span></span> <span data-ttu-id="b3efa-119">Tenga en cuenta que, en tal caso, los cambios en el intervalo de actualización no se hacen efectivos hasta que se actualiza la caché al final del período del intervalo anterior.</span><span class="sxs-lookup"><span data-stu-id="b3efa-119">Notice that, in such a case, a change in the refresh interval does not take effect until the cache is refreshed at the end of the old interval time.</span></span>  
  
 <span data-ttu-id="b3efa-120">El **ConfigPropertyBag** tiene los siguientes métodos:</span><span class="sxs-lookup"><span data-stu-id="b3efa-120">The **ConfigPropertyBag** has the following methods:</span></span>  
  
|<span data-ttu-id="b3efa-121">Método</span><span class="sxs-lookup"><span data-stu-id="b3efa-121">Method</span></span>|<span data-ttu-id="b3efa-122">Description</span><span class="sxs-lookup"><span data-stu-id="b3efa-122">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="b3efa-123">Lectura</span><span class="sxs-lookup"><span data-stu-id="b3efa-123">Read</span></span>|<span data-ttu-id="b3efa-124">Recupera un valor para una propiedad dada.</span><span class="sxs-lookup"><span data-stu-id="b3efa-124">Retrieves a value for a given property.</span></span>|  
|<span data-ttu-id="b3efa-125">Escribir</span><span class="sxs-lookup"><span data-stu-id="b3efa-125">Write</span></span>|<span data-ttu-id="b3efa-126">Asigna un valor a una propiedad.</span><span class="sxs-lookup"><span data-stu-id="b3efa-126">Assigns a value to a property.</span></span>|  
  
 <span data-ttu-id="b3efa-127">La clase utiliza una instancia de .NET **NameValueCollection** para almacenar los valores.</span><span class="sxs-lookup"><span data-stu-id="b3efa-127">The class uses an instance of a .NET **NameValueCollection** to hold the values.</span></span> <span data-ttu-id="b3efa-128">Implementan los métodos de acceso del **IPropertyBag** interfaz desde el **Microsoft.BizTalk.SSOClient.Interop** espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="b3efa-128">The two access methods implement the **IPropertyBag** interface from the **Microsoft.BizTalk.SSOClient.Interop** namespace.</span></span> <span data-ttu-id="b3efa-129">El **ConfigPropertyBag** clase es una clase interna y utiliza únicamente por la **ConfigParameters** clase.</span><span class="sxs-lookup"><span data-stu-id="b3efa-129">The **ConfigPropertyBag** class is an internal class and used only by the **ConfigParameters** class.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b3efa-130">Los nombres de clave en la bolsa de propiedades no distinguen entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="b3efa-130">Key names in the property bag are case insensitive.</span></span> <span data-ttu-id="b3efa-131">Subyacente **NameValueCollection** usa algoritmos hash y comparaciones entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="b3efa-131">The underlying **NameValueCollection** uses case-insensitive hashing and case-insensitive comparisons.</span></span>  
  
 <span data-ttu-id="b3efa-132">La aplicación utiliza el **ConfigParameters** clase para controlar los valores de configuración de SSO.</span><span class="sxs-lookup"><span data-stu-id="b3efa-132">The application uses the **ConfigParameters** class to handle the SSO configuration values.</span></span> <span data-ttu-id="b3efa-133">La clase tiene los siguientes métodos y atributos públicos:</span><span class="sxs-lookup"><span data-stu-id="b3efa-133">The class has the following public methods and attributes:</span></span>  
  
|<span data-ttu-id="b3efa-134">Método o atributo</span><span class="sxs-lookup"><span data-stu-id="b3efa-134">Method or Attribute</span></span>|<span data-ttu-id="b3efa-135">Description</span><span class="sxs-lookup"><span data-stu-id="b3efa-135">Description</span></span>|  
|-------------------------|-----------------|  
|<span data-ttu-id="b3efa-136">SSOConfigParameter</span><span class="sxs-lookup"><span data-stu-id="b3efa-136">SSOConfigParameter</span></span>|<span data-ttu-id="b3efa-137">Enumeración para especificar parámetros de configuración.</span><span class="sxs-lookup"><span data-stu-id="b3efa-137">An enumeration for specifying configuration parameters.</span></span>|  
|<span data-ttu-id="b3efa-138">GetConfigParameters</span><span class="sxs-lookup"><span data-stu-id="b3efa-138">GetConfigParameters</span></span>|<span data-ttu-id="b3efa-139">Método usado para recuperar un valor para un parámetro dado.</span><span class="sxs-lookup"><span data-stu-id="b3efa-139">A method used to retrieve a value for a given parameter.</span></span> <span data-ttu-id="b3efa-140">Utiliza SSOConfigParameter para indicar el parámetro.</span><span class="sxs-lookup"><span data-stu-id="b3efa-140">Uses the SSOConfigParameter to indicate the parameter.</span></span>|  
  
 <span data-ttu-id="b3efa-141">El **ConfigParameters** clase usa la clase Timer de .NET y una función de delegado para configurar la actualización de la **ConfigPropertyBag**:</span><span class="sxs-lookup"><span data-stu-id="b3efa-141">The **ConfigParameters** class uses the .NET Timer class and a delegate function to set up the refresh of the **ConfigPropertyBag**:</span></span>  
  
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
  
 <span data-ttu-id="b3efa-142">Observe que el constructor estático inicializa las variables de miembro estático además de habilitar el uso de los métodos de clase sin crear una instancia de la clase.</span><span class="sxs-lookup"><span data-stu-id="b3efa-142">Notice that the static constructor initializes the static member variables thus enabling the use of class methods without creating an instance of the class.</span></span> <span data-ttu-id="b3efa-143">El constructor crea instancias de almacén de configuración de SSO (**ISSOConfigStore**), la bolsa de propiedades de configuración (**ConfigPropertyBag**) y un bloqueo de sincronización ( **ReaderWriterLock**) permiten controlar el acceso a la **ConfigurationPropertyBag** durante las actualizaciones y lecturas.</span><span class="sxs-lookup"><span data-stu-id="b3efa-143">The constructor creates instances of the SSO configuration store (**ISSOConfigStore**), the configuration property bag (**ConfigPropertyBag**), and a synchronization lock (**ReaderWriterLock**) used to control access to the **ConfigurationPropertyBag** during updates and reads.</span></span> <span data-ttu-id="b3efa-144">A continuación, utiliza el constructor **GetConfigInfo** para recuperar los valores de configuración de SSO y colocarlos en la bolsa de propiedades.</span><span class="sxs-lookup"><span data-stu-id="b3efa-144">The constructor then uses **GetConfigInfo** to retrieve the SSO configuration values and to put them in the property bag.</span></span> <span data-ttu-id="b3efa-145">Por último, el constructor crea un **temporizador** objeto que, después del intervalo especificado, llama a la función de delegado, **cacheRefreshCallback**.</span><span class="sxs-lookup"><span data-stu-id="b3efa-145">Finally, the constructor creates a **Timer** object that, after the specified interval, calls the delegate function, **cacheRefreshCallback**.</span></span>  
  
 <span data-ttu-id="b3efa-146">El **temporizador** función de delegado es bastante sencillo:</span><span class="sxs-lookup"><span data-stu-id="b3efa-146">The **Timer** delegate function is relatively straightforward:</span></span>  
  
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
  
 <span data-ttu-id="b3efa-147">Tenga en cuenta que el método de devolución de llamada de actualización de caché deshabilita el temporizador para que el método se pueda ejecutar por completo.</span><span class="sxs-lookup"><span data-stu-id="b3efa-147">Notice that the cache refresh callback method disables the timer so that the method can run all the way through.</span></span> <span data-ttu-id="b3efa-148">Tenga también en cuenta el uso de bloqueos para controlar el acceso a la bolsa de propiedades.</span><span class="sxs-lookup"><span data-stu-id="b3efa-148">Also notice the use of the locks to control access to the property bag.</span></span> <span data-ttu-id="b3efa-149">El **ReaderWriterLock** es la mejor opción, se diseñó para casos donde hay más lecturas que escrituras.</span><span class="sxs-lookup"><span data-stu-id="b3efa-149">The **ReaderWriterLock** is the best choice here—it is designed for cases where there are more reads than writes.</span></span> <span data-ttu-id="b3efa-150">Observe también que el bloqueo, **syncLock**, es estático y declara la clase que todos los subprocesos comparten la misma instancia única del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="b3efa-150">Notice also that the lock, **syncLock**, is static and declared at the class level that all threads share the same, single instance of it.</span></span>  
  
## <a name="using-sso-from-code"></a><span data-ttu-id="b3efa-151">Usar SSO desde código</span><span class="sxs-lookup"><span data-stu-id="b3efa-151">Using SSO from Code</span></span>  
 <span data-ttu-id="b3efa-152">Cuando se utiliza un inicio de sesión único desde el código, el código debe asumir la función del adaptador: es decir, recuperar el vale de SSO desde el mensaje, canjear el vale para obtener el nombre de usuario y la contraseña para el sistema back-end y, por último, utilice el sistema back-end.</span><span class="sxs-lookup"><span data-stu-id="b3efa-152">When using single sign-on from code, the code must take on the role of the adapter: that is,retrieve the SSO ticket from the message, redeem the ticket to get the user name and password for the back-end system, and, finally, use the back-end system.</span></span> <span data-ttu-id="b3efa-153">La solución orientada a servicios hace esto mediante la **GetPendingTransactionsResponse** método de la **PendingTransactionsCaller** objeto.</span><span class="sxs-lookup"><span data-stu-id="b3efa-153">The service-oriented solution does this through the **GetPendingTransactionsResponse** method of the **PendingTransactionsCaller** object.</span></span>  
  
 <span data-ttu-id="b3efa-154">El método se muestra de la siguiente forma:</span><span class="sxs-lookup"><span data-stu-id="b3efa-154">The method appears as follows:</span></span>  
  
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
  
 <span data-ttu-id="b3efa-155">El método comienza recuperando la información de configuración, incluida la dirección URL, para el sistema servidor y el nombre de la aplicación servidor (afiliada).</span><span class="sxs-lookup"><span data-stu-id="b3efa-155">The method begins by retrieving configuration information, including the URL, for the back-end system and the name of the backend (affiliate) application.</span></span>  
  
 <span data-ttu-id="b3efa-156">Para canjear el vale, el método debe extraer el vale y el nombre de usuario original de la solicitud del mensaje.</span><span class="sxs-lookup"><span data-stu-id="b3efa-156">To redeem the ticket, the method must extract the ticket and original requesting user name from the message.</span></span> <span data-ttu-id="b3efa-157">El mensaje contiene el vale como una de las propiedades de contexto de mensaje, **BTS. SSOTicket**.</span><span class="sxs-lookup"><span data-stu-id="b3efa-157">The message contains the ticket as one of the message context properties, **BTS.SSOTicket**.</span></span> <span data-ttu-id="b3efa-158">Para obtener más información, consulte **propiedades de contexto de mensaje** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span><span class="sxs-lookup"><span data-stu-id="b3efa-158">For more information, see **Message Context Properties** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span> <span data-ttu-id="b3efa-159">El método también extrae el **OriginatorSID** desde las propiedades de contexto de mensaje.</span><span class="sxs-lookup"><span data-stu-id="b3efa-159">The method also extracts the **OriginatorSID** from the message context properties.</span></span> <span data-ttu-id="b3efa-160">Con el vale y el nombre del originador, el método llama al método RedeemTicket en el vale para recuperar las credenciales.</span><span class="sxs-lookup"><span data-stu-id="b3efa-160">With the ticket and the originator's name in hand, the method calls the RedeemTicket method on the ticket to retrieve the credentials.</span></span>  
  
 <span data-ttu-id="b3efa-161">El resto del código crea la caché NetworkCredential de .NET para las credenciales y llama al servicio Web servidor.</span><span class="sxs-lookup"><span data-stu-id="b3efa-161">The remainder of the code creates a .NET NetworkCredential cache for the credentials and calls the back-end Web service.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b3efa-162">Puesto que el nombre de usuario y la contraseña se devuelven desde SSO en forma de texto visible, se recomienda reducir la duración de las variables que contienen dicha información.</span><span class="sxs-lookup"><span data-stu-id="b3efa-162">Because the user name and password come back from SSO in clear text, you want to minimize the lifetime of variables holding that information.</span></span> <span data-ttu-id="b3efa-163">Tenga en cuenta que el código declara las variables de credencial dentro de un **intente** bloque.</span><span class="sxs-lookup"><span data-stu-id="b3efa-163">Notice that the code declares the credential variables within a **try** block.</span></span> <span data-ttu-id="b3efa-164">En este caso, las variables caducan al salir de la **intente** bloque.</span><span class="sxs-lookup"><span data-stu-id="b3efa-164">Here, the variables expire upon exit from the **try** block.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3efa-165">Vea también</span><span class="sxs-lookup"><span data-stu-id="b3efa-165">See Also</span></span>  
 [<span data-ttu-id="b3efa-166">Aspectos destacados de la implementación del servicio en la solución orientada a servicios</span><span class="sxs-lookup"><span data-stu-id="b3efa-166">Implementation Highlights of the Service Oriented Solution</span></span>](../core/implementation-highlights-of-the-service-oriented-solution.md)