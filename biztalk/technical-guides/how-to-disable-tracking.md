---
title: "Cómo deshabilitar el seguimiento | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4b1e6cdd-8266-494d-b6e7-260ac5a4f2fb
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 31476c3a538427a8c582533fbb0d7ad0418e3a0f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-disable-tracking"></a>Cómo deshabilitar el seguimiento
Este tema describe cómo deshabilitar el seguimiento mediante la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración. Puede configurar diversas opciones de seguimiento en tiempo de ejecución para las orquestaciones, puertos de envío, puertos de recepción y canalizaciones mediante el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración. Se pueden cambiar las opciones de seguimiento de un elemento en cualquier momento, sin necesidad de interrumpir el proceso empresarial.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server. Para obtener más información acerca de los permisos, consulte [permisos para administrar una aplicación](../technical-guides/permissions-for-managing-an-application.md).  
  
> [!NOTE]  
>  Si sólo desea ver las opciones de seguimiento, puede haber iniciado la sesión como miembro del [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] grupo de operadores.  
  
##  <a name="BKMK_DisableOrchTracking"></a>Para deshabilitar el seguimiento para una orquestación  
  
1.  Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **administración**, expanda el grupo de BizTalk, expanda **aplicaciones**y, a continuación, expanda la aplicación que contiene la orquestación para la que va a configurar el seguimiento.  
  
3.  Haga clic en **orquestaciones**y en el panel derecho, haga clic en la orquestación para la que desea configurar el seguimiento y, a continuación, haga clic en **propiedades**.  
  
4.  Haga clic en el **seguimiento** ficha, deshabilitar las opciones de seguimiento tal como se describe en la tabla siguiente y, a continuación, haga clic en **Aceptar**.  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Seguimiento de eventos - orquestación inicial y final**|Desactive esta casilla para deshabilitar el seguimiento de la instancia de orquestación antes y después de procesar todo el proceso empresarial.|  
    |**Seguimiento de eventos - envío y recepción de mensajes**|Desactive esta casilla para deshabilitar el seguimiento del mensaje de envío y recepción de eventos. Esta casilla de verificación sólo está disponible si selecciona el **orquestación inicial y final** casilla de verificación.|  
    |**Seguimiento de eventos - forma Inicio y finalización**|Desactive esta casilla de verificación cuando no necesite depurar instancias de orquestación en el depurador de orquestaciones. Al activar esta casilla, se llena la lista de eventos del Depurador de orquestaciones. Esta casilla de verificación sólo está disponible si selecciona el **orquestación inicial y final** casilla de verificación.|  
    |**Realizar un seguimiento de partes de mensaje – antes del procesamiento de orquestación**|Desactive esta casilla para deshabilitar la opción de guardar y realizar un seguimiento del contenido real del mensaje antes del procesamiento por la instancia de orquestación. Esta casilla de verificación sólo está disponible si selecciona el **el mensaje de envío y recepción** casilla de verificación.|  
    |**Realizar un seguimiento de cuerpos de mensaje - después del procesamiento de orquestación**|Desactive esta casilla para deshabilitar el almacenamiento y el seguimiento del contenido real del mensaje después del procesamiento de la instancia de orquestación. Esta casilla de verificación sólo está disponible si selecciona el **el mensaje de envío y recepción** casilla de verificación.|  
    |**Seguimiento de propiedades de mensaje - mensajes entrantes**|Desactive esta casilla para deshabilitar el seguimiento de las propiedades promocionadas de un mensaje entrante. Esta casilla de verificación sólo está disponible si selecciona el **el mensaje de envío y recepción** casilla de verificación.|  
    |**Seguimiento de propiedades de mensaje - mensajes salientes**|Desactive esta casilla para deshabilitar el seguimiento de las propiedades promocionadas de un mensaje saliente.  Esta casilla de verificación sólo está disponible si selecciona el **el mensaje de envío y recepción** casilla de verificación.|  
  
### <a name="to-disable-tracking-for-a-send-port"></a>Para deshabilitar el seguimiento de un puerto de envío  
  
1.  Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **administración**, expanda el grupo de BizTalk, expanda **aplicaciones**y, a continuación, expanda la aplicación que contiene el puerto de envío para el que va a configurar realizar un seguimiento.  
  
3.  Haga clic en **puertos de envío**, haga clic en el puerto de envío, haga clic en **propiedades**y, a continuación, haga clic en **seguimiento**.  
  
4.  Deshabilitar las opciones de seguimiento tal como se describe en la tabla siguiente y, a continuación, haga clic en **Aceptar**.  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Realizar un seguimiento de cuerpos de mensaje - mensaje de solicitud antes de procesamiento de puerto**|Desactive esta casilla para deshabilitar Guardar y seguimiento de contenido de los mensajes antes de que se recibe el mensaje. **Nota:** debe habilitar el seguimiento de canalización partes de mensaje realizar el seguimiento correctamente el mensaje de respuesta antes de procesamiento de puerto.|  
    |**Realizar un seguimiento de cuerpos de mensaje - mensaje de solicitud después del procesamiento de puerto**|Desactive esta casilla para deshabilitar Guardar y seguimiento del contenido del mensaje una vez recibido el mensaje.|  
    |**Realizar un seguimiento de cuerpos de mensaje - mensaje de respuesta antes de procesamiento de puerto**|Desactive esta casilla para deshabilitar Guardar y seguimiento de contenido de los mensajes antes de enviar el mensaje. Esta casilla de verificación sólo está disponible en los puertos de envío de petición-respuesta.|  
    |**Realizar un seguimiento de cuerpos de mensaje - mensaje de respuesta después del procesamiento de puerto**|Desactive esta casilla para deshabilitar Guardar y seguimiento de contenido de los mensajes después de enviar el mensaje. Esta casilla de verificación sólo está disponible en los puertos de envío de petición-respuesta.|  
    |**Seguimiento de propiedades de mensaje - mensaje de solicitud antes de procesamiento de puerto**|Desactive esta casilla para deshabilitar el seguimiento de las propiedades promocionadas de un mensaje entrante.|  
    |**Seguimiento de propiedades de mensaje - mensaje de solicitud después del procesamiento de puerto**|Desactive esta casilla de verificación si no desea realizar un seguimiento de las propiedades promocionadas de un mensaje saliente.|  
    |**Seguimiento de propiedades de mensaje - mensaje de respuesta antes de procesamiento de puerto**|Desactive esta casilla para deshabilitar Guardar y seguimiento de propiedades del mensaje antes de enviar el mensaje. Esta casilla de verificación sólo está disponible en los puertos de envío de petición-respuesta.|  
    |**Seguimiento de propiedades de mensaje - mensaje de respuesta después del procesamiento de puerto**|Desactive esta casilla para deshabilitar la opción de guardar y realizar un seguimiento de propiedades después de enviar el mensaje. Esta casilla de verificación sólo está disponible en los puertos de envío de petición-respuesta.|  
  
### <a name="to-disable-tracking-for-a-receive-port"></a>Para deshabilitar el seguimiento de un puerto de recepción  
  
1.  Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **administración**, expanda el grupo de BizTalk, expanda **aplicaciones**y, a continuación, expanda la aplicación que contiene el puerto de recepción para el que desea configurar el seguimiento.  
  
3.  Haga clic en **puertos de recepción**, haga clic en el puerto de recepción y, a continuación, haga clic en **seguimiento**.  
  
4.  Deshabilitar las opciones de seguimiento tal como se describe en la tabla siguiente y, a continuación, haga clic en **Aceptar**.  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Realizar un seguimiento de cuerpos de mensaje - mensaje de solicitud antes de procesamiento de puerto**|Desactive esta casilla para deshabilitar Guardar y seguimiento de contenido de los mensajes antes de que se recibe el mensaje.|  
    |**Realizar un seguimiento de cuerpos de mensaje - mensaje de solicitud después del procesamiento de puerto**|Desactive esta casilla para deshabilitar Guardar y seguimiento del contenido del mensaje una vez recibido el mensaje.|  
    |**Realizar un seguimiento de cuerpos de mensaje - mensaje de respuesta antes de procesamiento de puerto**|Desactive esta casilla para deshabilitar Guardar y seguimiento de contenido de los mensajes antes de enviar el mensaje. Esta casilla de verificación sólo está disponible en los puertos de recepción de solicitud-respuesta. **Nota:** debe habilitar el seguimiento de canalización partes de mensaje realizar el seguimiento correctamente el mensaje de respuesta antes de procesamiento de puerto.|  
    |**Realizar un seguimiento de cuerpos de mensaje - mensaje de respuesta después del procesamiento de puerto**|Desactive esta casilla para deshabilitar Guardar y seguimiento de contenido de los mensajes después de enviar el mensaje. Esta casilla de verificación sólo está disponible en los puertos de recepción de solicitud-respuesta.|  
    |**Seguimiento de propiedades de mensaje - mensaje de solicitud antes de procesamiento de puerto**|Desactive esta casilla para deshabilitar el seguimiento de las propiedades promocionadas de un mensaje entrante.|  
    |**Seguimiento de propiedades de mensaje - mensaje de solicitud después del procesamiento de puerto**|Desactive esta casilla de verificación si no desea realizar un seguimiento de las propiedades promocionadas de un mensaje saliente.|  
    |**Seguimiento de propiedades de mensaje - mensaje de respuesta antes de procesamiento de puerto**|Desactive esta casilla para deshabilitar Guardar y seguimiento de propiedades del mensaje antes de enviar el mensaje. Esta casilla de verificación sólo está disponible en los puertos de recepción de solicitud-respuesta.|  
    |**Seguimiento de propiedades de mensaje - mensaje de respuesta después del procesamiento de puerto**|Desactive esta casilla para deshabilitar la opción de guardar y realizar un seguimiento de propiedades después de enviar el mensaje. Esta casilla de verificación sólo está disponible en los puertos de recepción de solicitud-respuesta.|  
  
### <a name="to-disable-tracking-for-a-policy"></a>Para deshabilitar el seguimiento de una directiva  
  
1.  Haga clic en **iniciar**, haga clic en **programas**, haga clic en **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **administración**, expanda el grupo de BizTalk, expanda **aplicaciones**y, a continuación, expanda la aplicación que contiene la directiva para el que va a configurar realizar un seguimiento.  
  
3.  Haga clic en **directivas**, haga clic en la directiva, haga clic en **propiedades**y, a continuación, haga clic en **seguimiento**.  
  
4.  Deshabilitar las opciones de seguimiento tal como se describe en la tabla siguiente y, a continuación, haga clic en **Aceptar**.  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Actividad rápida**|Desactive esta casilla para deshabilitar el seguimiento de los datos de instancia en el que opera la directiva.|  
    |**Evaluación de condición**|Desactive esta casilla para deshabilitar el seguimiento de los resultados true/false de las condiciones de la directiva seleccionada.|  
    |**Activación de reglas**|Desactive esta casilla para deshabilitar el seguimiento de las acciones iniciadas como resultado de la directiva.|  
    |**Actualizaciones de agenda**|Desactive esta casilla para deshabilitar el seguimiento de las actualizaciones a la agenda. La agenda contiene una lista de acciones definidas como “true” que deben activarse.|  
  
### <a name="to-disable-tracking-for-a-schema"></a>Para deshabilitar el seguimiento de un esquema  
  
1.  Haga clic en **iniciar**, haga clic en **programas**, haga clic en **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **administración**, expanda el grupo de BizTalk, expanda **aplicaciones**y, a continuación, expanda la aplicación que contiene el esquema para el que va a configurar realizar un seguimiento.  
  
3.  Haga clic en **esquemas**, haga clic en el esquema y, a continuación, haga clic en **propiedades**.  
  
4.  En el panel izquierdo, haga clic en **seguimiento**.  
  
5.  Realice una de las siguientes acciones para especificar las propiedades que desea deshabilitar para el seguimiento de mensajes y, a continuación, haga clic en **Aceptar**:  
  
    -   Desactive el **hacer siempre el seguimiento de todas las propiedades** casilla de verificación si no desea utilizar todas las propiedades de mensaje independientemente de la versión de esquema. Esta casilla de verificación está disponible sólo para esquemas de documentos.  
  
    -   Desactive el **seleccionar todas las propiedades de mensaje** casilla de verificación si no desea utilizar todas las propiedades enumeradas.  
  
    -   En **lista de propiedades**, desactive la casilla de cada propiedad que no desea utilizar.  
  
    > [!NOTE]  
    >  Debe seleccionar sólo las opciones que necesita, dado que los mensajes de seguimiento crea rendimiento y la sobrecarga de almacenamiento para el sistema.  
  
### <a name="to-disable-tracking-for-a-pipeline"></a>Para deshabilitar el seguimiento de una canalización  
  
1.  Haga clic en **iniciar**, haga clic en **programas**, haga clic en **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
    > [!NOTE]  
    >  Si establece opciones de seguimiento en las canalizaciones, también establecerá las opciones de seguimiento globalmente para todos los puertos que usa la canalización. Esto, a su vez, puede hacer mucho más datos sometidos a seguimiento que se pretende, lo que ralentizará el rendimiento del sistema. En su lugar, puede establecer opciones de seguimiento en el envío de puertos y puertos de recepción.  
  
2.  En el árbol de consola, expanda [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **administración**, expanda el grupo de BizTalk, expanda **aplicaciones**y, a continuación, expanda la aplicación que contiene la canalización para el que va a configurar realizar un seguimiento.  
  
3.  Realice una de las siguientes operaciones:  
  
    -   Para deshabilitar el seguimiento para una de manera predeterminada las canalizaciones de BizTalk, expanda \<todos los artefactos >.  
  
    -   Para deshabilitar el seguimiento para una canalización personalizada que se haya implementado en una aplicación de BizTalk, expanda la aplicación que contiene la canalización.  
  
4.  Haga clic en el **canalizaciones** carpeta, haga clic en la canalización y, a continuación, haga clic en **seguimiento**.  
  
    > [!NOTE]  
    >  Para deshabilitar el seguimiento para varias canalizaciones a la vez, mantenga presionada la tecla MAYÚS, haga clic en cada canalizaciones que desea configurar, haga clic en una de las canalizaciones y, a continuación, haga clic en **seguimiento**.  
  
5.  Deshabilitar las opciones de seguimiento tal como se describe en la tabla siguiente y, a continuación, haga clic en **Aceptar**.  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Puerto eventos de inicio y finalización**|Desactive esta casilla para deshabilitar el seguimiento sólo cuando se inicia y finaliza una instancia. Los detalles incluyen el nombre de elemento, el ensamblado y otros metadatos.|  
    |**Mensaje de enviar y recibir eventos**|Desactive esta casilla para deshabilitar el seguimiento del mensaje de envío y recepción de eventos. Esta casilla de verificación está disponible solo si **eventos de inicio y fin de puerto** está seleccionada.|  
    |**Mensaje antes del procesamiento de canalización**|Desactive esta casilla para deshabilitar el seguimiento de cuerpos de los mensajes recibidos por la canalización y guardar, que contiene metadatos tales como las direcciones URL y las propiedades promocionadas. Si se trata de una canalización de recepción, el cuerpo del mensaje es el mensaje sin procesar que envía el componente de transporte a la canalización. En función de la aplicación, el mensaje podría estar cifrado, firmado o codificado. Cuando se usa un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] mapa, si se trata de una canalización de recepción, el seguimiento se efectúa después de procesa la asignación de entrada.<br /><br /> Esta casilla de verificación está disponible solo si **envío de mensajes y recibir eventos** está seleccionada.|  
    |**Mensaje después del procesamiento de canalización**|Desactive esta casilla para deshabilitar el seguimiento de cuerpos de los mensajes enviados por la canalización y guardar, que contiene metadatos tales como las direcciones URL y las propiedades promocionadas. Si se trata de una canalización de recepción, el cuerpo del mensaje es el mensaje procesado que se va a enviar a la base de datos de cuadro de mensajes, que puede ser XML, según la aplicación que utilice. Cuando se usa un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] mapa, si se trata de una canalización de envío, el seguimiento se efectúa antes de procesa la asignación de salida.<br /><br /> Esta casilla de verificación está disponible solo si **envío de mensajes y recibir eventos** está seleccionada.|  
  
## <a name="see-also"></a>Vea también  
 [Mantener el rendimiento](../technical-guides/maintaining-performance.md)