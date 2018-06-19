---
title: Cómo agregar Functoids básicos a una asignación | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6a81fb73-cccf-4f74-af92-39e4af13e255
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 23a6748a5ce128ef13ce012412e36570e4e01eba
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248988"
---
# <a name="how-to-add-basic-functoids-to-a-map"></a>Cómo agregar functoids básicos a una asignación
Muchos functoids son muy sencillos de utilizar. Estos se denominan aquí functoids básicos para distinguirlos de los functoids de la **avanzadas** categoría. Los functoids básicos comprenden las siguientes categorías: de conversión, acumulativos, de bases de datos, de fecha y hora, lógicos, matemáticos, científicos y de cadena.  
  
 Por regla general, los functoids básicos tienen tipos simples (por ejemplo, números y cadenas) como vínculos de entrada y salida.  
  
 La utilización de un functoid básico supone agregarlo una página de cuadrícula, crear vínculos de entrada al functoid, que provienen de la izquierda, y crear un vínculo de salida del functoid, que sale hacia la derecha. En este tema se proporcionan instrucciones detalladas para estas operaciones.  
  
## <a name="add-a-basic-functoid-to-a-map"></a>Agregar un functoid básico a un mapa  
  
1.  Con el cuadro de herramientas de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] activo, haga clic en la pestaña apropiada para seleccionar la categoría del functoid que desea ver.  
  
     Aparece la lista de functoids disponibles de la categoría seleccionada.  
  
2.  Arrastre el functoid que desea utilizar desde el cuadro de herramientas hasta la ubicación apropiada en una página de cuadrícula.  
  
    > [!NOTE]
    >  El functoid se colocará en la página de cuadrícula mostrada. Si desea colocar el functoid en una página de cuadrícula diferente, necesitará mostrar otra página de cuadrícula en primer lugar.  
  
    > [!NOTE]
    >  Si crea una asignación que utiliza más de un functoid, es necesario tener en cuenta su ubicación relativa de izquierda a derecha. Los functoids se ejecutan de izquierda a derecha. La salida de un functoid solo puede ser la entrada a otro functoid que esté situado más a la derecha.  
  
## <a name="create-input-links-to-a-basic-functoid"></a>Crear vínculos de entrada a un functoid básico  
  
1.  Arrastre un nodo Registro o Campo desde el esquema de origen hasta el functoid básico en la página de cuadrícula mostrada.  
  
     **- O bien-**  
  
     En la página de cuadrícula mostrada, arrastre otro functoid, que esté ubicado más a la izquierda, hasta el functoid básico en el que desea crear un vínculo de entrada.  
  
     **- O bien-**  
  
     Arrastre el functoid básico de la página de cuadrícula mostrada hasta un nodo Registro o Campo del esquema de origen.  
  
     **- O bien-**  
  
     En la página de cuadrícula mostrada, arrastre el functoid básico en el que desea crear un vínculo de entrada hasta otro functoid, que esté ubicado más a la izquierda.  
  
    > [!NOTE]
    >  Mientras se arrastra, el extremo que se mueve del vínculo, en lugar del extremo anclado el vínculo, se convierte en un icono de cruz para permitir más precisa del segundo extremo de destino. Si desplaza el extremo que se mueve del vínculo sobre un objeto que no es un segundo extremo apropiado para ese vínculo, como podría ocurrir si hay una falta de coincidencia en el tipo de datos, el icono de cruz se transforma en un icono que muestra un círculo con una barra diagonal.  
  
2.  Repita el paso 1 tantas veces como sea necesario para establecer el conjunto completo de vínculos de entrada (auque quizás no todo el conjunto de parámetros de entrada) para el functoid básico.  
  
    > [!NOTE]
    >  Existen algunos functoids que no requieren vínculos de entrada. Por ejemplo, el **fecha**, **tiempo**, y **fecha y hora** functoids en el **fecha y hora** categoría de functoid proporciona la fecha actual, tiempo, o fecha y hora, respectivamente, en el que se está procesando un mensaje de instancia. Por lo tanto, no requieren parámetros de entrada del esquema de origen.  
  
    > [!NOTE]
    >  El orden de los parámetros de entrada para muchos functoids es relevante, como se indica en el tema de referencia de functoids correspondiente (consulte **referencia de Functoid** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]). El orden en que se crean los vínculos establece el orden de los parámetros de entrada al functoid. Para obtener más información sobre propiedades de functoid y especificar el orden de los parámetros de entrada de functoid, consulte [editar propiedades de Functoid y parámetros de entrada](../core/editing-functoid-properties-and-input-parameters.md). Para obtener información sobre cómo configurar los parámetros de entrada de un functoid, consulte [cómo configurar parámetros de entrada del Functoid](../core/how-to-configure-functoid-input-parameters.md).  
  
    > [!NOTE]
    >  Asegúrese de que los functoids o el nodo de esquema de origen que desea vincular estén visibles en la página de cuadrícula mostrada o en la ventana de esquema de origen antes de comenzar a vincular.  
  
## <a name="create-the-output-link-from-a-basic-functoid"></a>Crear el vínculo de salida de un functoid básico  
  
1.  Arrastre un nodo Registro o Campo desde el esquema de destino hasta el functoid básico en la página de cuadrícula mostrada.  
  
     **- O bien-**  
  
     En la página de cuadrícula mostrada, arrastre otro functoid, que esté ubicado más a la derecha, hasta el functoid básico en el que desea crear un vínculo de salida.  
  
     **- O bien-**  
  
     Arrastre el functoid básico que está en la página de cuadrícula mostrada hasta un nodo Registro o Campo del esquema de destino.  
  
     **- O bien-**  
  
2.  En la página de cuadrícula mostrada, arrastre el functoid básico en el que desea crear el vínculo de salida hasta otro functoid que esté ubicado más a la derecha.  
  
    > [!NOTE]
    >  Asegúrese de que los functoids y el nodo de esquema de origen que desea vincular ya estén visibles en la página de cuadrícula mostrada y en la ventana de esquema de origen respectivamente antes de comenzar a vincular.  
  
    > [!NOTE]
    >  La vinculación de functoids siempre intenta evitar vinculaciones inapropiadas, como vínculos en los que los tipos de datos de origen y de destino no coinciden.  
  
    > [!NOTE]
    >  Mientras se arrastra, el extremo que se mueve del vínculo (a diferencia del extremo anclado) se transforma en un icono de cruz para permitir alcanzar el objetivo del segundo extremo de forma más precisa. Si desplaza el extremo que se mueve del vínculo sobre un objeto que no es un segundo extremo apropiado para ese vínculo, como podría ocurrir si hay una falta de coincidencia en el tipo de datos, el icono de cruz se transforma en un icono que muestra un círculo con una barra diagonal.  
  
## <a name="see-also"></a>Vea también  
**Referencia de functoid**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]