---
title: Configurar las transacciones atómicas, coherentes, aisladas y duraderas con el SDK de adaptador LOB de WCF | Documentos de Microsoft
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
ms.openlocfilehash: 58cf80a70b04e20aeb25b27210d88dfd861d7539
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224244"
---
# <a name="configure-atomic-consistent-isolated-and-durable-transactions-using-the-wcf-lob-adapter-sdk"></a>Configurar las transacciones atómicas, coherentes, aisladas y duraderas con el SDK de adaptador LOB de WCF
El [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] admite las transacciones al basarse en la funcionalidad expuesta por el [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]. Mediante la API expuesta por [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)], el adaptador puede admitir las transacciones y las operaciones que son:  
  
-   **Atomic**, asegurándose de que todas las actualizaciones pendientes se confirman o ninguno se confirman y se revierte a su estado anterior.  
  
-   **Coherente**, asegurarse de que los cambios realizados desde un estado coherente a otro.  
  
-   **Aislado**, evitar que una transacción para tener acceso a los cambios no confirmados en otras transacciones pendientes.  
  
-   **Duradero**, lo que significa que una vez confirmado, las actualizaciones serán persistentes frente a errores.  
  
 Sistemas de base de datos de los programadores del adaptador de destino relacional u otros sistemas de línea de negocio que admiten transacciones (o esperan) será necesario identificar cómo el sistema de destino es compatible con y expone la compatibilidad con transacciones y, a continuación, identificar un adecuado[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]modelo de transacción que se utilizará.  
  
 Para obtener más información acerca de [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] transacciones, vea [información general de las transacciones de Windows Communication Foundation](https://msdn.microsoft.com/library/ms733904.aspx). 
  
## <a name="see-also"></a>Vea también  
 [Planear y diseñar el adaptador mediante el SDK de adaptador LOB de WCF](../../adapters-and-accelerators/wcf-lob-adapter-sdk/plan-and-design-your-adapter-using-the-wcf-lob-adapter-sdk.md)