---
title: 'Inicio de sesión único: Evento 10604 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eea14ab1-5a89-4a62-b414-1bcb36ea339e
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d9d6858fb13542ca642c9c48a8a187b66ba6526
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270548"
---
# <a name="single-sign-on-event-10604"></a>Inicio de sesión único: Evento 10604
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|10604|  
|Origen del evento|ENTSSO|  
|Componente|N/D|  
|Nombre simbólico|SSO_ERROR_SSOCSTX_OUT_OF_PROC|  
|Texto del mensaje|La aplicación COM+ "Servidor de ENTSSO" no está configurada correctamente. Debe ser una aplicación de biblioteca COM+.|  
  
## <a name="explanation"></a>Explicación  
 La aplicación COM+ debe configurarse como una aplicación de biblioteca COM+.  
  
## <a name="user-action"></a>Acción del usuario  
 En Complemento MMC de ENTSSO, expanda la carpeta COM+ y busque el servidor de ENTSSO. Haga clic con el botón secundario en el servidor y, a continuación, haga clic en Propiedades. En lugar de Aplicación de servidor, seleccione Aplicación de biblioteca y, a continuación, haga clic en Aceptar.