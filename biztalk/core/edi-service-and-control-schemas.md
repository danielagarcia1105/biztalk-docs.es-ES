---
title: Esquemas de Control y servicio EDI | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4866571b-b12d-446c-8d27-a72fe7e479ef
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 480a86ccb001ec31a12ca82588a4db61721e1145
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968325"
---
# <a name="edi-service-and-control-schemas"></a>Esquemas de control y servicio EDI
Los esquemas de control son necesarios para procesar sobres de mensaje (esquemas de control de encabezado) y confirmaciones. Estos esquemas se implementan en Microsoft.BizTalk.Edi.BaseArtifacts.dll a través del programa de instalación. Estos esquemas no tienen que agregarse a proyectos de BizTalk, ya que se implementan en BaseArtifacts.dll. Debe agregar una referencia al ensamblado BaseArtifacts.dll en el proyecto que contiene los esquemas para que éstos se usen.  

## <a name="envelope-service-schemas"></a>Esquemas de servicio de sobres  
 Los esquemas de servicio X12ServiceSchema y EdifactServiceSchema se usan para validar encabezados y finalizadores de conjuntos de transacciones, grupos e intercambios del sobre de un intercambio EDI. Esto es cierto para todos los intercambios EDI: un intercambio sin procesar por lotes, un intercambio por lotes que se va a dividir o un intercambio por lotes debe conservarse. Los espacios de nombres para estos esquemas son http://schemas.microsoft.com/Edi/X12ServiceSchema y http://schemas.microsoft.com/Edi/EdifactServiceSchema.  

 Si el intercambio EDI es un intercambio de lote conservado, los esquemas de lote X12_BatchSchema y Edifact_BatchSchema se usan por el tiempo de ejecución de BizTalk, junto con los esquemas de servicio. Para obtener más información, consulte [esquemas por lotes de EDI](../core/edi-batch-schemas.md).  

 Puede personalizar enumeraciones de campo de Id. en estos esquemas. No se permiten otras modificaciones. Para obtener más información, consulte [personalizar enumeraciones en el esquema de sobres](../core/customizing-enumerations-in-the-envelope-schema.md).  

## <a name="acknowledgment-control-schemas"></a>Esquemas de Control de confirmación  
 La canalización de recepción EDI usa esquemas de confirmación para generar confirmaciones que van a enviarse, y la canalización de envío EDI los usa para procesar confirmaciones recibidas. Estos esquemas incluyen el esquema de confirmación funcional 997 y el esquema de confirmación de intercambio TA1 para la codificación X12, y el esquema CONTRL para la codificación EDIFACT, según se muestra en la siguiente tabla. No puede modificar estos esquemas.  


|      CONFIRMACIÓN       |     Nombre de esquema      |             Espacio de nombres de destino             |                               Root                                |
|----------------|----------------------|------------------------------------------|-------------------------------------------------------------------|
|    TA1 de X12     |    X12_TA1Schema     |   http://schemas.microsoft.com/Edi/X12   |                   GENERACIÓN<br /><br /> X12_TA1_Root                    |
|    997 de X12     |    X12_997Schema     |   http://schemas.microsoft.com/Edi/X12   |            ST<br /><br /> SE<br /><br /> X12_997_Root             |
| CONTRL de EDIFACT | Edifact_ContrlSchema | http://schemas.microsoft.com/Edi/Edifact | Efact_Contrl_Root<br /><br /> UCD<br /><br /> UCM<br /><br /> UCS |

 Para la codificación X12, el esquema de confirmación funcional de 997 define los encabezados y finalizadores de mensaje, conjunto de transacciones, grupo e intercambio usados en el sobre de un mensaje, y los segmentos de AK1, AK2, AK3, AK4, AK5 y AK9 que notifican el resultado de la validación de cuerpo. El esquema de confirmación técnica TA1 define el encabezado y el finalizador de intercambio, y el segmento de confirmación TA1 que notifica el resultado de la validación del encabezado. Es de la convención de nomenclatura para estos esquemas X12_\<número de versión\>*997. xsd y X12\\*\<número de versión\>_TA1.xsd. El espacio de nombres de destino para estos esquemas http://schemas.microsoft.com/BizTalk/EDI/X12/2006.  

 EDIFACT admite un paradigma de confirmación en dos fases. La primera confirmación es una recepción de intercambio construida a través de tres segmentos desde el esquema CONTRL. Esta confirmación técnica notifica el resultado de la validación de encabezados. La segunda confirmación usa los segmentos restantes del esquema CONTRL. La convención de nomenclatura para este esquema es EFACT_\<número de versión\>_CONTRL.xsd. El espacio de nombres de destino para este esquema es http://schemas.microsoft.com/BizTalk/EDI/EDIFACT/2006.  

## <a name="see-also"></a>Vea también  
 [Cómo BizTalk Server recibe mensajes EDI](../core/how-biztalk-server-receives-edi-messages.md)   
 [Cómo envía BizTalk Server los mensajes EDI](../core/how-biztalk-server-sends-edi-messages.md)