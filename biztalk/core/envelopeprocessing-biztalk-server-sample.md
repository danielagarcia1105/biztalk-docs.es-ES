---
title: EnvelopeProcessing (ejemplo de BizTalk Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, envelopes
- flat files, processing
- examples, flat files
- examples, messages
- examples, envelopes
- envelopes, messages
- flat files, examples
- envelopes, examples
ms.assetid: b4cd979b-c7b4-446c-be29-c9f3169afa1f
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4206d46ec3a14d269f14d977133fb7211db694c6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994533"
---
# <a name="envelopeprocessing-biztalk-server-sample"></a>EnvelopeProcessing (ejemplo de BizTalk Server)
El ejemplo EnvelopeProcessing muestra cómo se procesan los mensajes y los sobres de mensaje en las canalizaciones de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Además, muestra cómo procesar mensajes de archivos sin formato en mensajes XML.  

## <a name="what-this-sample-does"></a>Descripción del ejemplo  
 Este ejemplo configura la carpeta EnvInput como ubicación de recepción. Cuando se coloca un archivo, como el archivo de ejemplo EnvelopeProcessing_in.txt, en esta carpeta, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] procesa los mensajes de este archivo siguiendo estos pasos:  

1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] recupera el archivo de mensajes de la carpeta de ubicación de recepción EnvInput.  

2. En la canalización de recepción, el componente de canalización Desensamblador de archivos sin formato quita el encabezado y el finalizador de los mensajes de archivos sin formato, y los analiza en mensajes individuales.  

3. En la base de datos de cuadro de mensajes, los mensajes se enrutan al puerto de envío mediante filtros de suscripción.  

4. En la canalización de envío del puerto de envío, el componente de canalización Ensamblador de XML incluye los sobres XML y después los incluye en la carpeta del adaptador de envío EnvOutput.  

## <a name="how-this-sample-is-designed-and-why"></a>Cómo se ha diseñado este ejemplo y por qué  
 El diseño de este ejemplo tenía que adaptarse a dos requisitos básicos:  

- Recibir y procesar un mensaje de archivo sin formato que contenga uno o varios pedidos.  

- Enviar un mensaje XML que contenga un pedido e información del remitente a un directorio para que un sistema de procesamiento de servidor lo recoja.  

  Para cumplir estos requisitos, se utilizó una combinación de esquemas de archivos sin formato y XML, así como canalizaciones personalizadas. Estos y otros elementos de diseño se resumen en la siguiente tabla.  

|Elemento de diseño|Razones seleccionadas|  
|--------------------|--------------------------|  
|Canalización de recepción personalizada|-Utiliza el Desensamblador de archivo sin formato y esquemas de archivo sin formato para traducir los mensajes de pedido de compra de entrada.|  
|Esquemas de archivos sin formato para el encabezado, el cuerpo y el finalizador del mensaje.|-Define todas las mismas características registros y campos (incluida la estructura) como esquemas XML y proporcionan un mecanismo para definir todas las características de archivo sin formato que se necesitan para traducir un mensaje de instancia de archivo sin formato en una instancia XML equivalente mensaje (o viceversa).<br />-Encabezado, cuerpo y finalizador esquemas se utilizan para dividir el cuerpo en fragmentos para su procesamiento.|  
|Esquema de sobre|: Se usa para envolver pedidos individuales con información del encabezado.|  
|Filtro de suscripción|-El filtro de suscripción realiza el enrutamiento real mediante la captura de mensajes que cumplen los criterios de uno o varios basados en campos de propiedades.|  
|Canalización de envío personalizada|: Usa el ensamblador de XML y una combinación de los esquemas de sobre y el cuerpo para traducir los mensajes de instancia en formato XML.|  

 Las siguientes consideraciones se aplican al diseño de este ejemplo.  

-   El esquema de archivo sin formato (PO.xsd) contiene anotaciones ampliadas que describen la estructura del archivo de pedido sin formato. Estos archivos se pueden crear manualmente, pero muchos pueden generarse mediante el asistente para archivos sin formato.  

-   El esquema de archivo sin formato del pedido (PO.xsd) usa un valor Unqualified para elementFormDefault. De este modo, se generan resultados correctos pero con calificaciones xmlns adicionales e inesperadas. Para evitar este problema, use un valor Qualified para elementFormDefault.  

-   Los esquemas de archivo sin formato de encabezado y finalizador se usan para separar los datos iniciales y finales del mensaje. Las propiedades del esquema de encabezado, el documento y el finalizador del desensamblador de archivos sin formato se establecen como el esquema de encabezado, pedido y finalizador, respectivamente.  

-   El esquema de sobre XML combina elementos del encabezado y del pedido para generar un único mensaje XML. El esquema de encabezado promociona el campo de origen en el campo SourceParty del **BTS.bts_system_properties** espacio de nombres; el esquema de sobre promociona el mismo valor, lo que hace que se puede degradar el mensaje saliente.  

## <a name="where-to-find-this-sample"></a>Ubicación del ejemplo  
 `<Samples Path>`\Pipelines\AssemblerDisassembler\EnvelopeProcessing\  

 En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.  


|                      Archivos                      |                                                                                               Descripción                                                                                               |
|---------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                    Cleanup.bat                    |    Se utiliza para anular la implementación de ensamblados y quitarlos de la caché de ensamblados global. Quita los puertos de envío y recepción. Quita los directorios virtuales de los Servicios de Microsoft Internet Information (IIS) según sea necesario.     |
| EnvelopeProcessing.btproj, EnvelopeProcessing.sln |                                                                               Archivos de proyectos y de soluciones de este ejemplo.                                                                               |
|             EnvelopeProcessing_in.txt             |                                                                                           Archivo de entrada de ejemplo.                                                                                            |
|          Header.xsd, PO.xsd, Trailer.xsd          |                                                                      Esquema para el encabezado, el cuerpo y el finalizador del archivo sin formato, respectivamente.                                                                      |
|                  XmlEnvelope.xsd                  |                                                                                    Esquema para el sobre XML saliente.                                                                                    |
|    EnvReceivePipeline.btp, EnvSendPipeline.btp    | Archivos de canalización de recepción y envío de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] con los componentes de canalización Desensamblador de archivos sin formato y Ensamblador XML, respectivamente. |
|           EnvelopeProcessingBinding.xml           |                                                                             Se usa para la instalación automatizada, como el enlace de puerto.                                                                              |
|                     Setup.bat                     |                                                                                Se utiliza para crear e iniciar este ejemplo.                                                                                |

## <a name="how-to-use-this-sample"></a>Uso del ejemplo  
 Use este ejemplo como base para su propia solución de procesamiento de archivos sin formato. Puede ampliar muchos de los elementos de diseño usados en este ejemplo para cumplir sus propios requisitos. Algunos ejemplos son los siguientes:  

-   Mejore el ejemplo para escribir una versión del archivo sin formato de cada pedido, además de la versión XML. Para ello, cree una nueva canalización de envío personalizada y use el Ensamblador de archivos sin formato. En éste, especifique los esquemas de encabezado, pedido y finalizador de archivos sin formato. Si se usa en un puerto de envío, genera pedidos individuales con la información de encabezado y finalizador.  

-   Mejore el sobre con más información procedente del pedido. Para escribir información adicional en el mensaje de salida, promocione el nombre de envío u otros campos mediante Promoción rápida, agregue campos al sobre y, a continuación, promocione los campos del sobre al mismo campo. Cuando se procesa el mensaje a través del ensamblador, las propiedades promocionadas se degradan y copian en el mensaje de salida.  

## <a name="building-and-initializing-this-sample"></a>Crear e inicializar este ejemplo  

#### <a name="to-build-and-initialize-the-envelopeprocessing-sample"></a>Para crear e inicializar el ejemplo EnvelopeProcessing  

1. En una ventana de comandos, desplácese a la siguiente carpeta:  

    *\<Ejemplos de la ruta de acceso\>* \Pipelines\AssemblerDisassembler\EnvelopeProcessing  

2. Ejecute el archivo Setup.bat que realiza las acciones siguientes:  

   - Crea la carpeta de entrada (EnvInput) y la carpeta de salida (EnvOutput) para este ejemplo en la carpeta:  

      *\<Ejemplos de la ruta de acceso\>* \Pipelines\AssemblerDisassembler\EnvelopeProcessing\  

   - Compila e implementa el proyecto de Visual Studio para este ejemplo.  

   - Crea y enlaza la ubicación de recepción de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y los puertos de envío y recepción.  

      Este ejemplo muestra las siguientes advertencias al crear y enlazar puertos:  

     ```  
     Warning: Receive handler not specified for receive location "EnvelopeProcessing_RL"; updating with first receive handler with matching transport type.  
     Warning: Host not specified for orchestration "EnvelopeProcessing"; updating with first available host.  
     ```  

      Puede omitir estas advertencias de forma segura. (Para dar cabida a posibles diferencias de nombre en las instalaciones de usuario, se han omitido del archivo de enlace el nombre del host y el controlador de recepción).  

   - Habilita la ubicación de recepción e inicia el puerto de envío.  

> [!NOTE]
>  Antes de intentar ejecutar este ejemplo, debe confirmar que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no ha informado de ningún error durante el proceso de generación e inicialización.  
> 
> [!NOTE]
>  Si selecciona abrir y crear el proyecto de este ejemplo sin ejecutar Setup.bat, debe crear, en primer lugar, un par de claves de nombre seguro mediante la utilidad de nombre seguro de .NET Framework (sn.exe). Utilice este par de claves para firmar el ensamblado resultante.  
> 
> [!NOTE]
>  Para deshacer los cambios realizados por Setup.bat, ejecute Cleanup.bat. Debe ejecutar Cleanup.bat antes de ejecutar Setup.bat por segunda vez.  

## <a name="running-this-sample"></a>Ejecución del ejemplo  

#### <a name="to-run-the-envelopeprocessing-sample"></a>Para ejecutar el ejemplo EnvelopeProcessing  

1.  Ponga una copia del archivo EnvelopeProcessing_in.txt en la carpeta EnvInput.  

2.  Observe los tres archivos .xml creados en la carpeta EnvOutput. Los nombres de estos archivos .xml se basan en los GUID de Id. de mensaje. Contienen los mensajes extraídos del archivo de entrada e incluidos en sobres.  

## <a name="classes-or-methods-used-in-this-sample"></a>Clases o métodos usados en el ejemplo  
 Las secuencias de comandos de configuración Setup.bat y Cleanup.bat se basan en las siguientes secuencias de comando administrativas del instrumental de administración de Windows (WMI):  

- Iniciar puerto de envío\StartSendPort.vbs  

- Habilitar ubicación de recepción\EnableRecLoc  

- Quitar puerto de envío\RemoveSendPort  

  Los archivos por lotes de instalación y de limpieza usan BTSTask de la siguiente forma:  

- **BTSTask ImportBindings** para aplicar el archivo de enlace y crear la aplicación, puertos y enlaces  

- **BTSTask RemoveApp** para quitar flatfilereceiveapplication.  

## <a name="see-also"></a>Vea también  
 [Pipelines\AssemblerDisassembler (carpeta de ejemplos de BizTalk Server)](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)