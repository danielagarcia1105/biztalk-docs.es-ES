---
title: "Crear artefactos de envío de TIBCO EMS | Documentos de Microsoft"
description: "Crear el puerto de envío y configurar las propiedades de transporte para utilizar el adaptador de TIBCO Enterprise Message Service en BizTalk Server"
ms.custom: 
ms.date: 10/23/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8f82609c-1847-4796-a24c-28cb350ec739
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 570693f4d5644f0ea850a53ec537ce30db5ca568
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
---
# <a name="creating--tibco-enterprise-message-service-send-handlers"></a>Creación de controladores de envío de TIBCO Enterprise Message Service
Esta sección explica cómo establecer el puerto de envío para que se conecte con TIBCO Enterprise Message Service (EMS) y cómo incluir XML en la orquestación para que interactúe con TIBCO EMS en tiempo de ejecución.  


## <a name="create-a-send-port"></a>Crear un puerto de envío  
  
1.  En la consola de administración de BizTalk Server, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda la aplicación.  
  
2.  Haga clic en **puertos de envío**, seleccione **New**y, a continuación, seleccione **puerto de envío de petición-respuesta estático**.  
  
3.  En el **propiedades de puerto de envío**, realice lo siguiente:  
  
    1.  Escriba un nombre para el puerto de envío, por ejemplo, `SendToTIBCOEMS`.  
  
    2.  Desde el **tipo** lista desplegable, seleccione **TIBCO EMS**.  
  
    3.  Desde el **controlador de envío** lista desplegable, seleccione el URI.  
  
    4.  Desde el **canalización de envío** lista desplegable, seleccione **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**. Desde el **canalización de recepción** lista desplegable, seleccione **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**.  

        > [!NOTE]
        > El adaptador de BizTalk para TIBCO Enterprise Message Service requiere que seleccione XMLTransmit para envío y XMLReceive para recepción.  
  
    6.  Seleccione **configurar** para configurar el puerto de envío.  
  
4.  En el **propiedades de transporte de TIBCO EMS** diálogo cuadro, realice lo siguiente:  
  
    1.  Escriba **el control de mensajes**, **definición de conexión de servidor**, **compatibilidad con transacciones**, **nombre de usuario**y el  **contraseña**.  
  
         No tiene que establecer la información de inicio de sesión.  
  
    2.  En la lista, seleccione la aplicación afiliada que ha creado para representar el sistema TIBCO EMS.  
  
    3.  Para **usar SSO**, seleccione **Sí**.  
  
    4.  Seleccione **Aceptar**.  
  
5.  Seleccione **Aceptar**. 

## <a name="set-send-port-transport-properties"></a>Establecer propiedades de transporte del puerto de envío
Las propiedades de transporte de TIBCO Enterprise Message se configuran en tiempo de diseño y se usan en tiempo de ejecución. En el **propiedades de transporte**, establecer los parámetros de conexión y credenciales específicas para el sistema de servidor y los objetos que está intentando obtener acceso.  
  
 ![](../core/media/tib-tibcoemssendtransportpropertiess.gif "TIB_TIBCOEMSSendTransportPropertiess")  
  
  
1.  En el **propiedades de transporte**, expanda **definición del sistema**y escriba toda la información necesaria para la conexión al servidor TIBCO EMS.  
  
     Debe definir parámetros de configuración para conectar el Adaptador de Microsoft BizTalk para TIBCO Enterprise Message Service con TIBCO EMS. **Estos datos distingue mayúsculas de minúsculas.**  
  
2.  Expanda **control de mensajes**y escriba toda la información necesaria.  
  
    |Parámetro|Description|  
    |---------------|-----------------|  
    |`Message Expiration Time`|Entero que describe el tiempo que permanecerá el mensaje en la cola o tema; una vez que transcurra el tiempo, el servidor TIBCO EMS elimina el mensaje.<br /><br /> Es sinónimo del encabezado de propiedad del mensaje EMS.Expiration. Puede reemplazarse con la orquestación.<br /><br /> El valor predeterminado es 0 milisegundos, que indica que el mensaje no caducará desde el destino.|  
    |`Message is Persistent`|El servidor TIBCO EMS escribe los mensajes en el disco antes de que se confirmen.<br /><br /> Esta es la propiedad del encabezado TibcoEMS.DeliveryMode. Indica que los mensajes enviados persistan en la cola por parte del servidor antes de la recepción de la confirmación del mensaje al adaptador.<br /><br /> El valor predeterminado es **True**.|  
    |`Message Priority`|Rango numérico de 0 a 9, que define la prioridad del mensaje; cuando mayor sea el valor, mayor será la prioridad.<br /><br /> La prioridad afecta al orden en que el servidor envía mensajes a los consumidores (los valores mayores van primero).<br /><br /> La especificación JMS define diez niveles de valores de prioridad, desde cero (mínima prioridad) hasta 9 (máxima prioridad). La especificación sugiere que los clientes consideren los valores 0–4 como grados de prioridad normal y los valores 5–9 como grados de máxima prioridad.<br /><br /> Valor predeterminado es **4**.|  
  
3.  Expanda **definición de conexión de servidor** y escriba toda la información necesaria.  
  
    |Parámetro|Description|  
    |---------------|-----------------|  
    |`Destination`|Configuración obligatoria. Define el nombre y tipo de destino. Por ejemplo: staticqueue [Q1].<br /><br /> Define la cola o tema con el siguiente formato: {static} {dynamic] Queue [queuename] o {static} {dynamic] Topic [topicname]. **Nota:** puede enviar un mensaje a un destino que no existe. En tal caso, TIBCO Enterprise Message Service crea el destino; Esto se conoce como un *destino dinámico*. Se trata de un destino creado por un productor y eliminado cu ando se consume el mensaje y se desconecta el productor. A *destino estático* es un destino que solo se pueden crear por un administrador de servicios de TIBCO Enterprise Message. No puede conectarse a un puerto dinámico al abrir una conexión con el destino, pues el Adaptador de BizTalk para TIBCO Enterprise Message Service usa un mecanismo de bloqueo de nombres en el servidor. Solo son visibles los puertos estáticos cuando se usa la búsqueda de nombre. Al conectar con un puerto dinámico, puede usar destinos estáticos; no obstante, si no existe ningún destino de tal nombre, se creará uno. El destino le permite especificar explícitamente el tipo de destino que debe usar al definir el puerto. La sintaxis para el destino no distingue mayúsculas de minúsculas: staticqueue [nombre_de_cola], statictopic [topic_name], dynamicqueue [nombre_de_cola]; dynamictopic [topic_name].|  
    |`Port Number`|Puerto en que escucha el servidor TIBCO EMS.|  
    |`Server Name`|Configuración obligatoria. Nombre del sistema que hospeda el servidor TIBCO EMS.|  
  
4.  Proporcione credenciales mediante el inicio de sesión único (SSO).  
  
     Puede usar dos métodos para tener acceso al sistema TIBCO EMS. Puede usar credenciales (parámetros de nombre de usuario y contraseña) o el inicio de sesión único.  
  
    -   Seleccione **Sí** en el **usar SSO** usar Single Sign-On.  
  
    -   Seleccione una aplicación afiliada de la lista.  
  
         Una aplicación afiliada, creada por herramientas de inicio de sesión único empresarial, representa una aplicación como TBCO EMS. El Adaptador de BizTalk para TIBCO EMS usa las credenciales de un usuario de la aplicación. Estas credenciales se recuperan de la base de datos de SSO del sistema de servidor para una aplicación afiliada determinada.  
  
         Para obtener más información acerca de cómo crear una aplicación afiliada, vea [crear aplicaciones afiliadas](../core/creating-affiliate-applications5.md).  
  
5.  En **compatibilidad con transacciones**, seleccione **Sí** si este puerto de envío va a admitir transacciones.  
  
     Si habilita la compatibilidad con transacciones en el puerto, todas las orquestaciones que usen este puerto deberán ser transaccionales; en caso contrario, todas las llamadas se revertirán (por ejemplo, no se confirmarán). El objeto de ámbito agregado a la orquestación controla el ciclo de vida de la transacción.  
  
6.  Expanda **las credenciales de usuario** y escriba la **nombre de usuario** y **contraseña** para tener acceso al servidor TIBCO EMS.  
  
    |Parámetro|Description|  
    |---------------|-----------------|  
    |`Password`|La contraseña del usuario usada para comunicarse con un daemon TIBCO EMS.<br /><br /> Si no ha seleccionado **usar SSO**, debe establecer parámetros de credenciales para el adaptador de BizTalk para TIBCO EMS pueda comunicarse con un daemon TIBCO EMS.|  
    |`User Name`|Nombre de un usuario usado para comunicarse con un daemon TIBCO EMS.<br /><br /> Si no ha seleccionado **usar SSO**, debe establecer parámetros de credenciales para el adaptador de BizTalk para TIBCO EMS pueda comunicarse con un daemon TIBCO EMS.|  
  
7.  Haga clic en **aplicar**y, a continuación, haga clic en **Aceptar**.  

   
## <a name="next-steps"></a>Pasos siguientes
[Crear artefactos de recepción](../core/creating-tibco-enterprise-message-service-receive-handlers.md)  
[Propiedades de contexto del mensaje de TIBCO EMS](../core/message-context-properties-in-biztalk-server.md)