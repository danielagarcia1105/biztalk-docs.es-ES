---
title: Cómo configurar la forma transformación | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring [Orchestration Designer], Transform shape
- Transform shape [Orchestration Designer]
ms.assetid: ca81d153-77a6-4bcc-b14f-8f48469fffe0
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fc88110940626602059466324d0dc38e59f88afe
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980973"
---
# <a name="how-to-configure-the-transform-shape"></a>Cómo configurar la forma Transformación
![](../core/media/ebiz-orch-transform.gif "ebiz_orch_transform")  
Forma Transformación  
  
 Las transformaciones solo se usan al construir los mensajes, por lo que su **transformar** forma aparece siempre dentro de un **construir mensaje** forma. Puede quitar el **construir mensaje** la forma de la superficie de diseño y, a continuación, coloque el **transformar** forma dentro de él, o puede simplemente soltar la **transformar** forma en el diseño superficie y el Diseñador de orquestaciones creará la envolvente **construir mensaje** forma para usted.  
  
> [!NOTE]
>  Cualquier mensaje de origen o destino en un **transformar** debe basarse en un esquema.  
  
## <a name="procedure"></a>Procedimiento  
  
#### <a name="to-configure-a-transform-shape"></a>Para configurar una forma de transformación  
  
1.  En la ventana Propiedades, haga clic en el **puntos suspensivos** (**...** ) botón el **los mensajes de entrada**, **mensajes de salida**, o **nombre de asignación** propiedad.  
  
2.  Use la **configuración de transformación** cuadro de diálogo para configurar el **transformar** forma.  
  
> [!NOTE]
>  Un **transformar** forma solo puede existir dentro un **construir mensaje** forma. Si arrastra un **asignación de mensajes** en cualquier lugar en la superficie de diseño, dar forma a un nuevo **construir mensaje** forma se creará.  
  
### <a name="important-performance-considerations"></a>Consideraciones importantes de rendimiento  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] optimiza la capacidad de realizar transformaciones en los mensajes grandes al transmitir el documento en la memoria al aplicar la transformación frente a cargar todo el documento en memoria a la vez. Esta optimización permite la asignación/transformación de documentos mucho más grandes que los que permitían versiones anteriores de BizTalk Server. Se produce una limitación de esta optimización cuando una orquestación acepta varias entradas o salidas para formas de transformación.  
  
 Si una orquestación acepta varias entradas o salidas para formas de transformación, no se realiza la transmisión del documento y el uso de la memoria aumenta considerablemente. Una posible solución para este problema sería aplicar las transformaciones en una canalización de recepción, de manera que la orquestación nunca acepte más de una única entrada o una única salida para una forma de transformación.  
  
### <a name="newexisting-map-file"></a>¿Archivo de asignación nueva o existente?  
 En esta sección, puede hacer clic en cualquiera el **nueva asignación** o **mapa existente** botón de opción para seleccionar una asignación para asignar a la **transformar** forma.  
  
 Use la **nombre** campo debajo del botón de opción seleccionado para especificar una asignación. Si seleccionó **nueva asignación**, puede escribir una designación para la asignación que desea asignar. Cuando se usa el **nueva asignación** opción, debe especificar el nombre completo de la asignación en el cuadro de texto. El cuadro de texto muestra un ejemplo de este tipo de nombre de forma predeterminada, porque se rellena previamente con un nombre de identificador único basado en el espacio de nombres del proyecto y **transformar** nombre de la forma: \<espacio de nombres de proyecto\>.\< Nombre de la forma transformación\>_Map (por ejemplo, MyProject.Transform3_Map).  
  
 Si seleccionó **mapa existente**, haga clic en la flecha hacia abajo en la **nombre** campo para seleccionar el archivo de asignación para usar. Este cuadro de lista muestra una lista ordenada alfabéticamente de todas las asignaciones disponibles en el proyecto. En esta lista, si hace clic en el texto \<seleccionar del ensamblado mencionado\>, **Seleccionar tipo de artefacto** se muestra el cuadro de diálogo. Para obtener más información acerca de las selecciones disponible, consulte [cómo usar el cuadro de diálogo Seleccionar tipo de artefacto](../core/how-to-use-the-select-artifact-type-dialog-box.md).  
  
### <a name="select-source-and-destination-messages"></a>Seleccionar mensajes de destino y de origen  
 Utilice esta parte de la **configuración de transformación** cuadro de diálogo para configurar la asignación seleccionada en el **archivo de asignación nueva o existente?** sección. Si seleccionó **nueva asignación** en esa sección, cree que se asignan al configurarla en esta sección.  
  
 Si seleccionó **mapa existente**, puede utilizar esta sección para realizar una de estas dos cosas:  
  
- Seleccionar una asignación existente para volverla a utilizar tal cual en la transformación actual.  
  
- Seleccionar una asignación existente para modificarla (volverla a configurar) y, a continuación, utilizarla con su nueva configuración en la transformación actual.  
  
  Especificar mensajes de origen y destino mediante el **mensajes de origen** y **los mensajes de destino** controles de cuadrícula. Puede utilizar estos controles de cuadrícula para modificar el archivo de asignación de varias maneras. Si elimina un mensaje (una fila de cualquier control de cuadrícula), agrega un mensaje o selecciona un mensaje de un tipo diferente, se altera la estructura de la asignación. Cuando altera la estructura de una asignación, el resto de las transformaciones que la utilizan se tienen que modificar para que coincidan con la nueva estructura de la asignación. Otros cambios, como quitar un mensaje e insertar otro del mismo tipo en su lugar, no altera la estructura de la asignación.  
  
  El **mensajes de origen** y **los mensajes de destino** son idénticos en apariencia y comportamiento de los controles de cuadrícula. Cada control de cuadrícula tiene dos columnas: mensaje y tipo. Seleccione mensajes de la columna Mensaje para rellenar los controles de cuadrícula. (Solo se agregan datos a la columna Mensaje porque la columna Tipo es de solo lectura.) Las celdas de la columna Mensaje tienen listas desplegables que se rellenan con instancias de mensajes que se encuentran dentro del ámbito de la orquestación actual.  
  
  Puede seleccionar una fila en cualquier control de cuadrícula, haga clic en el *flecha derecha* botón (>) en el lado izquierdo del control de cuadrícula. Tras seleccionar una fila, puede eliminarla al presionar la tecla Supr. Eliminar una fila (un mensaje) altera la estructura del archivo de asignación que la contiene. Solo puede modificar archivos de asignación que sean locales del proyecto.  
  
### <a name="when-i-click-ok-launch-the-biztalk-mapper"></a>Iniciar el Asignador de BizTalk al hacer clic en Aceptar  
 Al hacer clic en **iniciar el asignador de BizTalk al hacer clic en Aceptar,** abre automáticamente el asignador de BizTalk al hacer clic en **Aceptar** para cerrar el **configuración de transformación** diálogo cuadro y guardar los cambios. Sin embargo, no puede guardar cambios si falta información necesaria. En este caso, terminar de rellenar los campos en el cuadro de diálogo y, a continuación, haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Acerca de las asignaciones](../core/about-maps.md)   
 [Construcción de mensajes](../core/constructing-messages.md)   
 [Cómo usar expresiones para los mensajes de la transformación dinámica](../core/how-to-use-expressions-to-dynamic-transform-messages.md)