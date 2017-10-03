---
title: "Desarrollar un ensamblado de componente de canalización | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IComponentUI interface, assembling
- IBaseComponent interface, assembling
- pipeline interfaces, IBaseComponent
- pipeline components [custom], interfaces
- pipeline interfaces, IComponentUI
- IAssemblerComponent interface, assembling
- pipeline interfaces, IAssemblerComponent
- pipeline components [custom], assembling
ms.assetid: 2f85421d-2010-4a36-82b5-ea8016f8aa99
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8de06a815e1c5a6bf71700ad373ae3f278b3a9a2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="developing-an-assembling-pipeline-component"></a>Desarrollar un componente de canalización de ensamblado
Un componente de canalización de ensamblado es un componente .NET o COM que recibe varios mensajes en la entrada y produce un mensaje en la salida. Los componentes de ensamblado se utilizan para recopilar documentos individuales en el lote de intercambio de mensajes.  
  
> [!NOTE]
>  No se utiliza la funcionalidad de ensamblado, por lo que BizTalk Server siempre transfiere un documento a la entrada del componente.  
  
 Un componentes de ensamblado debe implementar las interfaces siguientes:  
  
-   `IBaseComponent`  
  
-   `IAssemblerComponent`
  
-   `IComponentUI`
  
-   **IPersistPropertyBag.** Consulte la documentación de .NET Framework SDK para esta interfaz.  
  
> [!NOTE]
>  Los componentes de canalización personalizados deberían copiar todas las partes adicionales del mensaje de entrada en los mensajes de salida. Con ello, se conservan para el procesamiento ulterior en la canalización.  
  
## <a name="see-also"></a>Vea también  
 [Desarrollar un componente de canalización de General](../core/developing-a-general-pipeline-component.md)   
 [Desarrollar un componente de canalización de desensamblado](../core/developing-a-disassembling-pipeline-component.md)   
 [Desarrollar un componente de canalización de búsqueda](../core/developing-a-probing-pipeline-component.md)   
 [Informar de errores de componentes de canalización](../core/reporting-errors-from-pipeline-components.md)   
 [Configurar componentes de canalización nativos](../core/configuring-native-pipeline-components.md)   
 [Implementar componentes de canalización](../core/deploying-pipeline-components.md)   
 [CustomComponent (ejemplo de BizTalk Server)](../core/customcomponent-biztalk-server-sample.md)