---
title: Informar de errores de componentes de canalización | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IErrorInfo object
- pipeline components [custom], errors
- SetErrorInfo method
- Exception object
ms.assetid: ad7c519e-829a-4a92-a42f-3e367d5dbaa8
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c111a0c10f4316e7b29e873adf53a8e6b9a9acd
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25976042"
---
# <a name="reporting-errors-from-pipeline-components"></a>Informar de errores de componentes de canalización
Los componentes de canalización informan de errores de dos formas:  
  
-   En el caso de los componentes basados en .NET, mediante el inicio de una excepción.  
  
-   Componentes basados en COM, estableciendo el **ErrorInfo** objeto y devuelve un HRESULT de error.  
  
## <a name="reporting-errors-from-net-pipeline-components"></a>Notificar errores desde los componentes de canalización .NET  
 Para notificar un error, el componente de canalización basado en .NET necesita iniciar una excepción en la ubicación en la que informa del error. Para notificar el nombre del componente que se produce un error, establezca el **origen** propiedad de la **excepción** objeto.  
  
 El motor de mensajería utiliza el **mensaje** y **origen** propiedades de la **excepción** objeto que se va a notificar un error. Se escribe el siguiente mensaje en el registro de eventos:  
  
 "Hubo un error al ejecutar el [recepción &#124; envío] canalización: \<nombre de la canalización\> origen: \<origen\> [ubicación de recepción &#124; Puerto de envío:] \<ubicación &#124; nombre de puerto\> razón: \<mensaje\>. "  
  
## <a name="reporting-errors-from-com-pipeline-components"></a>Notificar errores desde los componentes de canalización COM  
 Para notificar un error, los componentes de canalización basados en COM realizan las siguientes acciones:  
  
1.  Los grupos de componentes de canalización del **IErrorInfo** objeto mediante una llamada a la **SetErrorInfo** método.  
  
2.  El componente de canalización devuelve un error de HRESULT al motor de mensajería.  
  
 El motor de mensajería utiliza el **GetSource** y **GetDescription** propiedades de la **IErrorInfo** objeto que se va a notificar un error. Si no se ha establecido el origen, se usa el nombre del componente. Si la descripción no está establecido o todo el **ErrorInfo** objeto no está establecido, se notifica el HRESULT devuelto en lugar de la descripción. Se escribe el siguiente mensaje en el registro de eventos:  
  
 "Hubo un error al ejecutar el [recepción &#124; envío] canalización: \<nombre de la canalización\> origen: \<GetSource\> [ubicación de recepción &#124; Puerto de envío:] \<ubicación &#124; nombre de puerto\> razón: \<GetDescription o HRESULT\>. "  
  
## <a name="see-also"></a>Vea también  
 [Desarrollo de componentes de canalización personalizados](../core/developing-custom-pipeline-components.md)