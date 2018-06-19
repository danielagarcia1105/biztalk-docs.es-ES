---
title: Canalización de envío | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 58ca6a63-525a-4b16-932d-6d26e68f6fab
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1b7ee5ad712466df79a4e6961062ea56b73ad248
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25964066"
---
# <a name="send-pipeline"></a>Canalización de envío
Este ejemplo proporciona un [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] canalización de envío que se puede personalizar para la aplicación.  
  
## <a name="demonstrates"></a>Demostraciones  
 Este ejemplo muestra cómo procesar un mensaje XML saliente en el mensaje RNIF equivalente mediante la canalización de envío BTARN (PipelineSend.btp). PipelineSend.btp se encuentra en  *\<unidad\>*: \Program BizTalk \<versión\> Acelerador para RosettaNet\SDK\RNPipelines. Incluye las etapas siguientes:  
  
-   ensamblador XML.  
  
-   Codificador MIME  
  
-   Enviar mensaje repudiate no  
  
> [!NOTE]
>  Si selecciona uno de los componentes anteriores de la BTARN canalización de envío en el Diseñador de canalizaciones en Visual Studio, las propiedades de ese componente no se mostrará en el panel Propiedades. Para mostrar las propiedades del componente, debe agregar el componente al cuadro de herramientas mediante el **elegir elementos del cuadro de herramientas** de comandos en el menú Herramientas; eliminar el componente existente de la canalización de envío; y, a continuación, agregue el componente de la Cuadro de herramientas en la fase apropiada en el Diseñador de canalizaciones. Si, a continuación, seleccione el componente, sus propiedades se mostrará en el panel Propiedades.  
  
 Para obtener más información acerca de los componentes de esta canalización y el flujo de mensajes dentro de esta canalización, consulte [canalización de envío de BTARN](../../adapters-and-accelerators/accelerator-rosettanet/btarn-send-pipeline.md).  
  
## <a name="see-also"></a>Vea también  
 [Ejemplos de canalizaciones](../../adapters-and-accelerators/accelerator-rosettanet/pipeline-samples.md)   
 [Canalización de envío de BTARN](../../adapters-and-accelerators/accelerator-rosettanet/btarn-send-pipeline.md)