---
title: Canalizaciones de recepción | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive pipelines, about receive pipelines
- receive pipelines, message flow
- receive pipelines
- messages, receive pipelines
- messages, message flow
- pipelines, receive pipelines
- receive pipelines, stages
ms.assetid: ee75c1d4-00b7-4177-bca3-1447a39d2238
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a0a248c69cb96603e9c4883e5d21caa39165da13
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268868"
---
# <a name="receive-pipelines"></a>Canalizaciones de recepción
La ilustración que aparece a continuación muestra el flujo de trabajo de procesamiento de mensajes aunque se centra en la canalización de recepción.  
  
 ![Diagrama del flujo de trabajo de procesamiento de mensajes. ] (../core/media/ebiz-dev-busprcsb.gif "ebiz_dev_busprcsb")  
Representación del flujo de trabajo de procesamiento de mensajes.  
  
 Una canalización de recepción funciona en un mensaje después de ser recibido por el adaptador de recepción. La canalización de recepción toma el mensaje inicial, realiza algunas transformaciones, y desensambla los datos sin procesar en uno, ninguno o varios mensajes. Entonces, el servidor de BizTalk Server puede procesar estos mensajes individuales.  
  
> [!NOTE]
>  Una canalización de recepción puede no crear ningún mensaje si se agrega a la canalización un componente que se esté utilizando. En este caso, el componente de canalización consume el mensaje y no crea ningún mensaje de salida. Si un componente que se está utilizando se coloca después de un componente de desensamblado, la ejecución de canalización se detiene después de haber consumido el primer mensaje y no se recupera ningún mensaje posterior del componente de desensamblado.  
  
 Al crear un proceso empresarial, puede crear una canalización de recepción nueva o puede usar uno de los dos valores predeterminados incluidas en BizTalk Server de canalizaciones de recepción, la canalización de recepción de paso a través o el código XML de la canalización de recepción. Para obtener más información acerca de estas canalizaciones predeterminadas, vea [canalizaciones predeterminadas](../core/default-pipelines.md).  
  
 La canalización de recepción consta de cuatro fases: descodificación, desensamblado, validación y ResolveParty. Este tema contiene consideraciones de diseño para rellenar estas fases.  
  
> [!NOTE]
>  En esta versión, no se admite el cambio de orden o presencia de estas fases en una canalización.  
  
## <a name="decode-stage"></a>Fase de descodificación  
  
-   Esta fase se utiliza para los componentes que descodifican o descifran el mensaje.  
  
    -   El componente de canalización de descodificador de MIME/SMIME o un componente de descodificación predeterminado debe situarse en esta fase si los mensajes de entrada necesitan descodificarse de un formato a otro.  
  
-   Esta fase recibe un mensaje y crea otro.  
  
-   Esta fase puede contener entre cero y 255 componentes.  
  
-   Se ejecutan todos los componentes de esta fase.  
  
## <a name="disassemble-stage"></a>Fase de desensamblado  
  
-   Esta fase se utiliza para los componentes que analizan o desensamblan el mensaje.  
  
    -   Los componentes de esta fase comprueban el mensaje para ver si se reconoce su formato. Según el reconocimiento del formato, uno de los componentes desensambla el mensaje.  
  
    -   Si esta fase contiene más de un componente, solo se ejecuta el primero que reconoce el formato del mensaje. Si ninguno de los componentes dentro de la fase reconoce el formato del mensaje, se produce un error de procesamiento de formato.  
  
    -   Esta fase debe incluir cualquier componente personalizado que implemente un comportamiento especial para desensamblar el contenido del mensaje.  
  
    -   Esta fase puede contener entre cero y 255 componentes. Si no hay ningún componente en la fase, se pasa el mensaje.  
  
## <a name="validate-stage"></a>Fase de validación  
  
-   Esta fase se utiliza para los componentes que validan el formato del mensaje.  
  
    -   Un componente de canalización solo procesa mensajes que se ajusten al esquema especificado en ese componente. Si una canalización recibe un mensaje cuyo esquema no está asociado con ningún componente de la canalización, ese mensaje no se procesa. Según el adaptador que envíe el mensaje, éste se suspende o se genera un error de remitente.  
  
    -   Los componentes de esta fase se utilizan para validar los mensajes XML creados en la fase de desensamblado. Los componentes de esta fase especifican esquemas para realizar la validación XML.  
  
-   Esta fase puede contener entre cero y 255 componentes.  
  
-   Se ejecutan todos los componentes de esta fase.  
  
    -   Esta fase puede ejecutarse más una vez. Se ejecuta una vez por cada mensaje creado en la fase de desensamblado.  
  
## <a name="resolveparty-stage"></a>ResolveParty  
  
-   Esta fase es un marcador de posición para el [componente de canalización de resolución de entidad](../core/party-resolution-pipeline-component.md).  
  
-   Esta fase puede ejecutarse más una vez. Se ejecuta una vez por cada mensaje creado en la fase de desensamblado.  
  
-   Esta fase puede contener entre cero y 255 componentes.  
  
-   Se ejecutan todos los componentes de esta fase.  
  
## <a name="see-also"></a>Vea también  
 [Canalizaciones de envío](../core/send-pipelines.md)   
 [Acerca de las canalizaciones, fases y componentes](../core/about-pipelines-stages-and-components.md)   
 [Tipos de componentes de canalización](../core/types-of-pipeline-components.md)   
 [Canalizaciones predeterminadas](../core/default-pipelines.md)   
 [Plantillas de canalización](../core/pipeline-templates.md)   
 [Componentes de canalización](../core/pipeline-components.md)   
 [Tipos de canalizaciones](../core/types-of-pipelines.md)