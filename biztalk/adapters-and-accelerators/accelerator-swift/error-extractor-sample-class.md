---
title: Clase de ejemplo de Extractor de error | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Error Extractor Sample class
- errors, Error Extractor Sample class
ms.assetid: d0d59b21-d80a-4466-a77a-1d3b7df1bc2a
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1085af05221b252bb6942e2c32bbe1f91c8d7688
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010773"
---
# <a name="error-extractor-sample-class"></a>Clase de ejemplo de Extractor de error
Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] Desensamblador errores a un objeto XML se serializa y se adjunta el objeto XML a la sección de errores de un mensaje de varias partes. El desensamblador, a continuación, publica el mensaje con errores en la base de datos de cuadro de mensajes tal como lo haría con un mensaje válido. Por lo tanto, no se pudo detalles del error de transporte de mensajes en la base de datos de cuadro de mensajes. Puede usar la clase de ejemplo de Extractor de Error para extraer los detalles del error de un mensaje con errores y generar un archivo que tiene los detalles del error y otro que tiene el mensaje original.  
  
> [!IMPORTANT]
>  La clase de ejemplo de Extractor de Error es el código de ejemplo en el SDK. No está pensado para su uso en producción.  
  
 Para usar la clase de ejemplo de Extractor de Error, debe crear una orquestación para procesar el mensaje con errores. Esta orquestación incluye pasos para extraer el cuerpo del mensaje con errores, extraer la parte de error del mensaje con errores y, a continuación, escribir el cuerpo y el elemento de error en los archivos XML independientes. La orquestación representa cada uno de estos pasos en una fase de la expresión que se llama a uno o varios de los siguientes métodos de la clase de ejemplo de Extractor de Error:  
  
## <a name="getbodypartasstring-method"></a>Método GetBodyPartAsString  
 Este método devuelve una cadena que contiene el XML que se encuentra en la parte del cuerpo del mensaje XLANG 'xm'. El método espera el mensaje XLANG 'xm' para que contenga una parte del cuerpo denominada "BodySegment". Por lo tanto, debe declarar 'xm' en la orquestación de llamada con este nombre de parte del cuerpo. Si no existe como parte de "xm", "BodySegment" **GetBodyPartAsString** produce una excepción.  
  
```  
SWIFTErrorExtractor.ErrorExtractor.GetBodyPartAsString(XLANGMessage xm);  
```  
  
## <a name="geterrorpartasstring-method"></a>Método GetErrorPartAsString  
 Este método devuelve una cadena que contiene el XML se encuentra en la parte de error del mensaje XLANG 'xm'. El método espera el mensaje XLANG 'xm' para que contenga una parte de error denominado "ErrorSegment." Por lo tanto, debe declarar 'xm' en la orquestación de llamada con este nombre de parte del error. Si no existe como parte de "xm", "ErrorSegment" **GetErrorPartAsString** produce una excepción.  
  
```  
SWIFTErrorExtractor.ErrorExtractor.GetErrorPartAsString(XLANGMessage xm);  
```  
  
## <a name="writetofile-method"></a>Método WriteToFile  
 Este método escribe la cadena desde el *mensaje* parámetro en el archivo especificado por el *filePath* parámetro.  
  
```  
SWIFTErrorExtractor.ErrorExtractor.WriteToFile(string filePath, string message);  
```  
  
 El programa de instalación de A4SWIFT la clase de ejemplo de Extractor de Error (SWIFTErrorExtractor.dll) se instala como parte del SDK de A4SWIFT en \< *unidad*\>: Acelerador de BizTalk para SWIFT\SDK\Tutorial\ \Program Files\Microsoft SWIFTErrorExtractor. Esta carpeta también incluye el código fuente de la clase de ejemplo (ErrorExtractor.cs).  
  
 Para llamar a SWIFTErrorExtractor.dll desde la orquestación, debe publicar el archivo .dll en la caché global de ensamblados.  
  
## <a name="see-also"></a>Vea también  
 [Herramientas](../../adapters-and-accelerators/accelerator-swift/tools.md)