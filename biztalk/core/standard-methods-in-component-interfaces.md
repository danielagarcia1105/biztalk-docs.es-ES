---
title: Métodos estándar en Interfaces de componentes | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- component interfaces, standard methods
- methods, viewing
- methods, component interfaces
- methods, changing
ms.assetid: 2273d946-3fc8-4b2d-a6a1-9e4f0da74d5b
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f44b3977a3921d92b1f3f83dd3e744f14b5709fc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278052"
---
# <a name="standard-methods-in-component-interfaces"></a>Métodos estándar en Interfaces de componentes
Los métodos estándar para la interfaz de componente son los siguientes:  
  
-   `Create`  
  
-   `Find`  
  
-   `Get`  
  
-   `Save`  
  
 Solo esos métodos del componente subyacente están disponibles. Por ejemplo, si el componente subyacente no contiene capacidades `Add`, `Create` no está disponible.  
  
## <a name="viewing-or-changing-available-methods"></a>Ver o cambiar los métodos disponibles  
  
#### <a name="to-view-or-change-available-methods"></a>Para ver o cambiar los métodos disponibles  
  
1.  Abra la interfaz de componentes **propiedades** cuadro de diálogo.  
  
     ![](../core/media/psadapter-46-ps-properties.gif "PSAdapter_46_PS_Properties")  
  
2.  Haga clic en el **métodos estándar** ficha.  
  
3.  Seleccione los métodos deseados y, a continuación, haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Cómo crear Interfaces de componentes](../core/how-to-create-component-interfaces.md)   
 [Apéndice C: usar Interfaces de componentes](../core/appendix-c-using-component-interfaces.md)