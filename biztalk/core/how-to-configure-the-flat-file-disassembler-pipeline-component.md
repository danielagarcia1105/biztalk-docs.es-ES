---
title: "Cómo configurar el componente de canalización de desensamblador de archivos sin formato | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Flat File Disassembler [pipeline component], configuring
- pipeline components, Flat File Disassembler
- messages, flat files
ms.assetid: c09996f6-6035-42a3-a75f-4def4ac39a95
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 403262bc18115923cdc5552a3b5e9e68d52f013e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-the-flat-file-disassembler-pipeline-component"></a>Cómo configurar el componente de canalización de desensamblador de archivos sin formato
El componente de canalización de desensamblador de archivo sin formato se utiliza para desensamblar documentos que tienen un formato de archivo sin formato y convertirlos en XML.  
  
### <a name="to-configure-the-properties-for-the-flat-file-disassembler-pipeline-component"></a>Para configurar las propiedades para el componente de canalización de desensamblador de archivo sin formato  
  
1.  Arrastre el componente de canalización de desensamblador de archivo sin formato en la fase de desensamblado de una canalización de recepción.  
  
2.  En la ventana Propiedades, en la **propiedades de componente de canalización** sección, realice lo siguiente.  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Esquema de documento**|Seleccionar el esquema de documento de archivo sin formato que se va a utilizar para analizar el mensaje del archivo sin formato a formato XML. El esquema de documento de archivo sin formato para realizar el análisis se puede crear en el Editor de BizTalk.<br /><br /> Valor predeterminado: Ninguno **Nota:** debe especificar un esquema para esta propiedad, o se producirá un error de tiempo de compilación.|  
    |**Esquema de encabezado**|Seleccionar un esquema para la parte del encabezado del mensaje de archivo sin formato. Este esquema se puede crear en el Editor de BizTalk.<br /><br /> Valor predeterminado: ninguno|  
    |**Conservar encabezado**|Establezca esta propiedad en **True** si necesita almacenar el encabezado del mensaje de archivo sin formato en el contexto del mensaje. Conservar el encabezado de un mensaje de archivo sin formato permite que la estructura del encabezado y el contenido se transmitan junto con el mensaje a través del servidor BizTalk Server. Ahora el encabezado se puede utilizar para serializar el mensaje de nuevo a un formato de archivo sin formato en el componente de canalización de ensamblador de archivo sin formato.<br /><br /> Cuando el ensamblador de archivo sin formato serialice el encabezado conservado, es probable que la propiedad Tiempo de diseño del documento de encabezado no disponga del nombre del esquema de encabezado porque esta información se puede obtener de forma dinámica en tiempo de ejecución. Esto se consigue al utilizar el tipo de mensaje del encabezado conservado.<br /><br /> Valor predeterminado: **False**|  
    |**Esquema de finalizador**|Seleccionar un esquema para la parte del finalizador del mensaje de archivo sin formato. El esquema para la parte del finalizador del mensaje de archivo sin formato se puede crear en el Editor de BizTalk.<br /><br /> Valor predeterminado: ninguno|  
    |**Procesamiento de intercambio recuperable**|Cuando es "false" indica que todo el intercambio está desensamblado como unidad (si falla cualquiera de los mensajes que contiene, se suspende todo el intercambio).<br /><br /> Cuando es "true" indica que el desensamblador extrae los mensajes que contiene el intercambio de forma individual con la posibilidad de que algunos se propaguen mediante la ruta de mensajería y otros se suspendan.<br /><br /> Para obtener más información sobre el procesamiento de intercambio recuperable, consulte [el procesamiento de intercambio recuperable](../core/recoverable-interchange-processing.md).|  
    |**Validar la estructura del documento**|Establezca esta propiedad en **True** si necesita validar todas las partes del mensaje de archivo sin formato (encabezado, cuerpo y finalizador) para asegurarse de que se ajusten a sus esquemas. Esta opción reduce el rendimiento del desensamblador de archivos sin, por lo que se establece en **False** de forma predeterminada.<br /><br /> Valor predeterminado: **False**|  
  
## <a name="see-also"></a>Vea también  
 [Componente de canalización de desensamblador de archivos sin formato](../core/flat-file-disassembler-pipeline-component.md)   
 [Configurar componentes de canalización nativos](../core/configuring-native-pipeline-components.md)   
 [Propiedades y esquema de propiedad de archivo sin formato y XML](../core/xml-and-flat-file-property-schema-and-properties.md)   
 [Las canalizaciones-AssemblerDisassembler (carpeta de ejemplos de BizTalk Server)](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)