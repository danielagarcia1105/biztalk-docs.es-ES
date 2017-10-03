---
title: "Cómo usar puertos de enlace directo autocorrelación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: feb651fa-3e35-4598-b229-335448f6919c
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b866d1042aed8abbb6441822e6bc7eda62254881
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-use-self-correlating-direct-bound-ports"></a>Cómo usar puertos de enlace directo de autocorrelación
Los puertos de enlace directo de autocorrelación hacen referencia a sí mismos. Esto significa que un puerto de enlace directo de autocorrelación suministra la información que puede utilizar una orquestación para devolver mensajes a su orquestación envolvente. Al utilizar el enlace directo de autocorrelación, el motor de orquestaciones generará un token de correlación en los mensajes que sean específicos de la instancia de orquestación. Esto ofrece la capacidad de devolver los mensajes a una instancia de orquestación específica sin usar un conjunto de correlaciones.  
  
 Por ejemplo, puede crear una recepción de autocorrelación puerto de enlace directo de orquestación mediante la especificación de **directa** para **enlace de puerto** y seleccionando **Autocorrelancionándose**en el Asistente para configuración de puertos. A continuación, en la orquestación B, declara un puerto como parámetro de orquestación de puerto de envío del mismo tipo de puerto que se ha definido en la orquestación A. Para ello, haga lo siguiente:  
  
1.  En la ventana Vista orquestación, haga clic en **parámetros de orquestación**y, a continuación, haga clic en **nuevo parámetro de puerto**.  
  
2.  En la ventana Propiedades, para **dirección de comunicación**, seleccione **enviar**y para **tipo de puerto**, seleccione el mismo tipo de puerto tal como se define en la orquestación A.  
  
 Esta declaración crea un puerto de envío lógico en la Superficie para el puerto del Diseñador de orquestaciones. Llama a orquestación A orquestación B utilizando el **Iniciar orquestación** forma y pasa el nuevo puerto como un parámetro, junto con los parámetros de orquestación, a la orquestación B. orquestación B, a continuación, realiza su lógica de negocios y envía un mensaje en el nuevo puerto que se pasó a él. El mensaje se envía al puerto de enlace directo de autocorrelación de recepción de la instancia de la orquestación A que inició la orquestación B.  
  
 Aunque la anterior secuencia de eventos también puede realizarse con un **orquestación de llamada** forma, solo tiene sentido cuando se usa un **Iniciar orquestación** forma. Esto es porque cuando se usa un **orquestación de llamada** forma, los puertos se pasan por referencia. La polaridad del puerto debe ser igual en ambas orquestaciones. Por lo tanto, la dirección de comunicación del puerto que pase desde una orquestación debe ser la misma que la dirección de la referencia de puerto en la orquestación a la que se llama. Sin embargo, cuando se usa el **Iniciar orquestación** forma, se genera una instancia asíncrona de una orquestación y no puede tener **Out** o **Ref** parámetros; por lo tanto, el puerto de enlace directo de autocorrelación proporciona una forma de una orquestación responder a la instancia de orquestación que creó la instancia.  
  
 Para obtener un ejemplo de cómo usar puertos de enlace directo de autocorrelación, consulte el ejemplo SDK "Implementing Scatter and Gather Pattern" en [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).  
  
## <a name="see-also"></a>Vea también  
 [Cómo usar el cuadro de mensajes directamente puertos de enlace](../core/how-to-use-messagebox-direct-bound-ports.md)   
 [Cómo utilizar la orquestación de socio directo puertos de enlace](../core/how-to-use-partner-orchestration-direct-bound-ports.md)