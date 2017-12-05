---
title: Clase de ejemplo de error Extractor | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Error Extractor Sample class
- errors, Error Extractor Sample class
ms.assetid: d0d59b21-d80a-4466-a77a-1d3b7df1bc2a
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 53ceb305dcd30164e385022f66140fcaa626b133
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="error-extractor-sample-class"></a>Clase de ejemplo de error extractor de tablas
El [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] Desensamblador serializa errores a un objeto XML y los asocia el objeto XML a la sección de errores de un mensaje de varias partes. El desensamblador, a continuación, publica el mensaje con errores en la base de datos de cuadro de mensajes tal como haría con un mensaje válido. Por lo tanto, no se pudo detalles del error de transporte de mensajes en la base de datos de cuadro de mensajes. Puede usar la clase de ejemplo de Error extractor de tablas para extraer los detalles del error de un mensaje con errores y generar un archivo que tiene los detalles del error y otro archivo que tiene el mensaje original.  
  
> [!IMPORTANT]
>  La clase de ejemplo de Extractor de Error es el código de ejemplo en el SDK. No está pensado para su uso en producción.  
  
 Para utilizar la clase de ejemplo de Extractor de Error, debe crear una orquestación para procesar el mensaje error. Esta orquestación incluye los pasos para extraer el cuerpo del mensaje con errores, extraer la parte de error del mensaje con errores y, a continuación, escribir el cuerpo y el elemento de error para separar archivos XML. La orquestación representa cada uno de estos pasos en una fase de expresión que llama a uno o varios de los siguientes métodos de la clase de ejemplo de Extractor de Error:  
  
## <a name="getbodypartasstring-method"></a>GetBodyPartAsString (método)  
 Este método devuelve una cadena que contiene el XML que se encuentra en la parte del cuerpo del mensaje XLANG 'xm'. El método espera el mensaje XLANG 'xm' para que contenga una parte del cuerpo denominado "BodySegment." Por lo tanto, se debe declarar 'xm' en la orquestación de llamada con este nombre de parte del cuerpo. Si no existe como parte de "xm", "BodySegment" **GetBodyPartAsString** produce una excepción.  
  
```  
SWIFTErrorExtractor.ErrorExtractor.GetBodyPartAsString(XLANGMessage xm);  
```  
  
## <a name="geterrorpartasstring-method"></a>GetErrorPartAsString (método)  
 Este método devuelve una cadena que contiene el XML que se encuentra en la parte de error del mensaje XLANG 'xm'. El método espera el mensaje XLANG 'xm' para que contenga una parte de error denominado "ErrorSegment." Por lo tanto, se debe declarar 'xm' en la orquestación de llamada con este nombre de parte de error. Si no existe como parte de "xm", "ErrorSegment" **GetErrorPartAsString** produce una excepción.  
  
```  
SWIFTErrorExtractor.ErrorExtractor.GetErrorPartAsString(XLANGMessage xm);  
```  
  
## <a name="writetofile-method"></a>Método WriteToFile  
 Este método escribe la cadena de la *mensaje* parámetro para el archivo especificado por el *filePath* parámetro.  
  
```  
SWIFTErrorExtractor.ErrorExtractor.WriteToFile(string filePath, string message);  
```  
  
 El programa de instalación de A4SWIFT la clase de ejemplo de Extractor de Error (SWIFTErrorExtractor.dll) se instala como parte del SDK de A4SWIFT en \< *unidad*\>: \Program Acelerador de BizTalk para SWIFT\SDK\Tutorial\ SWIFTErrorExtractor. Esta carpeta también incluye el código fuente de la clase de ejemplo (ErrorExtractor.cs).  
  
 Para llamar a SWIFTErrorExtractor.dll desde la orquestación, debe publicar el archivo .dll en la caché global de ensamblados.  
  
## <a name="see-also"></a>Vea también  
 [Herramientas](../../adapters-and-accelerators/accelerator-swift/tools.md)