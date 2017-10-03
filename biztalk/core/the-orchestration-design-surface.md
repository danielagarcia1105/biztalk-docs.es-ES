---
title: "La superficie de diseño de orquestación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c5fb190b-60d7-45e4-9883-7b3d2ed6b0c0
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f943c1543cf50e4ecb1f25627cbccd7b4d72eab5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="the-orchestration-design-surface"></a>La superficie de diseño de la orquestación
La superficie de diseño de orquestación es un diseñador visual que se puede usar para crear una orquestación de BizTalk, además de ser el componente central del diseñador de orquestaciones. Es un lienzo en el que puede arrastrar formas desde el cuadro de herramientas y configurar las formas. Como ventana del editor de Visual Studio, ocupa el área de la ventana principal usada por otras ventanas del editor de Visual Studio.  
  
 ![Diseñadores de orquestaciones](../core/media/b96c16e5-58a2-4d8e-b66c-485864846cec.gif "b96c16e5-58a2-4d8e-b66c-485864846cec")  
Superficie de diseño de orquestación  
  
 El nombre de la orquestación se muestra en la pestaña superior de la ventana Superficie de diseño de orquestación y en la barra de título de la ventana Visual Studio.  
  
 La superficie de diseño se divide en tres áreas: el área de proceso y dos superficies de puerto. El área central de proceso contiene formas que describen el flujo de proceso actual de la orquestación. Se encuentra rodeada a ambos lados por superficies de puerto, que contienen formas puerto y el vínculo de función que interactúan con la **enviar** y **recepción** formas en el área de proceso.  
  
 **Área de proceso**  
  
 El Área de proceso es la parte principal de la superficie de diseño de orquestación de diseñador de orquestaciones y siempre se centra horizontalmente en la superficie de diseño de orquestación.  
  
 En cualquier lado del área de proceso ve las superficies de puerto. El **comenzar** forma se coloca en la parte superior de la superficie de diseño y la orquestación se expande hacia abajo cuando se agregan formas.  
  
 **Superficies de puerto**  
  
 Se muestran dos superficies de puerto en la superficie de diseño de orquestación, una a cada lado del área de proceso. Superficies de puerto pueden contener dos tipos de formas: **puertos** y **vínculos de función**. Estas formas de interactúan con el **enviar** y **recepción** formas en el área de proceso.  
  
 No importa qué superficie de puerto se use para una forma; es decir, la forma funciona de forma idéntica tanto en la superficie de puerto derecha como en la superficie de puerto izquierda. Tener dos superficies de puerto en las que colocar puertos nuevos permite crear orquestaciones con menos conectores de entrelazado que, por tanto, son más fáciles de leer.  
  
 Las superficies de puerto se pueden contraer o expandir al hacer doble clic en ellas o al hacer clic en el icono de doble flecha.  
  
> [!IMPORTANT]
>  La mayoría de las tareas del diseñador de orquestaciones requieren que seleccione varios elementos, por ejemplo, esquemas u orquestaciones. Si estos elementos no se encuentran en el proyecto actual, debe recordar agregar una referencia del proyecto al ensamblado que contenga el elemento que desee seleccionar. Para ello, haga clic en el proyecto y seleccione **Agregar referencia**.  
  
 **Compatibilidad con zoom**  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]proporciona la capacidad de acercar o alejar la superficie del Diseñador de orquestaciones. Puede usar la compatibilidad con zoom completando uno de los siguientes pasos:  
  
-   Haga clic en la superficie del Diseñador de orquestaciones y haga clic en el **Zoom** opción de menú. Se puede seleccionar el porcentaje de ampliación que desee aplicar.  
  
-   Use la combinación CTRL + RUEDA DEL MOUSE para acercar o alejar. Mantenga presionado el botón CTRL y gire de forma simultánea la rueda del mouse hacia arriba o hacia abajo. Use la combinación CTRL+RUEDA DEL MOUSE HACIA ARRIBA para alejar y la combinación CTRL+RUEDA DEL MOUSE HACIA ABAJO para acercar.