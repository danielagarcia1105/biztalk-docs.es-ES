---
title: Métodos estándar en Interfaces de componentes | Microsoft Docs
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
ms.openlocfilehash: eecb56f262a56e6567b44b146c631542cb1ceda6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994829"
---
# <a name="standard-methods-in-component-interfaces"></a>Métodos estándar en Interfaces de componentes
Los métodos estándar para la interfaz de componente son los siguientes:  
  
- `Create`  
  
- `Find`  
  
- `Get`  
  
- `Save`  
  
  Solo esos métodos del componente subyacente están disponibles. Por ejemplo, si el componente subyacente no contiene capacidades `Add`, `Create` no está disponible.  
  
## <a name="viewing-or-changing-available-methods"></a>Ver o cambiar los métodos disponibles  
  
#### <a name="to-view-or-change-available-methods"></a>Para ver o cambiar los métodos disponibles  
  
1.  Abra la interfaz de componente **propiedades** cuadro de diálogo.  
  
     ![](../core/media/psadapter-46-ps-properties.gif "PSAdapter_46_PS_Properties")  
  
2.  Haga clic en el **métodos estándar** ficha.  
  
3.  Seleccione los métodos deseados y, a continuación, haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Cómo crear Interfaces de componentes](../core/how-to-create-component-interfaces.md)   
 [Apéndice C: Uso de interfaces de componentes](../core/appendix-c-using-component-interfaces.md)