---
title: Cómo configurar propiedades de transacción en una orquestación | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- atomic transactions
- orchestrations, transactions
- transactions, long-running
- orchestrations, configuring
- transactions, atomic
ms.assetid: 8eec6019-4d96-4ed6-8a90-9403738d8af4
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9164a9f5670a996a62450a19d802c97b89d8e242
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248820"
---
# <a name="how-to-configure-transactional-properties-on-an-orchestration"></a>Cómo configurar propiedades de transacción en una orquestación
Una orquestación puede tratarse como una transacción atómica, una transacción de larga ejecución o como ninguna de ellas.  
  
### <a name="to-make-your-orchestration-an-atomic-transaction"></a>Para convertir la orquestación en una transacción atómica  
  
1.  En la ventana Vista orquestación, seleccione **propiedades de orquestación**.  
  
2.  En la ventana Propiedades, seleccione **atómica** en la lista desplegable para la **tipo de transacción** propiedad.  
  
     **Lote**, **compensación**, **nivel de aislamiento**, **vuelva a intentar**, **tiempo de espera**, y **transacciones Identificador** aparecen como propiedades en la ventana Propiedades, tal y como hace para cualquier ámbito. Para obtener más información acerca de estas propiedades, vea [cómo configurar la forma ámbito](../core/how-to-configure-the-scope-shape.md).  
  
### <a name="to-make-your-orchestration-a-long-running-transaction"></a>Para convertir la orquestación en una transacción de larga ejecución  
  
1.  En la ventana Vista orquestación, seleccione **propiedades de orquestación**.  
  
2.  En la ventana Propiedades, seleccione **larga ejecución** en la lista desplegable para la **tipo de transacción** propiedad.  
  
     **Compensación**, **tiempo de espera**, y **identificador de transacción** aparecen como propiedades en la ventana Propiedades. Para obtener más información acerca de estas propiedades, tal y como se comportan con cualquier ámbito. Para obtener más información acerca de estas propiedades, vea [cómo configurar la forma ámbito](../core/how-to-configure-the-scope-shape.md).  
  
## <a name="see-also"></a>Vea también  
 [Realizar orquestaciones transaccionales](../core/making-orchestrations-transactional.md)