---
title: Herramientas de canalización | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline tools, XMLAsm.exe
- pipeline tools, FFDasm.exe
- Pipeline.exe
- FFDasm.exe
- pipeline tools, XMLDasm.exe
- pipeline tools
- XMLAsm.exe
- pipeline tools, DSDump.exe
- FFAsm.exe
- pipeline tools, FFAsm.exe
- pipeline tools, how to
- pipeline tools, about pipeline tools
- pipeline tools, Pipeline.exe
- utilities, pipeline tools
- XMLDasm.exe
ms.assetid: ca4d053a-1473-4d40-8cd0-1ed3a3af988a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9c53791906e64930b39b15a89ca20bc269dc8cd9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37017049"
---
# <a name="pipeline-tools"></a>Herramientas de canalización
Las herramientas de canalización proporcionadas con el kit de desarrollo de software (SDK) de Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] permiten comprobar que una canalización está funcionando correctamente sin tener que configurar el entorno de BizTalk Server, por ejemplo, los puertos de recepción y envío. Además, puede usar las herramientas de canalización para:  

-   Depurar los componentes de canalización de terceros fuera del entorno de servidor.  

-   Diagnosticar mensajes de error del motor de análisis.  

-   Experimentar con distintos esquemas sin la carga de compilación, implementación, anulación de la implementación y nueva compilación.  

-   Explorar archivo sin formato y comportamiento de ensamblador y desensamblador XML.  

-   Ver salida de desensamblador y descubrir las propiedades de contexto de mensaje que se promocionan, así como sus valores.  

-   Ejecutar canalizaciones de envío y recepción sin componentes de desensamblador y de ensamblador (por ejemplo, puede ver la salida del decodificador de S/MIME).  

-   Realizar mediciones de rendimiento precisas solo del componente (en lugar del subsistema de mensajería completo).  

## <a name="location-in-sdk"></a>Ubicación en SDK  
 \<*Ruta de instalación*\>\SDK\Utilities\PipelineTools  

 Use herramientas de canalización para ejecutar, depurar y generar perfiles de canalizaciones, además de componentes de canalización (es decir, archivo sin formato y componentes de ensamblador y desensamblador XML).  

## <a name="file-inventory"></a>Inventario de archivos  
 En la siguiente tabla se enumeran los archivos de herramientas de canalización y se describe el propósito de cada uno.  


|   Archivos    |                                                                                                                                                                                                                                Descripción                                                                                                                                                                                                                                 |
|--------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  DSDump.exe  |                                                Permite volcar la estructura de esquemas de documento, que es una representación ligera en memoria de uno o varios esquemas XSD, con o sin anotaciones de archivo sin formato. Esta herramienta puede resultar útil al obtener errores del motor de análisis, por ejemplo, $Root$0$3$2 y cuando sea necesario descodificarlos. Los números detrás de $ quieren decir índices o registros de base 0 cuando aparecen en el esquema de documentos.                                                |
|  FFAsm.exe   |                                                                                                                                     Ejecuta el componente de ensamblador de archivos sin formato, invocándolo directamente mediante la emulación de un componente de canalización que permite ver cómo serializa o ensambla documentos de XML de usuarios en un documento de archivo sin formato.                                                                                                                                      |
|  FFDasm.exe  |                                                                                                                               Ejecuta el componente de desensamblador de archivo sin formato, invocándolo directamente mediante la emulación de un componente de canalización de recepción que permite ver cómo analiza o desensambla un documento de archivo sin formato de usuario en uno o varios documentos XML.                                                                                                                               |
| Pipeline.exe | Ejecuta una canalización de envío o de recepción; acepta uno o varios documentos de entrada y sus partes, esquemas XSD e información relacionada y produce un documento de salida una vez que se ejecute la canalización. Pipeline.exe no tiene acceso a las bases de datos de BizTalk Server, por lo que las canalizaciones que contienen los componentes de ensamblador y desensamblador de BizTalk Framework que tienen acceso a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos durante la ejecución pueden no ser compatible. |
|  XMLAsm.exe  |                                                                                                                                 Ejecuta el componente de ensamblador XML, invocándolo directamente mediante la emulación de una canalización de envío que permite ver cómo serializa, ensambla o protegen con doble cifrado documentos XML de usuario en un documento XML de salida.                                                                                                                                  |
| XMLDasm.exe  |                                                                                                                             Ejecuta el componente de desensamblador XML, invocándolo directamente mediante la emulación de una canalización de recepción que permite ver cómo analizar, desensamblar o desproteger un documento XML de usuario con doble cifrado en uno o varios documentos XML.                                                                                                                              |

## <a name="usage"></a>Uso  
 En las secciones que se muestran a continuación se proporciona una descripción más detallada de cada uno de los archivos.  

### <a name="dsdumpexe"></a>DSDump.exe  
 DSDump.exe permite volcar la estructura de esquemas de documento, que es una representación ligera en memoria de uno o varios esquemas XSD, con o sin anotaciones de archivo sin formato.  

 DSDump.exe (herramienta de volcado de esquemas de documentos) es compatible con el siguiente parámetro de línea de comandos:  

```  
DSDump.exe schemaFileName  
```  

 En caso de que se realice de forma correcta, DSDump imprime el esquema de documentos en la consola.  

### <a name="ffasmexe"></a>FFAsm.exe  
 FFAsm.exe (ensamblador de archivo sin formato) es compatible con los siguientes parámetros de línea de comandos:  

```  
usage: ffasm document... [-dm documentMask...]-bs bodySchema [ -hs headerSchema ] [ -ts trailerSchema ] [ -c ] [ -d ] [ -sb ] [ -m filenamemask ] [ -en encoding ] [ -v ]  

where:  
  document           XML document(s)  
  documentMask       XML document(s) file mask, e.g., c:\\documents\\*.xml  
  bodySchema         Flat File body schema  
  headerSchema       Flat File header schema  
  trailerSchema      Flat File trailer schema  
  -c                 Display assembled FF message on the console  
  -d                 Demote properties  
  -sb                Set body schema(s) as design-time property  
  -m                 Output file name mask (default is %MessageID%)  
  encoding           Output message encoding name (e.g. windows-1252) or   
                         code page (e.g. 936)  
  -v                 Verbose mode  

file name macros:  
  %MessageID%        FF message identifier (Guid)  
  %MessagePartID%    FF message part identifier (Guid)  

```  

 Por ejemplo, si desea ensamblar tres documentos XML de entrada en un único documento de archivo sin formato con una degradación de encabezado y de propiedad, use el siguiente comando:  

```  
FFAsm.exe file_in1.xml file_in2.xml file_in3.xml –hs myHeaderSchema.xsd –bs myBodySchema.xsd -d  
```  

### <a name="ffdasmexe"></a>FFDasm.exe  
 FFDasm.exe (desensamblador de archivos sin formato) es compatible con los siguientes parámetros de línea de comandos:  

```  
usage: ffdasm document -bs bodySchema [ -hs headerSchema ] [ -ts trailerSchema ] [ -s ] [ -c ] [ -p ] [ -m filenamemask ] [ -en encoding ] [ -v ]  

where:  
  document           Flat File document  
  bodySchema         Flat File body schema  
  headerSchema       Flat File header schema  
  trailerSchema      Flat File trailer schema  
  -s                 Validate document structure  
  -c                 Display disassembled XML message on the console  
  -p                 Display promoted properties on the console  
  encoding           Input message body part encoding name (e.g. windows-1252) or code page (e.g., 396)  
  -m                 Output file name mask (default is %MessageID%)  
  -v                 Verbous mode  

file name macros:  
  %MessageID%        XML message identifier (Guid)  
  %MessagePartID%    XML message part identifier (Guid)  

```  

 Por ejemplo, si desea desensamblar un documento de archivo sin formato que tiene un encabezado, cuerpo y finalizador, y se muestran los resultados en la consola, use el siguiente comando:  

```  
FFDasm.exe file_in.txt –hs myHeaderSchema.xsd –bs myBodySchema.xsd –ts myTrailerSchema.xsd –c  
```  

### <a name="pipelineexe"></a>Pipeline.exe  
 Pipeline.exe (herramienta de canalización) es compatible con los siguientes parámetros de línea de comandos:  

```  
usage: pipeline ( pipeline[.btp] | -pt pipelineTypeName [ -an assemblyName ] ) -d document... [ -part part... ] [ -s schema[.xsd][:namespace.type]... ] [ -proj project[.btproj] ] [ -p ] [ -c ] [ -t ] [ -m filenamemask ] [ -pm partfilenamemask ] [ -en encoding ] [ -v ]  

where:  
  pipeline                Pipeline file name  
  pipelineTypeName     Compiled pipeline assembly qualified type name (e.g.   
"MyPipelines.ReceivePipeline, MyPipelines,   
Version=1.0.0.0, Culture=neutral,   
PublicKeyToken=e03965cb5971ad66" or full name (e.g.   
"MyPipelines.ReceivePipeline") if assembly name is   
specified  
  assemblyName         Compiled pipeline assembly file name (e.g.   
MyPipelines.dll) or name (e.g. "MyPipelines,   
Version=1.0.0.0, Culture=neutral,   
PublicKeyToken=e03965cb5971ad66")  
  document             Input document(s)  
  part                 Input document's part  
  schema               Schema file name  
  namespace            Schema namespace (as in BizTalk project system)  
  type                 Schema type (as in BizTalk project system)  
  project              BizTalk project file  
  -p                   Display promoted context properties for receive and   
send pipelines, and promote context properties for   
send pipelines  
  -c                      Display output document on the console  
  -t                      Display elapsed time of components execution  
  filenamemask         Output message file name mask (default is   
Message_%MessageID%.out)  
  partfilenamemask     Output part file name mask (default is   
Part_%MessagePartID%.out)  
  encoding             Output message encoding name (e.g. windows-1252)   
or code page (e.g. 936)  
  -v                   Verbous mode  

note:  
You can specify namespace and type for schemas either using namespace.type notation in schema file reference or by using BizTalk project file.  

file name macros:  
  %MessageID%           Message identifier (Guid)  
  %MessagePartID%       Message part identifier (Guid)  
  %MessageNumber%       Message number  

```  

 Por ejemplo, si desea ejecutar una canalización de recepción desde el archivo ReceivePipeline.btp (que tiene componentes de desensamblador XML y de validador de XML) mediante mySchema.xsd y mostrar los resultados en la consola, use el siguiente comando:  

```  
Pipeline.exe ReceivePipeline.btp –d file_in.xml –s MySchema.xsd:MyProject.MySchema -c  

```  

 \- O bien  

```  
Pipeline.exe ReceivePipeline.btp –d file_in.xml –s MySchema.xsd –proj MyProject.btproj -c  

```  

 En el primer ejemplo, un nombre de tipo completo (**MyProject.MySchema**) para el esquema se incluye como un argumento de línea de comandos. En el segundo ejemplo, el esquema se obtiene del archivo de proyecto de BizTalk especificado.  

 También puede ejecutar canalizaciones de compilado [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] archivos de proyecto, como se muestra en el ejemplo siguiente (la canalización se hace referencia por su nombre de tipo calificado con el ensamblado):  

```  
Pipeline.exe -pt "TestBtsProject.ReceivePipeline, TestBtsProject, Version=1.0.0.0, Culture=neutral, PublicKeyToken=e03965cb5971ad66" -d in.xml -s PO.xsd -proj TestBtsProject.btproj –c  
```  

 En el siguiente ejemplo, se hace referencia por separado a una canalización mediante el nombre de tipo y el nombre de archivo de ensamblado:  

```  
Pipeline.exe -pt TestBtsProject.ReceivePipeline –an TestBtsProject.dll -d in.xml -s PO.xsd -proj TestBtsProject.btproj –c   
```  

 En el siguiente ejemplo se muestra una canalización a la que se hace referencia mediante el nombre de ensamblado:  

```  
Pipeline.exe -pt TestBtsProject.ReceivePipeline –an "TestBtsProject, Version=1.0.0.0, Culture=neutral, PublicKeyToken=e03965cb5971ad66" -d in.xml -s PO.xsd -proj TestBtsProject.btproj –c  
```  

 Pipeline.exe se ejecuta con cualquiera de las credenciales usadas para iniciarlo. No utiliza la cuenta es normal [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ejecutarán las instancias de host, por lo que no podrá ejecutar canalizaciones que contienen componentes que requieren acceso de la base de datos. Asegúrese de que ejecuta Pipeline.exe en una cuenta que dispone de todos los privilegios necesarios.  

 Solo debe usar Pipeline.exe para comprobar las canalizaciones personalizadas sin componentes personalizados de terceros. Si usa pipeline.exe para comprobar una canalización personalizada con componentes personalizados de terceros, Pipeline.exe producirá el resultado deseado. Sin embargo, si implementa la misma canalización personalizada con componentes personalizados de terceros, use la canalización en un puerto de envío o de recepción y, a continuación, usa Pipeline.exe para enviar un mensaje a la canalización, la canalización producirá errores y el servidor BizTalk Server devolverá un error.  

### <a name="xmlasmexe"></a>XMLAsm.exe  
 XMLAsm.exe (herramienta de ensamblador XML) es compatible con los siguientes parámetros de línea de comandos:  

```  
usage: xmlasm document...[-dm documentmask...] -ds documentSchema... [ -es envelopeSchema... ] [ -c ] [ -d ] [ -sd ] [ -m filenamemask ] [ -v ]  

where:  
  document           XML document(s)  
  documentMask       XML document(s) file mask, e.g., c:\\documents\\*.xml  
  documentSchema     XML document schema(s)  
  envelopeSchema     XML envelope schema(s)  
  -c                 Display assembled XML message on the console  
  -d                 Demote properties  
  -sd                Set document schema(s) as design-time property  
  -d                 Demote properties  
  -m                 Output file name mask (default is %MessageID%)  
  -v                 Verbous mode  

file name macros:  
  %MessageID%        XML message identifier (Guid)  
  %MessagePartID%    XML message part identifier (Guid)  

```  

 Por ejemplo, si desea ensamblar dos documentos XML de entrada en un único documento XML con un sobre y mostrar los resultados en la consola, use el siguiente comando:  

```  
FFAsm.exe file_in1.xml file_in2.xml–es myEnvelopeSchema.xsd –ds myBodySchema.xsd –c  
```  

### <a name="xmldasmexe"></a>XMLDasm.exe  
 XMLDasm.exe es compatible con los siguientes parámetros de línea de comandos:  

```  
usage: xmldasm document -ds documentSchema... [ -es envelopeSchema... ] [ -s ] [ -c ] [ -p ] [ -sd ] [ -se ] [ -m filenamemask ] [ -en encoding ] [ -v ]  

where:  
  document           XML document  
  documentSchema     XML document schema(s)  
  envelopeSchema     XML envelope schema(s)  
  -s                 Validate document structure  
  -c                 Display disassembled XML message on the console  
  -p                 Display promoted properties on the console  
  -sd                Set document schema(s) as design-time property  
  -se                Set envelope schema(s) as design-time property  
  -m                 Output file name mask (default is %MessageID%)  
  encoding           Input message body part encoding name (e.g., windows-1252) or code page (e.g., 936)  
  -v                 Verbous mode  

file name macros:  
  %MessageID%        XML message identifier (Guid)  
  %MessagePartID%    XML message part identifier (Guid)  
  %MessageNumber%    XML message number  

```  

 Por ejemplo, si desea desensamblar un documento XML con dos sobres anidados y mostrar los resultados en la consola, use el siguiente comando:  

```  
XmlDasm.exe file_in.txt –ds myDocumentSchema.xsd –es myEnvelopeSchema1.xsd –es myEnvelopeSchema2.xsd –c  
```  

## <a name="see-also"></a>Vea también  
 [Utilidades del SDK](../core/utilities-in-the-sdk.md)