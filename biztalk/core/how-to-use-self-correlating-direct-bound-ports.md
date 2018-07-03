---
title: Cómo usar puertos de enlace directo autocorrelación | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: feb651fa-3e35-4598-b229-335448f6919c
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eaad102db33b4967c89cb78f944b93a688e4c213
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982325"
---
# <a name="how-to-use-self-correlating-direct-bound-ports"></a>Cómo usar puertos de enlace directo de autocorrelación
Los puertos de enlace directo de autocorrelación hacen referencia a sí mismos. Esto significa que un puerto de enlace directo de autocorrelación suministra la información que puede utilizar una orquestación para devolver mensajes a su orquestación envolvente. Al utilizar el enlace directo de autocorrelación, el motor de orquestaciones generará un token de correlación en los mensajes que sean específicos de la instancia de orquestación. Esto ofrece la capacidad de devolver los mensajes a una instancia de orquestación específica sin usar un conjunto de correlaciones.  
  
 Por ejemplo, puede crear una recepción de autocorrelación puerto de enlace directo de orquestación mediante la especificación de **directo** para **enlace de puerto** y seleccionando **Autocorrelancionándose**en el Asistente para configuración de puerto. A continuación, en la orquestación B, declara un puerto como parámetro de orquestación de puerto de envío del mismo tipo de puerto que se ha definido en la orquestación A. Para ello, haga lo siguiente:  
  
1. En la ventana Vista orquestación, haga clic en **parámetros de orquestación**y, a continuación, haga clic en **nuevo parámetro de puerto**.  
  
2. En la ventana Propiedades, para **dirección de comunicación**, seleccione **enviar**y para **tipo de puerto**, seleccione el mismo tipo de puerto, tal como se define en la orquestación A.  
  
   Esta declaración crea un puerto de envío lógico en la Superficie para el puerto del Diseñador de orquestaciones. Orquestación A llama a orquestación B con la **Iniciar orquestación** dar forma y pasa el nuevo puerto como parámetro, junto con los parámetros de orquestación, a la orquestación B. orquestación B, a continuación, realiza su lógica de negocios y envía un mensaje en el nuevo puerto que se pasó a él. El mensaje se envía al puerto de enlace directo de autocorrelación de recepción de la instancia de la orquestación A que inició la orquestación B.  
  
   Aunque la secuencia de eventos anterior también se puede hacer con un **orquestación de llamada** forma, solo tiene sentido cuando se usa un **Iniciar orquestación** forma. Esto es porque cuando se usa un **orquestación de llamada** forma, los puertos se pasan por referencia. La polaridad del puerto debe ser igual en ambas orquestaciones. Por lo tanto, la dirección de comunicación del puerto que pase desde una orquestación debe ser la misma que la dirección de la referencia de puerto en la orquestación a la que se llama. Sin embargo, cuando se usa el **Iniciar orquestación** forma, se genera una instancia asíncrona de una orquestación y no puede tener **Out** o **Ref** parámetros; por lo tanto, el puerto de enlace directo de autocorrelación proporciona una forma de una orquestación responder a la instancia de orquestación que creó la instancia.  
  
   Para obtener un ejemplo de cómo usar puertos de enlace directo de autocorrelación, consulte el ejemplo SDK "Implementing Scatter y Gather Pattern" en [ http://go.microsoft.com/fwlink/?LinkId=73703 ](http://go.microsoft.com/fwlink/?LinkId=73703).  
  
## <a name="see-also"></a>Vea también  
 [Cómo usar puertos de enlace de directo de cuadro de mensajes](../core/how-to-use-messagebox-direct-bound-ports.md)   
 [Puertos de enlace de uso directo de orquestación de socio](../core/how-to-use-partner-orchestration-direct-bound-ports.md)