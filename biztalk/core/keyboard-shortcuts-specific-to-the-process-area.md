---
title: Teclado métodos abreviados específicos para el área de proceso | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- keyboard shortcuts, Orchestration Designer
- Orchestration Designer, keyboard shortcuts
ms.assetid: d993d341-99f2-4788-b1f3-6a8b911e5278
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ba60b23c6c8719789e8de6903dbb538fa5088b08
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262068"
---
# <a name="keyboard-shortcuts-specific-to-the-process-area"></a>Métodos abreviados de teclado específicos para el área de proceso
La siguiente tabla describe la exploración del teclado disponible en el área de proceso, el área central de la superficie de diseño que se utiliza para definir el flujo de procesos de la orquestación.  
  
|Key|Efecto|  
|---------|------------|  
|FLECHA ABAJO|Mueve la selección a la línea de conexión siguiente o a la forma situada más abajo. Si la forma está conectada a varias ramas que aparecen más abajo (como en el caso de una forma Decidir), la selección se mueve hasta la primera forma en la rama del extremo izquierdo.<br /><br /> Si la selección está en la forma Fin de la orquestación, al presionar esta tecla no se produce ningún efecto ya que no hay más formas que aparezcan más abajo.|  
|FLECHA ARRIBA|Mueve la selección a la línea de conexión siguiente o a la forma situada más arriba. Si la forma está conectada a varias ramas que aparecen más arriba, la selección se mueve hasta la última forma en la rama del extremo izquierdo.<br /><br /> Al presionar esta tecla no tiene ningún efecto cuando la **iniciar** forma está seleccionada.|  
|FLECHA IZQUIERDA|Si la selección está en una forma Envío o Recepción y la forma está conectada a un puerto:<br /><br /> -Si la forma tiene un conector de puerto que conduce a un puerto en la superficie del puerto izquierda, foco y la selección se desplazan hacia el conector de puerto de la forma.<br />-Si la forma tiene un conector de puerto que conduce hacia un puerto en la superficie del puerto derecha, al presionar esta tecla no tiene ningún efecto.<br />-Si la forma no tiene ningún conector de puerto, navegación es el mismo que con cualquier otra forma.<br /><br /> Para otras formas (o formas Envío o Recepción que no están conectadas a un puerto):<br /><br /> -Si la selección está en una rama y ésta existe con formas a la izquierda de la rama actual, la selección se mueve a la forma más cercana en la bifurcación a la izquierda.<br />-La clave no tiene ningún efecto en ninguna otra parte de la orquestación.|  
|FLECHA DERECHA|Igual que la tecla FLECHA IZQUIERDA, pero en la dirección opuesta.|  
|INICIO|La selección cambia al conector que va desde la forma Inicio de la orquestación.|  
|END|La selección cambia al conector que va a la forma Fin de la orquestación.|  
|BLOQ NUM + -|Contrae la forma compleja seleccionada.|  
|BLOQ NUM + +|Expande la forma compleja seleccionada.|  
|BLOQ NUM + *|Expande la forma compleja seleccionada más cualquier forma compleja secundaria que pueda tener.|  
  
## <a name="see-also"></a>Vea también  
 [Métodos abreviados de teclado del Diseñador de orquestaciones](../core/orchestration-designer-keyboard-shortcuts.md)