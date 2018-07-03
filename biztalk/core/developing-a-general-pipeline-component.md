---
title: Desarrollar un componente de canalización generales | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 63f5d8d1-30fb-4a1e-b4bd-2be07b618b20
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8ca387b139a32606dea89f7c931c86245d151dcb
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966693"
---
# <a name="developing-a-general-pipeline-component"></a>Desarrollar un componente de canalización generales

## <a name="interfaces"></a>Interfaces
Un componente general de canalización consiste en un componente .NET o COM que implementa las interfaces siguientes:  
  
- Interfaz IBaseComponent (COM) [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
  
- IComponent (interfaz) (COM) [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
  
- Interfaz IComponentUI (COM) [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
  
- [IPersistPropertyBag](https://docs.microsoft.com/dotnet/api/microsoft.visualstudio.ole.interop.ipersistpropertybag)
  
  Un componente general de canalización recibe un mensaje del motor de mensajería de BizTalk, lo procesa y lo devuelve al motor de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Los componentes generales también pueden implementarse de modo que no devuelvan mensajes al servidor. A estos componentes se les denomina componentes consumidores porque el componente recibe mensajes, pero no genera ningún mensaje de resultado.  
  
> [!NOTE]
>  Los componentes de canalización personalizados deberían copiar todas las partes adicionales del mensaje de entrada en los mensajes de salida. Con ello, se conservan para el procesamiento ulterior en la canalización.  
  
## <a name="more-pipeline-resources"></a>Más recursos de la canalización
 [Desarrollar un componente de canalización de ensamblado](../core/developing-an-assembling-pipeline-component.md)   
 [Desarrollar un componente de canalización de desensamblado](../core/developing-a-disassembling-pipeline-component.md)   
 [Desarrollar un componente de canalización de búsqueda](../core/developing-a-probing-pipeline-component.md)   
 [Informes de errores de componentes de canalización](../core/reporting-errors-from-pipeline-components.md)   
 [Configurar componentes de canalización nativos](../core/configuring-native-pipeline-components.md)   
 [Implementar componentes de canalización](../core/deploying-pipeline-components.md)   
 [CustomComponent (ejemplo de BizTalk Server)](../core/customcomponent-biztalk-server-sample.md)