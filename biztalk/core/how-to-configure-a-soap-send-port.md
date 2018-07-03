---
title: Cómo configurar un puerto de envío SOAP | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SOAP adapters, send ports
- SOAP adapters, code samples
- code samples, SOAP adapters
- configuring [SOAP adapters], code samples
- configuring [SOAP adapters], send ports
- send ports, SOAP adapters
ms.assetid: 3a0622f4-d25d-4449-a063-d8ba217e9729
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 79a5bfc7e7a1455f55b10f36f5280c967ecf190d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978061"
---
# <a name="how-to-configure-a-soap-send-port"></a>Cómo configurar un puerto de envío SOAP
Los puertos de de envío SOAP pueden configurarse mediante programación, o bien utilizando la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  

 **Cómo configurar un puerto de envío SOAP mediante programación**  

 El modelo de objetos del explorador de BizTalk expone una interfaz específica del adaptador para puertos de envío denominado **ITransportInfo** que tiene el **TransportTypeData** propiedad de lectura/escritura. Esta propiedad acepta una bolsa de propiedades de puerto de envío SOAP en forma de par nombre-valor de cadenas XML. Tenga en cuenta que establecer esta propiedad en el objeto en el Explorador de BizTalk del modelo se debe establecer el **OutboundTransportLocation** propiedad de la **ITransportInfo** en primer lugar la interfaz.  

 El **TransportTypeData** propiedad de la **ITransportInfo** interfaz no es necesaria. Si no se define, el adaptador utiliza los valores predeterminados de configuración del puerto de envío SOAP, tal como se indica en la tabla siguiente.  

 En la tabla siguiente se enumeran las propiedades de configuración que pueden definirse en el modelo de objetos del Explorador de BizTalk para los puertos de envío de SOAP.  

|Nombre de propiedad|Tipo|Descripción|  
|-------------------|----------|-----------------|  
|**IDENTIFICADOR URI**|String|Directorio virtual que contiene el servicio Web en el servidor de implementación.|  
|**Nombre de usuario**|String|Nombre de usuario que se especifica para tener acceso al servicio Web de destino.<br /><br /> Valor predeterminado: en blanco|  
|**Contraseña**|String|Contraseña de usuario que se usará para la autenticación con el servidor.<br /><br /> Valor predeterminado: en blanco|  
|**ClientCertificate**|String|Huella digital del certificado SSL de cliente.<br /><br /> Valor predeterminado: en blanco|  
|**AffiliateApplicationName**|String|Nombre de la aplicación de SSO que se utilizará para canjear el vale de credenciales de cliente.<br /><br /> El **AffiliateApplicationName** es mutuamente excluyente un **Username** y **contraseña** par.<br /><br /> Valor predeterminado: en blanco|  
|**UseProxy**|Boolean|Indica si el puerto de envío de SOAP utiliza un servidor proxy para tener acceso al servicio Web de destino. Todos los puertos de envío SOAP pueden compartir el servidor proxy.<br /><br /> Valor predeterminado: False|  
|**ProxyAddress**|String|Dirección de proxy HTTP que se utilizará para llamar al servicio Web.<br /><br /> Valor predeterminado: en blanco|  
|**ProxyPort**|Integer|Puerto del proxy HTTP que se utilizará para llamar al servicio Web.<br /><br /> Valor predeterminado: en blanco|  
|**ProxyUsername**|String|Nombre de usuario que se va a utilizar para el proxy.<br /><br /> Valor predeterminado: en blanco|  
|**ProxyPassword**|String|Contraseña que se va a utilizar para el proxy.<br /><br /> Valor predeterminado: en blanco|  

 El código siguiente muestra el formato que debe utilizarse para definir estas propiedades:  

```  
<CustomProps>  
   <URI vt="8"/>  
   <ClientCertificate vt="8"/>  
   <Password vt="8">Encrypted</Password>  
   <ProxyAddress vt="8"/>  
   <ProxyPassword vt="8">Encrypted</ProxyPassword>  
   <ProxyPort vt="3"/>  
   <ProxyUsername vt="8"/>  
   <UseProxy vt="11"/>  
   <Username vt="8"/>  
   <AffiliateApplicationName vt="8"/>  
</CustomProps>  
```  

 **Cómo configurar un puerto de envío SOAP con la consola de administración de BizTalk Server**  

 Puede definir variables del adaptador de puerto de envío SOAP en la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Si no se establecen las propiedades para el puerto de envío, se usarán los valores predeterminados del controlador de envío establecidos en la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  

### <a name="to-configure-variables-for-a-soap-send-port"></a>Para configurar variables para un puerto de envío SOAP  

1. En la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], cree un nuevo puerto de envío o haga doble clic en uno existente para modificarlo. Para obtener más información, consulte [cómo crear un puerto de envío](../core/how-to-create-a-send-port2.md). Configure todas las opciones de puerto de envío y especifique **SOAP** para el **tipo** opción el **transporte** sección de la **General** ficha.  

2. En el **General** ficha la **transporte** junto a la sección **tipo**, haga clic en **configurar**.  

3. En el **propiedades de transporte SOAP** cuadro de diálogo el **General** ficha, realice lo siguiente:  


   |             Use              |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     Para                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
   |-----------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |        **Dirección URL del servicio Web**        |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   Especificar la dirección del servicio Web al que desea llamar. **Nota:** el URI para un envío de puerto o recibir ubicación no puede superar los 256 caracteres.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
   |        **Autenticación**         |                                                                                                                                                                                                                                                                                                                                                                                                                          Indicar el método de autenticación que utiliza el servicio Web al que está llamando.<br /><br /> Opciones:<br /><br /> -   **Anónimo.** La configuración predeterminada.<br />-   **Básico.** La conexión SOAP envía el nombre de usuario y la contraseña en texto sin formato.<br />-   **Síntesis.** La conexión SOAP envía la contraseña en un formato cifrado.<br />-   **NTLM.** La conexión SOAP no envía el nombre de usuario ni la contraseña. El adaptador de SOAP utiliza siempre las credenciales del proceso en el que se ejecuta el adaptador de envío SOAP para este tipo de autenticación.                                                                                                                                                                                                                                                                                                                                                                                                                           |
   |          **Credenciales**          | Especificar el tipo de credenciales que se va a utilizar.<br /><br /> Sólo está disponible si el **tipo de autenticación** es **básica** o **Digest**.<br /><br /> Opciones:<br /><br /> -   **No Use el inicio de sesión único**<br />     **Nombre de usuario.**<br />     Nombre de usuario que se utilizará para la autenticación con el servidor de destino. Si el **tipo de autenticación** propiedad es **Anonymous** o **NTLM**, esta opción está deshabilitada. Esta propiedad requiere un valor si **básica** o **Digest** está seleccionada, y no se utiliza Enterprise Single Sign-On.<br />     Longitud mínima: 0<br />     Longitud máxima: 256<br />     **Contraseña**<br />     Contraseña que se utilizará para la autenticación con el servidor de destino. Si el **tipo de autenticación** propiedad es **Anonymous** o **NTLM**, esta opción está deshabilitada. Esta propiedad requiere un valor si **básica** o **Digest** está seleccionada, y no se usa inicio de sesión único.<br />     Longitud mínima: 0<br />     Longitud máxima: 256<br />-   **Usar inicio de sesión único**<br />     Especificar si se utiliza el inicio de sesión único (SSO) para recuperar credenciales de cliente para la autenticación con el servidor de destino.<br />     **Aplicación afiliada**<br />     Especifica la aplicación afiliada que se use para el inicio de sesión único. Para obtener información acerca de cómo rellenar esta lista, consulte [aplicaciones afiliadas de SSO](../core/sso-affiliate-applications.md).<br />     Longitud mínima: 0<br />     Longitud máxima: 256 |
   | **Huella digital del certificado de cliente** |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        Especificar la huella digital de certificado de cliente que se utilizará para establecer una conexión.<br /><br /> Ejemplo: 01 23 45 67 89 AB CD EF 01 23 45 67 89 AB CD EF 01 23 45 67<br /><br /> Longitud mínima: 0<br /><br /> Longitud máxima: 59                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |


4. En el **propiedades de transporte SOAP** cuadro de diálogo el **Proxy** ficha, realice lo siguiente:  


   |                   Use                    |                                                                                                                                                                                                     Para                                                                                                                                                                                                      |
   |-----------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | **Usar configuración de proxy predeterminada del controlador** |                                                                         Especificar la configuración de controlador del servidor proxy del puerto de envío. Cuando se establece como true, el puerto utilizará la configuración del proxy en el nivel del controlador. Cuando se establece como false, el adaptador de envío utilizará la información del proxy especificado en el puerto de envío.<br /><br /> El valor de configuración predeterminado es true.                                                                         |
   |             **No utilizar proxy**              |                                                                                                                                                                             Indicar si el controlador de envío de SOAP utiliza un servidor proxy.                                                                                                                                                                             |
   |                 **Utilizar proxy**                 |                                                                                                                                                 Indicar si el controlador de envío de SOAP utiliza un servidor proxy. Todos los puertos de envío SOAP pueden compartir el servidor proxy.                                                                                                                                                  |
   |                  **Server**                   |                                                                                                    Especifica el nombre del servidor proxy.<br /><br /> Esta propiedad sólo requiere un valor si **utilizar proxy** está seleccionada.<br /><br /> Tipo: cadena<br /><br /> Longitud mínima: 0<br /><br /> Longitud máxima: 256                                                                                                     |
   |                   **Puerto**                    |                                       Especificar el puerto que utiliza el controlador de envío de SOAP.<br /><br /> Esta propiedad sólo requiere un valor si **utilizar proxy** está seleccionada.<br /><br /> Valor predeterminado: 80<br /><br /> Tipo: long<br /><br /> Valor mínimo: 0<br /><br /> Valor máximo: 65535 **Nota:** especificando un valor de 0 indica que se utilice el valor predeterminado, que es el puerto 80.                                        |
   |                 **Nombre de usuario.**                 | Especificar el nombre de usuario que se utilizará para la autenticación. Si usa la autenticación integrada de Windows, el nombre de usuario incluye el dominio, **dominio\nombre de usuario**. Si usa Basic o la autenticación implícita, el nombre de usuario no incluye **dominio\\**.<br /><br /> Esta propiedad sólo requiere un valor si **utilizar proxy** está seleccionada.<br /><br /> Tipo: cadena<br /><br /> Longitud mínima: 0<br /><br /> Longitud máxima: 256 |
   |                 **Contraseña**                  |                                                                                                Especificar la contraseña que se utilizará para la autenticación.<br /><br /> Esta propiedad sólo requiere un valor si **utilizar proxy** está seleccionada.<br /><br /> Tipo: cadena<br /><br /> Longitud mínima: 0<br /><br /> Longitud máxima: 256                                                                                                 |


5. En el **propiedades de transporte SOAP** cuadro de diálogo el **servicio Web** ficha, realice lo siguiente:  


   |          Use          |                                                                                                                                                                                                  Para                                                                                                                                                                                                  |
   |----------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | **Puerto Web de orquestación** |                                                                                                                                Especifica que se use el servicio Web que se expone en la dirección URL del servicio Web aparece en la **General** ficha.<br /><br /> Esta es la configuración predeterminada.                                                                                                                                 |
   |     **Nombre del ensamblado**      | Especificar el nombre del ensamblado que contiene el proxy de servicio Web. Este campo se puede rellenar haciendo clic en el botón Examinar para buscar un ensamblado. Después de seleccionar el ensamblado, este cuadro se rellena con el nombre completo del mismo. **Nota:** el ensamblado especificado debe estar presente en todas las [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]s en tiempo de ejecución. |
   |       **Nombre de tipo**        |                                                                                                                              Especificar el nombre de la clase que contiene el método Web que se va a invocar. Este nombre puede seleccionarse de una lista de tipos incluida en el ensamblado.                                                                                                                              |
   |      **Nombre del método**       |                                             Especificar uno de los métodos del cuadro de lista o seleccionar la opción a "Especificar más tarde". Si se selecciona la opción "Especificar más tarde", el método Web deberá definirse por cualquier otro medio como, por ejemplo, un componente de canalización. En este escenario, el método web debe escribirse en el adaptador de Soap **MethodName** propiedad de contexto.                                              |
   |        **SOAP 1.2**        |                                                                                                         Especificar que se genere código de proxy que proporcione compatibilidad con el protocolo SOAP 1.2. Si no habilita esta opción, se generará el código de proxy para compatibilidad con SOAP 1.1.<br /><br /> Valor predeterminado: desactivada                                                                                                          |


6. Haga clic en **Aceptar** y **Aceptar** nuevo para guardar la configuración.  

## <a name="see-also"></a>Vea también  
 [Publicación de servicios web](../core/publishing-web-services.md)