---
title: Procedimientos recomendados para la configuración de BizTalk Server | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e62024e1-f502-45a8-932f-edd8460bcf5f
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 461e2e1a4256d79112e4eec94047c25df34a4511
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001126"
---
# <a name="best-practices-for-biztalk-server-settings"></a>Procedimientos recomendados para la configuración de BizTalk Server
Este tema enumeran los procedimientos recomendados que debe seguir al realizar los procedimientos de preparación operativa para [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
 **Configurar el mensaje de procesamiento por lotes para aumentar el rendimiento del adaptador**  
  
- Minimizar el número de transacciones realizadas por un adaptador mediante la combinación de más de una operación en un único lote.  
  
- Limitar el tamaño del lote en función del número total de bytes en el lote, además de recuento de mensajes. Para obtener más información acerca de cómo limitar el tamaño del lote, vea [configuración de procesamiento por lotes para mejorar el rendimiento del adaptador](../technical-guides/configuring-batching-to-improve-adapter-performance.md).  
  
  **Ajustar el umbral de mensajes de gran tamaño**  
  
- Para mejorar el rendimiento, aumentar el umbral de mensajes de gran tamaño, lo que reduce el número de mensajes de gran tamaño que se almacenan en búfer en el disco durante la asignación.  
  
  **Determinar la información que necesita para realizar un seguimiento durante la planeación**  
  
- Debe decidir durante las fases de planeamiento de la información que necesita para realizar el seguimiento. De este modo, después de implementar el proyecto, puede establecer las opciones de seguimiento y limitar la cantidad de datos de seguimiento para proporcionar solo la información que necesita.  
  
  > [!NOTE]  
  >  Para obtener más información acerca de las prácticas recomendadas para seguimiento, vea [planificación del seguimiento](../technical-guides/planning-for-tracking.md) en esta guía y [seguimiento de estado y actividad](http://go.microsoft.com/fwlink/p/?LinkId=154187) (http://go.microsoft.com/fwlink/p/?LinkId=154187).  
  
  **No realizar seguimiento de todos los mensajes**  
  
- Se recomienda realizar un seguimiento no todos los mensajes. Esto es porque cada vez que se toca un mensaje, BizTalk Server crea otra copia del mensaje. En su lugar, puede restringir el ámbito mediante el seguimiento solo a un puerto específico. Esto ayuda a maximizar el rendimiento del sistema y a mantener despejado las bases de datos.  
  
  **Establecer el seguimiento en los puertos de envío y puertos en lugar de en una canalización de recepción**  
  
- Si configura las opciones de seguimiento de canalizaciones, también establecerá las opciones de seguimiento globalmente para todos los puertos que usa la canalización. Esto puede producir a su vez en muchos más datos de seguimiento que desea, lo que ralentizan el rendimiento del sistema. En su lugar, puede establecer las opciones de seguimiento en el envío de puertos y los puertos de recepción.  
  
  **Ajustar la limitación basada en la utilización de recursos**  
  
- Limitación en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] está configurado de forma predeterminada para proporcionar una buena protección para el sistema. Supervisar los contadores de rendimiento para la limitación de Estados para ver si la limitación está teniendo lugar. Analice, a continuación, si se basa el recurso en qué tipo de limitación (por ejemplo, base de datos de uso de memoria o de tamaño) se utiliza debajo o por encima. A continuación, ajustar la limitación de peticiones umbrales hacia arriba o hacia abajo según corresponda. Para obtener más información, consulte [ajustar umbrales de limitación: cuándo y por qué](http://go.microsoft.com/fwlink/p/?LinkId=154188) (<http://go.microsoft.com/fwlink/p/?LinkId=154188>).  
  
  **Usar la canalización PassThruTransmit si es posible**  
  
- Si no es necesario ningún procesamiento de documentos antes de enviar un mensaje a su destino, use la canalización PassThruTransmit en lugar de la canalización de envío XML.  
  
  **Minimizar el uso de orquestación "de forma Inicio y de finalización" eventos de seguimiento**  
  
- Aunque la forma orquestación de seguimiento tiene ventajas evidentes para la depuración de orquestación, tiene implicaciones de escalabilidad y de rendimiento. El **forma Inicio y finalización** evento de seguimiento puede provocar una sobrecarga considerable. Es mejor minimizar su uso en entornos de producción donde es necesario un alto rendimiento.  
  
  > [!NOTE]  
  >  **Forma Inicio y finalización** eventos de seguimiento están habilitados de forma predeterminada en todas las orquestaciones.  
  
## <a name="see-also"></a>Vea también  
 [Lista de comprobación: configuración de BizTalk Server](../technical-guides/checklist-configuring-biztalk-server.md)