---
title: Solución de problemas de varios | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- troubleshooting
ms.assetid: 6ebc1867-b5d3-46de-b3bd-69e570ed2b2c
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 765b32895fa76c0c77b740b76e2e6a03f0571351
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22211180"
---
# <a name="miscellaneous-troubleshooting"></a>Solución de problemas de varios
## <a name="leading-zeroes-validation-is-not-performed-for-fields-that-use-the-checkleadingzeroesinelement-method-to-validate-a-field-in-the-message-validation-policy"></a>Ceros iniciales no se realiza la validación de campos que utilizan el método CheckLeadingZeroesInElement para validar un campo en el mensaje de la directiva de validación.  
  
### <a name="symptom"></a>Síntoma  
 Si se envía un mensaje con ceros a la izquierda en un campo, aunque no se permiten ceros a la izquierda del campo y la directiva de validación incluye una regla para el campo que realiza esta validación, se devuelve ningún error de validación de BRE.  
  
### <a name="possible-cause"></a>Causa posible  
 El **CheckLeadingZeroInElement** método se incluye en una regla de negocios en la directiva de validación para el tipo de mensaje. Este método es desusado. El propósito de la llamada de función es generen un error si no hay un cero inicial en el elemento proporcionado en la llamada de función en la validación. Sin embargo, este método no hace que no puede validarse, incluso si hay un cero inicial en el campo.  
  
### <a name="solution"></a>Solución  
 Si desea comprobar los ceros iniciales, debe implementar la **CheckLeadingZero** en lugar del método la **CheckLeadingZeroInElement** método. **CheckLeadingZero** producirá un error de validación si no hay un cero a la izquierda de la entrada de cadena a la función.  
  
 Para implementar la **CheckLeadingZero** método, debe crear un método personalizado que se invoca el **CheckLeadingZero** método desde dentro de la función personalizada y proporciona a ella como una cadena el valor para que sea validar por ceros iniciales. Esto es porque **CheckLeadingZero** no registra un error, pero en su lugar, simplemente devuelve un valor booleano False si la cadena de entrada no es un campo de número de SWIFT válido o si la entrada de cadena tiene un cero inicial. En caso contrario, devuelve True. El método personalizado, a continuación, puede registrar los errores según corresponda.  
  
## <a name="an-error-is-returned-by-the-message-validation-policy-if-the-swift-number-field-has-a-leading-zero"></a>Se devuelve un error por la directiva de validación de mensaje si el campo de número de SWIFT tiene un cero a la izquierda  
  
### <a name="symptom"></a>Síntoma  
 Si un mensaje se envía con ceros a la izquierda en un campo aunque iniciales se permiten ceros para el campo, se devuelve un error de validación de BRE.  
  
### <a name="possible-cause"></a>Causa posible  
 Esto puede ocurrir si se usa alguno de los métodos siguientes para validar un campo de número de SWIFT en la regla que se trate, normalmente en la parte de la acción de la regla. Esto puede ocurrir en un campo de cantidad, velocidad, el precio o cantidad.  
  
-   **CheckCurrencyAmount**  
  
-   **CheckValidAmount**  
  
-   **CheckValidCurrencyAndPriceCode**  
  
-   **CheckValidSignCurrencyAmount**  
  
-   **CheckValidSignDateCurrencyAmount**  
  
-   **CheckValidSignRate**  
  
-   **IsValidTransactionDetailsCurrencyAmount**  
  
### <a name="solution"></a>Solución  
 Si cualquiera de los métodos en la lista anterior, excepto para **CheckValidSignRate**, se utiliza en la regla en la directiva de validación, habilitar los ceros iniciales como se describe en [compatible con ceros a la izquierda en el campo de cantidad validaciones](../../adapters-and-accelerators/accelerator-swift/supporting-leading-zeros-in-amount-field-validations.md).  
  
 Si el **CheckValidSignRate** método se utiliza en la regla que devuelve este error, es la única manera de admitir ceros a la izquierda quitar esta regla de la directiva de validación. Siga estos pasos para lograr esto:  
  
1.  En el Compositor de reglas de negocio, haga clic en el **versión** nodo para la directiva implementada que contiene una regla mediante el **CheckValidSignRate** método. Haga clic en **Anular la implementación**.  
  
2.  Haga clic en el **versión** nodo para la misma directiva y, a continuación, haga clic en **copia**.  
  
3.  Haga clic en el **Validation_Policy** nodo para la misma directiva y, a continuación, haga clic en **pegar**.  
  
4.  Expanda la nueva versión que no haya guardado de la directiva. Haga clic en la regla que tiene el **CheckValidSignRate** llamada al método y, a continuación, haga clic en **eliminar**.  
  
5.  Menú contextual nuevo sin guardar la directiva **versión** nodo y, a continuación, haga clic en **guardar**. Haga clic en el mismo nodo y, a continuación, haga clic en **publicar**. Haga clic en el mismo nodo y, a continuación, haga clic en **implementar**.  
  
## <a name="a4swift-database-requires-archiving"></a>Base de datos de A4SWIFT requiere el archivado  
  
### <a name="symptom"></a>Síntoma  
 El [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] base de datos es demasiado grande.  
  
### <a name="possible-cause"></a>Causa posible  
 La tabla de historial en el [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] base de datos no se archiva automáticamente. Esta tabla almacena datos acerca de la reparación de mensajes y nuevo envío, incluido quién llevó a cabo las tareas y los datos acerca de los procesos de orquestación. Esta tabla continuará creciendo como para realizar la reparación de mensajes y las operaciones de envío nuevo.  
  
### <a name="solution"></a>Solución  
 Para limitar el crecimiento de la [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] base de datos, archivarse periódicamente datos fuera de la tabla de historial, mediante el estándar de archivar los procedimientos.  
  
## <a name="see-also"></a>Vea también  
 [Solución de problemas: Problemas y soluciones](../../adapters-and-accelerators/accelerator-swift/troubleshooting-issues-and-resolutions1.md)