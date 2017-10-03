---
title: "Cómo establecer dinámicamente el URI de un servicio Web consumido | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 95829a28-7898-4757-87cc-40fc99bf707e
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3766eb98ffe5d2b73d79f09c58cf98f081c644db
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-dynamically-set-the-uri-of-a-consumed-web-service"></a>Cómo definir de forma dinámica el URI de un servicio Web utilizado
Cuando se crea un puerto Web para un servicio Web consumido, puede seleccionar un enlace de puerto dinámico. Cuando seleccione un enlace de puerto dinámico, debe definir el URI del servicio Web consumido en tiempo de ejecución. El URI seleccionado debe llamar un servicio Web que tenga el mismo proxy Web que el servico Web utilizado para crear el tipo de puerto Web.  
  
> [!NOTE]
>  En este tema se describe cómo definir mediante programación las propiedades de un puerto de envío SOAP dinámico en una orquestación. Sin embargo, se pueden establecer estas propiedades en una orquestación o en un componente de canalización personalizado, sin importar si el puerto de envío es estático o dinámico. Para obtener más información acerca de los componentes de canalización personalizado, consulte [desarrollar componentes de canalización personalizados](../core/developing-custom-pipeline-components.md).  
  
 Los enlaces de puerto dinámicos para puertos Web tienen un comportamiento distinto de los enlaces de puerto dinámicos para puertos que no son puertos Web. Cuando seleccione enlaces dinámicos para un puerto que no sea un puerto Web, no podrá utilizar el adaptador de SOAP.  
  
 Cuando utilice puertos Web dinámicos para consumir un servicio Web, las propiedades del puerto de envío están establecidas en los valores predeterminados. Algunos de estos valores se establecen internamente y otros valores predeterminados para los valores que se establecen en los **controlador de adaptador de SOAP** páginas de propiedades. Puede sobreescribir estos valores en una orquestación cuando se utilizan puertos de envío dinámicos. Para obtener más información, consulte [consideraciones al consumir servicios Web](../core/considerations-when-consuming-web-services.md).  
  
## <a name="dynamically-change-the-uri-of-a-consumed-web-service"></a>Cambiar dinámicamente el URI de un servicio Web consumido  
  
1.  Agregar un puerto Web tal como se describe en [cómo agregar un puerto Web](../core/how-to-add-a-web-port.md). Sin embargo, en lugar de seleccionar la **especificar ahora** enlace de puerto, seleccione **dinámica** el puerto de enlace, como se muestra en la ilustración siguiente.  
  
     ![](../core/media/ebiz-prog-wsc-dynamic.gif "ebiz_prog_wsc_dynamic")  
  
2.  En la orquestación que llama al servicio Web consumido, agregue un **expresión** forma en algún momento anterior a la **enviar** forma que se ha conectado al puerto Web.  
  
3.  En el **expresión** forma, agregue una expresión similar:  
  
    ```  
    myWebPort(Microsoft.XLANGs.BaseTypes.Address) = "http://orders/myCompany.asmx";  
    ```  
  
> [!NOTE]
>  Puede recuperar el URI utilizado en el Editor de expresiones de BizTalk desde varias ubicaciones, incluido el mensaje entrante, una base de datos SQL o una aplicación de líneas de negocio.  
  
## <a name="dynamically-modify-send-port-properties"></a>Modificar propiedades de puerto de envío de forma dinámica  
  
1.  En el **construir mensaje** forma que utiliza para construir el mensaje Web, agregue un **asignación de mensajes** forma si uno no está presente.  
  
2.  En el **asignación de mensajes** forma, agregue una expresión similar:  
  
    ```  
    myWebMessage(SOAP.UseSSO) = true;  
    ```  
  
 Todas las propiedades del puerto de envío SOAP utilizan el espacio de nombre SOAP.  
  
 La siguiente tabla contiene una lista de las propiedades de puerto de envío SOAP que se pueden definir cuando se utilizan puertos Web dinámicos.  
  
|Nombre de propiedad|Tipo|Description|  
|-------------------|----------|-----------------|  
|**AuthenticationScheme**|String|Método de autenticación que se utiliza para llamar el servicio Web.<br /><br /> Valor predeterminado: anónimo<br /><br /> Otros valores permitidos: Basic, Digest, NTLM|  
|**Nombre de usuario**|String|Nombre de usuario que se especifica para tener acceso al servicio Web de destino.<br /><br /> Valor predeterminado: en blanco|  
|**Contraseña**|String|Contraseña de usuario que se utilizará para la autenticación con el servidor.<br /><br /> Valor predeterminado: en blanco|  
|**ClientCertificate**|String|Huella digital de certificado de cliente de Capa de sockets seguros (SSL)<br /><br /> Valor predeterminado: en blanco|  
|**UseSSO**|Boolean|Indica si este puerto Web utilizará el Inicio de sesión único (SSO).<br /><br /> Valor predeterminado: False|  
|**AffiliateApplicationName**|String|Nombre de la aplicación de SSO que utilizará este puerto Web para canjear el vale de credenciales de cliente.<br /><br /> Valor predeterminado: en blanco|  
|**UseHandlerSetting**|Boolean|Indica si este puerto Web utilizará la configuración de proxy HTTP del controlador de envío SOAP. **Nota:** si la **UseProxy** propiedad de contexto se establece, entonces **UseHandlerSetting** se omite la propiedad de contexto. <br /><br /> Valor predeterminado: False|  
|**UseProxy**|Boolean|Indica si este puerto Web utilizar un servidor proxy para tener acceso al servicio Web de destino. **Nota:** si la **UseProxy** propiedad de contexto se establece, entonces **UseHandlerSetting** se omite la propiedad de contexto. <br /><br /> Valor predeterminado: False|  
|**ProxyAddress**|String|Dirección de proxy HTTP que se utilizará para llamar al servicio Web.<br /><br /> Valor predeterminado: recuperados de propiedades del controlador de envío SOAP.|  
|**ProxyPort**|Integer|Puerto del proxy HTTP que se utilizará para llamar al servicio Web.<br /><br /> Valor predeterminado: recuperados de propiedades del controlador de envío SOAP.|  
|**ProxyUsername**|String|Nombre de usuario que se va a utilizar para el proxy HTTP.<br /><br /> Valor predeterminado: recuperados de propiedades del controlador de envío SOAP.|  
|**ProxyPassword**|String|Contraseña que se va a utilizar para el proxy HTTP.<br /><br /> Valor predeterminado: recuperados de propiedades del controlador de envío SOAP.|  
|**ClientConnectionTimeout**|Int32|Valor de tiempo de espera de la conexión de cliente HTTP.<br /><br /> Valor predeterminado: igual que el tiempo de espera de conexión de HTTP de ASP.NET de forma predeterminada.|  
|**TypeName**|String|Especificar el nombre de la clase que contiene el método Web que se va a invocar.<br /><br /> Valor predeterminado: en blanco|  
|**MethodName**|String|Especificar el método de la clase que se va a invocar. **Nota:** configurar **MethodName** puerto de envío propiedad de SOAP estático mediante programación, es necesario establecer **nombre del método** a **[especificar más tarde]** en el **servicio Web** pestaña de la **propiedades de transporte SOAP** cuadro de diálogo de la consola de administración de BizTalk Server. Para obtener más información acerca de **propiedades de transporte SOAP** cuadro de diálogo, vea el **cuadro de diálogo de propiedades de transporte SOAP, servicio Web** ficha [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]. <br /><br /> Valor predeterminado: en blanco|  
|**AssemblyName**|String|Identifica el tipo .NET y el ensamblado que se va a cargar y a ejecutar.<br /><br /> Valor predeterminado: en blanco|  
|**UnknownHeaders**|String|Especifica la lista serializada de encabezados SOAP desconocidos.<br /><br /> Valor predeterminado: en blanco|  
|**UserDefined**|String|Define clases definidas por el usuario.<br /><br /> Valor predeterminado: en blanco|  
|**UseSoap12**|Boolean|Especificar que se genere código de proxy que proporcione compatibilidad con el protocolo SOAP 1.2. Si esta propiedad está definida como False, se generará código de proxy compatible con SOAP 1.1.<br /><br /> Valor predeterminado: False|  
  
> [!NOTE]
>  Excepto para la **ClientConnectionTimeout** configuración, estos valores pueden solo puede establecer dinámicamente cuando se usa **dinámica** enlaces de puerto. Son de solo lectura cuando se usa el **especificar ahora** enlace de puerto. Puede establecer la **ClientConnectionTimeout** con **especificar ahora** y **dinámica** enlaces de puerto.  
  
## <a name="see-also"></a>Vea también  
 [Encabezados SOAP con servicios Web consumidos](../core/soap-headers-with-consumed-web-services.md)   
 [Creación de puertos Web](../core/creating-web-ports.md)