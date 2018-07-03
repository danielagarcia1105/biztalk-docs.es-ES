---
title: Configurar las transacciones atómicas, coherentes, aisladas y duraderas mediante el SDK de adaptador LOB de WCF | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c20d2613-c77d-4b0d-b2e2-3ed28a8fb36c
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 37b39ec0e240a2d4ee9ba1239cf27d7b118ca0ad
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007709"
---
# <a name="configure-atomic-consistent-isolated-and-durable-transactions-using-the-wcf-lob-adapter-sdk"></a>Configurar las transacciones atómicas, coherentes, aisladas y duraderas mediante el SDK de adaptador LOB de WCF
El [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] admite transacciones basándose en la funcionalidad expuesta por el [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]. Mediante el uso de la API expuesta por [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)], el adaptador pueda admitir las transacciones y operaciones que son:  
  
- **Atomic**, lo que garantiza que todas las actualizaciones pendientes se confirman o ninguno se confirman y se revierten a su estado anterior.  
  
- **Coherente**, asegurarse de que los cambios realizados desde un estado coherente a otro.  
  
- **Aislado**, impidiendo una transacción para tener acceso a los cambios no confirmados en otras transacciones pendientes.  
  
- **Durable**, lo que significa que una vez confirmado, las actualizaciones serán persistentes frente a errores.  
  
  Sistemas de base de datos de los programadores del adaptador como destino relacional u otros sistemas de línea de negocio que admiten las transacciones (o esperarían) necesitará identificar cómo el sistema de destino es compatible con y expone la compatibilidad con transacciones y, a continuación, identificar un adecuado[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]modelo de transacción que se utilizará.  
  
  Para obtener más información acerca de [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] transacciones, vea [información general sobre las transacciones de Windows Communication Foundation](https://msdn.microsoft.com/library/ms733904.aspx). 
  
## <a name="see-also"></a>Vea también  
 [Planear y diseñar el adaptador mediante el SDK de adaptador LOB de WCF](../../adapters-and-accelerators/wcf-lob-adapter-sdk/plan-and-design-your-adapter-using-the-wcf-lob-adapter-sdk.md)