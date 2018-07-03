---
title: El descodificador AS2 no pudo procesar al validar el valor MIC devuelto en MDN | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3fe2d76d-b0f1-4118-8483-547c2c9fffb7
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2b15ec1518e4736052e31254283db66395d87fb6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985845"
---
# <a name="the-as2-decoder-failed-processing-when-validating-the-mic-value-returned-in-the-mdn"></a>Error de procesamiento de descodificador AS2 al validar el valor MIC devuelto en MDN
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                                                                                                       |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                          [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                           |
| Versión del producto |                                                                      [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                       |
|    Identificador del evento     |                                                                                                   -                                                                                                   |
|  Origen del evento   |                                                        EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                         |
|    Componente    |                                                                                              Motor AS2                                                                                               |
|  Nombre simbólico  |                                                                                AS2DecoderMdnMicFailureDuringProcessing                                                                                |
|  Texto del mensaje   | Error de procesamiento de descodificador AS2 al validar el valor MIC devuelto en MDN.  Detalles del mensaje MDN son los siguientes: AS2-de: "{0}" AS2-para: "{1}" MessageID: "{2}" OriginalMessageID: "{3}" |
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de recepción no pudo procesar el MDN entrante debido a que la comprobación de integridad del mensaje (MIC) no se pudo validar.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, compruebe que el algoritmo que se usa para la generación del MDN (en el encabezado Signed-Receipt-MICalg del mensaje original) es el mismo que el algoritmo especificado en la propiedad Signed-Receipt-MICalg para el receptor del mensaje AS2. Ambos deben ser SHA1 o MD5. Si el algoritmo especificado es el mismo, compruebe que el campo de extensión Received-Content-MIC en la segunda parte del mensaje MDN firmado con varias partes incluye una síntesis de MIC válida. Si es así, determine por qué el MDN no se corresponde con el intercambio que se ha enviado.