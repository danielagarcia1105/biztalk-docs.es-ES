---
title: "Resolución de entidades personalizadas (ejemplo de BizTalk Server) | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- examples, parties
- pipeline components [custom], examples
- pipeline components [custom], parties
- examples, pipeline components [custom]
- parties, pipeline components [custom]
- parties, custom
ms.assetid: 1f88450f-5fe9-486d-bfb8-fd11181c78b4
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c7b88d8126a1d63760888edbcd7691ad4bd76426
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="custom-party-resolution-biztalk-server-sample"></a>Resolución de entidades personalizadas (ejemplo de BizTalk Server)
El ejemplo de resolución de entidades personalizadas muestra cómo escribir un componente de canalización personalizada para resolver una entidad personalizada.  
  
## <a name="what-this-sample-does"></a>Descripción del ejemplo  
 El ejemplo de resolución de entidades personalizadas acompaña la tarea mediante la siguiente secuencia de pasos:  
  
1.  Se recupera un documento XML de una carpeta.  
  
2.  La canalización resuelve la entidad.  
  
3.  El mensaje XML se escribe en una carpeta.  
  
## <a name="where-to-find-this-sample"></a>Ubicación del ejemplo  
 *\<Ejemplos de ruta de acceso >*\Pipelines\CustomPartyResolution\  
  
 En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.  
  
|Archivos|Description|  
|---------------|-----------------|  
|AssemblyInfo.cs|Archivo de origen de C# de información de ensamblado.|  
|Cleanup.bat|Archivo por lotes de limpieza.|  
|CustomPartyResolution.sln|Archivo de solución.|  
|CustomPartyResolutionBinding.xml|Archivo de enlace.|  
|CustomPartyResolutionPipeline.btp|Archivo de canalización.|  
|CustomPartyResolutionPipeline.btproj|Archivo de proyecto de canalizaciones.|  
|CustomPartyResolutionPipelineComponent.cs|Código de origen de C# de componente de canalización.|  
|CustomPartyResolutionPipelineComponent.csproj|Archivo de proyecto de Visual Studio de componente de canalización.|  
|InboundDocumentSchema.xsd|Esquema de documento de entrada.|  
|PartyResolutionStream.cs|Código de origen de C# de secuencia de resolución de entidad.|  
|RoutingPropertySchema.xsd|Archivo de esquema de propiedad de enrutamiento.|  
|SampleInboundDocumentSchema.xml|Archivo de esquema de documento de entrada.|  
|SampleInboundDocumentSchema_Party1.xml|Instancia de datos de ejemplo.|  
|SampleInboundDocumentSchema_Party2.xml|Instancia de datos de ejemplo.|  
|Setup.bat|Archivo por lotes de componente de canalización de ejemplo de configuración y de versión de compilación.|  
  
## <a name="building-and-initializing-this-sample"></a>Crear e inicializar este ejemplo  
  
#### <a name="to-build-and-initialize-the-custom-party-resolution-sample"></a>Para crear e iniciar el ejemplo de resolución de entidades personalizadas  
  
1.  En una ventana de comandos, cambie el directorio (**cd**) a la siguiente carpeta:  
  
     *\<Ejemplos de ruta de acceso >*\Pipelines\CustomPartyResolution\  
  
2.  Ejecute el archivo Setup.bat que realizará las acciones siguientes:  
  
    -   Crea los directorios de entrada y salida utilizados en el ejemplo.  
  
    -   Genera un archivo de clave nuevo.  
  
    -   Genera e implementa el componente de canalización de resolución de entidades personalizadas.  
  
    -   Copia el componente de canalización generado para el  *\<ruta de acceso de instalación >*directorio \Pipeline Components.  
  
    -   Crea los puertos de envío y recepción.  
  
> [!NOTE]
>  Debe confirmar que no se ha informado de errores durante el proceso de creación e iniciación antes de intentar ejecutar este ejemplo.  
  
## <a name="running-this-sample"></a>Ejecución del ejemplo  
  
#### <a name="to-run-the-custom-party-resolution-sample"></a>Para ejecutar el ejemplo de resolución de entidades personalizadas  
  
1.  Copie el archivo SampleInboundDocumentSchema_Party1.xml o SampleInboundDocumentSchema_Party2.xml en la carpeta \In.  
  
2.  Los resultados aparecerán en la carpeta \Out con el nombre de archivo *guid*.xml.  
  
## <a name="see-also"></a>Vea también  
 [Canalizaciones (carpeta de ejemplos de BizTalk Server)](../core/pipelines-biztalk-server-samples-folder.md)