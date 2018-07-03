---
title: Cómo copiar, cortar y pegar vínculos y Functoids | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 80b4792a-5ff6-4603-96cd-b3d3d530c12f
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3dcce057f4c3e04eb4974ccd7f8833e2dab8e580
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37016043"
---
# <a name="how-to-copy-cut-and-paste-links-and-functoids"></a>Cómo copiar, cortar y pegar vínculos y functoids
La característica de copiar, cortar y pegar del Asignador de BizTalk permite la reutilización de una relación. En este tema se proporcionan instrucciones detalladas para copiar y cortar functoids y/o vínculos de una asignación, así como pegarlos en ella.  
  
 Puede usar la característica de copiar y pegar cuando desee reutilizar un conjunto de functoids y/o vínculos. Y, cuando desee eliminar la selección de la ubicación existente y moverla a una nueva ubicación, puede usar la característica de cortar y pegar.  
  
> [!IMPORTANT]
>  ¿Cree que las características de cortar y pegar y la característica de mover son similares? Hay una diferencia. Cuando selecciona cortar, solo los functoids o los vínculos de la selección se quitan de la página de cuadrícula de origen. Pero, cuando selecciona mover, todos los functoids y los vínculos de la relación (independientemente de la selección), de forma recursiva, se eliminan de la página de cuadrícula de origen. Para obtener más información acerca de cómo mover una relación, vea [cómo mover una relación entre las páginas de cuadrícula](../core/how-to-move-a-relationship-between-grid-pages.md).  
  
 Cuando copia o corta un conjunto de functoids o vínculos, se conservan los functoids, las etiquetas, los comentarios y los valores constantes (junto con los marcadores correctos) asociados a ese conjunto.  
  
 Solamente se pueden copiar y cortar estos elementos de asignación:  
  
- Vínculo de origen al esquema de destino.  
  
- Vínculo de functoid a nodo de esquema, únicamente si el “functoid” también se selecciona junto con el vínculo  
  
- Vínculo de functoid a functoid, únicamente si ambos functoids se seleccionan junto con el vínculo.  
  
  Puede copiar y pegar functoids y/o vínculos de:  
  
- Dentro de la misma página de cuadrícula de un mapa  
  
- Una página de cuadrícula a las otras del mismo mapa  
  
- Una asignación a las otras de la misma instancia de Visual Studio  
  
- Entre diferentes instancias de Visual Studio  
  
  Las operaciones de cortar y pegar no se pueden deshacer o rehacer. Para obtener más información, consulte [cómo deshacer o rehacer operaciones de usuario](../core/how-to-undo-or-redo-user-operations.md).  
  
  Además de esto, debe tener en cuenta lo siguiente al pegar vínculos:  
  
- Un vínculo entre el esquema de origen y el de destino únicamente se puede pegar si la asignación actual, donde se pega el vínculo, contiene un nodo de origen, así como un nodo de destino cuya XPath es idéntica a la XPath de los nodos de origen y de destino del vínculo que se pega.  
  
- Un vínculo entre el esquema de origen y el de destino únicamente se puede pegar si no hay ningún vínculo existente entre el origen indicado y los nodos de destino.  
  
- Un vínculo de un functoid a un esquema de destino únicamente se puede pegar si existe un nodo de destino cuya XPath sea la misma que la XPath del nodo de destino del vínculo que se pega.  
  
- Un vínculo de un esquema de origen a un functoid únicamente se puede pegar si existe un nodo de origen cuya XPath sea la misma que la XPath del nodo de origen del vínculo que se pega.  
  
> [!NOTE]
>  Cuando selecciona varios elementos (vínculos o functoids) de modo que algunos de ellos no se pueden cortar o copiar, al ejecutar el comando cortar o copiar, la barra de estado de Visual Studio muestra el mensaje de advertencia en el que se indica que no se pudieron cortar o copiar algunos de los elementos seleccionados. El mensaje también muestra información relevante.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Estas instrucciones requieren que se está ejecutando el asignador de BizTalk.  
  
### <a name="to-copy-and-paste-a-relationship"></a>Procedimiento para copiar y pegar una relación  
  
1.  En el Explorador de soluciones, abra el proyecto BizTalk y haga doble clic en el mapa para abrirlo en el Asignador de BizTalk.  
  
2.  Seleccione los functoids y/o los vínculos que desee copiar.  
  
    > [!TIP]
    >  Puede realizar una selección manteniendo presionada la tecla CTRL y seleccionando a continuación los functoids y/o vínculos que desee o bien arrastrando y soltando con el mouse por los vínculos para formar una selección rectangular.  
  
    > [!NOTE]
    >  Puede usar la operación "seleccionar en la cinta" para seleccionar varios vínculos o functoids. Para obtener más información, consulte [cómo seleccionar varios vínculos y Functoids](../core/how-to-select-multiple-links-and-functoids.md).  
  
3.  Haga clic en la selección. y, a continuación, haga clic en **copia**. Como alternativa, puede presionar CTRL+C en el teclado.  
  
    > [!NOTE]
    >  Para obtener una lista de métodos abreviados de teclado, consulte [métodos abreviados de teclado del asignador de BizTalk](../core/biztalk-mapper-keyboard-shortcuts.md).  
  
4.  Coloque el cursor donde desee pegar la selección.  
  
5.  Haga doble clic en la página de cuadrícula y, a continuación, haga clic en **pegar**. También puede seleccionar y presionar CTRL+V en el teclado. Aparece una copia de la selección en la nueva ubicación.  
  
### <a name="to-cut-and-paste-a-relationship"></a>Procedimiento para cortar y pegar una relación  
  
1.  En el Explorador de soluciones, abra el proyecto BizTalk y haga doble clic en el mapa para abrirlo en el Asignador de BizTalk.  
  
2.  Seleccione los functoids y/o los vínculos que desee cortar.  
  
    > [!TIP]
    >  Puede realizar una selección manteniendo presionada la tecla CTRL y seleccionando a continuación los functoids y/o vínculos que desee o bien arrastrando y soltando con el mouse por los vínculos para formar una selección rectangular.  
  
    > [!NOTE]
    >  Puede usar la operación "seleccionar en la cinta" para seleccionar varios vínculos o functoids. Para obtener más información, consulte [cómo seleccionar varios vínculos y Functoids](../core/how-to-select-multiple-links-and-functoids.md).  
  
3.  Haga clic en la selección y, a continuación, haga clic en **cortar**. Como alternativa, puede presionar CTRL+X en el teclado.  
  
    > [!NOTE]
    >  Para obtener una lista de métodos abreviados de teclado, consulte [métodos abreviados de teclado del asignador de BizTalk](../core/biztalk-mapper-keyboard-shortcuts.md).  
  
4.  Coloque el cursor donde desee pegar la selección.  
  
5.  Haga doble clic en la página de cuadrícula y, a continuación, haga clic en **pegar**. También puede seleccionar y presionar CTRL+V en el teclado. La selección se elimina de la ubicación existente y aparece en la nueva ubicación.