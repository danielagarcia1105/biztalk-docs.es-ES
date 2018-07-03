---
title: Cómo configurar la forma Iniciar orquestación | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring [Orchestration Designer], Start Orchestration shapes
- Start Orchestration shape [Orchestration Designer], parameters
- Start Orchestration shape [Orchestration Designer], configuring
- orchestrations, starting
- Start Orchestration shape [Orchestration Designer]
- Start Orchestration shape [Orchestration Designer], starting orchestrations
- Start Orchestration shape [Orchestration Designer], about Star Orchestration shape
ms.assetid: 9d01c41e-9bc5-4c1c-a869-b2f0df13036a
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4877d775b30f7ab407f57ebf2679f8cb65a0ef08
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974917"
---
# <a name="how-to-configure-the-start-orchestration-shape"></a>Cómo configurar la forma Iniciar orquestación
El **Iniciar orquestación** forma es similar a la **orquestación de llamada** forma, pero invoca otra orquestación de forma asincrónica con el **Iniciar orquestación** forma, es decir, el flujo de control en la orquestación invoca continúa más allá de la invocación, sin esperar a la orquestación invocada termine.  
  
 Puede especificar parámetros que pasarán a la orquestación invocada. Los parámetros pueden ser mensajes, variables, referencias a puertos, vínculos de función o conjuntos de correlaciones. El **Iniciar orquestación** solo puede tomar la forma *en* parámetros; no puede tomar *out* o *ref* parámetros.  
  
> [!CAUTION]
>  Si pasa objetos no serializables como XmlDocument o XmlNode como parámetros a una orquestación, se generará un error.  
  
 El **Iniciar orquestación** forma es la única forma en que puede invertir la polaridad en un puerto que se pasa como parámetro, por ejemplo un *usa* (puerto de envío) se puede pasar a una orquestación invocada, pero la orquestación invocada puede tratarlo como un *implementa* puerto (puerto de recepción). Tenga en cuenta que esto sólo se puede hacer con puertos que usen enlaces directos.  
  
 El **Iniciar orquestación** forma también se puede usar para llamar a una orquestación que se hace referencia en otro proyecto. Esto permite volver a utilizar patrones de flujo de trabajo de orquestaciones comunes en los proyectos de BizTalk. Para que poder llamar a la orquestación que se hace referencia, asegúrese de que el **modificador de tipo** propiedad para la orquestación de llamada se establece en **pública**. Para establecer el **modificador de tipo** propiedad para una orquestación **pública**, abra la orquestación en Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], haga clic en la forma Inicio verde en la parte superior de la orquestación para mostrar el  **Propiedades de orquestación** cuadro de diálogo y establezca el **modificador de tipo** propiedad **pública**. El valor predeterminado de **modificador de tipo** es **privada**.  
  
 Para obtener un ejemplo de cómo usar **Iniciar orquestación** forma, descargue el ejemplo SDK "Implementing Scatter y Gather Pattern" de [ http://go.microsoft.com/fwlink/?LinkId=73703 ](http://go.microsoft.com/fwlink/?LinkId=73703).  
  
### <a name="to-configure-a-start-orchestration-shape"></a>Para configurar una forma Iniciar orquestación  
  
1. Mediante el **selección de orquestación** cuadro de lista desplegable, seleccione una orquestación de la lista.  
  
2. Mediante el **parámetros de orquestación** cuadrícula controlar, especificar argumentos para pasar a la orquestación, según lo especificado en el **selección de orquestación** cuadro de lista desplegable, que se ha iniciado. Para especificar estos argumentos en las celdas de la columna Variable (una variable por celda) puede escribir el nombre de una variable o hacer clic en una variable de la lista desplegable de la celda.  
  
3. Para configurar el **Iniciar orquestación** forma según el servicio y los argumentos que especificó en el cuadro de diálogo, haga clic en **Aceptar**. Para cerrar el **iniciar configuración de orquestación** cuadro de diálogo sin realizar ningún cambio a la **Iniciar orquestación** forma, haga clic en **cancelar**.  
  
   > [!CAUTION]
   >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no admite orquestaciones recursivas. Si Orquestación A llama a Orquestación B o la inicia, ésta no podrá llamar a Orquestación A o iniciarla directamente; tampoco podrá llamar a las orquestaciones que llamen directa o indirectamente a la Orquestación A, ni iniciarlas.  
  
## <a name="orchestration-selection-drop-down-list-box"></a>Cuadro de lista desplegable de selección de orquestación  
 Haga clic en la flecha hacia abajo que se encuentra en el cuadro de lista desplegable para ver las orquestaciones disponibles y seleccionar uno. Esta lista contiene todas las orquestaciones que se pueden iniciar desde la orquestación actual, incluidos los ensamblados a los que se hace referencia.  
  
## <a name="orchestration-parameters-grid-control"></a>Control de cuadrícula de Parámetros de orquestación  
 Especifique los argumentos para pasar a una orquestación con parámetros mediante el **parámetros de orquestación** control de cuadrícula. La cuadrícula tiene cuatro columnas: las Variables de ámbito, nombre de parámetro, tipo de parámetro y dirección del parámetro. Sólo puede realizar cambios en la primera columna; el resto de columnas es de sólo lectura.  
  
 Cuando selecciona una orquestación válida, sus parámetros rellenan las columnas del nombre, del tipo y de la dirección del parámetro del control de cuadrícula. A continuación, seleccione las variables de cada fila para que pasen como argumentos. Estas variables se seleccionan de la lista desplegable que se encuentra en cada celda de la columna Variables en ámbito. Esta lista muestra todas las variables disponibles del tipo especificado en la celda Tipo de parámetro adyacente. Si sólo hay un objeto de ese tipo disponible, la celda Variables en ámbito se rellena de forma automática con el objeto. Asimismo, puede especificar que una celda Variables en ámbito seleccione una variable que esté disponible en la lista desplegable.  
  
> [!NOTE]
>  Dado que un **Iniciar orquestación** forma inicia una orquestación, los "parámetros de orquestación" que seleccione en este cuadro de diálogo realmente hacen referencia a variables de orquestación.  
  
 Si una orquestación que está ejecutando no tiene parámetros definidos, el control de cuadrícula del cuadro de diálogo no estará disponible.  
  
## <a name="in-this-section"></a>En esta sección  
 [Cómo crear suscripciones de recepción en Orquestaciones invocadas](../core/how-to-create-receive-subscriptions-at-invoked-orchestrations.md) 
  
## <a name="see-also"></a>Vea también  
 [Cómo configurar la forma de orquestación de llamada](../core/how-to-configure-the-call-orchestration-shape.md)