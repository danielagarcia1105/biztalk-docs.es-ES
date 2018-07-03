---
title: Validar datos de instancia | Microsoft Docs
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
ms.openlocfilehash: 939c13c246aaed7db40b723845d6f0a7b95817bd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007157"
---
# <a name="validate-instance-data"></a>Validar datos de instancia

## <a name="overview"></a>Información general
Durante el proceso de prueba de una asignación, quizá desee validar los datos de instancia con respecto a los esquemas de origen y destino para comprobar que esos datos de instancia se ajustan a la estructura del esquema. Para validar un mensaje de instancia con respecto al esquema de origen o destino, haga clic en el esquema en el Explorador de soluciones y, a continuación, haga clic en **Validar instancia**.  

> [!IMPORTANT]
>  Si en la salida utiliza constantes o datos personalizados, debe comprobar que los tipos de datos de los datos de prueba de origen y los valores constantes de destino sean válidos. Cuando se valida una asignación, el asignador de BizTalk no comprueba si los datos de instancia infringen los tipos de datos definidos por los esquemas. Esto se hace al probar la asignación o validar los datos de instancia.  

 Para obtener más información acerca de cómo generar y validar los datos de instancia mediante el Editor de BizTalk, consulte [validación y generación de mensajes de instancia](../core/instance-message-generation-and-validation.md) y [validación de instancia](../core/instance-validation.md). . El **valor** propiedad del nodo de un esquema también afecta a cómo BizTalk genera datos de instancia. Para obtener más información, consulte el **propiedades del nodo esquema** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].

## <a name="see-also"></a>Vea también  
- [Generación y validación de mensajes de instancia](../core/instance-message-generation-and-validation.md)   
- [Cómo validar esquemas en Visual Studio](../core/how-to-validate-schemas-in-visual-studio.md)   
- **Referencia de asignación de propiedad** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]  
- [Comprobación de asignaciones](../core/testing-maps.md)
