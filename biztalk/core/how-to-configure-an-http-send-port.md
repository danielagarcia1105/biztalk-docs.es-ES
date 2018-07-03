---
title: Cómo configurar un puerto de envío HTTP | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send ports, HTTP adapters
- HTTP adapters, send ports
- configuring [HTTP adapters], send ports
ms.assetid: 29c6868c-4570-4375-9494-08c07220eeb3
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0c5195f4cae1e7968f1a691ea177ffa5d65f9653
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011069"
---
# <a name="how-to-configure-an-http-send-port"></a>Cómo configurar un puerto de envío HTTP
Un puerto de envío HTTP se puede configurar mediante programación o mediante la consola de administración de BizTalk Server.  
  
## <a name="configure-an-http-send-port-programmatically"></a>Configurar un puerto de envío HTTP mediante programación
  
 El adaptador de HTTP almacena la información de configuración en la base de datos de administración de BizTalk (también conocida como la base de datos de configuración). La información de configuración se almacena en una bolsa de propiedades XML personalizada. Durante la inicialización del adaptador de HTTP y durante su tiempo de ejecución, el servidor pasa la configuración al adaptador del modo siguiente:  
  
- Para el controlador de envío HTTP, la información de configuración se pasa al adaptador llamando el **carga** método de la **IPersistPropertyBag** interfaz.  
  
- Para los puertos de envío HTTP, la información de configuración se pasa al adaptador como un conjunto de propiedades en un contexto de mensaje. El espacio de nombres HTTP agrupa estas propiedades.  
  
  El modelo de objetos del Explorador de BizTalk expone la interfaz de configuración del adaptador `ItransportInfo` para los puertos de envío, que contiene la propiedad de lectura y escritura `TransportTypeData`. Esta propiedad acepta la bolsa de propiedades de configuración del puerto de envío HTTP como una cadena XML de par nombre/valor. Tenga en cuenta que para establecer esta propiedad en el modelo de objetos del explorador de BizTalk, debe definirse en el `Address` propiedad de la **ITransportInfo** interfaz.  
  
  Establecer el **TransportTypeData** propiedad de la **ITransportInfo** interfaz no es necesaria. Si no se establece, el adaptador de HTTP utilizará los valores predeterminados del controlador de envío HTTP.  
  
  Si no se definen las propiedades de configuración del puerto de envío que duplican la configuración del controlador, se utilizan las propiedades de configuración del controlador. Si el controlador de envío HTTP no tiene valores de configuración, el adaptador de envío HTTP registra un error en el registro de sucesos y mueve el mensaje al adaptador de copia de seguridad.  
  
  Puede establecer propiedades de configuración mediante programación en un contexto de mensaje. Estas propiedades se pueden establecer en una programación de orquestación de BizTalk Server o en componentes de canalización personalizados. Las reglas siguientes se aplican cuando se utilizan estas propiedades:  
  
- Si la propiedad de configuración se establece en una orquestación o en un componente de canalización personalizado en una canalización de recepción, entonces:  
  
  -   Si se envía un mensaje a un puerto de envío estático, el valor de la propiedad se sobrescribirá con el valor configurado para dicho puerto de envío.  
  
  -   Si el mensaje se envía a un puerto de envío dinámico, el valor de la propiedad no se sobrescribirá.  
  
- Si la propiedad de configuración se establece en un componente de canalización personalizado de una canalización de envío, entonces:  
  
  -   El valor no se sobrescribirá independientemente de que el mensaje se envíe a un puerto de envío estático o dinámico.  
  
  En la siguiente tabla se enumeran las propiedades de configuración que se pueden establecer en el modelo de objetos del Explorador de BizTalk para la ubicación de envío HTTP.  
  
|Nombre de propiedad|Tipo|Descripción|Restrictions|Comentarios|  
|-------------------|----------|-----------------|------------------|--------------|  
|**RequestTimeout**|xs:int|Período de tiempo de espera de una respuesta del servidor. Si se establece como cero (0), el sistema calcula el tiempo de espera en función del tamaño del mensaje de solicitud.|**Valor mínimo:** 0<br /><br /> **Valor máximo:** MAX_LONG|**Valor predeterminado:** 0|  
|**ContentType**|xs:string|Tipo de contenido de los mensajes de solicitud.|**Longitud mínima:** 0<br /><br /> **Longitud máxima:** 256|**Valor predeterminado:** Text/XML|  
|**MaxRedirects**|xs:int|Número máximo de veces que el adaptador de HTTP puede redirigir la solicitud.|**Valor mínimo:** 0<br /><br /> **Valor máximo:** 10|**Valor predeterminado:** 5|  
|**UseHandlerProxySettings**|xs:boolean|Especifica si el puerto de envío HTTP utilizará la configuración del servidor proxy para el controlador de envío.|None|**Valor predeterminado:** True<br /><br /> Cuando se establece como true, el puerto de envío utilizará la configuración del proxy en el nivel del controlador. Cuando se establece como false, el adaptador de envío utilizará la información del proxy especificado en el puerto de envío.|  
|**UseProxy**|xs:boolean|Especifica si el adaptador de HTTP utilizará el servidor proxy. Todos los puertos de envío HTTP pueden compartir el servidor proxy.|None|**Valor predeterminado:** False<br /><br /> Esta propiedad se omite si **UseHandlerProxySettings** es **True**.|  
|**ProxyName**|xs:string|Especifica el nombre del servidor proxy.|**Longitud mínima:** 0<br /><br /> **Longitud máxima:** 256|**Valor predeterminado:** vacía<br /><br /> El adaptador de envío HTTP omite esta propiedad si el **UseHandlerProxySettings** propiedad está establecida en **True**. En caso contrario, HTTP adaptador de envío utiliza esta propiedad sólo si **UseProxy** es **True**. Esta propiedad es necesaria si **UseProxy** es **True**.|  
|**ProxyPort**|xs:int|Especifica el puerto del servidor proxy.|**Valor mínimo:** 0<br /><br /> **Valor máximo:** 65535|**Valor predeterminado:** 80<br /><br /> El adaptador de envío HTTP omite esta propiedad si **UseHandlerProxySettings** es **True**. En caso contrario, HTTP adaptador de envío utiliza esta propiedad sólo si **UseProxy** es **True**. Esta propiedad es necesaria si **UseProxy** es **True**.|  
|**ProxyUsername**|xs:string|Especifica el nombre de usuario para la autenticación con el servidor proxy.|**Longitud mínima:** 0<br /><br /> **Longitud máxima:** 256|**Valor predeterminado:** vacía<br /><br /> El adaptador de envío HTTP omite esta propiedad si **UseHandlerProxySettings** es **True**. En caso contrario, HTTP adaptador de envío utiliza esta propiedad sólo si **UseProxy** es **True**.|  
|**ProxyPassword**|xs:string|Especifica la contraseña de usuario para la autenticación con el servidor proxy.|**Longitud mínima:** 0<br /><br /> **Longitud máxima:** 256|**Valor predeterminado:** vacía<br /><br /> El adaptador de envío HTTP omite esta propiedad si **UseHandlerProxySettings** es **True**. En caso contrario, HTTP adaptador de envío utiliza esta propiedad sólo si **UseProxy** es **True**.|  
|**AuthenticationScheme**|xs:string|Tipo de autenticación que se utiliza con el servidor de destino.|None|**Valores válidos:**<br /><br /> -   **Anónima (predeterminada)**<br />-   **Básico**<br />-   **Resumen**<br />-   **Kerberos**|  
|**Nombre de usuario**|xs:string|Nombre de usuario que se utiliza para la autenticación con el servidor.|**Longitud mínima:** 0<br /><br /> **Longitud máxima:** 256|**Valor predeterminado:** vacía<br /><br /> Este valor es obligatorio si selecciona **básica** o **Digest** autenticación. El adaptador de HTTP omite el valor de esta propiedad si **UseSSO** es **True**.|  
|**Contraseña**|xs:string|Contraseña de usuario que se usará para la autenticación con el servidor.|**Longitud mínima:** 0<br /><br /> **Longitud máxima:** 256|**Valor predeterminado:** vacía<br /><br /> Este valor es obligatorio si selecciona **básica** o **Digest** autenticación. El valor de esta propiedad se omite si **UseSSO** es **True**.|  
|**EnableChunkedEncoding**|xs:boolean|Especifica si el adaptador de HTTP utiliza codificación fragmentada.|None|**Valor predeterminado:**<br /><br /> True|  
|**Certificado**|xs:string|Huella digital del certificado de cliente SSL.|**Longitud mínima:** 0<br /><br /> **Longitud máxima:** 59|**Valor predeterminado:** vacía|  
|**UseSSO**|xs:boolean|Especifica si SSO se utilizará para el puerto de envío.|None|**Valor predeterminado:** False|  
|**AffiliateApplicationName**|xs:string|Nombre de la aplicación afiliada que se utilizará para el inicio de sesión único.|**Longitud mínima:** 0<br /><br /> **Longitud máxima:** 256|**Valor predeterminado:** vacía<br /><br /> Es necesario si **UseSSO** es **True**.|  
  
 En el siguiente código se muestra la cadena XML que se utilizará para establecer estas propiedades:  
  
```  
<CustomProps>  
   <ContentType vt="8">text/xml</ContentType>  
   <RequestTimeout vt="3">0</RequestTimeout>  
   <MaxRedirects vt="3">5</MaxRedirects>  
   <UseHandlerProxySettings vt="8">-1</UseHandlerProxySettings>  
   <UseProxy vt="8">-1</UseProxy>  
   <ProxyName vt="8">sdfsd</ProxyName>  
   <ProxyPort vt="3">80</ProxyPort>  
   <ProxyUsername vt="8">Somename</ProxyUsername>  
   <ProxyPassword vt="8">Somepassword</ProxyPassword>  
   <AuthenticationScheme vt="8">Basic</AuthenticationScheme>  
   <Username vt="8">Somename</Username>  
   <Password vt="8">Somepassword</Password>  
   <EnableChunkedEncoding vt="11">1</EnableChunkedEncoding>  
   <Certificate vt="8">AAAA BBBB CCCC DDDD</Certificate>  
   <UseSSO vt="11">0</UseSSO>  
   <AffiliateApplicationName vt="8">Name</AffiliateApplicationName>  
</CustomProps>  
```  
  
## <a name="configure-an-http-send-port-with-the-biztalk-server-administration-console"></a>Configurar un puerto de envío HTTP con la consola de administración de BizTalk Server
  
 Se pueden establecer variables del adaptador de puerto de envío HTTP en la consola de administración de BizTalk Server. Si no se establecen las propiedades para el puerto de envío, se utilizan los valores predeterminados del controlador de envío establecidos en la consola de administración de BizTalk Server.  
  
> [!NOTE]
>  Las propiedades de configuración que se describen en este tema son comunes a los puertos de envío HTTP unidireccionales y de solicitud-respuesta.  
  
1.  En la consola de administración de BizTalk Server, cree un nuevo puerto de envío o haga doble clic en un puerto de envío existente para modificarlo. Consulte [cómo crear un puerto de envío](../core/how-to-create-a-send-port2.md) para obtener más información. Configure todas las opciones de puerto de envío y especifique **HTTP** para el **tipo** opción el **transporte** sección en la **General** ficha.  
  
2.  En el **General** ficha la **transporte** sección, haga clic en el **configurar** situado junto a **tipo**.  
  
3.  En el **propiedades de transporte HTTP** cuadro de diálogo el **General** ficha, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Dirección URL de destino**|Requerido. Especificar la dirección a la que enviar solicitudes HTTP. Incluir cadenas de consulta anexadas a la dirección URL base.<br /><br /> **Tipo:** cadena<br /><br /> **Longitud máxima:** 256<br /><br /> Para obtener más información, consulte [restricciones de la propiedad de dirección URL de destino](../core/restrictions-on-the-destination-url-property.md). **Nota:** el URI para un envío de puerto o recibir ubicación no puede superar los 256 caracteres.|  
    |**Habilitar codificación fragmentada**|Especificar el uso de la codificación fragmentada. Si se habilita esta opción, el adaptador de HTTP utilizará la codificación fragmentada HTTP con un tamaño máximo de fragmento de 8 KB. La codificación fragmentada se deshabilita implícitamente si el controlador de envío HTTP está configurado para **utilizar proxy**.<br /><br /> **Tipo:** booleano<br /><br /> **Valor predeterminado:** True|  
    |**Tiempo de espera de solicitud (seg.)**|Especificar el tiempo de espera en segundos para la transmisión HTTP/HTTPS. Si el adaptador de HTTP no recibe respuesta en este tiempo, el servicio registra el error y vuelve a enviar el mensaje según lo establecido en la infraestructura de reintentos.<br /><br /> Si se establece como cero (0), el motor de mensajería de BizTalk calcula el tiempo de espera en función del tamaño del mensaje de solicitud. Si no proporciona ningún valor, se usa el valor del controlador.<br /><br /> **Tipo:** largo<br /><br /> **Valor mínimo:** 0<br /><br /> **Valor máximo:** MAX_LONG|  
    |**Número máximo de redirecciones**|Especificar el número máximo de redirecciones permitidas para el mensaje que se está enviando.<br /><br /> **Valor predeterminado:** 5<br /><br /> **Tipo:** Int<br /><br /> **Valor mínimo:** 0<br /><br /> **Valor máximo:** 10|  
    |**Tipo de contenido**|Especificar el tipo de contenido de los mensajes de solicitud.<br /><br /> Si no se proporciona ningún valor, se utiliza el valor del controlador.<br /><br /> **Tipo:** cadena<br /><br /> **Longitud mínima:** 0<br /><br /> **Longitud máxima:** 256|  
  
4.  En el **propiedades de transporte HTTP** cuadro de diálogo el **Proxy (reemplazo de controlador)** ficha, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Usar configuración de proxy predeterminada del controlador**|Especificar que la configuración del puerto de envío debe utilizar la configuración de proxy especificada para el controlador de envío HTTP.<br /><br /> Esta es la configuración predeterminada.|  
    |**No utilizar proxy**|Especificar si el controlador de envío HTTP utiliza el servidor proxy.<br /><br /> Si se selecciona, el controlador de envío HTTP para este puerto de envío no utiliza el servidor proxy.|  
    |**Utilizar proxy**|Especificar si el controlador de envío HTTP utiliza el servidor proxy.<br /><br /> Si se selecciona, el controlador de envío HTTP utiliza el servidor proxy.|  
    |**Server**|Especificar la dirección del servidor proxy para este puerto de envío.<br /><br /> Esta propiedad sólo requiere un valor si **utilizar proxy** está seleccionada.<br /><br /> **Tipo:** cadena<br /><br /> **Longitud mínima:** 0<br /><br /> **Longitud máxima:** 256|  
    |**Puerto**|Especificar el puerto del servidor proxy para este puerto de envío.<br /><br /> Esta propiedad sólo requiere un valor si **utilizar proxy** está seleccionada.<br /><br /> **Valor predeterminado:** 80<br /><br /> **Tipo:** largo<br /><br /> **Valor mínimo:** 0<br /><br /> **Valor máximo:** 65535|  
    |**Nombre de usuario.**|Especificar el nombre de usuario para la autenticación con el servidor proxy.<br /><br /> Esta propiedad sólo requiere un valor si **utilizar proxy** está seleccionada.<br /><br /> **Tipo:** cadena<br /><br /> **Longitud mínima:** 0<br /><br /> **Longitud máxima:** 256|  
    |**Contraseña**|Especificar la contraseña de usuario para la autenticación con el servidor proxy.<br /><br /> Esta propiedad sólo requiere un valor si **utilizar proxy** está seleccionada.<br /><br /> **Tipo:** cadena<br /><br /> **Longitud mínima:** 0<br /><br /> **Longitud máxima:** 256|  
  
5.  En el **propiedades de transporte HTTP** cuadro de diálogo el **autenticación** ficha, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Tipo de autenticación**|Especificar el tipo de autenticación que se utilizará con el servidor de destino.<br /><br /> Las opciones válidas son:<br /><br /> -   **Anónimo**<br />-   **Básico**<br />-   **Resumen**<br />-   **Kerberos**<br /><br /> **Valor predeterminado:** anónimo|  
    |**Credenciales**|Especificar el tipo de credenciales que se va a utilizar.<br /><br /> Sólo está disponible si el **tipo de autenticación** es **básica** o **Digest**.<br /><br /> Las opciones válidas son:<br /><br /> -   **No Use el inicio de sesión único**<br />     **Nombre de usuario:**<br />     Nombre de usuario que se utilizará para la autenticación con el servidor de destino. Si el **tipo de autenticación** propiedad es **Anonymous** o **Kerberos**, esta opción está deshabilitada. Esta propiedad requiere un valor si **básica** o **Digest** está seleccionada, y no se utiliza Enterprise Single Sign-On.<br />     **Longitud mínima:** 0<br />     **Longitud máxima:** 256<br />     **Contraseña:**<br />     Contraseña que se utilizará para la autenticación con el servidor de destino. Si el **tipo de autenticación** propiedad es **Anonymous** o **Kerberos**, esta opción está deshabilitada. Esta propiedad requiere un valor si **básica** o **Digest** está seleccionada, y no se usa inicio de sesión único.<br />     **Longitud mínima:** 0<br />     **Longitud máxima:** 256<br />-   **Usar inicio de sesión único**<br />     Especificar si se utiliza el inicio de sesión único (SSO) para recuperar credenciales de cliente para la autenticación con el servidor de destino.<br />     **Aplicación afiliada**<br />     Especifica la aplicación afiliada que se use para el inicio de sesión único.<br />     Seleccionar las aplicaciones que desea incluir en el inicio de sesión único (SSO).<br />     **Longitud mínima:** 0<br />     **Longitud máxima:** 256|  
    |**Huella digital de certificado de cliente SSL**|Especificar la huella digital del certificado de cliente que se utilizará para establecer una conexión de Capa de sockets seguros (SSL).<br /><br /> **Longitud mínima:** 0<br /><br /> **Longitud máxima:** 59|  
  
6.  Haga clic en **Aceptar** y **Aceptar** nuevo para guardar la configuración.  
  
## <a name="see-also"></a>Vea también  
 [Configuración de un puerto de envío HTTP](../core/configuring-an-http-send-port.md)