---
title: Cómo configurar un adaptador de POP3 | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive locations, POP3 adapters
- POP3 adapters, receive locations
- configuring [POP3 adapters], receive locations
ms.assetid: 259cd105-733a-4f87-be30-c02e6bd0f457
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 410bfed33402d8d810434e7ff9287fa5c01462da
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25969346"
---
# <a name="how-to-configure-a-pop3-receive-location"></a>Cómo configurar un adaptador de POP3
Se pueden establecer variables de adaptador de ubicación de recepción de POP3 en la consola de administración de BizTalk Server. Si no se definen las propiedades en la ubicación de recepción, se utilizarán los valores predeterminados del controlador de recepción definidos en la consola de administración de BizTalk Server.  
  
> [!NOTE]
>  Antes de completar este procedimiento, debe haber agregado un puerto de recepción. Para obtener más información, consulte [cómo crear un puerto de recepción](../core/how-to-create-a-receive-port.md).  
  
 **Para configurar variables para un POP3 ubicación de recepción**  
  
1.  En la consola de administración de BizTalk Server, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda el aplicación que desea crear una ubicación de recepción.  
  
2.  En la consola de administración de BizTalk Server, en el panel izquierdo, haga clic en el **puerto de recepción** nodo. A continuación, en el panel de la derecha, haga clic con el botón secundario en el puerto de recepción asociado con una ubicación de recepción existente o que desee asociar con una nueva ubicación de recepción. A continuación, haga clic en **Propiedades**.  
  
3.  En el **propiedades de puerto de recepción** cuadro de diálogo, en el panel izquierdo, seleccione **ubicaciones de recepción**y, a continuación, en el panel derecho, haga doble clic en otra ubicación de recepción o haga clic en **New**para crear una nueva ubicación de recepción.  
  
4.  En el **propiedades de la ubicación de recepción** cuadro de diálogo, en la **transporte** junto a la sección **tipo**, seleccione **POP3** en la lista desplegable, y, a continuación, haga clic en **configurar**.  
  
5.  En el **propiedades de transporte POP3** diálogo cuadro, realice lo siguiente:  
  
    |**Use esto**|**Para ello**|  
    |------------------|--------------------|  
    |**Aplicar descodificación MIME**|Especificar si se aplica la descodificación MIME a los mensajes que recibe el adaptador de POP3. La descodificación MIME se utiliza para analizar el mensaje entrante y todos los adjuntos de un mensaje de BizTalk de varias partes. **Importante:** si este valor se establece en `False` , a continuación, el adaptador de POP3 enviará el cuerpo completo del correo electrónico, incluidos los encabezados de mensaje a BizTalk Server. <br /><br /> Valor predeterminado:`True`|  
    |**Tipo de contenido de parte de cuerpo**|Especificar el tipo de contenido de parte del cuerpo del mensaje de correo electrónico entrante que se va a enviar a BizTalk Server. Esta configuración es opcional. Vea [¿qué es el adaptador de POP3?](../core/what-is-the-pop3-adapter.md) para obtener más información.|  
    |**Índice de parte del cuerpo**|Especificar la parte del cuerpo del mensaje de correo electrónico entrante que se va a enviar a BizTalk Server. Vea [¿qué es el adaptador de POP3?](../core/what-is-the-pop3-adapter.md) para obtener más información.<br /><br /> Valor predeterminado: 0|  
    |**Servidor de correo electrónico**|Especificar el servidor de correo POP3 que aloja el buzón que sondeará el adaptador de POP3. **Nota:** el URI para un envío de puerto o recibir ubicación no puede superar los 256 caracteres.|  
    |**Puerto**|Especificar el puerto del servidor de correo POP3.<br /><br /> Valores válidos: de 1 a 65535 inclusive.<br /><br /> Valor predeterminado: 0 **Nota:** un valor de 0 indica que se use el puerto POP3 predeterminado 110 si **usar SSL** es `False` o el puerto 995 si **usar SSL** es `True`.|  
    |**Esquema de autenticación**|Especificar el tipo de autenticación que se utilizará con el servidor de destino.<br /><br /> Las opciones válidas son:<br /><br /> -   **Básico**<br />-   **Resumen**<br />-   **SPA** **Nota:** cuando utiliza la autenticación SPA, se debe especificar el nombre de usuario con uno de los siguientes formatos: las cuentas de dominio deben escribirse con la sintaxis: \<nombre de dominio\> \\< nombre de usuario\> cuentas locales deben escribirse con la sintaxis: \<nombre de la máquina\>\\< nombre de usuario\>|  
    |**Contraseña**|Especificar la contraseña de usuario que se utilizará para la autenticación con el servidor POP3.|  
    |**Usar SSL**|Especificar si se utilizará Capa de sockets seguros (SSL) para establecer la comunicación con el servidor de destino.<br /><br /> Valor predeterminado:`False`|  
    |**Nombre de usuario**|Especificar el nombre de usuario que se utilizará para la autenticación con el servidor POP3. Esta propiedad necesita un valor. **Nota:** la cuenta especificada para la propiedad de nombre de usuario debe tener la capacidad de inicio de sesión a la red. El adaptador de POP3 se conecta al buzón asociado con la cuenta especificada para la propiedad Nombre de usuario. Por esta razón, el adaptador de POP3 no se puede usar para conectarse a un buzón que no sea el asignado a la cuenta especificada. Por ejemplo, aunque varias cuentas tengan permisos de lectura para el buzón asociado con una cuenta concreta, solo se puede especificar el nombre de cuenta real para el Nombre de usuario.|  
    |**Umbral de error**|Especificar el número máximo de errores de red o de protocolo que se esperará antes de cerrar el adaptador. Especificar el valor 0 para evitar que se cierre el adaptador.<br /><br /> Valor predeterminado: 10|  
    |**Intervalo de sondeo**|Especificar el intervalo entre intentos de recuperar mensajes del servidor POP3.<br /><br /> Valor predeterminado: 5|  
    |**Unidad de intervalo de sondeo**|Especificar la unidad de medida que se usará para la **intervalo de sondeo**.<br /><br /> Valor predeterminado = Minutos|  
  
6.  Haga clic en **Aceptar**.  
  
7.  En el **propiedades de la ubicación de recepción** diálogo cuadro, escriba los valores adecuados para completar la configuración de la ubicación de recepción y, a continuación, haga clic en **Aceptar** para guardar la configuración. Para obtener información sobre la **propiedades de ubicaciones de recepción** cuadro de diálogo, vea [cómo crear una ubicación de recepción](../core/how-to-create-a-receive-location.md).  
  
> [!NOTE]
>  El adaptador de POP3 generará un error y no podrá procesar ningún mensaje si el buzón para cuya lectura se ha configurado contiene más de 2.147.483.647 mensajes de correo electrónico. El adaptador de POP3 almacena el número de mensajes del buzón para cuya lectura se ha configurado en una variable Int32; el valor máximo para el tipo de dato Int32 es 2.147.483.647.  
  
> [!IMPORTANT]
>  Después de que el adaptador de POP3 haya recuperado correctamente un mensaje de correo electrónico de un buzón de destino, lo eliminará de éste. Este comportamiento forma parte del diseño predeterminado para ayudar a evitar que el adaptador de POP3 recupere varias copias de un mensaje de correo electrónico. No configure una ubicación de recepción de POP3 para que supervise un buzón si no se desea eliminar el correo electrónico del buzón.  
  
## <a name="see-also"></a>Vea también  
 [Configuración del adaptador de POP3](../core/configuring-the-pop3-adapter.md)