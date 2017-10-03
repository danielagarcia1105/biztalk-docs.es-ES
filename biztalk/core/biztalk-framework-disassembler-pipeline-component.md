---
title: "Componente de canalización de desensamblador de BizTalk Framework | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipeline components, BizTalk Framework Disassembler
- BizTalk Framework Disassembler [pipeline component]
ms.assetid: 48d6c530-5c02-4c70-ad11-0ea6c3c808f8
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e1ab54ddb9ef0b5fa389e6716fc4426978dcbd7a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="biztalk-framework-disassembler-pipeline-component"></a>Componente de canalización de desensamblador de BizTalk Framework
El componente de canalización de desensamblador de BizTalk Framework analiza datos XML y determina si contienen carga de mensajería basada en BizTalk Framework. El componente de canalización guarda el contexto del mensaje y se crea uno nuevo con la propiedad de BizTalk Framework que haya que generar. Esta propiedad se utiliza para enrutar el mensaje al controlador de entrada de BizTalk Framework de forma que pueda recibir el mensaje que procesar.  
  
 El componente de canalización de desensamblador de BizTalk Framework proporciona una confirmación para el mensaje generado si el remitente solicitó una mediante el encabezado deliverReceiptRequest dentro del sobre de BizTalk Framework. Esto lo controla la propiedad generar notificación de entrega del componente de canalización de ensamblador de BizTalk Framework. Para obtener más información sobre el marco de trabajo de BizTalk, consulte [componente de canalización de ensamblador de BizTalk Framework](../core/biztalk-framework-assembler-pipeline-component.md).  
  
 Para obtener información sobre cómo configurar el componente de canalización de desensamblador de BizTalk Framework y crear la orquestación, consulte [cómo configurar el componente de canalización de desensamblador de BizTalk Framework](../core/how-to-configure-the-biztalk-framework-disassembler-pipeline-component.md).  
  
## <a name="see-also"></a>Vea también  
 [Cómo configurar el componente de canalización de desensamblador de BizTalk Framework](../core/how-to-configure-the-biztalk-framework-disassembler-pipeline-component.md)   
 [Componentes de canalización](../core/pipeline-components.md)