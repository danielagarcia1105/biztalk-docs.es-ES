---
title: Limitaciones de TIBCO Rendezvous | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: TIBCO Rendezvous, limitations
ms.assetid: 8e210457-2887-43f9-a249-be1daa6ee4eb
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 717188e42450d13dee92364cd9c673aaaf48eaf6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="tibco-rendezvous-limitations"></a>Limitaciones de TIBCO Rendezvous
En TIBCO Rendezvous, la exclusividad del nombre de campo no se garantiza. Si un mensaje de TIBCO Rendezvous contiene dos nombres de campo que son iguales, el XML resultante no es válido.  
  
 Otras limitaciones incluyen:  
  
-   No se proporciona la ordenación y clasificación de los campos.  
  
-   Según la documentación de TIBCO Rendezvous, los caracteres no imprimibles no se usan en nombres de asunto; sin embargo, sigue siendo posible usarlos. BizTalk Adapter para TIBCO Rendezvous no admite nombres de asunto que contengan esos caracteres.  
  
-   No se admite la conexión a daemons.  
  
-   No se admiten tipos de datos personalizados.  
  
-   No se admite la mensajería certificada en el lado de transmisión.  
  
## <a name="see-also"></a>Vea también  
 [Conceptos de TIBCO Rendezvous](../core/tibco-rendezvous-concepts.md)   
 [Introducción](../core/getting-started-with-biztalk-adapter-for-tibco-rendezvous.md)