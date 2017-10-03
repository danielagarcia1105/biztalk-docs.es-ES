---
title: "Cómo configurar un puerto de envío SMTP | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuring [SMTP adapters], send ports
- send ports, SMTP adapters
- SMTP adapters, send ports
ms.assetid: b2291378-718d-4d1a-9d54-cd34c1b2e000
caps.latest.revision: "25"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f69f61af2803272c34e3f4e8a0ac4dccfb151561
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-an-smtp-send-port"></a>Cómo configurar un puerto de envío de SMTP
Un puerto de envío de SMTP se puede configurar mediante programación o mediante la consola de administración de BizTalk Server.  
  
 **Cómo configurar un puerto de envío de SMTP mediante programación**  
  
 El adaptador de SMTP almacena la información de configuración en la base de datos de administración de BizTalk (a la que también se conoce como base de datos de configuración). La información de configuración se almacena en la bolsa de propiedades XML personalizada. Durante la inicialización del adaptador de SMTP y durante su tiempo de ejecución, el servidor pasa la configuración al adaptador del modo siguiente:  
  
-   Para el controlador de envío SMTP, la información de configuración se pasa al adaptador mediante una llamada a la **carga** método de la **IPersistPropertyBag** interfaz.  
  
-   Para los adaptadores de envío de SMTP, la información de configuración se pasa al adaptador como un conjunto de propiedades en un contexto de mensaje. El espacio de nombres de SMTP agrupa estas propiedades.  
  
 El modelo de objetos del Explorador de BizTalk expone la interfaz de configuración del adaptador ITransportInfo para los puertos de envío, que contiene la propiedad de lectura y escritura de Transport. Esta propiedad acepta la bolsa de propiedades de configuración del puerto de envío SMTP como una cadena XML de par nombre/valor. Tenga en cuenta que para establecer esta propiedad en el modelo de objetos del explorador de BizTalk, debe en primer lugar se establece en la propiedad de dirección de la **ITransportInfo** interfaz.  
  
 Establecer el **TransportTypeData** propiedad de la **ITransportInfo** interfaz no es necesaria. Si no se establece, el puerto de envío SMTP utiliza valores predeterminados para el controlador de envío de SMTP. Las propiedades específicas del puerto de envío SMTP se definen en el esquema de propiedades del adaptador de envío SMTP, bts_smtp_properties.xsd.  
  
 Si no define propiedades que dupliquen las propiedades de configuración del controlador de envío, se utilizan las propiedades de configuración para el controlador. Si no define las propiedades necesarias, se utilizan valores predeterminados. Si no define los valores predeterminados, el controlador de envío de SMTP registra un error en el registro de sucesos y mueve el mensaje al adaptador de copia de seguridad.  
  
 Se pueden establecer estas propiedades mediante programación en un contexto de mensaje. Se pueden establecer estas propiedades en una programación de orquestación de BizTalk Server o en un componente de canalización personalizado. Las reglas siguientes se aplican cuando se utilizan estas propiedades:  
  
-   Si la propiedad se establece en una orquestación o en un componente de canalización personalizado en una canalización de recepción, entonces:  
  
    -   Si se envía el mensaje al puerto de envío estático, el valor de la propiedad se sobrescribirá con el valor configurado para el puerto de envío.  
  
    -   Si se envía el mensaje a un puerto de envío dinámico, el valor de la propiedad no se sobrescribirá.  
  
-   Si la propiedad se establece en un componente de canalización personalizado en una canalización de envío, entonces:  
  
    -   El valor no se sobrescribirá independientemente de que el mensaje se envíe a un puerto de envío estático o dinámico.  
  
 En la siguiente tabla se enumeran las propiedades de configuración que se pueden definir en el modelo de objetos del Explorador de BizTalk para la ubicación de envío de SMTP.  
  
|Nombre de la propiedad|Tipo|Description|Restricciones|Comentarios|  
|-------------------|----------|-----------------|------------------|--------------|  
|**SMTPHost**|xs:string|Servidor SMTP que se usa para enviar mensajes.|Longitud máxima: 256|Valor predeterminado: vacío.<br /><br /> El valor predeterminado indica que el puerto de envío SMTP utilizará los valores de configuración para el controlador.|  
|**De**|xs:string|La dirección de correo electrónico que el puerto de envío de SMTP, se coloca en el protocolo SMTP **de** encabezado.|Longitud máxima: 256|Valor predeterminado: vacío.<br /><br /> El valor predeterminado indica que el puerto de envío SMTP utilizará los valores de configuración para el controlador.|  
|**CC**|xs:string|Dirección de correo electrónico a la que se enviará una copia del mensaje.|Longitud máxima: 1024|Valor predeterminado: vacío<br /><br /> Puede enumerar varias direcciones de correo electrónico.|  
|**Asunto**|xs:string|Asunto de los mensajes.|Longitud mínima: 0<br /><br /> Longitud máxima: 256|Valor predeterminado: % MessageID %.|  
|**SMTPAuthenticate**|xs:int|Tipo de autenticación que se va utilizar|Ninguno|Valores válidos:<br /><br /> -0 - sin autenticación<br />-1 - autenticación básica<br />-2 - cuenta de proceso (NTLM)<br /><br /> El valor predeterminado indica que el puerto de envío SMTP utilizará los valores de configuración para el controlador. Para aplicar el valor predeterminado, omita esta propiedad de la bolsa de propiedades cuando establezca la propiedad TransportTypeData.|  
|**UserName**|xs:string|Nombre de usuario que se utiliza para la autenticación con el servidor SMTP.|Longitud mínima: 0<br /><br /> Longitud máxima: 256|Valor predeterminado: vacío<br /><br /> Necesita un valor si **SMTPAuthenticate** es igual a 1 (autenticación básica).|  
|**Contraseña**|xs:string|Contraseña de usuario para la autenticación con el servidor SMTP.|Longitud mínima: 0<br /><br /> Longitud máxima: 256|Valor predeterminado: vacío<br /><br /> Necesita un valor si **SMTPAuthenticate** es igual a 1 (autenticación básica).|  
|**ReadReceipt**|xs:boolean|Solicita una confirmación de lectura para los mensajes desde este puerto de envío.|Ninguno|Valor predeterminado: False|  
|**DeliveryReceipt**|xs:boolean|Solicita una notificación de entrega para los mensajes desde este puerto de envío.|Ninguno|Valor predeterminado: False|  
|**EmailBodyText**|xs:string|Especifica el texto que se utilizará para el cuerpo del correo electrónico que se va a enviar.|Longitud máxima: 64 kb|Valor predeterminado: vacío|  
|**EmailBodyTextCharset**|xs:string|Especifica el carácter establecido para codificar el cuerpo del correo electrónico que se envía cuando el **EmailBodyText** se utiliza la opción. El adaptador de SMTP convertirá la **EmailBodyText** para el juego de caracteres especificado por **EmailBodyTextCharset**.|Ninguno|Valor predeterminado: ninguno. Debe establecer el valor de forma explícita (por ejemplo, UTF-8).<br /><br /> Si no establece un valor, puede que aparezca el mensaje de error que se muestra al final de este tema.|  
|**EmailBodyFile**|xs:string|Especifica que se utilice el contenido de un archivo para el cuerpo del correo electrónico que se va a enviar y la ruta de acceso completa de dicho archivo. Esta ruta debe estar a disposición del host para el adaptador de SMTP en tiempo de ejecución.|Longitud máxima de la ruta de acceso: 256 caracteres|Valor predeterminado: vacío|  
|**EmailBodyFileCharset**|xs:string|Especifica el carácter establecido para codificar el cuerpo del correo electrónico enviado cuando el **EmailBodyFile** propiedad está establecida. El adaptador de SMTP no realizará ninguna conversión en el archivo; el archivo ya se debe haber codificado en este juego de caracteres. Si el archivo tiene una marca de orden de bytes (BOM), el adaptador de SMTP la quitará.|Ninguno|Valor predeterminado: UTF-8 (65001)|  
|**Datos adjuntos**|xs:string|Especifica que se adjuntarán archivos al mensaje de correo electrónico y la ruta completa de esos archivos. Las rutas especificadas deben estar a disposición del host para el adaptador de SMTP en tiempo de ejecución.|Longitud máxima de la ruta de acceso: 256 caracteres|Valor predeterminado: vacío|  
|**MessagePartsAttachments**|xs:int|Especifica cómo se adjuntan las partes del mensaje de BizTalk al mensaje de correo electrónico.|Ninguno|Valores válidos:<br /><br /> -0 - partes de mensaje de BizTalk No se utilizará como datos adjuntos.<br />-1 - la parte del cuerpo de mensaje de BizTalk se envía como datos adjuntos de correo electrónico. En este caso, el **EmailBodyFile** o **EmailBodyText** deben especificarse propiedades. Si no se especifica ninguna de estas propiedades, la parte del cuerpo del mensaje de BizTalk se envía como cuerpo del mensaje de correo electrónico en lugar de como datos adjuntos.<br />-2 - todas las partes se envían como datos adjuntos. Sin embargo, si **EmailBodyText** o **EmailBodyFile** no se especifica, la parte del cuerpo de mensaje de BizTalk se envía como cuerpo del correo electrónico y otros elementos se envían como datos adjuntos.<br /><br /> Valor predeterminado: 0|  
|**ReplyBy**|xs:dateTime|Rellena el **Reply-By** campo de encabezado en el mensaje saliente con el valor especificado.|No se puede establecer esta propiedad en la página de propiedades de puerto de envío. Esta propiedad se puede establecer en una canalización u orquestación.|Valor predeterminado: vacío|  
  
 En el siguiente código se muestra el formato de la cadena XML que se utiliza para establecer estas propiedades:  
  
```  
<CustomProps>  
   <DeliveryReceipt vt="11">-1</DeliveryReceipt  
   <SMTPHost vt="8">sfdsadf</SMTPHost>  
   <Subject vt="8">Some subject</Subject>  
   <From vt="8">username@domain.com</From>  
   <SMTPAuthenticate vt="19">2</SMTPAuthenticate>  
   <ReadReceipt vt="11">-1</ReadReceipt>  
</CustomProps>  
```  
  
 **Cómo configurar un puerto de envío SMTP con la consola de administración de BizTalk Server**  
  
 Se pueden establecer variables de adaptador de puerto de envío SMTP en la consola de administración de BizTalk Server. Si no se establecen propiedades para el puerto de envío, se utilizan los valores predeterminados del controlador de envío establecidos en la consola de administración de BizTalk Server.  
  
 Para configurar un puerto de envío SMTP con la consola de administración de BizTalk Server, siga este procedimiento.  
  
### <a name="to-configure-variables-for-an-smtp-send-port"></a>Para configurar variables para un puerto de envío SMTP  
  
1.  En la consola de administración de BizTalk Server, cree un puerto de envío nuevo o haga doble clic en un puerto de envío existente para modificarlo. Para obtener más información, consulte [cómo crear un puerto de envío](../core/how-to-create-a-send-port2.md). Configure todas las opciones del puerto de envío y especifique **SMTP** para el **tipo** opción en el **transporte** sección de la **General** ficha.  
  
2.  En el **General** ficha la **transporte** sección, junto a **tipo**, haga clic en **configurar**.  
  
3.  En el **propiedades de transporte SMTP** cuadro de diálogo, en la **General** ficha, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Para**|Requerido. Especificar la dirección de correo electrónico a la que desea enviar mensajes.<br /><br /> Puede especificar más de una dirección de correo electrónico.<br /><br /> Longitud máxima: 256<br /><br /> Para obtener más información acerca de esta propiedad, vea [restricciones en la propiedad To SMTP](../core/restrictions-on-the-smtp-to-property.md).|  
    |**CC**|Especificar la dirección de correo electrónico a la que desea enviar una copia del mensaje.<br /><br /> Puede especificar más de una dirección de correo electrónico.<br /><br /> Longitud máxima: 1024|  
    |**Asunto**|Especifica el encabezado de asunto del mensaje.<br /><br /> Longitud mínima: 0<br /><br /> Longitud máxima: 256|  
    |**Notificación**|Especificar el tipo de notificación de entrega. Puede seleccionar uno o ambos tipos de entrega. Los tipos de notificación de entrega son:<br /><br /> -   **Confirmación de lectura**. Se envía un mensaje de correo electrónico de confirmación al leer el mensaje.<br />-   **Confirmación de entrega**. Se envía un mensaje de correo electrónico de confirmación al entregar el mensaje.|  
  
4.  En el **propiedades de transporte SMTP** cuadro de diálogo, en la **redactar** ficha, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Parte del cuerpo de mensaje de BizTalk**|Especificar que se utilice la parte del cuerpo del mensaje de BizTalk para el cuerpo del correo electrónico que se está enviando.|  
    |**Texto**|Especifica el texto que se utilizará para el cuerpo del correo electrónico que se va a enviar. Después de la **texto** opción está seleccionada, puede escribir el texto para el cuerpo del correo electrónico en el cuadro de texto.<br /><br /> **Longitud máxima:** 64 Kb|  
    |**Juego de caracteres para el texto**|-Especifique el juego de caracteres que utilizará para codificar el cuerpo del correo electrónico que se envían. Esta opción solo está disponible si la **texto** opción está seleccionada.<br />-   **Valor predeterminado:** UTF-8 (65001)|  
    |**Archivo**|Especificar que se utilice el contenido de un archivo para el cuerpo del correo electrónico que se está enviando y especificar la ruta de acceso a dicho archivo. Después de la **archivo** opción se puede hacer clic en el botón de puntos suspensivos (**...** ) botón para buscar el archivo.<br /><br /> Longitud máxima de la ruta de acceso: 256 caracteres **Nota:** es un procedimiento recomendado para especificar una ruta de acceso en un recurso compartido de archivos que sea accesible desde todos los servidores de BizTalk Server en el grupo de BizTalk Server para su uso en producción.|  
    |**Juego de caracteres del archivo**|Especificar la codificación del juego de caracteres del archivo que se envía. **Nota:** el adaptador de SMTP no aplica la codificación especificada en el archivo. Esta opción se utiliza exclusivamente para especificar cómo se codifica el archivo que se envía. <br /><br /> Esta opción solo está disponible si la **archivo** opción está seleccionada.<br /><br /> Valor predeterminado: UTF-8 (65001)|  
  
5.  En el **propiedades de transporte SMTP** cuadro de diálogo, en la **datos adjuntos** ficha, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Partes de mensaje de BizTalk restantes**|Especifica la forma de adjuntar partes del mensaje de BizTalk al mensaje de correo electrónico.<br /><br /> Opciones:<br /><br /> -   **No adjuntar partes**<br />-   **Adjuntar sólo parte del cuerpo**<br />-   **Adjuntar todas las partes**<br /><br /> Valor predeterminado: no adjuntar partes.|  
    |**Agregar**|Especificar un archivo o los archivos que se adjuntarán al mensaje de correo electrónico. Después de hacer clic **agregar** puede examinar para seleccionar un archivo y agregarlo a la lista de archivos que se adjuntan.<br /><br /> Longitud máxima de la ruta de acceso: 256 caracteres **Nota:** es un procedimiento recomendado para especificar una ruta de acceso en un recurso compartido de archivos que sea accesible desde todos los servidores de BizTalk Server en el grupo de BizTalk Server para su uso en producción.|  
    |**Quitar**|Quitar el archivo seleccionado de la lista de archivos que se van a adjuntar al mensaje de correo electrónico.|  
  
6.  En el **propiedades de transporte SMTP** cuadro de diálogo, en la **reemplazo de controlador** ficha, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Nombre del servidor SMTP**|Especifica el nombre del servidor SMTP que se utilizará al enviar mensajes.<br /><br /> Longitud máxima: 256 **Nota:** URI de un envío de puerto o recibir ubicación no puede superar los 256 caracteres.|  
    |**De (dirección de correo electrónico)**|Especifique la dirección de correo electrónico que coloque en el protocolo SMTP **de** encabezado.<br /><br /> Longitud máxima: 256|  
    |**Tipo de autenticación**|Especifica el tipo de autenticación que se utilizará con el servidor SMTP.<br /><br /> Opciones:<br /><br /> -   **(Valor predeterminado)**<br />-   **Sin autenticación**<br />-   **Autenticación básica**<br />-   **Cuenta de proceso (NTLM)**<br /><br /> El valor predeterminado indica que el puerto de envío SMTP utilizará los valores de configuración especificados en el controlador de envío.|  
    |**Nombre de usuario.**|Especifica el nombre de usuario que se utilizará para la autenticación en el servidor SMTP.<br /><br /> Esta propiedad necesita un valor si **tipo de autenticación** es **la autenticación básica**.<br /><br /> Longitud mínima: 0<br /><br /> Longitud máxima: 256|  
    |**Contraseña**|Especifica la contraseña que se utilizará para la autenticación en el servidor SMTP.<br /><br /> Esta propiedad necesita un valor si **tipo de autenticación** es **la autenticación básica**.<br /><br /> Longitud mínima: 0<br /><br /> Longitud máxima: 256|  
  
7.  Haga clic en **Aceptar** y **Aceptar** nuevo para guardar la configuración.  
  
## <a name="see-also"></a>Vea también  
 [Configurar el adaptador de SMTP](../core/configuring-the-smtp-adapter.md)