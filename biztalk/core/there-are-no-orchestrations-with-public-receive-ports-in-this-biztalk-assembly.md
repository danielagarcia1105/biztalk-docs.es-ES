---
title: No hay orquestaciones con público puertos de recepción en este ensamblado de BizTalk | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fb901d49-ce3c-4bc6-806a-eb5964d32bb4
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8e04c10119b617ebabe07169dcae999fe60210e0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279644"
---
# <a name="there-are-no-orchestrations-with-public-receive-ports-in-this-biztalk-assembly"></a>No hay orquestaciones con puertos de recepción públicos en este ensamblado de BizTalk
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|Identificador del evento|0|  
|Origen del evento|0|  
|Componente|0|  
|Nombre simbólico|0|  
|Texto del mensaje|No hay orquestaciones con puertos de recepción públicos en este ensamblado de BizTalk. Retroceda y especifique un ensamblado de BizTalk que contenga orquestaciones con puertos de recepción públicos.|  
  
## <a name="explanation"></a>Explicación  
 Este error indica que la orquestación selecciona‎da no tiene un puerto público.  
  
## <a name="user-action"></a>Acción del usuario  
 Use el procedimiento siguiente para configurar un puerto público.  
  
#### <a name="to-configure-a-public-port"></a>Para configurar un puerto público  
  
1.  Localice la orquestación y haga que el puerto de recepción deseado sea público.  
  
    1.  Abra al Asistente para configuración de puerto.  
  
    2.  En **seleccionar un tipo de puerto**, cambiar **restricciones de acceso** de **interno** (valor predeterminado) en **público: sin límite**.  
  
2.  Vuelva a compilar el ensamblado.  
  
     \- O BIEN  
  
     Cargue un ensamblado BizTalk con puertos de recepción públicos.