---
title: 'Paso 3: Implementar la conexión para el adaptador de Echo | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dc223901-3ad3-4e71-8672-fea6bb4efe65
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 15749fdca84508654fc915fff0c1abe7008de2f3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988413"
---
# <a name="step-3-implement-the-connection-for-the-echo-adapter"></a>Paso 3: Implementar la conexión para el adaptador de Echo
![Paso 3 de 9](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-3of9.gif "Step_3of9")  

 **Tiempo en completarse:** 45 minutos  

 En este paso, implementará la capacidad de conexión del adaptador de Echo. Según el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], debe implementar las siguientes clases abstractas e interfaces al conectarse al sistema de destino.  

- `Microsoft.ServiceModel.Channels.Common.ConnectionUri`  

- `Microsoft.ServiceModel.Channels.Common.IConnection`  

- `Microsoft.ServiceModel.Channels.Common.IConnectionFactory`  

  En lugar de derivar desde la anterior abstractas de clases e interfaces, la [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)] genera automáticamente las tres clases derivadas, EchoAdapterConnection, EchoAdapterConnectionUri y EchoAdapterConnectionFactory. Además de crear las clases, cada uno tiene un método predeterminado que se produce una excepción concreta, `System.NotImplementedException`.  Esta instrucción le recuerda a los desarrolladores implementar cada clase.  Cuando se implementa la clase, esta instrucción generadoras de excepciones se debe quitar.  

  En la siguiente sección, va a actualizar esas tres clases para obtener una mejor comprensión de cómo administrar una conexión, ¿qué es la estructura URI y cómo recuperar mediante programación los distintos elementos URI y, a continuación, usar esos elementos en el adaptador.  

## <a name="prerequisites"></a>Requisitos previos  
 Antes de comenzar este paso, debe haber completado correctamente [paso 2: clasificar las propiedades de conexión y adaptador](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-2-categorize-the-adapter-and-connection-properties.md). Y debe tener una idea clara de los `Microsoft.ServiceModel.Channels.Common.IConnection`, `Microsoft.ServiceModel.Channels.Common.IConnectionFactory`, y `Microsoft.ServiceModel.Channels.Common.ConnectionUri` clases.  

## <a name="connection-related-classes"></a>Clases relacionadas con la conexión  
 El [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)] genera tres clases derivadas, EchoAdapterConnection, EchoAdapterConnectionUri y EchoAdapterConnectionFactory. A continuación proporciona una breve descripción de los métodos asociados a cada uno.  

### <a name="echoadapterconnection"></a>EchoAdapterConnection  
 Según la complejidad del adaptador, que tenga que implementar todos los métodos siguientes de cinco. Adaptador de Echo, la mayoría no se admite, porque el ejemplo de adaptador de Echo no implica ningún sistema de destino.  

|**Método**|**Descripción**|  
|----------------|---------------------|  
|Cerrar void público (tiempo de espera TimeSpan)|Cierra la conexión al sistema de destino. El adaptador de Echo usa este método para agregar solo los eventos de seguimiento a la escucha de seguimiento.|  
|public bool IsValid (tiempo de espera TimeSpan)|Devuelve un valor que indica si la conexión sigue siendo válida.<br /><br /> No admite el adaptador de Echo.|  
|Abrir void público (tiempo de espera TimeSpan)|Se abre la conexión al sistema de destino.<br /><br /> No disponible para el adaptador de Echo. Sin embargo, en el ejemplo se muestra cómo usar un elemento URI llamado enableAuthentication para exigir que los usuarios proporcionar un nombre de usuario.|  
|ClearContext() void público|Borra el contexto de la conexión. Este método se llama cuando la conexión se vuelve a establecer el grupo de conexiones.<br /><br /> No admite el adaptador de Echo.|  
|Abort() void público|Anula la conexión al sistema de destino.<br /><br /> No admite el adaptador de Echo.|  

### <a name="echoadapterconnectionfactory"></a>EchoAdapterConnectionFactory  
 El generador de conexiones es responsable de crear la conexión. De forma predeterminada, debe modificar esta clase únicamente al conectarse a un sistema de destino. Aunque el adaptador de Echo no implica ningún sistema de destino, muestra cómo usar un elemento URI personalizado llamado enableAuthentication si la conexión requiere autenticación de usuario.  

> [!NOTE]
>  El enableAuthentication no es una palabra clave, es un nombre de variable. Por lo tanto, puede elegir cualquier nombre para ella.  

### <a name="echoadapterconnectionuri"></a>EchoAdapterConnectionUri  
 Representa una cadena de conexión al sistema de destino.  


|               **Método**               |                                                                                                                                       **Descripción**                                                                                                                                        |
|----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|        Uri de Uri de invalidación públicas         |                                                                                                    Obtiene y establece el identificador Uri. Obtiene para generar la cadena de Uri y se establece para analizar la cadena de Uri.                                                                                                     |
|   EchoAdapterConnectionUri() pública    |                                                                                                                    Inicializa una nueva instancia de la clase ConnectionUri.                                                                                                                    |
| cadena de invalidación públicas SampleUriString | Devuelve EchoAdapter.SCHEME + ": //{hostname}/{application}?enableAuthentication={True&#124;False}".<br /><br /> Esta cadena de valor devuelta se muestra como el **ejemplo** en el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] herramienta, tal como se muestra en la ilustración siguiente. |

 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/e4b9d0b8-f07f-4342-815f-9ef1507b0980.gif "e4b9d0b8-f07f-4342-815f-9ef1507b0980")  

## <a name="echo-adapter-connection-uri"></a>URI de conexión de adaptador de echo  
 La conexión del adaptador de Echo ejemplo URI se describe como: EchoAapter.SCHEME://{hostname}/{application}?enableAuthentication={true&#124;false}  

 Puesto que la EchoAapter.SCHEME es echov2, la conexión URI es:  

 echo2: / / lobhostname/lobapplication? enableAuthentication = {true&#124;false}  

 Puede leer el URI de conexión anterior cuando enableAuthentication = false como sigue:  

 El esquema de transporte echov2, vaya a un equipo denominado lobhostname, donde una aplicación denominada lobapplication que no requiere ninguna autenticación está esperando la conexión.  

 O, cuando enableAuthentication = true, la conexión de lectura como sigue:  

 El esquema de transporte echov2, vaya a un equipo denominado lobhostname, donde una aplicación denominada lobapplication espera que la autenticación está esperando la conexión. Para el adaptador de Echo, se requiere sólo un nombre de usuario.  

 Con un URI definido, puede consumir mediante programación y analizarlo para conectividad y la configuración. Si la conexión requiere datos confidenciales, como un nombre de usuario y una contraseña, no tienen dicha información en el URI. En su lugar, agregue dicha información en el `System.ServiceModel.Description.ClientCredentials` objeto. El ejemplo de código que agregue muestra cómo hacerlo.  

 En el código siguiente, el adaptador de Echo construye el URI de dos maneras para mostrarle cómo el adaptador puede usar diversos elementos URI para modificar la característica de adaptador.  

 echo2://lobhostname/lobapplication?enableAuthentication=[true&#124;false]  

 echo2://lobhostname/lobapplication?enableAuthentication=[true&#124;false]&echoInUpperCase=true  

### <a name="retrieving-the-uri-element"></a>Recupera el elemento de URI  
 Puede analizar cada elemento URI en el adaptador de Echo URI echo2: / / lobhostname/lobapplication? enableAuthentication = false & echoInUpperCase = false.  En la tabla siguiente se enumeran los valores de elemento URI y los métodos asociados:  

|**Valor del elemento URI**|**Método**|  
|---------------------------|----------------|  
|lobhostname|`System.Uri.Host%2A` para recuperar el nombre de host|  
|Lobapplication|`System.Uri.AbsolutePath%2A` para recuperar el nombre de la aplicación de destino|  
|enableAuthentation = false|GetQueryStringValue("enableAuthentication")<br /><br /> Utilice este elemento URI para validar las credenciales de usuario **Nota:** GetQueryStringValue es un método estático definido en el `Microsoft.ServiceModel.Channels.Common.ConnectionUri`|  
|echoInUpperValue = false|GetQueryStringValue("echoInUpperValue")<br /><br /> Utilice este elemento URI para convertir la cadena entrante a mayúsculas.|  

### <a name="enableauthentication-uri-element"></a>Elemento EnableAuthentication URI  
 El sistema de destino a menudo requiere que proporcione las credenciales del cliente para establecer una conexión con el sistema de destino. Como se mencionó, el adaptador de Echo no implica ningún sistema de destino. Aunque como ejemplo, muestra cómo usar un elemento URI personalizado llamado enableAuthentication para proporcionar las credenciales.  

```  
 public class EchoAdapterConnection : IConnection   
{  
….  
   public void Open(TimeSpan timeout)  
  {  
    // only validate the credentials if EnableAuthentication  
    // connection property value is true  
    if (this.ConnectionFactory.ConnectionUri.EnableAuthentication)  
    {  
        // this adapter expects a value in username  
        if (this.connectionFactory.ClientCredentials != null &&  
            string.IsNullOrEmpty(this.connectionFactory.ClientCredentials.UserName.UserName))  
        {  
            throw new CredentialsException("Username is expected.");  
        }  
  }  
}  
```  

 El código comprueba si enableAuthentication es true, y si no se proporciona un nombre de usuario; Si no se proporciona un nombre de usuario, produce una excepción, que ha sido detectada por el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] herramienta, tal como se muestra a continuación:  

 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/901095c7-c70d-491a-a1ae-8f37f22a61a7.gif "901095c7-c70d-491a-a1ae-8f37f22a61a7")  

 Para proporcionar el nombre de usuario, puede escribirla en el cuadro de diálogo Configurar el adaptador el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] herramienta, tal como se muestra en la ilustración siguiente:  

 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/e4069a7d-1403-4195-b0b5-21ad97dbc3ce.gif "e4069a7d-1403-4195-b0b5-21ad97dbc3ce")  

### <a name="echoinuppercase-uri-element"></a>Elemento EchoInUpperCase URI  
 Puede hacer referencia a elemento EchoInUpperCase URI como una marca booleana. Si la marca es true, el adaptador convierte la cadena de entrada de la operación EchoStrings en mayúsculas.  

 Para cambiar el valor predeterminado del elemento URI echoInUpperCase, use la ficha de propiedades del URI de configurar el adaptador en el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], tal y como se muestra a continuación.  

 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/f22511b2-3fca-4875-ac65-8e61f4367e94.gif "f22511b2-3fca-4875-ac65-8e61f4367e94")  

## <a name="updating-echoadapterconnection"></a>Actualizando EchoAdapterConnection  
 Implemente el método IsValid, apertura y cierre de la clase EchoAdapterConnection.  

#### <a name="to-update-the-echoadapterconnection-class"></a>Para actualizar la clase EchoAdapterConnection  

1.  En **el Explorador de soluciones**, haga doble clic en el **EchoAdapterConnection.cs** archivo.  

2.  En el editor de Visual Studio, el botón secundario en cualquier lugar dentro del editor, en el menú contextual, elija **esquematización**y, a continuación, haga clic en **Detener esquematización**.  

3.  En el editor de Visual Studio, busque el **IsValid** método. Dentro de la **IsValid** método, reemplace la implementación existente por el siguiente:  

    ```csharp  
    return true;  
    ```  

4.  En el editor de Visual Studio, busque el **abierto** método. Dentro de la **abierto** método, reemplace la implementación existente con la siguiente implementación. Esto muestra cómo usar el elemento URI enableAuthentication para asegurarse de que se proporciona el nombre de usuario:  

    ```csharp  
    // only validate the credentials if EnableAuthentication  
    // connection property value is true  
    if (this.ConnectionFactory.ConnectionUri.EnableAuthentication)  
    {  
        // this adapter expects a value in username  
        // it just logs the credentials in the trace file  
        if (this.connectionFactory.ClientCredentials != null &&  
            string.IsNullOrEmpty(this.connectionFactory.ClientCredentials.UserName.UserName))  
        {  
            throw new CredentialsException("Username is expected.");  
        }  
        // got the username, log it in trace file  
        EchoAdapterUtilities.Trace.Trace(System.Diagnostics.TraceEventType.Information, "EchoAdapterConnection::Open", "Username is " + this.connectionFactory.ClientCredentials.UserName.UserName);  
    }  
    EchoAdapterUtilities.Trace.Trace(System.Diagnostics.TraceEventType.Information, "EchoAdapterConnection::Open", "Connection successfully established!");  
    ```  

5.  En el editor de Visual Studio, busque el **cerrar** método. Dentro de la **cerrar** método, agregue la siguiente instrucción única:  

    ```csharp  
    EchoAdapterUtilities.Trace.Trace(System.Diagnostics.TraceEventType.Information, "EchoAdapterConnection::Close", "Connection successfully closed!");  
    ```  

## <a name="updating-the-echoadapterconnectionfactory"></a>Actualizando el EchoAdapterConnectionFactory  
 Implemente el constructor EchoAdapterConnectionFactory y agregar dos propiedades denominadas ClientCredentials y ConnectionUri.  

#### <a name="to-update-the-echoadapterconnectionfactory-class"></a>Para actualizar la clase EchoAdapterConnectionFactory  

1.  En **el Explorador de soluciones**, haga doble clic en el **EchoAdapterConnectionFactory.cs** archivo.  

2.  En el editor de Visual Studio, el botón secundario en cualquier lugar dentro del editor, en el menú contextual, elija **esquematización**y, a continuación, haga clic en **Detener esquematización**.  

3.  En el editor de Visual Studio, busque el **campos privados** región. Agregue la siguiente instrucción única:  

    ```csharp  
    private EchoAdapterConnectionUri connectionUri;  
    ```  

     La lista de campos privados debe coincidir con lo siguiente:  

    ```csharp  
    // Stores the client credentials  
    private ClientCredentials clientCredentials;  
    // Stores the adapter class  
    private EchoAdapter adapter;  
    private EchoAdapterConnectionUri connectionUri;  
    ```  

4.  En el editor de Visual Studio, busque el **EchoAdapterConnectionFactory** método. Dentro de la **EchoAdapterConnectionFactory** método de constructor, antes de "}", agregue la siguiente instrucción única como la última instrucción.  

    ```csharp  
    this.connectionUri = connectionUri as EchoAdapterConnectionUri;  
    ```  

     La implementación de la **EchoAdapterConnectionFactory** método debe coincidir con lo siguiente:  

    ```csharp  
    /// <summary>  
    /// Initializes a new instance of the EchoAdapterConnectionFactory class  
    /// </summary>  
    public EchoAdapterConnectionFactory(ConnectionUri connectionUri  
        , ClientCredentials clientCredentials  
        , EchoAdapter adapter)  
    {  
        this.clientCredentials = clientCredentials;  
        this.adapter = adapter;  
        //added  
        this.connectionUri = connectionUri as EchoAdapterConnectionUri;  
    }  
    ```  

5.  En el editor de Visual Studio, busque el **propiedades públicas** región. Agregue el código siguiente:  

    ```csharp  
    /// <summary>  
    /// Returns the client credentials  
    /// </summary>  
    public ClientCredentials ClientCredentials  
    {  
        get  
        {  
            return this.clientCredentials;  
        }  
    }  

    /// <summary>  
    /// Returns the Connection Uri for this adapter  
    /// </summary>  
    public EchoAdapterConnectionUri ConnectionUri  
    {  
        get  
        {  
            return this.connectionUri;  
        }  
    }  
    ```  

## <a name="updating-the-echoadapterconnectionuri"></a>Actualizando el EchoAdapterConnectionUri  
 Implemente el constructor predeterminado de EchoAdapterConnectionUri y EchoAdapterConnectionUri(Uri uri) sobrecargar el constructor público invalidar la propiedad Uri Uri.  

#### <a name="to-update-the-echoadapterconnectionuri-class"></a>Para actualizar la clase EchoAdapterConnectionUri  

1.  En **el Explorador de soluciones**, haga doble clic en el **EchoAdapterConnectionUri.cs** archivo.  

2.  En el editor de Visual Studio, el botón secundario en cualquier lugar dentro del editor, en el menú contextual, elija **esquematización**y, a continuación, haga clic en **Detener esquematización**.  

3.  En el editor de Visual Studio, busque el **constructores** región. Dentro de la **EchoAdapterConnectionUri()** un constructor predeterminado, agregue la siguiente instrucción:  

    ```csharp  
    Uri = new Uri("echov2://lobhostname/lobapplication?enableauthentication=False");  
    ```  

4.  En el editor de Visual Studio, dentro de la **EchoAdapterConnectionUri (uri del identificador Uri)** sobrecarga de constructor y agregue la siguiente instrucción:  

    ```csharp  
    Uri = uri;  
    ```  

     La implementación del método EchoAdapterConnectionUri(Uri uri) debería que coincida con el siguiente:  

    ```csharp  
    public EchoAdapterConnectionUri(Uri uri)  
        : base()  
    {  
        Uri = uri;  
    }  
    ```  

5.  En el editor de Visual Studio, dentro de la **público invalidar Uri Uri** método, reemplace el existente con la lógica siguiente. La operación get basa el Uri con echoInUpperCase o sin él. El conjunto analiza el identificador URI para recuperar el nombre de host, nombre de la base de datos y los valores de consulta.  

    ```csharp  
    get  
    {  
        // Build the uri  
        if (String.IsNullOrEmpty(this.hostname)) throw new InvalidUriException("Invalid target system host name.");  
        if (String.IsNullOrEmpty(this.application)) throw new InvalidUriException("Invalid target system data source name.");  
        if (EchoInUpperCase)  
        {  
            // build the uri with echoInUpperCase= query string  
            return new Uri(EchoAdapter.SCHEME + "://" + Hostname + "/" + Application + "?" + "enableAuthentication=" + EnableAuthentication + "&" + "echoInUpperCase=" + echoInUpperCase);  
        }  
        else  
        {  
            // build the uri without echoInUpperCase= query string  
            return new Uri(EchoAdapter.SCHEME + "://" + Hostname + "/" + Application + "?" + "enableAuthentication=" + EnableAuthentication);  
        }  
    }  
    set  
    {  
        // Parse the uri  
        String[] enableAuthValue = GetQueryStringValue(value, "enableAuthentication");  
        if (enableAuthValue.Length > 0) this.enableAuthentication = Boolean.Parse(enableAuthValue[0]);  
        String[] echoInUpperValue = GetQueryStringValue(value, "echoInUpperCase");  
        if (echoInUpperValue.Length > 0) this.echoInUpperCase = Boolean.Parse(echoInUpperValue[0]);  

        this.hostname = value.Host;  
        String[] applicationValue = value.AbsolutePath.Split('/');  
        if (applicationValue.Length > 1) this.Application = applicationValue[1];  
    }  
    ```  

6.  En Visual Studio, en el **archivo** menú, haga clic en **guardar todo**.  

7.  En el menú **Compilar** , haga clic en **Compilar solución**. Debe compilar correctamente el proyecto. Si no, asegúrese de que ha seguido todos los pasos anteriores.  

> [!NOTE]
>  Ya ha guardado su trabajo. Puede cerrar Visual Studio en este momento o vaya al paso siguiente, de forma segura [paso 4: implementar el controlador de examinar los metadatos para el adaptador de Echo](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-4-implement-the-metadata-browse-handler-for-the-echo-adapter.md).  

## <a name="what-did-i-just-do"></a>¿Qué simplemente hacer?  
 Implementa la conexión para el adaptador de Echo. Ha obtenido información sobre los componentes de conexión de la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], la estructura básica de la conexión URI, cómo analizar mediante programación los elementos del identificador URI y cómo puede usar el elemento URI para cambiar la función de adaptador.  

## <a name="next-steps"></a>Pasos siguientes  
 Implementar metadatos exploración, búsqueda y resolver las capacidades y el intercambio de mensajes salientes. Por último, compilar e implementar el adaptador.  

## <a name="see-also"></a>Vea también  
 [Paso 4: Implementar el controlador de exploración de metadatos para el adaptador de Echo](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-4-implement-the-metadata-browse-handler-for-the-echo-adapter.md)   
 [Tutorial 1: Desarrollar el adaptador de Echo](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)