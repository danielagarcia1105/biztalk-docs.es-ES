---
title: CBRSample (ejemplo de BizTalk Server) | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, routing
- messages, filters
- outbound maps
- examples, messages
- messages, routing
- examples, outbound maps
- examples, filters
- messages, examples
ms.assetid: 8fba494c-9257-4eed-8b6a-867056147c2c
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b772bc44d4a745d5bfa330e7df7fcadcf2c020db
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2018
---
# <a name="cbrsample-biztalk-server-sample"></a>CBRSample (ejemplo de BizTalk Server)
El ejemplo CBRSample muestra cómo aplicar filtros y una asignación de salida para transformar y enrutar mensajes de instancias basándose en su contenido.  
  
## <a name="what-this-sample-does"></a>Descripción del ejemplo  
 Este ejemplo muestra el enrutamiento de un mensaje que contiene nombre, dirección e información de contacto de una de dos carpetas basándose en el código de país. En concreto, este ejemplo realiza lo siguiente:  
  
1.  Define un formato de mensaje de ejemplo que contiene información básica de una persona, incluida la identidad con Id. de usuario y nombre completo, dirección con código de país e información de contacto telefónico.  
  
2.  Promueve la **CountryCode** propiedad en el documento de entrada para que se puede usar en un filtro de puertos para controlar la transformación y el enrutamiento.  
  
3.  Transforma el mensaje en una versión canadiense cuando **CountryCode** es igual a 200 o una versión estadounidense cuando **CountryCode**es igual a 100. Dos transformaciones pasan a través de todos los datos excepto intermedio iniciales (**inicial**). La versión canadiense también asigna **estado** a **provincia** y **ZipCode** a **PinCode**.  
  
4.  Enruta los mensajes estadounidenses al directorio US y los mensajes canadienses al directorio CAN.  
  
## <a name="how-this-sample-is-designed-and-why"></a>Cómo se ha diseñado este ejemplo y por qué  
 El diseño se basa en las canalizaciones XML de envío y recepción predeterminadas, la promoción de propiedades, los filtros de suscripción y las asignaciones de salida en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para enrutar los mensajes. En la tabla siguiente se muestran los elementos de diseño y su justificación.  
  
|Elemento de diseño|Razones seleccionadas|  
|--------------------|--------------------------|  
|Canalización de recepción XML predeterminada|-La canalización XMLReceive admite la promoción de propiedad; la canalización PassThruReceive no.<br />-El mensaje entrante está en formato XML y no necesita procesamiento más allá de desensamblado básico y la resolución de entidades.|  
|Promoción de propiedades|-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]depende de los campos de propiedades para efectuar el enrutamiento. Los campos distintivos los utilizan las orquestaciones y no se pueden usar para enrutamiento.|  
|Filtro de suscripción|-El filtro de suscripción realiza el enrutamiento real mediante la captura de mensajes que cumplen uno o varios criterios basados en campos de propiedades.|  
|Asignación de salida|-Las asignaciones transforman datos de un formato a otro. El ejemplo asigna un mensaje entrante a un formato estadounidense o canadiense.|  
|XMLTransmit|-Realiza el ensamblado básico de los mensajes XML salientes; la canalización PassThruTransmit no ofrece compatibilidad adicional.|  
  
 Este patrón básico puede ampliarse y utilizarse para escenarios más complejos.  
  
## <a name="where-to-find-this-sample"></a>Ubicación del ejemplo  
 En este ejemplo se encuentra en <`Samples Path>`\Messaging\CBRSample\\.  
  
 En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.  
  
|Archivos|Description|  
|---------------|-----------------|  
|CBRDataCAN.Xml, CBRDataUS.Xml|Los archivos de entrada de ejemplo que se ajustan al esquema definido en el archivo CBRInputSchema.xsd.|  
|CBRInput2CANMap.btm, CBRInput2USMap.btm|Archivos de asignación para las transformaciones de formato canadiense y estadounidense, respectivamente.|  
|CBRInputSchema.xsd, CBROutputSchemaCAN.xsd, CBROutputSchemaUS.xsd|Archivos de esquema para el formato de entrada, el formato de salida canadiense y el formato de salida estadounidense, respectivamente.|  
|CBRPromotedPropertySchema.xsd|Archivo de esquema de la propiedad promocionada que corresponde a la **CountryCode** elemento del XML de los archivos de entrada.|  
|CBRSample.btproj, CBRSample.sln|Proyecto de BizTalk y archivos de solución para este ejemplo.|  
|Cleanup.bat|Se utiliza para anular la implementación de ensamblados y quitarlos de la caché de ensamblados global. Quita los puertos de envío y recepción. Quita los directorios virtuales de Internet Information Services (IIS) según sea necesario.|  
|Setup.bat|Se utiliza para crear e iniciar este ejemplo.|  
  
## <a name="how-to-use-this-sample"></a>Uso del ejemplo  
 Use este ejemplo como ejemplo de trabajo de las acciones necesarias para enrutar un mensaje basándose en el contenido.  
  
## <a name="building-and-initializing-this-sample"></a>Crear e inicializar este ejemplo  
 Para crear e inicializar el ejemplo CBRSample, deberá crear e implementar el proyecto de BizTalk para este ejemplo, configurar la ubicación y el puerto de recepción, así como configurar dos puertos de envío diferentes.  
  
#### <a name="to-build-and-deploy-the-biztalk-project-for-this-sample"></a>Para crear e implementar el proyecto de BizTalk para este ejemplo  
  
1.  En una ventana de comandos, desplácese a la siguiente carpeta:  
  
     `<Samples Path>` **\Messaging\CBRSample**  
  
2.  Ejecutar **Setup.bat**, que realiza las siguientes acciones:  
  
    -   Crea la entrada (**en**) y las carpetas de salida (**US** y **puede**) para este ejemplo.  
  
    -   Compila e implementa el proyecto de Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] para este ejemplo.  
  
    -   Crea y enlaza la ubicación de recepción de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y los puertos de envío y recepción.  
  
    > [!NOTE]
    >  Este ejemplo muestra la siguiente advertencia al crear y enlazar los puertos:  
    >   
    >  **Advertencia: No se especifica para el controlador de recepción "CBRReceiveLocation"; de la ubicación de recepción Actualizando con el primer controlador de recepción cuyo tipo de transporte coincidente.**  
    >   
    >  Puede omitir esta advertencia de forma segura. (Para dar cabida a posibles diferencias de nombre en las instalaciones de usuario, se han omitido del archivo de enlace el nombre del host y el controlador de recepción).  
  
    > [!NOTE]
    >  Antes de intentar ejecutar este ejemplo, debe confirmar que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no ha informado de ningún error durante el proceso de generación e inicialización.  
  
    > [!NOTE]
    >  Si selecciona abrir y crear el proyecto de este ejemplo sin ejecutar Setup.bat, debe crear, en primer lugar, un par de claves de nombre seguro mediante la utilidad de nombre seguro de .NET Framework (sn.exe). Utilice este par de claves para firmar el ensamblado resultante.  
  
    > [!NOTE]
    >  Para deshacer los cambios realizados por Setup.bat, ejecute Cleanup.bat. Debe ejecutar Cleanup.bat antes de ejecutar Setup.bat por segunda vez.  
  
#### <a name="to-prepare-to-configure-the-receive-port-and-location-and-the-send-ports"></a>Para preparar la configuración de la ubicación y el puerto de recepción, así como de los puertos de envío  
  
1.  En **Microsoft SQL Management Studio**, seleccione la base de datos de administración de BizTalk correcta.  
  
    > [!NOTE]
    >  La base de datos de administración de BizTalk también se denomina la base de datos de configuración de BizTalk.  
  
#### <a name="to-configure-enlist-and-start-the-us-send-port"></a>Para configurar, dé de alta e inicie el puerto de envío estadounidense  
  
1.  En la consola de administración de BizTalk Server, expanda **puertos de envío**, haga clic en **CBRUSSendPort**y, a continuación, haga clic en **editar**.  
  
2.  En el **propiedades de puerto de envío de unidireccional estático** cuadro de diálogo, en el árbol de carpetas a la izquierda del cuadro de diálogo, seleccione **filtros & asignación &#124; filtros**y, a continuación, agregue una nueva fila estableciendo  **Propiedad** a **CBRSample.CountryCode**, dejando el **operador** columna establecida en **==**y la configuración de la **Valor** columna **100**.  
  
3.  En el árbol de carpetas a la izquierda del cuadro de diálogo, seleccione **filtros & asignación &#124; asignaciones de salida**, establezca el **asignar para aplicar** propiedad **CBRSample.CBRInput2USMap**, y, a continuación, haga clic en **Aceptar**. Puede que tenga que hacer clic en el botón de desplazamiento para ver la asignación.  
  
#### <a name="to-configure-enlist-and-start-the-canadian-send-port"></a>Para configurar, dé de alta e inicie el puerto de envío canadiense  
  
1.  En la consola de administración de BizTalk Server, expanda **puertos de envío**, haga clic en **CBRCANSendPort**y, a continuación, haga clic en **editar**.  
  
2.  En el **propiedades de puerto de envío de unidireccional estático** cuadro de diálogo, en el árbol de carpetas a la izquierda del cuadro de diálogo, seleccione **filtros & asignación &#124; filtros**y, a continuación, agregue una nueva fila estableciendo  **Propiedad** a **CBRSample.CountryCode**, dejando el **operador** columna establecida en **==**y la configuración de la **Valor** columna **200**.  
  
3.  En el árbol de carpetas a la izquierda del cuadro de diálogo, seleccione **filtros & asignación &#124; asignaciones de salida**, establezca el **asignar para aplicar** propiedad **CBRSample.CBRInput2CANMap** y, a continuación, haga clic en **Aceptar**.  
  
 Mediante estos pasos se conecta el puerto de envío al puerto de recepción. El ejemplo utiliza las propiedades promocionadas para enrutar los documentos.  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] está preparado para trabajar con este ejemplo.  
  
## <a name="running-this-sample"></a>Ejecución del ejemplo  
 Utilice el siguiente procedimiento para ejecutar el ejemplo CBRSample.  
  
#### <a name="to-run-this-sample"></a>Para ejecutar el ejemplo  
  
1.  Copie los archivos de entrada, **CBRDataCAN.xml** y **CBRDataUS.xml**, en la carpeta de entrada siguiente:  
  
     `<Samples Path>` **\Messaging\CBRSample\In**  
  
2.  Observe cómo cada uno de estos archivos se transforma y enrutan a uno de los siguientes dos carpetas de salida en función del valor de sus **CountryCode** elemento (100 frente a 200):  
  
    -   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] transforma y enruta el archivo de entrada **CBRDataCAN.xml** a la carpeta:  
  
         `<Samples Path>` **\Messaging\CBRSample\CAN**  
  
    -   BizTalk Server transforma y enruta el archivo de entrada **CBRDataUS.xml** a la carpeta:  
  
         `<Samples Path>` **\Messaging\CBRSample\US**  
  
## <a name="classes-or-methods-used-in-this-sample"></a>Clases o métodos usados en el ejemplo  
 Ninguno.  
  
## <a name="see-also"></a>Vea también  
 [Canalizaciones predeterminadas](../core/default-pipelines.md)   
 [Cómo configurar asignaciones de salida para un puerto de envío](../core/how-to-configure-outbound-maps-for-a-send-port.md)   
 [Messaging (carpeta de ejemplos de BizTalk Server)](../core/messaging-biztalk-server-samples-folder.md)