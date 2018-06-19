---
title: Cómo usar el cuadro de diálogo de tipo de artefacto seleccione | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Select Artifact Type dialog box
- artifacts, Select Artifact Type dialog box
- Orchestration Designer, items
ms.assetid: f0f767f1-4130-4ff0-a898-a089343ee71f
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 88167cbeb5c8c6bb0a62030e64f4ed3d91a9d1aa
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25971634"
---
# <a name="how-to-use-the-select-artifact-type-dialog-box"></a>Cómo usar el cuadro de diálogo de tipo de artefacto Select
Un *elemento* se usa para configurar los elementos de una orquestación en el Diseñador de orquestaciones. Los esquemas, las asignaciones, las canalizaciones, los tipos de puerto y los tipos de mensajes de varias partes son por ejemplo elementos. Al desarrollar una orquestación y las partes que la componen (por ejemplo, formas Puerto, formas Transformación y mensajes), puede que deba hacer referencia a elementos que no residen en la orquestación actual, pero que se encuentran en el proyecto actual o en otro proyecto compilado en un ensamblado de BizTalk Server. Usa el **Seleccionar tipo de artefacto** cuadro de diálogo para buscar y, a continuación, especificar elementos al configurar un elemento dentro de una orquestación.  
  
 El **Seleccionar tipo de artefacto** cuadro de diálogo está disponible desde varias ubicaciones en el Diseñador de orquestaciones. Puede seleccionar \<seleccionar del ensamblado mencionado\> en una lista desplegable que muestra las opciones de configuración; al hacer clic en este texto se abre el **Seleccionar tipo de artefacto** cuadro de diálogo.  
  
 Para poder seleccionar un elemento, primero debe seleccionar el elemento que desea configurar.  
  
 Puede usar el **Seleccionar tipo de artefacto** cuadro de diálogo para los siguientes fines específicos:  
  
|Acción|Finalidad|  
|------------|-------------|  
|Seleccionar una canalización|Seleccionar una canalización para la propiedad de canalización al configurar un puerto para enlace directo (anticipado).|  
|Seleccionar una asignación|Seleccione una asignación para utilizarla con una **transformar** forma.|  
|Seleccionar un esquema|Seleccionar esquemas en el proyecto al crear tipos de mensajes de varias partes.|  
|Seleccionar un tipo de puerto|Hacer referencia a tipos de puerto al crear un puerto.|  
|Seleccionar un tipo de mensaje de varias partes|Hacer referencia a tipos de mensaje de varias partes al crear mensajes.|  
|Seleccionar un tipo .NET|Hacer referencia a tipos .NET al crear variables o mensajes.|  
  
 **Panel de referencias**  
  
 El panel de referencias de la **Seleccionar tipo de artefacto** cuadro de diálogo muestra las referencias en el proyecto actual y en otros ensamblados disponibles. Para seleccionar una referencia en este panel, haga clic sobre ella. Para expandir un contenedor en este panel (como el **ensamblados** contenedor), haga clic en el signo más (+) junto a él.  
  
 **Panel de elementos**  
  
 El panel de elementos de la **Seleccionar tipo de artefacto** cuadro de diálogo muestra los elementos incluidos en la referencia seleccionada actualmente en el panel de referencias. El panel de elementos tiene dos columnas, **elemento** y **nombre completo**, que muestran información sobre los elementos de la referencia actual.  
  
### <a name="to-use-the-select-artifact-type-dialog-box"></a>Para usar el cuadro de diálogo Seleccionar tipo de artefacto  
  
1.  Expanda el **referencias** nodo en el panel izquierdo. El panel muestra los proyectos y los ensamblados disponibles.  
  
2.  Expanda el **ensamblados** nodo. Aparecen uno o varios ensamblados, como SYSTEM.DLL y MICROSOFT.BIZTALK.PIPELINES.DLL.  
  
3.  Haga clic en un ensamblado. Si el ensamblado contiene elementos, se mostrarán en el panel derecho. El nombre completo de los elementos se presenta en la columna derecha del panel de la derecha.  
  
    > [!NOTE]
    >  Si el proyecto actual contiene elementos, puede hacer clic en él para ver los elementos y seleccionar uno.  
  
4.  Para seleccionar un elemento en el panel derecho, haga clic en él y, a continuación, haga clic en **Aceptar** para salir del **Seleccionar tipo de artefacto** cuadro de diálogo. Con esta acción, ese elemento se asigna como el tipo del elemento seleccionado. Para cerrar la **Seleccionar tipo de artefacto** cuadro de diálogo sin seleccionar ni asignar un elemento, haga clic en **cancelar**.  
  
## <a name="see-also"></a>Vea también  
 [Formas de orquestación](../core/orchestration-shapes.md)   
 [Cómo agregar formas a orquestaciones](../core/how-to-add-shapes-to-orchestrations.md)   
 [Cómo agregar parámetros a orquestaciones](../core/how-to-add-parameters-to-orchestrations.md)