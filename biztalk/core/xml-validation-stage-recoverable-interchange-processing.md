---
title: Fase de validación de XML (procesamiento de intercambio recuperable) | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1ed00971-d85b-4adb-86c4-c56de7ba7c67
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 273a556cd943d5404a4d5dfe38b1f31e29fd752b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012253"
---
# <a name="xml-validation-stage-recoverable-interchange-processing"></a>Fase de validación de XML (procesamiento de intercambio recuperable)
El **validador XML** componente de canalización procesa un intercambio en dos modos:  
  
-   **Modo estándar**. Cuando el **validador XML** componente está configurado para realizar una validación estándar, se validan los mensajes contenidos en un intercambio en una unidad transaccional de trabajo. Específicamente, si falla la validación de un mensaje del intercambio, todo el intercambio (que contiene todos los mensajes) se coloca en la cola de suspensión.  
  
-   **Modo recuperable**. Cuando el **validador XML** componente está configurado para realizar el procesamiento de intercambio recuperable, si se produce un error de validación de un mensaje, el mensaje se coloca en la cola de suspensión y la **validador de XML** componente continúa validando los mensajes restantes del intercambio.  
  
### <a name="to-configure-recoverable-interchange-processing"></a>Procedimiento para configurar el procesamiento de intercambio recuperable  
  
1. Abra una canalización de recepción mediante el diseñador de canalizaciones de Visual Studio.  
  
2. Arrastre **validador XML** componente desde el **cuadro de herramientas** a la **validar** fase de la canalización de recepción.  
  
3. En la ventana Propiedades, establezca el valor de la **procesamiento de intercambio recuperable** propiedad **True** si desea que el **validador XML** componente a los intercambios de proceso en el modo recuperable, o establezca la propiedad en **False** si desea que el componente para procesar los intercambios del modo estándar. El valor predeterminado de esta propiedad es `False`.  
  
   El **XMLValidator** clase en el modelo de objetos, que corresponde a la **validador XML** canalización componente, tiene una propiedad pública denominada **RecoverableInterchangeProcessing**que puede usar para obtener o establecer el modo mediante programación. Consulte la documentación de [Microsoft.BizTalk.Component.XmlValidator](http://msdn.microsoft.com/library/microsoft.biztalk.component.xmlvalidator.aspx) clase para obtener más información.  
  
   Los mensajes que se han validado correctamente tienen identificada su entidad de envío según la entidad configurada para el puerto de recepción al que llegó el intercambio primario. Si se genera un error en alguno de los mensajes extraídos del intercambio, se considera que la resolución de entidades ha dado error en todo el intercambio.  
  
## <a name="see-also"></a>Vea también  
 [Cómo configurar el componente de canalización de validador XML](../core/how-to-configure-the-xml-validator-pipeline-component.md)