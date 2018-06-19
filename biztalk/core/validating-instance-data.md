---
title: Validar datos de instancia | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 19c3ca83-0abf-42ba-8e29-653ff12d5e20
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 86cde9d6133959e34ec09880be8a6beca5c37191
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287980"
---
# <a name="validate-instance-data"></a>Validar datos de instancia

## <a name="overview"></a>Información general
Durante el proceso de prueba de una asignación, quizá desee validar los datos de instancia con respecto a los esquemas de origen y destino para comprobar que esos datos de instancia se ajustan a la estructura del esquema. Para validar un mensaje de instancia con respecto al esquema de origen o destino, haga clic en el esquema en el Explorador de soluciones y, a continuación, haga clic en **Validar instancia**.  
  
> [!IMPORTANT]
>  Si en la salida utiliza constantes o datos personalizados, debe comprobar que los tipos de datos de los datos de prueba de origen y los valores constantes de destino sean válidos. Cuando se valida una asignación, el asignador de BizTalk no comprueba si los datos de instancia infringen los tipos de datos definidos por los esquemas. Esto se hace al probar la asignación o validar los datos de instancia.  
  
 Para obtener más información acerca de cómo generar y validar datos de instancia mediante el Editor de BizTalk, consulte [validación y generación de mensaje de instancia](../core/instance-message-generation-and-validation.md) y [validación de instancia](../core/instance-validation.md). . El **valor** propiedad del nodo de un esquema también afecta a cómo BizTalk genera datos de instancia. Para obtener más información, consulte el **propiedades del nodo esquema** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].
  
## <a name="see-also"></a>Vea también  
-  [Validación y generación de mensajes de instancia](../core/instance-message-generation-and-validation.md)   
-  [Cómo validar esquemas en Visual Studio](../core/how-to-validate-schemas-in-visual-studio.md)   
-  **Referencia de propiedad se asignan**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]  
-  [Probar las asignaciones](../core/testing-maps.md)