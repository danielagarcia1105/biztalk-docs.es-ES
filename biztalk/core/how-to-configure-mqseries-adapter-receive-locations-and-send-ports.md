---
title: Cómo configurar MQSeries adaptador ubicaciones de recepción y puertos de envío | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MQSeries adapters, receive ports
- receive ports, MQSeries adapters
- MQSeries adapters, send ports
- configuring [MQSeries adapters], send ports
- configuring [MQSeries adapters], receive ports
- send ports, MQSeries adapters
- configuring [MQSeries adapters], receive locations
- MQSeries adapters, receive locations
- receive locations, MQSeries adapters
ms.assetid: 552aacde-9ec0-4459-b369-073676b6f926
caps.latest.revision: 29
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 78de7ee2ac88dc0c000f4227e85659e9824b62ed
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006397"
---
# <a name="how-to-configure-mqseries-adapter-receive-locations-and-send-ports"></a>Cómo configurar MQSeries adaptador ubicaciones de recepción y puertos de envío
Puede configurar el adaptador de MQSeries tanto para ubicaciones de recepción como para puertos de envío.  

## <a name="to-configure-receive-locations-and-send-ports"></a>Procedimiento para configurar puertos de envío y ubicaciones de recepción  
 **Para crear el puerto de recepción y ubicación de recepción:**  

1. En la consola de administración de BizTalk Server, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda el aplicación en el que desea crear una ubicación de recepción.  

2. Haga clic en el **puertos de recepción** nodo, haga clic en **New,** y apuntar a **puerto de recepción unidireccional**.  

3. Escriba los valores apropiados en el **propiedades de puerto** cuadro de diálogo. Para obtener información sobre la **propiedades de puerto** cuadro de diálogo, vea [cómo crear un puerto de recepción](../core/how-to-create-a-receive-port.md).  

4. En la consola de administración de BizTalk Server, haga clic en el **puerto de recepción** nodo creado y, a continuación, haga clic en **propiedades**.  

5. En el **propiedades de puerto de recepción** cuadro de diálogo, en el panel izquierdo, seleccione **ubicaciones de recepción**y, a continuación, haga clic en **New** en el panel derecho.  

6. En el **propiedades de ubicación de recepción** cuadro de diálogo el **transporte** junto a la sección **tipo**, seleccione **MQSeries** en la lista desplegable lista y, a continuación, haga clic en **configurar**.  

7. En el **propiedades de transporte MQSeries** diálogo cuadro, realice lo siguiente:  


   |        Use        |                                                                                                                                                                                                                                                                                                                                                                                                                             Para                                                                                                                                                                                                                                                                                                                                                                                                                             |
   |------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |     **Tamaño de lote**     | Determinar el tamaño máximo de un lote de mensajes en KB. **Nota:** si el **admite transacciones** propiedad para la ubicación de recepción se establece en **Sí**; cada lote de mensajes se envía a la base de datos de cuadro de mensajes en el contexto de Microsoft Transacción de Distributed Transaction Coordinator (MSDTC). La transacción de MSDTC creada para un lote de mensajes permanece abierta hasta que todos los mensajes del lote se hayan guardado en el cuadro de mensajes y colocado en la cola de suscriptores apropiada. Por lo tanto, se aumenta la duración de esta transacción de MSDTC como el **tamaño máximo de lote** parámetro aumenta. Puesto que tener un gran número de transacciones de MSDTC abiertas al mismo tiempo puede afectar negativamente al rendimiento general, el **tamaño máximo de lote** parámetro no debe establecerse en un valor muy grande cuando se habilita la compatibilidad con transacciones. |
   | **Procesamiento ordenado** |                                                                                                                                                                                                                                                                                         Establecer MQSeries para que mantenga el orden de los mensajes tal como se reciben de la cola de MQSeries. **Nota:** para mantener el ordenamiento de mensajes de una cola específica, solo una instancia de Host de BizTalk puede estar recibiendo mensajes de dicha cola MQSeries. <br /><br /> **Valor predeterminado:** False                                                                                                                                                                                                                                                                                          |
   |       **Cola**        |                                                                                                                                                                                                                                                                                                                                                     Rellena con información de la **definición de la cola** cuadro de diálogo. **Nota:** el URI para un envío de puerto o recibir ubicación no puede superar los 256 caracteres.                                                                                                                                                                                                                                                                                                                                                      |
   |   **Transaccional**    |                                                                                                                                                                                                                                                                                                                   El adaptador inicia una transacción del Coordinador de transacciones distribuidas de Microsoft (DTC) entre BizTalk Server y MQSeries Server. Cuando se establece en **No**, no hay ninguna garantía de entrega de mensajes.<br /><br /> **Valor predeterminado:** False                                                                                                                                                                                                                                                                                                                   |


8. En el **propiedades de transporte MQSeries** cuadro de diálogo, haga clic en **Aceptar** para rellenar el **dirección (URI)** cuadro la **propiedades de ubicación de recepción**cuadro de diálogo.  

9. En el **propiedades de ubicación de recepción** diálogo cuadro, escriba los valores adecuados para completar la configuración de la ubicación de recepción y haga clic en **Aceptar** para guardar la configuración. Para obtener información sobre la **propiedades de las ubicaciones de recepción** cuadro de diálogo, vea [cómo crear una ubicación de recepción](../core/how-to-create-a-receive-location.md).  

   **Para crear el puerto de envío:**  

10. En la consola de administración de BizTalk Server, cree un puerto de envío estático nuevo. Consulte [cómo crear un puerto de envío](../core/how-to-create-a-send-port2.md) para obtener más información. Configure todas las opciones de puerto de envío y especifique **MQSeries** para el **tipo** opción el **transporte** sección de la **General** ficha.  

11. En el **General** ficha la **transporte** sección, haga clic en el **configurar** situado junto a **tipo**.  

12. En el **propiedades de transporte MQSeries** diálogo cuadro, realice lo siguiente:  

    |Property|Descripción|  
    |--------------|-----------------|  
    |**Tamaño de fragmentación**|Establece el tamaño del fragmento de mensaje en KB para los mensajes a medida que son enviados entre el adaptador y MQSAgent|  
    |**Aplicación afiliada de SSO**|Establece la aplicación afiliada de inicio de sesión único (SSO). El Id. de usuario y la contraseña de inicio de sesión único se usan para la **MQMD_UserIdentifier**y el **MQIIH_Authenticator** (o **MQCIH_Authenticator**) propiedad respectivamente.<br /><br /> **Valor predeterminado:** en blanco|  
    |**Conversión de datos**|Convierte el mensaje a la página de códigos ANSI de MQSeries para Windows Server.<br /><br /> Seleccione **Sí** para realizar esta conversión de Unicode a ANSI.<br /><br /> **Valor predeterminado:** n|  
    |**Ordenada**|Establece MQSeries para que mantenga el orden de los mensajes a medida que se envían a la cola MQSeries.<br /><br /> Seleccione **Sí** para mantener el orden de los mensajes. **Nota:** debe establecer el **notificación de entrega** propiedad en la orquestación para **transmitida** del puerto de envío. <br /><br /> **Valor predeterminado:** n|  
    |**Definición de la cola**|Rellenado con información de la **definición de la cola** cuadro de diálogo o directamente en el campo. **Nota:** el URI para un envío de puerto o recibir ubicación no puede superar los 256 caracteres.|  
    |**Segmentación permitida**|Utiliza la segmentación del administrador de cola MQSeries si un mensaje concreto sobrepasa la longitud máxima de mensajes de la cola MQSeries. Si selecciona **Sí**, MQSeries coloca los mensajes segmentados en la cola.<br /><br /> **Valor predeterminado:** n|  
    |**Compatibilidad con transacciones**|El adaptador comienza una transacción de DTC entre BizTalk Server y MQSeries Server. Cuando se establece en **No**, no hay ninguna garantía de entrega de mensajes.<br /><br /> **Valor predeterminado:** Sí **Nota:** no configure puertos de envío con diferentes **admite transacciones** configuración para enviar mensajes a la misma cola de MQSeries. **Nota:** a excepción de los escenarios de prueba, esta propiedad siempre debe establecerse en el valor predeterminado de **Sí**. Establecer esta propiedad en un valor de **No** en una producción entorno podrían provocar problemas inesperados.|  

     La ilustración siguiente muestra cómo puede configurar estas propiedades.  

     ![Cuadro de diálogo Propiedades de transporte MQSeries](../core/media/bts-dev-mqsendtransportprops.gif "BTS_Dev_MQSendTransportProps")  

13. Haga clic en el botón de puntos suspensivos (**...** ) situado a la derecha de la **definición de la cola** cuadro para definir la cola. Puede usar el **exportar** cuadro de diálogo, al igual que pudiera haber suscrito con la ubicación de recepción, para crear la cola inmediatamente o exportar un script que define la cola.  

14. Haga clic en **Aceptar** en cada cuadro de diálogo para cerrarlos y guardar la configuración.  

    **Para dar de alta el puerto de envío, inicie el puerto de envío y habilitar la ubicación de recepción:**  

15. Haga clic en el puerto de envío y haga clic en **Enlist** para dar de alta el puerto de envío.  

16. Haga clic en el puerto de envío y haga clic en **iniciar** para iniciar el puerto de envío.  

17. Haga clic en la ubicación de recepción y haga clic en **habilitar** para habilitar la ubicación de recepción.  

18. Revise el registro de sucesos para comprobar que no hay errores de BizTalk Server.  

## <a name="see-also"></a>Vea también  
 [Cómo configurar el adaptador de MQSeries controladores de recepción y envío](../core/how-to-configure-mqseries-adapter-send-and-receive-handlers.md)   
 [Configuración del adaptador de MQSeries](../core/configuring-the-mqseries-adapter.md)