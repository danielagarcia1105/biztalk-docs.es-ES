---
title: Delimitadores de mensaje | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, events
- messages, XML messages
- events
- delimiters
- messages, delimiters
- flat files
- XML messages
- messages, flat files
ms.assetid: d25bf6db-5512-4c82-be0e-00da024c55d1
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3339ded8edf46f7c5b96317cdf7a3ec822ec808b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001501"
---
# <a name="message-delimiters"></a>Delimitadores de mensaje
Eventos de mensaje definidos por los estándares de HL7 adoptan la forma siguiente:  
  
- **Archivos planos**. Eventos de mensaje definidos por las versiones de HL7 2.4 y anteriores adoptan la forma de archivos planos.  
  
- **XML**. Eventos de mensaje definidos por las versiones de HL7 2.xml XML y la versión 3 adoptan la forma de archivos XML.  
  
  Puesto que el estándar HL7 no sigue el formato posicional, usa los delimitadores para definir el segmento, campo, componente y niveles de subcomponentes de archivos planos. En la tabla siguiente se enumera los delimitadores predeterminados utilizados por los archivos sin formato de HL7.  
  
|Delimitador|Valor|Uso|  
|---------------|-----------|-----------|  
|Terminador de segmento|\<CR\>|Un retorno de carro finaliza un registro de segmento. No se puede cambiar este valor.|  
|Separador de campos|&#124;|Un carácter de barra vertical separa dos campos de datos adyacentes en un segmento. Este carácter separa también el identificador de segmento del primer campo de datos en cada segmento.|  
|Separador de componentes|^|Un carácter de hat separa los componentes adyacentes de datos de los campos donde lo permite el estándar HL7.|  
|Separador de subcomponente|&|Un carácter de y comercial separa adyacentes subcomponentes de datos de los campos donde lo permite el estándar HL7. Si no hay ningún subcomponentes, a continuación, puede omitir este carácter.|  
|Separador de repeticiones|~|Un carácter de tilde separa varias repeticiones de componentes o subcomponentes en un campo donde lo permite el estándar HL7.|  
|Carácter de escape|\|Utilice un carácter de escape con cualquier campo que se ajusta a un tipo de datos ST, TX o FT, o con el componente de tipo de datos de ED (cuarto) de datos. Si no existe ningún carácter de escape en un mensaje, puede omitir este carácter. Sin embargo, se debe incluir si usas subcomponentes en el mensaje.|  
  
## <a name="see-also"></a>Vea también  
 [Procesamiento de mensajes de HL7](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md)   
 [Procesamiento de mensajes](../../adapters-and-accelerators/accelerator-hl7/message-processing.md)   
 [Uso de esquemas HL7 2.X](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)