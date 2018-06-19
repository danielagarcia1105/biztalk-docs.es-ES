---
title: Prácticas recomendadas para la configuración de BizTalk Server | Documentos de Microsoft
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
ms.openlocfilehash: bf1f89ced33be6f10ceaae37ccb2c899c4e01eac
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22299524"
---
# <a name="best-practices-for-biztalk-server-settings"></a>Prácticas recomendadas para la configuración de BizTalk Server
Este tema enumeran las prácticas recomendadas que debería seguir al realizar procedimientos de preparación operativa para [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
 **Configurar el procesamiento por lotes de mensajes para aumentar el rendimiento de adaptador**  
  
-   Minimice el número de transacciones realizadas por un adaptador mediante la combinación de más de una operación en un único lote.  
  
-   Limitar el tamaño del lote en función del número total de bytes en el lote, además de recuento de mensajes. Para obtener más información acerca de cómo limitar el tamaño del lote, consulte [configuración de procesamiento por lotes para mejorar el rendimiento del adaptador](../technical-guides/configuring-batching-to-improve-adapter-performance.md).  
  
 **Ajustar el umbral de mensajes de gran tamaño**  
  
-   Para mejorar el rendimiento, aumentar el umbral de mensajes de gran tamaño, lo que reduce el número de mensajes de gran tamaño que se almacenan en búfer en el disco durante la asignación.  
  
 **Determinar la información que necesita para realizar un seguimiento durante la planeación**  
  
-   Debe decidir durante las fases de planeamiento la información que necesita para realizar el seguimiento. De este modo, después de implementar el proyecto, puede establecer las opciones de seguimiento y limitar la cantidad de datos a fin de sólo la información que necesita.  
  
    > [!NOTE]  
    >  Para obtener más información sobre los procedimientos recomendados relacionados con el seguimiento, vea [planeación para el seguimiento de](../technical-guides/planning-for-tracking.md) en esta guía y [seguimiento de estado y actividad](http://go.microsoft.com/fwlink/p/?LinkId=154187) (http://go.microsoft.com/fwlink/p/?LinkId=154187).  
  
 **No realizar seguimiento de todos los mensajes**  
  
-   Se recomienda que no realiza el seguimiento todos los mensajes. Esto es porque cada vez que se toca un mensaje, BizTalk Server crea otra copia del mensaje. En su lugar, puede restringir el ámbito mediante el seguimiento solo un puerto específico. Esto ayuda a maximizar el rendimiento del sistema y mantener las bases de datos ordenado.  
  
 **Configurar seguimiento de los puertos de envío y puertos en lugar de en una canalización de recepción**  
  
-   Si establece opciones de seguimiento en las canalizaciones, también establecerá las opciones de seguimiento globalmente para todos los puertos que usa la canalización. Esto a su vez puede hacer mucho más datos sometidos a seguimiento que piensa, lo que ralentizan el rendimiento del sistema. En su lugar, puede establecer opciones de seguimiento en el envío de puertos y puertos de recepción.  
  
 **Ajustar la limitación basada en la utilización de recursos**  
  
-   Limitación en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se configura de forma predeterminada para proporcionar una buena protección para el sistema. Supervisar los contadores de rendimiento para la limitación de Estados para ver si la limitación está teniendo lugar. Analice, a continuación, si se basa el recurso de la limitación (por ejemplo, la base de datos el uso de tamaño o memoria) es bajo o utilizando en exceso. A continuación, ajustar la limitación de peticiones umbrales hacia arriba o hacia abajo según corresponda. Para obtener más información, consulte [ajustar umbrales de limitación: cuándo y por qué](http://go.microsoft.com/fwlink/p/?LinkId=154188) (http://go.microsoft.com/fwlink/p/?LinkId=154188).  
  
 **Si es posible usar la canalización PassThruTransmit**  
  
-   Si no es necesario ningún procesamiento del documento antes de enviar un mensaje a su destino, use la canalización PassThruTransmit en lugar de la canalización de envío XML.  
  
 **Minimizar el uso de orquestación "forma Inicio y finalización" eventos de seguimiento**  
  
-   Aunque forma orquestación de seguimiento tiene ventajas obvias para la depuración de orquestación, tiene implicaciones de escalabilidad y de rendimiento. El **forma Inicio y finalización** evento de seguimiento puede provocar una sobrecarga significativa. Es mejor minimizar su uso en entornos de producción donde es necesario un alto rendimiento.  
  
    > [!NOTE]  
    >  **Forma Inicio y finalización** eventos de seguimiento están habilitados de forma predeterminada en todas las orquestaciones.  
  
## <a name="see-also"></a>Vea también  
 [Lista de comprobación: Configuración de BizTalk Server](../technical-guides/checklist-configuring-biztalk-server.md)