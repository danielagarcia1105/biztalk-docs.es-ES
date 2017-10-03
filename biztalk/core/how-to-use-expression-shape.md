---
title: "Cómo usar la forma expresión | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuring [Orchestration Designer], Expression shapes
- Expression shape [Orchestration Designer]
- Expression shape [Orchestration Designer], configuring
- Expression shape [Orchestration Designer], about Expression shape
ms.assetid: 2d702aa9-b824-4f47-a416-70707ce8ef29
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e263454db9674d5bc86b6b7dae1649003f3d129c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-use-expression-shape"></a>Cómo usar la forma Expresión
El **expresión** forma le permite escribir las expresiones de XLANG/s que desee utilizar en la orquestación. Por ejemplo, puede hacer una llamada a .NET para ejecutar un programa externo o, sencillamente, cambiar los valores de las variables de la orquestación.  
  
 Mientras el **expresión** forma es bastante flexible, no es recomendable utilizar lógica de orquestación de alto nivel, que preferentemente sería visible en el propio diseño de orquestación. En general, resulta más fácil de entender y mantener las orquestaciones si su **expresión** formas contienen expresiones simples y modulares.  
  
### <a name="to-configure-an-expression-shape"></a>Para configurar una forma Expresión  
  
1.  Si el Editor de expresiones de BizTalk no está visible, haga clic en el **expresión** forma y haga clic en **Editar expresión** o, en la ventana Propiedades, haga clic en el botón de puntos suspensivos (**...** ) botón la **expresión** propiedad.  
  
2.  En el Editor de expresiones de BizTalk, cree una expresión para asignar valores. Para obtener más información, consulte [requisitos y limitaciones para las expresiones](../core/requirements-and-limitations-for-expressions.md).  
  
## <a name="see-also"></a>Vea también  
 [Lenguaje XLANG-s.](../core/xlang-s-language.md)