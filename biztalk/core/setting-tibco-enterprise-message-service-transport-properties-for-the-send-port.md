---
redirect_url: /biztalk/core/creating-tibco-enterprise-message-service-send-handlers/
redirect_document_id: True
ROBOTS: NOINDEX
ms.openlocfilehash: 24e73be3b953cbd7f597a34a06f09d364ec0f4f4
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
---
# <a name="set-send-port-transport-properties-for-the-send-port-for-tibco-enterprise-message-service"></a>Establecer propiedades de transporte para el puerto de envío del puerto de envío para TIBCO Enterprise Message Service
Las propiedades de transporte de TIBCO Enterprise Message se configuran en tiempo de diseño y se usan en tiempo de ejecución. En el **propiedades de transporte** cuadro de diálogo, Establece los parámetros de conexión y credenciales específicas para el sistema de servidor y los objetos que está intentando obtener acceso.  
  
 ![](../core/media/tib-tibcoemssendtransportpropertiess.gif "TIB_TIBCOEMSSendTransportPropertiess")  
  
## <a name="enter-transport-properties"></a>Especifique las propiedades de transporte  
  
1.  En el **propiedades de transporte** cuadro de diálogo, expanda **definición del sistema**y escriba toda la información necesaria para la conexión al servidor TIBCO EMS.  
  
     Debe definir parámetros de configuración para conectar el Adaptador de Microsoft BizTalk para TIBCO Enterprise Message Service con TIBCO EMS. Estos datos distinguen entre mayúsculas y minúsculas.  
  
2.  Expanda **control de mensajes** y escriba toda la información necesaria.  
  
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
  
## <a name="see-also"></a>Vea también  
 [Proteger el adaptador](../core/security-in-biztalk-adapter-for-tibco-ems.md)  
 [Crear los artefactos de envío](../core/creating-tibco-enterprise-message-service-send-handlers.md)