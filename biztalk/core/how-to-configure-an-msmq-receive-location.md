---
title: "Cómo configurar ubicación de recepción de MSMQ | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MSMQ adapters, receive locations
- receive locations, MSMQ adapters
- configuring [MSMQ adapters], receive locations
ms.assetid: ba25cf43-18f1-4c19-84fb-74c7b82b95a9
caps.latest.revision: "43"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 795b72318054525485a64c9dd704b81ddf6cb6b9
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="how-to-configure-an-msmq-receive-location"></a>Cómo configurar una ubicación de recepción MSMQ
Se pueden establecer variables de adaptador de ubicación de recepción de MSMQ en la consola de administración de BizTalk Server. Si no se definen las propiedades en la ubicación de recepción, se utilizarán los valores predeterminados del controlador de recepción definidos en la consola de administración de BizTalk Server.  
  
> [!NOTE]
>  Antes de completar este procedimiento, debe haber agregado un puerto de recepción. Para obtener más información, consulte [cómo crear un puerto de recepción](../core/how-to-create-a-receive-port.md).  
  
> [!IMPORTANT]
>  Si una instancia de host está asociada con una ubicación de recepción o un puerto de envío MSMQ, compruebe que el servicio MSMQ se está ejecutando en ese equipo. Si el servicio no está en ejecución, los puertos de recepción MSMQ se cerrarán poco después de que se inicien y se suspenderán los mensajes enviados a los puertos de envío MSMQ.  
>   
>  En un escenario agrupado, es necesario que tanto la instancia de MSMQ agrupada como el servicio MSMQ de cada uno de los equipos del clúster esté en ejecución.  
  
## <a name="to-configure-variables-for-an-msmq-receive-location"></a>Para configurar variables para una ubicación de recepción de MSMQ  
 Siga estos pasos para configurar variables para una ubicación de recepción MSMQ:  
  
1.  En la consola de administración de BizTalk Server, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda el aplicación que desea crear una ubicación de recepción.  
  
2.  En la consola de administración de BizTalk Server, en el panel izquierdo, haga clic en el **puerto de recepción** nodo. A continuación, en el panel de la derecha, haga clic con el botón secundario en el puerto de recepción asociado con una ubicación de recepción existente o que desee asociar con una nueva ubicación de recepción. A continuación, haga clic en **Propiedades**.  
  
3.  En el **propiedades de puerto de recepción** cuadro de diálogo, en el panel izquierdo, seleccione **ubicaciones de recepción**y, a continuación, en el panel derecho, haga doble clic en otra ubicación de recepción o haga clic en **New**para crear una nueva ubicación de recepción.  
  
4.  En el **propiedades de la ubicación de recepción** cuadro de diálogo, en la **transporte** junto a la sección **tipo**, seleccione **MSMQ** en la lista desplegable, y, a continuación, haga clic en **configurar**.  
  
5.  En el **propiedades de transporte de MSMQ** diálogo cuadro, realice lo siguiente:  
  
    |Use|Para|Date (tipo)|Valor predeterminado|  
    |--------------|----------------|---------------|-------------------|  
    |**Contraseña**|Establecer una contraseña para usarla con una cola remota.|String|En blanco|  
    |**Nombre de usuario**|Determinar el nombre de usuario que se utilizará, junto con la contraseña, para tener acceso a una cola remota. No se puede utilizar el usuario local del equipo remoto como nombre de usuario.|String|En blanco|  
    |**Tamaño del lote**|Configurar el tamaño de lote. El adaptador de MSMQ envía mensajes por lotes a la base de datos de cuadros de mensaje. El tamaño predeterminado del lote es 20 y el tamaño mínimo del lote es 1. **Nota:** si la **transaccional** propiedad para la ubicación de recepción se establece en **True**; cada lote de mensajes se envía a la base de datos de cuadro de mensajes en el contexto de un Microsoft Distributed Transacción de Transaction Coordinator (MSDTC). La transacción de MSDTC creada para un lote de mensajes permanece abierta hasta que todos los mensajes del lote se hayan guardado en el cuadro de mensajes y colocado en la cola de suscriptores apropiada. Por lo tanto, la duración de esta transacción de MSDTC aumenta en función del **tamaño de lote** parámetro aumenta. Puesto que tiene un gran número de transacciones de MSDTC abiertas al mismo tiempo puede afectar negativamente al rendimiento, la **tamaño de lote** parámetro no debe establecerse en un valor muy grande cuando se habilita la compatibilidad con transacciones.|int|20|  
    |**En caso de error**|Especificar el modo en que el adaptador debe responder a un error. Defina esta propiedad con uno de los siguientes valores:<br /><br /> -   **Detener.** detiene la recepción de mensajes a través de esta ubicación de recepción en caso de producirse un error.<br />-   **Suspend(Non-Resumable).** suspende los mensajes y los marca como no reanudables.<br />-   **Suspender (reanudable).** suspende los mensajes y los marca como reanudables. **Importante:** si la **True** opción **procesamiento ordenado** propiedad, el **detener** opción el **en caso de error** propiedad y el **False** opción el **transaccional** propiedad se aplican al mismo tiempo, a continuación, los mensajes que se producirá un error de entrega no se suspende o se deja en la cola de origen. En este escenario, puede que se pierda el mensaje. Para evitar la pérdida de datos, al utilizar el **procesamiento ordenado** característica, el **detener** opción el **en caso de error** propiedad sólo se aplica si la **es True**  opción el **transaccional** se aplica la propiedad. De este modo, si se produce un error de entrega, el mensaje original se colocará en la cola de origen de MSMQ. Si el **procesamiento ordenado** propiedad está establecida en un valor de **False** la **en caso de error** propiedad no surtirá efecto y si produce un error de entrega de mensaje del mensaje se suspenderá con un estado de **suspendido (reanudable)**.|String|Suspender (reanudable)|  
    |**Procesamiento ordenado**|Establezca esta propiedad en **True** o **False**. Indica si los mensajes se procesan en serie. Establecer la propiedad en **True** se alojará la entrega de mensajes ordenada cuando se utiliza junto con un puerto de envío de orquestación o mensajería de BizTalk que tiene el **entrega ordenada** opción establecida en  **True**. Para obtener más información, consulte [ordenada de mensajes de entrega](../core/ordered-delivery-of-messages.md).<br /><br /> Si se establece esta propiedad en **True** también optimiza el uso de recursos cuando se administran los mensajes de gran tamaño convirtiendo el adaptador en un único subproceso. Para obtener más información, consulte [enviar y recibir mensajes de gran tamaño mediante el adaptador de MSMQ](../core/sending-and-receiving-large-messages-using-the-msmq-adapter.md).|Boolean|False|  
    |**Cola**|Escribir una ruta válida de acceso a la cola. Dependiendo de la ruta de la cola especificada, el sistema realiza las validaciones oportunas. **Nota:** el URI para un envío de puerto o recibir ubicación no puede superar los 256 caracteres. **Nota:** : adaptador de recepción MSMQ utiliza un mecanismo de sondeo para supervisar la cola MSMQ especificada si hay mensajes nuevos cada 0,5 segundos. Este intervalo de 0,5 segundos es un intervalo fijo.|String|En blanco|  
    |**Transaccional**|Establezca esta propiedad en **True** o **False**. **Nota:** el adaptador admite lecturas transaccionales de colas remotas con Message Queue Server 4.0 o versiones posteriores únicamente. En este escenario el servidor BizTalk Server y el servidor remoto de Message Queue Server deben ejecutar Message Queue Server 4.0 o posterior. <br /><br /> Para obtener más información, consulte [configurar el adaptador de MSMQ](../core/configuring-the-msmq-adapter.md) y [consideraciones para ejecutar controladores de adaptador dentro de un Host en clúster](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md).|Boolean|False|  
  
    > [!NOTE]
    >  El **nombre de usuario** y **contraseña** solo se aplican a las cuentas de Windows que se utiliza para tener acceso a las colas remotas.  
  
6.  Haga clic en **Aceptar**.  
  
7.  En el **propiedades de la ubicación de recepción** diálogo cuadro, escriba los valores adecuados para completar la configuración de la ubicación de recepción y haga clic en **Aceptar** para guardar la configuración. Para obtener información sobre la **propiedades de ubicaciones de recepción** cuadro de diálogo, vea [cómo crear una ubicación de recepción](../core/how-to-create-a-receive-location.md).  
  
## <a name="see-also"></a>Vea también  
 [Configuración del adaptador de MSMQ](../core/configuring-the-msmq-adapter.md)