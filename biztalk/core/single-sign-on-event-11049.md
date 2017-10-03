---
title: "Inicio de sesión único: Evento 11049 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 031ec1a6-4b2b-46b2-9dbb-5525d758651f
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 45ac6095950e02e7e73ab287b180bc22d88b4191
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-11049"></a>Inicio de sesión único: Evento 11049
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|11049|  
|Origen del evento|ENTSSO|  
|Componente|N/D|  
|Nombre simbólico|SSO_ERROR_DTC_FAILED|  
|Texto del mensaje|No se pudo obtener MSDTC. SSO necesita MSDTC para funcionar correctamente.|  
  
## <a name="explanation"></a>Explicación  
 El sistema ENTSSO no pudo conectarse con Microsoft DTC (Coordinador de transacciones distribuidas).  
  
## <a name="user-action"></a>Acción del usuario  
 Compruebe si MSDTC se encuentra operativo actualmente.  
  
 Para obtener ayuda sobre problemas de MSDTC, vea [solución de problemas con MSDTC](../core/troubleshooting-problems-with-msdtc.md).