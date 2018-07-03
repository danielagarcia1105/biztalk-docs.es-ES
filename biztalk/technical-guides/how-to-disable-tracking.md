---
title: Cómo deshabilitar el seguimiento de | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4b1e6cdd-8266-494d-b6e7-260ac5a4f2fb
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 848f8e8f27c9817b9805e82b002f175006c5bba9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015693"
---
# <a name="how-to-disable-tracking"></a>Cómo deshabilitar el seguimiento
En este tema se describe cómo deshabilitar el seguimiento del uso de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración. Puede configurar diversas opciones de seguimiento en tiempo de ejecución para las orquestaciones, puertos de envío, puertos de recepción y canalizaciones mediante la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración. Se pueden cambiar las opciones de seguimiento de un elemento en cualquier momento, sin necesidad de interrumpir el proceso empresarial.  

## <a name="prerequisites"></a>Requisitos previos  
 Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server. Para obtener más información sobre los permisos, consulte [permisos para administrar una aplicación](../technical-guides/permissions-for-managing-an-application.md).  

> [!NOTE]
>  Si solo desea ver las opciones de seguimiento, puede haber iniciado la sesión como miembro del [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] grupo de operadores.  

##  <a name="BKMK_DisableOrchTracking"></a> Para deshabilitar el seguimiento para una orquestación  

1. Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  

2. En el árbol de consola, expanda [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **administración**, expanda el grupo de BizTalk, expanda **aplicaciones**y, a continuación, expanda la aplicación que contiene la orquestación para la que desea configurar el seguimiento.  

3. Haga clic en **orquestaciones**y en el panel derecho, haga clic en la orquestación que desea configurar el seguimiento y, a continuación, haga clic en **propiedades**.  

4. Haga clic en el **seguimiento** pestaña, deshabilitar las opciones de seguimiento tal como se describe en la tabla siguiente y, a continuación, haga clic en **Aceptar**.  

   |Use|Para|  
   |--------------|----------------|  
   |**Seguimiento de eventos - inicio de la orquestación y de finalización**|Desactive esta casilla para deshabilitar el seguimiento de la instancia de orquestación antes y después del procesamiento de todo el proceso empresarial.|  
   |**Seguimiento de eventos - envío y recepción de mensajes**|Desactive esta casilla para deshabilitar el seguimiento de mensaje de envío y recepción de eventos. Esta casilla solo está disponible si selecciona el **orquestación inicial y final** casilla de verificación.|  
   |**Seguimiento de eventos - forma Inicio y finalización**|Desactive esta casilla de verificación cuando no necesita depurar instancias de orquestación en el depurador de orquestaciones. Al activar esta casilla, se llena la lista de eventos del Depurador de orquestaciones. Esta casilla solo está disponible si selecciona el **orquestación inicial y final** casilla de verificación.|  
   |**Seguimiento de partes de mensaje – antes del procesamiento de orquestación**|Desactive esta casilla para deshabilitar la opción de guardar y realizar un seguimiento del contenido real del mensaje antes del procesamiento por la instancia de orquestación. Esta casilla solo está disponible si selecciona el **mensaje de envío y recepción** casilla de verificación.|  
   |**Realizar un seguimiento de cuerpos de mensaje - después del procesamiento de orquestación**|Desactive esta casilla para deshabilitar el almacenamiento y el seguimiento del contenido real del mensaje después del procesamiento de la instancia de orquestación. Esta casilla solo está disponible si selecciona el **mensaje de envío y recepción** casilla de verificación.|  
   |**Seguimiento de propiedades de mensaje - mensajes entrantes**|Desactive esta casilla para deshabilitar el seguimiento de las propiedades promocionadas de un mensaje entrante. Esta casilla solo está disponible si selecciona el **mensaje de envío y recepción** casilla de verificación.|  
   |**Seguimiento de propiedades de mensaje - mensajes salientes**|Desactive esta casilla para deshabilitar el seguimiento de las propiedades promocionadas de un mensaje saliente.  Esta casilla solo está disponible si selecciona el **mensaje de envío y recepción** casilla de verificación.|  

### <a name="to-disable-tracking-for-a-send-port"></a>Para deshabilitar el seguimiento de un puerto de envío  

1. Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  

2. En el árbol de consola, expanda [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **administración**, expanda el grupo de BizTalk, expanda **aplicaciones**y, a continuación, expanda la aplicación que contiene el puerto de envío para el que desea configurar realizar un seguimiento.  

3. Haga clic en **puertos de envío**, haga clic en el puerto de envío, haga clic en **propiedades**y, a continuación, haga clic en **seguimiento**.  

4. Deshabilitar las opciones de seguimiento tal como se describe en la tabla siguiente y, a continuación, haga clic en **Aceptar**.  

   |Use|Para|  
   |--------------|----------------|  
   |**Realizar un seguimiento de cuerpos de mensaje - mensaje de solicitud antes del procesamiento de puerto**|Desactive esta casilla para deshabilitar Guardar y seguimiento del contenido del mensaje antes de que se reciba el mensaje. **Nota:** debe habilitar el seguimiento de canalización del cuerpo de mensaje realizar el seguimiento correctamente el mensaje de respuesta antes de procesamiento de puerto.|  
   |**Realizar un seguimiento de cuerpos de mensaje - mensaje de solicitud después del procesamiento de puerto**|Desactive esta casilla para deshabilitar Guardar y seguimiento del contenido del mensaje una vez recibido el mensaje.|  
   |**Realizar un seguimiento de cuerpos de mensaje - mensaje de respuesta antes de procesamiento de puerto**|Desactive esta casilla para deshabilitar Guardar y seguimiento del contenido del mensaje antes de enviar el mensaje. Esta casilla de verificación sólo está disponible en los puertos de envío de petición-respuesta.|  
   |**Realizar un seguimiento de cuerpos de mensaje - mensaje de respuesta después del procesamiento de puerto**|Desactive esta casilla para deshabilitar Guardar y seguimiento del contenido del mensaje después de enviar el mensaje. Esta casilla de verificación sólo está disponible en los puertos de envío de petición-respuesta.|  
   |**Seguimiento de propiedades de mensaje - mensaje de solicitud antes del procesamiento de puerto**|Desactive esta casilla para deshabilitar el seguimiento de las propiedades promocionadas de un mensaje entrante.|  
   |**Seguimiento de propiedades de mensaje - mensaje de solicitud después del procesamiento de puerto**|Desactive esta casilla si no desea realizar un seguimiento de las propiedades promocionadas de un mensaje saliente.|  
   |**Seguimiento de propiedades de mensaje - mensaje de respuesta antes de procesamiento de puerto**|Desactive esta casilla para deshabilitar Guardar y seguimiento de propiedades del mensaje antes de enviar el mensaje. Esta casilla de verificación sólo está disponible en los puertos de envío de petición-respuesta.|  
   |**Seguimiento de propiedades de mensaje - mensaje de respuesta después del procesamiento de puerto**|Desactive esta casilla para deshabilitar la opción de guardar y realizar un seguimiento de propiedades después de enviar el mensaje. Esta casilla de verificación sólo está disponible en los puertos de envío de petición-respuesta.|  

### <a name="to-disable-tracking-for-a-receive-port"></a>Para deshabilitar el seguimiento de un puerto de recepción  

1. Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  

2. En el árbol de consola, expanda [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **administración**, expanda el grupo de BizTalk, expanda **aplicaciones**y, a continuación, expanda la aplicación que contiene el puerto de recepción para el que desea configurar el seguimiento.  

3. Haga clic en **puertos de recepción**, haga clic en el puerto de recepción y, a continuación, haga clic en **seguimiento**.  

4. Deshabilitar las opciones de seguimiento tal como se describe en la tabla siguiente y, a continuación, haga clic en **Aceptar**.  

   |Use|Para|  
   |--------------|----------------|  
   |**Realizar un seguimiento de cuerpos de mensaje - mensaje de solicitud antes del procesamiento de puerto**|Desactive esta casilla para deshabilitar Guardar y seguimiento del contenido del mensaje antes de que se reciba el mensaje.|  
   |**Realizar un seguimiento de cuerpos de mensaje - mensaje de solicitud después del procesamiento de puerto**|Desactive esta casilla para deshabilitar Guardar y seguimiento del contenido del mensaje una vez recibido el mensaje.|  
   |**Realizar un seguimiento de cuerpos de mensaje - mensaje de respuesta antes de procesamiento de puerto**|Desactive esta casilla para deshabilitar Guardar y seguimiento del contenido del mensaje antes de enviar el mensaje. Esta casilla de verificación sólo está disponible en los puertos de recepción de solicitud-respuesta. **Nota:** debe habilitar el seguimiento de canalización del cuerpo de mensaje realizar el seguimiento correctamente el mensaje de respuesta antes de procesamiento de puerto.|  
   |**Realizar un seguimiento de cuerpos de mensaje - mensaje de respuesta después del procesamiento de puerto**|Desactive esta casilla para deshabilitar Guardar y seguimiento del contenido del mensaje después de enviar el mensaje. Esta casilla de verificación sólo está disponible en los puertos de recepción de solicitud-respuesta.|  
   |**Seguimiento de propiedades de mensaje - mensaje de solicitud antes del procesamiento de puerto**|Desactive esta casilla para deshabilitar el seguimiento de las propiedades promocionadas de un mensaje entrante.|  
   |**Seguimiento de propiedades de mensaje - mensaje de solicitud después del procesamiento de puerto**|Desactive esta casilla si no desea realizar un seguimiento de las propiedades promocionadas de un mensaje saliente.|  
   |**Seguimiento de propiedades de mensaje - mensaje de respuesta antes de procesamiento de puerto**|Desactive esta casilla para deshabilitar Guardar y seguimiento de propiedades del mensaje antes de enviar el mensaje. Esta casilla de verificación sólo está disponible en los puertos de recepción de solicitud-respuesta.|  
   |**Seguimiento de propiedades de mensaje - mensaje de respuesta después del procesamiento de puerto**|Desactive esta casilla para deshabilitar la opción de guardar y realizar un seguimiento de propiedades después de enviar el mensaje. Esta casilla de verificación sólo está disponible en los puertos de recepción de solicitud-respuesta.|  

### <a name="to-disable-tracking-for-a-policy"></a>Para deshabilitar el seguimiento de una directiva  

1. Haga clic en **iniciar**, haga clic en **programas**, haga clic en **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  

2. En el árbol de consola, expanda [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **administración**, expanda el grupo de BizTalk, expanda **aplicaciones**y, a continuación, expanda la aplicación que contiene la directiva para el que desea configurar realizar un seguimiento.  

3. Haga clic en **directivas**, haga clic en la directiva, haga clic en **propiedades**y, a continuación, haga clic en **seguimiento**.  

4. Deshabilitar las opciones de seguimiento tal como se describe en la tabla siguiente y, a continuación, haga clic en **Aceptar**.  

   |Use|Para|  
   |--------------|----------------|  
   |**Actividad rápida**|Desactive esta casilla para deshabilitar el seguimiento de los datos de instancia en los que opera la directiva.|  
   |**Evaluación de condición**|Desactive esta casilla para deshabilitar el seguimiento de los resultados true/false de las condiciones de la directiva seleccionada.|  
   |**Activación de reglas**|Desactive esta casilla para deshabilitar el seguimiento de las acciones iniciadas como resultado de la directiva.|  
   |**Actualizaciones de agenda**|Desactive esta casilla para deshabilitar el seguimiento de las actualizaciones a la agenda. La agenda contiene una lista de acciones definidas como “true” que deben activarse.|  

### <a name="to-disable-tracking-for-a-schema"></a>Para deshabilitar el seguimiento de un esquema  

1. Haga clic en **iniciar**, haga clic en **programas**, haga clic en **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  

2. En el árbol de consola, expanda [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **administración**, expanda el grupo de BizTalk, expanda **aplicaciones**y, a continuación, expanda la aplicación que contiene el esquema para el que desea configurar realizar un seguimiento.  

3. Haga clic en **esquemas**, haga clic en el esquema y, a continuación, haga clic en **propiedades**.  

4. En el panel izquierdo, haga clic en **seguimiento**.  

5. Realice una de las siguientes opciones para especificar qué propiedades que desee deshabilitar para el seguimiento de mensajes y, a continuación, haga clic en **Aceptar**:  

   -   Desactive el **siempre realizar un seguimiento de todas las propiedades** casilla de verificación si no desea utilizar todas las propiedades de mensaje independientemente de la versión de esquema. Esta casilla de verificación está disponible sólo para esquemas de documentos.  

   -   Desactive el **seleccionar todas las propiedades de mensaje** casilla de verificación si no desea utilizar todas las propiedades enumeradas.  

   -   En **lista propiedades**, desactive la casilla de cada propiedad que no desea utilizar.  

   > [!NOTE]  
   >  Debe seleccionar sólo las opciones que necesita, porque el seguimiento de mensajes crea rendimiento y sobrecarga de almacenamiento para el sistema.  

### <a name="to-disable-tracking-for-a-pipeline"></a>Para deshabilitar el seguimiento de una canalización  

1. Haga clic en **iniciar**, haga clic en **programas**, haga clic en **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  

   > [!NOTE]  
   >  Si configura las opciones de seguimiento de canalizaciones, también establecerá las opciones de seguimiento globalmente para todos los puertos que usa la canalización. Esto, a su vez, puede hacer mucho más datos sometidos a seguimiento previstos, lo que ralentizará el rendimiento del sistema. En su lugar, puede establecer las opciones de seguimiento en el envío de puertos y los puertos de recepción.  

2. En el árbol de consola, expanda [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **administración**, expanda el grupo de BizTalk, expanda **aplicaciones**y, a continuación, expanda la aplicación que contiene la canalización para el que desea configurar realizar un seguimiento.  

3. Realice una de las siguientes operaciones:  

   -   Para deshabilitar el seguimiento para una de las predeterminadas canalizaciones de BizTalk, expanda \<todos los artefactos\>.  

   -   Para deshabilitar el seguimiento de una canalización personalizada que se haya implementado en una aplicación de BizTalk, expanda la aplicación que contiene la canalización.  

4. Haga clic en el **canalizaciones** carpeta, haga clic en la canalización y, a continuación, haga clic en **seguimiento**.  

   > [!NOTE]  
   >  Para deshabilitar el seguimiento para varias canalizaciones a la vez, mantenga presionada la tecla MAYÚS, haga clic en cada canalización para configurar, haga clic en una de las canalizaciones y, a continuación, haga clic en **seguimiento**.  

5. Deshabilitar las opciones de seguimiento tal como se describe en la tabla siguiente y, a continuación, haga clic en **Aceptar**.  


   |                Use                |                                                                                                                                                                                                                                                                                                                                 Para                                                                                                                                                                                                                                                                                                                                 |
   |----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |     **Eventos de inicio y finalización de puerto**      |                                                                                                                                                                                                                                                                  Desactive esta casilla para deshabilitar el seguimiento sólo cuando una instancia se inicia y finaliza. Los detalles incluyen el nombre de elemento, el ensamblado y otros metadatos.                                                                                                                                                                                                                                                                  |
   |  **Envío y recepción de eventos de mensajes**   |                                                                                                                                                                                                                                                      Desactive esta casilla para deshabilitar el seguimiento del mensaje de enviar y recibir eventos. Esta casilla de verificación está disponible solo si **eventos de inicio y finalización de puerto** está seleccionada.                                                                                                                                                                                                                                                       |
   | **Mensaje antes del procesamiento de canalización** | Desactive esta casilla para deshabilitar guardando y seguimiento de cuerpos de los mensajes recibidos por la canalización, que contiene metadatos tales como las direcciones URL y las propiedades promocionadas. Si se trata de una canalización de recepción, el cuerpo del mensaje es el mensaje sin procesar que envía el componente de transporte a la canalización. En función de la aplicación, el mensaje podría estar cifrado, firmado o codificado. Cuando se usa un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] mapa, si se trata de una canalización de recepción, el seguimiento se efectúa después de procesa la asignación de entrada.<br /><br /> Esta casilla de verificación está disponible solo si **envío de mensajes y recibir eventos** está seleccionada. |
   | **Mensaje después del procesamiento de canalización**  |                        Desactive esta casilla para deshabilitar guardando y seguimiento de cuerpos de los mensajes enviados por la canalización, que contiene metadatos tales como las direcciones URL y las propiedades promocionadas. Si se trata de una canalización de recepción, el cuerpo del mensaje es el mensaje procesado que se va a enviar a la base de datos de cuadro de mensajes, que puede ser XML, según la aplicación que utilice. Cuando se usa un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] mapa, si se trata de una canalización de envío, el seguimiento se efectúa antes de procesa la asignación de salida.<br /><br /> Esta casilla de verificación está disponible solo si **envío de mensajes y recibir eventos** está seleccionada.                        |

## <a name="see-also"></a>Vea también  
 [Mantenimiento del rendimiento](../technical-guides/maintaining-performance.md)