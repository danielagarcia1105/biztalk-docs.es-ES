---
title: Canalización de envío | Microsoft Docs
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
ms.openlocfilehash: 5700b3adb0769edff4ec820b4d95353383c08e6d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968021"
---
# <a name="send-pipeline"></a>Canalización de envío
Este ejemplo proporciona un Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] canalización de envío que se puede personalizar para su aplicación.  
  
## <a name="demonstrates"></a>Demostraciones  
 Este ejemplo muestra cómo procesar un mensaje XML saliente en el mensaje RNIF equivalente mediante la canalización de envío BTARN (PipelineSend.btp). PipelineSend.btp se encuentra en  *\<unidad\>*: \Program Files\Microsoft BizTalk \<versión\> Acelerador para RosettaNet\SDK\RNPipelines. Incluye las etapas siguientes:  
  
-   ensamblador XML.  
  
-   Codificador MIME  
  
-   Enviar mensaje Non-repudiate  
  
> [!NOTE]
>  Si selecciona uno de los componentes anteriores de la BTARN canalización de envío en el Diseñador de canalizaciones en Visual Studio, las propiedades de ese componente no se mostrará en el panel Propiedades. Para mostrar las propiedades del componente, debe agregar el componente al cuadro de herramientas mediante el **elegir elementos del cuadro de herramientas** comando en el menú Herramientas; elimine el componente existente desde la canalización de envío; y, a continuación, agregue el componente desde el Cuadro de herramientas en la fase apropiada en el Diseñador de canalizaciones. Si, a continuación, seleccione el componente, sus propiedades se mostrará en el panel Propiedades.  
  
 Para obtener más información acerca de los componentes de esta canalización y el flujo de mensajes dentro de esta canalización, consulte [canalización de envío de BTARN](../../adapters-and-accelerators/accelerator-rosettanet/btarn-send-pipeline.md).  
  
## <a name="see-also"></a>Vea también  
 [Ejemplos de canalizaciones](../../adapters-and-accelerators/accelerator-rosettanet/pipeline-samples.md)   
 [Canalización de envío de BTARN](../../adapters-and-accelerators/accelerator-rosettanet/btarn-send-pipeline.md)