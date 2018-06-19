---
title: Cómo configurar la forma de orquestación de llamada | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Call Orchestration shape [Orchestration Designer], parameters
- Call Orchestration shape [Orchestration Designer], configuring
- Call Orchestration shape [Orchestration Designer], about Call Orchestration shapes
- configuring [Orchestration Designer], Call Orchestration shapes
- Call Orchestration shape [Orchestration Designer]
- nonserializable objects
- orchestrations, nonserializable objects
- Call Orchestration shape [Orchestration Designer], referencing orchestrations
- orchestrations, parameters
ms.assetid: 718ce2a0-ac08-4662-8b4e-1be279dbc749
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dabb73b3bed616f17c69923799169a7c6ca2b6d0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249708"
---
# <a name="how-to-configure-the-call-orchestration-shape"></a>Cómo configurar la forma Orquestación de llamada
El **orquestación de llamada** forma puede utilizarse para llamar a una orquestación que se hace referencia en otro proyecto de forma sincrónica. Esto permite volver a utilizar patrones de flujo de trabajo de orquestaciones comunes en los proyectos de BizTalk. Cuando se invoca otra orquestación anidada sincrónicamente con la **orquestación de llamada** forma la orquestación envolvente espera a que la orquestación anidada finalice antes de continuar.  
  
 Puede especificar parámetros que pasarán a la orquestación anidada. Los parámetros pueden ser mensajes, variables, referencias a puertos, vínculos de función o conjuntos de correlaciones. Referencias a puertos, vínculos de función y los conjuntos de correlación transmitidos actúan como sobres autodirigidos: que suministran la orquestación anidada información puede usar para enviar información a la orquestación envolvente.  
  
> [!CAUTION]
>  Si pasa objetos no serializables, como XmlDocument o XmlNode, como parámetros a una orquestación, se generará un error.  
  
 Para obtener un ejemplo de cómo usar **orquestación de llamada** forma, consulte [CallOrchestration (ejemplo de BizTalk Server)](../core/callorchestration-biztalk-server-sample.md).  
  
### <a name="to-configure-a-call-orchestration-shape"></a>Para configurar la forma Orquestación de llamada  
  
1.  Mediante el **selección de orquestación** cuadro de lista desplegable, seleccione una orquestación de la lista.  
  
2.  Mediante el **parámetros de orquestación** cuadrícula controlar, especifique argumentos que se pasarán a la orquestación: como se especifica en el **selección de orquestación** cuadro de lista desplegable, que se llama. Para especificar estos argumentos en las celdas de la columna Variable (una variable por celda) puede escribir el nombre de una variable o hacer clic en una variable de la lista desplegable de la celda.  
  
3.  Para configurar el **orquestación de llamada** forma según el servicio y los argumentos que especificó en el cuadro de diálogo, haga clic en **Aceptar**. Para cerrar la **configuración de orquestación de llamada a** cuadro de diálogo sin realizar ningún cambio a la **orquestación de llamada** forma, haga clic en **cancelar**.  
  
    > [!CAUTION]
    >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no admite orquestaciones recursivas. Si Orquestación A llama a Orquestación B o la inicia, ésta no podrá llamar a Orquestación A o iniciarla directamente; tampoco podrá llamar a las orquestaciones que llamen directa o indirectamente a la Orquestación A, ni iniciarlas.  
  
## <a name="referenced-orchestrations"></a>Orquestaciones a las que se hace referencia  
 Para que se pueda llamar a la orquestación a la que se hace referencia, asegúrese de que se han configurado las siguientes propiedades para la orquestación de llamada:  
  
-   Establecer el **modificador de tipo** propiedad **público** para la orquestación invocada. Para establecer el **modificador de tipo** propiedad para una orquestación **público**, abra la orquestación en Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], haga clic en la forma Inicio verde en la parte superior de la orquestación para mostrar el  **Propiedades de orquestación** cuadro de diálogo y establezca el **modificador de tipo** propiedad **público**.  
  
-   Establecer el **activar** propiedad de la forma recepción inicial en la orquestación para **False**.  
  
## <a name="orchestration-selection-drop-down-list-box"></a>Cuadro de lista desplegable de selección de orquestación  
 Haga clic en la flecha hacia abajo que se encuentra en el cuadro de lista desplegable para ver los servicios disponibles y seleccionar uno. Esta lista contiene todos los servicios a los que se pueden llamar desde la orquestación actual, incluidos los ensamblados a los que se hace referencia.  
  
## <a name="orchestration-parameters-grid-control"></a>Control de cuadrícula de Parámetros de orquestación  
 Especifique los argumentos para pasar a una orquestación con parámetros mediante el **parámetros de orquestación** control de cuadrícula. La cuadrícula tiene cuatro columnas: las Variables de ámbito, nombre de parámetro, tipo de parámetro y dirección del parámetro. Sólo puede realizar cambios en la primera columna; el resto de columnas es de sólo lectura.  
  
 Cuando se selecciona una orquestación válida, sus parámetros rellenan las columnas de nombre, tipo y la dirección de parámetro del control de cuadrícula. A continuación, seleccione las variables de cada fila para que pasen como argumentos. Estas variables se seleccionan de la lista desplegable que se encuentra en cada celda de la columna Variables en ámbito. Esta lista muestra todas las variables disponibles del tipo especificado en la celda Tipo de parámetro adyacente. Si sólo hay un objeto de ese tipo disponible, la celda Variables en ámbito se rellena de forma automática con el objeto. Asimismo, puede especificar que una celda Variables en ámbito seleccione una variable que esté disponible en la lista desplegable.  
  
> [!NOTE]
>  Dado que un **orquestación de llamada** forma llama a una orquestación, los "parámetros de orquestación" que seleccione en este cuadro de diálogo realmente hacen referencia a variables de orquestación.  
  
 Si una orquestación a la que está llamando no tiene parámetros definidos, el control de cuadrícula del cuadro de diálogo no estará disponible.  
  
## <a name="see-also"></a>Vea también  
 [Cómo configurar la forma Iniciar orquestación](../core/how-to-configure-the-start-orchestration-shape.md)