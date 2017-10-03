---
title: "Componente de resolución de esquema (ejemplo de BizTalk Server) | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Flat File Disassembler [pipeline component], examples
- examples, schemas
- schemas, examples
- examples, Flat File Disassembler [pipeline component]
ms.assetid: 9ef68988-c4ee-42d5-83b5-a5c978b2007d
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 37ec562cbc64d15e66d2f265c52606817169bb85
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="schema-resolver-component-biztalk-server-sample"></a>Componente de resolución de esquema (ejemplo de BizTalk Server)
El ejemplo del componente de resolución de esquema muestra cómo extender la funcionalidad del componente de desensamblador de archivos sin formato de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
 El componente desensamblador de archivos sin formato normalmente requiere que se defina un esquema de análisis en tiempo de diseño. De modo que si espera recibir distintos documentos de archivos sin formato en la misma ubicación de recepción, incluiría varios desensambladores de archivos sin formato en la canalización de recepción, uno por cada esquema. En el tiempo de ejecución, el componente del desensamblador correcto se seleccione mediante un mecanismo de búsqueda de canalizaciones. Sin embargo, este enfoque resulta caro si tiene varios esquemas de archivos sin formato porque la búsqueda de cada componente de desensamblador correspondiente disminuye el rendimiento de la canalización.  
  
## <a name="what-this-sample-does"></a>Descripción del ejemplo  
 El componente de resolución de esquema muestra un método alternativo de seleccionar el esquema del componente de desensamblador de archivos sin formato. En este ejemplo, se definen cuatro esquemas y los dos primeros caracteres de un mensaje de cada esquema son únicos. Se define una asignación entre entre los dos primeros caracteres únicos y el esquema correspondiente. Cuando el mensaje de entrada se entrega al componente de resolución de esquema, lee los dos primeros caracteres, determina qué esquema debe utilizarse para el documento correspondiente, guarda la información del esquema en el contexto del mensaje y, a continuación, llama al componente desensamblador de archivos sin formato estándar. El componente desensamblador de archivos sin formato estándar lee la información del esquema desde el contexto del mensaje y utiliza ese esquema para analizar el documento.  
  
## <a name="where-to-find-this-sample"></a>Ubicación del ejemplo  
 *\<Ejemplos de ruta de acceso >*\Pipelines\SchemaResolverComponent\  
  
 En la siguiente tabla se incluyen los archivos usados en este ejemplo y se describe el propósito de cada uno de ellos.  
  
|Archivos|Description|  
|---------------|-----------------|  
|SchemaResolverSample.sln|Solución para el proyecto de BizTalk que ejercita el componente de canalización personalizado.|  
|SchemaResolverSample.btproj|El proyecto de BizTalk que ejercita el componente de canalización personalizado.|  
|SchemaResolverRP.btp|Canalización de recepción que contiene el componente personalizado.|  
|PurchaseOrder.xsd, PurchaseRequest.xsd, SalesOrder.xsd, SalesRequest.xsd|Esquemas de archivos sin formato.|  
|POInstance.txt, PRInstance.txt, SOInstance.txt, SRInstance.txt|Instancias de documentos de archivos sin formato correspondientes.|  
|SchemaResolverFlatFileDasm.sln|Solución para la implementación del componente de canalización.|  
|SchemaResolverFlatFileDasm.csproj|Proyecto C# para la implementación del componente de canalización.|  
|SchemaResolverFlatFileDasmComp.cs|Implementación del componente de canalización.|  
|SeekableReadOnlyStream.cs|Implementación de la secuencia de sólo lectura en la que se pueden efectuar búsquedas usada por el componente.|  
|VirtualStream.cs|Implementación de la secuencia virtual usada por el componente de canalización.|  
  
## <a name="building-and-initializing-this-sample"></a>Crear e inicializar este ejemplo  
 Utilice el siguiente procedimiento para crear e inicializar el ejemplo del componente de resolución de esquema.  
  
#### <a name="to-build-and-initialize-this-sample"></a>Para generar e inicializar el ejemplo  
  
1.  En una ventana de comandos, cambie el directorio (cd) a la siguiente carpeta:  
  
     *\<Ejemplos de ruta de acceso >*\Pipelines\SchemaResolverComponent  
  
2.  Ejecute el archivo Setup.bat que realiza las acciones siguientes:  
  
    -   Genera el componente.  
  
    -   Copia el ensamblado del componente en la carpeta BizTalk \Componentes de canalización.  
  
    -   Crea e implementa el proyecto de BizTalk de ejemplo.  
  
    -   Configura la ubicación de recepción y el puerto de envío, y los inicia.  
  
    > [!NOTE]
    >  Debe confirmar que no se ha informado de errores durante el proceso de creación e iniciación antes de intentar ejecutar este ejemplo.  
  
## <a name="running-this-sample"></a>Ejecución del ejemplo  
 Utilice el siguiente procedimiento para ejecutar el ejemplo del componente de resolución de esquema.  
  
#### <a name="to-run-this-sample"></a>Para ejecutar el ejemplo  
  
1.  Coloque los archivos archivos POInstance.txt, PRInstance.txt, SOInstance.txt y SRInstance.txt en la ubicación de recepción \< *ruta de acceso de instalación*> \SDK\Samples\Pipelines\SchemaResolverComponent\In  
  
2.  Observe los cuatro archivos .xml escritos en el \<Installdir > \SDK\Samples\Pipelines\SchemaResolverComponent\Out carpeta.  
  
## <a name="see-also"></a>Vea también  
 [Canalizaciones (carpeta de ejemplos de BizTalk Server)](../core/pipelines-biztalk-server-samples-folder.md)