---
title: FlatFileReceive (ejemplo de BizTalk Server) | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 90bd9e8d-6ed9-49c4-8437-c0c8b2a9a78d
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: db996437cce8cb6f89fb00b589fcbc95429e72f2
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="flatfilereceive-biztalk-server-sample"></a>FlatFileReceive (ejemplo de BizTalk Server)
El ejemplo FlatFileReceive muestra cómo puede usar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para procesar un archivo sin formato en el archivo .xml equivalente.  
  
## <a name="what-this-sample-does"></a>Descripción del ejemplo  
 Este ejemplo configura la carpeta FFInput como ubicación de recepción. Cuando se coloca un archivo, como el archivo de ejemplo FlatFileReceive_in.txt, en esta carpeta, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] procesa el mensaje de este archivo mediante los siguientes pasos:  
  
1.  Lee el mensaje del archivo de entrada en la carpeta FFInput de la ubicación de recepción.  
  
2.  En la canalización de recepción, el componente Desensamblador de archivo sin formato convierte el mensaje sin formato en el mensaje XML equivalente.  
  
3.  En la base de datos de cuadro de mensajes, el mensaje se enruta a un puerto de envío FILE que escribe el mensaje XML en un archivo de la carpeta del adaptador de envío FFOutput.  
  
## <a name="how-this-sample-is-designed-and-why"></a>Cómo se ha diseñado este ejemplo y por qué  
 El mensaje de ejemplo determina la mayor parte del diseño básico de este ejemplo. Los mensajes de archivos sin formato se deben desensamblar con el Desensamblador de archivo sin formato y un esquema de archivo sin formato en la canalización de recepción personalizada. Estos y otros elementos de diseño se resumen en la siguiente tabla.  
  
|Elemento de diseño|Razones seleccionadas|  
|--------------------|--------------------------|  
|Canalización de recepción personalizada|-La canalización personalizada utiliza el Desensamblador de archivos sin formato y mensajes de pedido de compra de un esquema de archivo sin formato para traducir los entrantes. El Desensamblador de archivos sin formato no es una canalización y no puede utilizarse al configurar una canalización de recepción en la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].|  
|Esquema de archivos sin formato|-Definen todas las mismas características registros y campos (incluida la estructura) como un esquema XML y proporcionan un mecanismo para definir todas las características de archivo sin formato que se necesitan para traducir un mensaje de instancia de archivo sin formato en una instancia XML equivalente mensaje (o viceversa).|  
|Filtro de suscripción|-El filtro de suscripción realiza el enrutamiento real mediante la captura de mensajes que cumplen uno o varios criterios basados en campos de propiedades.|  
|XMLTransmit|-Realiza el ensamblado básico de salida XML mensajes cuando sea necesario. La canalización PassThruTransmit no ofrece compatibilidad adicional.|  
  
 Estos elementos se combinan para producir una solución que acepta mensajes de pedido de compra en archivos sin formato en la ubicación de recepción y escribe la representación XML resultante en la ubicación de envío.  
  
 Las siguientes consideraciones se aplican al diseño de este ejemplo:  
  
-   El esquema de archivo sin formato (PO.xsd) contiene anotaciones ampliadas que describen la estructura del archivo de pedido sin formato. Estos archivos se pueden crear manualmente, pero muchos pueden generarse mediante el asistente para archivos sin formato.  
  
-   El esquema de archivo sin formato utiliza un valor de elementFormDefault de Unqualified. De este modo, se generan resultados correctos pero con calificaciones del espacio de nombres XML (xmlns) adicionales e inesperadas. Para evitar este problema, use un valor Qualified para elementFormDefault.  
  
-   XMLTransmit se utiliza como la canalización de envío. Utilice la canalización PassThruTransmit cuando no resulte necesario realizar la degradación de la propiedad u otro procesamiento de mensajes en el puerto de envío.  
  
## <a name="where-to-find-this-sample"></a>Ubicación del ejemplo  
 *\<Ejemplos de ruta de acceso\>*\Pipelines\AssemblerDisassembler\FlatFileReceive\  
  
 En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.  
  
|Archivos|Description|  
|---------------|-----------------|  
|Cleanup.bat|Se utiliza para anular la implementación de ensamblados y quitarlos de la caché de ensamblados global. Quita los puertos de envío y recepción. Quita los directorios virtuales de los Servicios de Microsoft Internet Information (IIS) según sea necesario.|  
|FFReceivePipeline.btp|El archivo de canalización de recepción de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] con el componente Desensamblador de archivo sin formato.|  
|FlatFileReceive.btproj, FlatFileReceive.sln|Archivos de proyectos y de soluciones de este ejemplo.|  
|FlatFileReceive_in.txt|Archivo de entrada de ejemplo.|  
|FlatFileReceiveBinding.xml|Se utiliza para la instalación automatizada, como el enlace de puerto.|  
|PO.xsd|Esquema del archivo sin formato entrante.|  
|Setup.bat|Se utiliza para crear e iniciar este ejemplo.|  
  
## <a name="how-to-use-this-sample"></a>Uso del ejemplo  
 Use este ejemplo como base para su propia solución de procesamiento de archivos sin formato. Puede ampliar muchos de los elementos de diseño usados en este ejemplo para cumplir sus propios requisitos.  
  
## <a name="building-and-initializing-this-sample"></a>Crear e inicializar este ejemplo  
  
1.  En una ventana de comandos, desplácese a la siguiente carpeta:  
  
     *\<Ejemplos de ruta de acceso\>*\Pipelines\AssemblerDisassembler\FlatFileReceive  
  
2.  Ejecute el archivo Setup.bat que realiza las acciones siguientes:  
  
    -   Crea la carpeta de entrada (FFInput) y la carpeta de salida (FFOutput) para este ejemplo en la carpeta:  
  
         *\<Ejemplos de ruta de acceso\>*\Pipelines\AssemblerDisassembler\FlatFileReceive  
  
    -   Compila e implementa el proyecto de Visual Studio para este ejemplo.  
  
    -   Crea y enlaza la ubicación de recepción de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y los puertos de envío y recepción.  
  
        > [!NOTE]
        >  Este ejemplo muestra la siguiente advertencia al crear y enlazar puertos: `Warning: Receive handler not specified for receive location "FlatFileReceive_RL"; updating with first receive handler with matching transport type.` puede omitir estas advertencias. (Para dar cabida a posibles diferencias de nombre en las instalaciones de usuario, se han omitido del archivo de enlace el nombre del host y el controlador de recepción).  
  
    -   Habilita la ubicación de recepción e inicia el puerto de envío.  
  
> [!NOTE]
>  Antes de intentar ejecutar este ejemplo, debe confirmar que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no ha informado de ningún error durante el proceso de generación e inicialización.  
  
> [!NOTE]
>  Si selecciona abrir y crear el proyecto de este ejemplo sin ejecutar Setup.bat, debe crear, en primer lugar, un par de claves de nombre seguro mediante la utilidad de nombre seguro de .NET Framework (sn.exe). Utilice este par de claves para firmar el ensamblado resultante.  
  
> [!NOTE]
>  Para deshacer los cambios realizados por Setup.bat, ejecute Cleanup.bat. Debe ejecutar Cleanup.bat antes de ejecutar Setup.bat por segunda vez.  
  
## <a name="running-this-sample"></a>Ejecución del ejemplo  
  
1.  Guarde una copia del archivo FlatFileReceive_in.xml en la carpeta FFInput.  
  
2.  Observe el archivo .xml creado en la carpeta FFOutput. El nombre del archivo de salida se basa en el GUID de Id. del mensaje. Este archivo contiene el equivalente XML del archivo sin formato situado en la carpeta de recepción.  
  
## <a name="classes-or-methods-used-in-this-sample"></a>Clases o métodos usados en el ejemplo  
 Las secuencias de comandos de configuración Setup.bat y Cleanup.bat se basan en las siguientes secuencias de comando administrativas del instrumental de administración de Windows (WMI):  
  
-   Iniciar puerto de envío\StartSendPort.vbs  
  
-   Habilitar ubicación de recepción\EnableRecLoc  
  
-   Quitar puerto de envío\RemoveSendPort  
  
 Los archivos por lotes de instalación y de limpieza usan BTSTask de la siguiente forma:  
  
-   **BTSTask ImportBindings** para aplicar el archivo de enlace y crear la aplicación, puertos y enlaces  
  
-   **BTSTask RemoveApp** para quitar flatfilereceiveapplication.  
  
## <a name="see-also"></a>Vea también  
-  [Pipelines\AssemblerDisassembler (carpeta de ejemplos de BizTalk Server)](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)   
-  [Desensamblador de archivos sin formato [componente de canalización]](../core/flat-file-disassembler-pipeline-component.md)   
-  [Esquemas de archivos sin formato](../core/flat-file-schemas.md)   
-  [Canalizaciones predeterminadas](../core/default-pipelines.md)   
-  **Ejemplos de scripts WMI**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]   
-  [Referencia de línea de comandos de BTSTask](../core/btstask-command-line-reference.md)   
-  [FlatFileSend (ejemplo de BizTalk Server)](../core/flatfilesend-biztalk-server-sample.md)